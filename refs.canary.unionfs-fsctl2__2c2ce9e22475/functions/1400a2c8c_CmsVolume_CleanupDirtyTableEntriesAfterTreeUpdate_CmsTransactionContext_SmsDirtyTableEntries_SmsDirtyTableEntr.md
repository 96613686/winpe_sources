# CmsVolume::CleanupDirtyTableEntriesAfterTreeUpdate(CmsTransactionContext *,SmsDirtyTableEntries *,SmsDirtyTableEntries *,long,uchar)

- ea: `0x1400a2c8c`
- end: `0x1400a316e`
- name: `?CleanupDirtyTableEntriesAfterTreeUpdate@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAUSmsDirtyTableEntries@@1JE@Z`
- size: `1250`
- prototype: `void(CmsVolume *__hidden this, struct CmsTransactionContext *, struct SmsDirtyTableEntries *, struct SmsDirtyTableEntries *, int, unsigned __int8)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x14013ff9c`

## callees

- `0x140036df0`
- `0x140037c90`
- `0x140038f20`
- `0x1400710d0`
- `0x140094430`
- `0x1400a2c8c`
- `0x1401e9ce0`
- `0x1401e9dc0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400a3148`
- `ntoskrnl!KeSetEvent` at `0x1400a3148`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400a2cdf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400a2cdf`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400a2d98`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400a2dd2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400a2d98`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400a2dd2`
- `ntoskrnl!KeClearEvent` at `0x1400a2d60`
- `ntoskrnl!KeClearEvent` at `0x1400a2d60`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400a3015`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400a315d`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400a3015`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400a315d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a30d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a30d8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400a2fda`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400a312e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400a2fda`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400a312e`

## pseudocode

```c

```
