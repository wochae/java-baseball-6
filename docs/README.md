## 🚀 기능 요구 사항

네 가지의 클래스가 존재합니다.

- 경기, 심판, 타자, 투수
- 경기는 큰 틀을 역할하고 그 각 객체 즉 인스턴스로 존재
- 한 경기에 각각 하나의 심판, 타자, 투수가 존재함.
- 다른 경기에는 이 세 객체가 존재하면 안되게 설계.

### 상대방(컴퓨터) 구현

컴퓨터는 1부터 9까지의 서로 다른 수로 이뤄진 3자리의 수를 가진다.
경기 최초 시 가지고 있으며 새로운 경기가 진행 시 이전 수는 초기화 해야한다.

#### 기능 구현

- 1-9 범위의 무작위 3개의 숫자를 생성하는 클래스 컴퓨터

#### 유효성 검사

인스턴스로 생성한 두 컴퓨터가 서로 다른지 
- 참조에 대해 등식 관계로 구현
- 우연히 무작위의 숫자가 같을 수 있기 때문에 객체의 주소를 비교
- 목적은 한 경기에 하나 뿐인 컴퓨터로 존재하기 위함.

### 심판 구현

심판은 컴퓨터가 가지고 있는 숫자를 비교해서 볼과 스트라이크를 판별한다.
야구에 심판은 처음 보는 단어라 Referee라는 대체어를 사용.

#### 기능 구현

- 경기 안내를 진행한다.
- 볼, 스트라이크를 판별한다.

#### 유효성 검사

- 판별을 제대로 하는지 기댓값과 비교해본다.

### 유저 구현

경기에서 승부를 보기 위해 컴퓨터가 생성한 임의의 세 자리 숫자를 맞춰야한다.
근데 못 맞춰도 기회는 많다. 힌트도 준다.
심판이 다 알려준다.

#### 기능 구현

- 맞출 때까지 숫자를 입력한다.
- 맞춘 경우 계속 하려면 1을, 그만하려면 2를 입력하여 종료한다. 


#### 유효성 검사

- 입력 내용이 세 자리 숫자로만 이뤄졌는지 확인한다.
- 3 스트라이크를 입력한 경우, 재경기 여부 안내를 받는지 확인한다.

### 경기 구현

경기는 매번 독립적인 인스턴스로 존재합니다.
3스트라이크가 나올 때까지가 경기의 생명주기이며 경기가 종료 후,
재경기를 희망하면 다음 경기가 진행된다.

#### 기능 구현

- 한 경기가 생성되고 그 안에 심판과, 타자, 투수가 존재한다.
- 3스트라이크가 나올 때까지 반복문들 돌아 유저로부터 입력을 받는다.
- 3스트라이크가 나와서 경기가 종료가 되면 재경기를 물어보고 반복문에서 나온다.

#### 유효성 검사

- 경기 안에서 유저로부터 받은 입력이 올바르지 않는 경우 요구한 에러를 반환한다.
