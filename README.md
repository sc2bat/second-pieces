# 🎬 second-pieces (세컨즈 피시즈)

> **"하루 1초, 평범한 일상의 조각들을 모아 만드는 나만의 영화"** > `second-pieces`는 매일 1초의 일상을 기록하고, 이 조각들을 모아 30초, 365초의 아름다운 추억 영상으로 병합해 주는 Flutter 기반의 영상 다이어리 앱입니다.

---

## 📌 프로젝트 개요
* **개발 기간:** 2026.06 ~ 진행 중
* **개발 환경:** Linux Mint 22.2 / Flutter Stable (3.44.4)
* **주요 기술:** Flutter, Dart, FFmpeg, Android SDK
* **목표:** 복잡한 영상 편집 과정 없이, 누구나 직관적으로 일상을 아카이빙할 수 있는 MVP 앱 구현

---

## 🛠️ 기술 스택 및 라이브러리 (Tech Stack)

| 분류 | 기술 및 패키지 | 용도 |
| :--- | :--- | :--- |
| **Framework** | `Flutter (Dart)` | 크로스 플랫폼 모바일 앱 개발 |
| **Media Picker** | `image_picker` | 스마트폰 갤러리/카메라 영상 소스 확보 |
| **Video Player** | `video_player` | 영상 편집 구간 선택 및 날짜별 영상 재생 |
| **Video Engine** | `ffmpeg_kit_flutter` | 1초 자르기(Trimming) 및 영상 병합(Merging) 핵심 엔진 |
| **UI Components**| `table_calendar` | 날짜별 기록 상태 시각화 및 다이어리 캘린더 UI |

---

## 📋 핵심 기능 정리 (MVP Roadmap)

현재 기능 개발은 Git 브랜치 전략에 따라 기능별로 분기하여 안전하게 진행 중입니다.

### 1. 영상 자르기 및 저장 엔진 (`feat/video-trimmer`)
* 갤러리에서 동영상 선택 또는 카메라 촬영 기능
* `FFmpeg`를 이용해 선택한 영상의 특정 구간을 정확히 **1초**로 싹둑 자르기
* 잘라낸 1초 영상 파일(`.mp4`)을 앱 내부 로컬 디렉토리에 안전하게 보관

### 2. 메인 다이어리 달력 UI (`feat/diary-calendar`)
* `table_calendar` 기반의 직관적인 메인 홈 화면
* 영상이 기록된 날(초록 불)과 기록되지 않은 날(회색)을 시각적으로 구분
* 날짜 셀 커스텀 인터랙션 구현

### 3. 날짜별 영상 재생 및 관리 (`feat/video-player`)
* 달력에서 특정 날짜 탭 시 그날의 1초 영상 가볍게 재생
* 기록된 영상 삭제 및 다른 영상으로의 교체(재업로드) 기능

### 4. 추억의 영상 병합 기능 (`feat/video-merger`)
* 로컬에 저장된 날짜별 1초 영상을 날짜 순서대로 정렬
* `FFmpeg` 명령어로 여러 조각들을 하나의 완성된 영상(30초, 365초 등)으로 자연스럽게 이어 붙이기
* 최종 완성본을 스마트폰 갤러리에 저장 및 외부 공유

---

## 🚀 개발 환경 세팅 (Getting Started)

리눅스(Linux Mint) 환경에서 이 프로젝트를 빌드하고 실행하는 방법입니다.

```bash
# 1. 저장소 클론
git clone [https://github.com/sc2bat/second-pieces.git](https://github.com/sc2bat/second-pieces.git)
cd second_pieces

# 2. 의존성 패키지 다운로드
flutter pub get

# 3. 안드로이드 에뮬레이터 구동 확인 후 실행
flutter run