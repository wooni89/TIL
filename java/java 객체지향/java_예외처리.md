# 예외처리

오류가 발생하더라도 JVM을 멈추지 않고 계속 실행할 수 있게 도와주는 문법
메서드를 실행하는 중에 예외가 발생했을 때 호출자에게 알려주는 문법
메서드를 호출하는 중에 예외를 받았을 때 처리하는 문법

예외처리 문법의 의미

1) 메서드 실행 중에 예외 상황을 만났을 때 리턴 값으로 알려주는 방식의 한계를 극복하기 위해
2) 예외가 발생하더라도 시스템을 멈추지 않고 적절한 조ㅂ₩  치를 취한 후 계속 실행하기 위해

```java
try {
  예외가 발생할 수 있는 코드
} catch (예외정보를 받을 변수/*(파라미터)*/) /*예외정보를 담고있는 객체 주소!*/ {
  예외를 처리하는 코드
}
```

## 예외정보를 담는 클래스의 hierarchy(계층도)

- `Object`
  - `Thowable`
    - 1) catch블록의 파라미터타입으로 선언할 수 있다.
    - 2) throw 명령으로 오류정보를 던질 수 있다.
      - `Error`
        - JVM에서 발생하는 오류 "시스템오류"
        - 개발자는 사용금지
        - 복구불가
          - 적절한 조치 후 즉시 JVM 종료
      - `Exception`
        - App에서 발생하는 오류
        - 애플리케이션 오류(예외)
        - 개발자가 사용가능
        - 복구가능
          - 적절한 조치 후 계속 실행
        - checked 예외
          - 예외처리 코드를 명시적으로 작성했는지 컴파일러가 검사한다.
          - 예외처리를 강제한다.
            - `RuntimeException`
              - uchecked 예외
              - 예외처리코드를 작성했는지 컴파일러가 검사하지 않는다.
              - 코드가 간결해진다
              - 안정성이 떨어진다.

## Exception 예외 다루기

throw

- 예외 상황을 맞이 했을 떄 예외정보를 호출자에 던지는 문법

예외처리 상황

```java

void m1() {
  try {
    m2();
  } catch (Throwable e) {

  }
}

void m2() throws Throwable {

}

```