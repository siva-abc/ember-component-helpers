# Ember-component-helpers

Some handlebar helpers for working with Ember components

## Available Helpers
* [`component-apply`](#component-apply)
* [`componentize`](#componentize)

## Usage Examples

#### `component-apply`
Ember's regular `component` is to `Function#call` as `component-apply` is to `Function#apply`

Consider the following example of calling Ember's `link-to` component:
```handlebars
{{#component "link-to" "dashboard.post.index" post}}
  {{post.content}}
{{/component}}
```
Now with `component-apply` (and the `append` helper from [ember-composable-helpers](https://www.npmjs.com/package/ember-composable-helpers))
```handlebars
{{#component-apply "link-to" (append "dashboard.post.index" post)}}
  {{post.content}}
{{/component-apply}}
```

#### `componentize`
Wraps a vanilla HTML tag into an element, useful for components which demand a parentView such as tooltips from [ember-tooltips](https://www.npmjs.com/package/ember-tooltips)

```handlebars
{{#componentize "li" class="mdl-list__item"}}
  {{#tooltip-on-parent}}
    You don't have to use data-tooltip-content + separate js call anymore!
  {{/tooltip-on-parent}}
  Brian Cranston
{{/componentize}}
```

## Installation

* `git clone` this repository
* `npm install`
* `bower install`

## Running

* `ember server`
* Visit your app at http://localhost:4200.

## Running Tests

* `npm test` (Runs `ember try:testall` to test your addon against multiple Ember versions)
* `ember test`
* `ember test --server`

## Building

* `ember build`

For more information on using ember-cli, visit [http://ember-cli.com/](http://ember-cli.com/).