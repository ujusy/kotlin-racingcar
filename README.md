# kotlin-racingcar

## Step2: 문자열 계산기

### 기능 요구 사항

- 사용자가 입력한 문자열 값에 따라 사칙 연산을 수행할 수 있는 계산기를 구현해야 한다.
- 문자열 계산기는 사칙 연산의 계산 우선순위가 아닌 입력 값에 따라 계산 순서가 결정된다. 즉, 수학에서는 곱셈, 나눗셈이 덧셈, 뺄셈 보다 먼저 계산해야 하지만 이를 무시한다.
- 예를 들어 "2 + 3 * 4 / 2"와 같은 문자열을 입력할 경우 2 + 3 * 4 / 2 실행 결과인 10을 출력해야 한다.

### 기능 구현

- [x] 덧셈
- [x] 뺄셈
- [x] 곱셈
- [x] 나눗셈
    - [x] 0으로 나눌 수 없다
- [x] 입력값이 null이거나 빈 공백 문자일 경우 `IllegalArgumentException`
    - [x] 입력값의 배열의 길이가 짝수인 경우 `IllegalArgumentException`
- [x] 사칙연산 기호가 아닌 경우 `IllegalArgumentException`
- [x] 각 함수에 대한 test

## Step3: 자동차 경주

### 기능 요구 사항

초간단 자동차 경주 게임을 구현한다.

- 주어진 횟수 동안 n대의 자동차는 전진 또는 멈출 수 있다.
- 사용자는 몇 대의 자동차로 몇 번의 이동을 할 것인지를 입력할 수 있어야 한다.
- 전진하는 조건은 0에서 9 사이에서 무작위 값을 구한 후 무작위 값이 4 이상일 경우이다.
- 자동차의 상태를 화면에 출력한다. 어느 시점에 출력할 것인지에 대한 제약은 없다.

### 기능 구현

- [x] 자동차 수와 횟수를 입력받을 수 있다.
- [x] 입력이 숫자가 아닐경우 `IllegalArgumentException`
- [x] 0-9 까지의 무작위 값을 반환할 수 있다.
- [x] 4 이상일 경우 전진한다.
- [x] 결과를 출력할 수 있다.

## Step4: 자동차 경주 (우승자)

### 기능 구현

- [x] 각 자동차에 이름을 부여할 수 있다. 자동차 이름은 5자를 초과할 수 없다.
    - Car class에서 예외처리
- [x] 전진하는 자동차를 출력할 때 자동차 이름을 같이 출력한다.
- [x] 자동차 이름은 쉼표(,)를 기준으로 구분한다.
    - split
- [x] 자동차 경주 게임을 완료한 후 누가 우승했는지를 알려준다. 우승자는 한 명 이상일 수 있다.
    - maxOf 메서드를 사용하고싶었으나 최초 1개만 반환됨.
    - 따라서 max가 동일한 값으로 여러개일 경우 여러개를 반환할 수 있는 확장 함수 구현

## Step5: 자동차 경주 (리팩토링)

### 변경 사항

- [x] Game class의 winner 함수의 maxPositionCar 변수명 변경
- [x] Game class move 함수 추출하여 테스트 가능하도록 수정 