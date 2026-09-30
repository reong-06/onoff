# ON/OFF — Capacitor project

웹 앱(`www/index.html`)을 iOS / Android 네이티브 앱으로 패키징하는 프로젝트입니다.

## 준비물
- Node.js 20+
- iOS: Mac + Xcode (Apple Developer Program 필요)
- Android: Android Studio (Google Play Console 계정 필요)

## 1. 설치
```bash
npm install @capacitor/core @capacitor/cli @capacitor/ios @capacitor/android
npm install -D @capacitor/assets
```

## 2. 앱 ID 바꾸기
`capacitor.config.json` 의 `appId` 를 본인 것으로 수정 (예: `com.hong.onoff`). 한 번 출시하면 바꾸기 어려워요.

## 3. 플랫폼 추가 (최초 1회)
```bash
npx cap add ios
npx cap add android
```

## 4. 아이콘 / 스플래시 생성
`assets/icon.png`(1024x1024), `assets/splash.png`(2732x2732) 를 원하는 이미지로 교체 후:
```bash
npm run icons
```

## 5. 실행
```bash
npm run ios       # Xcode가 열림 → ▶ 로 시뮬레이터/실기기 실행
npm run android   # Android Studio가 열림 → ▶ 실행
```
`www/index.html` 을 수정할 때마다 `npx cap sync` 로 반영하세요.

## 6. 스토어 출시
- iOS: Xcode → Product → Archive → App Store Connect 업로드
- Android: Android Studio → Build → Generate Signed Bundle (.aab) → Play Console 업로드

## 출시 전 체크
- 개인정보처리방침 URL (데이터는 기기 내 저장만 한다고 명시)
- 스토어 스크린샷, 앱 설명 (영문)
- 앱 이름/번들 ID 확인
