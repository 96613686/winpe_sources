# ndisSignalD0RequestComplete(_NDIS_MINIPORT_BLOCK *,long)

- ea: `0x1400452c0`
- end: `0x14004540b`
- name: `?ndisSignalD0RequestComplete@@YAXPEAU_NDIS_MINIPORT_BLOCK@@J@Z`
- size: `331`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *, int)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400abad0`
- `0x1400b2f5c`
- `0x1400c7d70`
- `0x140180470`

## callees

- `0x14003d6e0`
- `0x140045020`
- `0x1400452c0`
- `0x140045420`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400453be`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400453be`
- `ntoskrnl!KeSetEvent` at `0x140045374`
- `ntoskrnl!KeSetEvent` at `0x140045374`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004530b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004530b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400452d2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400452d2`

## pseudocode

```c

```
