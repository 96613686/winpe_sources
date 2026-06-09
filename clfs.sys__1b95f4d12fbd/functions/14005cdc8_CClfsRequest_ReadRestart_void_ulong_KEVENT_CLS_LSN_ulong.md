# CClfsRequest::ReadRestart(void *,ulong,_KEVENT *,_CLS_LSN &,ulong &)

- ea: `0x14005cdc8`
- end: `0x14005d0c1`
- name: `?ReadRestart@CClfsRequest@@QEAAJPEAXKPEAU_KEVENT@@AEAT_CLS_LSN@@AEAK@Z`
- size: `761`
- prototype: `__int64 __usercall@<rax>(CClfsRequest *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, struct _KEVENT *@<r9>, union _CLS_LSN *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14005c934`

## callees

- `0x140007470`
- `0x140008330`
- `0x14000f3d4`
- `0x14000f64c`
- `0x140017f20`
- `0x14005cdc8`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14005d021`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005d021`
- `ntoskrnl!KeClearEvent` at `0x14005cec9`
- `ntoskrnl!KeClearEvent` at `0x14005cec9`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14005ce78`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14005ce78`
- `ntoskrnl!IoAllocateMdl` at `0x14005cf1a`
- `ntoskrnl!IoAllocateMdl` at `0x14005cf1a`
- `ntoskrnl!MmProbeAndLockPages` at `0x14005cf3d`
- `ntoskrnl!MmProbeAndLockPages` at `0x14005cf3d`
- `ntoskrnl!IoFreeMdl` at `0x14005d095`
- `ntoskrnl!IoFreeMdl` at `0x14007a132`
- `ntoskrnl!IoFreeMdl` at `0x14005d095`
- `ntoskrnl!IoFreeMdl` at `0x14007a132`
- `ntoskrnl!MmUnlockPages` at `0x14005d084`
- `ntoskrnl!MmUnlockPages` at `0x14007a122`
- `ntoskrnl!MmUnlockPages` at `0x14005d084`
- `ntoskrnl!MmUnlockPages` at `0x14007a122`
- `ntoskrnl!IoAllocateIrp` at `0x14005ce26`
- `ntoskrnl!IoAllocateIrp` at `0x14005ce26`

## pseudocode

```c

```
