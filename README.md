# 0037_codewars_algorithms

## 5/20/2017

## [Delete occurrences of an element if it occurs more than n times](https://www.codewars.com/kata/554ca54ffa7d91b236000023/train/javascript)

- Given a list lst and a number N, create a new list that contains each number of lst at most N times without reordering. For example if N = 2, and the input is [1,2,3,1,2,1,2,3], you take [1,2,3,1,2], drop the next [1,2] since this would lead to 1 and 2 being in the result 3 times, and then take 3, which leads to [1,2,3,1,2,3].

```js
function deleteNth(arr, n) {
  let obj = {};

  return arr.filter(function(num) {
    obj[num] = obj[num] ? obj[num] + 1 : 1;

    if (obj[num] <= n) {
      return obj[num];
    }
  })
}

deleteNth([20,37,20,21],1) // return [20,37,21]
deleteNth([20,37,20,21,37,20], 3) // [ 20, 37, 20, 21, 37 ]
deleteNth([1,1,1,1],2) // return [1,1]
```

# 12/26/2017

## Find the divisors!

```js
function divisors(integer) {
  let arr = [];

  for (var i = 2; i < integer; i++){
    if (Number.isInteger(integer/i)) {
      arr.push(i);
    }
  }

  if (arr[0] === undefined) {
    return `${integer} is prime`;
  } else {
    return arr;
  }
}

divisors(15)
```

# 12/24/2017

## Convert string to camel case

```js
function toCamelCase(str){
  let array = str.split(/[-_]/gi);
  let newArr = array[0];

  if (str === '') {
    return '';
  }

  for (var i = 1; i < array.length; i++) {
    let str = array[i].charAt(0).toUpperCase() + array[i].slice(1);
    newArr += str;
  }

  return newArr;
}

toCamelCase("the-stealth-warrior")
```

# 12/23/2017

## Sum of all the multiples of 3 or 5

```js
function findSum(n) {
  let multiples = [];

  for (var i = 0; i <= n; i++) {
    if (i % 3 === 0 || i % 5 === 0) {
      multiples.push(i);
    }
  }
  return multiples.reduce((prev, next) => prev + next);
}

findSum(5);
```

## Opposite Number

```js
function opposite(number) {
  return number * (-1);
}
```

## Disemvowel Trolls

```js
function disemvowel(str) {
  str = str.replace(/a/gi, '');
  str = str.replace(/e/gi, '');
  str = str.replace(/i/gi, '');
  str = str.replace(/o/gi, '');
  str = str.replace(/u/gi, '');
  return str;
}

disemvowel("This website is for losers LOL!")
```

## Convert boolean values to strings 'Yes' or 'No'.

```js
function boolToWord( bool ){
  if (bool === true) {
    return "Yes";
  }
  else if (bool === false) {
    return "No";
  }
}
```

## Highest and Lowest

```js
function highAndLow(numbers){
  var str = "";

  // Convert string to an array
  // Sort the array for lowest and highest
  var arr = numbers.split(" ").sort(function(a,b){return a - b})

  // Return the high and low values
  str += (arr[arr.length - 1]) + " " + arr[0];
  return str;
}
```

## List filtering

```js
function filter_list(l) {
  let newArr = [];

  for(var i = 0; i < l.length; i++) {
    if(typeof l[i] === 'number') {
      newArr.push(l[i]);
    }
  }
  return newArr;
}
```

## Who likes it?

```js
var array = ["Alex", "Jacob", "Mark", "Max"];

function likes(names) {
  if (names.length === 0) {
    return "no one likes this";
  }

  else if (names.length === 1) {
    return `${names[0]} likes this`;
  }

  else if (names.length === 2) {
    return `${names[0]} and ${names[1]} like this`;
  }

  else if (names.length === 3) {
    return `${names[0]}, ${names[1]} and ${names[2]} like this`;
  }

  else {
    return `${names[0]}, ${names[1]} and ${names.length - 2} others like this`;
  }
}

likes(array);
```

## Mumbling

```js
accum("abcd");    // "A-Bb-Ccc-Dddd"

function accum(s) {
  let newStr = s.toLowerCase();
  let newArr = [];
  for (var i = 0; i < newStr.length; i++) {
    newArr.push(newStr[i].toUpperCase() + newStr[i].repeat(i))
  }
  return newArr.join('-');
}

// Solution 1
function accum(s) {
  return s.split('').map((x,index) => x.toUpperCase()+Array(index+1).join(x.toLowerCase())).join('-');
}

// Solution 2
function accum(s) {
  return s.split('').map((c, i) => (c.toUpperCase() + c.toLowerCase().repeat(i))).join('-');
}
```

## Money, Money, Money

```js
function calculateYears(principal, interest, tax, desired) {
  let newPrincipal = principal;
  let years = 0;

  while (newPrincipal < desired) {
    let newInterest = newPrincipal * interest;
    let afterTax = newInterest - (newInterest * tax);
    newPrincipal += afterTax;
    years++;
  }

  return years;
}

calculateYears(1000, 0.05, 0.18, 1100);
calculateYears(1000,0.01625,0.18,1200);
```

## Printer Errors

```js
// 1. Loop over string
// 2. Add to counter if error
// 3. Return number of errrors
var s="aaaaaaaaaaaaaaaabbbbbbbbbbbbbbbbbbmmmmmmmmmmmmmmmmmmmxyz"

function printerError(s) {
  var count = s.search(/[n-z]/gi);

  if (count === -1) {
    return `0/${s.length}`;
  } else {
    return `${s.match(/[n-z]/gi).length}/${s.length}`;
  }
}


var s = "Hello World!!!1";
var rx = /[a-z]/gi;
var m = s.match(rx);
if (m) {
  console.log(m.length);
}
```
