# RefsSynchronousMetadataIo(uchar,_VCB *,_FCB *,SmsBigIdentifier *,__int64,ulong,void *,ulong *,void *,ulong,ulong)

- ea: `0x14009d250`
- end: `0x14009d67d`
- name: `?RefsSynchronousMetadataIo@@YAJEPEAU_VCB@@PEAU_FCB@@PEATSmsBigIdentifier@@_JKPEAXPEAK4KK@Z`
- size: `1069`
- prototype: `int(unsigned __int8, struct _VCB *, struct _FCB *, union SmsBigIdentifier *, __int64, unsigned int, void *, unsigned int *, void *, unsigned int, unsigned int)`
- caller_count: `9`
- callee_count: `12`
- tags: ``

## callers

- `0x14009d124`
- `0x14009d1c0`
- `0x1400d8ed8`
- `0x1400e3534`
- `0x1400eefc0`
- `0x1400f72b8`
- `0x14028a18c`
- `0x140299694`
- `0x140302dbc`

## callees

- `0x1400531a0`
- `0x140054950`
- `0x140054b90`
- `0x14008ed70`
- `0x140095850`
- `0x14009d250`
- `0x1400accb4`
- `0x1400b0f9c`
- `0x1400e2e8c`
- `0x1400ef800`
- `0x1400feb68`
- `0x140115d30`

## import_xrefs

- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14009d4e6`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14009d4e6`
- `ntoskrnl!IoGetStackLimits` at `0x14009d3d9`
- `ntoskrnl!IoGetStackLimits` at `0x14009d3d9`
- `ntoskrnl!DbgPrintEx` at `0x14009d529`
- `ntoskrnl!DbgPrintEx` at `0x1401fadc1`
- `ntoskrnl!DbgPrintEx` at `0x14009d529`
- `ntoskrnl!DbgPrintEx` at `0x1401fadc1`
- `ntoskrnl!IoFreeIrp` at `0x14009d458`
- `ntoskrnl!IoFreeIrp` at `0x1401fac48`
- `ntoskrnl!IoFreeIrp` at `0x14009d458`
- `ntoskrnl!IoFreeIrp` at `0x1401fac48`
- `ntoskrnl!IoAllocateMdl` at `0x14009d54c`
- `ntoskrnl!IoAllocateMdl` at `0x14009d54c`
- `ntoskrnl!MmProbeAndLockPages` at `0x1401fabf7`
- `ntoskrnl!MmProbeAndLockPages` at `0x1401fabf7`
- `ntoskrnl!IoFreeMdl` at `0x14009d48a`
- `ntoskrnl!IoFreeMdl` at `0x1401fac31`
- `ntoskrnl!IoFreeMdl` at `0x14009d48a`
- `ntoskrnl!IoFreeMdl` at `0x1401fac31`
- `ntoskrnl!MmUnlockPages` at `0x14009d47a`
- `ntoskrnl!MmUnlockPages` at `0x14009d47a`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1401fad34`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1401fad34`
- `ntoskrnl!MmMdlPageContentsState` at `0x1401fac0c`
- `ntoskrnl!MmMdlPageContentsState` at `0x1401fac0c`
- `ntoskrnl!IofCallDriver` at `0x14009d404`
- `ntoskrnl!IofCallDriver` at `0x14009d404`
- `ntoskrnl!IoAllocateIrpEx` at `0x14009d2c8`
- `ntoskrnl!IoAllocateIrpEx` at `0x14009d2c8`
- `ntoskrnl!KeWaitForSingleObject` at `0x14009d4ae`
- `ntoskrnl!KeWaitForSingleObject` at `0x14009d4ae`
- `ntoskrnl!KeInitializeEvent` at `0x14009d328`
- `ntoskrnl!KeInitializeEvent` at `0x14009d328`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009d668`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009d668`

## string_xrefs

- `0x1401fadb3`: `SynchronousMinstoreIo (readcopy) to Vcb: %p TargetDeviceObject: %p returned unexpected status %08lx (will be reported only once)\n`
- `0x14009d623`: `write`

## pseudocode

```c

```
