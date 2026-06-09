# ndisCreateNotifyQueue(_NDIS_MINIPORT_BLOCK *,_NDIS_OPEN_BLOCK *,CO_ADDRESS_FAMILY *,_NDIS_AF_NOTIFY * *)

- ea: `0x14017cc80`
- end: `0x14017cfa0`
- name: `?ndisCreateNotifyQueue@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_OPEN_BLOCK@@PEAUCO_ADDRESS_FAMILY@@PEAPEAU_NDIS_AF_NOTIFY@@@Z`
- size: `800`
- prototype: `__int64 __fastcall(struct _NDIS_MINIPORT_BLOCK *, struct _NDIS_OPEN_BLOCK *, struct CO_ADDRESS_FAMILY *, struct _NDIS_AF_NOTIFY **)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400d5000`
- `0x14017cb20`

## callees

- `0x1400051c0`
- `0x140005840`
- `0x1400100f0`
- `0x14001c6b0`
- `0x14002ab60`
- `0x140069cb0`
- `0x14017cc80`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1401894b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401894b6`
- `ntoskrnl!ExAllocatePool2` at `0x14017cd36`
- `ntoskrnl!ExAllocatePool2` at `0x14017ce8e`
- `ntoskrnl!ExAllocatePool2` at `0x14017cd36`
- `ntoskrnl!ExAllocatePool2` at `0x14017ce8e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14017cd01`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14017ce61`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14017cd01`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14017ce61`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14017cd8c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14017cebe`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14017cf3a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140189492`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14017cd8c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14017cebe`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14017cf3a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140189492`

## pseudocode

```c

```
