# PerformLockedOperation

- ea: `0x180008114`
- end: `0x1800082bf`
- name: `PerformLockedOperation`
- size: `427`
- prototype: `BOOLEAN __fastcall(int, struct _KMUTANT *, KSYNCHRONIZE_ROUTINE *, void *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180012080`
- `0x180049c20`
- `0x18004b268`
- `0x180051ba8`
- `0x180058f80`
- `0x180060a50`

## callees

- `0x180008114`
- `0x180019cb0`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1800081fd`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1800081fd`
- `ntoskrnl!ExReleaseFastMutex` at `0x180008257`
- `ntoskrnl!ExReleaseFastMutex` at `0x180008257`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180008198`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800081ee`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180008198`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800081ee`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800081a9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800081a9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800081c6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800081c6`
- `ntoskrnl!ExAcquireFastMutex` at `0x18000823a`
- `ntoskrnl!ExAcquireFastMutex` at `0x18000823a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x18000821a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x18000821a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008226`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008226`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000813b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000813b`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000815c`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000815c`
- `ntoskrnl!KeSynchronizeExecution` at `0x1800081dd`
- `ntoskrnl!KeSynchronizeExecution` at `0x1800081dd`
- `ntoskrnl!KeReleaseMutex` at `0x18000829b`
- `ntoskrnl!KeReleaseMutex` at `0x18000829b`
- `ntoskrnl!KeWaitForSingleObject` at `0x18000827c`
- `ntoskrnl!KeWaitForSingleObject` at `0x18000827c`

## pseudocode

```c

```
