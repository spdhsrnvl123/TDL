# 화살표 함수 기본

함수 표현식보다 단순하고 간결한 문법으로 함수를 만들 수 있는 방법이 있다.

바로 화살표 함수(arrow function)를 사용하는 것이다. 화살표 함수라는 이름은 문법의 생김새를 차용해 지었다.

```js
let func = (arg1, arg2, ...argN) => expression;
```

이렇게 코드를 작성하면 인자 `arg1..argN`를 받는 함수 `func`이 만들어진다. 함수 `func`는 화살표(`=>`)우측의 `표현식(expression)`을 평가하고, 평가 결과를 반환한다.

아래 함수의 축약 버전이다.

```js
let func = function (arg1, arg2, ...argN) {
  return expression;
};
```

구체적인 예시

```js
let sum = (a, b) => a + b;
/*위 화살표 함수는 아래 함수의 축약 버전
let sum = function(a,b){
    return a + b;
};
*/
alert(sum(1, 2)); //3
```

`(a,b) => a + b`는 인수 a와 b를 받는 함수이다. `(a,b)=>a+b`는 실행되는 순간 표현식 `a+b`를 평가하고 그 결과를 반환한다.

- 인수가 하나밖에 없다면 인수를 감싸는 괄호를 생략할 수 있다. 괄호를 생략하면 코드 길이를 더 줄일 수 있다.<br />
  ex)

```js
let double = (n) => n * 2;
//let double = function(n){return n*2}과 거의 동일하다.
alert(double(3));
```

-인수가 하나도 없을 땐 괄호를 비워놓으면 된다. 다만, 이 때 괄호는 생략할 수 없다.

```js
let sayHi = () => alert("안녕하세요!");
sayHi();
```

화살표 함수는 함수 표현식과 같은 방법으로 사용할 수 있다.<br />
아래 예시와 같이 함수를 동적으로 만들 수 있다.

```js
let age = prompt("나이를 알려주세요.", 18);
let welcome = age < 18 ? () => alert("안녕") : alert("안녕하세요!");

welcome();
```

### 본문이 여러 줄인 화살표 함수

```js
let sum = (a, b) => {
  // 중괄호는 본문 여러 줄로 구성되어 있음을 알려줍니다.
  let result = a + b;
  return result;
  // 중괄호를 사용했다면, return 지시자로 결괏값을 반환해주어야 합니다.
};

alert(sum(1, 2)); // 3
```

### 요약

화살표 함수는 본문이 한 줄인 함수를 작성할 때 유용하다. 본문이 한 줄이 아니라면 다른 방법으로 화살표 함수를 작성해야한다.<br />

- 중괄호 없이 작성: `(...args) => expression` – 화살표 오른쪽에 표현식을 둡니다. 함수는 이 표현식을 평가하고, 평가 결과를 반환합니다.
- 중괄호와 함께 작성: `(...args) => { body }` – 본문이 여러 줄로 구성되었다면 중괄호를 사용해야 합니다. 다만, 이 경우는 반드시 `return` 지시자를 사용해 반환 값을 명기해 주어야 합니다.
- https://ko.javascript.info/arrow-functions-basics
