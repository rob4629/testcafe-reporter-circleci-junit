# testcafe-reporter-circleci-junit
[![Build Status](https://github.com/rob4629/testcafe-reporter-circleci-junit.svg)](https://github.com/rob4629/testcafe-reporter-circleci-junit)

> This is the fork of the [**junit**](https://travis-ci.org/alexschwantes/testcafe-reporter-junit) reporter plugin for [TestCafe](http://devexpress.github.io/testcafe).

This reporter plugin for TestCafe outputs a junit xml report that is compatible with continuous integration servers, specifically CircleCi. The two main differences between this plugin and the default xunit plugin is that in this plugin;
1. the testcase name attribute will only contain the testcase name and any additional information such as screenshots and (unstable) flags are output to `<system-out/>` tag. This allows for better reporting and analysis or repeated test runs.
2. The Fixture file path will be reported, in order for CircleCi to split regression tests by run times.

<p align="center">
    <img src="https://raw.github.com/rob4629/testcafe-reporter-circleci-junit/master/media/preview.png" alt="preview" />
</p>

## Install

To install this reporter, you can use the following command:

```
npm install testcafe-reporter-circleci-junit
```

## Usage

When you run tests from the command line, specify the reporter name by using the `--reporter` option:

```
testcafe chrome 'path/to/test/file.js' --reporter junit-circleci
```


When you use API, pass the reporter name to the `reporter()` method:

```js
testCafe
    .createRunner()
    .src('path/to/test/file.js')
    .browsers('chrome')
    .reporter('junit-circleci') // <-
    .run();
```
