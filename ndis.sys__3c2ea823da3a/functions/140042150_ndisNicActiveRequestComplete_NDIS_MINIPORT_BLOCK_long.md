# ndisNicActiveRequestComplete(_NDIS_MINIPORT_BLOCK *,long)

- ea: `0x140042150`
- end: `0x1400422e7`
- name: `?ndisNicActiveRequestComplete@@YAXPEAU_NDIS_MINIPORT_BLOCK@@J@Z`
- size: `407`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400423f0`

## callees

- `0x140015170`
- `0x140019b40`
- `0x140040bc0`
- `0x140041f40`
- `0x140042150`
- `0x1400422f0`
- `0x140085810`
- `0x1400c2360`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140042192`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400421f3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140042192`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400421f3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004216e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400421ce`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004216e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400421ce`

## pseudocode

```c

```
