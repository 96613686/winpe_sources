# ndisExpandStackTrace(_NDIS_STACK_TRACE * *,_RTL_DYNAMIC_HASH_TABLE_CONTEXT *,unsigned __int64 *)

- ea: `0x140069080`
- end: `0x140069178`
- name: `?ndisExpandStackTrace@@YAEPEAPEAU_NDIS_STACK_TRACE@@PEAU_RTL_DYNAMIC_HASH_TABLE_CONTEXT@@PEA_K@Z`
- size: `248`
- prototype: `unsigned __int8(struct _NDIS_STACK_TRACE **, struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140068e10`

## callees

- `0x140069080`
- `0x1400eb4c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140069151`
- `ntoskrnl!ExFreePoolWithTag` at `0x140069151`
- `ntoskrnl!ExAllocatePool2` at `0x1400690bb`
- `ntoskrnl!ExAllocatePool2` at `0x1400690bb`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140069120`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140069120`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14006913d`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14006913d`

## pseudocode

```c

```
