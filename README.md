# angular-notes
Angular Interview Notes
WEB BASICS-HTML and CSS
1.	Request Lifecycle
Local Processing->Resolve an IP->Establish TCP connection->Send HTTP request->tearing down,cleaning up
If you go to www.google.com (not using any forms, just wanting the site), this is what happens:First the browser needs to translate www.google.com to an IP address if it does not already know it. If it knows it, nothing happens at this point. If it does not know it, it contacts a DNS server to resolve the name.
1.	Then browser will open a TCP connection to the IP address of www.google.com and send a HTTP GET request over. In this example it will be
GET / HTTP/1.1 Host: www.google.com
2.	The server software will get this HTTP request. It will somehow generate a HTTP response and send that back trough the TCP connection. How the server does this is server software dependent. You can for example plug in application code in Apache, or just make Apache return a file from the filesystem. PHP is an application called by some software, which then generates the response sent to the browser. When the response is sent, in HTTP version 1.0 the connection is closed. HTTP 1.1 can have persistent connections though.
3.	When the browser gets the response, it typically renders it on screen. The HTTP request is now done. A click on "search" will send a new request to the server.

2.	Atomic Design
 
Atomic Design  involves breaking a website down into its basic components and then working up from there to create a site. 
You can mix and match components
•	Reusabilty
•	Creating a style guide is simple
•	Code is more consistent 
•	Quicker prototyping
•	Easier to update and remove parts of the site

3.	Design Systems 
A design system is a set of standards to manage design at scale by reducing redundancy while creating a shared language and visual consistency across different pages and channels.

4.	Semantic HTML
but using them helps browsers, screen-readers, and other tools understand the content they contain.
•	A semantic element clearly describes its meaning to both the browser and the developer.Examples of non-semantic elements: <div> and <span> - Tells nothing about its content.Examples of semantic elements: <form>, <table>, and <article> - Clearly defines its content. 
•	<article>
•	<aside>
•	<details>
•	<figcaption>
•	<figure>
•	<footer>
•	<header>
•	<main>
•	<mark>
•	<nav>
•	<section>
•	<summary>
•	<time>
5.	DOM
•	The DOM is a W3C (World Wide Web Consortium) standard.
•	The DOM defines a standard for accessing documents:
•	"The W3C Document Object Model (DOM) is a platform and language-neutral interface that allows programs and scripts to dynamically access and update the content, structure, and style of a document."
•	The W3C DOM standard is separated into 3 different parts:
•	Core DOM - standard model for all document types
•	XML DOM - standard model for XML documents
•	HTML DOM - standard model for HTML documents
 
6.	Forms and Validations
7.	Media Responsive Images,Audio and Video
.responsive {
  width: 100%;
  max-width: 400px;
  height: auto;
}

<audio controls autoplay muted>
  <source src="horse.ogg" type="audio/ogg">
  <source src="horse.mp3" type="audio/mpeg">
Your browser does not support the audio element.
</audio>

<video width="320" height="240" controls>
  <source src="movie.mp4" type="video/mp4">
  <source src="movie.ogg" type="video/ogg">
Your browser does not support the video tag.
</video>

<iframe width="420" height="345" src="https://www.youtube.com/embed/tgbNymZ7vqY">
</iframe>
8.	Browser Side workers,storage,workers caching-local,session,cookies,Indexdb,WebSQL
Worklets are hooks into the browser’s rendering pipeline, enabling us to have low-level access to the browser’s rendering processes such as styling and layout.
Web Workers
Web Workers provide a simple means for web content to run scripts in background threads. The worker thread can perform tasks without interfering with the user interface. In addition, they can perform I/O using XMLHttpRequest (although the responseXML and channel attributes are always null). Once created, a worker can send messages to the JavaScript code that created it by posting messages to an event handler specified by that code (and vice versa.)
Source - Using Web Workers
Service Worker
Service workers essentially act as proxy servers that sit between web applications, and the browser and network (when available). They are intended to (amongst other things) enable the creation of effective offline experiences, intercepting network requests and taking appropriate action based on whether the network is available and updated assets reside on the server. They will also allow access to push notifications and background sync APIs.
9.	Service workers,Web workers
10.	SEO basics
A Secure and Accessible Website.
Page Speed (Including Mobile Page Speed)
Mobile Friendliness.
Domain Age, URL, and Authority.
Optimized Content.
Technical SEO.
User Experience (RankBrain)
Links.
11.	CSSOM,rules,selectors,property values,cascading,inheritance,specificity
12.	Responsive design mobile and desktop first,media
Hiding an Image in CSS
The trick to hiding any element on your web page is to insert either a "display: none;" or "visibility: hidden;" rule for that element. The "display: none;" rule not only hides the element, but also removes it from the document flow. That is, the web browser will not leave any space for that element when it displays the page. The "visibility: hidden;" rule hides the element but causes the browser to still leave an appropriate amount of blank space for it.
To suppress the display of the image only on devices with a small screen, like mobile phones, include the rule in the section of your style sheet that is only applied in such instances.
Take the following as an example.
@media (max-width:629px) {
  img#optionalstuff {
    display: none;
  }
}

13.	Layout float,flex,grid,display,positioning
14.	Animations and translations,basics,SVG
15.	Processors,preprocessors,frameworks,CSS in JS
A CSS preprocessor is a program that lets you generate CSS from the preprocessor's own unique syntax.

There are many CSS preprocessors to choose from, however most CSS preprocessors will add some features that don't exist in pure CSS, such as mixin, nesting selector, inheritance selector, and so on. These features make the CSS structure more readable and easier to maintain.

To use a CSS preprocessor, you must install a CSS compiler on your web server; Or use the CSS preprocessor to compile on the development environment, and then upload compiled CSS file to the web server.

Generally speaking, pre-processing has its own stylesheet languages, such as Sass and LESS, that convert into pure CSS. Post-processing takes that basic CSS, and applies automation/repetition. It usually means adding code to fallbacks for older browsers,
OOJS/Functional JS
1.	Variables,Scopes,Datatypes
Scope determines the accessibility (visibility) of variables.
JavaScript has 3 types of scope:
•	Block scope
•	Function scope
•	Global scope
•	ES6 introduced two important new JavaScript keywords: let and const.
•	These two keywords provide Block Scope in JavaScript.
•	Variables declared inside a { } block cannot be accessed from outside the block:
•	Function Scope
•	JavaScript has function scope: Each function creates a new scope.
•	Variables defined inside a function are not accessible (visible) from outside the function.
•	Variables declared with var, let and const are quite similar when declared inside a function.
•	They all have Function Scope:
•	function myFunction() {
  var carName = "Volvo";   // Function Scope
}
•	function myFunction() {
  let carName = "Volvo";   // Function Scope
}
•	function myFunction() {
  const carName = "Volvo";   // Function Scope
}
•	Global Scope
•	Variables declared Globally (outside any function) have Global Scope.
•	Global variables can be accessed from anywhere in a JavaScript program.
•	Variables declared with var, let and const are quite similar when declared outside a block.
•	They all have Global Scope:
•	var x = 2;       // Global scope
•	let x = 2;       // Global scope
•	const x = 2;       // Global scope
•	Global variables defined with the let keyword do not belong to the window object:
•	let carName = "Volvo";
// code here can not use window.carName
Hoisting is JavaScript's default behavior of moving all declarations to the top of the current scope (to the top of the current script or the current function).
The let and const Keywords
Variables defined with let and const are hoisted to the top of the block, but not initialized.
Meaning: The block of code is aware of the variable, but it cannot be used until it has been declared.
Using a let variable before it is declared will result in a ReferenceError. Var will give undefined
The variable is in a "temporal dead zone" from the start of the block until it is declared:

typeof ""             // Returns "string"
typeof "John"         // Returns "string"
typeof "John Doe"     // Returns "string"

2.	Operators loops,If statement
For(let i=0;i<n;i++){}
For(let I in array){I->index}
For(let val of array)-?gives value

let language = "JavaScript";

let text = "";
for (let x of language) {
text += x;
}
3.	Error handling and functions
Try,catch,finally,throw
try {
  writeMyFile(theData); // This may throw an error
} catch(e) {
  handleError(e); // If an error occurred, handle it
} finally {
  closeMyFile(); // Always close the resource
}

4.	Execution context(this)
Execution context (EC) is defined as the environment in which the JavaScript code is executed. By environment, I mean the value of this, variables, objects, and functions JavaScript code has access to at a particular time.
Execution context in JavaScript is of three types as:
Global execution context (GEC): This is the default execution context in which JS code start its execution when the file first loads in the browser. All of the global code i.e. code which is not inside any function or object is executed inside the global execution context. GEC cannot be more than one because only one global environment is possible for JS code execution as the JS engine is single threaded.
Functional execution context (FEC): Functional execution context is defined as the context created by the JS engine whenever it finds any function call. Each function has its own execution context. It can be more than one. Functional execution context has access to all the code of the global execution context though vice versa is not applicable. While executing the global execution context code, if JS engine finds a function call, it creates a new functional execution context for that function. In the browser context, if the code is executing in strict mode value of this is undefined else it is window object in the function execution context.
Eval: Execution context inside eval function.
Execution context stack (ECS): Execution context stack is a stack data structure, i.e. last in first out data structure, to store all the execution stacks created during the life cycle of the script. Global execution context is present by default in execution context stack and it is at the bottom of the stack. While executing the global execution context code, if JS engines find a function call, it creates a functional execution context for that function and pushes it on top of the execution context stack. JS engine executes the function whose execution context is at the top of the execution context stack. Once all the code of the function is executed, JS engines pop out that function’s execution context and start’s executing the function which is below it.
5.	Call,bind apply
BASIC RULES WORTH REMEMBERING:
1.	“this” always refers to an object.
2.	“this” refers to an object which calls the function it contains.
3.	In the global context “this” refers to either window object or is undefined if the ‘strict mode’ is used.
var car = { 
    registrationNumber: "GA12345",
    brand: "Toyota",

    displayDetails: function(){
        console.log(this.registrationNumber + " " + this.brand);
    }
}
The above will work perfectly fine as long as we use it this way:

car.displayDetails(); // GA12345 Toyota
But what if we want to borrow a method?

var myCarDetails =  car.displayDetails;
myCarDetails();
Well, this won’t work as the “this” will be now assigned to the global context which doesn’t have neither the registrationNumber nor the brand property.
The bind() Method
For such cases we can use the ECMAScript 5 bind() method of the Function.prototype property. This means bind() can be used by every single function.

var myCarDetails = car.displayDetails.bind(car); 
myCarDetails(); // GA12345 Toyota
The bind() method creates a new function where “this” refers to the parameter in the parenthesis in the above case “car”. This way the bind() method enables calling a function with a specified “this” value. call() and apply() methods
Similar but slightly different usage provide the call() and apply() methods which also belong to the Function.prototype property.

This time there is a car object without the displayDetails function, which is located in the global context.

var car = { 
    registrationNumber: "GA12345",
    brand: "Toyota"
}

function displayDetails(ownerName) {
    console.log(ownerName + ", this is your car: " + this.registrationNumber + " " + this.brand);
}
We can use the apply() function:

displayDetails.apply(car, ["Vivian"]); // Vivian, this is your car: GA12345 Toyota
Or

displayDetails.call(car, "Vivian"); // Vivian, this is your car: GA12345 Toyota
Note that when using the apply() function the parameter must be placed in an array. Call() accepts both an array of parameters and a parameter itself. Both are great tools for borrowing functions in JavaScript.

6.	ES5 vs ES6
In ES6, there are some additions to JavaScript data types. It introduced a new primitive data type 'symbol' for supporting unique values.
It was part of ES6 specification and its sole purpose is to act as a unique identifier of object properties, i.e. it can be used as a key in objects. You can think of symbols as big numbers and every time you create a symbol, a new random number gets generated (uuid).
In ES6, there are two new ways to define variables that are let and const.

An arrow function is a new feature introduced in ES6 by which we don't require the function keyword to define the function.
ES6 introduced the concept of for...of loop to perform an iteration over the values of the iterable objects.

Due to destructuring and speed operators, object manipulation can be processed more smoothly in ES6.
Transpilation
As of now, there are no browsers that fully support the ES6 features; however, we can convert the ES6 code to the ES5 code by using the transpilation.

There are two major compilers Babel and Traceur, which are used to convert the ES6 code to ES5 code as part of the build process.

Spread Operator (...)
It is introduced in ES6, which makes it easy to merge arrays and objects.

Template Literal (`)
It is a new feature introduced in ES6 that allows us to work with strings. Template literals allow us to perform string interpolation easily.

7.	Events and Event handling ,DOM manipulation
onchange	An HTML element has been changed
onclick	The user clicks an HTML element
onmouseover	The user moves the mouse over an HTML element
onmouseout	The user moves the mouse away from an HTML element
onkeydown	The user pushes a keyboard key
onload	The browser has finished loading the page

8.	Object prototype,prototype inheritance,Closure
let person = {
    name: "John Doe",
    greet: function () {
        return "Hi, I'm " + this.name;
    }
};

let teacher = {
    teach: function (subject) {
        return this.greet()+" I can teach " + subject;
    }
};

teacher.__proto__=person;
console.log(teacher.name);
console.log(teacher.teach('Maths'));

class person  {
   constructor(name){
   this.name=name;
   }
    greet() {
        return "Hi, I'm " + this.name;
    }
}

class teacher extends person {
constructor(name,subject){
  super(name);
  this.subject=subject;
   }
   teach() {
        return this.greet() + this.subject;
    }
}

let teacherSub= new teacher('subin','Maths');

console.log(teacherSub.name);
console.log(teacherSub.teach());
9.	Async Programming-Event loops- how it works, macro and micro tasks
The event loop concept is very simple. There’s an endless loop, where the JavaScript engine waits for tasks, executes them and then sleeps, waiting for more tasks.
The general algorithm of the engine:
1.	While there are tasks:
o	execute them, starting with the oldest task.
2.	Sleep until a task appears, then go to 1.
 
Microtasks come solely from our code. They are usually created by promises: an execution of .then/catch/finally handler becomes a microtask. Microtasks are used “under the cover” of await as well, as it’s another form of promise handling.
There’s also a special function queueMicrotask(func) that queues func for execution in the microtask queue.
Immediately after every macrotask, the engine executes all tasks from microtask queue, prior to running any other macrotasks or rendering or anything else.
For instance, take a look:
setTimeout(() => alert("timeout"));

Promise.resolve()
  .then(() => alert("promise"));

alert("code");
Web Workers
For long heavy calculations that shouldn’t block the event loop, we can use Web Workers.
That’s a way to run code in another, parallel thread.
Web Workers can exchange messages with the main process, but they have their own variables, and their own event loop.
Web Workers do not have access to DOM, so they are useful, mainly, for calculations, to use multiple CPU cores simultaneously.

10.	Callbacks and setTimeout,promises,chaining promises
11.	Promise.all,promise.race
Promise.all accepts an array of promises, and will attempt to fulfill all of them. Exits early if just 1 promise gets rejected.
Promise.race also accepts an array of promises, but returns the first promise that is settled. A settled promise can either be resolved or rejected.
12.	Async await
13.	Error handling
14.	Testing,POV on different types of tests,TL,Jest,karma,jasmine,Enzyme
15.	Patterns,Module systems,principles
16.	Singleton,factory functions,module,prototype,Pubsub,observable
17.	Common JS ,UMD AMD
CJS
CJS is short for CommonJS. Here is what it looks like:
//importing 
const doSomething = require('./doSomething.js'); 

//exporting
module.exports = function doSomething(n) {
  // do something
}
•	Some of you may immediately recognize CJS syntax from node. That's because node uses CJS module format.
•	CJS imports module synchronously.
•	You can import from a library node_modules or local dir. Either by const myLocalModule = require('./some/local/file.js') or var React = require('react'); works.
•	When CJS imports, it will give you a copy of the imported object.
•	CJS will not work in the browser. It will have to be transpiled and bundled.
AMD
AMD stands for Asynchronous Module Definition. Here is a sample code:
define(['dep1', 'dep2'], function (dep1, dep2) {
    //Define the module value by returning a value.
    return function () {};
});
or
// "simplified CommonJS wrapping" https://requirejs.org/docs/whyamd.html
define(function (require) {
    var dep1 = require('dep1'),
        dep2 = require('dep2');
    return function () {};
});
•	AMD imports modules asynchronously (hence the name).
•	AMD is made for frontend (when it was proposed) (while CJS backend).
•	AMD syntax is less intuitive than CJS. I think of AMD as the exact opposite sibling of CJS.
UMD
UMD stands for Universal Module Definition. Here is what it may look like (source):
(function (root, factory) {
    if (typeof define === "function" && define.amd) {
        define(["jquery", "underscore"], factory);
    } else if (typeof exports === "object") {
        module.exports = factory(require("jquery"), require("underscore"));
    } else {
        root.Requester = factory(root.$, root._);
    }
}(this, function ($, _) {
    // this is where I defined my module implementation

    var Requester = { // ... };

    return Requester;
}));
•	Works on front and back end (hence the name universal).
•	Unlike CJS or AMD, UMD is more like a pattern to configure several module systems. Check here for more patterns.
•	UMD is usually used as a fallback module when using bundler like Rollup/ Webpack
ESM
ESM stands for ES Modules. It is Javascript's proposal to implement a standard module system. I am sure many of you have seen this:
import React from 'react';
Other sightings in the wild:
import {foo, bar} from './myLib';

...

export default function() {
  // your Function
};
export const function1() {...};
export const function2() {...};
•	Works in many modern browsers
•	It has the best of both worlds: CJS-like simple syntax and AMD's async
•	Tree-shakeable, due to ES6's static module structure
•	ESM allows bundlers like Rollup to remove unnecessary code, allowing sites to ship less codes to get faster load.

18.	12 factor APP,SOLID,DRY principles
19.	Functional programming pure fn/side effects,purigying closures,paint free style,composition,compound functions
20.	Immutability,mab,filter,reduce
With Object.freeze we achieve full immutability. But there are two other methods that provide object immutability, only partially.
•	Object.seal – We can not add a new property or delete existing properties of an object sealed with this method. But we can still update the value of existing properties.
•	Object.preventExtensions – This method prevents new property creation. But you can update and delete existing properties.

const numbers = [1, 2, 3, 4];
const doubled = numbers.map(item => item * 2);
console.log(doubled); // [2, 4, 6, 8]

const numbers = [1, 2, 3, 4];
const evens = numbers.filter(item => item % 2 === 0);
console.log(evens); // [2, 4]

var pets = ['dog', 'chicken', 'cat', 'dog', 'chicken', 'chicken', 'rabbit'];

var petCounts = pets.reduce(function(obj, pet){
    if (!obj[pet]) {
        obj[pet] = 1;
    } else {
        obj[pet]++;
    }
    return obj;
}, {});

console.log(petCounts); 

/*
Output:
 { 
    dog: 2, 
    chicken: 3, 
    cat: 1, 
    rabbit: 1 
 }
 */
const numbers = [1, 2, 3, 4];
const sum = numbers.reduce(function (result, item) {
  return result + item;
}, 0);
console.log(sum); // 10

21.	Higher order fn,currying and composition
Currying is a checking method to make sure that you get everything you need before you proceed. It helps you to avoid passing the same variable again and again. It divides your function into multiple smaller functions that can handle one responsibility.
Function composition is the process of combining two or more functions to produce a new function. Composing functions together is like snapping together a series of pipes for our data to flow through.

const toSlug = input => encodeURIComponent(
	  input.split(' ')
	    .map(str => str.toLowerCase())
	    .join('-')
	);

If we use the higher order function, filter(), we can abstract so much:
const numbers = [1, 2, 3, 4, 5];

const oddArray = numbers.filter((number) => number % 2 !== 0);
console.log(oddArray);
In this definition, operations can mean taking one or more functions as an argument OR returning a function as the result. It doesn't have to do both. Doing one or the other qualifies a function as a higher order function.
Higher Order Functions provide a higher level of abstraction for functions.

What is currying in JavaScript?
Currying simply means evaluating functions with multiple arguments and decomposing them into a sequence of functions with a single argument.
In other terms, currying is when a function — instead of taking all arguments at one time — takes the first one and returns a new function, which takes the second one and returns a new function, which takes the third one, etc. until all arguments are completed.

22.	PWA-app manifest
Smaller and Faster: The progressive web apps are much smaller in size than native apps. They don’t even need to install. That’s they are not wasting disc space and load very fast.
Responsive Interface: Progressive web app (PWA) supported web pages are capable to fit in every screen sizes automatically. It could be a smartphone, tablet, desktop or laptop.
No Updates Required: Most of the mobile apps need regular weekly updates. Like the normal website, progressive web apps (PWA) are always loaded latest updated version whenever the user interaction happens and no App or Play Store approval required.
Cost Effective: Native mobile apps need to be developed for both Android and iOS devices separately and their development cost is very high. On the other hand, progressive web apps are had the same features but the fraction of the prior price.
SEO Advantage: Progressive web apps are discoverable by search engines and load super-fast. Just like other websites, their links are sharable too. This, in other words, gives good user experience and result in SEO rank boost.
Offline capabilities: Due to the support of service worker API, PWAs are accessible in offline or low internet connections.
Security: PWAs are delivered over HTTPS connection and secure user-data over each interaction.
Push Notifications: By the support of push notifications, PWAs can interact easily with the users and provide a really amazing user experience.
Bypass the app stores: PWAs don’t need the App store or Google play store support. Their updated version can be directly loaded from the web server without the requirement of app store approval. On the other hand, native apps need days of approval if any new update required. There are possibilities of getting rejected or banned.
Zero installation: During browsing, progressive web app gets its own icon on phones and tablets, just like a mobile application, but without the need to go through the tedious and slow App Store installation process.
23.	Caching and service workers
24.	Background sync
25.	Push notifications
26.	Work box
27.	Tooling webpack/parcel/rollup-config from ground setup
Rollup has node polyfills for import/export, but webpack doesn't. Rollup has support for relative paths in config, but webpack doesn't 
webpack --env entry='./app.js' --env output='bundle.js'
28.	Code splitting
29.	Tree shaking
Tree shaking
Tree shaking is a term commonly used within a JavaScript context to describe the removal of dead code.
In modern JavaScript applications, we use module bundlers (e.g., webpack or Rollup) to automatically remove dead code when bundling multiple JavaScript files into single files. This is important for preparing code that is production ready, for example with clean structures and minimal file size.
30.	Federation
Multiple separate builds should form a single application. These separate builds should not have dependencies between each other, so they can be developed and deployed individually.

This is often known as Micro-Frontends,
31.	Loaders and plugins
32.	Transpliation using babel
Babel enables developers to use cutting-edge Javascript without worrying about browser support. Babel is a JavaScript transpiler, meaning it converts a newer version of ECMAScript, such as ES9, to a standard version (ES5).
33.	Git hooks
Git hooks
Git hooks are scripts that run automatically every time a particular event occurs in a Git repository. They let you customize Git's internal behavior and trigger customizable actions at key points in the development life cycle.
34.	Code bundling/minfication/production ready assets using webpack
35.	Eslint,husky and ather code analysing tools
 
36.	Event Capturing – Also known as trickling, Event Capturing is rarely used. The process starts with the outermost element capturing the event and then propagating it to the innermost element.
For event capturing, we set the handler capture option to true: elem. addEventListener(event, handler, true) . By default, it is set to bubbling: false . 
37.	Event Bubbling – In this process, the event gets handled by the innermost element first and then propagated to the outermost element. event.stopPropagation() method stops the event to travel to the bottom to top.
38.	debounce calls a function when a user hasn't carried out an event in a specific amount of time, while throttle calls a function at intervals of a specified amount of time while the user is carrying out an event


NFR’s
1.	Performance:compression.caching,cdn/expirations.http headers,
2.	JS profiling(CPU/MEM)
JavaScript Profiling shows us which function or processes take most of the time and runtime performance shows how Musicblocks performs when it's running. Firebug provides a highly detailed profiling report. It will tell you how long each method invocation takes in a giant (detailed) table.
console.profile([title])
//also see
console.trace()
You need to call console.profileEnd ()

3.	http2
4.	universal view state
5.	perf analysis
6.	log monitoring tools
7.	basic perf testing: lighthouse,webpage tests,
8.	metrices like TTFB,TTI and their possible ,high no causes
9.	Security:SSL,TLS,CORS,XSS,CSRF,access,refresh token
Content security policy (CSP)
Content Security Policy (CSP) is an added layer of security that helps to detect and mitigate certain types of attacks, including Cross-Site Scripting (XSS) and data injection attacks. These attacks are used for everything from data theft to site defacement to the distribution of malware.

CSRF
CSRF (Cross-Site Request Forgery) is an attack that impersonates a trusted user and sends a website unwanted commands.
This can be done, for example, by including malicious parameters in a URL behind a link that purports to go somewhere else:
<img src="https://www.example.com/index.php?action=delete&id=123">
Copy to Clipboard
For users who have modification permissions on https://www.example.com, the <img> element executes action on https://www.example.com without their noticing, even if the element is not at https://www.example.com.
There are many ways to prevent CSRF, such as implementing RESTful API, adding secure tokens, etc.

10.	Encryptions,validations,encoding,http cookies,sec headers,session,authentication,authorization
11.	protect user data,rbac,abac
12.	A/AA?AAA accessibility,accesssibilty benchmarks,dynamic content accessible with ARIA
13.	WCAG A - Minimum level – without addressing these items, barriers exist that cannot be overcome by assistive technology.  This level affects the broadest group with the most benefits and is essential.
14.	WCAG AA - More accessible – With the minimum level of support, some barriers will still exist which impact certain groups of users.  The criteria at this level establish a level of accessibility which should work with most assistive technology on desktop and mobile devices. Addressing Level AA criteria may impact the look of a page or affect site logic to a greater extent.
15.	WCAG AAA – Even more accessible– Some AAA accessibility criteria cannot be applied everywhere, so level AAA is generally not required. That being said, even meeting level AAA does not make web pages accessible to everyone.

16.	Enahanced technigues viz:skip navigation,no js
17.	Crate accessible forms
18.	Contents and best practces
19.	Gulp/grunt create task
20.	Webpak/parcel/rollup
21.	Loaders and plugins
22.	Docker vagrant and difference
Compared to Vagrant, Docker wins on this criterion because it spends fewer resources, and you can create Docker images faster than Vagrant virtual machines. With Vagrant, it's the opposite situation - creating a virtual machine is laborious and time-consuming, which may slow down the startup time a little.
23.	Integrate plugins like sitespeed
24.	Logging standards
25.	Top-down,bottom-up approaches
26.	WB5/poker

how-to-secure-my-login-page
Firstly, I'd add a csrf token to your form to stop those types of attacks.
//the most simple type of csrf token
if (!isset($_SESSION['token'])):
    $token = md5(uniqid(rand(), TRUE));
    $_SESSION['token'] = $token;
else:
    $token = $_SESSION['token'];
endif;
Then in your form, include a hidden input field:
<input type="hidden" name="token" id="token" value="<?php echo $token; ?>"/>


What are HTTP cookies used for?
Typically, an HTTP cookie is used to tell if two requests come from the same browser—keeping a user logged in, for example. It remembers stateful information for the stateless HTTP protocol.
What are the 3 types of HTTP cookies?


There are three types of computer cookies: session, persistent, and third-party.
override-console-log-for-production
Put this at the top of the file:
var console = {};
console.log = function(){};
For some browsers and minifiers, you may need to apply this onto the window object.
window.console = console;

