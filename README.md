What Are We Building?

In this tutorial, we’ll show how to build an interactive tic-tac-toe game with React.

You can see what we’ll be building here: Final Result. If the code doesn’t make sense to you, or if you are unfamiliar with the code’s syntax, don’t worry! The goal of this tutorial is to help you understand React and its syntax.

We recommend that you check out the tic-tac-toe game before continuing with the tutorial. One of the features that you’ll notice is that there is a numbered list to the right of the game’s board. This list gives you a history of all of the moves that have occurred in the game, and it is updated as the game progresses.

You can close the tic-tac-toe game once you’re familiar with it. We’ll be starting from a simpler template in this tutorial. Our next step is to set you up so that you can start building the game.

```
npx create-react-app my-app
```

Delete all files in the src/ folder of the new project

Add a file named index.css in the src/ folder with this CSS code.

Add a file named index.js in the src/ folder with this JS code.

Add these three lines to the top of index.js in the src/ folder:

By inspecting the code, you’ll notice that we have three React components:

    Square
    Board
    Game

The Square component renders a single `<button>` and the Board renders 9 squares. The Game component renders a board with placeholder values which we’ll modify later. There are currently no interactive components.

Congratulations! You’ve just “passed a prop” from a parent Board component to a child Square component. Passing props is how information flows in React apps, from parents to children.

Making an Interactive Component

Let’s fill the Square component with an “X” when we click it.

React components can have state by setting this.state in their constructors. this.state should be considered as private to a React component that it’s defined in. Let’s store the current value of the Square in this.state, and change it when the Square is clicked.

    Note

    In JavaScript classes, you need to always call super when defining the constructor of a subclass. All React component classes that have a constructor should start with a super(props) call.

Now we’ll change the Square’s render method to display the current state’s value when clicked:

    Replace this.props.value with this.state.value inside the <button> tag.
    Replace the onClick={...} event handler with onClick={() => this.setState({value: 'X'})}.
    Put the className and onClick props on separate lines for better readability.

By calling this.setState from an onClick handler in the Square’s render method, we tell React to re-render that Square whenever its `<button>` is clicked. After the update, the Square’s this.state.value will be 'X', so we’ll see the X on the game board. If you click on any Square, an X should show up.

When you call setState in a component, React automatically updates the child components inside of it too.
