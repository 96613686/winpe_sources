# VidMmAppendReadyPacket(VIDMM_WORKER_THREAD *,VIDMM_PAGING_QUEUE *,VIDMM_PAGING_QUEUE_PACKET *,unsigned __int64 *)

- ea: `0x1400e99fc`
- end: `0x1400e9d39`
- name: `?VidMmAppendReadyPacket@@YAXPEAUVIDMM_WORKER_THREAD@@PEAUVIDMM_PAGING_QUEUE@@PEAUVIDMM_PAGING_QUEUE_PACKET@@PEA_K@Z`
- size: `829`
- prototype: `void __fastcall(struct VIDMM_WORKER_THREAD *, struct VIDMM_PAGING_QUEUE *, struct VIDMM_PAGING_QUEUE_PACKET *, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x1400e9544`
- `0x1400ea904`
- `0x1400eaf5c`

## callees

- `0x14002b730`
- `0x140032560`
- `0x140033934`
- `0x1400aba44`
- `0x1400e8860`
- `0x1400e99fc`
- `0x1400eb540`
- `0x14010bf2c`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400e9b1f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400e9b1f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e9b2b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e9b2b`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e9b7f`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e9bc7`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e9bf1`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e9c18`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e9b7f`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e9bc7`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e9bf1`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e9c18`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400e9aa6`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400e9ad5`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400e9b61`

## pseudocode

```c

```
