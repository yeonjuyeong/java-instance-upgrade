# java-instance-upgrade
클래스 - 1,2,3단계 모두 포함
생성자 - 3단계에만 사용
인스턴스 - 2,3단계에서 사용
매개변수 - 3단계에서만
this - 3단계에서만
## 첫번째 java instance
```java
class Accounting{
	public static double value0fSupply;
  public static double vatRate = 0.1;
  public static double getVAT( ) {
	  return value0fSupply * vatRate;
  }
  public static double getTotal() {
	  return value0fSupply + getVAT();
  }
}

public class Sungill21110_Test12 {
	public static void main(String[] args) {
		// TODO Auto-generated method stub

		Accounting.value0fSupply = 10000.0;
		System.out.println("Value of supply :" + Accounting.value0fSupply);
		System.out.println("Value of supply :" + Accounting.value0fSupply);
		
		Accounting.value0fSupply = 10000.0;
		System.out.println("VAT :" + Accounting.getVAT());
		Accounting.value0fSupply = 20000.0;
		System.out.println("VAT :" + Accounting.getVAT());
		
		Accounting.value0fSupply = 10000.0;
		System.out.println("Total :" + Accounting.getTotal());
		Accounting.value0fSupply = 20000.0;
		System.out.println("Total :" + Accounting.getTotal());
	}

}
```
부가가치세를 계산하여 나타내는 출력문이다. 부가가치세 포함x, 부가가치세만, 부가가치세 포함0의 값을 출력한다.

## 두번째 java instance
```java
class Accounting2{
	public double value0fSupply;
	public static double vatRate = 0.1;
	public double getVAT( ) {
		return value0fSupply * vatRate;
	}
	public double getTotal() {
		return value0fSupply + getVAT();
	}
}
public class Sungil21110_Test13 {
	public static void main(String[] args) {
		// TODO Auto-generated method stub

		Accounting2 a1 = new Accounting2();
		a1.value0fSupply = 10000.0;
		
		Accounting2 a2 = new Accounting2();
		a2.value0fSupply = 20000.0;
		
		System.out.println("Value of supply :" + a1.value0fSupply);
		System.out.println("Value of supply :" + a2.value0fSupply);
		
		System.out.println("VAT :" + a1.getVAT());
		System.out.println("VAT :" + a2.getVAT());
		
		System.out.println("Total :" + a1.getTotal());
		System.out.println("Total :" + a2.getTotal());
	}

}
```
첫번째 코드에서 좀더 간결하게 바꾸고 인스턴스를 사용한 버전이다. println으로 뽑아낼때 Accounting을 계속써서 코드가 커보였지만
매소드에서 value0fSupply, getVAT, getTotal의 static을 없애 인스턴스를 쓰게 만들고 
```java
		Accounting2 a1 = new Accounting2();
		a1.value0fSupply = 10000.0;
```
이런식으로 출력문위에 선언을 해 출력문마다 Accounting을 계속 안써도 되게 만들었다.

## 세번째 java instance
```java
class Accounting3{                                                 
	public double value0fSupply;                                   
	public static double vatRate = 0.1;                            
	public Accounting3(double value0fSupply) {                     
		this.value0fSupply  = value0fSupply;                       
	}                                                              
	public double getVAT( ) {                                      
		return value0fSupply * vatRate;                            
	}                                                              
	public double getTotal() {                                     
		return value0fSupply + getVAT();                           
	}                                                              
}                                                                  
public class sungil21110_test14 {                                  
	public static void main(String[] args) {                       
		// TODO Auto-generated method stub                         
                                                                   
		Accounting3 a1 = new Accounting3(10000.0);                 
		                                                           
		Accounting3 a2 = new Accounting3(20000.0);                 
		                                                           
		System.out.println("Value of supply :" + a1.value0fSupply);
		System.out.println("Value of supply :" + a2.value0fSupply);
		                                                           
		System.out.println("VAT :" + a1.getVAT());                 
		System.out.println("VAT :" + a2.getVAT());                 
		                                                           
		System.out.println("Total :" + a1.getTotal());             
		System.out.println("Total :" + a2.getTotal());             
	}                                                              
                                                                   
}                                                                  
```
