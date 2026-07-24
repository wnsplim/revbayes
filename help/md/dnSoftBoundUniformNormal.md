## name
dnSoftBoundUniformNormal
## title
Softbound Uniform Distribution with Normal distributed tails.
## description
A softbound uniform distribution with normally distributed tails outside the interval of the uniform distribution.
## details
The center piece of this distribution a uniform distribution defined between the given interval. A variable is drawn from that uniform distribution with probability p and with probability 1-p outside the interval. The probability density outside the interval is described by a normal distribution with standard deviation sd.
## authors
Sebastian Hoehna
## see_also
dnUniform
## example
	calib ~ dnSoftBoundUniformNormal( 13.6, 25, sd = 1.0, p = 0.95, "upper" )
	moves[1] = mvSlide(calib, delta=0.1, weight=1.0)
	monitors[1] = screenmonitor(printgen=1000, separator = TAB, calib)
	mymodel = model(p)
	mymcmc = mcmc(mymodel, monitors, moves)
	mymcmc.burnin(generations=20000,tuningInterval=100)
	mymcmc.run(generations=200000)

## references
