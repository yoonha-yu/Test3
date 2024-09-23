## 1차 요구사항 구현
- [o] 유저가 루트 url로 접속시에 게시글 리스트 페이지(http://주소:포트/article/list)가 나온다.
- [o] 리스트 페이지에서는 등록 버튼이 있고 버튼을 누르면 http://주소:포트/article/create 경로로 이동하고 등록 폼이 나온다.
- [o] 게시글 등록을 하면 http://주소:포트/article/create로 POST 요청을 보내어 DB에 해당 내용을 저장한다.
- [o] 게시글 등록이 되면 해당 게시글 리스트 페이지로 리다이렉트 된다. 페이지 URL 은 http://주소:포트/article/list 이다.
- [o] 리스트 페이지에서 해당 게시글을 클릭하면 상세페이지로 이동한다. 해당 경로는 http://주소:포트/article/detail/{id} 가 된다.
- [o] 게시글 상세 페이지에는 id에 맞는 게시글 데이터와 목록 버튼이 있다. 목록 버튼을 누르면 게시글 리스트 페이지로 이동하게 된다.

## 미비사항 or 막힌 부분
- DataNotFoundException 클래스를 정의해도 오류가 나서 이 방법을 사용하지 않고 지피티를 활용하여 NoSuchElementException 으로 수정해서 코드를 작성하였다.
- html이 아직 익숙하지 않아서 전에 공부했던걸 복사붙여넣기하였다

## UI/UX (화면 캡처본을 복사 붙여 넣기, url 주소 나오도록)
- 게시글 리스트 페이지
- <img width="1321" alt="스크린샷 2024-09-23 오전 11 46 04" src="https://github.com/user-attachments/assets/ce454b71-1a34-460b-b8e9-42724487743d">

- 게시글 등록 폼 페이지
- <img width="1302" alt="스크린샷 2024-09-23 오후 12 24 36" src="https://github.com/user-attachments/assets/6b7870d2-de3f-432d-b79f-03694519c576">


- 
- 게시글 상세 페이지
- <img width="1307" alt="스크린샷 2024-09-23 오전 11 46 56" src="https://github.com/user-attachments/assets/2180b872-2a07-4a45-b06b-e7b09ac19593">

## MVC 패턴
- Model, View, Controller의 세가지 구성요소로 애플리케이션을 구조화하는 디자인 패턴입니다.
모델: 데이터와 비즈니스 로직을 관리합니다.
뷰: 사용자 인터페이스를 표시합니다.
컨트롤러: 사용자 입력을 처리하고 모델과 뷰를 연결합니다.


## 스프링에서 의존성 주입(DI) 방법 3가지 방법
- 1.생성자 주입 (불변성을 보장하고, 필수 의존성을 명확하게 할 수 있습니다.)
- 2.새터 주입(선택적 의존성에 유용하며, 의존성을 변경할 수 있습니다.)
- 3.필드 주입 (직접 필드에 주입합니다. 주로 @Autowired 애노테이션을 사용합니다.)

## JPA의 장점과 단점
- 장점
데이터베이스의 테이블과 자바 객체 간의 매핑을 자동으로 처리하여 개발자가 SQL을 직접 작성할 필요를 줄입니다.
반복적인 CRUD 작업을 간소화하고, 데이터베이스와의 상호작용을 더 쉽게 만들어 개발 속도를 높입니다.
트랜잭션 관리:
JPA는 트랜잭션을 쉽게 관리할 수 있도록 지원하며, 데이터 일관성을 보장합니다.
-단점
ORM이 항상 최적의 성능을 보장하지 않으며, 복잡한 쿼리에 대해서는 직접 SQL을 작성하는 것이 더 효율적일 수 있습니다.
JPA의 개념과 다양한 설정, 기능들을 이해하는 데 시간이 필요할 수 있습니다.
객체 상태 관리와 트랜잭션을 자동으로 처리하다 보니, 복잡한 상태를 추적하는 것이 어려울 수 있습니다.
SQL 쿼리가 자동 생성되기 때문에, 문제가 발생했을 때 어떤 쿼리가 실행되었는지 파악하기 어려울 수 있습니다.


## HTTP GET 요청과 POST 요청의 차이
- GET 요청
주로 데이터를 조회하는 데 사용됩니다. 예를 들어, 서버에서 특정 리소스를 가져올 때 사용됩니다.
URL에 노출되기 때문에 보안이 취약하고, 전송할 수 있는 데이터의 양에 제한이 있습니다.
-POST 요청
주로 데이터를 서버에 제출할 때 사용됩니다. 예를 들어, 폼 데이터를 제출하거나 새로운 리소스를 생성할 때 사용됩니다.
데이터가 URL에 노출되지 않으므로 상대적으로 보안이 더 높고, 더 많은 데이터를 전송할 수 있습니다.

# 2차 요구사항
- [ ] 게시글 상세페이지(http://주소:포트/article/detail/{id})에 수정 버튼이 있다. 수정 버튼을 누르면 게시글을 수정 할 수 있는 폼이나 오고 수정이 가능하다.
- [ ] 게시글 상세페이지에 삭제 버튼이 있다. 삭제 버튼을 누르면 게시글이 삭제가 된다. 삭제 후 리스트 페이지로 리다이렉트 된다.
- [o] 모든 페이지 상단에 루트 디렉토리로 이동하는 버튼이 있다.(예: 로고)
- [o] 모든 페이지 상단에 로그인 상태 표시하는 버튼이 있다.(예: 로그인 / 로그아웃) 
- [o] 모든 페이지 회원가입 버튼이 있다. 버튼을 누르면 회원가입 폼으로 이동한다.
  - [o] 회원가입 폼은 유저ID, 닉네임, 비빌번호, 비밀번호 확인으로 구성된다. 회원가입 버튼을 누르면 데이터 검증 후 회원가입이 된다.
- [o] 로그인 버튼을 누르면 로그인 폼으로 이동한다. 
	- [o] 로그인 페이지는 사용자 유저ID과 비밀번호를 입력하는 폼으로 구성되고 로그인 버튼을 누르면 데이터 검증 후 로그인이 된다.
- [o] 로그아웃 버튼을 누르면 로그아웃이 된다.
- [ ] 유저가 게시글 작성 및 수정  접근시 로그인 여부를 검사하고 본인 글에 대해서만 수정 / 삭제가 가능하다.
- [ ] (선택)메인페이지에 검색 기능이 구현되어야 한다. input 박스에 내용을 적고 검색 버튼을 누르면 해당 문자가 포함된 게시글이 리스트업 되어야 한다.
본인 글에 대해서만 수정 / 삭제가 가능하다.

## 미비사(선택)항 or 막힌 부분
- 아직 수정과 삭재부분을 제대로 공부하지 못해서 하지를 못했습니다

## UI/UX (화면 캡처본을 복사 붙여 넣기, url 주소 나오도록)
- 게시글 리스트 페이지
- <img width="1301" alt="스크린샷 2024-09-23 오후 12 43 23" src="https://github.com/user-attachments/assets/9b78be01-ef25-49f8-8937-ded124f9b7bb">

- 게시글 등록 폼 페이지
- <img width="1298" alt="스크린샷 2024-09-23 오후 12 44 18" src="https://github.com/user-attachments/assets/a62892b2-f691-4641-92fd-f54697139f45">

- 게시글 상세 페이지
- <img width="1282" alt="스크린샷 2024-09-23 오후 12 45 05" src="https://github.com/user-attachments/assets/3200e9de-681f-44bd-8484-9df445518455">

- 로그인 페이지
- <img width="1301" alt="스크린샷 2024-09-23 오후 12 45 25" src="https://github.com/user-attachments/assets/d8cf090d-2c66-4e41-9365-42722419a066">

- 회원가입 페이지
- <img width="1304" alt="스크린샷 2024-09-23 오후 12 45 43" src="https://github.com/user-attachments/assets/7f8d346a-2ccb-4927-be5f-22f3fd869acb">

- (선택) 검색 페이지
댓글(0)
