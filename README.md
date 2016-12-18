
# 파이썬으로 풀어보는 2017학년도 대학수학능력시험 수학영역


$1.\space 두\space 백터\space \overrightarrow{a}=(1,3),\space \overrightarrow{b}=(5,-6)에\space 대하여\space 벡터 \overrightarrow{a}-\overrightarrow{b}의\space 모든\space 성분의\space 합은?$


```python
import numpy as np
```


```python
a = np.matrix([1,3])
b = np.matrix([5,-6])
np.sum(a-b)
```




    5



$2.\space\lim_{x \rightarrow 0}\frac{e^{6x}-1}{ln(1+3x)}의\space값은?$


```python
from mpmath import *
limit(lambda x: (exp(6*x)-1)/(ln(1+3*x)), 0)
```




    mpf('2.0')



$3.\space \int_{0}^{\frac{\pi}{2}}2\sin \space x \space dx 의 값은?$


```python
from scipy import integrate
f = lambda x: 2*sin(x)
integrate.quad(f,0,pi/2)
```




    (1.9999999999999998, 2.2204460492503128e-14)



$4.\space 두\space 사건\space A와\space B는\space 서로\space 독립이고\\
P(B^{C})=\frac{1}{3}, P(A|B)=\frac{1}{2} \\
일\space 때,\space P(A)P(B)의 값은?\space (단, B^{C}은\space B의\space 여사건이다.)$
> A,B가 서로 독립일때 P(A)P(B)=P(A) 이 성립한다 ([출전:위키피디아](https://ko.wikipedia.org/wiki/%EC%A1%B0%EA%B1%B4%EB%B6%80_%ED%99%95%EB%A5%A0))


```python
PB = 1 - (1/3)
PA = 1/2
PA * PB
```




    0.33333333333333337



5.숫자 1,2,3,4,5 중에서 중복을 허락하여 네 개를 택해 일렬로 나열하여 만든 네 자리의 자연수가 5의 배수인 경우의 수는?

> 5의 배수가 될 수 있는 수는 끝자리가 0 아니면 5가 되어야 하는데 제시된 5개의 숫자중에 0이 없다. 따라서 5x5x5x1


```python
5*5*5*1
```




    125



$6.\space함수\space f(x)=x^3+x+1의\space 역함수를\space g(x)라\space 할때,\space g'(1)의\space 값은?$

> http://j1w2k3.tistory.com/316 에 의하면 역함수의 미분은 원래 함수를 미분한 값의 역과 같아야 하는데... 계산 결과가 보기에 없다. ㅡ,.ㅡ;


```python
from sympy import *
from pynverse import inversefunc
x = symbols('x') #심볼 정의
fx = x**3+x+1    #식 정의
fx1 = (lambda x: diff(fx))
fy1 = inversefunc(fx1)
# 1 / diff(fx).doit().subs({x:1}) #원래 식의 미분에 대해 역을 구했으나...
```


    ---------------------------------------------------------------------------

    ImportError                               Traceback (most recent call last)

    <ipython-input-33-82d8734b7caf> in <module>()
          1 from sympy import *
    ----> 2 from pypi import inversefunc
          3 x = symbols('x') #심볼 정의
          4 fx = x**3+x+1    #식 정의
          5 fx1 = (lambda x: diff(fx))


    ImportError: No module named 'pypi'


7.한 개의 주사위를 3 번 던질 때, 4 의 눈이 한 번만 나올 확률은?

> 4이외의 주사위가 두번 그리고 4가 한번 나올 확률이므로 

$\frac{5*5*1*3}{6^3} = \frac{25}{72}$


```python

```
