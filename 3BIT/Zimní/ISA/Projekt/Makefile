#
# Warning: you may need more libraries than are included here on the
# build line.  The agent frequently needs various libraries in order
# to compile pieces of it, but is OS dependent and we can't list all
# the combinations here.  Instead, look at the libraries that were
# used when linking the snmpd master agent and copy those to this
# file.
#

CC=gcc

CFLAGS=-I. `net-snmp-config --cflags`
BUILDLIBS=`net-snmp-config --libs`
BUILDAGENTLIBS=`net-snmp-config --agent-libs`

# shared library flags (assumes gcc)
DLFLAGS=-fPIC -shared

isaAgentObject.so: isaAgentObject.c Makefile
	$(CC) $(CFLAGS) $(DLFLAGS) -c -o isaAgentObject.o isaAgentObject.c
	$(CC) $(CFLAGS) $(DLFLAGS) -o isaAgentObject.so isaAgentObject.o

clean:
	rm isaAgentObject.so isaAgentObject.o
