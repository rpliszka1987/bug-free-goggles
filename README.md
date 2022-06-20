# Regular Expression (Regex) Tutorial

Purpose of this repository is to have a better understanding of **Regular Expression (REGEX)**. First to have a better undestanding regex is a sequence of characters that define a specific search pattern.

## Summary

Including **Regular Expression (REGEX)** in search algorithms to find certain pattern of characters within a string. Another way to use them in your code is for validation puporses. Below in the table of contents you can learn about applying regex to your application. You can confirm the user format is an email by confirming the following string format. In the example below you can see that there are characters separated by @ and then a period (.), which would be an email format such as example@email.com.
Example email:

```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Author](#author)

## Regex Components

### Anchors

- **^** anchor matches any string that start with specified string.
  - Example would be **^john** which in this case will look for all strings that start with john.

```javascript
let text = "John@gmail.com";

console.log(text.match(/^John/));
```

- **$** anchor matches any strings that end with the specified string.
  - Example would be **$com** will match strings ending with com, which would be specifically for email.

```javascript
let text = "John@gmail.com";

console.log(text.match(/com$/));
```

- **^ $** anchors would match any strings that start with strat sting and end with end string.
  - Example would be **john com$** will match any string which starts with john and ends with com.
- **gmail** this will match any string that contains gmail
  - Example would be matching email string whitch contain gmail or yahoo.

```javascript
let text = "John@gmail.com";

console.log(text.match(/gmail/));
```

### Quantifiers

- Quantifiers match a number of instances of a character, group, or character class in a string
- Exact count {n} will specify how many characters you would like to match. Below example matches emails with 4 digits in them

```javascript
let text = "John1234@gmail.com";

console.log(text.match(/\d{4}/));
```

- Below is an example of matching 4 letters in an email:

```javascript
let text = "John1234@gmail.com";

console.log(text.match(/\w{4}/));
```

### OR Operator

- Are searches done my a starting letter, number or character followed by certain other characters. Below example shows an email starting with John or Jim. Which will only look for email that start with John or Jim. This will do a global and case insensitive search.

```javascript
let text = "John1234@gmail.com Jim@gmail.com";

console.log(text.match(/john|jim/gi));
```

### Character Classes

- Will match only certain character classes. There are 4 to choose from:
  - \d - single character that is a digit
  - \w - a word character
  - \s - whitespaces
  - - - all

```javascript
let text = "John1234@gmail.com";

// Word Character
console.log(text.match(/\w/));

// Digit
console.log(text.match(/\d/));

// All
console.log(text.match(/\*/));
```

### Flags

- There are different flags which can be added to the end of expression. There are 3 main ones to choose from:
  - i - case insensitive
  - g - global which looks for all matches
  - m - multiline

```javascript
let text = "John@gmail.com";

// Global
console.log(text.match(/gmail/g));

// Case insensitive
let text = "John@gmail.com";

console.log(text.match(/gmail/i));

// Multiline
let text = "John@gmail.com";

console.log(text.match(/gmail/m));
```

### Bracket Expressions

- These are searches with characters between brackets [] which will match only characters which have thos characters or avoid those specified characters. Examples below will match characters that contain j in first example, and in second characters that dont contain j.

```javascript
let text = "John1234@gmail.com Robert@gmail.com";

// Contain J
console.log(text.match(/[j]/gi));

// Without J
console.log(text.match(/[^j]/gi));
```

## Author

My name is Robert and I am a Junior Developer learning how to create web application using JavaScript and other frameworks. Currently getting my Certification from Columbia University, after which I will apply this knowledge in a new career path. Below is a link to my GitHub for more of my projects.

https://github.com/rpliszka1987

[Back to top](#regular-expression-regex-tutorial)
