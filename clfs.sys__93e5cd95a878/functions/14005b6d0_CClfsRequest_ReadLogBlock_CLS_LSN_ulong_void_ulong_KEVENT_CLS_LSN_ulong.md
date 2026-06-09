# CClfsRequest::ReadLogBlock(_CLS_LSN &,ulong,void *,ulong,_KEVENT *,_CLS_LSN &,ulong &)

- ea: `0x14005b6d0`
- end: `0x14005ba43`
- name: `?ReadLogBlock@CClfsRequest@@QEAAJAEAT_CLS_LSN@@KPEAXKPEAU_KEVENT@@0AEAK@Z`
- size: `883`
- prototype: `__int64 __fastcall(CClfsRequest *__hidden this, union _CLS_LSN *, unsigned int, void *, unsigned int, struct _KEVENT *, union _CLS_LSN *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400596b8`

## callees

- `0x140007470`
- `0x140008330`
- `0x14000c98c`
- `0x14000f3d4`
- `0x140017f20`
- `0x14005b6d0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14005b9b0`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005b9b0`
- `ntoskrnl!KeClearEvent` at `0x14005b81e`
- `ntoskrnl!KeClearEvent` at `0x14005b81e`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14005b786`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14005b786`
- `ntoskrnl!IoAllocateMdl` at `0x14005b891`
- `ntoskrnl!IoAllocateMdl` at `0x14005b891`
- `ntoskrnl!MmProbeAndLockPages` at `0x14005b8b3`
- `ntoskrnl!MmProbeAndLockPages` at `0x14005b8b3`
- `ntoskrnl!IoAllocateIrp` at `0x14005b735`
- `ntoskrnl!IoAllocateIrp` at `0x14005b735`

## pseudocode

```c

```
