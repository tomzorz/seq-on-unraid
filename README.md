# seq-on-unraid
How to get Seq up and running on UnRaid, illustrated.

## Base requirements

1. Have UnRaid installed
2. Have the Community Apps plugin installed and enabled

## Installation guide

# Enable DockerHub search results

1. Go to the [Apps] tab

![Apps](https://github.com/tomzorz/seq-on-unraid/blob/master/1.png)

2. On the left side, find the [Settings] option

![Apps](https://github.com/tomzorz/seq-on-unraid/blob/master/2.png)

3. Toggle the "Enable additional search results from docerHub" to "Yes", then press [Apply]

![Apps](https://github.com/tomzorz/seq-on-unraid/blob/master/3.png)

4. Back in the [Apps] tab, search for `seq`. You won't find anything, but you'll see a link "Click Here To Get More Results From DockerHub" - click that.

![Apps](https://github.com/tomzorz/seq-on-unraid/blob/master/4.png)

5. The first result you see should be `seq` by `datalust`, click the [Download] icon to start installation.

![Apps](https://github.com/tomzorz/seq-on-unraid/blob/master/5.png)

6. Set up the screen to match the settings below - obviously adjusting for your local environment.

![Apps](https://github.com/tomzorz/seq-on-unraid/blob/master/6.png)

Name: `seq` (or whatever you want)

Repository: leave as-is

Network type: usually it's a safe bet to pick that previously worked with other containers, e.g. `Bridge` or `Host`

Console shell command: leave as-is

Privileged: leave as-is

After these, you'll need to go into the "Add another Path, Port, Variable, Label or Device" option 4 times.

1. Create a "Container Variable" called e.g. "eula" with the "Key" `ACCEPT_EULA` and "Value" `Y`
2. Create a "Container Path" called e.g. "data" with the "Container Path" `/data`, "Host Path" somewhere inside your `appdata` e.g. `/mnt/user/appdata/Seq/` and "Access Mode" "Read/Write"
3. Create a "Container Port" called e.g. "interface" with the "Container Port" `80`, "Host Port" something free for you e.g. `12301` and "Connection Type" "TCP"
4. Create a "Container Port" called e.g. "intake" with the "Container Port" `5341`, "Host Port" something free for you e.g. `12302` and "Connection Type" "TCP"

With all that done, just press [Apply], and your new Seq instance should be up and running.
