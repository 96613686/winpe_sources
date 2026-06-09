# NdisMIdleNotificationCompleteEx

- ea: `0x1400773b0`
- end: `0x1400774cf`
- name: `NdisMIdleNotificationCompleteEx`
- size: `287`
- prototype: `__int64 __fastcall(struct _NDIS_MINIPORT_BLOCK *, char)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140077390`

## callees

- `0x140010d20`
- `0x140011190`
- `0x14003dec0`
- `0x140073210`
- `0x1400773b0`
- `0x1400c759c`
- `0x1400c796c`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14007743a`
- `ntoskrnl!KeSetEvent` at `0x14007743a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140077463`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007748f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400774a5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140077463`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007748f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400774a5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400773c8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400773c8`

## pseudocode

```c

```
