# ndisSignalD0RequestComplete(_NDIS_MINIPORT_BLOCK *,long)

- ea: `0x1400423f0`
- end: `0x14004253b`
- name: `?ndisSignalD0RequestComplete@@YAXPEAU_NDIS_MINIPORT_BLOCK@@J@Z`
- size: `331`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *, int)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400a6690`
- `0x1400adb1c`
- `0x1400c2b90`
- `0x14017a4a0`

## callees

- `0x140012a70`
- `0x140042150`
- `0x1400423f0`
- `0x140042550`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400424ee`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400424ee`
- `ntoskrnl!KeSetEvent` at `0x1400424a4`
- `ntoskrnl!KeSetEvent` at `0x1400424a4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004243b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004243b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140042402`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140042402`

## pseudocode

```c

```
