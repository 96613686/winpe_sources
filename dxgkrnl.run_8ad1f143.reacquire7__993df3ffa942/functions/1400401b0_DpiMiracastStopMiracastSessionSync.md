# DpiMiracastStopMiracastSessionSync

- ea: `0x1400401b0`
- end: `0x140040756`
- name: `DpiMiracastStopMiracastSessionSync`
- size: `1446`
- prototype: `__int64 __usercall@<rax>(PVOID P@<rcx>, int, int)`
- caller_count: `7`
- callee_count: `13`
- tags: ``

## callers

- `0x1400407e0`
- `0x1400831c0`
- `0x140085010`
- `0x14019d880`
- `0x140311fe0`
- `0x14035d7c4`
- `0x140366eb0`

## callees

- `0x140022434`
- `0x1400401b0`
- `0x140040908`
- `0x14004094c`
- `0x140061b18`
- `0x1400836a4`
- `0x1400851c0`
- `0x140085298`
- `0x1400a0bd0`
- `0x1402b9380`
- `0x1402b9f08`
- `0x140365a4c`
- `0x140367720`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14004025b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004025b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140040659`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140040659`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140040281`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140040281`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004064d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004064d`
- `ntoskrnl!ObfDereferenceObject` at `0x140040463`
- `ntoskrnl!ObfDereferenceObject` at `0x140040720`
- `ntoskrnl!ObfDereferenceObject` at `0x140040463`
- `ntoskrnl!ObfDereferenceObject` at `0x140040720`
- `ntoskrnl!KeDelayExecutionThread` at `0x140040518`
- `ntoskrnl!KeDelayExecutionThread` at `0x140040518`
- `ntoskrnl!KeClearEvent` at `0x140040301`
- `ntoskrnl!KeClearEvent` at `0x14004047d`
- `ntoskrnl!KeClearEvent` at `0x140040491`
- `ntoskrnl!KeClearEvent` at `0x140040301`
- `ntoskrnl!KeClearEvent` at `0x14004047d`
- `ntoskrnl!KeClearEvent` at `0x140040491`
- `ntoskrnl!KeSetEvent` at `0x140040450`
- `ntoskrnl!KeSetEvent` at `0x1400404d5`
- `ntoskrnl!KeSetEvent` at `0x140040711`
- `ntoskrnl!KeSetEvent` at `0x140040450`
- `ntoskrnl!KeSetEvent` at `0x1400404d5`
- `ntoskrnl!KeSetEvent` at `0x140040711`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400406a2`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400406a2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400404ec`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400404ec`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400404b8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400404b8`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140040294`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140040294`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140040628`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140040628`
- `ntoskrnl!IoCancelIrp` at `0x140040355`
- `ntoskrnl!IoCancelIrp` at `0x140040355`
- `watchdog!WdLogSingleEntry2` at `0x14004032e`
- `watchdog!WdLogSingleEntry2` at `0x14004032e`
- `watchdog!WdLogSingleEntry1` at `0x140040235`
- `watchdog!WdLogSingleEntry1` at `0x1400402d2`
- `watchdog!WdLogSingleEntry1` at `0x140040585`
- `watchdog!WdLogSingleEntry1` at `0x1400406d9`
- `watchdog!WdLogSingleEntry1` at `0x140040235`
- `watchdog!WdLogSingleEntry1` at `0x1400402d2`
- `watchdog!WdLogSingleEntry1` at `0x140040585`
- `watchdog!WdLogSingleEntry1` at `0x1400406d9`

## pseudocode

```c

```
