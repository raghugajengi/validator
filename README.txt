Spring Boot – Validation using Hibernate Validator

Hibernate validator offers validation annotations for Spring Boot that can be applied to the data fields within your
Entity class, and allows you to follow specific rules and conditions for fields in which we are applying validators
to meet your custom constraints. These annotations help ensure that the data meets all the conditions applied using
the validators.

Internally Hibernate validator uses default JRS-380 implementation to validate upon the argument.

Hibernate validators are very useful and they provide the following annotations that are very helpful for software
development.

Annotation

Usages

@NotNull	Char Sequence, Collection, Map, or Array object can be validated with this and they should not be null but can be empty
@NotEmpty	Char Sequence, Collection, Map, or Array object can be validated with this and they should not be null and not empty
@NotBlank	Char Sequence, Collection, Map, or Array objects can be validated with this and they should not be null and not empty and not blank
@Min	Given Minimum value has to be satisfied
@Max	Given Maximum value has to be satisfied
@Size	Field size should be less than or greater than the specified field size
@Email	Email can be validated with this
@Pattern	Given RegEx Pattern has to be satisfied.

dependency: 
<dependency>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-starter-validation</artifactId>
</dependency>

Let us start with a bean class GeekEmployee.java below contains examples of validators. In this we will be using
 Lombok dependency to generate boilerplate code i.e. for Getter, Setter, etc.

2.2.1 @NotNull
Let’s create a field Emp_id. Initially, the first thought that comes to our mind about Employee Id is that it can not be a NULL
 but can be left Empty in case it is auto-generated i.e. it should be assigned with any number, NULL can not be assigned.

 Note: @Data Annotation is used to generate Getter, Setter, etc for the data fields.

2.3 Exception handling for Validators
To collect all the errors, we need to have an “ExceptionHandler” and it is given below

ExceptionHandler.java