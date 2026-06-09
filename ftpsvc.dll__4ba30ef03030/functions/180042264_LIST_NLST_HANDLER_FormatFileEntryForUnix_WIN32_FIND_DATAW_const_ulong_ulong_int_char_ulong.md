# LIST_NLST_HANDLER::FormatFileEntryForUnix(_WIN32_FIND_DATAW const *,ulong,ulong,int,char *,ulong *)

- ea: `0x180042264`
- end: `0x180042536`
- name: `?FormatFileEntryForUnix@LIST_NLST_HANDLER@@SAJPEBU_WIN32_FIND_DATAW@@KKHPEADPEAK@Z`
- size: `722`
- prototype: `__int64 __fastcall(const struct _WIN32_FIND_DATAW *, UINT, int, int, char *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003c19c`
- `0x180042760`

## callees

- `0x18002b84c`
- `0x180042264`
- `0x180047050`

## import_xrefs

- `msvcrt!sprintf_s` at `0x1800423e2`
- `msvcrt!sprintf_s` at `0x1800423f4`
- `msvcrt!sprintf_s` at `0x18004241a`
- `msvcrt!sprintf_s` at `0x1800424f5`
- `msvcrt!sprintf_s` at `0x1800423e2`
- `msvcrt!sprintf_s` at `0x1800423f4`
- `msvcrt!sprintf_s` at `0x18004241a`
- `msvcrt!sprintf_s` at `0x1800424f5`
- `KERNEL32!GetSystemTime` at `0x180042303`
- `KERNEL32!GetSystemTime` at `0x180042303`
- `KERNEL32!GetLastError` at `0x180042327`
- `KERNEL32!GetLastError` at `0x180042391`
- `KERNEL32!GetLastError` at `0x180042327`
- `KERNEL32!GetLastError` at `0x180042391`
- `KERNEL32!FileTimeToLocalFileTime` at `0x18004231d`
- `KERNEL32!FileTimeToLocalFileTime` at `0x18004231d`
- `KERNEL32!GetLocalTime` at `0x18004230f`
- `KERNEL32!GetLocalTime` at `0x18004230f`
- `KERNEL32!FileTimeToSystemTime` at `0x180042387`
- `KERNEL32!FileTimeToSystemTime` at `0x180042387`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800422d3`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800422d3`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180042503`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180042503`
- `iisutil!PuDbgPrintError` at `0x180042374`
- `iisutil!PuDbgPrintError` at `0x180042374`

## string_xrefs

- `0x180042366`: `inetsrv\iis\iisrearc\ftp\server\ftp_protocol\list_nlst_handler.cxx`

## pseudocode

```c

```
