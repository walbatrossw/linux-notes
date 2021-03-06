# 사용자와 그룹관리

## 1. 사용자와 그룹
- 리눅스는 다중 사용자 시스템
- 기본적으로 root라는 이름을 가진 Superuser가 있으며, 모든 작업을 할 수 있는 권한을 가짐
- 모든 사용자를 하나 이상의 그룹에 소속되어 있음
- 사용자는 `/etc/passwd` 파일에 정의되어 있음
  - 각 행의 의미
    ```
    사용자 이름:암호:사용자ID:사용자가 소속된 그룹ID:추가정보:홈디렉토리:기본셀
    ```
- 사용자의 비밀번호는 `/etc/shadow` 파일에 정의되어 있음
- 그룹은 `/etc/group` 파일에 정의되어 있음
  - 각 행의 의미
    ```
    그룹명:비밀번호:그룹ID:보조그룹사용자
    ```

## 2. 사용자와 그룹 관련 명령어
- 새로운 사용자 추가
  ```
  # adduser [사용자명]
  ```
- 새로운 사용자를 추가하면서 그룹에 추가하기
  ```
  # adduser -gid [그룹ID] [사용자명]
  ```
- 사용자의 비밀번호를 지정하거나 변경
  ```
  # passwd [비밀번호]
  ```
- 사용자의 속성 변경
  ```
  # usermod --group [그룹] [사용자명]
  ```
- 사용자 삭제
  - 사용자만 삭제
  ```
  # userdel [사용자명]
  ```
  - 사용자, 홈디렉토리까지 삭제
  ```
  # userdel -r [사용자명]
  ```
- 사용자 암호를 주기적으로 변경하도록 설정
  ```
  # chage -m [암호를 최소한 사용할 기간] [사용자명]
  ```
- 사용자는 최소 하나이상의 그룹에 속해야함, 보조 그룹에 들어갈 수 있음
- 현재 사용자가 속한 그룹을 보여줌
  ```
  # groups
  ```
- 새로운 그룹 생성
  ```
  # groupadd [새로운 그룹명]
  ```
- 그룹의 속성을 변경
  ```
  # groupmod --new-name [새로운 그룹명] [기존의 그룹명]
  ```
- 그룹 삭제
  ```
  # groupdel [그룹명]
  ```
- 그룹의 암호 설정, 그룹관리 수행
  ```
  # gpassword [그룹명]
  ```
