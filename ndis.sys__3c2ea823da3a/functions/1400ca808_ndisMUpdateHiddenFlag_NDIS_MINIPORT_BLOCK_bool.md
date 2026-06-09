# ndisMUpdateHiddenFlag(_NDIS_MINIPORT_BLOCK *,bool)

- ea: `0x1400ca808`
- end: `0x1400ca961`
- name: `?ndisMUpdateHiddenFlag@@YAXPEAU_NDIS_MINIPORT_BLOCK@@_N@Z`
- size: `345`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *, bool)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x14005d470`
- `0x140147e88`
- `0x14017f260`

## callees

- `0x140015280`
- `0x1400230c0`
- `0x140025da0`
- `0x1400837ac`
- `0x1400ca808`
- `0x1401685c0`

## import_xrefs

- `ntoskrnl!IoInvalidateDeviceState` at `0x1400ca947`
- `ntoskrnl!IoInvalidateDeviceState` at `0x1400ca947`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ca868`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ca8d5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ca923`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ca868`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ca8d5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ca923`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400ca87b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400ca8f3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400ca87b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400ca8f3`

## pseudocode

```c

```
