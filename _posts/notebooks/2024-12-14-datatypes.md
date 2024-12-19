---
title: 데이터의 종류
tags: data
sidebar:
  nav: docs-en
---
# 데이터의 종류
데이터 분석을 위해서는 먼저 데이터가 어떤 종류인지 파악하는 것이 중요하다. 왜냐하면 데이터의 종류에 따라 사용할 수 있는 분석 기법이 달라지기 때문이다.

## 정형 데이터 (Structured Data)

정형데이터의 분류
1. 질적 데이터 (Qualitative Data)
품질, 특성 또는 특성의 유무를 나타내는 비수치적 데이터. 범주형 데이터라고도 불리며, 수학적 계산이 가능하더라도 의미는 없다.

- 명목형 데이터(nominal data): 순서의 개념이 없다.
- 서열형 데이터(ordinal data): 순서의 개념이 있다.

1. 양적 데이터 (Quantitative Data)
양이나 수치를 나태낼 수 있는 데이터로, 수학적 계산이 가능한 데이터.

- 연속형 데이터 (Continuous Data): 실수와 같이 연속적인 수치를 나타내는 데이터
- 이산형 데이터 (Discrete Data): 정수와 같이 불연속적인 수치를 나타내는 데이터.


## 비정형 데이터 (Unstructured Data)

텍스트나 음성, 비디오와 같이 구조가 없거나 제한적인 구조를 가지고 있지 않은 데이터

## 반정형 데이터 (Semi-Structed Data)

일정한 형식을 지니고 있지만 완전한 정형 데이터는 아닌 데이터


```python
import pandas as pd
df = pd.read_csv('data/titanic.csv')
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>PassengerId</th>
      <th>Survived</th>
      <th>Pclass</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>SibSp</th>
      <th>Parch</th>
      <th>Ticket</th>
      <th>Fare</th>
      <th>Cabin</th>
      <th>Embarked</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>0</td>
      <td>3</td>
      <td>Braund, Mr. Owen Harris</td>
      <td>male</td>
      <td>22.0</td>
      <td>1</td>
      <td>0</td>
      <td>A/5 21171</td>
      <td>7.2500</td>
      <td>NaN</td>
      <td>S</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>1</td>
      <td>1</td>
      <td>Cumings, Mrs. John Bradley (Florence Briggs Th...</td>
      <td>female</td>
      <td>38.0</td>
      <td>1</td>
      <td>0</td>
      <td>PC 17599</td>
      <td>71.2833</td>
      <td>C85</td>
      <td>C</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>1</td>
      <td>3</td>
      <td>Heikkinen, Miss. Laina</td>
      <td>female</td>
      <td>26.0</td>
      <td>0</td>
      <td>0</td>
      <td>STON/O2. 3101282</td>
      <td>7.9250</td>
      <td>NaN</td>
      <td>S</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>1</td>
      <td>1</td>
      <td>Futrelle, Mrs. Jacques Heath (Lily May Peel)</td>
      <td>female</td>
      <td>35.0</td>
      <td>1</td>
      <td>0</td>
      <td>113803</td>
      <td>53.1000</td>
      <td>C123</td>
      <td>S</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>0</td>
      <td>3</td>
      <td>Allen, Mr. William Henry</td>
      <td>male</td>
      <td>35.0</td>
      <td>0</td>
      <td>0</td>
      <td>373450</td>
      <td>8.0500</td>
      <td>NaN</td>
      <td>S</td>
    </tr>
  </tbody>
</table>
</div>



여기서 성별(Sex)는 `male`, `female`값을 갖고 수학적 계산을 할 수 없고 순서의 개념도 없는 명목형 데이터이다.
보통의 경우 갯수를 세는  방식으로 분석을 한다.


```python
df['Sex'].value_counts().plot.bar()
```




    <Axes: >




    
![Jupyter Notebook Plot](/assets/notebooks/2024-12-14-datatypes_files/2024-12-14-datatypes_4_1.png)
    


요금(Fare)의 경우 실수 값을 갖고 수학적 계산이 가능하며 연속적인 수치값을 갖는 연속형 데이터이다. 평균과 같은 통계값 계산이 가능하다.


```python
df['Fare'].plot.box()
```




    <Axes: >




    
![Jupyter Notebook Plot](/assets/notebooks/2024-12-14-datatypes_files/2024-12-14-datatypes_6_1.png)
    



```python

```
