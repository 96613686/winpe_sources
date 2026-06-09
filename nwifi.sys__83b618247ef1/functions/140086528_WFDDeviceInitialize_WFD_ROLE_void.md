# WFDDeviceInitialize(_WFD_ROLE *,void * *)

- ea: `0x140086528`
- end: `0x14008665d`
- name: `?WFDDeviceInitialize@@YAHPEAU_WFD_ROLE@@PEAPEAX@Z`
- size: `309`
- prototype: `__int64 __fastcall(struct _WFD_ROLE *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14007a964`

## callees

- `0x14000d22c`
- `0x140020dc0`
- `0x140086528`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400865da`
- `ntoskrnl!KeInitializeEvent` at `0x1400865da`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008656b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008656b`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400865f7`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400865f7`

## pseudocode

```c

```
