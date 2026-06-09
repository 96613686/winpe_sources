# DXGADAPTER::AcquireCoreResourceExclusive(DXGADAPTER_EXCLUSIVEACCESS_REASON,uint,char const *)

- ea: `0x14032600c`
- end: `0x1403265ef`
- name: `?AcquireCoreResourceExclusive@DXGADAPTER@@AEAAXW4DXGADAPTER_EXCLUSIVEACCESS_REASON@@IPEBD@Z`
- size: `1507`
- prototype: ``
- caller_count: `5`
- callee_count: `15`
- tags: ``

## callers

- `0x14005fd50`
- `0x1401e80a0`
- `0x1401fe560`
- `0x1403265f8`
- `0x140365e94`

## callees

- `0x140012540`
- `0x14001b9c0`
- `0x14001d884`
- `0x140051e80`
- `0x140258190`
- `0x1402593dc`
- `0x14025a054`
- `0x14032600c`
- `0x140328500`
- `0x14032a5c4`
- `0x14033a890`
- `0x14033a920`
- `0x140367720`
- `0x1403b1c5c`
- `0x1403ed154`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14032636a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14032636a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140326089`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403262e4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140326355`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140326089`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403262e4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140326355`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14032623a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403265ba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14032623a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403265ba`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403265ae`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403265ae`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14032603a`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1403261e9`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14032603a`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1403261e9`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403260a6`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403262a5`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403263b9`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403260a6`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403262a5`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403263b9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403261d6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403261d6`
- `watchdog!WdLogSingleEntry0` at `0x14032630e`
- `watchdog!WdLogSingleEntry0` at `0x1403264c6`
- `watchdog!WdLogSingleEntry0` at `0x140326524`
- `watchdog!WdLogSingleEntry0` at `0x14032630e`
- `watchdog!WdLogSingleEntry0` at `0x1403264c6`
- `watchdog!WdLogSingleEntry0` at `0x140326524`
- `watchdog!WdLogSingleEntry5` at `0x140326064`
- `watchdog!WdLogSingleEntry5` at `0x140326064`

## pseudocode

```c

```
