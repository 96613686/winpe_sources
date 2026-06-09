# Dot11DelayedIoctlReset(void *,void *,_IO_WORKITEM *)

- ea: `0x14003e970`
- end: `0x14003eabb`
- name: `?Dot11DelayedIoctlReset@@YAXPEAX0PEAU_IO_WORKITEM@@@Z`
- size: `331`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x14001667c`
- `0x140019e34`
- `0x140024944`
- `0x140034538`
- `0x14003e970`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14003e9e9`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003e9e9`
- `ntoskrnl!IoFreeWorkItem` at `0x14003eaa1`
- `ntoskrnl!IoFreeWorkItem` at `0x14003eaa1`
- `ntoskrnl!KeSetEvent` at `0x14003ea31`
- `ntoskrnl!KeSetEvent` at `0x14003ea31`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003ea6c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003ea6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ea7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ea7d`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14003e991`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14003e991`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003e9ba`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003e9ba`

## pseudocode

```c

```
