# ndisUnprocessAllOpens(_NDIS_MINIPORT_BLOCK *)

- ea: `0x14005b020`
- end: `0x14005b1e5`
- name: `?ndisUnprocessAllOpens@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z`
- size: `453`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140175b70`

## callees

- `0x14001cf50`
- `0x14005b020`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14005b1aa`
- `ntoskrnl!KeSetEvent` at `0x14005b1aa`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005b11e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005b11e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005b05e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005b05e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14005b0ed`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14005b0ed`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14005b0a3`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14005b0a3`

## pseudocode

```c

```
