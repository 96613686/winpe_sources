# MsKmeAllocateIoRun

- ea: `0x1c003dfc0`
- end: `0x1c003e359`
- name: `MsKmeAllocateIoRun`
- size: `921`
- prototype: `__int64 __fastcall(int, int, int, int, __int16, PVOID VirtualAddress, ULONG Length, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x1c003dfc0`
- `0x1c003e360`
- `0x1c003e3c4`
- `0x1c005b72c`
- `0x1c006acc0`
- `0x1c006af80`
- `0x1c0092bf0`
- `0x1c009d164`
- `0x1c009d1d8`
- `0x1c009d260`
- `0x1c009d2e4`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0081f72`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0081f72`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1c006bff9`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1c006bff9`
- `ntoskrnl!KeDelayExecutionThread` at `0x1c008216f`
- `ntoskrnl!KeDelayExecutionThread` at `0x1c008216f`
- `ntoskrnl!IoAllocateMdl` at `0x1c003e084`
- `ntoskrnl!IoAllocateMdl` at `0x1c003e084`
- `ntoskrnl!MmProbeAndLockPages` at `0x1c003e0ca`
- `ntoskrnl!MmProbeAndLockPages` at `0x1c003e0ca`
- `ntoskrnl!IoFreeMdl` at `0x1c0081e53`
- `ntoskrnl!IoFreeMdl` at `0x1c0081ec3`
- `ntoskrnl!IoFreeMdl` at `0x1c0081fe2`
- `ntoskrnl!IoFreeMdl` at `0x1c0081e53`
- `ntoskrnl!IoFreeMdl` at `0x1c0081ec3`
- `ntoskrnl!IoFreeMdl` at `0x1c0081fe2`
- `ntoskrnl!MmUnlockPages` at `0x1c0081fd2`
- `ntoskrnl!MmUnlockPages` at `0x1c0081fd2`
- `ntoskrnl!IoMakeAssociatedIrpEx` at `0x1c003e14d`
- `ntoskrnl!IoMakeAssociatedIrpEx` at `0x1c0081f45`
- `ntoskrnl!IoMakeAssociatedIrpEx` at `0x1c003e14d`
- `ntoskrnl!IoMakeAssociatedIrpEx` at `0x1c0081f45`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c00820bf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c00820bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0082152`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0082152`

## pseudocode

```c

```
