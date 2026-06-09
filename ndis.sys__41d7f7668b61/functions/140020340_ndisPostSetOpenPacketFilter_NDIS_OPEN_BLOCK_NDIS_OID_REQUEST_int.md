# ndisPostSetOpenPacketFilter(_NDIS_OPEN_BLOCK *,_NDIS_OID_REQUEST *,int)

- ea: `0x140020340`
- end: `0x140020614`
- name: `?ndisPostSetOpenPacketFilter@@YAXPEAU_NDIS_OPEN_BLOCK@@PEAU_NDIS_OID_REQUEST@@H@Z`
- size: `724`
- prototype: `void __fastcall(struct _NDIS_OPEN_BLOCK *, struct _NDIS_OID_REQUEST *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140020100`

## callees

- `0x140020340`
- `0x140020990`
- `0x140020a70`
- `0x14002fe60`
- `0x14008c6d0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140020491`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400204f1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140020491`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400204f1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002045c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400204ba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002045c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400204ba`

## pseudocode

```c

```
