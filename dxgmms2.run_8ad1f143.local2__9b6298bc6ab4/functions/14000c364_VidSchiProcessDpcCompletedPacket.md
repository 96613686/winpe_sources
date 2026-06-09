# VidSchiProcessDpcCompletedPacket

- ea: `0x14000c364`
- end: `0x14000cc99`
- name: `VidSchiProcessDpcCompletedPacket`
- size: `2357`
- prototype: `__int64 __fastcall(struct _VIDSCH_DMA_PACKET *)`
- caller_count: `1`
- callee_count: `30`
- tags: `broker_com_uri`

## callers

- `0x140023398`

## callees

- `0x1400045ec`
- `0x14000a724`
- `0x14000a7f8`
- `0x14000aa18`
- `0x14000bc90`
- `0x14000c364`
- `0x14000cca0`
- `0x14000ce1c`
- `0x14000cf08`
- `0x14000d074`
- `0x14000eda0`
- `0x140010760`
- `0x140011f40`
- `0x140016b74`
- `0x140017380`
- `0x14001978c`
- `0x14001b354`
- `0x14001ba84`
- `0x14001c360`
- `0x14001ca80`
- `0x140020138`
- `0x1400201d0`
- `0x140020aec`
- `0x140023dfc`
- `0x1400347a0`
- `0x14003d034`
- `0x140044ca4`
- `0x14004de78`
- `0x14004e274`
- `0x140058ac0`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000c400`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000c400`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000c67c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000c67c`
- `ntoskrnl!ExQueueWorkItem` at `0x14000c887`
- `ntoskrnl!ExQueueWorkItem` at `0x14000c887`
- `ntoskrnl!RtlSetBitEx` at `0x14000c8a3`
- `ntoskrnl!RtlSetBitEx` at `0x14000c8a3`
- `ntoskrnl!KeSetEvent` at `0x14000c700`
- `ntoskrnl!KeSetEvent` at `0x14000c722`
- `ntoskrnl!KeSetEvent` at `0x14000c744`
- `ntoskrnl!KeSetEvent` at `0x14000c94e`
- `ntoskrnl!KeSetEvent` at `0x14000cc88`
- `ntoskrnl!KeSetEvent` at `0x14000c700`
- `ntoskrnl!KeSetEvent` at `0x14000c722`
- `ntoskrnl!KeSetEvent` at `0x14000c744`
- `ntoskrnl!KeSetEvent` at `0x14000c94e`
- `ntoskrnl!KeSetEvent` at `0x14000cc88`
- `watchdog!WdLogSingleEntry2` at `0x14000c9b6`
- `watchdog!WdLogSingleEntry2` at `0x14000c9b6`
- `HAL!KeQueryPerformanceCounter` at `0x14000c43e`
- `HAL!KeQueryPerformanceCounter` at `0x14000c49c`
- `HAL!KeQueryPerformanceCounter` at `0x14000c43e`
- `HAL!KeQueryPerformanceCounter` at `0x14000c49c`

## pseudocode

```c

```
