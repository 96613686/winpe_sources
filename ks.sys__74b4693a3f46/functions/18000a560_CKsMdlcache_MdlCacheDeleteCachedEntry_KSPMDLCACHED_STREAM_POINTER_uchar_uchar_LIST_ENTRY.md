# CKsMdlcache::MdlCacheDeleteCachedEntry(_KSPMDLCACHED_STREAM_POINTER *,uchar,uchar &,_LIST_ENTRY * *)

- ea: `0x18000a560`
- end: `0x18000a658`
- name: `?MdlCacheDeleteCachedEntry@CKsMdlcache@@QEAAXPEAU_KSPMDLCACHED_STREAM_POINTER@@EAEAEPEAPEAU_LIST_ENTRY@@@Z`
- size: `248`
- prototype: `void(CKsMdlcache *__hidden this, struct _KSPMDLCACHED_STREAM_POINTER *, unsigned __int8, unsigned __int8 *, struct _LIST_ENTRY **)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a2f8`
- `0x1800188c0`

## callees

- `0x18000a560`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x18000a647`
- `ntoskrnl!ObfDereferenceObject` at `0x18000a647`
- `ntoskrnl!MmUnlockPages` at `0x18000a616`
- `ntoskrnl!MmUnlockPages` at `0x18000a616`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000a5f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000a5f3`
- `ntoskrnl!IoFreeMdl` at `0x18000a5d1`
- `ntoskrnl!IoFreeMdl` at `0x18000a5d1`
- `ntoskrnl!KeSetEvent` at `0x18000a632`
- `ntoskrnl!KeSetEvent` at `0x18000a632`

## pseudocode

```c

```
