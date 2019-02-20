# SARL Demos


## Body Demo

This demo displays a universe with bodies that puts forces on each other thus changing their position with every tick.

This demo was provided by Sebastian Rodriguez.


### Description

The system is composed of a **Universe** agent and many **Body** agents that pose forces to each other.

The cycle of operation is as follows:

- First agent **Universe** creates the world an spawns a number of bodies.
	- Each body has a location, mass, velocity, and a given current _force_ on it.
- Then **Universe** emits a *Tick* event every `TICK_DELAY`. At every tick, each body:
	- updates its position (based on current location, velocity, and force).
	- informs its body to everyone by emitting an `BodyInfo` event (location and mass).
	- resets its force to zero.
- Every time a body receives a `BodyInfo` event, a (different) body updates its force to account for that body.
- Every time **Universe** receives a `BodyInfo` event (from some body), it re-draws that body.

### Running it

You can run it with the JAR with dependencies:

	java -cp target/demo-nbody-1.0.0.7.2-jar-with-dependencies.jar io.janusproject.Boot au.edu.rmit.agtgrp.sarl.demos.nbody.Universe

Since `io.janusproject.Boot` is the main class in the JAR file you can also just run:

	java -jar target/demo-nbody-1.0.0.7.2-jar-with-dependencies.jar  au.edu.rmit.agtgrp.sarl.demos.nbody.Universe



### Screenshot

![Screenshot](/screenshot.png)



-------------------------

## Ping Pong Demo

This is the [Ping-Pong tutorial](http://www.sarl.io/docs/official/tutorials/PingPong.html) demo in SARL documentation.

The demo-tutorial is in package `au.edu.rmiagtgrp.sarl.demos.pingpong`

To run it:

```
java -cp target/demo-nbody-1.0.0.8.6-jar-with-dependencies.jar io.janusproject.Boot au.edu.rmiagtgrp.sarl.demos.pingpong.BootAgent
```

