# python-test

점프 투 파이썬

## 8장. 정규표현식

### 08-2 정규표현식 시작하기
####  정규 표현식의 기초, 메타 문자
##### [] 문자 - 문자 클래스

####  컴파일 옵션
##### DOTALL, S
##### IGNORECASE, I
##### MULTILINE, M
메타 문자인 ^, $과 연관된 옵션

^는 문자열의 처음, $는 문자열의 마지막

예를 들어, ^python인 경우, 문자열의 처음은 항상 python으로 시작해야 매치됨

python$이라면 문자열의 마지막은 항상 python으로 끝나야 매치됨
코드1
```
data = """python one
life is too short
python two
you need python
python three"""

p = compile("^python\s\w+")
print(p.findall(data))
```
결과1
```
['python one']
```
코드2
```
p = compile("^python\s\w+", M)
print(p.findall(data))
```
결과2
```
['python one', 'python two', 'python three']
```
