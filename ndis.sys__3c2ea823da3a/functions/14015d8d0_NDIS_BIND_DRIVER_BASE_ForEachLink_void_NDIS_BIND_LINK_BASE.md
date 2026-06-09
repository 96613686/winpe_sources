# NDIS_BIND_DRIVER_BASE::ForEachLink(void (*)(NDIS_BIND_LINK_BASE *))

- ea: `0x14015d8d0`
- end: `0x14015d9d8`
- name: `?ForEachLink@NDIS_BIND_DRIVER_BASE@@QEAAXP6AXPEAUNDIS_BIND_LINK_BASE@@@Z@Z`
- size: `264`
- prototype: `void __fastcall(NDIS_BIND_DRIVER_BASE *__hidden this, void (*)(struct NDIS_BIND_LINK_BASE *))`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x1400b75c0`
- `0x14013cd60`
- `0x1401461f0`
- `0x14015d870`

## callees

- `0x14001cc80`
- `0x14001e4b0`
- `0x1400e6240`
- `0x14015d8d0`
- `0x14015df90`
- `0x140162ff0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14015d9c0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14015d9c0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14015d8f1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14015d8f1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14015d9a1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14015d9a1`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14015d90a`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14015d90a`
- `ntoskrnl!ExReleasePushLockEx` at `0x14015d9b4`
- `ntoskrnl!ExReleasePushLockEx` at `0x14015d9b4`

## pseudocode

```c

```
