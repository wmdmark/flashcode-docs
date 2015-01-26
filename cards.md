
### Challenge card structure

Challenge cards are built with JavaScript and Markdown.

There are four fields that make up a challenge card:

- **Instructions**: GHF Markdown instructions for how to complete the challenge. 
- **Context** (optional): Any extra JavaScript that is needed for the user's solution. 
- **Initial JavaScript (optional)**: A JavaScript template that show's up in the solution editor to help the user get started. 
- **Solution Validation**: Tests that validate the user's solution. Assertions can be written in Chai and/or Sinon.

### Running the solution
When a solution is submitted by the user a code block is built and run:

```js
var solutionJS = [
    card.contextJS,
    userSolutionJS, // the user's submitted solution
    card.validationJS
].join("\n")
```

This code block is run in a sandbox and if any exceptions are thrown from it they are handled and displayed to the user. If no exceptions are thrown, the solution is considered to be correct.


### Examples

Check out the [Demo Deck for Creators](https://ss15-teampw.divshot.io/deck/wJeWGe4cgD/play) for a few examples on how to build different types of challenge cards.


### Known bugs/quirks
- [ ] Using Markdown headings and links in instructions is currently broken :frowning: