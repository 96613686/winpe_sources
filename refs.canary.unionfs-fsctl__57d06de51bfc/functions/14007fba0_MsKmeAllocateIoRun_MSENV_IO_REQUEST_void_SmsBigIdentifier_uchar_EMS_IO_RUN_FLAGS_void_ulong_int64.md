# MsKmeAllocateIoRun(_MSENV_IO_REQUEST *,void *,SmsBigIdentifier *,uchar,_EMS_IO_RUN_FLAGS,void *,ulong,__int64)

- ea: `0x14007fba0`
- end: `0x1400802fa`
- name: `?MsKmeAllocateIoRun@@YAPEAU_MS_IO_RUN@@PEAU_MSENV_IO_REQUEST@@PEAXPEATSmsBigIdentifier@@EW4_EMS_IO_RUN_FLAGS@@1K_J@Z`
- size: `1882`
- prototype: ``
- caller_count: `10`
- callee_count: `11`
- tags: ``

## callers

- `0x1400602cc`
- `0x14007f200`
- `0x14007fb20`
- `0x140080300`
- `0x140083174`
- `0x1400ad95c`
- `0x1400af380`
- `0x140120260`
- `0x14012229c`
- `0x140129880`

## callees

- `0x14007fba0`
- `0x1400a5c6c`
- `0x1400accb4`
- `0x1400e2e8c`
- `0x1400f6bdc`
- `0x1400f6bf0`
- `0x1400f8c4c`
- `0x1400f8cc0`
- `0x1400f8d4c`
- `0x1400f8dd4`
- `0x1401e9e40`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1401f7899`
- `ntoskrnl!KeDelayExecutionThread` at `0x1401f7899`
- `ntoskrnl!IoAllocateMdl` at `0x14007fc96`
- `ntoskrnl!IoAllocateMdl` at `0x14007fc96`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007fce9`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007fce9`
- `ntoskrnl!IoFreeMdl` at `0x14007fda0`
- `ntoskrnl!IoFreeMdl` at `0x140080121`
- `ntoskrnl!IoFreeMdl` at `0x1400801df`
- `ntoskrnl!IoFreeMdl` at `0x14007fda0`
- `ntoskrnl!IoFreeMdl` at `0x140080121`
- `ntoskrnl!IoFreeMdl` at `0x1400801df`
- `ntoskrnl!MmUnlockPages` at `0x14007fd91`
- `ntoskrnl!MmUnlockPages` at `0x14007fd91`
- `ntoskrnl!IoMakeAssociatedIrpEx` at `0x14007fd74`
- `ntoskrnl!IoMakeAssociatedIrpEx` at `0x1401f77b1`
- `ntoskrnl!IoMakeAssociatedIrpEx` at `0x14007fd74`
- `ntoskrnl!IoMakeAssociatedIrpEx` at `0x1401f77b1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400802d2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400802d2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401f787b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401f787b`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1401eb2c4`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1401eb2c4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401f77df`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401f77df`

## pseudocode

```c

```
