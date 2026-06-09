# ndisNicActiveRequestComplete(_NDIS_MINIPORT_BLOCK *,long)

- ea: `0x140045020`
- end: `0x1400451b7`
- name: `?ndisNicActiveRequestComplete@@YAXPEAU_NDIS_MINIPORT_BLOCK@@J@Z`
- size: `407`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400452c0`

## callees

- `0x14000dbe0`
- `0x1400434e0`
- `0x140044330`
- `0x140045020`
- `0x1400451c0`
- `0x14005ec80`
- `0x14008aa90`
- `0x1400c7790`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140045062`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400450c3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140045062`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400450c3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004503e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004509e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004503e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004509e`

## pseudocode

```c

```
