Most of the tornado tutorials are written in the context of a web server. While that's what tornado is designed for, you don't need to start a server to use it.

I find it easier to learn the basics about tornado with command line programs because they are a bit easier to run.

Here’s a snippet that I found online. It’s very simple

```
# Example of non-blocking sleep.
import time
from tornado.ioloop import IOLoop
from tornado import gen


@gen.engine
def f():
    print 'sleeping'
    yield gen.Task(IOLoop.instance().add_timeout, time.time() + 1)
    print 'awake!'


if __name__ == "__main__":
    # Note that now code is executed "concurrently"
    IOLoop.instance().add_callback(f)
    IOLoop.instance().add_callback(f)
    IOLoop.instance().start()
```

the problem is, it doesn't really do much and it's not clear everything
works.

(to be continued...)