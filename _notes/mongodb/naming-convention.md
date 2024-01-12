---
layout: note
title: MongoDB Naming 관습 (Database, Collection, Field)
date: 2024-01-11
---






1. 데이터베이스 네이밍 

- 카멜케이스(Camel case)나 전부 소문자(lower case)로 작성할 것. (개인적으로 전부 소문자가 좋다)
- 카멜케이스는 낙타 등이 구불구불 한 것처럼 합성어의 구분을 합쳐진 글자의 첫 글자를 대문자로 작성해서 구분하는 것을 의미한다. 첫 글자는 소문자로 한다.
- 영문자a-z 숫자0-9 사용
- case sensitive하다. 즉 대소문자 구별에 주의해야한다.
- 소문자로 작성하는 것이 좋다.
- 64bytes 미만
- 운영체제에 따라 금지되는 특수문자가 있다.


- Windows
    - / \ . ” $ * < > : | ?


- Linux / Unix
    - / \ . ” $



- 데이터베이스 이름은 공백일수없다.
- 널 문자열이나 공백 문자 띄어쓰기를 포함해선 안된다.
- 가독성 좋게 구분자를 넣는 것이 권유한다.
- 구분자는 '-'나 '_'를 쓸 수 있다.







2. 콜렉션 네이밍 

- 카멜케이스나 소문자를 사용하면 되는데, 소문자 사용이 더 선호된다. (원치않는 이슈를 피하기 위해서)
- 콜렉션의 이름은 $, 공백 문자(ex. " "),널 문자, System이라는 접두사 사용 금지(예약됨) 는 포함해선 안된다.
- 구분자를 포함하는 것이 가독성이 좋아진다. '-'나 '_' 사용
- 120bytes 이하
- 복수형이 권장 ( ex. students, employees)
 






3. 필드 네이밍 

- 카멜케이스, 파스칼케이스, 소문자 사용
- 파스칼케이스는 카멜케이스와 비슷한데 합성어의 단어 구분을 첫글자를 대문자로 해서 구분한다.
(camelCase, PascalCase) 
- 널 문자열, 공백 문자, . 을 포함해선 안된다.
- $기호로 시작할 수 없다. ( MongoDB 3.6이상부터는 .과 $를 필드 이름에 포함 가능)
- 필드 이름엔 구분자를 사용하지 않아도 된다. _ 사용가능.
- mongodb는 자바스크립트를 사용하므로 camelCase가 좋음
 
공통적으로는 모호한 표현을 피하자.
가능한 짧으면서도 의미를 파악할 수 있게 정하자.
협업하는 동료들과 미리 규칙을 정하고 지키자.
기호에 따른 선택이 가능한 것은 결정하면 통일감 있게 사용하자. 


---




## Reference

- <https://www.mongodb.com/docs/manual/reference/limits/#naming-restrictions>
- <https://www.thecodebuzz.com/mongo-db-naming-conventions-standards-guidelines/>