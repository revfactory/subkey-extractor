# 🔐 Google JWT Sub Key 추출기

구글 로그인 후 발급받은 JWT 토큰에서 `sub` key(사용자 고유 ID)를 추출하여 화면에 표시하는 웹 애플리케이션입니다.

## 🌟 주요 기능

- **Google OAuth 로그인**: Google Identity Services를 사용한 안전한 인증
- **JWT 토큰 파싱**: ID 토큰에서 payload를 자동으로 디코딩
- **Sub Key 추출**: 사용자 고유 식별자(sub) 표시
- **추가 정보 제공**: 이메일, 이름, 전체 JWT payload
- **Syntax Highlighting**: 보기 좋은 JSON 형식으로 payload 표시
- **클립보드 복사**: 원클릭으로 정보 복사
- **반응형 디자인**: 모든 디바이스에서 최적화된 UX

## 🚀 사용 방법

### 온라인 사용
https://revfactory.github.io/subkey-extractor

1. 페이지 접속
2. "Google로 로그인" 버튼 클릭
3. Google 계정으로 로그인
4. JWT 토큰의 sub key 및 관련 정보 확인

### 로컬 사용

1. 저장소 클론
```bash
git clone https://github.com/revfactory/subkey-extractor.git
cd subkey-extractor
```

2. 브라우저에서 `index.html` 파일 열기

3. Google Cloud Console 설정
   - [Google Cloud Console](https://console.cloud.google.com/apis/credentials) 접속
   - OAuth 2.0 클라이언트 ID 생성
   - 승인된 JavaScript 원본에 사용할 도메인 추가
   - 생성된 Client ID를 웹페이지에 입력

## 🔧 Google Cloud Console 설정

### 1. OAuth 동의 화면 구성
- User Type: "외부" 선택
- 앱 이름, 사용자 지원 이메일 입력
- 필요한 경우 테스트 사용자 추가

### 2. OAuth 2.0 클라이언트 ID 생성
- 애플리케이션 유형: "웹 애플리케이션"
- 승인된 JavaScript 원본:
  - 로컬 테스트: `http://localhost` 또는 `http://127.0.0.1`
  - GitHub Pages: `https://revfactory.github.io`

### 3. Client ID 설정
생성된 Client ID를 코드의 `DEFAULT_CLIENT_ID` 상수에 설정:
```javascript
const DEFAULT_CLIENT_ID = 'YOUR_CLIENT_ID.apps.googleusercontent.com';
```

## 📋 JWT Payload 예시

```json
{
  "iss": "https://accounts.google.com",
  "sub": "1234567890",
  "email": "user@example.com",
  "email_verified": true,
  "name": "홍길동",
  "picture": "https://...",
  "given_name": "길동",
  "family_name": "홍",
  "iat": 1234567890,
  "exp": 1234567890
}
```

## 🎨 기술 스택

- **Frontend**: HTML5, CSS3, JavaScript (Vanilla)
- **Authentication**: Google Identity Services
- **Styling**: Custom CSS with gradient backgrounds
- **Syntax Highlighting**: Custom JSON formatter

## 🔒 보안

- 모든 인증은 Google OAuth 2.0을 통해 안전하게 처리됩니다
- JWT 토큰은 클라이언트 측에서만 파싱되며 서버로 전송되지 않습니다
- 민감한 정보는 로컬 브라우저에만 저장됩니다

## 📱 지원 브라우저

- Chrome (최신 버전)
- Firefox (최신 버전)
- Safari (최신 버전)
- Edge (최신 버전)

## 🤝 기여

이슈 및 풀 리퀘스트는 언제든 환영합니다!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 라이선스

이 프로젝트는 MIT 라이선스 하에 배포됩니다. 자세한 내용은 [LICENSE](LICENSE) 파일을 참고하세요.

## 👤 작성자

**revfactory**

- GitHub: [@revfactory](https://github.com/revfactory)

## 🙏 감사의 말

- Google Identity Services
- GitHub Pages

---

⭐ 이 프로젝트가 도움이 되었다면 별을 눌러주세요!
