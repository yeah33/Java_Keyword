Keyword2
================

<br><br>

**1. package** <br> 패키지는 비슷한 성격의 자바 클래스들을 모아 놓는 자바의 디렉토리입니다.

<br><br><br><br><br>

**2. instance** <br> instance란 클래스의 정의를 통해 만들어진 객체를 의미합니다. 객체를 실제로 생성하는 과정을 인스턴스화 한다고 표현합니다.

<br> *객체와 인스턴스의 차이점* <br> 객체는 선언을 의미합니다. 선언된 객체는 null값을 가지며 어떤 메모리도 객체에 차지되어 있지 않습니다. <br> 그러한 객체를 인스턴스화하면 메모리가 객체에 의해 차지되고, 실체화 됩니다.

<br><br><br><br><br>

**3. this** <br> 자바에서 this는 ‘인스턴스의 자기 자신’을 의미합니다. <br> 주로 메소드 또는 생성자의 이름과 매개변수의 이름이 동일할 때 인스턴스 필드임을 명확히 하기 위해 사용합니다. <br><br>

    public class List{
        public String major;
        public int grade; 
        
        
        public List(String major, int grade){
            this.major=major;
            this.grade=grade;
        }
        
        public static void main(String[] args) {
            List yeeun = new List("economy",3); 
            
            System.out.println("major: "+yeeun.major);
            System.out.println("grade: "+yeeun.grade);
        }
    }

<br><br> 위의 List 클래스를 보시면 멤버변수로 선언되어 있는 major와 grader변수는 생성자 List의 매개변수의 이름과 동일합니다. <br> 이 때 this 를 사용하면 지금 선언하는 변수는 생성자의 매개변수가 아니라 멤버변수를 받아주는 것임을 알 수 있습니다. <br> 위의 경우에서 this 를 사용하지 않으면 코드는 사용 가능하지만, major와 grade변수는 지역변수로 선언되기 때문에 null값이 출력되는 것을 알 수 있습니다.

<br><br><br><br><br>

**4. super** <br> This가 ‘인스턴스의 자기 자신’을 의미했다면, super는 ‘상위 클래스의 멤버 변수’를 의미합니다.

<br><br>

    public class List{
        public String major="economics";
        public int grade=3;
    }

        
        
    class Info extends List{

            void info() {
                super.major=major;
                super.grade=grade;
                System.out.println(major);
                System.out.println(grade);  
            }
            
            public static void main(String[] args) {
                Info yeeuninfo = new Info();
                yeeuninfo.info();
                
            }
        }
        

<br><br>
List클래스에서 major변수와 grade변수의 값을 선언해주었습니다. <br> Info 클래스는 List클래스의 하위 클래스입니다. <br> 하위 클래스인 Info클래스에서 super키워드를 이용해 상위클래스인 List클래스에 선언해 주었던 변수의 값을 가져와 사용할 수 있습니다. <br> 따라서 ‘economics’ 와 ‘3’이 출력되는 것을 알 수 있습니다.

<br><br><br><br><br>

**5. final** <br> Final로 선언된 변수는 값을 초기화만 할 수 있고, 그 값의 변경 또는 새로운 할당이 불가능한 값이 됩니다. <br> 예를 들어 회원가입 기능을 구현할 때 아이디와 주민등록번호 변수는 final로 선언해 주어 변경이 불가능하도록 할 수 있습니다.

<br><br><br><br><br>

**6. static** <br> Static은 변수나 메소드 앞에 붙여 사용합니다. <br> 변수를 static으로 설정하면 같은 곳의 메모리 주소를 바라보기 때문에 static변수의 값을 공유하게 됩니다.

<br><br>


    public class Age {
        static int age=25;
        
        Age(){
                this.age++;
                System.out.println(this.age);
        }
        
        public static void main(String[] args) {
            Age one_year_later=new Age();
            Age two_years_later=new Age();
        }
        
    }

<br><br>
위의 Age 클래스에서 age변수에 static키워드를 붙여주었습니다. <br> main함수에서 age()함수를 사용할 때 같은 메모리 주소를 바라보기 때문에 증가된 값이 저장된 곳을 가리키기 때문에 매년 한 살 씩 정상적으로 증가하는 나이를 출력해 볼 수 있습니다. <br> 이 때 만약 age변수에 static 키워드를 붙여주지 않으면 age변수는 매번 주어진 25이라는 값을 받아주어 출력되기 때문에, 내년의 나이도 내후년의 나이도 26으로 동일한 증가값을 출력하게 됩니다.

<br><br><br><br><br>

**7. Access Modifier** <br> 접근제어자에는 private, default, protected, public이 있습니다. <br> private -&gt; default -&gt; protected -&gt; public 순으로 더 많은 접근을 허용합니다.

<br><br><br><br><br>

**8. Overloading** <br> Overloading은 같은 이름의 메소드를 여러 개 정의하고, 매개변수의 유형과 개수를 다르게 하여 다양한 호출을 할 수 있도록 하는 기술입니다.

<br><br>



    public class Overloading {
        
        static void license(String license1) {
            System.out.println("level1 : "+license1);
        }
        
        static void license(String license1,String license2) {
            System.out.println("level2 : "+license1+","+license2);
        }
        
        static void license(String license1,String license2,String license3) {
            System.out.println("level3 : " +license1+ ","+license2+","+license3);
        }
        
        public static void main(String[] args) {
            license("TOEIC");
            license("TOEIC","TOEFL");
            license("TOEIC","TOEFL","TEPS");
        }
        
    }

<br><br>

Overloading클래스에 license라는 동일한 이름을 가진 메소드를 3개 정의했습니다. <br> 매개변수의 개수에 따라 출력되는 레벨이 다르도록 하여 호출할 수 있습니다. <br> 출력값은 다음과 같습니다. <br><br> level1 : TOEIC <br> level2 : TOEIC,TOEFL <br> level3 : TOEIC,TOEFL,TEPS <br><br>

출력값을 살펴보면 호출한 메소드의 이름은 같지만 매개변수의 개수에 따라 다른 값을 출력할 수 있다는 것을 확인 할 수 있습니다.

<br><br><br><br><br>

**9. Overriding** <br> Overriding은 상위 클래스가 가지고 있는 메소드가 하위 클래스로 상속되어 하위 클래스에서 사용할 수 있도록 하는 기능입니다. <br> 하위 클래스에서는 메소드를 재정의 하여 사용할 수 있습니다.

<br><br>


    public class OverridingParents {
        
        static void license(String license1) {
            System.out.println("level1 : "+license1);
        }
    }


    public class Overriding extends OverridingParents{
        String license2;
        String license3;
        
        static void license(String license1, String license2, String license3) {
            System.out.println("level3 : "+license1+","+license2+","+license3);
        }
        
        public static void main(String[] args) {
            license("TOEIC");
            license("TOEIC","TOEFL","TEPS");
        }

    }

<br><br>

Overriding 클래스는 OverridingParents 클래스를 상속받고 있습니다. <br>
상위클래스인 OverridingParents가 가지고 있는 license메소드를 하위클래스인 Overriding 클래스가 상속받아 매개변수의 개수를 추가하여 재정의하여 사용하고 있습니다.

<br><br><br><br><br>

**10. Singleton pattern** <br> 싱글톤 패턴은 여러 디자인 패턴 중 하나입니다. 싱글톤은 단 하나의 객체만을 생성하도록 강제하는 패턴입니다. <br> 하나의 인스턴스만을 유지하기 위해 인스턴스 생성에 특별한 제약을 걸어둬야 합니다. <br> new를 실행할 수 없도록 private접근 제어자를 지정하고, 정적 메소드를 지원해야 합니다. <br> 인스턴스를 여러개 생성하여 자원을 낭비하거나 버그가 발생하는 것을 방지하기 위해 사용합니다.

<br><br>
