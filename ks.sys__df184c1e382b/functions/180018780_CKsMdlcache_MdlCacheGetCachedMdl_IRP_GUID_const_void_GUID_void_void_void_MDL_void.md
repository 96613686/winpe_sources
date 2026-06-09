# CKsMdlcache::MdlCacheGetCachedMdl(_IRP *,_GUID const &,void (*)(_GUID,void *,void *),void *,_MDL * *,void * *)

- ea: `0x180018780`
- end: `0x180018904`
- name: `?MdlCacheGetCachedMdl@CKsMdlcache@@UEAAJPEAU_IRP@@AEBU_GUID@@P6AXU3@PEAX3@Z3PEAPEAU_MDL@@PEAPEAX@Z`
- size: `388`
- prototype: `__int64 __fastcall(CKsMdlcache *__hidden this, struct _IRP *, const struct _GUID *, void (*)(struct _GUID *__struct_ptr, void *, void *), void *, struct _MDL **, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000dddc`
- `0x180018780`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1800188ca`
- `ntoskrnl!ObfReferenceObject` at `0x1800188ca`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180018814`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180018814`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800188e4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800188e4`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1800187ac`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1800187ac`

## pseudocode

```c

```
