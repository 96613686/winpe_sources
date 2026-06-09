# VIDMM_DEVICE::CleanupAllocationCommitment(VIDMM_ALLOC *)

- ea: `0x1400e0eb0`
- end: `0x1400e1189`
- name: `?CleanupAllocationCommitment@VIDMM_DEVICE@@QEAAXPEAUVIDMM_ALLOC@@@Z`
- size: `729`
- prototype: `void(VIDMM_DEVICE *__hidden this, struct VIDMM_ALLOC *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14009ced0`

## callees

- `0x1400045ec`
- `0x14002eb94`
- `0x140030fc4`
- `0x1400e0eb0`
- `0x1400e2668`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400e10f3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400e10f3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e10ff`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e10ff`
- `watchdog!WdLogSingleEntry5` at `0x1400e0fb9`
- `watchdog!WdLogSingleEntry5` at `0x1400e10af`
- `watchdog!WdLogSingleEntry5` at `0x1400e0fb9`
- `watchdog!WdLogSingleEntry5` at `0x1400e10af`
- `watchdog!WdLogSingleEntry0` at `0x1400e113c`
- `watchdog!WdLogSingleEntry0` at `0x1400e113c`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400e0f97`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400e108d`

## pseudocode

```c

```
