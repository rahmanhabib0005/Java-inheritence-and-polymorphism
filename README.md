Java OOP Concepts: Inheritance and Polymorphism

---

### 1. Inheritance

**Definition:**
Inheritance is one of the core concepts of object-oriented programming in Java. It allows a class (called a **subclass** or **child class**) to inherit fields and methods from another class (called a **superclass** or **parent class**).

**Purpose:**
- Promote code reusability
- Model real-world relationships
- Implement polymorphism

**Syntax:**
```java
class Parent {
    // fields and methods
}

class Child extends Parent {
    // inherits fields and methods of Parent
}
```

**Example:**
```java
class Animal {
    void makeSound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.makeSound(); // Inherited from Animal
        dog.bark();      // Specific to Dog
    }
}
```

---

### 2. Polymorphism

Polymorphism allows objects to take many forms. It enables a single method to behave differently on different classes.

#### 2.1. Compile-Time Polymorphism (Method Overloading)

**Definition:**
This type of polymorphism is resolved during compile time. It occurs when multiple methods have the same name but different parameters within the same class.

**Example:**
```java
class Calculator {
    int add(int a, int b) {
        return a + b;
    }

    double add(double a, double b) {
        return a + b;
    }

    int add(int a, int b, int c) {
        return a + b + c;
    }
}

public class Main {
    public static void main(String[] args) {
        Calculator calc = new Calculator();
        System.out.println(calc.add(2, 3));          // Output: 5
        System.out.println(calc.add(2.5, 3.5));      // Output: 6.0
        System.out.println(calc.add(1, 2, 3));       // Output: 6
    }
}
```

#### 2.2. Runtime Polymorphism (Method Overriding)

**Definition:**
This type of polymorphism is resolved during runtime. It occurs when a subclass provides a specific implementation of a method that is already defined in its superclass.

**Example:**
```java
class Animal {
    void makeSound() {
        System.out.println("Some generic animal sound");
    }
}

class Cat extends Animal {
    @Override
    void makeSound() {
        System.out.println("Meow");
    }
}

class Dog extends Animal {
    @Override
    void makeSound() {
        System.out.println("Bark");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal a1 = new Cat();
        Animal a2 = new Dog();

        a1.makeSound(); // Output: Meow
        a2.makeSound(); // Output: Bark
    }
}
```

**Benefits of Runtime Polymorphism:**
- Enables dynamic method dispatch
- Increases program flexibility and maintainability

---

### Summary

| Concept                | Type         | Resolved At | Example                   | Benefit                         |
|------------------------|--------------|-------------|----------------------------|----------------------------------|
| Inheritance            | Structural   | -           | Dog inherits Animal       | Code reuse, hierarchy            |
| Compile-Time Polymorphism | Static     | Compile-time| Method Overloading        | Flexibility with method names    |
| Runtime Polymorphism   | Dynamic      | Runtime     | Method Overriding         | Dynamic behavior at runtime      |

These core principles help build scalable, reusable, and flexible applications in Java.
