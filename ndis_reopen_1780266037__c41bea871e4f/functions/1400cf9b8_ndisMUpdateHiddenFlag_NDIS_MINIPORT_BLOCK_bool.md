# ndisMUpdateHiddenFlag(_NDIS_MINIPORT_BLOCK *,bool)

- ea: `0x1400cf9b8`
- end: `0x1400cfb11`
- name: `?ndisMUpdateHiddenFlag@@YAXPEAU_NDIS_MINIPORT_BLOCK@@_N@Z`
- size: `345`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *, bool)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140061940`
- `0x14014ee28`
- `0x140185810`

## callees

- `0x140009320`
- `0x140017220`
- `0x140019f00`
- `0x140088a2c`
- `0x1400cf9b8`
- `0x14016f4b0`

## import_xrefs

- `ntoskrnl!IoInvalidateDeviceState` at `0x1400cfaf7`
- `ntoskrnl!IoInvalidateDeviceState` at `0x1400cfaf7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cfa18`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cfa85`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cfad3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cfa18`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cfa85`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cfad3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cfa2b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cfaa3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cfa2b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cfaa3`

## pseudocode

```c

```
