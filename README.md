# Hibernate Style Guide

Always use transactions for read-only operations
https://stackoverflow.com/a/40269166/3405171

Stress what you are using: a join table or a join column. Even if you don't need to specify a name of a join table or a join column.

```java
class Customer {

  @OneToMany
  @JoinTable
  List<Credit> credits;

}

class Customer {

  @OneToMany(mappedBy = "customer")
  List<Credit> credits;

}

class Credit {
  
  @ManyToOne
  @JoinColumn
  Customer customer;

}
```
