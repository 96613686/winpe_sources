# ndisRestartFilter(_NDIS_MINIPORT_BLOCK *,NDIS_BIND_FILTER_LINK *,NDIS_RESTART_INFORMATION *)

- ea: `0x14015d780`
- end: `0x14015d8e8`
- name: `?ndisRestartFilter@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAUNDIS_BIND_FILTER_LINK@@PEAUNDIS_RESTART_INFORMATION@@@Z`
- size: `360`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *, Ndis::BindState *this, struct NDIS_RESTART_INFORMATION *)`
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x14015eda0`

## callees

- `0x1400400d0`
- `0x140053280`
- `0x140063390`
- `0x140065780`
- `0x1400683c0`
- `0x140068550`
- `0x1400eb380`
- `0x1400eb7c0`
- `0x14014a41c`
- `0x140153100`
- `0x14015d760`
- `0x14015d780`
- `0x14015dae0`
- `0x14015ed60`
- `0x1401624a0`
- `0x14017d0d0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14015d872`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140173c14`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14015d872`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140173c14`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14015d887`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140173c29`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14015d887`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140173c29`

## pseudocode

```c

```
