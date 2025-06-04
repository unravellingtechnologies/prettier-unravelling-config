# @unravellingtechnologies/prettier-config

**A Prettier configuration based off Unravelling's JavaScript style guide**

## Installation

```bash
npm install prettier @unravellingtechnologies/prettier-config --save-dev
```

or with pnpm:

```bash
pnpm add prettier @unravellingtechnologies/prettier-config -D
```

or with yarn:

```bash
yarn add prettier @unravellingtechnologies/prettier-config --dev
```

## Usage

### In your package.json

Add the prettier configuration to your `package.json`:

```json
{
  "name": "my-project",
  "version": "1.0.0",
  "prettier": "@unravellingtechnologies/prettier-config"
}
```

### Using .prettierrc.json

If you don't want to use your `package.json`, you can create a `.prettierrc.json` file in your project's root directory:

```json
"@unravellingtechnologies/prettier-config"
```

### Extending the configuration

If you would like to extend or modify these properties, create a `.prettierrc.js` file in your project's root directory and export your desired modifications:

```javascript
module.exports = {
  ...require('@unravellingtechnologies/prettier-config'),
  printWidth: 120,
  // Add your custom overrides here
};
```

## Configuration Details

This configuration includes the following Prettier settings:

### Code Style

#### Single Quotes

> Use single quotes instead of double quotes for strings.

```json
"singleQuote": true
```

**Example:**

```javascript
// ✅ Good
const greeting = "Hello, world!";

// ❌ Bad
const greeting = "Hello, world!";
```

#### Semicolons

> Do not use semicolons at the end of statements.

```json
"semi": false
```

**Example:**

```javascript
// ✅ Good
const name = "John";
const age = 25;

// ❌ Bad
const name = "John";
const age = 25;
```

### Indentation and Spacing

#### Use Tabs

> Use tab characters for indentation instead of spaces.

```json
"useTabs": true,
"tabWidth": 2
```

**Example:**

```javascript
// ✅ Good (using tabs)
function example() {
  return {
    name: "test",
    value: 42,
  };
}
```

#### Bracket Spacing

> Print spaces between brackets in object literals.

```json
"bracketSpacing": true
```

**Example:**

```javascript
// ✅ Good
const obj = { name: "John", age: 30 };

// ❌ Bad
const obj = { name: "John", age: 30 };
```

### Line Length and Wrapping

#### Print Width

> Specify the line length that the printer will wrap on (180 characters).

```json
"printWidth": 180
```

This allows for longer lines before Prettier wraps them, accommodating wider screens and reducing unnecessary line breaks.

### Trailing Commas

> Add trailing commas wherever possible in ES5 (arrays, objects, parameters, etc.).

```json
"trailingComma": "es5"
```

**Example:**

```javascript
// ✅ Good
const array = [
  "first",
  "second",
  "third", // trailing comma
];

const obj = {
  name: "John",
  age: 30,
  city: "New York", // trailing comma
};
```

### Object Properties

#### Quote Props

> Only quote object properties when necessary (when they're invalid identifiers).

```json
"quoteProps": "as-needed"
```

**Example:**

```javascript
// ✅ Good
const obj = {
  name: "John",
  age: 30,
  "invalid-key": "value", // quotes needed due to hyphen
  "2nd-item": "another value", // quotes needed due to number prefix
};

// ❌ Bad
const obj = {
  name: "John",
  age: 30,
  "invalid-key": "value",
};
```

## Editor Integration

### VS Code

Install the [Prettier - Code formatter](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) extension and add the following to your VS Code settings:

```json
{
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.formatOnSave": true
}
```

### WebStorm/IntelliJ

1. Go to **File** → **Settings** → **Languages & Frameworks** → **JavaScript** → **Prettier**
2. Set **Prettier package** to your project's `node_modules/prettier`
3. Check **On save** and **On 'Reformat Code' action**

## Scripts

Add these scripts to your `package.json` for easy formatting:

```json
{
  "scripts": {
    "format": "prettier --write .",
    "format:check": "prettier --check ."
  }
}
```

## License

MIT

## Contributing

Issues and pull requests are welcome on [GitHub](https://github.com/unravellingtechnologies/prettier-unravelling-config).
