#SQL 처리과정

###1. SQL Parsing
  - SQL Parser : 사용자가 던진 SQL을 가장 먼저 받아서 처리하는 엔진
  - Parsing 순서
    1) 개별 구성요소를 분석하고 파싱(tokenize)해서 파싱 트리를 구성
      - 문법적 오류 *Syntax 체크* : 순서, 누락키워드, 사용불가 키워드
    2) 의미상 오류 확인하는 *Semantic 체크*
    3) 문법적 오류가 없고, 의미상 오류가 없으면 해싱 알고리즘을 통해 SQL 커서가 Shared Pool에 캐싱 되어있는지 확인
      - SQL ASCII 텍스트에 대한 숫자 값을 계산한 후, 해시 값으로 변환하여 캐싱 확인
-- Shared Pool에서 찾은 SQL 문장과 수행하려는 SQL문이 100% 일치하더라도 파싱을 요청한 사용자가 다르거나 옵티마이저 관련 파리미터 설정이 다르다면 새로운 SQL 캐시 생성

###2. Optimization (SQL 최적화)
  - Optimizer : 사스템 통계 및 오브젝트 통계 정보를 판단기주으로 삼아 다양한 엑세스 경로를 비교하여 가장 효율적인 *실행 계획*을 선택해주는 DBMS의 *핵심 엔진*
###3. Row-Source Genertaion
###4. Execution

#
