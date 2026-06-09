# VIDMM_GLOBAL::Evict(VIDMM_DEVICE *,VIDMM_MULTI_ALLOC * *,uint,ulong,unsigned __int64 *)

- ea: `0x1400e9544`
- end: `0x1400e99f5`
- name: `?Evict@VIDMM_GLOBAL@@QEAAXPEAVVIDMM_DEVICE@@PEAPEAUVIDMM_MULTI_ALLOC@@IKPEA_K@Z`
- size: `1201`
- prototype: `void(VIDMM_GLOBAL *__hidden this, struct VIDMM_DEVICE *, struct VIDMM_MULTI_ALLOC **, unsigned int, unsigned int, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation`

## callers

- `0x140032460`
- `0x1400be7b4`

## callees

- `0x140003490`
- `0x140004268`
- `0x140011efc`
- `0x14002bc54`
- `0x14002bddc`
- `0x14002d8cc`
- `0x14002dab4`
- `0x14002eba4`
- `0x140030854`
- `0x140059380`
- `0x1400c38cc`
- `0x1400e9544`
- `0x1400e99fc`
- `0x1400e9d40`
- `0x1400eaab8`
- `0x1400eac74`
- `0x1400ead58`
- `0x1400eae20`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e975e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e975e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400e9774`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400e9774`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400e97dc`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400e97dc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e97e8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e97e8`
- `watchdog!WdLogSingleEntry2` at `0x1400e9606`
- `watchdog!WdLogSingleEntry2` at `0x1400e9606`
- `watchdog!WdLogSingleEntry0` at `0x1400e997e`
- `watchdog!WdLogSingleEntry0` at `0x1400e997e`

## string_xrefs

- `0x1400e961c`: `VIDMM_ALLOC 0x%p with no residency references being evicted. pGlobalAlloc->AlwaysResident=%d`

## pseudocode

```c

```
