# DpiPersistence::CreateMonitorSetId(_LUID const &,uint,_UNICODE_STRING *,bool *)

- ea: `0x14022de84`
- end: `0x14022e573`
- name: `?CreateMonitorSetId@DpiPersistence@@YAJAEBU_LUID@@IPEAU_UNICODE_STRING@@PEA_N@Z`
- size: `1775`
- prototype: `__int64 __fastcall(struct _LUID *this, const struct _LUID *, unsigned int, struct _UNICODE_STRING *, bool *)`
- caller_count: `1`
- callee_count: `22`
- tags: ``

## callers

- `0x1403dc418`

## callees

- `0x140012380`
- `0x140015458`
- `0x140015780`
- `0x140016fac`
- `0x14001b890`
- `0x14001f460`
- `0x14002ec90`
- `0x140032870`
- `0x140034874`
- `0x140036d18`
- `0x140038ff8`
- `0x140039308`
- `0x140046ac8`
- `0x140065e5c`
- `0x1400a0100`
- `0x14022dd3c`
- `0x14022de84`
- `0x14030dc1c`
- `0x14030fcb0`
- `0x140323280`
- `0x140323854`
- `0x14036a4e0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14022ded3`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14022df01`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14022ded3`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14022df01`
- `watchdog!WdLogSingleEntry2` at `0x14022deeb`
- `watchdog!WdLogSingleEntry2` at `0x14022e264`
- `watchdog!WdLogSingleEntry2` at `0x14022e301`
- `watchdog!WdLogSingleEntry2` at `0x14022deeb`
- `watchdog!WdLogSingleEntry2` at `0x14022e264`
- `watchdog!WdLogSingleEntry2` at `0x14022e301`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14022e51e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14022e51e`
- `watchdog!WdLogSingleEntry3` at `0x14022e01d`
- `watchdog!WdLogSingleEntry3` at `0x14022e1da`
- `watchdog!WdLogSingleEntry3` at `0x14022e01d`
- `watchdog!WdLogSingleEntry3` at `0x14022e1da`
- `watchdog!WdLogSingleEntry0` at `0x14022df5d`
- `watchdog!WdLogSingleEntry0` at `0x14022e07a`
- `watchdog!WdLogSingleEntry0` at `0x14022e0fe`
- `watchdog!WdLogSingleEntry0` at `0x14022e152`
- `watchdog!WdLogSingleEntry0` at `0x14022e4e5`
- `watchdog!WdLogSingleEntry0` at `0x14022df5d`
- `watchdog!WdLogSingleEntry0` at `0x14022e07a`
- `watchdog!WdLogSingleEntry0` at `0x14022e0fe`
- `watchdog!WdLogSingleEntry0` at `0x14022e152`
- `watchdog!WdLogSingleEntry0` at `0x14022e4e5`
- `watchdog!WdLogSingleEntry1` at `0x14022dfaa`
- `watchdog!WdLogSingleEntry1` at `0x14022dfaa`

## string_xrefs

- `0x14022e1f7`: `Failed (0x%I64x) to acquire shared access for adapter LUID: 0x%I64x%08I64x`

## pseudocode

```c

```
