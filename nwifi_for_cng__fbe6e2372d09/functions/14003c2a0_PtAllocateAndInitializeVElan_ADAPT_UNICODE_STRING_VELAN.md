# PtAllocateAndInitializeVElan(_ADAPT *,_UNICODE_STRING *,_VELAN * *)

- ea: `0x14003c2a0`
- end: `0x14003c793`
- name: `?PtAllocateAndInitializeVElan@@YAHPEAU_ADAPT@@PEAU_UNICODE_STRING@@PEAPEAU_VELAN@@@Z`
- size: `1267`
- prototype: `int(struct _ADAPT *, struct _UNICODE_STRING *, struct _VELAN **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x140035ae0`

## callees

- `0x14000d21c`
- `0x1400208f0`
- `0x140020dc0`
- `0x140024944`
- `0x140036ca0`
- `0x14003c2a0`
- `0x140091e24`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14003c48b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003c48b`
- `ntoskrnl!RtlGUIDFromString` at `0x14003c4a2`
- `ntoskrnl!RtlGUIDFromString` at `0x14003c4a2`
- `ntoskrnl!KeInitializeEvent` at `0x14003c40a`
- `ntoskrnl!KeInitializeEvent` at `0x14003c40a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003c390`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003c390`
- `ntoskrnl!ExAllocatePool2` at `0x14003c3a6`
- `ntoskrnl!ExAllocatePool2` at `0x14003c3a6`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003c575`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003c5d4`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003c5ed`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003c575`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003c5d4`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003c5ed`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14003c45d`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14003c45d`
- `NDIS!NdisAllocateTimerObject` at `0x14003c63e`
- `NDIS!NdisAllocateTimerObject` at `0x14003c63e`
- `NDIS!NdisAllocateRWLock` at `0x14003c3d6`
- `NDIS!NdisAllocateRWLock` at `0x14003c3d6`

## pseudocode

```c

```
