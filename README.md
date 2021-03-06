# DesignPattern_Study_Flyweight

# Notion Link
https://five-cosmos-fb9.notion.site/FLYWEIGHT-a00d021724a0493c96f3eda28283a482


# 플라이급 (FLYWEIGHT)

### 의도

**공유(sharing)**을 통해 많은 **수의 소립(find-grained)** 객체들을 효과적으로 지원한다.

<aside>
🎈 다수의 오브젝트를 사용할 때 **공유할 수 있는 오브젝트를 공유**하여  **메모리 사용량**을 줄여주는 디자인 패턴이다.

</aside>

![image](https://user-images.githubusercontent.com/18654358/157136607-cbd8e770-d110-4936-a579-1bfc45139230.png)

- 위와 같이 Dog 클래스가 있다고 가정할 때
- 하나의 Dog 클래스를 생성하면 100MB 의 메모리를 사용하게 된다.
- 이런 상황에서 Dog 클래스를 1000개 만들게 되면 어떻게 될까?
    - 100MB * 1000 = 100,000 MB = 약 100GB 😂

<aside>
🎈 예시가 애매할 수 있지만 강아지의 “**종(Breed)**”에 따라 “**DNA**” 가 같다면 ? 
**1,000 마리의 강아지를 만들 때 모두 종이 다르지 않다면 DNA를 공유할 수 있을 것이다.!**

</aside>

![image](https://user-images.githubusercontent.com/18654358/157136632-39a94b5b-3d2f-4d02-b9e4-b905dd9b1126.png)


### 어떤가?

**클래스 구조가 다름을 확인할 수 있다.**

**디자인 패턴의 구조를 보면 이해하기 어려운 구조이다.. (용어부터 시작하여...!!)**

<aside>
🎈 디자인 패턴을 사용하는 이유는 이해하기 쉬운 코드를 만들기 위함이지 남들이 못하는 것을 나만 할 수 있다는 것으로 확인하기 위함이 아니야!

</aside>

***다시 한번 확인해보면 자주 사용되는 방법 중 하나로 볼 수 있을 것 같다.***

공통적으로 사용될 수 있는 Object들을 각 Object를 생성할 때마다 함께 생성하지 않고 

**Static한 영역, 예를 들면 Memory Cache 와 같은 곳에 위치시켜두고** 

**Reference 참조**를 통해 활용하는 방법을 **Flyweight**라고 칭한다고 볼 수 있을 것 같다.

---

### 우리 제품에 적용시킬 수 있는 케이스는 무엇이 있을까?

- 음,, 어떤 케이스가 있을꼬?
- 대부분은 메모리의 문제를 일으킬 만큼 많은 문제가..?~!

---

### 활용성

- 응용프로그램이 대량의 객체를 사용해야 할 때
- 객체의 수가 너무 많아져 저장 비용이 너무 높아질 때
- 대부분의 객체 상태를 부가적인 것으로 만들 수 있을 때
- 부가적인 속성들을 제거한 후 객체들을 조사해보니 객체의 많은 묶음이 비교적 적은 수의 공유된 객체로 대체될 수 있을 때. 현재 서로 다른 객체로 간주한 이유는 이들 부가적인 속성 때문이었지 본질이 달랐던 것은 아닐 때
- 응용프로그램이 객체의 정체성에 의존하지 않을 때. 플라이급 객체들은 공유될 수 있음을 의미하는데, 식별자가 있다는 것은 서로 다른 객체로 구별해야 한다는 의미이므로 플라이급 객체를 사용할 수 없다.

### 구조

![image](https://user-images.githubusercontent.com/18654358/157136652-beb8f497-29ae-4b0f-bcf8-10cd778d8c6a.png)
