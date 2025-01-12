# nodejs-beginner

Node.js is a powerful, open-source, cross-platform runtime environment that allows you to execute JavaScript code outside the browser. It’s widely used for server-side applications and is the foundation for many modern web applications.

----

## 1. What is Node.js?
- **Built on V8 Engine:** Node.js uses Google’s V8 JavaScript engine, which compiles JavaScript into native machine code.
- **Non-blocking I/O:** It uses an event-driven, non-blocking architecture, making it suitable for scalable applications.
- **Server-Side JavaScript:** You can use JavaScript to create back-end/server-side functionality.

## Why Use Node.js?
- Real-time applications (e.g., chat apps, live dashboards).
- Fast and scalable.
- Uses JavaScript end-to-end (frontend + backend).

----

## 2. Setting Up Node.js
### Step 1: Install Node.js
- Visit Node.js Official Website.
- Download the LTS (Long-Term Support) version.
- Install it by following the instructions for your operating system.
### Step 2: Verify Installation
After installation, open your terminal or command prompt and run:

```
node -v
```

This will display the installed version of Node.js. To check npm (Node Package Manager), run:
```
npm -v
```
----

## 3. Your First Node.js Program

Let’s create a simple "Hello, World!" program.

### Step 1: Create a File
Create a file named app.js.

### Step 2: Write the Code
Add the following code to ```app.js```:
```
console.log("Hello, World!");
```
### Step 3: Run the Program
Run the file in your terminal:
```
node app.js
```

You should see Hello, World! printed in your terminal.

----
## 4. Understanding Node.js Modules
Node.js has a built-in module system that allows you to organize your code.

### Types of Modules:
- **Core Modules:** Built into Node.js (e.g., fs, http).
- **Custom Modules:** Your own modules.
- **Third-Party Modules:** Installed using npm.

### Example: Using a Core Module (os)
```
const os = require("os");

console.log("Platform:", os.platform());
console.log("Architecture:", os.arch());
console.log("Free Memory:", os.freemem());
console.log("Total Memory:", os.totalmem());
```
----

## 5. Working with the File System
Node.js has a fs (File System) module for working with files.

### Example 1: Reading a File
Create a file named example.txt with some text content, then use the following code:

```
const fs = require("fs");

fs.readFile("example.txt", "utf8", (err, data) => {
  if (err) {
    console.error(err);
    return;
  }
  console.log("File Content:", data);
});
```

### Example 2: Writing to a File
```
const fs = require("fs");

fs.writeFile("output.txt", "This is some output text.", (err) => {
  if (err) {
    console.error(err);
    return;
  }
  console.log("File written successfully!");
});
```

----

## 6. Creating a Basic HTTP Server
Node.js can be used to create servers without the need for additional software.

### Step 1: Create an HTTP Server
```
const http = require("http");

const server = http.createServer((req, res) => {
  res.writeHead(200, { "Content-Type": "text/plain" });
  res.end("Hello, this is your Node.js server!");
});

server.listen(3000, () => {
  console.log("Server is running at http://localhost:3000");
});
```

### Step 2: Run the Server
Run the file:
```
node app.js
```
Open your browser and go to http://localhost:3000. You should see the message from the server.


----
## 7. Using npm (Node Package Manager)
### What is npm?
npm is the default package manager for Node.js. It allows you to install and manage third-party libraries and tools.

### Step 1: Initialize a Project
Run the following command to create a package.json file:

```
npm init -y
```

### Step 2: Install a Package
For example, install the axios library for making HTTP requests:
```
npm install axios
```
### Step 3: Use the Package
```
const axios = require("axios");

axios.get("https://api.github.com/users/github")
  .then(response => {
    console.log(response.data);
  })
  .catch(error => {
    console.error(error);
  });
```
----

## 8. Async Programming with Node.js
Node.js uses asynchronous programming by default. Here's an example of using Promises with fs.promises:
```
const fs = require("fs").promises;

async function readFile() {
  try {
    const data = await fs.readFile("example.txt", "utf8");
    console.log("File Content:", data);
  } catch (err) {
    console.error(err);
  }
}

readFile();
```
----

## 9. Debugging in Node.js
Run your app in debug mode:
```
node inspect app.js
```
Alternatively, use modern tools like VS Code Debugger for an easier debugging experience.

----

