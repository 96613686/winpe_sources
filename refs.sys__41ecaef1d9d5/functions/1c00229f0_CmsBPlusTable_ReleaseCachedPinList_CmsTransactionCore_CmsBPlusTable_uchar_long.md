# CmsBPlusTable::ReleaseCachedPinList(CmsTransactionCore *,CmsBPlusTable *,uchar,long)

- ea: `0x1c00229f0`
- end: `0x1c0022dfd`
- name: `?ReleaseCachedPinList@CmsBPlusTable@@QEAAXPEAVCmsTransactionCore@@PEAV1@EJ@Z`
- size: `1037`
- prototype: `void __fastcall(CmsBPlusTable *__hidden this, struct CmsTransactionCore *, struct CmsBPlusTable *, unsigned __int8, int)`
- caller_count: `12`
- callee_count: `7`
- tags: ``

## callers

- `0x1c0020fe0`
- `0x1c0021950`
- `0x1c00229f0`
- `0x1c0031520`
- `0x1c0046d20`
- `0x1c0047f38`
- `0x1c0060ba0`
- `0x1c00caea4`
- `0x1c00cb0b8`
- `0x1c00cdec4`
- `0x1c00ee870`
- `0x1c00eecb0`

## callees

- `0x1c000384c`
- `0x1c00229f0`
- `0x1c0030d28`
- `0x1c0030ebc`
- `0x1c00400c4`
- `0x1c00424b4`
- `0x1c006ac80`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0022b8e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0022b8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0022d32`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c007964c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0022d32`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c007964c`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0022bbb`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00796da`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0022bbb`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00796da`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c0022ce9`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c0079632`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c00796ad`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c0022ce9`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c0079632`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c00796ad`
- `ntoskrnl!ExQueryDepthSList` at `0x1c0022ccc`
- `ntoskrnl!ExQueryDepthSList` at `0x1c0022ccc`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1c0022aac`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1c0022aac`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1c0022c00`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1c0022c00`
- `ntoskrnl!ExTryAcquirePushLockSharedEx` at `0x1c00795c4`
- `ntoskrnl!ExTryAcquirePushLockSharedEx` at `0x1c00795c4`

## pseudocode

```c

```
