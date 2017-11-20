函數
========================================================
author: 郭耀仁
date: 2017-11-20
autosize: true

函數型編程
========================================================

- R 語言本質上是一個函數型語言

> Everything that happens is a function call. By [John Chambers](https://en.wikipedia.org/wiki/John_Chambers_(statistician))

函數型編程（2）
========================================================

- R 語言本質上是一個函數型語言

> R, at its heart, is a functional programming (FP) language. By [Hadley Wickham](http://adv-r.had.co.nz/Functional-programming.html)

自訂函數的外觀
========================================================

```
function_name <- function(輸入 1, 輸入 2, 參數 1, 參數 2, ...) {
  # 一些描述來製作輸出
  return(輸出) #把輸出回傳
}
```

自訂函數
========================================================

- $y = x^2$


```r
# 宣告函數
squared <- function(x) {
  return(x**2)
}

# 呼叫函數
squared(5)
```

```
[1] 25
```

隨堂練習
========================================================

- 自訂 BMI 計算機函數 `BMI_calculator()`，輸入身高、體重就可以得知 BMI

圓形計算機
========================================================


```r
# 宣告函數
circle_calculator <- function(radius, is_area) {
  if (is_area == TRUE) {
    circle_area <- pi * radius**2
    return(circle_area)
  } else {
    circle_circum <- 2 * pi * radius
    return(circle_circum)
  }
}
```

圓形計算機（2）
========================================================


```r
# 呼叫函數
circle_calculator(3, TRUE) # 計算圓面積
```

```
[1] 28.27433
```

```r
circle_calculator(is_area = FALSE, radius = 3) # 計算圓周長
```

```
[1] 18.84956
```

圓形計算機（3）
========================================================

- 參數的預設值


```r
# 宣告函數
circle_calculator <- function(radius, is_area = TRUE) {
  if (is_area == TRUE) {
    circle_area <- pi * radius**2
    return(circle_area)
  } else {
    circle_circum <- 2 * pi * radius
    return(circle_circum)
  }
}
```

圓形計算機（4）
========================================================


```r
# 呼叫函數
circle_calculator(3) # 預設計算圓面積
```

```
[1] 28.27433
```

```r
circle_calculator(is_area = FALSE, radius = 3) # 計算圓周長
```

```
[1] 18.84956
```

圓形計算機（5）
========================================================

- 用 list 資料結構處理多個輸出


```r
# 宣告函數
circle_calculator <- function(radius) {
  circle_area <- pi * radius**2
  circle_circum <- 2 * pi * radius
  list_to_return <- list(
    area = circle_area,
    circum = circle_circum
  )
  return(list_to_return)
}
```

圓形計算機（6）
========================================================


```r
# 呼叫函數
circle_calculator(3)$area
```

```
[1] 28.27433
```

```r
circle_calculator(3)$circum
```

```
[1] 18.84956
```

隨堂練習
========================================================

- 自訂 `length()` 函數
- 自訂 `sum()` 函數
- 自訂 `mean()` 函數

隨堂練習
========================================================

- 自訂函數 is_prime() 判斷輸入的整數是否為質數

回家作業
========================================================

- `count_primes(a, b)` 函數：算出 a、b 之間有幾個質數




```r
count_primes(3, 7)
```

```
[1] 3
```

回家作業
========================================================

- `fib_generator(f1, f2, f_len)` 函數：回傳符合使用者輸入的 Fibonacci 數列




```r
fib_generator(0, 1, 20)
```

```
 [1]    0    1    1    2    3    5    8   13   21   34   55   89  144  233
[15]  377  610  987 1597 2584 4181
```

回家作業
========================================================

- `my_sd(x)` 函數：回傳 x 這個向量中數字的樣本標準差

$$s = \sqrt{\frac{1}{N-1}\displaystyle\sum_{i=1}^{N}(x_i - \bar{x})^2}$$




```r
my_sd(1:100)
```

```
[1] 29.01149
```
