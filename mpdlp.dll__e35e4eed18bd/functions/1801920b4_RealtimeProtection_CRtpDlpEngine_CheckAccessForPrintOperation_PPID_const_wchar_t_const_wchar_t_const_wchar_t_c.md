# RealtimeProtection::CRtpDlpEngine::CheckAccessForPrintOperation(PPID const &,wchar_t const *,wchar_t const *,wchar_t const *,ulong,ulong *,int *,CommonUtil::CPrinterInformationJSONParser *)

- ea: `0x1801920b4`
- end: `0x1801927b2`
- name: `?CheckAccessForPrintOperation@CRtpDlpEngine@RealtimeProtection@@QEAAJAEBUPPID@@PEB_W11KPEAKPEAHPEAVCPrinterInformationJSONParser@CommonUtil@@@Z`
- size: `1790`
- prototype: `int(RealtimeProtection::CRtpDlpEngine *__hidden this, const struct PPID *, const wchar_t *, const wchar_t *, const wchar_t *, unsigned int, unsigned int *, int *, struct CommonUtil::CPrinterInformationJSONParser *)`
- caller_count: `2`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180141e80`
- `0x18019cbe0`

## callees

- `0x180028a10`
- `0x180040cd8`
- `0x180050300`
- `0x180074f60`
- `0x180075448`
- `0x18007a5c4`
- `0x18007aebc`
- `0x1800809d0`
- `0x180089510`
- `0x18008ac70`
- `0x18010cb40`
- `0x1801920b4`
- `0x1801a37b0`
- `0x1801a590c`
- `0x1801a59fc`
- `0x1801d7938`
- `0x1801d7ff8`
- `0x1801d8054`
- `0x1801d80b0`
- `0x18020cbe8`
- `0x18023a310`

## import_xrefs

- `KERNEL32!Sleep` at `0x180192602`
- `KERNEL32!Sleep` at `0x180192653`
- `KERNEL32!Sleep` at `0x180192602`
- `KERNEL32!Sleep` at `0x180192653`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801923bc`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801926ff`
- `KERNEL32!ReleaseSRWLockShared` at `0x18019274d`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801923bc`
- `KERNEL32!ReleaseSRWLockShared` at `0x1801926ff`
- `KERNEL32!ReleaseSRWLockShared` at `0x18019274d`
- `KERNEL32!DebugBreak` at `0x180192126`
- `KERNEL32!DebugBreak` at `0x180192126`

## string_xrefs

- `0x180192116`: `MpDlp_BreakOnPrintAccessCheck`

## pseudocode

```c

```
