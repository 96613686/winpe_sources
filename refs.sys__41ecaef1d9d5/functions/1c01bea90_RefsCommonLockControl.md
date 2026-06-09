# RefsCommonLockControl

- ea: `0x1c01bea90`
- end: `0x1c01bf015`
- name: `RefsCommonLockControl`
- size: `1413`
- prototype: `__int64 __fastcall(PVOID Context, PIRP Irp)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1c0008060`
- `0x1c0099ba0`

## callees

- `0x1c0004484`
- `0x1c00049a0`
- `0x1c0005450`
- `0x1c0005768`
- `0x1c000f770`
- `0x1c0013f90`
- `0x1c0063db0`
- `0x1c0068168`
- `0x1c01bea90`
- `0x1c01c7014`

## import_xrefs

- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1c01bee86`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1c01bee86`
- `ntoskrnl!ObfDereferenceObject` at `0x1c01bef42`
- `ntoskrnl!ObfDereferenceObject` at `0x1c01beffe`
- `ntoskrnl!ObfDereferenceObject` at `0x1c01bef42`
- `ntoskrnl!ObfDereferenceObject` at `0x1c01beffe`
- `ntoskrnl!FsRtlCheckOplock` at `0x1c01bede6`
- `ntoskrnl!FsRtlCheckOplock` at `0x1c01bede6`
- `ntoskrnl!ObfReferenceObject` at `0x1c01becb2`
- `ntoskrnl!ObfReferenceObject` at `0x1c01becb2`
- `ntoskrnl!FsRtlAreThereWaitingFileLocks` at `0x1c01bedb9`
- `ntoskrnl!FsRtlAreThereWaitingFileLocks` at `0x1c01bedb9`
- `ntoskrnl!FsRtlProcessFileLock` at `0x1c01bee4a`
- `ntoskrnl!FsRtlProcessFileLock` at `0x1c01bee4a`

## pseudocode

```c

```
