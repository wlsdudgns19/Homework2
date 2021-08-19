**<1차 과제 수정 내용>**
 - 1차 과제 수행 중 spring연동에 문제가 있었습니다.
 - 계속 재설치하고 찾아보다가 이후 root-context.xml에서 내가 설정해둔 MariaDB 비밀번호로 수정해 주었습니다.
 - 이후 제대로 연동되어 동작하였습니다.

<hr/>

**<2차 과제>**

1.	Rest API가 무엇인 지 학습하고 Github에 올립니다.
  - REST API란 REST를 기반으로 만들어진 API를 의미. 
  - 우선 REST API를 알기 위해 REST부터 알아봐야 한다.
  - REST란? REST(Representational State Transfer)의 약자로 자원을 이름으로 구분하여 해당 자원의 상태를 주고받는 모든 것을 의미.
  - 즉 REST란 
    * HTTP URI(Uniform Resource Identifier)를 통해 자원(Resource)을 명시하고,
    * HTTP Method(POST, GET, PUT, DELETE)를 통해
    * 해당 자원(URI)에 대한 CRUD Operation을 적용하는 것을 의미.
  - CRUD Operation이란
    * CRUD는 대부분의 컴퓨터 소프트웨어가 가지는 기본적인 데이터 처리 기능인 Create(생성), Read(읽기), Update(갱신), Delete(삭제)를 묶어서 일컫는 말.
    * Create: 데이터 생성(POST), Read: 데이터 조회(GET), Update: 데이터 수정(PUT), Delete: 데이터 삭제(DELETE)
  - REST 구성 요소
    * 자원(Resource): HTTP URI
    * 자원에 대한 행위(Verb): HTTP Method
    * 자원에 대한 행위의 내용(Representations): HTTP Message Pay Load
  - REST의 특징
    * Server-Client(서버-클라이언트 구조)
    * Stateless(무상태)
    * Cacheable(캐시 처리 기능)
    * Layered System(계층화)
    * Uniform Interface(인터페이스 일관성)
  - REST API란? REST의 원리를 따르는 API를 의미
  - REST API를 올바르게 설계하기 위해서는 지켜야 하는 몇가지 규칙이 있으며 해당 규칙이 있다.
  - REST API 설계 예시
    * URI는 동사보다는 명사를, 대문자보다는 소문자를 사용하여야 한다.
    * 마지막에 슬래시 (/)를 포함하지 않는다.
    * 언더바 대신 하이폰을 사용한다.
    * 파일확장자는 URI에 포함하지 않는다.
    * 행위를 포함하지 않는다.
  - RESTful이란?
    * RESTFUL이란 REST의 원리를 따르는 시스템을 의미. 하지만 REST를 사용했다 하여 모두가 RESTful 한 것은 아니다.
    * REST API의 설계 규칙을 올바르게 지킨 시스템을 RESTful하다 말할 수 있으며, 모든 CRUD 기능을 POST로 처리하는 API 혹은 URI 규칙을 올바르게 지키지 않은 API는 REST API의 설계 규칙을 올바르게 지키지 못한 시스템은 REST API를 사용하였지만 RESTful 하지 못한 시스템이라고 할 수 있다.

<hr/>

2.	HTTP 통신에 관하여
-	HTTP란 Hyper Text Transfer Protocol의 두문자어로, 웹 브라우저와 웹 서버가 HTML로 작성된 웹 페이지나 동영상, 음성 파일 등등을 주고받기 위한 프로토콜(통신규약)이다.
-	HTTP에서는 클라이언트가 서버에 요청 메시지를 보내고 이에 대해 서버가 응답 메시지를 반환.
  + 좀 더 쉽게 풀어보면 "서버야 나는 이렇게 줄 테니 너는 이렇게 받고 나는 너가 준 거 그렇게 받을게" 라고 통신 규약에 맞게 데이터를 주고받는 것.
-	HTTP 프로토콜의 특징
  + 서버는 응답 메시지를 반환한 후에 초기 상태로 돌아간다. 이 때 서버는 클라이언트의 상태를 저장하지 않는다.
  + 즉, HTTP 프로토콜은 상태가 없는 프로토콜이다. 여기서 상태가 없다라는 말은 데이터를 주고받기 위한 각각의 데이터 요청이 서로 독립적으로 관리가 된다는 말이고, 이전 데이터 요청과 다음 데이터 요청이 서로 관련이 없다.
  * 이러한 특징 덕분에 서버는 세션과 같은 별도의 추가 정보를 관리하지 않아도 되고, 다수의 요청 처리 및 서버의 부하를 줄일 수 있는 성능 상의 이점이 생긴다.
  * HTTP 프로토콜은 전송 계층 프로토콜로 TCP를 사용하고 네트워크 계층 프로토콜로 IP를 사용하는 것이 일반적이다.
이 두 계층을 합쳐서 TCP/IP라는 이름으로 부르고, TCP/IP에서는 IP주소를 사용해서 통신할 컴퓨터를 결정합니다. 그리고 포트 번호를 사용해서 그 컴퓨터의 어떤 프로그램과 통신할지를 결정합니다. HTTP에서는 기본적으로 80번 포트를 사용한다.
-	HTTP 요청 메시지 (request)
  * 요청 메서드는 송수신 방법을 뜻하며, GET, POST, PUT, DELETE 등이 요청 메서드에 속한다.
  * 웹 페이지에서는 대부분의 통신에 GET 메서드를 사용하며, 폼 등을 사용해서 데이터를 전송할 때는 POST 메서드를 사용한다.
    +	GET (존재하는 자원에 대한 요청)
    +	POST (새로운 자원을 생성)
    +	PUT (존재하는 자원에 대한 변경)
    +	DELETE (존재하는 자원에 대한 삭제)
-	HTTP 응답 메시지 (response)
  * 상태 코드는 특정 HTTP 요청이 성공적으로 완료되었는지를 뜻합니다. 아래는 주요 상태 코드와 상태 설명의 목록이다.
    +	상태코드 200: 성공
    +	상태코드 401, 403, 404, 408: 클라이언트 오류
    +	상태코드 500, 403: 서버 오류
-	HTTP 정리
  * HTTP란 브라우저와 서버가 통신할 수 있도록 만들어주는 여러 프로토콜 가운데 한 종류. 
  * 클라이언트와 서버 간 요청과 응답이 이루어지는 과정.
    +	서버는 클라이언트의 요청에 대해 무조건 응답을 돌려주어야 한다.
    +	서버로 데이터를 전송하여 새로운 리소스를 생성하고자 할 때 사용해야 하는 HTTP 메서드는 POST가 있다.
  * HTTP 통신에는 stateless, connectionless 라는 두 가지 속성이 있다.
    +	stateless (무상태성)는 모든 http 요청은 독립적이므로 서버는 클라이언트의 상태를 기억하지 못해서 지속적인 state라는 것이 없다는 속성이다.
    +	connectionless (무연결성)는 응답이 완료가 되면 클라이언트와 서버의 연결이 끊어지는 특징을 가진 속성이다.

<hr/>

3.	브라우저에 URL을 입력 후 요청하여 서버에서 응답하는 과정까지에 대해 학습한 내용을 작성
-	우선 웹 부라우저에 URL을 입력하고 Enter.
-	이후 바로 URL의 주소로 이동, 웹 브라우저가 입력한 URL을 분석하며 일을 시작
-	URL 분석
  * URL구조가 맞으면 사용 중인 웹 브라우저의 검색엔진으로 입력어를 검색한다.
  * URL구조가 맞지 않으면 HSTS 목록을 받아와 url내의 주소와 목록의 주소가 일치한다면 https로, 그렇지 않으면 http로 첫 요청을 보낸다.
-	DNS에 내가 접근하려는 name주소의 IP주소를 요청한다.
  * Reculsive server의 cache를 먼저 확인한다. 있으면 그 IP 주소를 리턴한다.
  * 없을 경우 DNS 시스템에 따라, Root server - TLD server - Authoriative server에 IP주소를 물어본다.
-	IP주소를 받은 다음, ARP를 통해 실질적으로 내가 접근해야할 IP주소를 할당받은 것의 MAC 주소를 추적한다.
-	대상과 TCP통신을 통해 Socket을 연다.
-	HTTPS => TLS과정 추가
-	HTTP 프로토콜 요청
  * Client가 서버에 HTTP 프로토콜을 요청한다.
  * HTML에서 참조하는 모든 페이지(Image, css, favicon.ico 등)에 대해 이 과정을 반복한다.
-	HTTP의 응답
-	웹 브라우저의 그림 그리기
  *	구문 분석 (HTML, CSS, JS) + 렌더링 (DOM Tree 구성 - 렌더 트리 구성 - 렌더트리 레이아웃 배치 - 렌더트리 그리기)
  *	HTML parsing, CSS parsing, Page Rendering, GPU Rendering을 통해 그림을 그려냄
