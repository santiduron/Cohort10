# How to use Gulp in your projects

## High Level Steps
- Install `gulp` globally
- Create a `package.json` in your web folder using `npm init`
- Create a `bower.json` in your web folder using `bower init`
- Add your `gulpfile.js` to your web folder
- Override `bootstrap` and `font-awesome` main definitions
- Add hooks in index.html

## Install `gulp` globally
Before we can use `gulp`, we need to make sure it can be executed on the command line. To ensure this, open up your terminal/command prompt and type:

`npm install gulp -g`

This will put `gulp` in your PATH so it can be run from the command line.

## Create a `package.json` file in your web folder
1. Navigate to your web folder in the terminal
2. Run `npm init` and keep pressing enter to choose the default options.
3. This creates a `package.json` file in your project.

## Create a `bower.json` file in your web folder

1. Similar to `npm init`, navigate to your web folder in the terminal
2. Run `bower init` - **when it asks if you'd like to include installed dependencies, choose yes.**
3. This creates a `bower.json` file in your project.

## Install the folowing gulp extensions
### Install gulp
(Yes, I know you think you already did this - but this time we're installing gulp into the project, not globally.)

`npm install gulp --save`

### Install gulp-inject
`npm install gulp-inject --save`

### Install wiredep
`npm install wiredep --save`

### Install browser-sync
`npm install browser-sync --save`

## Add this `gulpfile.js` to your web folder
```js
const gulp = require('gulp');
```

## Override `bootstrap` and `font-awesome` main definitions
In your `bower.json` file, add the following object between the `ignore` array and the `dependencies` object.

```json
  "overrides": {
```

## Add hooks to index.html
In your `index.html` file, add the following "hooks", similar to the example file.

```html
<html>

	<head>
		<!-- bower:css -->
		<!-- endbower -->
	
		<!-- inject:css -->
		<!-- endinject -->
	</head>

	<body>
		<!-- bower:js -->
		<!-- endbower -->
		
		<!-- inject:js -->
		<!-- endinject -->
	</body>

</html>
```

## Run gulp tasks!
Now, simply run `gulp serve` in the command line to run your gulp file. This will:

- Inject all your bower dependencies as `<script>` or `<link>` elements
- Inject all your custom CSS files as `<link>` elements
- Inject all your custom JS files as `<script>` elements
- Start a web server on port `3000`
- Reload the page automatically when changes to files are detected. (**Awesome!!**)