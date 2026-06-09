# ADAPTER_RENDER::GetUmdFileVersion(_LARGE_INTEGER *)

- ea: `0x140363030`
- end: `0x140363434`
- name: `?GetUmdFileVersion@ADAPTER_RENDER@@QEAAJPEAT_LARGE_INTEGER@@@Z`
- size: `1028`
- prototype: `__int64 __fastcall(ADAPTER_RENDER *__hidden this, union _LARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x14035fa00`

## callees

- `0x140009030`
- `0x14000d7d0`
- `0x14001b890`
- `0x140363030`
- `0x1403634ec`
- `0x140363640`

## import_xrefs

- `ntoskrnl!wcsnlen` at `0x14036314b`
- `ntoskrnl!wcsnlen` at `0x14036329a`
- `ntoskrnl!wcsnlen` at `0x14036314b`
- `ntoskrnl!wcsnlen` at `0x14036329a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14036323c`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14036324f`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140363375`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140363388`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1403633b3`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14036323c`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14036324f`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140363375`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140363388`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1403633b3`
- `watchdog!WdLogSingleEntry2` at `0x1403633e5`
- `watchdog!WdLogSingleEntry2` at `0x1403633e5`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14036327e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14036327e`
- `watchdog!WdLogSingleEntry0` at `0x140363068`
- `watchdog!WdLogSingleEntry0` at `0x140363167`
- `watchdog!WdLogSingleEntry0` at `0x1403632b6`
- `watchdog!WdLogSingleEntry0` at `0x140363068`
- `watchdog!WdLogSingleEntry0` at `0x140363167`
- `watchdog!WdLogSingleEntry0` at `0x1403632b6`
- `watchdog!WdLogSingleEntry1` at `0x1403631f3`
- `watchdog!WdLogSingleEntry1` at `0x14036334f`
- `watchdog!WdLogSingleEntry1` at `0x1403631f3`
- `watchdog!WdLogSingleEntry1` at `0x14036334f`

## string_xrefs

- `0x14036336a`: `\Systemroot\System32\`
- `0x1403633f6`: `Failed to open the user mode driver DLL on adapter %I64d (ntStatus = %I64d).`

## pseudocode

```c

```
