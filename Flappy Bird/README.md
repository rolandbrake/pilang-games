# Flappy Bird

A PiLang implementation of the familiar one-button arcade game. Guide the bird through an endless series of pipes and try to set a new high score.

<p align="center" >
    <img src="./screenshot.png" width = 200>
</p>


## Play

On Windows, open `Flappy Bird.exe`.

Alternatively, run the source from this folder with the PiLang runtime located in the parent directory:

```powershell
..\pilang.exe run .\main.pi
```

Run the command while your current directory is `Flappy Bird`; the game loads its sprite and sound files using relative paths.

## Controls

- Start, flap, or restart after a game over: left-click, `Space`, or `Up Arrow`

Each flap sends the bird upward. Avoid the pipes and ground; passing a pipe earns one point.

## Build

To rebuild the Windows executable from the project manifest:

```powershell
..\pilang.exe pack target:win
```

This updates `main.px` and replaces `Flappy Bird.exe`. To compile only the PiLang project file, use:

```powershell
..\pilang.exe build .\main.pi
```

## Web build

Create a static website with the browser runtime, sprites, and sounds:

```powershell
..\..\pilang\bin\pilang.exe pack target:web
```

Upload the generated `dist/` folder to any static host, or preview it locally from this folder:

```powershell
python -m http.server 8000 --directory dist
```

Then open `http://localhost:8000`. Do not open `index.html` with `file://`; browsers must fetch the WebAssembly runtime and assets over HTTP.

## Project layout

| Path | Purpose |
| --- | --- |
| `main.pi` | Game source code |
| `sprites/` | Backgrounds, bird frames, pipes, score digits, and interface art |
| `audio/` | Flap, score, collision, and game-over sounds |
| `package.loon` | Windows and web packaging configuration |

## License

The included game assets are provided under the [MIT License](LICENSE).
