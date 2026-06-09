# VIDMM_GLOBAL::Evict(VIDMM_DEVICE *,VIDMM_MULTI_ALLOC * *,uint,ulong,unsigned __int64 *)

- ea: `0x1400e1530`
- end: `0x1400e19e1`
- name: `?Evict@VIDMM_GLOBAL@@QEAAXPEAVVIDMM_DEVICE@@PEAPEAUVIDMM_MULTI_ALLOC@@IKPEA_K@Z`
- size: `1201`
- prototype: `void(VIDMM_GLOBAL *__hidden this, struct VIDMM_DEVICE *, struct VIDMM_MULTI_ALLOC **, unsigned int, unsigned int, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation`

## callers

- `0x140033f80`
- `0x1400bad14`

## callees

- `0x1400037a0`
- `0x1400045ec`
- `0x14001245c`
- `0x14002eb94`
- `0x14002ed1c`
- `0x14002fbac`
- `0x14002fd94`
- `0x140030fc4`
- `0x140032a04`
- `0x140058ac0`
- `0x1400bf7dc`
- `0x1400e1530`
- `0x1400e19e8`
- `0x1400e2668`
- `0x1400e284c`
- `0x1400e2930`
- `0x1400e29f0`
- `0x1400e2ad8`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e174a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e174a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400e1760`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400e1760`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400e17c8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400e17c8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e17d4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e17d4`
- `watchdog!WdLogSingleEntry2` at `0x1400e15f2`
- `watchdog!WdLogSingleEntry2` at `0x1400e15f2`
- `watchdog!WdLogSingleEntry0` at `0x1400e196a`
- `watchdog!WdLogSingleEntry0` at `0x1400e196a`

## string_xrefs

- `0x1400e1608`: `VIDMM_ALLOC 0x%p with no residency references being evicted. pGlobalAlloc->AlwaysResident=%d`

## pseudocode

```c

```
