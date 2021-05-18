# Setup React Project

## Pre-requirements

- **NodeJS** and **npm**

## Setup

Open command line (ctrl+j)

Setup package.json, enter:

```bash
npm init -y
```

Install React and React-DOM (other packages are required for other platforms, e.g. Android and iOS)

_Note: If it installation fails to missing permissions, open VS Code as administrator and try again_

```bash
npm install react react-dom
```

- Install Webpack to allow dependencies like the React library to the end user

```bash
npm install webpack webpack-cli webpack-dev-server
```

- Create a new file named _webpack.config.js_, this file is expected by Webpack
- Copy contents from _template-webpack.config.js_ or look up how to fill it out manually

Finally we need to install Babel Loader and some Babel packages

```bash
npm install @babel/core
npm install @babel/preset-env
npm install @babel/preset-react
npm install babel-loader
```

- Add Webpack serve to scripts in package.json, it should look like following

```bash
"scripts": {
"dev": "webpack serve",
"test": "echo \"Error: no test specified\" && exit 1"
}
```

## Project Structure

Crate a new folder "App"

In "App", create

- index.html
- Main.js

### index.html

Create basic structure by typing _doc_ and then press tab

Add following in the main body:

```bash

<!-- Create an empty div 'app' which React can hook into -->
<div id="app"></div>
<script src="/bundled.js"></script>

```

### Main.js

```bash
import React from "react"
import ReactDOM from "react-dom"

// Example dummy component
function ExampleComponent() {
  return (
    <div>
      <h1>This is our app!</h1>
      <p>The sky is blue</p>
    </div>
  )
}

ReactDOM.render(<ExampleComponent />, document.querySelector("#app"))

// Allow automatic insert new changes without refreshing browser
if (module.hot) {
  module.hot.accept()
}
```

## Run Application

To start the application task, run the _dev_ script we added to _package.json_:

```bash
npm run dev
```

Browse to localhost:3000 and verify that it is working!

### ./App

All code goes here

##
