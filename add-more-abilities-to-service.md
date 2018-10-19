# \#15: 🎁 Add more abilities to service

In this chapter, we'll improve our service by adding more abilities.

First, lets open our app's service file, which is available at ![](.gitbook/assets/service.svg) **todo-list.service.ts**.

There we'll add a new method to the service, called `addItem`, like so:

{% code-tabs %}
{% code-tabs-item title="todo-list.service.ts" %}
```typescript
addItem(item): void {
  this.todoList.push(item);
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

This will allow us to call the same method from everywhere across the application, thus making our app easier to maintain.

And now we can change our code in ![](.gitbook/assets/component.svg) **list-manager.component.ts** to call the `addItem` method directly from the service like so:

{% code-tabs %}
{% code-tabs-item title="list-manager.component.ts" %}
```typescript
addItem(title): void {
  this.todoListService.addItem({ title });
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

* There may be additional logic when calling these methods, i.e. saving the changes in a database \(which we'll implement later\).
* A better way to handle data is using _immutable objects_, but that's a bigger topic than we can cover in this tutorial at the moment.

