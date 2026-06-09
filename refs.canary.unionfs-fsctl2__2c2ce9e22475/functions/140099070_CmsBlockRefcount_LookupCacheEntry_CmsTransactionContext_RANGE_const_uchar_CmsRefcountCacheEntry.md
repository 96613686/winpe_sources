# CmsBlockRefcount::LookupCacheEntry(CmsTransactionContext *,_RANGE const *,uchar,CmsRefcountCacheEntry * &)

- ea: `0x140099070`
- end: `0x1400994cb`
- name: `?LookupCacheEntry@CmsBlockRefcount@@AEAAJPEAVCmsTransactionContext@@PEBU_RANGE@@EAEAPEAVCmsRefcountCacheEntry@@@Z`
- size: `1115`
- prototype: `__int64 __usercall@<rax>(CmsBlockRefcount *__hidden this@<rcx>, struct CmsTransactionContext *@<rdx>, const struct _RANGE *@<r8>, unsigned __int8@<r9b>, struct CmsRefcountCacheEntry **)`
- caller_count: `3`
- callee_count: `17`
- tags: `authz_impersonation`

## callers

- `0x140043790`
- `0x1400c8778`
- `0x14013b408`

## callees

- `0x140023ac0`
- `0x14003234c`
- `0x1400325d0`
- `0x140034ab0`
- `0x140036df0`
- `0x140081940`
- `0x140099070`
- `0x14009ac80`
- `0x1400a2ab0`
- `0x1400a3600`
- `0x1400a3840`
- `0x1400c6fd0`
- `0x1400cb474`
- `0x14013c800`
- `0x14013c864`
- `0x14013c9f0`
- `0x1401e9dc0`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x140099426`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401f9f5c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401f9f5c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400990fd`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400990fd`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1400991c5`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1401fa04c`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1400991c5`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1401fa04c`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1400992db`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1401fa01e`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1401fa0c1`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1400992db`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1401fa01e`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1401fa0c1`
- `ntoskrnl!ExReleasePushLockEx` at `0x14009913a`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400992f5`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401f9f49`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401fa0d6`
- `ntoskrnl!ExReleasePushLockEx` at `0x14009913a`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400992f5`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401f9f49`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401fa0d6`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14009919f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14009919f`

## pseudocode

```c

```
