# WFDDeviceInitialize(_WFD_ROLE *,void * *)

- ea: `0x140087d58`
- end: `0x140087e8d`
- name: `?WFDDeviceInitialize@@YAHPEAU_WFD_ROLE@@PEAPEAX@Z`
- size: `309`
- prototype: `__int64 __fastcall(struct _WFD_ROLE *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14007c194`

## callees

- `0x14000d21c`
- `0x140020dc0`
- `0x140087d58`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140087e0a`
- `ntoskrnl!KeInitializeEvent` at `0x140087e0a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140087d9b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140087d9b`
- `ntoskrnl!KeInitializeSpinLock` at `0x140087e27`
- `ntoskrnl!KeInitializeSpinLock` at `0x140087e27`

## pseudocode

```c

```
