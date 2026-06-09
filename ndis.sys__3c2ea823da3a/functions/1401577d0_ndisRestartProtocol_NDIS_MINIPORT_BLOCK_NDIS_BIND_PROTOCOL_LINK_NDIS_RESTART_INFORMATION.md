# ndisRestartProtocol(_NDIS_MINIPORT_BLOCK *,NDIS_BIND_PROTOCOL_LINK *,NDIS_RESTART_INFORMATION *)

- ea: `0x1401577d0`
- end: `0x140157b22`
- name: `?ndisRestartProtocol@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAUNDIS_BIND_PROTOCOL_LINK@@PEAUNDIS_RESTART_INFORMATION@@@Z`
- size: `850`
- prototype: `void(struct _NDIS_MINIPORT_BLOCK *, struct NDIS_BIND_PROTOCOL_LINK *, struct NDIS_RESTART_INFORMATION *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140157e00`

## callees

- `0x1400571d0`
- `0x1400596f0`
- `0x14005edf0`
- `0x140061f30`
- `0x140062ff0`
- `0x14009d530`
- `0x140156db0`
- `0x1401577d0`
- `0x140157dc0`
- `0x14015b500`
- `0x14015c5a0`
- `0x14016a620`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1401578cb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140157999`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401578cb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140157999`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401578dc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401579aa`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401578dc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401579aa`

## pseudocode

```c

```
