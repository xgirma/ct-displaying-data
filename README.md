# Component & Template: Displaying Data

You can display data by binding controls in an HTML template to properties of a component.

```javascript
export class AppComponent {
  title = 'Tour of Heroes';
  heroes = ['Windstorm', 'Bombasto', 'Magneta', 'Tornado'];
  myHero = this.heroes[0];
}
```

The app's code defines the data directly inside the component, which isn't best practice. In a simple demo, however, it's fine.
At the moment, the binding is to an array of strings. In real applications, most bindings are to more specialized objects.
To convert this binding to use specialized objects, turn the array of hero names into an array of Hero objects. For that you'll need a Hero class:

hero.js
```javascript
export class Hero {
  constructor(
    public id: number,
    public name: string) { }
}
```

app.component.ts
```javascript
import { Component } from '@angular/core';

import { Hero } from './hero';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  title = 'Tour of Heroes';
  heroes = [
    new Hero(1, 'Windstorm'),
    new Hero(13, 'Bombasto'),
    new Hero(15, 'Magneta'),
    new Hero(20, 'Tornado')
  ];
  myHero = this.heroes[0];

  constructor() {}

}
```
