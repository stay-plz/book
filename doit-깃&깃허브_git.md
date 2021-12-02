# GIT

### ● 깃 환경설정

```
$ git config --global user.name "Username"
$ git config --global user.email "UserEmail@Email"
```

### ● 초기 작업환경 구성

```
$ git init
$ git config user.name "이름"
$ git config user.email "이메일"
```

### ● 깃 초기화

```
$ git init
```

### ● 깃 상태확인

```
$ git status
```

### ● 파일 트리에서 스테이지로 이동 (스테이징)

```
$ git add 파일명
$ git add .
```

### ● 깃 상태확인

```
$ git status
```

### ● 스테이지에 있는 파일 커밋

```
$ git commit
$ git commit -m "커밋메시지"
```

### ● 방금 커밋한 메시지 수정

```
$ git commit --amend
```

### ● 스테이징과 커밋 한번에 처리

```
$ git commit -am "커밋메세지"
$ git commit -a -m "커밋메세지"
```

### ● 깃 로그확인 (버전이 제대로 만들어졌는지)

```
$ git log
$ git log --stat (커밋에 관련된 파일 표시)
$ git log --online (한줄로확인)
$ git log --online --branches (각브랜치커밋 확인)
$ git log --online --branches --graph (각브랜치커밋관계 그래프 확인)
```

### ● 깃 변경사항 확인

```
$ git diff
```

### ● 작업트리에서 수정한 파일 되돌리기

소스를 최신 버전의 상태로 되돌림

```
$ git checkout --파일명
```

### ● 스테이징 되돌리기

```
$ git reset HEAD (스테이지에 있는 모든파일 되돌리기)
$ git reset HEAD 파일명 (해당파일만 되돌리기)
```

### ● 최신 커밋 되돌리기

```
커밋취소, 스테이징 취소, 취소파일이 작업트리에만 남는다.
$ git reset HEAD^
$ git reset --soft HEAD^ (최근 커밋을 하기 전 상태로 작업트리 되돌림)
$ git reset --mixed HEAD^ (최근 커밋, 스테이징을 하기 전 상태로 작업트리 되돌림. 기본옵션)
$ git reset --hard HEAD^ (최근커밋, 스테이징, 파일 수정을 하기 전 상태로 작업트리 되돌림. 복구불가능.)
```

### ● 특정 커밋으로 되돌리고 그 이후버전 삭제

특정 커밋으로 되돌리고, 그 이후 버전을 삭제

```
$ git reset --hard 되돌아갈커밋해시
```

### ● 특정 커밋으로 되돌리기 커밋 삭제하지 않음

특정 커밋으로 되돌리고, 그 이후 버전을 삭제

```
$ git revert 취소하려고하는커밋해시
```

### ● 브랜치 확인 및 생성

```
$ git branch (브랜치확인)
$ git branch 브랜치명 (브랜치생성)
```

### ● 브랜치 이동

```
$ git checkout 브랜치명
$ git checkout -b 브랜치명 (브랜치 만들고 체크아웃까지 한번에)
```

### ● 브랜치 사이 차이점

```
$ git log 브랜치1..브랜치2 (브랜치2-브랜치1=브랜치2에만있는커밋)
```

### ● 브랜치 병합

```
$ git merge 가져올브랜치명
```

### ● 브랜치 병합

```
$ git merge 가져올브랜치명
```

### ● 브랜치 삭제

삭제된 브랜치 이름으로 다시 브랜치를 만들면 이전 작업내용이 그대로 나타난다. 사실은 감추는것.

```
$ git merge -d 삭제할브랜치명
```

### ● 수정중인 파일 감추기 및 되돌리기

브랜치에서 파일을 수정하고 커밋하지 않은 상태에서 급하게 다른 파일을 커밋해야할 경우 사용. 잠시 감춰둔다.

```
$ git stash
stash목록 파일들 되돌리기
$ git stash pop
```

### ● 원격저장소 연결하기

origin은 https://github.com/... 과 같음.

```
$ git remote add origin 주소
```

### ● 원격저장소 연결확인

```
$ git remote -v
```

### ● 원격저장소 파일올리기

지역저장소의 브랜치를 origin(원격저장소)의 master 브랜치로 푸시하라는 명령어. -u 옵션은 지역저장소 브랜치를 원격 저장소의 master 브랜치에 연결하기 위한 것으로처음에 한번만 사용한다.

```
$ git push -u origin master
$ git push
```

### ● 원격저장소 파일 내려받기

origin(원격저장소)의 내용을 master브랜치로 가져온다.
기본 원격 저장소가 origin이고, 지역저장소의 기본 브랜치가 master이기 때문에 git pull만 입력해도 된다.

```
$ git pull origin master
```

### ● SSH 원격 접속

아이디, 비밀번호를 입력하지 않고 프라이빗키와 퍼블릭키를 사용해 기기를 깃허브에 인증하는 방식.

```
$ ssh-keygen
$ cd ~/.ssh
$ cat id_rsa.pub
$ pub key 깃허브에 등록
$ git remote add origin ssh복사주소 붙여넣기
```

### ● 원격저장소 복제하기

```
$ git clone 복제하려는주소 복제하려는디렉토리 (복제하려는 디렉토리가 없다면 새로 생성됨)
$ git clone 복제하려는주소 . (현재디렉토리)
```

### ● 원격 브랜치 정보 가져오기

```
$ git fetch
패치해서 가져온 최신 정보를 보고싶으면 FETCH_HEAD 브랜치로 체크아웃하여 확인한다.
$ get checkout FETCH_HEAD
확인 후 최신커밋을 현재 브랜치에 합치려면 합치려는 브랜치로 이동 후
$ git pull 하거나.
$ git merge FETCH_HEAD
```

### ● 공동작업자 추가

settings-colaborators-add colaborator

### ● 브랜치 푸시

origin(원격저장소)에 브랜치를 푸시

```
$ git push origin 브랜치명
```
