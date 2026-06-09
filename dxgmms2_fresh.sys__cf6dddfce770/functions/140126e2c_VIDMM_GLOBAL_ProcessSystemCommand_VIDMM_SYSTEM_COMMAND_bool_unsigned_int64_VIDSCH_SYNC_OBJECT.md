# VIDMM_GLOBAL::ProcessSystemCommand(VIDMM_SYSTEM_COMMAND *,bool,unsigned __int64,_VIDSCH_SYNC_OBJECT *)

- ea: `0x140126e2c`
- end: `0x14012795c`
- name: `?ProcessSystemCommand@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_SYSTEM_COMMAND@@_N_KPEAU_VIDSCH_SYNC_OBJECT@@@Z`
- size: `2864`
- prototype: `__int64 __usercall@<rax>(VIDMM_GLOBAL *__hidden this@<rcx>, struct VIDMM_SYSTEM_COMMAND *@<rdx>, bool@<r8b>, unsigned __int64@<r9>, struct _VIDSCH_SYNC_OBJECT *)`
- caller_count: `1`
- callee_count: `44`
- tags: `broker_com_uri`

## callers

- `0x1400eb75c`

## callees

- `0x140004268`
- `0x14002eba4`
- `0x1400305ac`
- `0x140031434`
- `0x14003196c`
- `0x14003b264`
- `0x1400451d4`
- `0x140058f50`
- `0x140059030`
- `0x140096a04`
- `0x140096f40`
- `0x140097100`
- `0x140097580`
- `0x140097be8`
- `0x140099360`
- `0x140099714`
- `0x14009ca80`
- `0x14009cf50`
- `0x14009eb04`
- `0x14009ecf4`
- `0x14009edf0`
- `0x1400a00dc`
- `0x1400a0358`
- `0x1400a6a34`
- `0x1400a6b84`
- `0x1400a9b88`
- `0x1400aac08`
- `0x1400ac0c8`
- `0x1400ac6b4`
- `0x1400aefa0`
- `0x1400b4b40`
- `0x1400b762c`
- `0x1400b76d0`
- `0x1400bb090`
- `0x1400bc8bc`
- `0x1400bce18`
- `0x1400bd0c4`
- `0x1400bee00`
- `0x1400e8860`
- `0x1400ff470`
- `0x140105a00`
- `0x140106010`
- `0x14010cfa4`
- `0x140126e2c`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x140126ff1`
- `ntoskrnl!KeCancelTimer` at `0x140126ff1`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14012775e`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14012775e`
- `ntoskrnl!KeSetEvent` at `0x1401278e2`
- `ntoskrnl!KeSetEvent` at `0x140127925`
- `ntoskrnl!KeSetEvent` at `0x1401278e2`
- `ntoskrnl!KeSetEvent` at `0x140127925`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14012776a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14012776a`
- `watchdog!WdLogSingleEntry5` at `0x1401277cd`
- `watchdog!WdLogSingleEntry5` at `0x1401277cd`
- `watchdog!WdLogSingleEntry1` at `0x14012735e`
- `watchdog!WdLogSingleEntry1` at `0x140127828`
- `watchdog!WdLogSingleEntry1` at `0x14012735e`
- `watchdog!WdLogSingleEntry1` at `0x140127828`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1401277a7`

## pseudocode

```c

```
