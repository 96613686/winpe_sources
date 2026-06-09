# VIDMM_GLOBAL::ProcessSystemCommand(VIDMM_SYSTEM_COMMAND *,bool,unsigned __int64,_VIDSCH_SYNC_OBJECT *)

- ea: `0x1400e8d90`
- end: `0x1400e98f5`
- name: `?ProcessSystemCommand@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_SYSTEM_COMMAND@@_N_KPEAU_VIDSCH_SYNC_OBJECT@@@Z`
- size: `2917`
- prototype: `__int64 __usercall@<rax>(VIDMM_GLOBAL *__hidden this@<rcx>, struct VIDMM_SYSTEM_COMMAND *@<rdx>, bool@<r8b>, unsigned __int64@<r9>, struct _VIDSCH_SYNC_OBJECT *)`
- caller_count: `1`
- callee_count: `45`
- tags: `broker_com_uri`

## callers

- `0x1400e7114`

## callees

- `0x1400045ec`
- `0x140030fc4`
- `0x1400327ec`
- `0x1400335c4`
- `0x1400336b8`
- `0x14003c554`
- `0x140044fd0`
- `0x140058680`
- `0x140058760`
- `0x140094008`
- `0x1400941c8`
- `0x140095810`
- `0x140095bc4`
- `0x140098f38`
- `0x140099408`
- `0x14009afbc`
- `0x14009b1ac`
- `0x14009b2a8`
- `0x14009c7fc`
- `0x14009ced0`
- `0x14009df00`
- `0x1400a39a8`
- `0x1400a3a40`
- `0x1400a61a4`
- `0x1400a62f4`
- `0x1400a8744`
- `0x1400a8a34`
- `0x1400a9ab8`
- `0x1400ab080`
- `0x1400ab304`
- `0x1400ada50`
- `0x1400b3500`
- `0x1400b3cf0`
- `0x1400b3d94`
- `0x1400b76a8`
- `0x1400b8ed4`
- `0x1400b9430`
- `0x1400b96dc`
- `0x1400bb360`
- `0x1400e0400`
- `0x1400e8d90`
- `0x1400e9900`
- `0x1400fdb18`
- `0x1400fe540`
- `0x140108c64`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x1400e92ac`
- `ntoskrnl!KeCancelTimer` at `0x1400e92ac`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400e9187`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400e9187`
- `ntoskrnl!KeSetEvent` at `0x1400e98c6`
- `ntoskrnl!KeSetEvent` at `0x1400e98e4`
- `ntoskrnl!KeSetEvent` at `0x1400e98c6`
- `ntoskrnl!KeSetEvent` at `0x1400e98e4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e9193`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e9193`
- `watchdog!WdLogSingleEntry5` at `0x1400e91c9`
- `watchdog!WdLogSingleEntry5` at `0x1400e9757`
- `watchdog!WdLogSingleEntry5` at `0x1400e91c9`
- `watchdog!WdLogSingleEntry5` at `0x1400e9757`
- `watchdog!WdLogSingleEntry1` at `0x1400e8f68`
- `watchdog!WdLogSingleEntry1` at `0x1400e979d`
- `watchdog!WdLogSingleEntry1` at `0x1400e8f68`
- `watchdog!WdLogSingleEntry1` at `0x1400e979d`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400e91a4`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400e9731`

## pseudocode

```c

```
