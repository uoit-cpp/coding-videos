# This makefile will be used to build our program

CC = g++ # Choosing a compiler
CFLAGS = # Compiler flags
LDFLAGS = # Linker flags

SOURCES = main.cpp Sum.cpp	# cpp files needed to make the program
HEADERS = Sum.h # header file
OBJECTS = $(SOURCES:.cpp=.o) # a rule that will construct the names of .o files from .cpp files
EXE = sum

all: $(EXE)											# default build target depends upon our program

$(EXE): $(OBJECTS)							# the program depends to upon .o files (so if any .o file is changed since the last build, program will be built again)
	$(CC) $(LDFLAGS) -o $@ $(OBJECTS)

%.o: %.cpp $(HEADERS)						# compile .cpp file to create .o file.  if a .cpp or any header file change, rebuild the .o file
	$(CC) -c $(CFLAGS) $<

.PHONY: clean										# a .PHONY target - even if a file `clean` exists in the current directory make clean target

clean:													# clean up everything (i.e. temp files generated by built)
	rm -rf *.o $(EXE)

