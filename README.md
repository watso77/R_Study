# R_Study

## R Studio 설치

## Trouble shooting 
### Mac에서 csv read시 내용에 한글 포함되어 읽기 실패 시
- 두가지 방법이 있는데, 하나는 시스템의 인코딩을 변경 시켜주는 방법이고, 이것도 안되면 첨부파일 read시 parameter로 fileEncoding을 지정해주면 해결 된다.
  - 시스템 인코딩 설정 : Sys.setlocale("LC_ALL", "ko_KR.UTF-8")
  - 첨부파일 Load시 인코딩 지정 : map<-read.csv("/mapv2_final.csv", header=T,fileEncoding ="euc-kr")

### ggplot에 범례 및 Title에서 한글깨짐 시 처리 방법
1. 내 맥 또는 서버에 한글 글꼴(ttf 폰트)유무 확인 및 설치
  - /Library/Fonts/에 한글 폰트가 없을 경우 https://hangeul.naver.com/font 에서 다운로드 및 설치한다.

2. 위에 추가된 한글 폰트를 R에서 설치 한다. 
  - install.packages("extrafont") 
  - library(extrafont) 
  - font_import()
3. R에서 글꼴 불러오기
  - library(ggplot2) 
  - theme_set(theme_grey(base_family='NanumGothic'))
