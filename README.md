# mvc2-study

인프런 **김영한의 스프링 MVC 2편 - 백엔드 웹 개발 활용 기술** 학습 저장소입니다.

> 참고: MVC 2편 전체가 아니라 아래 섹션(검증, 예외 처리, 타입 컨버터, 메시지/국제화) 중심으로 학습한 코드가 담겨 있습니다. 타임리프 기본, 로그인 처리, 필터·인터셉터 단독 섹션, 파일 업로드 등은 포함되어 있지 않습니다.

## 강의 / 학습 정보

- 강의: 스프링 MVC 2편 - 백엔드 웹 개발 활용 기술 (김영한)
- 플랫폼: 인프런

## 사용 기술

- Java 11
- Spring Boot 2.4.4
- Spring MVC, Thymeleaf
- Spring Validation / Bean Validation
- Lombok, JUnit 5
- Gradle (Groovy DSL)

## 학습한 내용 (코드 근거)

- 메시지·국제화: `messages.properties`, `messages_en.properties`, `MessageSourceTest`
- 검증(Validation):
  - 직접 검증 → `BindingResult`/`Errors` 활용 → `Validator` 분리 (`ValidationItemControllerV1`~`V4`, `ItemValidator`)
  - Bean Validation: `@Validated`, 검증 그룹(`SaveCheck`/`UpdateCheck`), 폼 객체 분리(`ItemSaveForm`/`ItemUpdateForm`), API 검증 (`ValidationItemApiController`, `BeanValidationTest`)
- 예외 처리:
  - 서블릿 예외 처리와 오류 페이지 (`servlet/ErrorPageController`, `WebServerCustomizer`)
  - API 예외 처리: `HandlerExceptionResolver`, `@ExceptionHandler`, `@ControllerAdvice` (`api/ApiExceptionController`~`V3`, `resolver`, `exhandler/advice`)
  - 필터·인터셉터를 통한 로깅 (`filter/LogFilter`, `interceptor/LogInterceptor`)
- 타입 컨버터:
  - `Converter` 구현(String ↔ Integer, String ↔ IpPort) (`typeconverter/converter`)
  - `Formatter`와 `@NumberFormat` 등 포맷터 (`typeconverter/formatter`)

## 프로젝트 구조

```
mvc2-study/
└── src/main/java/hello/study/
    ├── itemservice/    # 검증 (BindingResult, Bean Validation, 검증 그룹)
    ├── exception/      # 예외 처리 (오류 페이지, ExceptionResolver, ControllerAdvice, 필터/인터셉터)
    └── typeconverter/  # 타입 컨버터 (Converter, Formatter)
```
