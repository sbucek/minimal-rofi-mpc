# rofi-mpc
Stripped down version of Marco98/rofi-mpc package to list and play playlist entries from multiple MPD sources.
Fast graphical Rofi-Interface for quick switching between audio sources. Removed unneeded functionality to jump straight to the playlist selection.
## Features
#### Current list of features:
* List and Play playlist entries
* Source Selection:
  * Playlist generation for the **~/Music** directory
  * List and Load playlists from mpd's **playlist_directory**
#### Planned features:
* Implement "Play/Pause" toggling functionality directly in the playlist
* Enable toggling rofi on/off using same keyboard shourctus 
## Installation
#### Requirements
* **python**
* **mpd**
* **rofi**
#### Recommended Configuration of mpd
Recommended config path:
```
mkdir -p ~/.config/mpd/playlists
```
Recommended **~/.config/mpd/mpd.conf**:
```
db_file				"~/.config/mpd/database"
log_file			"~/.config/mpd/log"
restore_paused			"yes"
music_directory			"~/Music"
playlist_directory		"~/.config/mpd/playlists"
pid_file			"~/.config/mpd/pid"
state_file			"~/.config/mpd/state"
sticker_file			"~/.config/mpd/sticker.sql"
```
Start mpd on boot or at xinit like this:
```
mpd ~/.config/mpd/mpd.conf
```
#### Deployment
```
sudo wget -O /usr/local/bin/rofi-mpc  https://raw.githubusercontent.com/sbucek/rofi-mpc/master/rofi-mpc
sudo chmod +x /usr/local/bin/rofi-mpc
```
Then you just need to set a keybind for rofi-mpc
For example, if you're using i3wm you just need to add this line in you config:
```
bindsym $mod+a exec rofi-mpc
```
#### Adding Streams
If you're using my recommended **mpd.conf** you just need to add it into the playlists-directory like this:
```
echo "http://example.com/stream.mp3" > ~/.config/mpd/playlists/[STREAM-NAME].m3u
```
