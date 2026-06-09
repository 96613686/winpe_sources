# NdisMIdleNotificationCompleteEx

- ea: `0x140071960`
- end: `0x140071a7f`
- name: `NdisMIdleNotificationCompleteEx`
- size: `287`
- prototype: `__int64 __fastcall(struct _NDIS_MINIPORT_BLOCK *, char)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140071940`

## callees

- `0x140014850`
- `0x14001cc80`
- `0x14001d030`
- `0x14006d890`
- `0x140071960`
- `0x1400c216c`
- `0x1400c253c`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400719ea`
- `ntoskrnl!KeSetEvent` at `0x1400719ea`
- `ntoskrnl!KeReleaseSpinLock` at `0x140071a13`
- `ntoskrnl!KeReleaseSpinLock` at `0x140071a3f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140071a55`
- `ntoskrnl!KeReleaseSpinLock` at `0x140071a13`
- `ntoskrnl!KeReleaseSpinLock` at `0x140071a3f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140071a55`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140071978`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140071978`

## pseudocode

```c

```
