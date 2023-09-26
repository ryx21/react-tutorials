# README

Basic JavaScript: https://www.freecodecamp.org/news/top-javascript-concepts-to-know-before-learning-react/

React Tutorial: https://react.dev/learn/tutorial-tic-tac-toe

## Setup
* Installed `nvm` and used this to install `node` following the `nvm` repo instructions: [here](https://github.com/nvm-sh/nvm)
* When running `npm start` I ran into the error below - this was fixed by running `npm install react-scripts@latest` (see [here](https://kinsta.com/knowledgebase/react-must-be-in-scope-when-using-jsx/))

```
Failed to compile.

./src/App.js
  Line 2:  'React' must be in scope when using JSX  react/react-in-jsx-scope
```

## Notes

* You can view the Console with the keyboard shortcut Shift + Ctrl + J (on Windows/Linux) or Option + ⌘ + J (on macOS).
* React provides a special function called `useState` that you can call from your component to let it “remember” things. It returns a `value`, a `set` function, and takes an a argument defining the default `value`
* When you call a `set` function in a component, React re-renders the component and any child components inside too.
* **Lifting State**: to collect data from multiple children, or to have two child components communicate with each other, declare the shared state in their parent component instead. The parent component can pass that state back down to the children via props. This keeps the child components in sync with each other and with their parent.
    * Lifting state into a parent component is common when React components are refactored.
* Use *arrow functions* pass functions down as props rather than call them e.g. `onSquareClick=() => handleClick(0)` over `onSquareClick=handleClick(0)`
    * The latter will call the function right away which will make React rerender the comonent in an infinite loop
* In React, it’s conventional to use `onSomething` names for props which represent events and `handleSomething` for the function definitions which handle those events.
    * Example: `onSquareClick` is a prop that represents and event (passes a value to `onClick`), and `handleClick` does something with that event (defines what happens when the `onClick` event occures)
* JavaScript supports closures which means an inner function (e.g. `handleClick`) has access to variables and functions defined in a outer function (e.g. `Board`)
* Immutability makes complex features much easier to implement. Avoiding direct data mutation lets you keep previous versions of the data intact, and reuse them later.
    * Immutability makes it very cheap for components to compare whether their data has changed or not. 
    * Read more in the [memo API reference](https://react.dev/reference/react/memo).
* Keys tell React about the identity of each component, which allows React to maintain state between re-renders. If a component’s key changes, the component will be destroyed and re-created with a new state.
    * It’s strongly recommended that you assign proper keys whenever you build dynamic lists. If you don’t have an appropriate key, you may want to consider restructuring your data so that you do.

## Extention Exercises

* [x] For the current move only, show “You are at move #…” instead of a button.
* [ ] Rewrite Board to use two loops to make the squares instead of hardcoding them.
* [ ] Add a toggle button that lets you sort the moves in either ascending or descending order.
* [ ] When someone wins, highlight the three squares that caused the win (and when no one wins, display a message about the result being a draw).
* [ ] Display the location for each move in the format (row, col) in the move history list.