# VidSchiSubmitQueueCommandDirect

- ea: `0x14005092c`
- end: `0x140050b79`
- name: `VidSchiSubmitQueueCommandDirect`
- size: `589`
- prototype: `__int64 __fastcall(struct _VIDSCH_QUEUE_PACKET *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140050728`

## callees

- `0x14000daac`
- `0x14000ebd0`
- `0x140010760`
- `0x1400121c0`
- `0x140022d28`
- `0x14002ee50`
- `0x140040438`
- `0x14005092c`
- `0x140058760`
- `0x1400dd830`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140050970`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140050970`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140050a5c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140050a5c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140050b08`
- `ntoskrnl!ExReleaseResourceLite` at `0x140050b08`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x1400509f0`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x1400509f0`

## pseudocode

```c

```
