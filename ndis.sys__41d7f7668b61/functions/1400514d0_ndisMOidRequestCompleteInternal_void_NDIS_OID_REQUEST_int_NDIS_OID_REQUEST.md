# ndisMOidRequestCompleteInternal(void *,_NDIS_OID_REQUEST *,int,_NDIS_OID_REQUEST *)

- ea: `0x1400514d0`
- end: `0x140051961`
- name: `?ndisMOidRequestCompleteInternal@@YAXPEAXPEAU_NDIS_OID_REQUEST@@H1@Z`
- size: `1169`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *, struct _NDIS_OID_REQUEST *, int, struct _NDIS_OID_REQUEST *)`
- caller_count: `9`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140032f00`
- `0x1400335f0`
- `0x14003cec0`
- `0x1400510e0`
- `0x140051220`
- `0x140051380`
- `0x1400745d0`
- `0x1400774e0`
- `0x14008c0f0`

## callees

- `0x140009320`
- `0x14000b820`
- `0x1400110b0`
- `0x1400114b0`
- `0x140014e40`
- `0x140017220`
- `0x14001a380`
- `0x14001b1b0`
- `0x14004f290`
- `0x1400514d0`
- `0x14007efa0`
- `0x140088cc0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400517e3`
- `ntoskrnl!KeSetEvent` at `0x14005193a`
- `ntoskrnl!KeSetEvent` at `0x1400517e3`
- `ntoskrnl!KeSetEvent` at `0x14005193a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005157c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400515f5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005170c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005189c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400518e5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400f08bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005157c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400515f5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005170c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005189c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400518e5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400f08bf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140051532`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005159f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140051624`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140051532`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005159f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140051624`

## pseudocode

```c

```
