# ndisNotifyBindFailureOnUnboundProtocols(_NDIS_MINIPORT_BLOCK *)

- ea: `0x1401681a0`
- end: `0x1401682ca`
- name: `?ndisNotifyBindFailureOnUnboundProtocols@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z`
- size: `298`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14013c470`
- `0x14017be80`
- `0x14017f260`
- `0x140180960`

## callees

- `0x14005a5c0`
- `0x14005b1f0`
- `0x14007e840`
- `0x1401681a0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140168235`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140168264`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140168235`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140168264`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401681b0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14016829d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401681b0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14016829d`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401681c5`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401682b2`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401681c5`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401682b2`
- `ntoskrnl!ExReleasePushLockEx` at `0x14016824a`
- `ntoskrnl!ExReleasePushLockEx` at `0x140168279`
- `ntoskrnl!ExReleasePushLockEx` at `0x14016824a`
- `ntoskrnl!ExReleasePushLockEx` at `0x140168279`

## pseudocode

```c

```
