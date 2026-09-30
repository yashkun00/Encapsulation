# 🐍 Python Encapsulation

A beginner-friendly Python lesson covering **Encapsulation**, an important concept in Object-Oriented Programming (OOP).

Encapsulation is the idea of **keeping data inside a class and controlling how that data can be accessed or modified**.

---

## 📌 Topics Covered

* Encapsulation
* Private Attributes
* `__` Double Underscore
* Accessing Data Through Methods
* Controlling Data Modification

---

# 1. What is Encapsulation?

Encapsulation means keeping an object's data and the methods that work with that data together inside a class.

It can also be used to restrict direct access to certain attributes.

For example, a bank account should control how its balance is changed instead of allowing any code to directly modify it.

---

## 💰 Example: Bank Account

```python
class BankAccount:
    def __init__(self, balance):
        self.__balance = balance

    def deposit(self, amount):
        self.__balance += amount

    def show_balance(self):
        print(self.__balance)


account = BankAccount(1000)

account.deposit(500)
account.show_balance()
```

### Output

```text
1500
```

---

# 2. What is `__balance`?

Notice this line:

```python
self.__balance = balance
```

The double underscore (`__`) indicates that `balance` is intended to be a **private attribute**.

```text
balance
   ↓
__balance
   ↓
Private attribute
```

This discourages direct access from outside the class.

---

# 3. Accessing the Data Through Methods

Instead of directly changing the balance, the class provides a method:

```python
def deposit(self, amount):
    self.__balance += amount
```

The user interacts with the account through:

```python
account.deposit(500)
```

The balance is then updated internally.

To view the balance, we use:

```python
account.show_balance()
```

This keeps the data handling inside the class.

---

# 4. Why Use Encapsulation?

Imagine we allowed direct modification:

```python
account.balance = -50000
```

This could lead to unwanted or invalid changes.

With encapsulation, we can control how the data is modified.

For example, we could later add validation:

```python
def deposit(self, amount):
    if amount > 0:
        self.__balance += amount
```

Now the class controls what values can be added to the balance.

---

# 5. Encapsulation Flow

```text
        BankAccount
             │
      ┌──────┴──────┐
      │             │
 __balance       Methods
      │             │
      │       ┌─────┴─────┐
      │       │           │
      │    deposit()  show_balance()
      │       │           │
      └───────┴───────────┘
              │
        Controlled Access
```

The data stays inside the object while methods provide controlled interaction with it.

---

# 6. Important Note About Python

Python does not have truly private attributes in the same way some other programming languages do.

The double underscore triggers **name mangling**, which makes accidental direct access harder.

For example:

```python
self.__balance
```

is internally name-mangled by Python.

The main purpose is to signal:

> "This attribute is intended to be used internally by the class."

---

## 🆚 Normal vs Encapsulated Attribute

### Normal Attribute

```python
self.balance = balance
```

It can be accessed directly:

```python
account.balance
```

### Double Underscore Attribute

```python
self.__balance = balance
```

It is intended to be accessed through class methods:

```python
account.show_balance()
```

---

## 🎯 Learning Outcomes

After completing this lesson, you should understand:

* What encapsulation means.
* Why data can be kept inside a class.
* What `__` means in Python.
* How private attributes work.
* How methods can control access to data.
* Why encapsulation is useful in real-world applications.
* The basic idea of name mangling in Python.

---



## 👨‍💻 Author

**Yash**

⭐ If you found this lesson useful, consider giving the repository a star.
