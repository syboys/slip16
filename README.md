# slip16


Q.1 Write a Java Program to implement Observer Design Pattern for number conversion.
Accept a number in Decimal form and represent it in Hexadecimal, Octal and Binary.
Change the Number and it reflects in other forms also 
Q.2. Write a python program to Implement Simple Linear Regression for predicting house
price. 
Q.3 Create a js file named main.js for event-driven application. There should be a main loop
that listens for events, and then triggers a callback function when one of those
events is detected



Q.1 .Write a Java Program to implement Observer Design Pattern for number conversion.
Accept a number in Decimal form and represent it in Hexadecimal, Octal and Binary.
Change the Number and it reflects in other forms also.
:

import java.util.ArrayList;
import java.util.List;
class Subject
{
 private List<Observer>observers=new ArrayList<Observer>();
 private int state;
 public int getState()
 {
 return state;
 }
 public void setState(int s)
 {
 this.state=s;
 notifyAllObservers();
 }

 public void attach (Observer o1)
 {
 observers.add(o1);
 }
 public void notifyAllObservers()
 {
 for(Observer o1: observers)
 {
 o1.update();
 }
 }
}
abstract class Observer
{
protected Subject s1;
public abstract void update();
}
class BinaryObserver extends Observer
 {
 public BinaryObserver(Subject s)
 {
 this.s1=s;
 this.s1.attach(this);
 }
 public void update()
 {
 System.out.println("Binary String:" +Integer.toBinaryString(s1.getState()));
 }
}
class OctalObserver extends Observer
 {
 public OctalObserver(Subject s)
 {
 this.s1=s;
 this.s1.attach(this);
 }
 public void update()
 {
 System.out.println("Octal String:" +Integer.toOctalString(s1.getState()));
 }
}
class HexaObserver extends Observer
 {
 public HexaObserver(Subject s)
 {
 this.s1=s;
 this.s1.attach(this);
 }
 public void update()
 {
 System.out.println("Heaxdeciamal String:" +Integer.toHexString(s1.getState()));
 }
}
public class Main
{
 public static void main(String [] args)
 {
 Subject s1=new Subject();
 new BinaryObserver(s1);
 new OctalObserver(s1);
 new HexaObserver(s1);
 System.out.println("First state Change:15");
 s1.setState(15);
 System.out.println("Second state Change:10");
 s1.setState(10);
 }
} 


Q.2. Write a python program to Implement Simple Linear Regression for predicting house
price.

:import numpy as np

class SimpleLinearRegression:
  def __init__(self):
    self.bias = 0
    self.weight = 0
  
  def fit(self, X, y):
    """
    Fit the model to the data.
    
    Parameters:
    X: A numpy array containing the independent variables.
    y: A numpy array containing the dependent variables.
    """
    n = len(X)
    x_mean = np.mean(X)
    y_mean = np.mean(y)
    num = 0
    den = 0
    for i in range(n):
      num += (X[i] - x_mean) * (y[i] - y_mean)
      den += (X[i] - x_mean) ** 2
    self.weight = num / den
    self.bias = y_mean - self.weight * x_mean
    
  def predict(self, X):
    """
    Predict the dependent variable given the independent variable.
    
    Parameters:
    X: A numpy array containing the independent variables.
    
    Returns:
    A numpy array containing the predicted dependent variables.
    """
    return self.bias + self.weight * X


Q.3 Create a js file named main.js for event-driven application. There should be a main loop
that listens for events, and then triggers a callback function when one of those
events is detected
:
const mainLoop = () => {
  // Set up event listeners for various events
  document.addEventListener('click', handleClick);
  document.addEventListener('keypress', handleKeyPress);
  document.addEventListener('scroll', handleScroll);
  
  // Main loop function
  const loop = () => {
    // Check for events and trigger callbacks as needed
    checkForEvents();
    
    // Call the loop function again after a brief delay
    setTimeout(loop, 100);
  }
  
  // Start the main loop
  loop();
}

// Call the mainLoop function to start the event-driven application
mainLoop();

 
