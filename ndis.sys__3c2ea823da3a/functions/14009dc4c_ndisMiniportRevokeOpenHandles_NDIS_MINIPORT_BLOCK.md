# ndisMiniportRevokeOpenHandles(_NDIS_MINIPORT_BLOCK *)

- ea: `0x14009dc4c`
- end: `0x14009deaf`
- name: `?ndisMiniportRevokeOpenHandles@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z`
- size: `611`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1400821b0`
- `0x1401428e0`

## callees

- `0x140015280`
- `0x14001cf50`
- `0x14001d030`
- `0x1400733f0`
- `0x14009dc4c`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14009de59`
- `ntoskrnl!KeSetEvent` at `0x14009de59`
- `ntoskrnl!KeReleaseSpinLock` at `0x14009ddf4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14009ddf4`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14009ddbf`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14009ddbf`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14009dcfd`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14009dcfd`

## pseudocode

```c

```
