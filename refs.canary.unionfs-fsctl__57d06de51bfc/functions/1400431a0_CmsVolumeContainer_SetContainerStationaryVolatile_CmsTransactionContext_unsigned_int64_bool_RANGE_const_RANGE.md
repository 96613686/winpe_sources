# CmsVolumeContainer::SetContainerStationaryVolatile(CmsTransactionContext *,unsigned __int64,bool,_RANGE const *,_RANGE *)

- ea: `0x1400431a0`
- end: `0x140043506`
- name: `?SetContainerStationaryVolatile@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@_K_NPEBU_RANGE@@PEAU3@@Z`
- size: `870`
- prototype: `__int64 __usercall@<rax>(CmsVolumeContainer *__hidden this@<rcx>, struct CmsTransactionContext *@<rdx>, unsigned __int64@<r8>, bool@<r9b>, const struct _RANGE *, struct _RANGE *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1400243f8`
- `0x140056890`

## callees

- `0x1400431a0`
- `0x140043e80`
- `0x140045910`
- `0x14008e900`
- `0x1400ad8bc`
- `0x14013651c`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401f29bc`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401f29bc`
- `ntoskrnl!ExAllocatePool2` at `0x1401f29f8`
- `ntoskrnl!ExAllocatePool2` at `0x1401f29f8`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x140043360`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x140043360`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x140043395`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x140043395`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14004337e`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14004337e`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14004331a`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14004331a`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400432f3`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400432f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400434be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400434e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400434be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400434e8`

## pseudocode

```c

```
