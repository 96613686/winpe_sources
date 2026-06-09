# ndisExpandStackTrace(_NDIS_STACK_TRACE * *,_RTL_DYNAMIC_HASH_TABLE_CONTEXT *,unsigned __int64 *)

- ea: `0x14007d580`
- end: `0x14007d678`
- name: `?ndisExpandStackTrace@@YAEPEAPEAU_NDIS_STACK_TRACE@@PEAU_RTL_DYNAMIC_HASH_TABLE_CONTEXT@@PEA_K@Z`
- size: `248`
- prototype: `unsigned __int8(struct _NDIS_STACK_TRACE **, struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140014f00`

## callees

- `0x14007d580`
- `0x1400e62c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14007d651`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007d651`
- `ntoskrnl!ExAllocatePool2` at `0x14007d5bb`
- `ntoskrnl!ExAllocatePool2` at `0x14007d5bb`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14007d620`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14007d620`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14007d63d`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14007d63d`

## pseudocode

```c

```
