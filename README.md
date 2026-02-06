# 알짜배기 (Alzza) 

<img width="1594" height="892" alt="Image" src="https://github.com/user-attachments/assets/6e251d23-36f7-4325-8290-55235564c6d4" />

> **한 줄 소개**  
> “멈추지 않는 골반을 멈추기 위한” **운동 자세 코칭 서비스**입니다.  
> 휴대폰 기울기(자세/각도) 기반으로 사용자의 운동 자세를 인지하고, 올바른 자세로 돌아오도록 코칭합니다.

- Frontend (Demo): https://realdeal-fe.vercel.app/
- Backend API Docs: https://alzza.cloud/docs

---

## 문제 정의 (Problem)
운동/재활 동작에서 **골반의 미세한 흔들림/틀어짐**은 통증이나 운동 효과 저하로 이어질 수 있습니다.  
하지만 초보자는 **스스로 자세가 무너지는 순간을 인지하기 어렵고**, 매번 트레이너에게 교정받기도 어렵습니다.

---

## 해결 방법 (Solution)
알짜배기는 다음 흐름으로 사용자의 자세를 코칭합니다.

1. **휴대폰 센서(기울기) 기반으로 자세 변화 감지**
2. 특정 임계값(허용 범위)을 벗어나면 **즉시 교정 안내**
3. 사용자의 프로필/기록 기반으로 **개인화된 코칭 경험 제공**

---

## 주요 기능 (Key Features)
- **회원/인증**
  - 회원 가입 및 로그인
- **프로필(Profile)**
  - 사용자의 입력/상태/목표(또는 코칭 데이터)를 저장하고 재사용
- **이력서/경력(Resume)**
  - 사용자의 커리어/학습 자료(또는 결과물) 저장 및 분석 결과 저장
- **회사(Company)**
  - 회사 데이터 저장 및 조회(관심 기업/추천/태그 등 확장 가능)
- **백엔드 문서화**
  - Swagger 기반 API 문서 제공: https://alzza.cloud/docs

> 해커톤 단계에서 핵심은 “자세 감지 → 교정 유도”의 사용자 경험을 빠르게 검증하는 것이며,  
> 데이터 모델은 이후 “운동 루틴/세션/리포트”로 확장 가능하도록 구성했습니다.

---

## 서비스 데모 (Demo)
- Web Frontend: https://realdeal-fe.vercel.app/

---

## 기술 스택 (Tech Stack)
### Frontend
- Vercel 배포
- (프로젝트에 맞게 React/Next.js 등 실제 사용 스택을 여기에 적으면 더 좋아요)

### Backend
- NestJS
- TypeORM
- MariaDB / MySQL 계열(DB)
- Swagger(OpenAPI) 문서화

### Infra / Deployment
- Cloud Run (Backend)
- Cloud SQL (Database)

---

## 아키텍처 (Architecture)
- **Frontend**: Vercel에서 정적/SSR 호스팅
- **Backend**: Cloud Run에서 NestJS API 제공
- **DB**: Cloud SQL(MySQL/MariaDB 호환) 사용  
- **Docs**: `/docs` 경로에서 Swagger UI 제공

---

## API 문서 (API Docs)
- Swagger UI: https://alzza.cloud/docs

---

## 데이터베이스 모델 (Database Model)
현재 핵심 테이블(요약):
- `users`: 사용자 계정 (UUID PK)
- `profiles`: 사용자 프로필 데이터 (userId 유니크)
- `resumes`: 사용자 이력/콘텐츠 및 분석 결과
- `companies`: 회사/기업 정보
