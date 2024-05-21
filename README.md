# 🐍 Snek.js [![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT) [![snekjs on NPM](https://img.shields.io/npm/v/snekjs.svg?color=green&label=snekjs)](https://www.npmjs.com/package/snekjs)

A terminal-based Snake implementation written in JavaScript (Node.js).

![snek.gif](https://raw.githubusercontent.com/taniarascia/snek/master/snek.gif)

## Instructions

To play the game, one needs to implement a game client. An example solution code for the client can be [found here](https://github.com/lighthouse-labs/snek-client) (it's a private repository, not accessible to everyone).

## Installation

### Clone from repository

```bash
git clone git@github.com:rlitoncs/snake-server.git
cd snake-server

# install and run via npm
npm install
npm run play
```

## Acknowledgements

This project was not built from scratch. It was inspired and started from [snek](https://github.com/taniarascia/snek) ([blog post](https://www.taniarascia.com/snake-game-in-javascript/)). [Tania Rascia](https://www.taniarascia.com) is the original author.
This project was also cloned from [lighthouse-labs](https://github.com/lighthouse-labs/snek-multiplayer).

## License

This project is open source and available under the [MIT License](LICENSE).


## Stretch
Added the feature of broadcasting message to all clients when new player joins, and number of connected players!

```javascript
handleNewClient(client) {
// ...
   ...
    client.on('data', (data) => {
      if (data.includes('Name')){
        this.clients.forEach(user => { user.write(`New Player '${data.split(' ').slice(1)}' Has Joined`)})
      }
    })

    this.clients.forEach(user => user.write(`Number of Players Connected: ${this.clients.length}`))
}
```
