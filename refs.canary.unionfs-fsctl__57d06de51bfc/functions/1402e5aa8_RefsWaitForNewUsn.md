# RefsWaitForNewUsn

- ea: `0x1402e5aa8`
- end: `0x1402e5fb8`
- name: `RefsWaitForNewUsn`
- size: `1296`
- prototype: `__int64 __fastcall(int, int, int, int, char, struct _IRP *, PLARGE_INTEGER, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1402e5fc0`

## callees

- `0x14008dbd0`
- `0x14009db50`
- `0x1400abbf4`
- `0x1400c8644`
- `0x1400ca788`
- `0x1401ea140`
- `0x1402e5aa8`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1402e5cce`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402e5e67`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402e5cce`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402e5e67`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402e5c53`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402e5d99`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402e5c53`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402e5d99`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402e5c96`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402e5c96`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e5ba6`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e5e98`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e5ba6`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e5e98`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e5bbc`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e5ea7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e5bbc`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e5ea7`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e5c0d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e5ee0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e5f09`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e5c0d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e5ee0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e5f09`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e5c19`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e5eec`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e5f15`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e5c19`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e5eec`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e5f15`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402e5c7f`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402e5c7f`
- `ntoskrnl!KeInitializeEvent` at `0x1402e5b83`
- `ntoskrnl!KeInitializeEvent` at `0x1402e5b83`
- `ntoskrnl!ExReleaseFastResource` at `0x1402e5c47`
- `ntoskrnl!ExReleaseFastResource` at `0x1402e5d8d`
- `ntoskrnl!ExReleaseFastResource` at `0x1402e5c47`
- `ntoskrnl!ExReleaseFastResource` at `0x1402e5d8d`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x1402e5cec`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x1402e5e86`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x1402e5cec`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x1402e5e86`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402e5f26`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402e5f98`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402e5f26`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402e5f98`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402e5add`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402e5add`

## pseudocode

```c

```
