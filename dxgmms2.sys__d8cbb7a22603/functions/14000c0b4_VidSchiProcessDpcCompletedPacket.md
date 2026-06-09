# VidSchiProcessDpcCompletedPacket

- ea: `0x14000c0b4`
- end: `0x14000c9e9`
- name: `VidSchiProcessDpcCompletedPacket`
- size: `2357`
- prototype: `__int64 __fastcall(struct _VIDSCH_DMA_PACKET *)`
- caller_count: `1`
- callee_count: `30`
- tags: `broker_com_uri`

## callers

- `0x140020478`

## callees

- `0x140004268`
- `0x14000a3b4`
- `0x14000a488`
- `0x14000a768`
- `0x14000b9e0`
- `0x14000c0b4`
- `0x14000c9f0`
- `0x14000cb6c`
- `0x14000cc58`
- `0x14000cdc4`
- `0x14000e840`
- `0x140010200`
- `0x1400119e0`
- `0x1400157e8`
- `0x140017750`
- `0x1400190ac`
- `0x14001ac74`
- `0x14001b3a4`
- `0x14001bc80`
- `0x14001e5d8`
- `0x14001e670`
- `0x14001ef8c`
- `0x140020edc`
- `0x14002dbd0`
- `0x140033090`
- `0x14003bd44`
- `0x140044ea8`
- `0x14004e588`
- `0x14004e984`
- `0x140059380`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000c150`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000c150`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000c3cc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000c3cc`
- `ntoskrnl!ExQueueWorkItem` at `0x14000c5d7`
- `ntoskrnl!ExQueueWorkItem` at `0x14000c5d7`
- `ntoskrnl!RtlSetBitEx` at `0x14000c5f3`
- `ntoskrnl!RtlSetBitEx` at `0x14000c5f3`
- `ntoskrnl!KeSetEvent` at `0x14000c450`
- `ntoskrnl!KeSetEvent` at `0x14000c472`
- `ntoskrnl!KeSetEvent` at `0x14000c494`
- `ntoskrnl!KeSetEvent` at `0x14000c69e`
- `ntoskrnl!KeSetEvent` at `0x14000c9d8`
- `ntoskrnl!KeSetEvent` at `0x14000c450`
- `ntoskrnl!KeSetEvent` at `0x14000c472`
- `ntoskrnl!KeSetEvent` at `0x14000c494`
- `ntoskrnl!KeSetEvent` at `0x14000c69e`
- `ntoskrnl!KeSetEvent` at `0x14000c9d8`
- `watchdog!WdLogSingleEntry2` at `0x14000c706`
- `watchdog!WdLogSingleEntry2` at `0x14000c706`
- `HAL!KeQueryPerformanceCounter` at `0x14000c18e`
- `HAL!KeQueryPerformanceCounter` at `0x14000c1ec`
- `HAL!KeQueryPerformanceCounter` at `0x14000c18e`
- `HAL!KeQueryPerformanceCounter` at `0x14000c1ec`

## pseudocode

```c

```
