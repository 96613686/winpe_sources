# ndisReferenceNextUnprocessedOpenEx(_NDIS_MINIPORT_BLOCK *,uchar)

- ea: `0x14005bb90`
- end: `0x14005bd33`
- name: `?ndisReferenceNextUnprocessedOpenEx@@YAPEAU_NDIS_OPEN_BLOCK@@PEAU_NDIS_MINIPORT_BLOCK@@E@Z`
- size: `419`
- prototype: `struct _NDIS_OPEN_BLOCK *__fastcall(struct _NDIS_MINIPORT_BLOCK *, unsigned __int8)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14017bb40`

## callees

- `0x1400100f0`
- `0x140011190`
- `0x14005bb90`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14005bc85`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005bc85`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005bbca`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005bbca`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14005bbff`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14005bbff`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14005bc39`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14005bc66`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14005bc39`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14005bc66`

## pseudocode

```c

```
