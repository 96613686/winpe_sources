# DXGMMS_EXPORT::Initialize(uint)

- ea: `0x140243940`
- end: `0x140243c94`
- name: `?Initialize@DXGMMS_EXPORT@@QEAAJI@Z`
- size: `852`
- prototype: `__int64 __fastcall(DXGMMS_EXPORT *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14023c2a4`

## callees

- `0x14001b890`
- `0x14002e110`
- `0x1400a01e0`
- `0x140243940`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140243989`
- `ntoskrnl!RtlInitUnicodeString` at `0x140243989`
- `ntoskrnl!DbgPrintEx` at `0x1402439cc`
- `ntoskrnl!DbgPrintEx` at `0x1402439cc`
- `ntoskrnl!ZwSetSystemInformation` at `0x140243a1a`
- `ntoskrnl!ZwSetSystemInformation` at `0x140243a1a`
- `ntoskrnl!RtlFindExportedRoutineByName` at `0x140243a3b`
- `ntoskrnl!RtlFindExportedRoutineByName` at `0x140243afe`
- `ntoskrnl!RtlFindExportedRoutineByName` at `0x140243b18`
- `ntoskrnl!RtlFindExportedRoutineByName` at `0x140243a3b`
- `ntoskrnl!RtlFindExportedRoutineByName` at `0x140243afe`
- `ntoskrnl!RtlFindExportedRoutineByName` at `0x140243b18`
- `watchdog!WdIsDebuggerPresent` at `0x1402439ad`
- `watchdog!WdIsDebuggerPresent` at `0x1402439ad`
- `watchdog!WdLogSingleEntry2` at `0x140243aa3`
- `watchdog!WdLogSingleEntry2` at `0x140243aa3`
- `watchdog!WdLogSingleEntry5` at `0x1402439f5`
- `watchdog!WdLogSingleEntry5` at `0x1402439f5`
- `watchdog!WdLogSingleEntry1` at `0x140243a5d`
- `watchdog!WdLogSingleEntry1` at `0x140243b78`
- `watchdog!WdLogSingleEntry1` at `0x140243bdb`
- `watchdog!WdLogSingleEntry1` at `0x140243c10`
- `watchdog!WdLogSingleEntry1` at `0x140243c3e`
- `watchdog!WdLogSingleEntry1` at `0x140243a5d`
- `watchdog!WdLogSingleEntry1` at `0x140243b78`
- `watchdog!WdLogSingleEntry1` at `0x140243bdb`
- `watchdog!WdLogSingleEntry1` at `0x140243c10`
- `watchdog!WdLogSingleEntry1` at `0x140243c3e`

## string_xrefs

- `0x14024396c`: `\SystemRoot\System32\drivers\dxgmms1.sys`
- `0x14024397f`: `\SystemRoot\System32\drivers\dxgmms2.sys`
- `0x1402439bf`: `\nAn attempt to load dxgmms1.sys failed with NTSTATUS 0x%x.\nWe broke into the  debugger to allow a chance for debugging this issue.\nAnother attempt to load it will be made now.\n`

## pseudocode

```c

```
