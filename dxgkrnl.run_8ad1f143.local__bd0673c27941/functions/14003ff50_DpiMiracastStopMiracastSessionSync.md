# DpiMiracastStopMiracastSessionSync

- ea: `0x14003ff50`
- end: `0x1400404f6`
- name: `DpiMiracastStopMiracastSessionSync`
- size: `1446`
- prototype: `__int64 __usercall@<rax>(PVOID P@<rcx>, int, int)`
- caller_count: `7`
- callee_count: `13`
- tags: ``

## callers

- `0x140040580`
- `0x1400827f0`
- `0x140084640`
- `0x140199880`
- `0x14030b270`
- `0x14035d314`
- `0x140366e70`

## callees

- `0x140022264`
- `0x14003ff50`
- `0x1400406a8`
- `0x1400406ec`
- `0x140061768`
- `0x140082cd4`
- `0x1400847f0`
- `0x1400848c8`
- `0x1400a0100`
- `0x1402b29d0`
- `0x1402b3558`
- `0x140365a0c`
- `0x1403676e0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14003fffb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003fffb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400403f9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400403f9`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140040021`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140040021`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400403ed`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400403ed`
- `ntoskrnl!ObfDereferenceObject` at `0x140040203`
- `ntoskrnl!ObfDereferenceObject` at `0x1400404c0`
- `ntoskrnl!ObfDereferenceObject` at `0x140040203`
- `ntoskrnl!ObfDereferenceObject` at `0x1400404c0`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400402b8`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400402b8`
- `ntoskrnl!KeClearEvent` at `0x1400400a1`
- `ntoskrnl!KeClearEvent` at `0x14004021d`
- `ntoskrnl!KeClearEvent` at `0x140040231`
- `ntoskrnl!KeClearEvent` at `0x1400400a1`
- `ntoskrnl!KeClearEvent` at `0x14004021d`
- `ntoskrnl!KeClearEvent` at `0x140040231`
- `ntoskrnl!KeSetEvent` at `0x1400401f0`
- `ntoskrnl!KeSetEvent` at `0x140040275`
- `ntoskrnl!KeSetEvent` at `0x1400404b1`
- `ntoskrnl!KeSetEvent` at `0x1400401f0`
- `ntoskrnl!KeSetEvent` at `0x140040275`
- `ntoskrnl!KeSetEvent` at `0x1400404b1`
- `ntoskrnl!KeWaitForSingleObject` at `0x140040442`
- `ntoskrnl!KeWaitForSingleObject` at `0x140040442`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004028c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004028c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140040258`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140040258`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140040034`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140040034`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1400403c8`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1400403c8`
- `ntoskrnl!IoCancelIrp` at `0x1400400f5`
- `ntoskrnl!IoCancelIrp` at `0x1400400f5`
- `watchdog!WdLogSingleEntry2` at `0x1400400ce`
- `watchdog!WdLogSingleEntry2` at `0x1400400ce`
- `watchdog!WdLogSingleEntry1` at `0x14003ffd5`
- `watchdog!WdLogSingleEntry1` at `0x140040072`
- `watchdog!WdLogSingleEntry1` at `0x140040325`
- `watchdog!WdLogSingleEntry1` at `0x140040479`
- `watchdog!WdLogSingleEntry1` at `0x14003ffd5`
- `watchdog!WdLogSingleEntry1` at `0x140040072`
- `watchdog!WdLogSingleEntry1` at `0x140040325`
- `watchdog!WdLogSingleEntry1` at `0x140040479`

## pseudocode

```c

```
