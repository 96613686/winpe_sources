# MsKmeAllocateIoRun(_MSENV_IO_REQUEST *,void *,SmsBigIdentifier *,uchar,_EMS_IO_RUN_FLAGS,void *,ulong,__int64)

- ea: `0x140081630`
- end: `0x140081eae`
- name: `?MsKmeAllocateIoRun@@YAPEAU_MS_IO_RUN@@PEAU_MSENV_IO_REQUEST@@PEAXPEATSmsBigIdentifier@@EW4_EMS_IO_RUN_FLAGS@@1K_J@Z`
- size: `2174`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: ``

## callers

- `0x140080aa0`
- `0x1400813e4`
- `0x1400815b0`
- `0x140082204`
- `0x1400c7fcc`

## callees

- `0x140081630`
- `0x14009fe7c`
- `0x1400fdb0c`
- `0x1400fdb80`
- `0x1400fdc0c`
- `0x1400fdc94`
- `0x1401f4100`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x140081db7`
- `ntoskrnl!KeDelayExecutionThread` at `0x140081db7`
- `ntoskrnl!IoAllocateMdl` at `0x1400817f7`
- `ntoskrnl!IoAllocateMdl` at `0x1400817f7`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400818b9`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400818b9`
- `ntoskrnl!IoFreeMdl` at `0x14008181b`
- `ntoskrnl!IoFreeMdl` at `0x140081917`
- `ntoskrnl!IoFreeMdl` at `0x1400819e8`
- `ntoskrnl!IoFreeMdl` at `0x14008181b`
- `ntoskrnl!IoFreeMdl` at `0x140081917`
- `ntoskrnl!IoFreeMdl` at `0x1400819e8`
- `ntoskrnl!MmUnlockPages` at `0x1400819d9`
- `ntoskrnl!MmUnlockPages` at `0x1400819d9`
- `ntoskrnl!IoMakeAssociatedIrpEx` at `0x1400819c1`
- `ntoskrnl!IoMakeAssociatedIrpEx` at `0x1400819c1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140081d06`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140081d06`
- `ntoskrnl!KeReleaseSpinLock` at `0x140081d99`
- `ntoskrnl!KeReleaseSpinLock` at `0x140081d99`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1401f5414`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1401f5414`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140081b0c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140081b0c`

## pseudocode

```c

```
