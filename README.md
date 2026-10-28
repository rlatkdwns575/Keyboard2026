# 취향 공략집 | 2026 키보드 구매 가이드

사용 목적과 키감을 기준으로 키보드를 찾아보는 웹페이지입니다. 키보드와 커스텀 부품 37개를 실제 제품 이미지로 비교하고, 제품 카드를 눌러 공식 페이지나 구매 페이지로 이동할 수 있습니다.

## 주요 기능

- 가성비, 풀배열, 알루미늄, 무접점, 자석축, 커스텀 분류
- 모델명·브랜드 검색 및 추천 제품만 보기
- 용도별 조건에서 제품을 찾아가는 선택 맵
- 제품 카드 클릭 시 공식·구매 페이지를 새 탭으로 열기
- PC와 모바일에 맞춰 바뀌는 반응형 화면
- 전체 선택 맵 1장과 챕터별 10장을 PNG 또는 ZIP으로 저장
- 제품 사진 출처 확인 및 사진 파일 교체

## 파일 구성

```text
keyboard-guide/
├── index.html   # 스타일, 제품 데이터, 스크립트를 포함한 웹페이지
└── README.md    # 프로젝트 소개와 배포 방법
```

HTML, CSS, JavaScript와 Canvas API로 구성했습니다. 별도 서버, 데이터베이스, 패키지 설치 없이 사용할 수 있습니다.

## 로컬에서 실행하기

`index.html`을 Chrome 또는 Edge에서 엽니다. 제품 사진은 외부 주소에서 불러오므로 인터넷 연결이 필요합니다.

## GitHub Pages 배포

1. GitHub에 `keyboard-guide`라는 이름의 **Public** 저장소를 만듭니다.
2. 저장소 최상위에 `index.html`과 `README.md`를 업로드하고 커밋합니다.
3. 저장소의 **Settings → Pages**로 이동합니다.
4. 다음 설정을 선택하고 **Save**를 누릅니다.

   | 항목 | 설정 |
   |---|---|
   | Source | Deploy from a branch |
   | Branch | main |
   | Folder | / (root) |

5. 배포가 완료되면 Pages 화면의 **Visit site**로 접속합니다.

저장소 이름을 `keyboard-guide`로 정했다면 공개 주소는 다음 형태입니다. `YOUR_GITHUB_ID`를 본인의 GitHub 아이디로 바꿉니다.

```text
https://YOUR_GITHUB_ID.github.io/keyboard-guide/
```

배포 반영에는 최대 10분 정도 걸릴 수 있습니다. 생성된 주소를 블로그 본문에 연결하면 됩니다.

[GitHub Pages 공식 배포 안내](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)

## 내용 수정하기

`index.html` 안의 `window.PHOTO_ASSETS` 배열에서 제품 정보를 관리합니다.

| 항목 | 내용 |
|---|---|
| `name`, `displayName` | 제품명과 화면에 표시할 이름 |
| `brand`, `category`, `layout` | 브랜드, 분류, 배열 |
| `price`, `priceContext` | 참고 가격과 가격 기준 |
| `summary` | 제품 소개 문구 |
| `image` | 제품 사진 주소 |
| `destination`, `destinationLabel` | 제품 카드의 이동 주소와 링크 문구 |
| `source`, `credit`, `note` | 사진 출처와 모델 구분 정보 |
| `recommended` | 추천 제품 표시 여부 |

PNG로 저장하는 챕터의 문구와 구성은 같은 파일의 `BOARDS` 배열에서 별도로 관리합니다. 가격이나 추천 내용을 바꿀 때는 제품 카드와 저장 이미지의 내용도 함께 확인합니다.

수정한 파일을 `main` 브랜치에 커밋하면 GitHub Pages에 반영됩니다.

## 사진과 가격 정보

- 가격은 **2026년 10월 본문에 제시한 참고가**입니다. 실제 판매가, 재고, 옵션은 연결된 제품 페이지에서 확인할 수 있습니다.
- 사진 출처와 제품 카드의 이동 주소는 별도로 관리합니다. 사진 출처는 사이트 하단의 **사진 출처**에서 확인할 수 있습니다.
- Neo·QK 시리즈는 사용한 사진의 예시 모델을 표시하고, 기판과 케이스 사진은 완성 키보드와 구분합니다.
- 외부 사진 주소가 바뀌거나 접근이 제한되면 일부 사진이 표시되지 않을 수 있습니다. 사진 출처 창에서 원본을 확인하거나 사진 파일을 선택해 바꿀 수 있습니다.
- PNG·ZIP 저장은 해당 사진이 모두 준비되면 사용할 수 있습니다. 원본 연결이 실패하면 이미지 저장 창의 **사진 및 파일 옵션 → 사진 불러오기 호환 모드**에서 `wsrv.nl`을 통한 로딩을 사용할 수 있습니다.
