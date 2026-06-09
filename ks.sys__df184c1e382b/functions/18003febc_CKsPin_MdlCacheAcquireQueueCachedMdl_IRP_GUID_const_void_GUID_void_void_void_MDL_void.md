# CKsPin::MdlCacheAcquireQueueCachedMdl(_IRP *,_GUID const &,void (*)(_GUID,void *,void *),void *,_MDL * *,void * *)

- ea: `0x18003febc`
- end: `0x180040005`
- name: `?MdlCacheAcquireQueueCachedMdl@CKsPin@@QEAAJPEAU_IRP@@AEBU_GUID@@P6AXU3@PEAX3@Z3PEAPEAU_MDL@@PEAPEAX@Z`
- size: `329`
- prototype: `__int64 __fastcall(CKsPin *__hidden this, struct _IRP *, const struct _GUID *, void (*)(struct _GUID *__struct_ptr, void *, void *), void *, struct _MDL **, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800425d8`

## callees

- `0x18000c630`
- `0x180019cb0`
- `0x18003febc`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x18003ffe3`
- `ntoskrnl!KeReleaseMutex` at `0x18003ffe3`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003fef0`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003fef0`

## pseudocode

```c

```
