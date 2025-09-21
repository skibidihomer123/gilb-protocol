# gilb-protocol

Text-based protocol over TCP.

All commands are ASCII.

Each protocol message ends with a newline (\n).

For data exchange, messages are length-prefixed so they can contain arbitrary characters, including newlines.

## Connection Handshake

```
Client (in ascii): lets gilb [server identifier]\n
<server checks identifier, if it matches the real identifier then>
  Server (in ascii): OK LETS GILB\n
<else>
  Server (in ascii): sorry no\n
```

## Disconnect Handshake

```
Client (in ascii): i want to disconnect my gilbbing\n
Server (in ascii): ok\n
<connection closed>
```

## Data Send/Recieve

```
Client (in ascii): heres my [MESSAGE LEN IN BYTES] gilberts [MESSAGE]\n
Server (in ascii): ok i gilbert\n
```

```
Server (in ascii): heres your [MESSAGE LEN IN BYTES] gilberts [MESSAGE]\n
Client (in ascii): ok i gilbert\n
```

## Example Conversation

```
Client: lets gilb myserver123\n
Server: OK LETS GILB\n

Client: heres my 12 gilberts hello world!\n
Server: ok i gilbert\n

Server: heres your 20 gilberts welcome to gilb!\n
Client: ok i gilbert\n

Client: i want to disconnect my glibbing\n
Server: ok\n
<connection closed>
```
