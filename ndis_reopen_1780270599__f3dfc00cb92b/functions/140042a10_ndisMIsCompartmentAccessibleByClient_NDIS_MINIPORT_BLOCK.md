# ndisMIsCompartmentAccessibleByClient(_NDIS_MINIPORT_BLOCK *)

- ea: `0x140042a10`
- end: `0x140042c95`
- name: `?ndisMIsCompartmentAccessibleByClient@@YA_NPEAU_NDIS_MINIPORT_BLOCK@@@Z`
- size: `645`
- prototype: `bool __fastcall(struct _NDIS_MINIPORT_BLOCK *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400421a0`

## callees

- `0x14000b820`
- `0x140014e40`
- `0x140017220`
- `0x140019d90`
- `0x14001a380`
- `0x140042a10`
- `0x140042ca0`
- `0x140088cc0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140042bad`
- `ntoskrnl!KeSetEvent` at `0x140042bad`
- `ntoskrnl!KeReleaseSpinLock` at `0x140042a84`
- `ntoskrnl!KeReleaseSpinLock` at `0x140042b6a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140042c76`
- `ntoskrnl!KeReleaseSpinLock` at `0x140042a84`
- `ntoskrnl!KeReleaseSpinLock` at `0x140042b6a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140042c76`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140042a42`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140042abc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140042a42`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140042abc`

## pseudocode

```c

```
