# ios-screen-mirroring
Instructions for mirroring iOS device on web browser

## Instructions to install ios-minicap

### 1. Connect an iOS device

### 2. Install prerequisites

In terminal, type the following commands. Omit the $ sign when typing the commands. 

```
$ brew install libjpeg-turbo

$ brew install cmake
```

### 3. Install ios-minicap

In terminal, navigate to desired folder, type the following command.

```
$ git clone https://github.com/openstf/ios-minicap
```

Alternatively, download the folder from <https://github.com/openstf/ios-minicap>.

### 4. Additional fixes

You might be prompted to install additional modules, with some of the following commands

```
$ cd /User/yourname/ios-minicap/example

$ npm install express

$ npm install ws

$ npm install websocket
```

In /User/yourname/ios-minicap/example, locate app.js. Open the file in a text editor, after line 64, add in:

```
stream.destroy();
```

The resulting lines should look like:

```
ws.on('close', () => {
    console.info('Lost a client')
    stream.end()
    stream.destroy();
  })
```

### 5. Run minicap

```
$ cd /User/yourname/ios-minicap

$ ./build.sh

$ ./run.sh
```

Keep the terminal open, in a new terminal window, carry out Step 5. 

### 6. Run demo

In a new terminal window, type the following commands. 

```
$ cd /User/yourname/ios-minicap/example

$ npm install

$ node app.js
```

### 7. Open demo in browser

Open <http://localhost:9002> in browser to see mirrored screen of iOS device. 
