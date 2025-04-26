# React-Interview

# 1. JavaScript Callbacks
Answer: A callback is a function that is passed as an argument to another function and is executed after the completion of the other function.
Example: 
        functon show(sum){
            alart('i am  show function + sum );
        }
        funcction display(num1,num2,myshow){
            let sum = num1 +num2;
            myshow(sum);

        }
        display(10,20,show);

# 2. What is a Promise?
Answer: A Promise is a way to handle tasks that take time, like fetching data from a server.

It has 3 states:

Pending – Work is still going on

Resolved – Work is done successfully

Rejected – Work failed

code example:
let promise = new Promise(function(resolve, reject) {
  let success = true;

  if (success) {
    resolve("Task done!");
  } else {
    reject("Task failed!");
  }
});

promise.then((message) => {
  console.log(message);  // Task done!
}).catch((error) => {
  console.log(error);
});

# 3. what is Hosting?
Answer: Hoisting means JavaScript moves declarations (like var, function) to the top of the code before running it.

Example: console.log(a);  // undefined
         var a = 5;

JavaScript changes it like this behind the scenes:

var a;
console.log(a);  // undefined
a = 5;
# 4. What is the difference between let and var?
Answer: let is block-scoped and var is function-scoped.

# 5. what is closure?
Answer:  A closer is a inner function that can access the outer function variables as well as global variables.

Example:
        function greet(name) {
  return function() {
    console.log("Hello, " + name);
  };
}

const sayHello = greet("Saurabh");

sayHello();  // Hello, Saurabh

# 6. Different between Function Component and Class Component?
Answer:
Great! This is a very common React question. Here’s the difference in **simple words** with an example.

---

### 👉 Difference between **Function Component** and **Class Component**:

| Feature             | Function Component                  | Class Component                          |
|---------------------|-------------------------------------|-------------------------------------------|
| Syntax              | Simple function                     | Uses class and extends `React.Component` |
| `this` keyword      | Not used                            | Used                                      |
| State               | Use `useState()`                    | Use `this.state`                         |
| Lifecycle Methods   | Use `useEffect()`                   | Has methods like `componentDidMount()`   |
| Code Length         | Short and clean                     | Longer and more complex                  |

---

### ✅ Function Component Example:

```javascript
import React, { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  return <button onClick={() => setCount(count + 1)}>Click {count}</button>;
}
```

---

### ✅ Class Component Example:

```javascript
import React from "react";

class Counter extends React.Component {
  constructor() {
    super();
    this.state = { count: 0 };
  }

  render() {
    return (
      <button onClick={() => this.setState({ count: this.state.count + 1 })}>
        Click {this.state.count}
      </button>
    );
  }
}
```

---

### 👍 Tip:
Today, we mostly use **Function Components** with **Hooks** (like `useState`, `useEffect`).

# 7. what is useState?
Answer: 1. useState is a React hook that allows you to add state to a functional component.
2. It returns an array with two values: the current state and a function to update it.
3. To track state, state like data or properties that change over time.

Example:
import React, { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);  // count = value, setCount = function to update

  return (
    <button onClick={() => setCount(count + 1)}>
      Clicked {count} times
    </button>
  );
}
export default Counter;

# 8. What is jsx.
Answer: 
JSX stands for JavaScript XML.
It lets you write HTML inside JavaScript in React.
we used JSX to create User interfaces.
we can write html inside javascript using JSX.
Browser can't read JSX., s Bablel is compiler which converts JSX into javascript.

# 9. Different in setTimeout and setInterval.
Answer:
The setTimeout() method calls a function only on time at specified time.
The setInterval() method calls a function repeatedly at specified time intervals.

### ✅ `setTimeout` Example:

```javascript
setTimeout(() => {
  console.log("Hello after 2 seconds");
}, 2000);
```

➡️ Runs once after **2 seconds**.

---

### ✅ `setInterval` Example:

```javascript
setInterval(() => {
  console.log("Hello every 2 seconds");
}, 2000);
```

➡️ Runs again and again **every 2 seconds**.

---

### 💡 Bonus Tip:
To **stop** `setInterval`, use `clearInterval()` with an ID.

```javascript
const id = setInterval(() => {
  console.log("Running...");
}, 1000);

clearInterval(id);  // Stops it
```

# 10. NPM VS Yarn.
Answer: 
NPM is a package manager for Node.js.
Yarn is a package manager for Node.js.

# 11. What is flux?
Answer:
---

### 👉 What is **Flux**?

**Flux** is an **architecture** (or pattern) used in React to manage **data flow** in your app.

It helps keep **data organized** when your app grows big.

---

### 📌 In simple words:
Flux is a way to **control how data moves** in your React app — in **one direction** only (called **unidirectional flow**).

---

### ✅ Main parts of Flux:

1. **Action** – What happened (like "user clicked")
2. **Dispatcher** – Sends the action to the right place
3. **Store** – Stores (saves) the data
4. **View** – React UI that shows the data

---

### 🔄 Data Flow (one way):

```
View → Action → Dispatcher → Store → View
```

---

### 💡 Example:
If you click a "Like" button:

1. **Action:** "User liked the post"
2. **Dispatcher:** Sends it
3. **Store:** Updates the like count
4. **View:** Shows the new like count

---

### 🧠 Bonus:
- **Redux** is based on Flux.
- In small apps, you don’t need Flux. But in large apps, it helps manage complex data.

# 12. JavaScript EventListener.
Answer: AddEneventListener() is Javascript method that allows adding more than one handler for an event.

syntax- 
element.addEventListener(evnt, function, useCapture);
event and function is required, useCapture is optional.

# 13. what is the use of refs ?
Answer: Using useref hook we can handle Dom Element manipulation,for this web add a ref qttribute to an element to access it directly in the Dom.

import React, { useRef } from "react";

const ElementRef = useRef("");
<input ref={ElementRef} type="text" value="hello" />
ElementRef.current.style.cplor="red";

# 14. what is the props in react?
Answer:props stands for properties, props are used to pass data from one component to another component.

<Header title='php tutorial' authoer='shishir'/>    passsing props in functional component and component are same but on receive some difference.

function component receive as function argument 
class component reveive by this.props properties.

# 15. what is Controlled and Uncontrolled Component?
Answer:
Controlled component:
From Data handled a React component men uing ueState we can do.

cont[name, setName] = useState("");
<input type="text" value={name} onChange={(e) => setName(e.target.value)} />

Uncontrolled component:
From Data handled by the DOM .we use UsseRef hook to handle this.

const inputRef = useRef();
nmeref.current.value;
<input type="text" ref={inputRef} required />

# 16. what is Hooks React?
Answer:

# 17. what is Prop dilling?
Answer:Propo drilling iss a sitution when we passsing some data to every leve nd our requirement i for final level component so we are unnecessary passing data.

To avoid this issue we can use.

1-Redux
2-Context
3-Component Composition

# 18. what is shallow copy and deep copy in javaScript?
Answer:
shallow copy: Coping only top level element, it means certain values are still connected to the original variable.

Deep copy: Copying top level and nested elements, it makes a copy of copy of all attributes of the old object and allocates separate memory address for the new object.

et personObj = {
    Name: "saurabh",
    age: 25,
    address: {
        city: "nawada",
        state: "bihar"
    }

}

let shallowCopy = Object.assign({}, personObj); 
let deepCopy = JSON.parse(JSON.stringify(personObj));

# 19. what is an event loop in JavaScript?
Answer:
. javaScript is a single-threaded language, which means it can only execute one task at a time.
. so for this purpose it use stack means global execution context.

# 20. wht i emntic UI?
Answer: semantic UI used to build UI for app very fastly and easily,we can also say react ui libraries.

List of UI libraries.
1-Material UI
2-Ant Design
3-Semantic UI
4-Bootstrap
5-React Bootstrap
6-redux
7-Fluent UI

# 21. how  Redux works?
Answer:
.Redux is a state management library for JavaScript apps.
.it is third party libraly.
.we can use Redux in anywhere like angular,vue,react etc.

Store : where we store all states.
Components: here we are use states.
Action: type(increment,decrement) and payload(data).
Dispatcher: dispatch() is the method used to dispatch action and trigger state changes to the store.
Reducer: here we can write logic to change the states.

# 22. what is useReducer hook?
Answer: .useReducer Hook is similar to the useState Hook.
.useReducer (<reducer>, <initialState>)
.useReucer Hook returrn the current state and a dispatch methhod.

# 23. what is Memoization?
Answer: .memoization is a technique for speeding up applications by caching.
.javascript
.React useMemo Hook.

# 24. what is Higherr Order Component?
Answer: .it is a component.
.it take another component as an argument.
.it return a new component.

# 25. what is Life cycle method in React?
Answer: In React Each component has three phases that is Mounting,Updating, and Unmounting.

1.Mounting:
Mounting means putting elements into the DOM.

2.Updating:
Updating means updating a component.

3.Unmounting:
Unmounting means removed from the Dom.

# 26. what is Readux Thunk?
Answer: .Redux Thunk is a middleware. its is a function that return another function.

And the purpose of middleware is to intercept an action before it reaches the reducer.

Instead of sending the action to the reducer directly.

First it will go to middleware by thunk and if need some change like type, payload then do it and then pass to reducers.

# 27. what is Lexicial scoping?
Answer: Using lexial scoping, In inner function we can access the variable of the outer fuunction.
.mean we can access the variable of the outer function in the inner function.
.The child function is seen to have lexically bound the parent function.
.it is also called static scoping.

# 28. what is Pure function?
Answer: .A pure function is a function that always returns the same result if the same arguments are passed.
.pure function is function that accept argument and return value.
.it is depend upon what argument are you passing.
.it does not modifying any value.
.its output doesn't get affected by other values and state.


# 29. what is Pure component in Class Component?
Answer: .Pure Component is similar to component but it skips re-renders for same props and state.
.PureComponent is a subclass of compontns

# 30. what is React Router?
Answer: .React Router is a standard library for routing in React.
.it enables the navigation among views of various components in a React Application, allows changing the browser URL, and keeps the UI in sync with the URL.

# 31. what is React Router Dom?
Answer: .React Router Dom is a library for routing in react.
.it is a library for routing in react.
.