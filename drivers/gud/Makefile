#
# Makefile for the kernel mobicore drivers
#
GUD_ROOT_FOLDER := drivers/gud/
# add our modules to kernel.
obj-$(CONFIG_MOBICORE_API) += mcKernelApi.o
obj-$(CONFIG_MOBICORE_SUPPORT) += mcDrvModule.o

mcDrvModule-objs := MobiCoreDriver/mcDrvModule.o

mcKernelApi-objs := MobiCoreKernelApi/main.o \
		MobiCoreKernelApi/clientlib.o \
		MobiCoreKernelApi/device.o \
		MobiCoreKernelApi/session.o \
		MobiCoreKernelApi/connection.o

# Release mode by default
ccflags-y := -DNDEBUG
ccflags-y += -Wno-declaration-after-statement

ccflags-$(CONFIG_MOBICORE_DEBUG) += -DDEBUG
ccflags-$(CONFIG_MOBICORE_VERBOSE) += -DDEBUG_VERBOSE

ccflags-y += -I$(GUD_ROOT_FOLDER)/MobiCoreDriver/platforms/EXYNOS_4X12_STD
ccflags-y += -I$(GUD_ROOT_FOLDER)/MobiCoreDriver/public
ccflags-y += -I$(GUD_ROOT_FOLDER)/include
ccflags-y += -I$(GUD_ROOT_FOLDER)/include/Mci
