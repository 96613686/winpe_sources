# DXGADAPTER::AcquireCoreResourceExclusive(DXGADAPTER_EXCLUSIVEACCESS_REASON,uint,char const *)

- ea: `0x14031f29c`
- end: `0x14031f87f`
- name: `?AcquireCoreResourceExclusive@DXGADAPTER@@AEAAXW4DXGADAPTER_EXCLUSIVEACCESS_REASON@@IPEBD@Z`
- size: `1507`
- prototype: ``
- caller_count: `5`
- callee_count: `15`
- tags: ``

## callers

- `0x14005f9a0`
- `0x1401e5d20`
- `0x1401fc180`
- `0x14031f888`
- `0x140365e54`

## callees

- `0x140012380`
- `0x14001b890`
- `0x14001d6b4`
- `0x140051cc0`
- `0x140253b44`
- `0x140254d8c`
- `0x140255a04`
- `0x14031f29c`
- `0x140321790`
- `0x140323854`
- `0x140333e70`
- `0x140333f00`
- `0x1403676e0`
- `0x1403b3b4c`
- `0x1403ecc94`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14031f5fa`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14031f5fa`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14031f319`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14031f574`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14031f5e5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14031f319`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14031f574`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14031f5e5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14031f4ca`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14031f84a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14031f4ca`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14031f84a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14031f83e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14031f83e`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14031f2ca`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14031f479`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14031f2ca`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14031f479`
- `ntoskrnl!PsGetCurrentProcess` at `0x14031f336`
- `ntoskrnl!PsGetCurrentProcess` at `0x14031f535`
- `ntoskrnl!PsGetCurrentProcess` at `0x14031f649`
- `ntoskrnl!PsGetCurrentProcess` at `0x14031f336`
- `ntoskrnl!PsGetCurrentProcess` at `0x14031f535`
- `ntoskrnl!PsGetCurrentProcess` at `0x14031f649`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14031f466`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14031f466`
- `watchdog!WdLogSingleEntry0` at `0x14031f59e`
- `watchdog!WdLogSingleEntry0` at `0x14031f756`
- `watchdog!WdLogSingleEntry0` at `0x14031f7b4`
- `watchdog!WdLogSingleEntry0` at `0x14031f59e`
- `watchdog!WdLogSingleEntry0` at `0x14031f756`
- `watchdog!WdLogSingleEntry0` at `0x14031f7b4`
- `watchdog!WdLogSingleEntry5` at `0x14031f2f4`
- `watchdog!WdLogSingleEntry5` at `0x14031f2f4`

## pseudocode

```c

```
