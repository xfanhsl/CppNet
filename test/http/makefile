SRCS = $(wildcard ./*.cpp)

OBJS = $(patsubst %.cpp, %.o, $(SRCS))

CC = g++

INCLUDES = -I.               \
           -I../../base      \
           -I../../include   \

#debug
#CCFLAGS = -lpthread -fPIC -m64 -g -pg -std=c++11 -lstdc++ -pipe 

CCFLAGS = -lpthread -fPIC -m64 -O2 -std=c++11 -lstdc++ -pipe -march=corei7 

TARGET = ../../libcppnet.a
SERBIN = httpser

all: $(SERBIN)

$(SERBIN):$(OBJS) $(TARGET)
	$(CC) $^ -o $@  $(TARGET)  $(CCFLAGS) $(INCLUDES)

%.o : %.cpp
	$(CC) -c $< -o $@ $(CCFLAGS) $(INCLUDES) 

clean:
	rm -rf $(OBJS) $(SERBIN)