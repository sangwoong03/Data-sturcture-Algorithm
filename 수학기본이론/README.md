## 1. 알고리즘 복잡도

---

알고리즘 성능 평가 5가지 지표 (코딩테스트는 굵은 글씨 중점)

1. 정확성
2. 작업량
3. **메모리사용량**
4. 최적성
5. 효율성 (**시간 복잡도**, 공간 복잡도)

※ 시간 복잡도란?

- 입력 크기의 값에 대해 단위 연산을 몇 번 수행하는지 계산하여, 알고리즘의 수행시간을 평가하는 방법
- 3가지 점근적 표현법
  1. **Ο(빅오)**: 최악의 상황을 고려하여 성능 측정 결과 표현
  2. Θ(세타): 평균적인 경우에서 성능 측정 결과 표현
  3. Ω(오메가): 최선의 상황일 때 성능 측정 결과 표현

빅오표기법 예제

```javascript
  function bigO(n) {
    let sum = 0; // 1회
    sum = n * 2; // 1회
    return sum; // 1회
	  // 총 3회로 O1
  }

  function bigO(arr, n) {
	  let sum = 0; // 1회

    for (let i = 0; i < n; i++) {
      sum += arr[i];
    } // n회

    return sum; // 1회
    // (n+2) → O(n)
  }

  function bigO(arr, n){
    let sum = 0; // 1회

    for (let i = 0 ; i < n , i++) {
      for (let j = 0; j < n; j++>) {
      sum += arr[i][j];
    }
    // n * n회
  return sum; // 1회
  // n^ + 2 → O(n^)
  }


  function bigO(n) {
	  let sum = 0; // 1회

	  for (let i = 0; i < n; i *= 2) {
		  sum += 2;
	  } // n/2회

	  return sum; // 1회
	  // (n/2 + 2) → O(logN)
  }
```

<br>

## 2. 경우의 수

---

완전탐색으로 경우의 수를 푸는 알고리즘

1. 순열: 서로 다른 n개의 원소 중에서 r를 중복 없이 골라 **순서에 따라 나열** 하는 경우의 수

2. 조합: 서로 다른 n개의 원소 중에서 r를 중복 없이 골라 **순서에 상관없이 나열** 하는 경우의 수

<br>

## 3. 점화식 (재귀식)

---

수열에서 이웃하는 두개의 항 사이에 성립하는 관계를 나타낸 관계식

대표적인 점화식 예:

- 등차수열(AP, arithmetic progression): F(n) = F(n-1) + a (a는 상수)
- 등비수열(GS, geometric sequence): F(n) = F(n-1) \* a
- 팩토리얼(!, factorial): F(n) = F(n-1) \* n
- 피보나치 수열(fibonacci numbers): F(n) = F(n-1) + F(n-2)
