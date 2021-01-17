# 04-2.Pandas
  - Pandas library 
  - numpy의 업그레이드 버전
## 1. Series
- 1차원 데이터

- 1. 생성
  - pd.Series( data, index(지정 가능), dtype(지정 가능), name(지정 가능) )
    - data에는 리스트, 튜플, 딕셔너리가 올 수 있음
    <br>
- 2. 속성<br>
  --------- numpy와 같은 속성 -------------
  - sr.dtype : 데이터 타입
  - sr.ndim  : 데이터 차원
  - sr.shape : 데이터 구조
  - sr.size  : 데이터 개수<br>
  --------- Series 고유 속성 -------------
  - sr.name : 시리즈 이름
  - **sr.index** : 시리즈 인덱스
  - **sr.values** : 시리즈 값
    - --> **(!중요) sr.index는 index객체, sr.values는 ndarray객체를 반환**
  <br>
 - 3. 인덱싱 슬라이싱
    - (1) value를 기준으로 zero-base인덱싱, 슬라이싱 가능( numpy랑 같다 )
    - (2) **부여된 인덱스**를 기준으로 인덱싱, 슬라이싱 가능, 
      이때 슬라이싱은 끝에 값을 포함한다.
    - (3) **iloc, loc**
    - (4) boolean 인덱싱 : True값만 반환
    <br>
- 4. 연산
  - Series, Series.index에도 사용가능하다.
  - **Series.between**
    - numpy에선 '&'로 사용했던 조건을 between으로 줄 수 있음
  - **Series.isin**
    - numpy에서 '|'로 사용했던 조건을 isin으로 줄 수 있음
  - not은 ~로 주기
    - numpy와 같음
  <br>
- 5. 추가, 수정, 삭제, 검색, 정렬
  - sr.append( )
  - 삭제
    - sr.drop( **index = '부여된 인덱스'** )
  - 정렬
    - sr.sort_index()
    - sr.sort_values()
  - 검색
    - **문자열**
      - 정규표현식: https://wikidocs.net/4308
      - **str속성** 이용
        - sr.str :  문자열 인덱싱 슬라이싱
        - sr.str.contains : 문자열 검색
        - sr.str.replace : 문자열 대체
    <br>
- 6. 통계
  - 주요 속성
    - sr.nlargest(n, keep)
    - sr.idxmax
    - sr.unique
      - *numpy는 arr.unique 인자로 count설정을 줄 수 있음
    - sr.value_counts()
  - **함수 적용**
    - **sr.apply** : 조건별 연산이 가능!!
  - EDA
    - pd.cut( data, bins= , labels ) : 도수분포표
