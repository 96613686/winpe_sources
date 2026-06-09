# CKsMdlcache::MdlCacheGetCachedMdl(_IRP *,_GUID const &,void (*)(_GUID,void *,void *),void *,_MDL * *,void * *)

- ea: `0x180018730`
- end: `0x1800188b4`
- name: `?MdlCacheGetCachedMdl@CKsMdlcache@@UEAAJPEAU_IRP@@AEBU_GUID@@P6AXU3@PEAX3@Z3PEAPEAU_MDL@@PEAPEAX@Z`
- size: `388`
- prototype: `__int64 __fastcall(CKsMdlcache *__hidden this, struct _IRP *, const struct _GUID *, void (*)(struct _GUID *__struct_ptr, void *, void *), void *, struct _MDL **, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000dddc`
- `0x180018730`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x18001887a`
- `ntoskrnl!ObfReferenceObject` at `0x18001887a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1800187c4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1800187c4`
- `ntoskrnl!KeReleaseSpinLock` at `0x180018894`
- `ntoskrnl!KeReleaseSpinLock` at `0x180018894`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x18001875c`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x18001875c`

## pseudocode

```c

```
