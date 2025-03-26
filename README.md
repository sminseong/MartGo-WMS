# MartGO

## 📌 프로젝트 개요
MartGO는 물류 창고(Warehouse Management System, WMS)의 프로세스를 학습하고 이해하는 것을 목표로 한 프로젝트입니다.
Java와 MySQL을 활용하여 WMS의 핵심 기능을 구현하며, MVC 패턴을 적용하여 구조적인 개발을 경험하고 협업 및 Git을 활용한 프로젝트 관리 역량을 습득하는 것을 목적으로 합니다.


## 🛠 기술 스택
- 언어: Java (JDK 17)

- 데이터베이스: MySQL (8.0)

- 라이브러리:

  - JDBC (MySQL Connector 8.0.17)

  - Lombok

- 패턴 및 설계:

  - MVC (Model-View-Controller) 패턴

  - DAO (Data Access Object) 패턴

  - DTO (Data Transfer Object) 패턴

  - Service Layer 적용


## 🚀 설치 및 실행 방법

### 1️⃣ 필수 요구사항
- Java 17 이상 설치
- MySQL 데이터베이스 설치
- MySQL connector 8.0.17 라이브러리 추가

### 2️⃣ 실행 방법
```sh
# 프로젝트 클론
git clone https://github.com/username/project-name.git

# 프로젝트 빌드 및 실행
cd MartGO
java -jar target/MartGO.jar
```

## 📝 주요 기능

### ✅ 회원 관리

- 회원가입 및 로그인 (일반 회원과 관리자 구분)

- 회원 정보 저장 및 검증

### ✅ 창고 및 섹터 관리

- 창고 및 섹터 생성

- 용적률 관리 (창고 내 섹터의 부피 계산)

- 임대 신청 및 승인 프로세스 (회원 → 창고 관리자 → 총 관리자 승인)

### ✅ 제품 및 재고 관리

- 거래처 회원의 제품 등록 기능

- 입고/출고 요청 및 승인 프로세스

- 재고 변경 이력 관리 (입고 및 출고 시 자동 기록)

### ✅ 입고 및 출고 시스템

- 회원이 입고 신청 → 창고 관리자 승인 → 총 관리자 최종 승인

- 출고 신청 프로세스 (회원 → 창고 관리자 → 총 관리자 승인 후 출고 처리)

### ✅ 데이터 관리

- MySQL을 활용한 데이터 저장 및 관리

- 트리거 및 프로시저를 활용한 데이터 무결성 유지


## 📌역할분담
- 강창선(조장) : 재고, 재고변경, 산출물 관리
- 방민영(팀원) : 임대 관리, 용적률 관리, 창고 및 섹터 생성
- 서민성(팀원) : 입고, 출고 프로세스, 제품 등록 시스템
- 임성빈(팀원) : 로그인, 회원가입


## 📂 프로젝트 구조
```sh
📦 MartGo
 ┣ 📂 src
 ┃ ┣ 📂 common
 ┃ ┃ ┣ 📂 config
 ┃ ┃ ┣ 📂 constans
 ┃ ┃ ┣ 📂 exception
 ┃ ┃ ┣ 📂 utils
 ┃ ┣ 📂 controller
 ┃ ┣ 📂 model
 ┃ ┃ ┣ 📂 dao
 ┃ ┃ ┣ 📂 dto
 ┃ ┃ ┣ 📂 service
 ┃ ┣ 📂 view
 ┗ 📜 README.md
```


## 🛠 데이터베이스 설계

### 📌 테이블 목록

- user (회원 정보)

- admin (관리자 정보)

- warehouse (창고 정보)

- sector (창고 섹터 정보)

- product (제품 정보)

- stock (재고 정보)

- incoming (입고 내역)

- outgoing (출고 내역)

- rent_history (임대 내역)

- stock_history (재고 변경 이력)

- cost_info (창고 및 섹터별 비용 정보)

### 🔗 관계 개요

- user 테이블은 admin 테이블과 연관 (회원이 특정 창고 관리자에 속함)

- product 테이블은 user (거래처)와 연관 (거래처가 제품을 등록 가능)

- stock 테이블은 product, warehouse, sector와 연관

- incoming 테이블은 product, user와 연관 (입고 신청 시 생성)

- outgoing 테이블은 stock, user와 연관 (출고 신청 시 생성)

- stock_history는 incoming 및 outgoing 테이블과 연관 (재고 변경 기록)


## 🛠 예외 처리 및 유효성 검사

- ValidationUtil을 활용하여 유효성 검사 (ID, 비밀번호, 날짜 형식 등)
  
- ErrorCode를 활용하여 에러메시지 출력


## 📜 라이선스
이 프로젝트는 신세계 I&C 6차수 3팀 전먹사에 의해 완성되었습니다.
