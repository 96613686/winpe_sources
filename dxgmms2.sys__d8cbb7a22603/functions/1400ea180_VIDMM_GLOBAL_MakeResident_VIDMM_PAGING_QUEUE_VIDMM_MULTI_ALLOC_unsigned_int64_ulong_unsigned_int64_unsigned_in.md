# VIDMM_GLOBAL::MakeResident(VIDMM_PAGING_QUEUE *,VIDMM_MULTI_ALLOC * *,unsigned __int64,ulong,unsigned __int64 *,unsigned __int64 *)

- ea: `0x1400ea180`
- end: `0x1400ea815`
- name: `?MakeResident@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_QUEUE@@PEAPEAUVIDMM_MULTI_ALLOC@@_KKPEA_K3@Z`
- size: `1685`
- prototype: `__int64 __usercall@<rax>(VIDMM_GLOBAL *__hidden this@<rcx>, struct VIDMM_PAGING_QUEUE *@<rdx>, struct VIDMM_MULTI_ALLOC **@<r8>, unsigned __int64@<r9>, unsigned int, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `4`
- callee_count: `15`
- tags: `authz_impersonation`

## callers

- `0x14002fe60`
- `0x1400bfce0`
- `0x1400c1cdc`
- `0x1400f24e0`

## callees

- `0x140004268`
- `0x140011efc`
- `0x14001e960`
- `0x14002bc54`
- `0x14002bddc`
- `0x14002eba4`
- `0x140059380`
- `0x1400e827c`
- `0x1400ea180`
- `0x1400ea81c`
- `0x1400ea904`
- `0x1400eaa68`
- `0x1400eaab8`
- `0x1400eab70`
- `0x1400eadb4`

## import_xrefs

- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400ea48a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400ea48a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400ea5e3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400ea5e3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ea496`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ea496`
- `watchdog!WdLogSingleEntry0` at `0x1400ea768`
- `watchdog!WdLogSingleEntry0` at `0x1400ea7bd`
- `watchdog!WdLogSingleEntry0` at `0x1400ea768`
- `watchdog!WdLogSingleEntry0` at `0x1400ea7bd`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400ea2fc`

## pseudocode

```c

```
