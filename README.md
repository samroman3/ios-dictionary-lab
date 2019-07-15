# Dictionaries lab

Fork and clone this repo. On your fork, answer and commit the follow questions. When you are finished, submit the link to your repo on Canvas.


## Question 1 - done

- Create an instance of a dictionary called `citiesDict` that maps 3 countries to their capital cities.

- Add two more countries to your dictionary.

- Translate at least 3 of the capital names into another language.

```
var citiesDict: [String:String] = ["United Kingdom" : "London","Mexico" : "Mexico City", "Canada" : "Ottawa"]

citiesDict["Sweden"] = "Stockholm"
citiesDict["Pakistan"] = "Islamabad"

citiesDict["United Kingdom"] = "Landan" //London in arabic
citiesDict["Mexico"] = "Madinat Maksiku" // Mexico City in arabic
citiesDict["Sweden"] = "Satukahulam" //Stockholm in arabic
```


## Question 2 - todo

`var someDict:[String:Int] = ["One": 1, "Two": 4, "Three": 9, "Four": 16, "Five": 25]`

- Using `someDict`, add together the values associated with "Three" and "Five" and print the result.

- Add values to the dictionary for the keys "Six" and "Seven".

- Make a key called `productUpToSeven` and set its value equal to the product of all the values.

- Make a key called `sumUpToSix` and set its value equal to the sum of the keys "One", "Two", "Three", "Four", "Five" and "Six".

- Remove the new keys made in the previous two steps

- Add 2 to every value inside of `someDict`.

```
var someDict:[String:Int] = ["One": 1, "Two": 4, "Three": 9, "Four": 16, "Five": 25]

//1
if let three = someDict["Three"], let five = someDict["Five"]{
print(three+five)

//2
someDict["Five"] = 13
someDict["Six"] = 44

//3
var product = 1

for (_,value) in someDict{
product *= value
}

someDict["productUpToSeven"] = product

//4
someDict["sumUpToSix"]

var sum = 0

for (key,value) in someDict {
if key == "Seven" || key == "productUpToSeven" {
continue }
else {
sum += value
}
}

print(sum)

//5
someDict.removeValue(forKey: "productUpToSeven")
someDict.removeValue(forKey: "sumUpToSix")

print(someDict)

//6
for (_,v) in someDict {
v + 2
}
```

## Question 3- done

Create a variable that is explicitly typed as a dictionary that maps strings to floating point numbers. Initialize the variable to the data shown in the table below which lists an author name and their comprehensibility score.

| Author Name |	Score |
| :--: | :--: |
| Mark Twain |	8.9 |
| Nathaniel Hawthorne	| 5.1 |
| John Steinbeck	| 2.3 |
| C.S. Lewis | 9.9 |
| Jon Krakauer | 6.1 |
```
var authorDict: [String:Double] = ["Mark Twain": 8.9, "Nathaniel Hawthorne": 5.1, "John Steinbeck": 2.3, "C.S. Lewis" : 9.9, "Jon Krakauer" : 6.1]

print(authorDict["John Steinbeck"]!)

authorDict["Erick Larson"] = 9.2

if authorDict["Jon Krakauer"]! > authorDict["Mark Twain"]! {
print("Jon Krakauer")
} else {
print("Mark Twain")
}

for (key,value) in authorDict {
print(key,value)
}

```
Using the dictionary created in the previous problem, do the following:

- Print out the floating-point score for “John Steinbeck”.

- Add an additional author named “Erik Larson” with an assigned score of 9.2.

- Write an if/else statement that compares the score of John Krakaur with Mark Twain. Print out the name of the author with the highest score.

- Use a for-loop to iterate through the dictionary you created at the beginning of the problem, and print out the content in the form of key: value, one entry per line.


## Question 4 - done

You are given a dictionary code of type [String:String] which has values for all lowercase letters. The code dictionary represents a way to encode a message. For example if code["a"] = "z" and code["b"] = "x" the encoded version if "ababa" will be "zxzxz". You are also given a message which contains only lowercase letters and spaces. Use the `code` dictionary below to encode the message and print it.

```swift
var code = [
    "a" : "b",
    "b" : "c",
    "c" : "d",
    "d" : "e",
    "e" : "f",
    "f" : "g",
    "g" : "h",
    "h" : "i",
    "i" : "j",
    "j" : "k",
    "k" : "l",
    "l" : "m",
    "m" : "n",
    "n" : "o",
    "o" : "p",
    "p" : "q",
    "q" : "r",
    "r" : "s",
    "s" : "t",
    "t" : "u",
    "u" : "v",
    "v" : "w",
    "w" : "x",
    "x" : "y",
    "y" : "z",
    "z" : "a"
]

var message = "hello world"

var encodedHello = String()

for i in message {
if i == " "{ encodedHello.append(" ") }
if let encodei = code[String(i)]{
encodedHello.append(encodei)
}
}
print(encodedHello)


```

You are also given an `encodedMessage` which contains only lowercase letters and spaces. Use the `code` dictionary to decode the message and print it.
```
var encodedMessage = "uijt nfttbhf jt ibse up sfbe"`

for c in encodedMessage{
if c == " "{
decodedMessage.append(" ")
}
for(key, value) in code{
if String(c) == value{
decodedMessage.append(key)
}
}
}
print(decodedMessage)
```


## Question 5 - done

You are given an array of dictionaries. Each dictionary in the array contains exactly 2 keys `“firstName”` and `“lastName”`. Create an array of strings called `firstNames` that contains only the values for `“firstName”` from each dictionary.

```swift
var people: [[String:String]] = [ [ "firstName": "Calvin", "lastName": "Newton"],["firstName":"Garry", "lastName": "Mckenzie"],["firstName": "Leah","lastName": "Rivera"],["firstName": "Sonja","lastName": "Moreno"],["firstName": "Noel","lastName": "Bowen"]]


print(people[1]["lastName"]!)
for person in people {

}
var lastNames: [String] = []

for person in people {
for (k,v) in person {
if k == "lastName" {
lastNames.append(v)
}
}
}
print(lastNames)

var fullNames: [String] = []

for person in people {
for (k,v) in person {
fullNames.append(v)
}
}

print(fullNames)
```

Now, create an array of strings called `fullNames` that contains the values for `“firstName”` and `“lastName”` from the dictionary separated by a space.


## Question 6 - todo

You are given an array of dictionaries. Each dictionary in the array describes the score of a person. Find the person with the best score and print his full name.

```swift
var peopleWithScores: [[String: String]] = [
    [
        "firstName": "Calvin",
        "lastName": "Newton",
        "score": "13"
    ],
    [
        "firstName": "Garry",
        "lastName": "Mckenzie",
        "score": "23"
    ],
    [
        "firstName": "Leah",
        "lastName": "Rivera",
        "score": "10"
    ],
    [
        "firstName": "Sonja",
        "lastName": "Moreno",
        "score": "3"
    ],
    [
        "firstName": "Noel",
        "lastName": "Bowen",
        "score": "16"
    ]
]
```
var topScorer = (fname: "", lname: "", score: "0")

for arrayOfDictionaries in peopleWithScores {
let keys = arrayOfDictionaries.keys.sorted()
var fname = "", lname = "", score = ""
for key in keys{
if key == "firstName", let fn = arrayOfDictionaries[key]{
fname = fn
}
if key == "lastName", let ln = arrayOfDictionaries[key]{
lname = ln
}
if key == "score", let sc = arrayOfDictionaries[key]{
score = sc
}
}
if let score = Int(score), let topScore = Int(topScorer.score), score > topScore {
topScorer = (fname,lname,String(score))
}
}

print("The best score, \(topScorer.score), is held by \(topScorer.fname) \(topScorer.lname).")

Print out the dictionary above in the following format:  **full name - score**


## Question 7

`var numbers = [1, 2, 3, 2, 3, 5, 2, 1, 3, 4, 2, 2, 2]`

You are given an array of integers. The frequency of a number is the number of times it appears in the array. Find out the frequency of each one.

Print the numbers in ascending order followed by their frequency.

```
var numbers = [1, 2, 3, 2, 3, 5, 2, 1, 3, 4, 2, 2, 2]

var frequencyOfNumbers = [Int : Int]()

numbers.sort()

var currentNum = numbers[0]
var counter = 0

for number in numbers {
if number == currentNum {
counter += 1
frequencyOfNumbers[number] = counter
} else {
currentNum = number
counter = 1
frequencyOfNumbers[number] = counter
}
}
let keys = frequencyOfNumbers.keys.sorted()
for key in keys {
if let value = frequencyOfNumbers[key] {
print("(\(key): \(value))", terminator: " ")
}
}
```


## Question 8

Print the most common letter in the string below:

`var myString = "We're flooding people with information. We need to feed it through a processor. A human must turn information into intelligence or knowledge. We've tended to forget that no computer will ever ask a new question."`


## Question 9

Write code that creates a dictionary where the keys are Ints between 0 and 20 inclusive, and each key's value is its cube.
```
var cubedNumbers = [Int: Int]()
for number in 0...20 {
cubedNumbers[number] = number * number * number
}

print(cubedNumbers)
```

## Question 10

Write code that iterates through `testStates` and prints out whether or not that key is in `statePop`.

```swift
let statePop = ["Alabama": 4.8, "Alaska": 0.7, "Arizona": 6.7, "Arkansas": 3.0]
let testStates = ["California","Arizona", "Alabama", "New Mexico"]
//

let statePopKeys = statePop.keys
for state in testStates {
if statePopKeys.contains(state) {
print("\(state) is a key in statePop.")
} else {
print("\(state) is not a key in statePop.")
}
}
```


## Question 11

You are given the dictionary `deposits`, which maps a persons name to an array of deposits that have been made to their account.

a) Write code to to print the name and total amount deposited of the person who recieved the most money.

b) Create an array called `stolenCents`, iterate over deposits for each person and steal their cents! ... like Office Space or Superman 3. Calculate the decimal part of each value, add it to the `stolenCents` array and round down the value in the dict.

c) How much money did you steal?

```swift
var deposits: [String: [Double]] = [
 "Williams" : [300.65, 270.45, 24.70, 52.00, 99.99],
 "Cooper" : [200.56, 55.00, 600.78, 305.15, 410.76, 35.00],
 "Davies" : [400.98, 56.98, 300.00],
 "Clark" : [555.23, 45.67, 99.95, 80.76, 56.99, 46.50, 265.70],
 "Johnson" : [12.56, 300.00, 640.50, 255.60, 26.88]
]
```


## Question 12

Print the second most common letter in the string below:

`var myString = "We're flooding people with information. We need to feed it through a processor. A human must turn information into intelligence or knowledge. We've tended to forget that no computer will ever ask a new question."`


## Question 13

Given the below 4 arrays of Ints,

a) create a new array, sorted in ascending order, that contains all the values without duplicates.

b) create another new array that contains unique values that appear in all 4 arrays.

```swift
let arr1 = [2, 4, 5, 6, 8, 10, 12]
let arr2 = [1, 2, 3, 4, 5, 6]
let arr3 = [5, 6, 7, 8, 9, 10, 11, 12]
let arr4 = [1, 3, 4, 5, 6, 7, 9]

var arrayofArrs = [arr1,arr2,arr3,arr4]

var setArr: Set <Int> = []

for i in arrayofArrs {
setArr = Set(i).union(setArr)
}

print(setArr.sorted())


```



## Question 14

Given the following exert from the Declaration of Independence, find the most frequent word that is longer than 5 characters.

 - use `components(separatedBy:)` to break up the string into an array.

 - use `CharacterSet.punctuationCharacters` in union with any other characters you don't want in your array, like spaces and new lines.

 ```swift
let declarationOfIndependence = """
When in the Course of human events, it becomes necessary for one people to dissolve the
political bands which have connected them with another, and to assume among the powers of the
earth, the separate and equal station to which the Laws of Nature and of Nature's God entitle
them, a decent respect to the opinions of mankind requires that they should declare the causes
which impel them to the separation.

We hold these truths to be self-evident, that all men are created equal, that they are endowed by
their Creator with certain unalienable Rights, that among these are Life, Liberty and the pursuit
of Happiness. That to secure these rights, Governments are instituted among Men, deriving
their just powers from the consent of the governed, That whenever any Form of Government
becomes destructive of these ends, it is the Right of the People to alter or to abolish it, and to
institute new Government, laying its foundation on such principles and organizing its powers in
such form, as to them shall seem most likely to effect their Safety and Happiness. Prudence,
indeed, will dictate that Governments long established should not be changed for light and
transient causes; and accordingly all experience hath shewn, that mankind are more disposed to
suffer, while evils are sufferable, than to right themselves by abolishing the forms to which they
are accustomed. But when a long train of abuses and usurpations, pursuing invariably the same
Object evinces a design to reduce them under absolute Despotism, it is their right, it is their duty,
to throw off such Government, and to provide new Guards for their future security. Such has
been the patient sufferance of these Colonies; and such is now the necessity which constrains
them to alter their former Systems of Government. The history of the present King of Great
Britain is a history of repeated injuries and usurpations, all having in direct object the
establishment of an absolute Tyranny over these States. To prove this, let Facts be submitted to a
candid world.
"""
```
```
