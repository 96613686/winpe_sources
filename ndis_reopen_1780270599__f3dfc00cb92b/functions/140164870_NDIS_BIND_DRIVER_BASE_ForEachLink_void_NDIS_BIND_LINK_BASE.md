# NDIS_BIND_DRIVER_BASE::ForEachLink(void (*)(NDIS_BIND_LINK_BASE *))

- ea: `0x140164870`
- end: `0x140164978`
- name: `?ForEachLink@NDIS_BIND_DRIVER_BASE@@QEAAXP6AXPEAUNDIS_BIND_LINK_BASE@@@Z@Z`
- size: `264`
- prototype: `void __fastcall(NDIS_BIND_DRIVER_BASE *__hidden this, void (*)(struct NDIS_BIND_LINK_BASE *))`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x1400bc9f0`
- `0x140143d00`
- `0x14014d190`
- `0x140164810`

## callees

- `0x140010d20`
- `0x140012610`
- `0x1400eb460`
- `0x140164870`
- `0x140164e30`
- `0x140169f80`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140164960`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140164960`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140164891`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140164891`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140164941`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140164941`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401648aa`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401648aa`
- `ntoskrnl!ExReleasePushLockEx` at `0x140164954`
- `ntoskrnl!ExReleasePushLockEx` at `0x140164954`

## pseudocode

```c

```
