# CmsReadCache::GatherCacheContext(CmsTransactionContext *,_RANGE const *,ulong,ulong,_MINSTORE_READ_CACHE_CONTEXT *,_MINSTORE_READ_CACHE_CONTEXT_ENVELOPE * *)

- ea: `0x1c00c43c0`
- end: `0x1c00c59a2`
- name: `?GatherCacheContext@CmsReadCache@@QEAAJPEAVCmsTransactionContext@@PEBU_RANGE@@KKPEAU_MINSTORE_READ_CACHE_CONTEXT@@PEAPEAU_MINSTORE_READ_CACHE_CONTEXT_ENVELOPE@@@Z`
- size: `5602`
- prototype: `__int64 __usercall@<rax>(CmsReadCache *__hidden this@<rcx>, struct CmsTransactionContext *@<rdx>, const struct _RANGE *@<r8>, unsigned int@<r9d>, unsigned int, struct _MINSTORE_READ_CACHE_CONTEXT *, struct _MINSTORE_READ_CACHE_CONTEXT_ENVELOPE **)`
- caller_count: `1`
- callee_count: `29`
- tags: ``

## callers

- `0x1c00b1dd0`

## callees

- `0x1c00059f4`
- `0x1c002313c`
- `0x1c002357c`
- `0x1c002981c`
- `0x1c002b674`
- `0x1c0047d84`
- `0x1c0068960`
- `0x1c006acc0`
- `0x1c006af80`
- `0x1c00b3750`
- `0x1c00c382c`
- `0x1c00c3f98`
- `0x1c00c42e0`
- `0x1c00c43c0`
- `0x1c00c59a8`
- `0x1c00c59f0`
- `0x1c00c5a50`
- `0x1c00c5b08`
- `0x1c00c5c44`
- `0x1c00c67c0`
- `0x1c00c6944`
- `0x1c00c69bc`
- `0x1c00c8244`
- `0x1c00c8414`
- `0x1c00c877c`
- `0x1c00c8b78`
- `0x1c00c8eb4`
- `0x1c00c900c`
- `0x1c00c9074`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00c457d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00c47a8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00c457d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00c47a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00c45e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00c5918`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00c45e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00c5918`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00c46e4`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00c46e4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c00c47f1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c00c5134`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c00c47f1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c00c5134`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00c5025`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00c5233`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00c57bd`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00c5025`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00c5233`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00c57bd`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c00c46a9`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c00c46a9`

## pseudocode

```c

```
