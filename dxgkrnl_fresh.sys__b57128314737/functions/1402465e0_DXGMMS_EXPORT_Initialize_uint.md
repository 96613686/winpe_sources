# DXGMMS_EXPORT::Initialize(uint)

- ea: `0x1402465e0`
- end: `0x140246934`
- name: `?Initialize@DXGMMS_EXPORT@@QEAAJI@Z`
- size: `852`
- prototype: `__int64 __fastcall(DXGMMS_EXPORT *this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14023ee04`

## callees

- `0x14001b9c0`
- `0x14002e2e0`
- `0x1400a0cb0`
- `0x1402465e0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140246629`
- `ntoskrnl!RtlInitUnicodeString` at `0x140246629`
- `ntoskrnl!DbgPrintEx` at `0x14024666c`
- `ntoskrnl!DbgPrintEx` at `0x14024666c`
- `ntoskrnl!ZwSetSystemInformation` at `0x1402466ba`
- `ntoskrnl!ZwSetSystemInformation` at `0x1402466ba`
- `ntoskrnl!RtlFindExportedRoutineByName` at `0x1402466db`
- `ntoskrnl!RtlFindExportedRoutineByName` at `0x14024679e`
- `ntoskrnl!RtlFindExportedRoutineByName` at `0x1402467b8`
- `ntoskrnl!RtlFindExportedRoutineByName` at `0x1402466db`
- `ntoskrnl!RtlFindExportedRoutineByName` at `0x14024679e`
- `ntoskrnl!RtlFindExportedRoutineByName` at `0x1402467b8`
- `watchdog!WdIsDebuggerPresent` at `0x14024664d`
- `watchdog!WdIsDebuggerPresent` at `0x14024664d`
- `watchdog!WdLogSingleEntry2` at `0x140246743`
- `watchdog!WdLogSingleEntry2` at `0x140246743`
- `watchdog!WdLogSingleEntry5` at `0x140246695`
- `watchdog!WdLogSingleEntry5` at `0x140246695`
- `watchdog!WdLogSingleEntry1` at `0x1402466fd`
- `watchdog!WdLogSingleEntry1` at `0x140246818`
- `watchdog!WdLogSingleEntry1` at `0x14024687b`
- `watchdog!WdLogSingleEntry1` at `0x1402468b0`
- `watchdog!WdLogSingleEntry1` at `0x1402468de`
- `watchdog!WdLogSingleEntry1` at `0x1402466fd`
- `watchdog!WdLogSingleEntry1` at `0x140246818`
- `watchdog!WdLogSingleEntry1` at `0x14024687b`
- `watchdog!WdLogSingleEntry1` at `0x1402468b0`
- `watchdog!WdLogSingleEntry1` at `0x1402468de`

## string_xrefs

- `0x14024661f`: `\SystemRoot\System32\drivers\dxgmms2.sys`
- `0x14024660c`: `\SystemRoot\System32\drivers\dxgmms1.sys`
- `0x14024665f`: `\nAn attempt to load dxgmms1.sys failed with NTSTATUS 0x%x.\nWe broke into the  debugger to allow a chance for debugging this issue.\nAnother attempt to load it will be made now.\n`

## pseudocode

```c

```
