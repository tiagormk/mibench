# By default, the code is compiled for a "big endian" machine.
# To compile on a "little endian" machine set the LITTLE_ENDIAN flag.
# To make smaller object code, but run a little slower, don't use UNROLL_LOOPS.
# To use NIST's modified SHA of 7/11/94, define USE_MODIFIED_SHA

#CC = gcc #defined externally
CFLAGS = -O3 -Wall

%.o: %.c
	$(PREFIX)gcc -c $(CFLAGS) -o $@ $<

all: sha sha_repeat

sha:	sha_driver.o sha.o
	$(PREFIX)gcc -static -o $@ sha_driver.o sha.o
	$(PREFIX)strip $@

sha_repeat:	sha_driver.o sha_repeat.o
	$(PREFIX)gcc -static -o $@ sha_driver.o sha_repeat.o
	$(PREFIX)strip $@

clean:
	rm -rf *.o sha sha_repeat output*
