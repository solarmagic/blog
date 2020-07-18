# 내가 macOS에서 PS 환경 설정하는 법

이번에 마침 macOS 를 싹 다 밀고 다시 프로그램을 까는 중이라 관련 포스트를 적을 수 있을것 같다.  매번 나도 컴퓨터가 달라지거나 할 수 있기 때문에 이번 기회에 내가 쓰는 환경을 정리하려고 한다.

## PS란?

**P**roblem **S**olving의 약자로 알고리즘 문제 풀이를 PS라고 부른다. *C*ompetitive *P*rogramming 의 약자로 CP라고도 하며 CP는 시간이 정해져있는 대회 같은데에서 문제 푸는것으로 의미를 축소 시키기도 한다. 코딩 테스트, 정보올림피아드, ICPC, SCPC, Facebook Hacker Cup, Google Code Jam과 같은 곳에서 문제를 푸는 것을 말한다.

## 언어 설정

대학생이 참가할 수 있는 PS에서 가장 권위있는 대회중 하나인 [ICPC의 World Finals 의 규정](https://icpc.global/worldfinals/programming-environment)을 보면 쓸 수 있는 언어는 Java, C, C++, Python3, Kotlin이다. 개인적으로 이 외의 언어로 PS를 하는 것은 비추한다.  ICPC World Finals를 나가기 위해 거쳐야하는 ICPC Korea Regional 대회에서의 언어 규정은 C, C++, Java, 한국 기업 대회중 가장 규모가 큰 SCPC(삼성프로그래밍 경진대회)의 경우에도  C, C++, Java만이 사용 가능하다.

C++이 제공하는 라이브러리의 범위와 수준이 매우좋고, 같은 동작을 실행할때 Java에 비해 수배는 빠른 성능을 보여쥑 때문에  PS에서 쓰는 언어는 사실상 C++이라고 볼 수있다.

C++의 컴파일은 대부분의 대회에서 de facto standard 컴파일러인 `gcc`로  컴파일되고 C++14, 혹은 C++17 옵션을 사용한다. 개인적으로 후자를 쓰는걸 좋아하는데 아쉽게도 아직 C++14로 치뤄지는 대회가 더 많은 것 같다. 

Java나 Python의 경우 알아 놓으면 그래도 매운 큰수를 처리할 때, 매우 정밀한 수를 처리 할 때, 정규표현식을 처리할때 등 가끔씩 더 편할 때도 있긴하다. 그러나 그냥 C++만 제대로 할 줄 알아도 PS를 하는데 불편함은 없을 것으로 추정된다.

## 기초 환경 설정

정말 macOS를 처음 접한다고 생각하고 얘기를 시작한다.

### Homebrew 설치

>**macOS 용 패키지 관리자**

[설치 링크](https://brew.sh/index_ko)

`Homebrew` 는 macOS 패키지 관리자로 이것 없이 다른 패키지를 설치/제거 하는건 좀 귀찮은 일이다. macOS를 깐 개발자들이라면 거의 무조건 설치해야하는 친구라 할 수 있다.

Windows에는 `Chocolately` Ubuntu `apt`  CentOS `yum` 과 비슷한 기능을 한다.

### gcc 설치

`brew install gcc` 로 gcc를 설치해주자.

기존의 macOS에서는 gcc를 실행하면 clang이 실행되었기 때문에 gcc-10, g++-10 과 같은 명령어를 통해서 실행을 할 수 있다.

## 편집기 선택

 [ICPC의 World Finals 의 규정](https://icpc.global/worldfinals/programming-environment)을 다시 보면 사용할 수 있는 editor와 IDE는 다음과 같다.

### Editor

-   vi/vim
-   gvim
-   emacs
-   gedit
-   geany
-   kate

### IDE

-   Eclipse 4.13 (2019-09), configured with:
    -   JDT (Java Development Tools version 3.18.100.v20190916-1045 using Java as listed above)
    -   CDT (C/C++ Development Tools version 9.9.0.201909091956 using C/C++ as listed above)
    -   PyDev (Python Development Environment version 7.3.0.201908161924 using Python 3 as listed above)
-   IntelliJ (IDEA Community Edition version 2019.2.2), configured with:
    -   Java as listed above
    -   Kotlin plugin 1.3.41-release-IJ2019.2
-   CLion (version 2019.2.2), configured with:
    -   C/C++ as listed above
-   Pycharm Community Edition Python IDE (version 2019.2.2), configured with:
    -   Python 3 as listed above
-   Code::Blocks (version 17.12-1), configured with:
    -   C/C++ as listed above

### 무엇을 택할 것인가?

개인적으로는 PS대회 (CP) 는 매우 짧은 시간내에 이루어지기 때문에 컴파일과 실행이 빠르게 진행되는 것을 선호한다. 그래서 대부분의 PSer들은 IDE의 무거운 기능 필요없이 single file run 을 잘 할 수있는 가벼운 편집기를 선호하는 경향이 있다.  혹은 Debug를 잘 할 수있는 에디터를 선호한다.

World Finals에서 많이 쓰는 거는 vi/vim, Code::Blocks이고 새롭게 CLion도 이제 쓰는 사람들이 생긴것 같다. 아마 나도 저 중에서 고르라면 Code::Blocks를 고를 것 같지만 macOS에서는 Code::Blocks가 그렇게 좋지 않기 때문에 대회 환경에 맞추지 않고 다른 편집기를 택하도록 한다.

개인적으로 추천하는건 Sublime Text이다. 가벼우면서 적당한 기능을 가지고 있다. VS Code도 좋지만 내가 익숙하고 만들어 놓은 snippets 기능이 좋다. 디버그 기능이 사실 조금 부족하긴 한데 그냥 출력으로 디버깅 하거나 정 필요할때는 xcode로 옮겨서 디버깅하곤 한다.

## 편집기 설정

### 다운로드

[다운로드 링크](https://www.sublimetext.com/3)  
80$ 를 주고 유료를 살 수 있는데 무료버전은 그냥 가끔씩 저장할 때 유료 사주세요! 말고는 기능적 제한은 없으니 무료버전으로 충분하다. 개인적으로 쓰다가 내가 이 에디터로 80$ 이상의 가치를 한것 같으면 사는 것을 추천한다.

### Package Control 설치

`CMD + SHIFT + 'P'` 키를 누른다음에 Package Control를 입력하면 Package Control를 설치할 수 있다. 얘도 `Homebrew`와 같은 패키지 관리 툴이다.

엔터를 치고 조금 기다리면 설치과 완료된다.

### Package Resoruce Viewer 설치 및 사용

`CMD + SHIFT + 'P'`  를 누르고 Install Package를 검색한다음 PRV를 검색해서 `Package Resoruce Viewer`를 깔아주자. 

설치가 완료 되면 
1. `CMD + SHIFT + 'P'` 이후 PRV: Extract Package를 누르고 C++ 을 통해 C++의 패키지를 압축 해제 해주자. 
2. `CMD + SHIFT + 'P'` 하고 PRV: Open Resources를 누르고 C++, C++ Single File.sublime-build를 누르자.
3. 파일의 내용을 다음과 같이 편집하자

<script src="https://gist.github.com/solarmagic/f49607d438aceb6b8ee34080b7e91cc6.js"></script>

input.txt라는 파일에서 input을 받고, gcc, C++14로 컴파일하는 코드이다.

## 테스트

소스파일이 생기는 곳과 동일한 폴더에 input.txt를 만든다. 개인적으로 `CMD + OPTION + '2'` 키를 눌러서 한 화면를 갈라서 왼쪽에는 코드 오른쪽에는 인풋을 놓고 코드를 짜는 것을 선호한다.

다음과 같이 작성해보도록 한다.


![sublime test settings](https://i.imgur.com/HMICLvd.png)


`CMD + 'B'`를 한다음에 Single File - Run을 선택한다. 다음부터는 Run을 누르지 않더라도 자동으로 `CMD + 'B'`만 하면 자동으로 실행이 된다.

하단에 46이 나왔다면 성공이다.

## 추가 설정

### 글씨

폰트 크기는 그냥 `CMD + '+'` 혹은 `CMD + '-'`로 조정하곤 한다.  폰트는 D2 Coding을 선호한긴하는데 개인의 취향에 맞게 설정하자.

### 테마

예쁜 테마를 많이 다운로드 할 수 있다. 개인적으로는 귀찮아서 잘 안한다.

### 스니펫

사실 서브라임을 쓰는 주요 이유다. 

PS문제를 풀다보면 같은 코드를 반복해서 짤 일이 많은데 이를 간소화 시켜준다.

<video draggable="false" playsinline="" autoplay="" loop="" class="" style="width: 960px; height: 574px;"><source type="video/mp4" src="https://i.imgur.com/9Qvjrnp.mp4"></video>

파인더에서 `CMD + SHIFT + 'G'`를 누르고 `/Users/{user}/Library/Application Support/Sublime Text 3/Packages` 경로로 가서 snippet 파일을 작성할 수 있다.

샘플로 다른곳에서 따온 코드하나를 쓰자면

<script src="https://gist.github.com/solarmagic/b816dd6c4b6eea22999e70b21c759a98.js"></script>

이런식으로 작성해서 저장할 수 있다.

<!--stackedit_data:
eyJoaXN0b3J5IjpbNTA2Njc0MDMwXX0=
-->