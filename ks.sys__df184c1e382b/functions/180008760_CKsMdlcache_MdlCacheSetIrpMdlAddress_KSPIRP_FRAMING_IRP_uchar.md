# CKsMdlcache::MdlCacheSetIrpMdlAddress(KSPIRP_FRAMING_ *,_IRP *,uchar)

- ea: `0x180008760`
- end: `0x1800088a9`
- name: `?MdlCacheSetIrpMdlAddress@CKsMdlcache@@UEAAJPEAUKSPIRP_FRAMING_@@PEAU_IRP@@E@Z`
- size: `329`
- prototype: `__int64 __fastcall(KSPIN_LOCK *this, struct KSPIRP_FRAMING_ *, struct _IRP *, char)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008760`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1800087e0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1800087e0`
- `ntoskrnl!KeReleaseSpinLock` at `0x180008856`
- `ntoskrnl!KeReleaseSpinLock` at `0x180008856`
- `ntoskrnl!ExFreePoolWithTag` at `0x180008876`
- `ntoskrnl!ExFreePoolWithTag` at `0x180008894`
- `ntoskrnl!ExFreePoolWithTag` at `0x180008876`
- `ntoskrnl!ExFreePoolWithTag` at `0x180008894`

## pseudocode

```c

```
