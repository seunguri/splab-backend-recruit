# 스플랩 백엔드 채용 과제

지원자의 개발 및 협업 역량을 예측하기 위하여 진행합니다.

완성을 원하는 것이 아니라 코드 작성에 대한 과정 및 의도를 보려고 함이니 큰 부담 가지지 않으셔도 됩니다.

해당 프로젝트는 인터뷰에 활용됩니다.

### 과제 기능

해당 과제는 센드타임의 그룹 기능 중 **참여자 초대**를 각색하였습니다. 실제 센드타임을 바탕으로 과제 상황 및 기능을 설명드립니다.

<img width="1439" alt="Screen Shot 2022-11-29 at 1 18 30 PM" src="https://user-images.githubusercontent.com/52988414/208357897-383de7bb-e376-4f6c-a1f6-4f27ecc414cd.png">



센드타임에서는 그룹에 참여자를 초대할 수 있습니다.

그룹 매니저가 참여자 정보를 입력하여 초대장을 발송하면 초대받은 참여자에게 메일이 발송됩니다. 

참여자는 메일에 있는 그룹 참여 링크를 통해 그룹에 참여합니다. 해당 참여 링크는 1회 사용시 만료됩니다.

### 과제 기획

1. 회원 초대 API: `/members/invite` 
    
    DB에 PENDING 상태 회원을 생성합니다.
    
    생성 시에 이름, 전화번호, 이메일은 필수 값입니다.
    
    회원의 인증/인가는 구현하지 않습니다.
    
2. 그룹원 참여 API: `/members/joinMember`
    
    임시 상태 회원을 ACTIVATED 상태로 변경하고 초대 링크를 만료합니다.
    
3. Member
    - member 필수 필드
    
    ```json
    private String name;
    private String phone;
    private String email;
    private InvitaionStatus status;
    ```
    
    InvitaionStatus : enum 
    
    | 값 | 설명 |
    | --- | --- |
    | ACVTIVATED | 활성화 |
    | PENDING | 초대 발송 후 참여 대기 |
4. 초대 링크
    
    초대 링크는 자유롭게 구현해주세요. Member에 포함하거나 별도로 구현해도 무방합니다.
    

## 프레임워크

- Java 11 이상
- Spring Boot 2.6.6 이상
- Gradle
- DB는 가장 편한 것을 사용해주세요. (h2 등)

## 제출 방법

메일을 수신하신 날로부터 3일 뒤 meetime@splab.dev로 repository 주소를 보내주세요.

수신하신 채용 메일에 정확한 일시를 명시하였습니다.

## FAQ

- Q. 제시된 Api path를 따라야하나요?
    
    A. 과제 기획 1,2번에 예시로 제시한 `/members/invite` `/members/join` 를 동일하게 구현하지 않아도 됩니다. 요구사항에 맞게 구현하시면 문제없습니다👍
    

---

추가적인 문의는 safg0421@splab.dev 으로 메일 보내주세요.
