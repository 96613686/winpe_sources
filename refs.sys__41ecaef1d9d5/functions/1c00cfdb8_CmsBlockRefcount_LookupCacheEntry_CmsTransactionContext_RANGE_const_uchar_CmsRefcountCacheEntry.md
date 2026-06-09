# CmsBlockRefcount::LookupCacheEntry(CmsTransactionContext *,_RANGE const *,uchar,CmsRefcountCacheEntry * &)

- ea: `0x1c00cfdb8`
- end: `0x1c00cff96`
- name: `?LookupCacheEntry@CmsBlockRefcount@@AEAAJPEAVCmsTransactionContext@@PEBU_RANGE@@EAEAPEAVCmsRefcountCacheEntry@@@Z`
- size: `478`
- prototype: `__int64 __usercall@<rax>(CmsBlockRefcount *__hidden this@<rcx>, struct CmsTransactionContext *@<rdx>, const struct _RANGE *@<r8>, unsigned __int8@<r9b>, struct CmsRefcountCacheEntry **)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1c0040310`
- `0x1c00cf664`
- `0x1c00cf9c0`

## callees

- `0x1c002313c`
- `0x1c002981c`
- `0x1c0047d84`
- `0x1c00642c4`
- `0x1c0065660`
- `0x1c006ac80`
- `0x1c00cfcb0`
- `0x1c00cfdb8`
- `0x1c00d07c8`
- `0x1c00d1048`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00cfeaa`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00cfeaa`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00cff1d`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00cff52`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00cff1d`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00cff52`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1c00cfebc`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1c00cfebc`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1c00cff08`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1c00cff3d`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1c00cff08`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1c00cff3d`

## pseudocode

```c

```
