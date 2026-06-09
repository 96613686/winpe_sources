# ndisMIsCompartmentAccessibleByClient(_NDIS_MINIPORT_BLOCK *)

- ea: `0x1400400f0`
- end: `0x140040375`
- name: `?ndisMIsCompartmentAccessibleByClient@@YA_NPEAU_NDIS_MINIPORT_BLOCK@@@Z`
- size: `645`
- prototype: `bool __fastcall(struct _NDIS_MINIPORT_BLOCK *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14003f880`

## callees

- `0x140017780`
- `0x140020ce0`
- `0x1400230c0`
- `0x140025c30`
- `0x140026220`
- `0x1400400f0`
- `0x140040380`
- `0x140083a40`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14004028d`
- `ntoskrnl!KeSetEvent` at `0x14004028d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140040164`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004024a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140040356`
- `ntoskrnl!KeReleaseSpinLock` at `0x140040164`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004024a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140040356`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140040122`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004019c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140040122`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004019c`

## pseudocode

```c

```
