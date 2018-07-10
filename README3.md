# 팀 및 프로세스 설계 (Netflix 사례)
Nginx 블로그에서 Netflix의 마이크로서비스 적용 사례중 팀과 프로세스 디자인에 대한 사례가 있어서 간단히 정리하였습니다.



## 1. 효율보다는 속도로 최적화 해라
* 넷플릭스에서 배운 가장 중요한 교훈은 시장에서는 **속도가 승리**한다는 것입니다.

  * 느린 개발 프로세스가 더 나은지 개발자에게 묻는다면 대부분의 개발자는 그렇다고 답하지 않을 것입니다.

  * 경영진이나 고객이 개발주기가 너무 빠르다고 불평하지 않습니다.

  * 속도의 필요성은 IT 회사에서만 중요한 것이 아닙니다.


* 넷플리스는 속도를 최적화 하기 위해 조기 결정을 내렸습니다.

  * 고객이 원하는 바에 신속하게 대응하거나 고객의 관심을 끄는 혁신적인 웹 환경을 만들 수 있도록 **개발 프로세스를 개선**하는 것을 말합니다.

  * **속도**란 **고객에 대해 배우고 고객이 원하는 것을 경쟁사보다 빠르게 제공하는 것을 의미**합니다.


* 이러한 방식은 효율성을 위해 최적화 하는 패러다임을 바꿉니다.
  * 효율성은 일반적으로 개발 프로세스의 전반적인 흐름을 제어하여 비용 절감에 주력하면서 노력의 중복을 제거하고 실수를 방지하는 것입니다.

  * "나는 이것이 더 효율적이기 때문에 하고 있다" 라는 말은 본의 아니게 **누군가의 작업 속도를 늦출 수 있다**는 말이 될 수 있습니다.

  * 효율적으로 비즈니스를 성장시키는 방법을 **더 빨리 진행하는 것**입니다.

## 2. 여러분의 가정(Assumptions)이 여전히 사실인지 확인 해라
* 시장에서 성공을 거둔 많은 기존의 대기업들은 **반응이 빠른 작은 조직들에게 추월** 당하고 있습니다.
* 넷플릭스의 예를 보시면 아시겠지만 **기업의 크기가 문제는 아닙니다**.
* 가장 큰 문제점은 **더 이상 사실이 아닌 비즈니스 가정 하에서 운영** 되고 있는 것입니다.

  * 물론 비즈니스 모델을 공식화 할 때 가정을 해야하며 비즈니스 모델을 중심으로 최적화 하는 것은 좋습니다. 그러면 그것들을 중심으로 관행으로 최적화 하는 것이 타당합니다.

  * 다만 문제는 **위험이 더 이상 사실이 아니라고 가정**을 고수하는데서 오는데, 이것은 잘못된 것에 최적화 하고 있다는 것을 의미합니다. 

## 3. 인프라를 클라우드로
* 이전에 컴퓨터 성능을 높이기 위한 유일한 방법은 더 좋은 하드웨어를 구입하는 것이었습니다.

* 클라우드 출현으로 이 가정은 완전히 무효화 되었습니다.
  * 필요 할 때에 필요한 용량 구입이 가능합니다.

  * 실제로 사용하는 시간에 대해서만 비용 지불이 가능합니다.

* 넷플릭스의 엔지니어는 캘리포니아에서 전세계 인프라를 관리합니다.
  * 실험을 통해 특정 위치에 서버를 추가하여 성능향상이 가능한지 결정 할 수 있습니다.( 인스턴스 추가 이후 일주일 동안 테스트 한 다음 서버 인스턴스 비용을 정당화 하기에 좋지 않다고 생각되면 빠르게 종료가 가능합니다. 이러한 테스트를 전통적인 인프라를 통해 한다면 테스트를 실행하기까지 6개월 정도가 걸리게 됩니다.)

## 4. 적은 프로세스를 통해서 자유롭고 책임감 있는 문화 만들기
* 많은 기업들이 문제를 예방하기 위해서 누군가가 실수를 하면 메뉴얼에 "다시하지 마라"라는 규칙이 추가 됩니다.
  * 이러한 것처럼 문제가 생길 때마다 새로운 규칙과 같은 단계가 생기면 결국 우리를 느리게 하는 복잡한 "scar tissue"(흉터 조직) 과정이 생기게 됩니다.


* 넷플릭스에는 단 하나의 가이드 라인만 존재합니다.
  * **넷플릭스의 이익에 최선을 다하십시오**

  * 팀원들의 판단들을 신뢰하지 않는다면, 왜 그들을 고용하고 있는지 물어보는게 정상입니다.

## 5. 마이크로서비스 팀으로 교체
* 대부분의 개발 그룹은 사일로 형태로 분리되어 있으며 사일로 사이에 인력이 겹치지 않습니다.

* 개발 프로젝트의 표준 프로세스는 새로운 기능에 대한 아이디어를 논의하기 위해 프로덕트 매니저가 사용자 경험과 개발 그룹과 만나면서 시작합니다.

* 아이디어가 코드로 구현되면 코드가 QA 및 데이터베이스 관리 팀에 전달 되고 더 많은 회의에서 논의가 됩니다. 그 외에도 시스템 및 네트워크 관리자와의 대화도 이루어져야 하며 결과적으로 전체 프로세스는 매우 느려지게 됩니다.

![](https://cdn.wp.nginx.com/wp-content/uploads/2015/03/silos-base.png)


* 일부 기업은 개발 프로세스를 처음부터 끝까지 처리하는 작은 "스타트 업" 스타일의 팀을 만들어 속도를 높이려고 합니다.

* 하지만 이러한 소규모 팀들이 여전히 monolithic delivery를 수행 중이라면 일반적으로 다른 기능에 대한 책임이 있는 개인이나 그룹간에 핸드 오프가 존재합니다. 결국 이러한 프로세스는 대기업에서 동일한 방식으로 발생하는 동일한 문제(효율적이지 못하고 민첩하지 못함)로 인해 어려움을 겪습니다.

![](https://cdn-1.wp.nginx.com/wp-content/uploads/2015/03/silos-monolith1.png)

* Conway 법칙에 따르면 **소프트웨어 시스템 인터페이스 구조는 이를 만든 조직의 구조를 반영** 합니다.

* 따라서 마이크로 서비스 아키텍처로 전환하려면 직원을 product 팀으로 조직하고 DevOps 방법론을 사용해야 합니다.

* 더 이상 고립된 사일로 안에서 제품 관리자, UX 관리자, 개발 관리자 등이 사일로 안에서 하향식으로 관리 하지 않습니다.

* 마이크로서비스로 구현된 각 제품 기능에 대한 관리자가 존재하며, 구상부터 deployment 까지 마이크로서비스에 대한 소프트웨어 개발의 모든 측면을 담당하는 팀을 감독합니다.

* 플랫폼 팀은 제품 팀이 API를 통해 액세스 할 수 있는 인프라를 지원합니다.
  * 넷플릭스의 플랫폼 팀은 주로 AWS에서 관리되는 인프라 계층을 기반으로 구축 되었습니다.


  ![](https://cdn-1.wp.nginx.com/wp-content/uploads/2015/03/silos-microservices1.png)

## 6. 출처
https://www.nginx.com/blog/adopting-microservices-at-netflix-lessons-for-team-and-process-design/#cloud