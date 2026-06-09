# DxgEscapeEvictWorker(_D3DKMT_VIDMM_ESCAPE *,DXGPROCESS *)

- ea: `0x140239c9c`
- end: `0x14023a992`
- name: `?DxgEscapeEvictWorker@@YAJPEAU_D3DKMT_VIDMM_ESCAPE@@PEAVDXGPROCESS@@@Z`
- size: `3318`
- prototype: `int(struct _D3DKMT_VIDMM_ESCAPE *, struct DXGPROCESS *)`
- caller_count: `1`
- callee_count: `29`
- tags: ``

## callers

- `0x14023989c`

## callees

- `0x1400144ec`
- `0x1400150d0`
- `0x140015780`
- `0x140015970`
- `0x1400161c8`
- `0x140017fb8`
- `0x14001a7d4`
- `0x14001ab20`
- `0x14001b890`
- `0x14001bd70`
- `0x14001f120`
- `0x14001f460`
- `0x14002ec90`
- `0x140034740`
- `0x140045b1c`
- `0x14006f294`
- `0x140074a4c`
- `0x1400a0100`
- `0x140196f20`
- `0x140219808`
- `0x140239c9c`
- `0x14028e824`
- `0x140323d38`
- `0x140327c10`
- `0x140329000`
- `0x140340d50`
- `0x14036f9f0`
- `0x14036fd90`
- `0x14038dd14`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140239d6f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140239d6f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140239d5e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140239d5e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140239f4a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14023a27e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14023a4a7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14023a957`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140239f4a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14023a27e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14023a4a7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14023a957`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140239f3e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14023a272`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14023a49b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14023a94b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140239f3e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14023a272`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14023a49b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14023a94b`
- `watchdog!WdLogSingleEntry0` at `0x14023a060`
- `watchdog!WdLogSingleEntry0` at `0x14023a212`
- `watchdog!WdLogSingleEntry0` at `0x14023a434`
- `watchdog!WdLogSingleEntry0` at `0x14023a555`
- `watchdog!WdLogSingleEntry0` at `0x14023a8ea`
- `watchdog!WdLogSingleEntry0` at `0x14023a060`
- `watchdog!WdLogSingleEntry0` at `0x14023a212`
- `watchdog!WdLogSingleEntry0` at `0x14023a434`
- `watchdog!WdLogSingleEntry0` at `0x14023a555`
- `watchdog!WdLogSingleEntry0` at `0x14023a8ea`
- `watchdog!WdLogSingleEntry1` at `0x140239ce1`
- `watchdog!WdLogSingleEntry1` at `0x140239e49`
- `watchdog!WdLogSingleEntry1` at `0x140239f89`
- `watchdog!WdLogSingleEntry1` at `0x140239fb3`
- `watchdog!WdLogSingleEntry1` at `0x14023a2b0`
- `watchdog!WdLogSingleEntry1` at `0x14023a6a9`
- `watchdog!WdLogSingleEntry1` at `0x14023a7e2`
- `watchdog!WdLogSingleEntry1` at `0x140239ce1`
- `watchdog!WdLogSingleEntry1` at `0x140239e49`
- `watchdog!WdLogSingleEntry1` at `0x140239f89`
- `watchdog!WdLogSingleEntry1` at `0x140239fb3`
- `watchdog!WdLogSingleEntry1` at `0x14023a2b0`
- `watchdog!WdLogSingleEntry1` at `0x14023a6a9`
- `watchdog!WdLogSingleEntry1` at `0x14023a7e2`

## string_xrefs

- `0x140239fbf`: `Failed to acquire coredeviceaccess shared lock, returning 0x%I64x`
- `0x14023a2c1`: `Failed to acquire CoreAdapterAccess shared lock, returning 0x%I64x`
- `0x14023a6c6`: `Failed to acquire CoreAdapterAccess shared lock, returning 0x%I64x`

## pseudocode

```c

```
