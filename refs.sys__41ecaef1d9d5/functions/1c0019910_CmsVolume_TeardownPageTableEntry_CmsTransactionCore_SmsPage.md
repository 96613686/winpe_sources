# CmsVolume::TeardownPageTableEntry(CmsTransactionCore *,SmsPage *)

- ea: `0x1c0019910`
- end: `0x1c0019b4f`
- name: `?TeardownPageTableEntry@CmsVolume@@AEAAXPEAVCmsTransactionCore@@PEAUSmsPage@@@Z`
- size: `575`
- prototype: `void(CmsVolume *__hidden this, struct CmsTransactionCore *, struct SmsPage *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x1c0017a30`
- `0x1c0019580`
- `0x1c001d31c`

## callees

- `0x1c000384c`
- `0x1c0019910`
- `0x1c0036a10`
- `0x1c0044070`
- `0x1c005b468`
- `0x1c006ac80`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00763da`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00763da`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0019b41`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c007649a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0019b41`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c007649a`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0076445`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0076445`
- `ntoskrnl!KeSetEvent` at `0x1c0076428`
- `ntoskrnl!KeSetEvent` at `0x1c0076428`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c0019ac3`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c0076480`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c0019ac3`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c0076480`
- `ntoskrnl!ExQueryDepthSList` at `0x1c0019aaa`
- `ntoskrnl!ExQueryDepthSList` at `0x1c0019aaa`
- `ntoskrnl!ExDeleteResourceLite` at `0x1c0019981`
- `ntoskrnl!ExDeleteResourceLite` at `0x1c0019981`
- `ntoskrnl!KdDebuggerEnabled` at `0x1c0019941`

## pseudocode

```c

```
