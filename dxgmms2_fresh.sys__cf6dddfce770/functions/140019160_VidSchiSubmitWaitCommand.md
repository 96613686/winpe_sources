# VidSchiSubmitWaitCommand

- ea: `0x140019160`
- end: `0x1400196ca`
- name: `VidSchiSubmitWaitCommand`
- size: `1386`
- prototype: `__int64 *__fastcall(struct _VIDSCH_QUEUE_PACKET *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400e5a50`
- `0x1400e5c90`

## callees

- `0x14000bd28`
- `0x14000be28`
- `0x14000e840`
- `0x140017930`
- `0x140019160`
- `0x140019b80`
- `0x14001ac74`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001919b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001919b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400192dc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400192dc`
- `ntoskrnl!KeSetEvent` at `0x140019549`
- `ntoskrnl!KeSetEvent` at `0x140019667`
- `ntoskrnl!KeSetEvent` at `0x140019549`
- `ntoskrnl!KeSetEvent` at `0x140019667`
- `watchdog!WdLogSingleEntry3` at `0x14001924b`
- `watchdog!WdLogSingleEntry3` at `0x14001924b`

## pseudocode

```c

```
