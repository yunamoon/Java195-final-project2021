# :pencil2: java-195_final-project : 동영상 학습 사이트 YANADO 
 YANADO는 Spring을 기반으로 AWS s3를 이용하여 제작한, 동영상 영어 학습 사이트 입니다.

# 개발 환경
- spring, java , html , css , javascript , jquery , ajax , oracle DB, jsp , aws s3

# 프로젝트 상세
- 프로젝트 기간 : 2021.04.19 ~ 2021.06.30 ( 기획 26일, 개발 48일)
- 프로젝트 인원 : 5 인 

# 기획 및 설계
- 노션 : https://www.notion.so/YANADO-9706894949a94d91bfdb4c2d1255f184

# 구현 화면 보기 

## 로그인 전 메인 화면
![스크린샷(22)](https://user-images.githubusercontent.com/78346017/127022227-746e0cc2-717b-4fd5-8692-fb9c64f1b80d.png)
<br>
- 로그인 전에는 서비스를 제공하지 않기 때문에 , 로그인 혹은 회원 가입 메뉴만 노출 됩니다.

<br>
<br>


## 회원 가입 및 휴대폰 인증
![스크린샷(33)](https://user-images.githubusercontent.com/78346017/127022302-bb2c7dd5-5086-49ac-b78e-27e439202c58.png)
![스크린샷(34)](https://user-images.githubusercontent.com/78346017/127022303-761bad67-1078-4e07-ad2d-d972626c692a.png)
![스크린샷(35)](https://user-images.githubusercontent.com/78346017/127022307-025819e2-6f7b-4868-8eaf-d0dea263100f.png)
![스크린샷(36)](https://user-images.githubusercontent.com/78346017/127022312-607a1ffa-6770-4804-9159-e03904836cb7.png)
![KakaoTalk_20210727_002114690](https://user-images.githubusercontent.com/78346017/127022330-655f2c68-f2d3-47bb-9d0e-4551e22be223.jpg)
![스크린샷(37)](https://user-images.githubusercontent.com/78346017/127022346-6d6c9a63-28e5-4d34-80da-c1a9599bde0a.png)
<br>
- JOINUS를 클릭하면 회원 가입 JSP로 이동합니다.
- 회원 가입 시에는, ID 중복 확인, Password 일치 확인, 휴대폰 인증이 이루어집니다.
- 휴대폰 인증 시에는 전송 받은 인증 번호와 등록한 인증번호가 일치해야 합니다.
<br>
<br>

## 로그인 및 로그아웃 
![스크린샷(23)](https://user-images.githubusercontent.com/78346017/127022459-9efe826d-7826-4e1a-b2a1-fb923ce69fb1.png)
![스크린샷(24)](https://user-images.githubusercontent.com/78346017/127022462-81b9e3c8-68e8-428c-a6e9-6cddfc5fbfa0.png)
![스크린샷(25)](https://user-images.githubusercontent.com/78346017/127022469-39fd198e-9bcc-408c-ab1f-315fd6b49d21.png)
<br>
- 메인의 login 버튼을 클릭하면 로그인 jsp로 이동합니다.
- login 시, 일치하는 정보가 존재하지 않으면 아이디 또는 비밀번호를 확인하라는 경고 문구가 출력됩니다.
- login 시, 회원 정보가 휴면 또는 탈퇴한 회원으로 확인되면 사용할수 없는 아이디라는 경고 문구가 출력됩니다.
- login 정보가 관리자로 확인되면 관리자 로그인이 이루어집니다.
<br>
<br>
## 소셜 로그인 및 로그 아웃
![스크린샷(29)](https://user-images.githubusercontent.com/78346017/127022492-da3847fe-6c7f-41d2-ab20-8489e7eaa8f8.png)
![스크린샷(30)](https://user-images.githubusercontent.com/78346017/127022503-55be75f5-12fa-4a6e-a43c-929ba48ad567.png)
![스크린샷(32)](https://user-images.githubusercontent.com/78346017/127022526-c08ba6ac-fbd9-484f-83a3-893cfb4ba434.png)
<br>
- login jsp의 kakao login인을 클릭하면 kakao 계정으로 login이 가능합니다.
- 최초 1회는 사이트 정보 제공에 동의해야, 로그인이 가능합니다.
- 로그인 이후 meminfo table에 정보가 존재하지 않는다면, 정보를 저장 한 후 결제 페이지로 이동합니다.
- 로그인 이후 meminfo table에 정보가 존재하지만 결제 정보가 없다면 결제 페이지로 이동합니다.
- meminfo table 내 회원 정보와 결제 정보가 모두 존재한다면 로그인 후 메인으로 이동합니다.
<br>
<br>
## 결제 
![스크린샷(31)](https://user-images.githubusercontent.com/78346017/127022538-25f82986-039f-4787-83f3-e07425992ca3.png)
![스크린샷(27)](https://user-images.githubusercontent.com/78346017/127022542-e6f5a7c1-113c-41da-98f3-cbdf8f984f2a.png)
<br>
- 결제 jsp 내에서 원하는 이용권을 선택하여 결제 가능합니다.
- 결제 성공 시에는 meminfo table의 isPay가 업데이트 됩니다.
- 결제 실패 시에는 결제 실패 알림창이 뜨며, 여전히 사이트 이용이 제한됩니다.
<br>
<br>

## Id / Password 찾기 및 이메일 전송
![스크린샷(39)](https://user-images.githubusercontent.com/78346017/127022603-1328f463-c6a5-48c7-b942-868b4a966245.png)
![스크린샷(42)](https://user-images.githubusercontent.com/78346017/127022611-cf0578c2-f413-49fd-9a64-072a34bb8eb2.png)
![스크린샷(43)](https://user-images.githubusercontent.com/78346017/127022616-ca80e065-0373-47c2-bd72-639193e0c76e.png)
<br>
- login 시도 시에, id나 password를 잊어버렸다면 밑에 있는 Forgot password ? 를 클릭하면 됩니다.
- 클릭 시 id,password 찾기 jsp로 이동합니다.
- 상단의 옵션 버튼을 클릭하면, 원하는 메뉴로 이동합니다.
- id 찾기 시에는 등록한 이메일로 id가 전송됩니다.
- password 찾기 시에는 등록한 이메일로 임시 비밀번호가 전송됩니다.
<br>
<br>

## 회원 정보 수정 
![스크린샷(48)](https://user-images.githubusercontent.com/78346017/127022638-cac12429-cb93-4b0f-9815-042191de9936.png)
<br>
- 회원 정보 수정 페이지 입니다. 


## 로그인 후 메인
![KakaoTalk_20210630_110731445_04](https://user-images.githubusercontent.com/78346017/127023700-8437617b-3407-446c-879c-256cdbe5b1a3.png)
<br>
- 로그인 및 결제가 완료 된 후 확인 할 수 있는 메인 화면 입니다.
- 화면 내에는 최근 시청 기록과 태그 별 영상이 노출됩니다.
<br>
<br>

## 동영상 재생 페이지 
![KakaoTalk_20210630_110731445_10](https://user-images.githubusercontent.com/78346017/127022685-d0f6c3ed-e904-4b9d-a961-a74039ecb7cd.png)
<br>
- 동영상 재생 페이지입니다. 동영상 재생 화면과 오른쪽에 자막 스크롤이 생성되며, 자막 클릭 시 원하는 구간으로 이동이 가능합니다.
- 또한 오른쪽 스크립트 내의 별 모양 아이콘을 클릭하면 북마크를 저장 할 수 있습니다.
- 자막 역시 한글/영어/한영으로 옵션 선택 가능합니다.
- 영상 중지 시 최근 시청 기록이 저장되며, 추후 재생 시 해당 구간부터 이어서 시청 하실 수 있습니다.

## 최근 시청 기록
![KakaoTalk_20210630_110731445_05](https://user-images.githubusercontent.com/78346017/127022699-b1ae23cb-753a-4457-99ec-18f275cd8f9b.png)
<br>
- 마이 페이지 내에서 확인 가능한 최근 시청 기록 입니다.
- 최근 시청 기록은 자동으로 저장됩니다.
- 해당 포스터 클릭 시 시청하던 영상 구간으로 이동하여 이어서 감상 하실 수 있습니다.
<br>
<br>
## 북마크
![KakaoTalk_20210630_110731445_06](https://user-images.githubusercontent.com/78346017/127022725-bc3fc2f0-151b-4ad6-b96b-58f21db3e74b.png)
<br>
- 마이 페이지 내에서 확인 가능한 북마크 입니다.
- 원하는 자막을 저장 할 수 있으며, 클릭 시 해당 자막 구간을 감상 하실 수 있습니다.
<br>
<br>

## Q&A 게시판 
![KakaoTalk_20210630_110731445_12](https://user-images.githubusercontent.com/78346017/127022759-7c67d37e-9328-45fb-9812-a30f7f9f7d63.png)
<br>
- Q&A 멀티 게시판 입니다.
- 화면 내에서 작성, 수정, 삭제가 모두 가능합니다.
- Q&A 게시판의 답변 권한은 관리자 계정으로 로그인 시에만 노출 됩니다.
- 회원은 마이 페이지 내에서 자신이 작성한 Q&A 목록을 확인 할 수 있습니다.
<br>
<br>

## aws s3 비디오 업로드
![스크린샷(50)](https://user-images.githubusercontent.com/78346017/127023585-d5f7aef9-ce26-4234-98ad-1bc1d36b4a5c.png)
<br>
- aws s3 미디어 파일 업로드와 oracle db 업로드 jsp입니다.
- 상단의 informaition file 버튼을 클릭하고 영상 정보가 담긴 파일을 선택하면 해당하는 정보들이 공란에 자동으로 입력 됩니다.
- 또한 원하는 미디어 파일을 해당 input 에 등록한 후 submit 버튼을 클릭하면 aws s3 와 oracle db 데이터 저장이 동시에 이루어집니다.
- aws s3에는 파일 자체가 업로드 되고, oracle db에는 aws s3가 제공하는 미디어 파일 접근 경로가 저장됩니다.
<br>
<br>
<br>
