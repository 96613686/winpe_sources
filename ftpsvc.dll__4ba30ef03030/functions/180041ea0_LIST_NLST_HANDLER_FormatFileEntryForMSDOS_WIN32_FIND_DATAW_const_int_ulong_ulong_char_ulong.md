# LIST_NLST_HANDLER::FormatFileEntryForMSDOS(_WIN32_FIND_DATAW const *,int,ulong,ulong,char *,ulong *)

- ea: `0x180041ea0`
- end: `0x18004225d`
- name: `?FormatFileEntryForMSDOS@LIST_NLST_HANDLER@@SAJPEBU_WIN32_FIND_DATAW@@HKKPEADPEAK@Z`
- size: `957`
- prototype: `__int64 __fastcall(const struct _WIN32_FIND_DATAW *, int, UINT, int, char *, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003c19c`
- `0x180042760`

## callees

- `0x18002b84c`
- `0x180041ea0`
- `0x180046ff7`
- `0x180047050`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180041f62`
- `KERNEL32!GetLastError` at `0x180041fce`
- `KERNEL32!GetLastError` at `0x180041f62`
- `KERNEL32!GetLastError` at `0x180041fce`
- `KERNEL32!FileTimeToLocalFileTime` at `0x180041f58`
- `KERNEL32!FileTimeToLocalFileTime` at `0x180041f58`
- `KERNEL32!FileTimeToSystemTime` at `0x180041fc4`
- `KERNEL32!FileTimeToSystemTime` at `0x180041fc4`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180041ef9`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180041ef9`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18004222b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18004222b`
- `iisutil!PuDbgPrintError` at `0x180041faf`
- `iisutil!PuDbgPrintError` at `0x180041faf`

## string_xrefs

- `0x180041fa1`: `inetsrv\iis\iisrearc\ftp\server\ftp_protocol\list_nlst_handler.cxx`

## pseudocode

```c

```
