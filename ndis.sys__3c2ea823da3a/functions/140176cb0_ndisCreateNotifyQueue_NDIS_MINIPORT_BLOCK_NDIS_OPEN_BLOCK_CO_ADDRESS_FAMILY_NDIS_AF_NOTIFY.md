# ndisCreateNotifyQueue(_NDIS_MINIPORT_BLOCK *,_NDIS_OPEN_BLOCK *,CO_ADDRESS_FAMILY *,_NDIS_AF_NOTIFY * *)

- ea: `0x140176cb0`
- end: `0x140176fd0`
- name: `?ndisCreateNotifyQueue@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_OPEN_BLOCK@@PEAUCO_ADDRESS_FAMILY@@PEAPEAU_NDIS_AF_NOTIFY@@@Z`
- size: `800`
- prototype: `__int64 __fastcall(struct _NDIS_MINIPORT_BLOCK *, struct _NDIS_OPEN_BLOCK *, struct CO_ADDRESS_FAMILY *, struct _NDIS_AF_NOTIFY **)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400cfe50`
- `0x140176b50`

## callees

- `0x14001c050`
- `0x140028550`
- `0x140029620`
- `0x1400363f0`
- `0x140036a70`
- `0x140064570`
- `0x140176cb0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1401834e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401834e6`
- `ntoskrnl!ExAllocatePool2` at `0x140176d66`
- `ntoskrnl!ExAllocatePool2` at `0x140176ebe`
- `ntoskrnl!ExAllocatePool2` at `0x140176d66`
- `ntoskrnl!ExAllocatePool2` at `0x140176ebe`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140176dbc`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140176eee`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140176f6a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1401834c2`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140176dbc`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140176eee`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140176f6a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1401834c2`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140176d31`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140176e91`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140176d31`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140176e91`

## pseudocode

```c

```
