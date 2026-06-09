# Dot11DelayedIoctlReset(void *,void *,_IO_WORKITEM *)

- ea: `0x14003eb90`
- end: `0x14003ecdb`
- name: `?Dot11DelayedIoctlReset@@YAXPEAX0PEAU_IO_WORKITEM@@@Z`
- size: `331`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x14001666c`
- `0x140019e34`
- `0x140024944`
- `0x140034758`
- `0x14003eb90`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14003ec09`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003ec09`
- `ntoskrnl!IoFreeWorkItem` at `0x14003ecc1`
- `ntoskrnl!IoFreeWorkItem` at `0x14003ecc1`
- `ntoskrnl!KeSetEvent` at `0x14003ec51`
- `ntoskrnl!KeSetEvent` at `0x14003ec51`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003ec8c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003ec8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ec9d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ec9d`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14003ebb1`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14003ebb1`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003ebda`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003ebda`

## pseudocode

```c

```
