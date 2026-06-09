# RealtimeProtection::CRtpDlpEngine::CheckAccessForFile(DlpFileAccessCheckType,RealtimeProtection::DlpFilePath const &,wchar_t const *,wchar_t const *,PPID const &,_MP_KNOWN_PROCESS_TYPE,std::optional<RealtimeProtection::FileUniqueId> const &,ulong,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,MpDlpResultAccessDecision *,MpDlpResultAccessReason *)

- ea: `0x1800538c4`
- end: `0x1800542b6`
- name: `?CheckAccessForFile@CRtpDlpEngine@RealtimeProtection@@QEAAJW4DlpFileAccessCheckType@@AEBVDlpFilePath@2@PEB_W2AEBUPPID@@W4_MP_KNOWN_PROCESS_TYPE@@AEBV?$optional@VFileUniqueId@RealtimeProtection@@@std@@KKPEAEK6K6KPEAW4MpDlpResultAccessDecision@@PEAW4MpDlpResultAccessReason@@@Z`
- size: `2546`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, int, __int64, RealtimeProtection::DlpEngineUtils *, int, __int64, int, __int64, int, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation`

## callers

- `0x180052190`

## callees

- `0x180021fbc`
- `0x180023460`
- `0x180027a90`
- `0x180029590`
- `0x18002a020`
- `0x180034420`
- `0x180038450`
- `0x180050300`
- `0x1800538c4`
- `0x1800553b4`
- `0x18006aa2c`
- `0x180072520`
- `0x180080030`
- `0x1800809d0`
- `0x1800853e0`
- `0x1800878d0`
- `0x180089fa0`
- `0x18008ac70`
- `0x18008b160`
- `0x180094b40`
- `0x1800964f4`
- `0x1800b7ef0`
- `0x1800cab4c`
- `0x18010cb40`
- `0x180119740`
- `0x18018d9f0`
- `0x18023a290`

## import_xrefs

- `MpClient!MpFreeMemory` at `0x180053afc`
- `MpClient!MpFreeMemory` at `0x180053c8f`
- `MpClient!MpFreeMemory` at `0x180053cf2`
- `MpClient!MpFreeMemory` at `0x180053afc`
- `MpClient!MpFreeMemory` at `0x180053c8f`
- `MpClient!MpFreeMemory` at `0x180053cf2`
- `KERNEL32!ReleaseSRWLockShared` at `0x180053e82`
- `KERNEL32!ReleaseSRWLockShared` at `0x180053e82`
- `KERNEL32!DebugBreak` at `0x180053a97`
- `KERNEL32!DebugBreak` at `0x180053aea`
- `KERNEL32!DebugBreak` at `0x180053a97`
- `KERNEL32!DebugBreak` at `0x180053aea`

## string_xrefs

- `0x180053a10`: `MpDlp_DebugCheckAccessForFile`
- `0x180053a34`: `MpDlp_DebugCheckAccessForFilePath`
- `0x180053c0d`: `MpDlp_BlockAsUnallowedAppAccessForFilePath`

## pseudocode

```c

```
