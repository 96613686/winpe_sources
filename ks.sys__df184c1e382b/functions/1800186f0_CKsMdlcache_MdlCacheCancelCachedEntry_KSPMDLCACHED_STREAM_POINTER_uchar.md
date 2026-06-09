# CKsMdlcache::MdlCacheCancelCachedEntry(_KSPMDLCACHED_STREAM_POINTER *,uchar &)

- ea: `0x1800186f0`
- end: `0x180018779`
- name: `?MdlCacheCancelCachedEntry@CKsMdlcache@@QEAAJPEAU_KSPMDLCACHED_STREAM_POINTER@@AEAE@Z`
- size: `137`
- prototype: `__int64 __fastcall(KSPIN_LOCK *this, struct _KSPMDLCACHED_STREAM_POINTER *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a2f8`

## callees

- `0x180019cb0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18001874d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18001874d`
- `ntoskrnl!KeReleaseSpinLock` at `0x18001871f`
- `ntoskrnl!KeReleaseSpinLock` at `0x18001871f`

## pseudocode

```c

```
