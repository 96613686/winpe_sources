# VidMmAppendReadyPacket(VIDMM_WORKER_THREAD *,VIDMM_PAGING_QUEUE *,VIDMM_PAGING_QUEUE_PACKET *,unsigned __int64 *)

- ea: `0x1400e19e8`
- end: `0x1400e1d25`
- name: `?VidMmAppendReadyPacket@@YAXPEAUVIDMM_WORKER_THREAD@@PEAUVIDMM_PAGING_QUEUE@@PEAUVIDMM_PAGING_QUEUE_PACKET@@PEA_K@Z`
- size: `829`
- prototype: `void __fastcall(struct VIDMM_WORKER_THREAD *, struct VIDMM_PAGING_QUEUE *, struct VIDMM_PAGING_QUEUE_PACKET *, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x1400e1530`
- `0x1400e2504`
- `0x1400e34ac`

## callees

- `0x14002e850`
- `0x140034080`
- `0x140035044`
- `0x1400aa904`
- `0x1400e0400`
- `0x1400e19e8`
- `0x1400e729c`
- `0x1400ffdf8`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400e1b0b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400e1b0b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e1b17`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e1b17`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e1b6b`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e1bb3`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e1bdd`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e1c04`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e1b6b`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e1bb3`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e1bdd`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e1c04`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400e1a92`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400e1ac1`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400e1b4d`

## pseudocode

```c

```
