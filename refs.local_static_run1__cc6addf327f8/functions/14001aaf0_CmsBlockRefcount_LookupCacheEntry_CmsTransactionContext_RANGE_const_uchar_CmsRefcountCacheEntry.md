# CmsBlockRefcount::LookupCacheEntry(CmsTransactionContext *,_RANGE const *,uchar,CmsRefcountCacheEntry * &)

- ea: `0x14001aaf0`
- end: `0x14001b369`
- name: `?LookupCacheEntry@CmsBlockRefcount@@AEAAJPEAVCmsTransactionContext@@PEBU_RANGE@@EAEAPEAVCmsRefcountCacheEntry@@@Z`
- size: `2169`
- prototype: `__int64 __usercall@<rax>(CmsBlockRefcount *__hidden this@<rcx>, struct CmsTransactionContext *@<rdx>, const struct _RANGE *@<r8>, unsigned __int8@<r9b>, struct CmsRefcountCacheEntry **)`
- caller_count: `4`
- callee_count: `17`
- tags: `authz_impersonation`

## callers

- `0x1400193e0`
- `0x140019c20`
- `0x1400cef20`
- `0x140140f9c`

## callees

- `0x140012c34`
- `0x140012ec0`
- `0x1400147e0`
- `0x140016440`
- `0x1400185d4`
- `0x140018810`
- `0x14001aaf0`
- `0x140076da0`
- `0x140078ce0`
- `0x140095e10`
- `0x14009d210`
- `0x1400cdd00`
- `0x1400d1a90`
- `0x140142524`
- `0x140142588`
- `0x140142720`
- `0x1401f4090`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x14001b1b8`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401f9934`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401f9934`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14001ab7f`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14001ab7f`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x14001ac47`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1401f9a2d`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x14001ac47`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1401f9a2d`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x14001ad6a`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1401f99ff`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1401f9ac6`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x14001ad6a`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1401f99ff`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1401f9ac6`
- `ntoskrnl!ExReleasePushLockEx` at `0x14001abbc`
- `ntoskrnl!ExReleasePushLockEx` at `0x14001ad84`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401f9921`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401f9adb`
- `ntoskrnl!ExReleasePushLockEx` at `0x14001abbc`
- `ntoskrnl!ExReleasePushLockEx` at `0x14001ad84`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401f9921`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401f9adb`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001ac21`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001ac21`

## pseudocode

```c

```
