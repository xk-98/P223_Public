#!/bin/sh
#
# Makefile for Leroi_c

FC	= gfortran
OS	= $(shell uname -s)
BUILD 	= RELEASE
# BUILD	= PARANOID
# BUILD 	= DEBUG
EXE	= Leroi.x
RUN	= Leroi

ifeq ($(BUILD), RELEASE)
<<<<<<< HEAD
	FC_OPTS = -O3 -march=native -Q -fwhole-program -fdefault-real-16
=======
	FC_OPTS = -O3 -march=native -Q -fwhole-program -fdefault-real-16 -ffpe-summary=none
>>>>>>> 4676aa917c9d4f1b6eb5eadfe8fe6efe03da6050
else ifeq ($(BUILD), PARANOID)
	FC_OPTS = -fcheck=all, -ffpe-trap=invalid,zero,overflow -g -Wall -Wextra -Werror -pedantic
else ifeq ($(BUILD), DEBUG)
	FC_OPTS = -g -zero -fcheck=all
endif

%.o: %.f90
	$(FC) $(FC_OPTS) -c $<

%.x: %.o
	$(FC) $(LN_OPTS) -o $(EXE) $<

all: $(EXE)

clean:
	rm -f *.o *.mod

install:
	chmod +x $(RUN)
	cp $(RUN) ~/bin
	cp $(EXE) ~/bin

