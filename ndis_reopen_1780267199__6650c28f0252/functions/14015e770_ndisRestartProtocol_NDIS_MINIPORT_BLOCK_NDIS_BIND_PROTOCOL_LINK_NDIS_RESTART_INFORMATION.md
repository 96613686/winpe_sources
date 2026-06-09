# ndisRestartProtocol(_NDIS_MINIPORT_BLOCK *,NDIS_BIND_PROTOCOL_LINK *,NDIS_RESTART_INFORMATION *)

- ea: `0x14015e770`
- end: `0x14015eac2`
- name: `?ndisRestartProtocol@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAUNDIS_BIND_PROTOCOL_LINK@@PEAUNDIS_RESTART_INFORMATION@@@Z`
- size: `850`
- prototype: `void(struct _NDIS_MINIPORT_BLOCK *, struct NDIS_BIND_PROTOCOL_LINK *, struct NDIS_RESTART_INFORMATION *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x14015eda0`

## callees

- `0x14005bd40`
- `0x14005dde0`
- `0x140063390`
- `0x1400668f0`
- `0x1400683c0`
- `0x1400a27b0`
- `0x14015dd50`
- `0x14015e770`
- `0x14015ed60`
- `0x1401624a0`
- `0x140163540`
- `0x140171510`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14015e86b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14015e939`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14015e86b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14015e939`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14015e87c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14015e94a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14015e87c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14015e94a`

## pseudocode

```c

```
