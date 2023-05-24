# Game

This is a simple HTML5 game that uses canvas to draw graphics and animations with vanilla JavaScript. The game involves a player who can jump over obstacles by pressing the space key or touching the screen. The game keeps track of the score and the high score and displays them on the screen. The game ends when the player collides with an obstacle or goes off the screen. The game is responsive and supports both keyboard and touch input.

## Code structure

The code consists of three main parts: HTML, CSS and JavaScript.

### HTML

The HTML part defines the basic structure of the web page. It includes a `<canvas>` element where the game graphics are drawn, and a `<script>` element where the JavaScript code is embedded.

### CSS

The CSS part defines some basic styles for the web page. It sets the margin and overflow properties of the body element to zero, to remove any unwanted space and scroll bars around the canvas.

### JavaScript

The JavaScript part contains all the logic and functionality of the game. It uses several variables, constants, functions and classes to implement the game features.

#### Variables and constants

The code defines some variables and constants that are used throughout the game. These include:

- `canvas`: A reference to the `<canvas>` element in the HTML document.
- `context`: A reference to the 2D rendering context of the canvas.
- `width`: The width of the canvas, set to match the inner width of the window.
- `height`: The height of the canvas, set to match the inner height of the window.
- `dark`: A color string for a dark shade of gray, used as the background color of the canvas.
- `light`: A color string for a light shade of gray, used as the text color on the canvas.
- `gravity`: A number that represents the gravity acceleration that affects the player's vertical velocity.
- `jumpForce`: A number that represents the jump velocity that is applied to the player when they jump.
- `obstacleWidth`: A number that represents the width of each obstacle object.
- `speed`: A number that represents the horizontal speed at which each obstacle object moves to the left.
- `spawnTimer`: A variable that holds a reference to a timeout function that creates new obstacle objects at random intervals.
- `score`: A number that represents the current score of the game, which is incremented by one every time an obstacle object is passed by the player.
- `highScore`: A number that represents the highest score achieved by the player in previous games.
- `isJumping`: A boolean that indicates whether or not the player is currently jumping.
- `gameOver`: A boolean that indicates whether or not the game is over.
- `gameStarted`: A boolean that indicates whether or not the game has started.
- `player`: An object that represents the player character in the game. It has properties such as `width`, `height`, `x`, `y`, `vy`, and `color` that define its appearance and position on the canvas.
- `obstacles`: An array that holds all the obstacle objects in the game. Each obstacle object has properties such as `x`, `y`, `width`, `height`, `speed`, `passed`, and `color` that define its appearance and position on the canvas.
- `particles`: An array that holds all the particle objects in the game. Each particle object is an instance of a class called Particle, which has properties such as `x`, `y`, `vx`, `vy`, and `alpha` that define its appearance and position on
the canvas.

#### Classes

The code defines one class called Particle, which is used to create particle objects for visual effects. The class has a constructor method that takes two parameters: x and y, which are
the initial coordinates of each particle object. The constructor also assigns random values to
the horizontal and vertical velocities (vx and vy) and sets an initial alpha value (opacity) of 1
to each particle object. The class also has two methods: update and draw. The update method
updates the position and alpha value of each particle object based on its velocity. The draw
method draws each particle object on the canvas using its position, alpha value and color.

#### Functions

The code defines several functions that perform different tasks in
the game. These include:

- createObstacle: This function creates two new obstacle objects (one for
the upper part and one for lower part) with random dimensions and gaps between them,
and pushes them to obstacles array. It also sets a timeout function to call itself again after
a random interval between 700 and 1400 milliseconds, using spawnTimer variable to store
the reference to it.
- spawnParticles: This function creates 10 new particle objects with their initial positions set
to be near bottom edge of player object, and pushes them to particles array.
- jump: This function is an event handler that is triggered when space key is pressed or screen
is touched. It checks if gameOver flag is false, then sets player's vertical velocity (vy) to jumpForce value. It also sets isJumping flag to true if event type is keydown or false if event type
is keyup.
- startGame: This function is an event handler that is triggered when space key is pressed or screen is touched before game starts. It checks if gameStarted flag is false, then calls createObstacle function to start spawning obstacles, sets gameStarted flag to true,
and removes itself from keydown and touchstart events. It also calls requestAnimationFrame function with loop function as argument to start updating and drawing game frames.
- isCollide: This function takes two parameters: a and b, which are two objects with x, y,
width and height properties. It returns true if these two objects are overlapping or false otherwise. It uses a margin value of 3 pixels to make collision detection more forgiving.
- update: This function updates all logic in game frame by frame. It updates player's position based on its vertical velocity (vy), adds gravity value to vy, checks if player goes off screen boundaries and sets gameOver flag accordingly. It also increments score by one every time an obstacle object passes player without colliding with it, checks collision between player
and obstacle objects using isCollide function, updates position of obstacle objects based on their speed values, removes obstacle objects from obstacles array if they go off left edge of canvas,
updates position and alpha value of particle objects based on their velocity values,
removes particle objects from particles array if their alpha value reaches zero,
and calls draw function at end.
- draw: This function draws all graphics in game frame by frame. It draws background color,
player object, obstacle objects, particle objects, score text, high score text,
and game over text using context methods such as fillRect, fillText,
fillStyle etc.
- loop: This function calls update function repeatedly using requestAnimationFrame function until gameOver flag becomes true. Then it calls reset function to reset all variables
and restart game.
- reset: This function resets all variables to their initial values such as clearing spawnTimer,
obstacles array, particles array etc., setting gameOver flag to false,
setting player's position and velocity to default values etc. It also displays high score text
and start instruction text on canvas using drawText function,
and adds startGame function back to keydown and touchstart events.

## How to run

To run this game, simply open index.html file in any modern web browser that supports HTML5 canvas element and JavaScript features such as classes,
arrow functions etc. Alternatively, you can host this file on any web server
and access it via URL.

## How to play

To play this game, press space key or touch screen to make player jump over obstacles. Avoid colliding with obstacles or going off screen boundaries. Try to score as high as possible by passing more obstacles without hitting them.

## Credits

This code was generated by Bing chat mode using OpenAI Codex engine.

