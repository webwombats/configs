# Web Wombats config files

![NPM package](https://github.com/webwombats/configs/workflows/Publish%20to%20NPM/badge.svg)

- [Common](./common) - common for each project
- [Frontend](./frontend) - frontend specific
- [Backend](./backend) - backend specific

## Install

```sh
$ yarn add @webwombats/configs --dev
```

## Usage

`tsconfig.json`

```js
{
  "extends": "@webwombats/configs/frontend/tsconfig.json",
  // It's also possible to override the rules
  "compilerOptions": {
    "outDir": "dist",
    "lib": ["es2018"]
  },
  "exclude": ["node_modules", "example-folder"]
}
```

`.prettierrc.js`

Name a configuration file `.prettierrc.js` and import default config from this package.

```js
module.exports = require("@webwombats/configs/common/.prettierrc");
```

`.jest.config.js`

```js
module.exports = require("@webwombats/configs/common/.jest.config");
```

## Package publishing

1. Bump the version in `package.json` and commit the changes. For example `1.0.1` --> `1.0.2`. This package should follow [Semantic Versioning 2.0.0](https://semver.org/).
2. Go to [Release page](https://github.com/webwombats/configs/releases) and create a new release from the master branch. Provide the same tag version you specified in the previous step. Title and description are also important, let your team members know what has been done in this release.
3. Publish release and GitHub Actions do the rest.
