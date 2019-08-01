# BF2 Mod docker builder

This is a simple script to build a docker container for a specific mod.

## Prerequisites

This extends the [bf2 server docker](https://github.com/senclan/bf2-server-docker)
image. You will need to first build a `bf2/server:latest` image before you can
build this one.

You should also make sure you download a `zip` of the mods files.

## Usage

```
$ ./build.sh -h
USAGE: ./build.sh [OPTION]...

Options:
  -h        Prints this message
  -s PATH   Path to source file
  -t tag    Tag for docker image
  -k        Keep extracted files directory
              Warning: all files from directory will be included in image
```

## Example

First update the docker file to point to the mod you're installing.

```
sed -i 's/MOD_FOLDER/MODNAME/' Dockerfile
```

Replacing `MODNAME` with the appropriate mod name.

```
./build.sh -s /path/to/mymod.zip -t bf2/mod/mymod:latest
```

Reference [bf2 server docker](https://github.com/senclan/bf2-server-docker) for
examples of running the docker container.
