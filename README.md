# JAVASCRIPT-PRACTICE

기본이 중요하다!!!!!!!!!!!!!!!!!!!!!!!!!!!

------------------------------------------

&nbsp;처음에는 자바스크립트와 HTML따위는 걍 대충 갖다 쓰면 될 줄 알았다. 물론 되긴 됐지만, 역시 아무나 할 수 있는 그런 것이었지,, 개발자라고 할 수 없었다.

    Git 공부를 위해 branch별로 챕터를 나눠서 진행하겠다리..
    또한, Markdown 공부를 겸하겠다..

<hr>

1. 데이터 타입과 연산자
   1. 모든 언어의 기본은 **데이터 타입**을 파악하는 것부터 시작한다.
      1. 기본타입
         1. Number, String, Boolean, undefined, null
      2. 참조타입
         1. Object
            1. Array
            2. Function
            3. 정규표현식(exp)
   2. ```var foo = { name: 'foo', age: 30, gender: 'male'}```에서 foo 변수는 객체 자체를 저장하는 것이 아닌 생성된 객체의 주소를 가르키는 것이다.(참조값을 가르킴)
   3. 자료의 기본형은 함수 내 인자로 넘길 때 복사한 값을 넘기지만, 객체 즉 참조형은 참조값(주소값)을 넘긴다. 그렇기 때문에 기존 기본형 변수는 변하지 않지만 참조값을 변경하면 객체의 값은 바뀐다.
   4. 객체의 부모는 여기서 ``프로토 타입`` 이라고 부른다. 모든 객체는 ``프로토 타입(숨겨진 프로퍼티)``를 갖고 있다.
   5. ``splice()``를 이용하면 배열을 동적으로 삭제할 수 있다. ``golang``의 ``slice``와 같군..
   6. ``==``는 비교하려는 타입이 다를 경우 변환 후 비교하지만, ``===``는 그대로 비교한다.<br/><br/>
2. 함수와 프로토타입 체이닝
   1. 함수 생성법
      1. 함수 선언문(function statment)
         1. 익명 함수(함수명이 없는 자바스크립트의 함수선언)
      2. 함수 표현식(function expression)
         1. 변수형 함수
            1. 실제로 자바스크립트 엔진에서 함수명으로 변수명으로 하여 만들어 준다. 함수명은 선택사항
            2. ***함수선언 뒤에는 ``;``를 붙여주자!!!***
      3. Function() 생성자 함수  
         1. ``new Function(arg1, arg2, argN, functionBody)`` ``argN``은 매개변수, ``functionBody``는 실행된 코드를 포함한 문자열
   2. 하지만 ``함수 호이스팅``때문에 ``함수 표현식``만을 사용할 것을 권장하고 있다.
      1. 함수 호이스팅: 함수 선언문으로 정의된 함수는 scope가 코드의 맨 처음부터 끝이다.
   3. 함수도 **객체**다. 그러므로 함수 내에도 프로퍼티를 지정할 수 있다. 생성될 때 ``생성자``가 최초에 만들어진다.
   4. 함수를 인자로 전달 가능
   5. 함수의 다양한 형태
      1. 콜백함수와
      2. 즉시실행함수(최초 실행되는 초기화 코드에 사용)
      3. 내부함수
         1. 외부에서 접근할 수 없다. 내부함수에서 자신을 감싸고 있는 외부함수에는 접근 가능. 
            1. 하지만 내부함수의 리턴값을 호출해서 받으면 쌉가능
      4. 함수를 리턴하는 함수(자신을 호출해서 재정의가 가능하다)
      5. this바인딩을 쓰는 경우 내부함수 호출일지라도 전역변수를 호출하기 때문에 주의해야 한다.
   6. 자바스크립트 함수는 항상 **리턴값**을 반환한다.
      1. 리턴값을 지정하지 않는 경우, **undefined**값이 리턴된다.
   7. 자바스크립트의 ``OOP``를 이해하기 위해서는 ``Proto type``를 이해하는 것이 중요하다. 해당 ``proto type``의 ``property``에서 해당 메서드를 찾고 없으면 부모 격인 ``ProtoType``의 ``property``에서 매서드를 찾는다.
   8. 프로토타입도 자바스크립트의 객체다.. 그러므로 동적으로 할당이 가능하다.<br/><br/>
3. 실행 컨텍스트와 클로저
   1. 실행 컨텍스트
      1. 실행 가능한 코드를 형상화하고 구분하는 추상적인 개념
      2. 실행 가능한 자바스크립트 코드 블록이 실행되는 환경
      3. 전역 실행 컨텍스트 -> 실행 컨텍스트
   2. 스코프 체인
   3. 클로저의 활용
      1. 특정 함수에 사용자가 정의한 객체의 메서드 연결하기
      2. 함수의 캡슐화
      3. setTimeout()에 지정되는 함수의 사용자 정의
   4. 클로저 사용 시 주의사항
      1. 프로퍼티값 쓰기가 가능하므로, 그 값이 여러 번 호출로 항상 변할 수 있음
      2. 하나의 클로저가 여러 함수 객체의 스코프 체인에 들어가 있는 경우도 있다.
      3. 루프 안에 클로저를 사용할 때는 주의하자