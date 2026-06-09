# ndisMiniportRevokeOpenHandles(_NDIS_MINIPORT_BLOCK *)

- ea: `0x1400a2ecc`
- end: `0x1400a312f`
- name: `?ndisMiniportRevokeOpenHandles@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z`
- size: `611`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140087430`
- `0x140149880`

## callees

- `0x140009320`
- `0x1400110b0`
- `0x140011190`
- `0x140078ad0`
- `0x1400a2ecc`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400a30d9`
- `ntoskrnl!KeSetEvent` at `0x1400a30d9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400a3074`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400a3074`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400a2f7d`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400a2f7d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400a303f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400a303f`

## pseudocode

```c

```
