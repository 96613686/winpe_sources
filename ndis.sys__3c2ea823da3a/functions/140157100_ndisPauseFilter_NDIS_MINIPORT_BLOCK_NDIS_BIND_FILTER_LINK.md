# ndisPauseFilter(_NDIS_MINIPORT_BLOCK *,NDIS_BIND_FILTER_LINK *)

- ea: `0x140157100`
- end: `0x14015723c`
- name: `?ndisPauseFilter@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAUNDIS_BIND_FILTER_LINK@@@Z`
- size: `316`
- prototype: `void(struct _NDIS_MINIPORT_BLOCK *, struct NDIS_BIND_FILTER_LINK *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140157e00`

## callees

- `0x14003d920`
- `0x14004e050`
- `0x140060900`
- `0x140155150`
- `0x1401567c0`
- `0x140157100`
- `0x140157dc0`
- `0x1401783a0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14015716e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401571bc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14015716e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401571bc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140157183`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401571d1`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140157183`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401571d1`

## pseudocode

```c

```
