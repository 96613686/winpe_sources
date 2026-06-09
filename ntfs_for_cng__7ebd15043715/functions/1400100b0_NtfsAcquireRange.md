# NtfsAcquireRange

- ea: `0x1400100b0`
- end: `0x1400105cc`
- name: `NtfsAcquireRange`
- size: `1308`
- prototype: `char __fastcall(__int64, __int64, __int64, __int64, char, __int64)`
- caller_count: `8`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x14000f02c`
- `0x14001d13c`
- `0x1400cc78c`
- `0x1401771e0`
- `0x14021ebd0`
- `0x1402336bc`
- `0x140234fd0`
- `0x1402447d0`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x1400100b0`
- `0x1400105d4`
- `0x140010670`
- `0x14001072c`
- `0x140010788`
- `0x140010858`
- `0x140036d14`
- `0x140038e9c`
- `0x140059250`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400101d5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140010318`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400101d5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140010318`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400101b7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001029e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400102fe`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001036d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400104a1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001054e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400101b7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001029e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400102fe`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001036d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400104a1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001054e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400101f2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400102d5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140010348`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001052c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005db3e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400101f2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400102d5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140010348`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001052c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005db3e`

## pseudocode

```c

```
