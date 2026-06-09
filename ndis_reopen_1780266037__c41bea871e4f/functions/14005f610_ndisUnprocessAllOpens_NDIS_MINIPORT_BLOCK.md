# ndisUnprocessAllOpens(_NDIS_MINIPORT_BLOCK *)

- ea: `0x14005f610`
- end: `0x14005f7d5`
- name: `?ndisUnprocessAllOpens@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z`
- size: `453`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14017bb40`

## callees

- `0x1400110b0`
- `0x14005f610`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14005f79a`
- `ntoskrnl!KeSetEvent` at `0x14005f79a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005f70e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005f70e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005f64e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005f64e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14005f693`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14005f693`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14005f6dd`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14005f6dd`

## pseudocode

```c

```
