# ndisMOidRequestCompleteInternal(void *,_NDIS_OID_REQUEST *,int,_NDIS_OID_REQUEST *)

- ea: `0x14004cb00`
- end: `0x14004cf91`
- name: `?ndisMOidRequestCompleteInternal@@YAXPEAXPEAU_NDIS_OID_REQUEST@@H1@Z`
- size: `1169`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *, struct _NDIS_OID_REQUEST *, int, struct _NDIS_OID_REQUEST *)`
- caller_count: `9`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140011570`
- `0x140012580`
- `0x14004c710`
- `0x14004c850`
- `0x14004c9b0`
- `0x1400507a0`
- `0x14006e8e0`
- `0x140071a90`
- `0x140086e00`

## callees

- `0x140015280`
- `0x140017780`
- `0x14001cf50`
- `0x14001d350`
- `0x140020ce0`
- `0x1400230c0`
- `0x140026220`
- `0x140027050`
- `0x14004a830`
- `0x14004cb00`
- `0x1400798d0`
- `0x140083a40`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14004ce13`
- `ntoskrnl!KeSetEvent` at `0x14004cf6a`
- `ntoskrnl!KeSetEvent` at `0x14004ce13`
- `ntoskrnl!KeSetEvent` at `0x14004cf6a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004cbac`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004cc25`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004cd3c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004cecc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004cf15`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400eb9b7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004cbac`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004cc25`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004cd3c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004cecc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004cf15`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400eb9b7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004cb62`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004cbcf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004cc54`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004cb62`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004cbcf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004cc54`

## pseudocode

```c

```
