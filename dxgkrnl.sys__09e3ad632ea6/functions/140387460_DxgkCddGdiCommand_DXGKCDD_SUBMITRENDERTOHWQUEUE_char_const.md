# DxgkCddGdiCommand(_DXGKCDD_SUBMITRENDERTOHWQUEUE *,char const *)

- ea: `0x140387460`
- end: `0x140388183`
- name: `?DxgkCddGdiCommand@@YAJPEAU_DXGKCDD_SUBMITRENDERTOHWQUEUE@@PEBD@Z`
- size: `3363`
- prototype: `__int64 __fastcall(struct _DXGKCDD_SUBMITRENDERTOHWQUEUE *, char *, __int64)`
- caller_count: `1`
- callee_count: `32`
- tags: `broker_com_uri`

## callers

- `0x1401d6320`

## callees

- `0x140012cd4`
- `0x140013a20`
- `0x140014950`
- `0x140015a70`
- `0x140015b30`
- `0x140015b60`
- `0x1400164c0`
- `0x1400164f0`
- `0x1400169f0`
- `0x14001b9c0`
- `0x14001bbd0`
- `0x14001c5c0`
- `0x14001ce20`
- `0x14001d214`
- `0x14001f2f0`
- `0x140020320`
- `0x14002ff90`
- `0x140033d80`
- `0x14003c044`
- `0x14003ce94`
- `0x1400a0bd0`
- `0x1400a1000`
- `0x140292bc4`
- `0x14031d764`
- `0x14032a5c4`
- `0x1403873d8`
- `0x140387460`
- `0x14038818c`
- `0x1403881bc`
- `0x140388440`
- `0x1403892dc`
- `0x140398f34`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140388028`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14038810a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140388028`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14038810a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403878d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140387975`
- `ntoskrnl!ExFreePoolWithTag` at `0x14038799e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140387b62`
- `ntoskrnl!ExFreePoolWithTag` at `0x140387b8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140387cd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140387cfe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140387dd7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140387f77`
- `ntoskrnl!ExFreePoolWithTag` at `0x140387fcc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140387ff6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403880b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403880d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403878d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140387975`
- `ntoskrnl!ExFreePoolWithTag` at `0x14038799e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140387b62`
- `ntoskrnl!ExFreePoolWithTag` at `0x140387b8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140387cd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140387cfe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140387dd7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140387f77`
- `ntoskrnl!ExFreePoolWithTag` at `0x140387fcc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140387ff6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403880b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403880d9`
- `ntoskrnl!ExAllocatePool2` at `0x140387862`
- `ntoskrnl!ExAllocatePool2` at `0x140387862`
- `ntoskrnl!PsGetCurrentProcess` at `0x140387505`
- `ntoskrnl!PsGetCurrentProcess` at `0x140387531`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403875e3`
- `ntoskrnl!PsGetCurrentProcess` at `0x140387614`
- `ntoskrnl!PsGetCurrentProcess` at `0x140387505`
- `ntoskrnl!PsGetCurrentProcess` at `0x140387531`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403875e3`
- `ntoskrnl!PsGetCurrentProcess` at `0x140387614`
- `ntoskrnl!ExReleaseResourceLite` at `0x14038801c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1403880fe`
- `ntoskrnl!ExReleaseResourceLite` at `0x14038801c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1403880fe`
- `watchdog!WdLogSingleEntry2` at `0x14038751b`
- `watchdog!WdLogSingleEntry2` at `0x1403877e3`
- `watchdog!WdLogSingleEntry2` at `0x14038751b`
- `watchdog!WdLogSingleEntry2` at `0x1403877e3`
- `watchdog!WdLogSingleEntry3` at `0x1403875fb`
- `watchdog!WdLogSingleEntry3` at `0x1403876d5`
- `watchdog!WdLogSingleEntry3` at `0x140387c8d`
- `watchdog!WdLogSingleEntry3` at `0x140387ec5`
- `watchdog!WdLogSingleEntry3` at `0x140387ef4`
- `watchdog!WdLogSingleEntry3` at `0x140387f1d`
- `watchdog!WdLogSingleEntry3` at `0x1403875fb`
- `watchdog!WdLogSingleEntry3` at `0x1403876d5`
- `watchdog!WdLogSingleEntry3` at `0x140387c8d`
- `watchdog!WdLogSingleEntry3` at `0x140387ec5`
- `watchdog!WdLogSingleEntry3` at `0x140387ef4`
- `watchdog!WdLogSingleEntry3` at `0x140387f1d`
- `watchdog!WdLogSingleEntry0` at `0x1403878a8`
- `watchdog!WdLogSingleEntry0` at `0x140387949`
- `watchdog!WdLogSingleEntry0` at `0x140387dad`
- `watchdog!WdLogSingleEntry0` at `0x14038807d`
- `watchdog!WdLogSingleEntry0` at `0x1403878a8`
- `watchdog!WdLogSingleEntry0` at `0x140387949`
- `watchdog!WdLogSingleEntry0` at `0x140387dad`
- `watchdog!WdLogSingleEntry0` at `0x14038807d`
- `watchdog!WdLogSingleEntry1` at `0x140387aaf`
- `watchdog!WdLogSingleEntry1` at `0x140387ad6`
- `watchdog!WdLogSingleEntry1` at `0x140387b06`
- `watchdog!WdLogSingleEntry1` at `0x140387aaf`
- `watchdog!WdLogSingleEntry1` at `0x140387ad6`
- `watchdog!WdLogSingleEntry1` at `0x140387b06`

## pseudocode

```c

```
