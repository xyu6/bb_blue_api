#project name change to match your main c file
TARGET = center_servos




 

TOUCH 	 := $(shell touch *)
CC	:= gcc
LINKER   := gcc -o
CFLAGS	:= -c -Wall -g
LFLAGS	:= -lm -lrt -lpthread -lbb_blue_api

SOURCES  := $(wildcard *.c)
INCLUDES := $(wildcard *.h)reboot
OBJECTS  := $(SOURCES:$%.c=$%.o)
RM := rm -f

INSTALL_DIR = /usr/bin/

# linking Objects
$(TARGET): $(OBJECTS)
	@$(LINKER) $(@) $(OBJECTS) $(LFLAGS)
	@echo
	@echo "Linking Complete"


# compiling command
$(OBJECTS): %.o : %.c
	@$(TOUCH) $(CC) $(CFLAGS) -c $< -o $(@)
	@echo "Compiled "$<" successfully!"


# install to /usr/bin
$(phony all) : $(TARGET)
.PHONY: install

install: $(all)
	@$(MAKE)
	@install -m 0755 $(TARGET) $(INSTALL_DIR)
	@echo
	@echo "Project "$(TARGET)" installed to $(INSTALL_DIR)"
	@echo
	
clean:
	@$(RM) $(OBJECTS)
	@$(RM) $(TARGET)
	@echo "Cleanup complete!"

	