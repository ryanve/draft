# css

## Vision
Our long-term vision is to provide CSS classes as a design system for feature development. We want to empower our teams with powerful approachable CSS classes that prevent the need for write CSS over and over again.

## Repos

- [<b>`structure`</b>](https://github.com/plangrid/structure) is our CSS framework and HTML guide
- [<b>`paint`</b>](https://github.com/plangrid/paint) is our color library used in CSS and JavaScript
- [<b>`controls`</b>](https://github.com/plangrid/controls) has in-development React components using structure and paint
- [<b>`iconography`</b>](https://github.com/plangrid/iconography) svg warehouse plus transitional sprites

## Approach

### Approachable :white_check_mark:

Favor approachable naming to help facilitate cross-functional adoption.

### Functional :white_check_mark:

Functional CSS favors resuable content-agnostic simple-purpose classes. They facilitate rapid building without having to continually author more CSS. Component styling is readable for CSS developers and debuggable in the browser. `<Example className="flex flex-wrap">`. Data attributes are applicable for functional CSS too because they have equal specificity to classes.

### Composable :white_check_mark:
Favoring composition helps maximize reusability. In CSS an ideal way to do this is to group classes by property. Only set the properties needed such that classes defined for some properties compose well with ones for other property without depending on cascade order.

### Immutable :white_check_mark:
In order for classes to be predictable they need to be immutable. This means that classes are defined and then never overriden or extended. Immutable classes facilite debugging and consistency because they behave consistently regardless of context.

### Flat :white_check_mark:

Flat CSS means favoring flat (unnested) selectors wherever possible. Flatness facilites composition because it reduces specificity conflicts and helps rules behave consistently regardless of context. Flatter selectors are also more performant.

### Specificity :warning:
Keep equal specifity per module for maximum composability. Keep selectors simple and predictable.

- `.example` :white_check_mark:
- `[data-example]` :white_check_mark:
- `tag` :no_entry: because it affects any tag
- `tag.example` :no_entry: because `.example` is more reusable on its own
- `:pseudo` :no_entry:
- `.control:pseudo` :white_check_mark: when all rules for `.control` match this specificty

### Nesting :no_entry:
Nested CSS selectors are notorious for causing bugs related to specifity or context. Avoid nesting for these reasons and because they are time consuming to refactor&mdash;especially when their target is hard to find for.

```
.bad .example {}
.worse example {}
.good-example {}
```

### Techniques
#### Favor modern responsive techniques

- [Favor flexbox](https://github.com/plangrid/layout)
- Favor relative units

### Units

- Favor relative units because these improve the responsive experience
- [Favor `em` for dimension media queries](https://zellwk.com/blog/media-query-units/)
- Use `px` when necessary to support legacy code

| Property | Preferred unit |
|:---------|:----------------|
| `margin` | `rem` |
| `padding` | `rem` |
| `border` | `px` |
| `font-size` | `rem` |
