# karma-jasmine-html-reporter-sourcemaps
forked from [taras42/karma-jasmine-html-reporter](https://github.com/taras42/karma-jasmine-html-reporter)

### This is currently a work in progress.

> Reporter that dynamically shows tests results at debug.html page.
> Jasmine 1.3 is not supported.

![alt tag](https://raw.github.com/taras42/karma-jasmine-html-reporter/master/screenshots/reporter_1.png)

You can also run describe block, or single test.

![alt tag](https://raw.github.com/taras42/karma-jasmine-html-reporter/master/screenshots/reporter_2.png)

## Installation

The easiest way is to keep `karma-jasmine-html-reporter-sourcemaps` as a devDependency in your `package.json`.
```json
{
  "devDependencies": {
    "karma": "~0.10",
    "karma-jasmine-html-reporter-sourcemaps": "~0.1"
  }
}
```

You can simple do it by:
```bash
npm install karma-jasmine-html-reporter-sourcemaps --save-dev
```

## Configuration
see [example](https://github.com/kshanafelt/karma-jasmine-html-reporter-sourcemaps-example/tree/release/inline-sourcemap)

```js
// karma.conf.js
module.exports = function(config) {
  config.set({
    frameworks: ['jasmine'],
    preprocessors: {
            // add webpack as preprocessor
            'test/*_test.js': ['webpack', 'sourcemap'],
            'test/**/*_test.js': ['webpack', 'sourcemap']
     },
    reporters: ['karma-jasmine-html-sourcemaps']

  });
};
```
Currently only inline-source-maps are supported.

```js
// webpack.config.js
module.exports = { 
    devtool: 'inline-source-map' 
};

You can pass list of reporters as a CLI argument too:
```bash
karma start --reporters kjhtml
```
