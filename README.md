# Quickstart Webpack

A scaffold project for a [Webpack](https://webpack.js.org/) webapplication, without the overhead of specific libraries. It can be used to quickstart a prototype project for any kind of module-based webapplication. It has some preconfigured standards for development and production. The only predefined technology in the stack is a [SASS](https://sass-lang.com/) preprocessor, for importing `.scss` stylesheets.

## Installation

First ```git clone``` this project.

Second, step into the new folder and remove the git remote:

```bash
git remote remove origin
```

After that install all the default dependecies:

```bash
npm install
```

Now the project is ready to use. You can start the dev server with ```npm run start``` or create a deployable release version of it with ```npm run build```.

## Where to start?

The `index.html` can be found in the `dist` folder. It's preconfigured to load the via Webpack generated module bundle.
If you have static resources, wich shouldn't be loaded by Webpack, put it in here. When running a build, Webpack generates the resource bundle into this folder. The content of this folder is production ready and can deployed / copied to any kind of webserver (i.e. [Apache](https://httpd.apache.org/)). It will be a standard ECMAScript 5 webapplication. Node.js and npm are not needed in production.

The main entry point of your web application is the `index.js`, you can find in the `src` folder. Start your implementation here. Use the ECMAScript 6 module-system, by using [import](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import) and [export](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export).

All scripts and resources, that should be handled by Webpack, should be placed in the `src` folder (except for the libraries you installed via npm). In the default configuration of this project Webpack can import .js and .jsx files (add React), .css and .scss files, JPG's, PNG's, SVG's and various Webfont files.

## How to add React?

If you want to have a [React](https://reactjs.org/) application you just have to excecute ```npm install react react-dom```, to add the frontend libraries. Then run ```npm install --save-dev babel-preset-react``` to add the backend library to parse JSX files.

Then just add the value `react` to the presets in your `.babelrc` file :

```javascript
{
    "presets": ["env", "react"]
}
```

Your now ready to use [React and JSX](https://reactjs.org/docs/hello-world.html)!

## Something else?

If you publish a project, based on this scaffold, don't forget to:

- rename the project in the `package.json`
- change the description in the `package.json`
- change the author in the `package.json`
- adapt the license in the `package.json` if you need
- rewrite this `README.md` file
- maybe use `git rebase` to [squash the history](https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History) of this project into one commit, so your project's history isn't bloated with stuff related to this scaffold :)

# Reference

```bash
npm run start
```

- starts the application in a development server
- URL is shown on console
- refresh on every code change

```bash
npm run build
```

- creates the source bundle in the `dist` folder
- content in `dist` folder is production ready

```bash
npm run clean
```

- cleans up the workspace by deleting generated sources
