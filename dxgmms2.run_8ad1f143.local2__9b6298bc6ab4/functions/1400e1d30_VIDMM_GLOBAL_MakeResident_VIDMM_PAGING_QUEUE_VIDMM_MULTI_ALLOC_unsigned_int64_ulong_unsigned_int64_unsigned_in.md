# VIDMM_GLOBAL::MakeResident(VIDMM_PAGING_QUEUE *,VIDMM_MULTI_ALLOC * *,unsigned __int64,ulong,unsigned __int64 *,unsigned __int64 *)

- ea: `0x1400e1d30`
- end: `0x1400e2415`
- name: `?MakeResident@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_QUEUE@@PEAPEAUVIDMM_MULTI_ALLOC@@_KKPEA_K3@Z`
- size: `1765`
- prototype: `__int64 __usercall@<rax>(VIDMM_GLOBAL *__hidden this@<rcx>, struct VIDMM_PAGING_QUEUE *@<rdx>, struct VIDMM_MULTI_ALLOC **@<r8>, unsigned __int64@<r9>, char, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `4`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x1400320a0`
- `0x1400bc240`
- `0x1400bdbf8`
- `0x14010416c`

## callees

- `0x1400045ec`
- `0x14001245c`
- `0x1400204c0`
- `0x14002eb94`
- `0x14002ed1c`
- `0x140030fc4`
- `0x140058ac0`
- `0x1400dfe1c`
- `0x1400e1d30`
- `0x1400e241c`
- `0x1400e2504`
- `0x1400e2668`
- `0x1400e2720`
- `0x1400e298c`

## import_xrefs

- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400e2040`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400e2040`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400e21a3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400e21a3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e204c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e204c`
- `watchdog!WdLogSingleEntry0` at `0x1400e2368`
- `watchdog!WdLogSingleEntry0` at `0x1400e23bd`
- `watchdog!WdLogSingleEntry0` at `0x1400e2368`
- `watchdog!WdLogSingleEntry0` at `0x1400e23bd`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400e1ecb`

## pseudocode

```c

```
