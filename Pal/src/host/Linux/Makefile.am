# Add host-specific compilation rules here
HOST_DIR = host/$(PAL_HOST)
SEC_DIR = security/$(PAL_HOST)

CC	= gcc
AS	= gcc
AR	= ar rcs
LD	= ld

CFLAGS	= -Wall -fPIC -O2 -std=gnu99 -fgnu89-inline -U_FORTIFY_SOURCE \
	  -fno-omit-frame-pointer \
	  -fno-stack-protector -fno-builtin
ASFLAGS = -DPIC -DSHARED -fPIC -DASSEMBLER -Wa,--noexecstack \
	  -x assembler-with-cpp
LDFLAGS	= -shared -nostdlib -z combreloc -z defs \
	  --version-script $(HOST_DIR)/pal.map -T $(HOST_DIR)/pal.lds
ARFLAGS	=

pal_loader = libpal.so
pal_sec = $(SEC_DIR)/libpal_sec.so
pal_lib = libpal.so
pal_lib_deps = $(HOST_DIR)/pal.map $(HOST_DIR)/pal.lds
pal_lib_post =
pal_static = libpal.a
