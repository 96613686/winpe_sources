# DxgEscapeEvictWorker(_D3DKMT_VIDMM_ESCAPE *,DXGPROCESS *)

- ea: `0x14023c7fc`
- end: `0x14023d4f2`
- name: `?DxgEscapeEvictWorker@@YAJPEAU_D3DKMT_VIDMM_ESCAPE@@PEAVDXGPROCESS@@@Z`
- size: `3318`
- prototype: `__int64 __fastcall(struct _D3DKMT_VIDMM_ESCAPE *, struct DXGPROCESS *)`
- caller_count: `1`
- callee_count: `29`
- tags: ``

## callers

- `0x14023c3fc`

## callees

- `0x1400146ac`
- `0x140015290`
- `0x140015940`
- `0x140015b30`
- `0x140016388`
- `0x140018054`
- `0x14001a874`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001bea0`
- `0x14001f2f0`
- `0x14001f630`
- `0x14002ee60`
- `0x140034910`
- `0x140045d7c`
- `0x14006f844`
- `0x14007508c`
- `0x1400a0bd0`
- `0x14019af20`
- `0x14021be58`
- `0x14023c7fc`
- `0x140295184`
- `0x14032aaa8`
- `0x14032e980`
- `0x14032fd70`
- `0x14036fa30`
- `0x14036fdd0`
- `0x14037ecf0`
- `0x14038cde4`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14023c8cf`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14023c8cf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14023c8be`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14023c8be`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14023caaa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14023cdde`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14023d007`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14023d4b7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14023caaa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14023cdde`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14023d007`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14023d4b7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14023ca9e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14023cdd2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14023cffb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14023d4ab`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14023ca9e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14023cdd2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14023cffb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14023d4ab`
- `watchdog!WdLogSingleEntry0` at `0x14023cbc0`
- `watchdog!WdLogSingleEntry0` at `0x14023cd72`
- `watchdog!WdLogSingleEntry0` at `0x14023cf94`
- `watchdog!WdLogSingleEntry0` at `0x14023d0b5`
- `watchdog!WdLogSingleEntry0` at `0x14023d44a`
- `watchdog!WdLogSingleEntry0` at `0x14023cbc0`
- `watchdog!WdLogSingleEntry0` at `0x14023cd72`
- `watchdog!WdLogSingleEntry0` at `0x14023cf94`
- `watchdog!WdLogSingleEntry0` at `0x14023d0b5`
- `watchdog!WdLogSingleEntry0` at `0x14023d44a`
- `watchdog!WdLogSingleEntry1` at `0x14023c841`
- `watchdog!WdLogSingleEntry1` at `0x14023c9a9`
- `watchdog!WdLogSingleEntry1` at `0x14023cae9`
- `watchdog!WdLogSingleEntry1` at `0x14023cb13`
- `watchdog!WdLogSingleEntry1` at `0x14023ce10`
- `watchdog!WdLogSingleEntry1` at `0x14023d209`
- `watchdog!WdLogSingleEntry1` at `0x14023d342`
- `watchdog!WdLogSingleEntry1` at `0x14023c841`
- `watchdog!WdLogSingleEntry1` at `0x14023c9a9`
- `watchdog!WdLogSingleEntry1` at `0x14023cae9`
- `watchdog!WdLogSingleEntry1` at `0x14023cb13`
- `watchdog!WdLogSingleEntry1` at `0x14023ce10`
- `watchdog!WdLogSingleEntry1` at `0x14023d209`
- `watchdog!WdLogSingleEntry1` at `0x14023d342`

## string_xrefs

- `0x14023cb1f`: `Failed to acquire coredeviceaccess shared lock, returning 0x%I64x`
- `0x14023ce21`: `Failed to acquire CoreAdapterAccess shared lock, returning 0x%I64x`
- `0x14023d226`: `Failed to acquire CoreAdapterAccess shared lock, returning 0x%I64x`

## pseudocode

```c

```
