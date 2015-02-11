## Some basics
To get started, we need to make sure ipfs has been initialized,
if you havent done this yet:
```
ipfs init
```

Next lets start up the ipfs daemon:
```
ipfs daemon
```

Once the daemon is fully set up it will print something like 
"api server listening on /ip4/127.0.0.1/tcp/5001". after you see this message,
youll be able to run any of the ipfs commands you want. without running
the daemon, youll only be able to successfully run a smaller subset of the
commands.

Now that we have the daemon up, lets have some fun.

Basic work with files in ipfs:
```
echo "welcome to ipfs!" > hello
ipfs add hello
```

That should have printed out something along the lines of:
```
added qmxzzpcazv6tw1tvicf9poare9kkb1fwmzbvamytdwvshe hello
```

That means that the file was successfully added into the ipfs datastore,
and may be accessed through ipfs now.

To check, try:
```
ipfs cat qmxzzpcazv6tw1tvicf9poare9kkb1fwmzbvamytdwvshe
```
(Note: if your files hash was different in the first step, use your
hash instead of mine)


If all went well, you should see the text from your file printed out to you!

`ipfs cat` is a great command to quickly retrieve and view files, but if the
file you are requesting contains binary data (such as an image or movie)
`ipfs get` might be more appropriate:
```
ipfs get -o cats.png $hashofcatpic
```

This will create a file named 'cats.png' that contains the data from the
given hash.

