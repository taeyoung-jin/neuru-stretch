# 느루 - AI 스트레칭 코치 (프로토타입)

자연어로 몸 상태와 목적을 말하면 Claude가 대화하며 맞춤 스트레칭 플랜을 짜주는 웹 프로토타입.

- 데모: https://taeyoung-jin.github.io/neuru-stretch/
- 조건이 갈리는 경우(도구 보유, 공간, 통증 성격)에만 중간 질문
- 기본 동작 DB 38개 + 부족할 때 Claude web search로 DB 외 동작을 출처/영상과 함께 제안
- 동작별 스틱 피겨 반복 애니메이션, 따라하기 타이머 모드
- 위험 신호(저림, 방사통, 최근 수술 등) 감지 시 전문가 상담 권고

## 사용 방법

1. 페이지를 열고 본인의 Anthropic API 키를 입력 (브라우저 localStorage에만 저장, 서버 전송 없음)
2. 몸 상태를 자연어로 입력

## 기술

- 정적 단일 HTML, 프레임워크 없음
- Claude API 직접 호출 (BYOK, `anthropic-dangerous-direct-browser-access`)
- 모델: 정밀 `claude-opus-5` / 빠름 `claude-haiku-4-5`
- 서버 도구 `web_search` 사용 (플랜당 최대 3회)

## 주의

- 프로토타입입니다. 추천 내용은 의료 조언이 아닙니다.
- API 키는 반드시 본인 키를 사용하고, 공용 PC에서는 저장을 끄세요.
