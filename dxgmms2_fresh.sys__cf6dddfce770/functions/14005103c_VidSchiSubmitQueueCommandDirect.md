# VidSchiSubmitQueueCommandDirect

- ea: `0x14005103c`
- end: `0x140051289`
- name: `VidSchiSubmitQueueCommandDirect`
- size: `589`
- prototype: `__int64 __fastcall(struct _VIDSCH_QUEUE_PACKET *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140050e38`

## callees

- `0x14000d5c0`
- `0x14000e670`
- `0x140010200`
- `0x140011c60`
- `0x14001fe08`
- `0x14002bf10`
- `0x14003edb8`
- `0x14005103c`
- `0x140059030`
- `0x1400e5c90`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140051080`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140051080`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005116c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005116c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140051218`
- `ntoskrnl!ExReleaseResourceLite` at `0x140051218`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x140051100`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x140051100`

## pseudocode

```c

```
