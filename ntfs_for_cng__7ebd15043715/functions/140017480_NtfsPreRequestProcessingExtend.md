# NtfsPreRequestProcessingExtend

- ea: `0x140017480`
- end: `0x1400177c0`
- name: `NtfsPreRequestProcessingExtend`
- size: `832`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `23`
- callee_count: `25`
- tags: ``

## callers

- `0x140015540`
- `0x140015d10`
- `0x140016850`
- `0x1400b96a0`
- `0x1400e0080`
- `0x14013a200`
- `0x14013af10`
- `0x14017b350`
- `0x1401a1dc0`
- `0x1401a75e0`
- `0x1401bbd30`
- `0x1401c3320`
- `0x1401d8340`
- `0x1401dc5e8`
- `0x1401f5420`
- `0x140201f40`
- `0x140218400`
- `0x14021c370`
- `0x14021e68c`
- `0x1402502b0`
- `0x14026de20`
- `0x140270f00`
- `0x140288508`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x14000c290`
- `0x14000cb00`
- `0x140010be0`
- `0x140012e70`
- `0x140017480`
- `0x14001c8c0`
- `0x140020de0`
- `0x140033030`
- `0x140052a6c`
- `0x140055170`
- `0x1400cc568`
- `0x1400f9d48`
- `0x140113364`
- `0x140188028`
- `0x140188ce4`
- `0x14018aca8`
- `0x14018dc4c`
- `0x140192470`
- `0x140196e30`
- `0x1401982b0`
- `0x1401aab20`
- `0x1401d5ad0`
- `0x140201468`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14005a37d`
- `ntoskrnl!ObfDereferenceObject` at `0x14005e7ad`
- `ntoskrnl!ObfDereferenceObject` at `0x14005a37d`
- `ntoskrnl!ObfDereferenceObject` at `0x14005e7ad`
- `ntoskrnl!FsRtlCancellableWaitForSingleObject` at `0x14005ea2d`
- `ntoskrnl!FsRtlCancellableWaitForSingleObject` at `0x14005ede8`
- `ntoskrnl!FsRtlCancellableWaitForSingleObject` at `0x14005ea2d`
- `ntoskrnl!FsRtlCancellableWaitForSingleObject` at `0x14005ede8`
- `ntoskrnl!IoCancelIrp` at `0x14005ebea`
- `ntoskrnl!IoCancelIrp` at `0x14005ebea`
- `ntoskrnl!FsRtlCurrentOplock` at `0x14005ed17`
- `ntoskrnl!FsRtlCurrentOplock` at `0x14005ed17`
- `ntoskrnl!FsRtlOplockBreakToNoneEx` at `0x14005edb7`
- `ntoskrnl!FsRtlOplockBreakToNoneEx` at `0x14005edb7`
- `ntoskrnl!KeClearEvent` at `0x14005ed4d`
- `ntoskrnl!KeClearEvent` at `0x14005ed4d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005e54b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005e581`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005e61f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005e7fd`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005ea63`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005e54b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005e581`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005e61f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005e7fd`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005ea63`
- `ntoskrnl!KeInitializeEvent` at `0x14005ead9`
- `ntoskrnl!KeInitializeEvent` at `0x14005ead9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a419`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ee80`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a419`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ee80`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005eabd`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005eabd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005e71b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005e85d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005e71b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005e85d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005a33e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005a3b9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e76c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e8ab`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e9d3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005a33e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005a3b9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e76c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e8ab`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e9d3`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140017566`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140017566`
- `ntoskrnl!KeDelayExecutionThread` at `0x14001776c`
- `ntoskrnl!KeDelayExecutionThread` at `0x14001776c`
- `ntoskrnl!ExRaiseStatus` at `0x140017754`
- `ntoskrnl!ExRaiseStatus` at `0x140017754`

## pseudocode

```c

```
