# Python HTTP Server and Proxy Exercises

Python networking exercises using TCP sockets to explore HTTP request handling, concurrent connections, and proxy caching.

## Contents

The repository includes two sets of implementations:

- **`project/`** — HTTP server implementations, including `single_threaded.py`, `stmain.py`, and `mt_main.py`, plus a proxy-server exercise in `proxyS.py`.
- **`Mini Project 371/`** — an additional set of server and proxy implementations, sample HTML files, a project report, and notes on reproducing a `304 Not Modified` response.

These directories contain related but distinct versions of the exercises; they are retained separately.

## Concepts explored

- TCP sockets and client/server communication
- Parsing basic HTTP requests
- Handling GET requests and, in the `project/` implementation, POST requests
- Returning HTTP response status codes
- Handling multiple connections using Python threads
- Exploring simple HTTP proxy caching

## Running the examples

Use Python 3 and run each server from the directory containing its sample HTML files.

For example, to start the single-threaded server:

```bash
cd project
python single_threaded.py
```

This implementation binds to `localhost:8080`. You can then make a request from another terminal:

```bash
curl http://localhost:8080/test.html
```

To explore the other versions, run `stmain.py` or `mt_main.py` in the relevant directory instead. Check each script's configured port before connecting; the examples do not all use the same port. Stop a running server with Ctrl+C before launching another instance on the same port.

The proxy exercises are in `proxyS.py`. They are instructional implementations and may need adjustments for modern Python and HTTP environments.

## Notes and limitations

These are coursework-oriented networking implementations, **not production HTTP servers**. In particular:

- Request parsing and HTTP header handling are simplified.
- File paths come from requests and are not safely restricted to a document root.
- Error handling, connection management, and concurrency behavior are limited.
- The proxy code uses legacy assumptions and should not be exposed to untrusted networks.
- Some status-code behaviors were designed for exercises rather than full HTTP compliance.

For safety, run the examples locally in a controlled environment.

## Suggested improvements

- Add automated tests for GET, POST, and error responses.
- Validate request paths and prevent directory traversal.
- Use context managers for files and sockets.
- Improve HTTP response formatting and request parsing.
- Consolidate shared logic after verifying the differences between implementations.
