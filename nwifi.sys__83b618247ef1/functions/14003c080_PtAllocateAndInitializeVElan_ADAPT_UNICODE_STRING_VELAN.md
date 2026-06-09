# PtAllocateAndInitializeVElan(_ADAPT *,_UNICODE_STRING *,_VELAN * *)

- ea: `0x14003c080`
- end: `0x14003c573`
- name: `?PtAllocateAndInitializeVElan@@YAHPEAU_ADAPT@@PEAU_UNICODE_STRING@@PEAPEAU_VELAN@@@Z`
- size: `1267`
- prototype: `int(struct _ADAPT *, struct _UNICODE_STRING *, struct _VELAN **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1400358c0`

## callees

- `0x14000d22c`
- `0x1400208f0`
- `0x140020dc0`
- `0x140024944`
- `0x140036a80`
- `0x14003c080`
- `0x140090644`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14003c26b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003c26b`
- `ntoskrnl!RtlGUIDFromString` at `0x14003c282`
- `ntoskrnl!RtlGUIDFromString` at `0x14003c282`
- `ntoskrnl!KeInitializeEvent` at `0x14003c1ea`
- `ntoskrnl!KeInitializeEvent` at `0x14003c1ea`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003c170`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003c170`
- `ntoskrnl!ExAllocatePool2` at `0x14003c186`
- `ntoskrnl!ExAllocatePool2` at `0x14003c186`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003c355`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003c3b4`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003c3cd`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003c355`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003c3b4`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003c3cd`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14003c23d`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14003c23d`
- `NDIS!NdisAllocateTimerObject` at `0x14003c41e`
- `NDIS!NdisAllocateTimerObject` at `0x14003c41e`
- `NDIS!NdisAllocateRWLock` at `0x14003c1b6`
- `NDIS!NdisAllocateRWLock` at `0x14003c1b6`

## pseudocode

```c

```
