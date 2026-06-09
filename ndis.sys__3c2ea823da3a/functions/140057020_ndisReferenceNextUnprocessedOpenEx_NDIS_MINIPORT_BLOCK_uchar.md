# ndisReferenceNextUnprocessedOpenEx(_NDIS_MINIPORT_BLOCK *,uchar)

- ea: `0x140057020`
- end: `0x1400571c3`
- name: `?ndisReferenceNextUnprocessedOpenEx@@YAPEAU_NDIS_OPEN_BLOCK@@PEAU_NDIS_MINIPORT_BLOCK@@E@Z`
- size: `419`
- prototype: `struct _NDIS_OPEN_BLOCK *__fastcall(struct _NDIS_MINIPORT_BLOCK *, unsigned __int8)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140175b70`

## callees

- `0x14001c050`
- `0x14001d030`
- `0x140057020`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140057115`
- `ntoskrnl!KeReleaseSpinLock` at `0x140057115`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005705a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005705a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400570c9`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400570f6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400570c9`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400570f6`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14005708f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14005708f`

## pseudocode

```c

```
