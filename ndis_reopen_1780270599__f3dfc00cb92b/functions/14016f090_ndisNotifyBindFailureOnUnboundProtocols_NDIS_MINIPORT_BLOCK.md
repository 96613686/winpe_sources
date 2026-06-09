# ndisNotifyBindFailureOnUnboundProtocols(_NDIS_MINIPORT_BLOCK *)

- ea: `0x14016f090`
- end: `0x14016f1ba`
- name: `?ndisNotifyBindFailureOnUnboundProtocols@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z`
- size: `298`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140143410`
- `0x140181e50`
- `0x140185810`
- `0x140186f10`

## callees

- `0x14005eaa0`
- `0x14005f7e0`
- `0x140084030`
- `0x14016f090`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14016f125`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14016f154`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14016f125`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14016f154`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14016f0a0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14016f18d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14016f0a0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14016f18d`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14016f0b5`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14016f1a2`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14016f0b5`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14016f1a2`
- `ntoskrnl!ExReleasePushLockEx` at `0x14016f13a`
- `ntoskrnl!ExReleasePushLockEx` at `0x14016f169`
- `ntoskrnl!ExReleasePushLockEx` at `0x14016f13a`
- `ntoskrnl!ExReleasePushLockEx` at `0x14016f169`

## pseudocode

```c

```
