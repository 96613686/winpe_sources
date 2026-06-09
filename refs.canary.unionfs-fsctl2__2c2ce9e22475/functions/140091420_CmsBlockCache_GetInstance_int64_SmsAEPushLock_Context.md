# CmsBlockCache::GetInstance(__int64,SmsAEPushLock::Context &)

- ea: `0x140091420`
- end: `0x140091677`
- name: `?GetInstance@CmsBlockCache@@AEAAPEAU_SmsCacheInstance@@_JAEAUContext@SmsAEPushLock@@@Z`
- size: `599`
- prototype: `struct _SmsCacheInstance *__fastcall(CmsBlockCache *__hidden this, __int64, struct SmsAEPushLock::Context *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400596e0`

## callees

- `0x140091420`
- `0x1400b06ac`
- `0x1401e9e40`
- `0x1401ea140`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140091543`
- `ntoskrnl!ExAllocatePool2` at `0x1400915b8`
- `ntoskrnl!ExAllocatePool2` at `0x140091543`
- `ntoskrnl!ExAllocatePool2` at `0x1400915b8`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x140091468`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x140091468`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1400914c1`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x140091664`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1400914c1`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x140091664`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1400914e1`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1400914e1`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x140091507`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x140091614`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x14009164e`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x140091507`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x140091614`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x14009164e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140091627`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f9576`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f9598`
- `ntoskrnl!ExFreePoolWithTag` at `0x140091627`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f9576`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f9598`

## pseudocode

```c

```
