# CClfsContainer::QuerySecurityDescriptor(void * &,ulong &)

- ea: `0x140070b5c`
- end: `0x140070cba`
- name: `?QuerySecurityDescriptor@CClfsContainer@@QEAAJAEAPEAXAEAK@Z`
- size: `350`
- prototype: `__int64 __fastcall(CClfsContainer *__hidden this, void **, unsigned int *)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400337e4`
- `0x14003be98`
- `0x140070a38`

## callees

- `0x14003306c`
- `0x140070b5c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140070bee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140070ca5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bcc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140070bee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140070ca5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bcc1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140070ba3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140070c25`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140070ba3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140070c25`

## pseudocode

```c

```
