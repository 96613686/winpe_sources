# DpiPersistence::CreateMonitorSetId(_LUID const &,uint,_UNICODE_STRING *,bool *)

- ea: `0x140230998`
- end: `0x140231087`
- name: `?CreateMonitorSetId@DpiPersistence@@YAJAEBU_LUID@@IPEAU_UNICODE_STRING@@PEA_N@Z`
- size: `1775`
- prototype: `__int64 __fastcall(struct _LUID *this, const struct _LUID *, unsigned int, struct _UNICODE_STRING *, bool *)`
- caller_count: `1`
- callee_count: `22`
- tags: ``

## callers

- `0x1403dc838`

## callees

- `0x140012540`
- `0x140015618`
- `0x140015940`
- `0x14001716c`
- `0x14001b9c0`
- `0x14001f630`
- `0x14002ee60`
- `0x140032a40`
- `0x140034a44`
- `0x140036ee8`
- `0x140039258`
- `0x140039568`
- `0x140046d28`
- `0x14006627c`
- `0x1400a0bd0`
- `0x140230850`
- `0x140230998`
- `0x14031498c`
- `0x140316a28`
- `0x140329ff0`
- `0x14032a5c4`
- `0x14036a520`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1402309e7`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140230a15`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1402309e7`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140230a15`
- `watchdog!WdLogSingleEntry2` at `0x1402309ff`
- `watchdog!WdLogSingleEntry2` at `0x140230d78`
- `watchdog!WdLogSingleEntry2` at `0x140230e15`
- `watchdog!WdLogSingleEntry2` at `0x1402309ff`
- `watchdog!WdLogSingleEntry2` at `0x140230d78`
- `watchdog!WdLogSingleEntry2` at `0x140230e15`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140231032`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140231032`
- `watchdog!WdLogSingleEntry3` at `0x140230b31`
- `watchdog!WdLogSingleEntry3` at `0x140230cee`
- `watchdog!WdLogSingleEntry3` at `0x140230b31`
- `watchdog!WdLogSingleEntry3` at `0x140230cee`
- `watchdog!WdLogSingleEntry0` at `0x140230a71`
- `watchdog!WdLogSingleEntry0` at `0x140230b8e`
- `watchdog!WdLogSingleEntry0` at `0x140230c12`
- `watchdog!WdLogSingleEntry0` at `0x140230c66`
- `watchdog!WdLogSingleEntry0` at `0x140230ff9`
- `watchdog!WdLogSingleEntry0` at `0x140230a71`
- `watchdog!WdLogSingleEntry0` at `0x140230b8e`
- `watchdog!WdLogSingleEntry0` at `0x140230c12`
- `watchdog!WdLogSingleEntry0` at `0x140230c66`
- `watchdog!WdLogSingleEntry0` at `0x140230ff9`
- `watchdog!WdLogSingleEntry1` at `0x140230abe`
- `watchdog!WdLogSingleEntry1` at `0x140230abe`

## string_xrefs

- `0x140230d0b`: `Failed (0x%I64x) to acquire shared access for adapter LUID: 0x%I64x%08I64x`

## pseudocode

```c

```
