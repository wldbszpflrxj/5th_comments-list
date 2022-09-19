# 원티드 프리온보딩 4차 과제

> ## 2팀 소개

<table>
  <tr>
    <td height="50px" align="center"><a href="https://github.com/nknkcho">조남경<br>(팀장)</a></td>
    <td height="50px" align="center"><a href="https://github.com/
hyoungqu23">이형민</a></td>
    <td height="50px" align="center"><a href="https://github.com/hasunghwa">하성화</a></td>
    <td height="50px" align="center"><a href="https://github.com/HaJunRyu">류하준</a></td>
    <td height="50px" align="center"><a href="https://github.com/
wldbszpflrxj">변지윤</a></td>
  </tr>
  <tr>
    <td align="center">Redux 환경 설정 및 적용</td>
    <td align="center">Redux 환경 설정 및 적용</td>
    <td align="center">댓글 CRUD 및 관련 요구사항</td>
    <td align="center">API 추상화 및 UI 마이그레이션</td>
    <td align="center">댓글 호출 및 페이지네이션</td>
  </tr>
</table>

> ## 데모

[🌎 데모 영상]()

> ## 실행 방법

```
yarn install

yarn dev
```

> ## 목차

- [과제 내용](#과제-내용)
- [폴더 구조](#폴더-구조)
- [과제 요구사항 및 해결 방법](#과제-요구사항-및-해결-방법)
- [기술 스택](#기술-스택)

> ## 과제 내용

원티드 프리온보딩 프론트엔드 기업 협업 과제 - 스파크펫

- ### 주제
  - API 서버와 통신해서 작동하는 댓글 프로젝트를 Redux를 통해 구현

- ### 기간
  - 2022년 9월 16일 ~ 9월 19일

> ## 폴더 구조

```
📦
src
├─api
├─assets
├─components
│  └─home
│    ├─CommentList
│    ├─Form
│    └─PageList
├─pages
│  └─Home
├─store
└─styles

```

<br/>

> ## 과제 요구사항 및 해결 방법

### Redux 미들웨어 적용을 위해 Redux-thunk 선택, Redux-logger와 Redux-Devtools 설정

- 애플리케이션 내 공통적으로 실행되어야 하는 코드를 한 곳에서 작동하게 하고, 비동기 처리를 동반한 사이드 이펙트 처리를 위해 미들웨어를 도입하기로 결정   
- 간단한 댓글 CRUD 애플리케이션이고, 과제 마감일자를 고려했을 때 구현 러닝 커브가 상대적으로 낮은 Redux-thunk를 미들웨어로 도입하는 것이 적절할 것으로 판단.  

**해결방법**

- 전체 댓글 불러오기, 댓글 하나의 데이터 불러오기, 댓글 CRUD 관련 Thunk를 작성
- 각각의 기능에 대한 슬라이스를 구현한 뒤, 엑스트라 리듀서를 통해 미들웨어를 세 단계의 비동기 처리(panding, fulfilled, rejected)로 구현

**트러블 슈팅**

- 첫 페이지에서만 CRUD 작업 후 리렌더링이 발생하지 않는 문제
- 원인 : 전체 댓글(comments)과 댓글(comment)의 상태를 하나의 상태로 관리하지 않아 발생하는 문제
- 전체 댓글과 댓글의 상태를 하나의 상태로 관리하지 않은 이유 : 과제 조건이 댓글 작성 및 삭제 이후 첫 페이지로 돌아가도록 구현하는 조건이었기에 DB 상에서의 업데이트만 있다면 리렌더링에 대한 이슈는 없을 것으로 판단, 또한 각각의 상태를 분리하여 작업하는 것이 데이터를 받아 처리하는 과정에서 더 사용하기 편리하지 않을까 판단
- 최종 해결 방법 : 첫 페이지의 경우에만 댓글 작성 및 삭제 시 페이지를 강제로 리로드 하도록 보완

### 댓글 CRUD

- 댓글 작성 후 다른 페이지에 위치하고 있었더라도 1페이지로 이동, 입력 폼 초기화
- 댓글 수정 후 현재 보고있는 페이지 유지, 입력 폼 초기화
- 댓글 삭제 후 1페이지로 이동

**해결방법**

-


### 페이지네이션

-

**해결방법**

-

> ## 기술 스택

![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![redux](https://img.shields.io/badge/Redux-D26AC2?style=for-the-badge&logo=emotion&logoColor=white)
![Redux-Logger](https://img.shields.io/badge/Redux--Logger-0081CB?style=for-the-badge&logo=material-ui&logoColor=white)
![Redux-Devtools](https://img.shields.io/badge/Redux--Devtools-61dafb?style=for-the-badge&logo=Context-API&logoColor=white)