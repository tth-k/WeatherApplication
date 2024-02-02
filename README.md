# ☀️날씨 일기 프로젝트
Open Weather Map api를 통해 날씨를 받고 일기 작성, 조회, 수정, 삭제를 할 수 있는 날씨 일기 프로젝트입니다.


## 개요
- 프로젝트 이름 : weatherDaily
- 프로젝트 유형 : 개인 프로젝트
- 프로젝트 지속기간 : 2023.10.16 ~ 2023.10.30
- 개발 언어 : Java

## 기능 설명
1. 일기
   - 생성 API
     - POST / create / diary
     - 파라미터 : 날짜는 date(형식 : yyyy-mm-dd) / 일기는 text
     - 정책 : 외부 API 에서 받아온 날씨 데이터와 함께 DB에 저장한다.

   - 조회(하루)API
      - GET / read / diary
      - 파라미터 : date
      - 성공 응답 : 해당 기간의 일기를 List 형태로 반환
   
    - 조회(기간)API
      - GET / read / diaries
      - 파라미터 : startDate, endDate(조회기간의 시작일과 종료일)
      - 성공 응답 : 해당 기간의 일기를 List 형태로 반환

    - 수정 API
      - PUT / update / diary
      - 파라미터 : 날짜는 date, 수정 할 새 일기글은 text
      - 정책 : 해당 날짜의 첫번째 일기 글을 새로 받아온 일기글로 수정
     
    - 삭제 API
      - DELETE / delete / diary
      - 파라미터 : 날짜는 date
      - 정책 : 해당 날짜의 모든 일기를 삭제
     
2. 부가 기능
   - 매일 새벽 1시에 날씨 데이터를 외부 API 에서 받아다 DB에 저장해두는 로직 구현
   - logback 을 이용하여 프로젝트에 로그 남김
