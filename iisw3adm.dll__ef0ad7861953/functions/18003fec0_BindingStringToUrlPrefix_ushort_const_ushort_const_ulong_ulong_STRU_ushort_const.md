# BindingStringToUrlPrefix(ushort const *,ushort const *,ulong,ulong,STRU *,ushort const * *)

- ea: `0x18003fec0`
- end: `0x18004063d`
- name: `?BindingStringToUrlPrefix@@YAJPEBG0KKPEAVSTRU@@PEAPEBG@Z`
- size: `1917`
- prototype: `__int64 __fastcall(wchar_t *String, const unsigned __int16 *, unsigned int, unsigned int, struct STRU *, const unsigned __int16 **)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003fd28`
- `0x1800588e8`
- `0x18005b640`

## callees

- `0x180005878`
- `0x18003fec0`
- `0x180061060`

## import_xrefs

- `msvcrt!wcstoul` at `0x180040191`
- `msvcrt!wcstoul` at `0x180040245`
- `msvcrt!wcstoul` at `0x180040191`
- `msvcrt!wcstoul` at `0x180040245`
- `msvcrt!wcschr` at `0x18003ff56`
- `msvcrt!wcschr` at `0x1800400f2`
- `msvcrt!wcschr` at `0x180040114`
- `msvcrt!wcschr` at `0x18003ff56`
- `msvcrt!wcschr` at `0x1800400f2`
- `msvcrt!wcschr` at `0x180040114`
- `msvcrt!_ultow` at `0x1800405cf`
- `msvcrt!_ultow` at `0x1800405cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040328`
- `api-ms-win-core-normalization-l1-1-0!IdnToNameprepUnicode` at `0x18004031e`
- `api-ms-win-core-normalization-l1-1-0!IdnToNameprepUnicode` at `0x18004036c`
- `api-ms-win-core-normalization-l1-1-0!IdnToNameprepUnicode` at `0x18004031e`
- `api-ms-win-core-normalization-l1-1-0!IdnToNameprepUnicode` at `0x18004036c`
- `iisutil!PuDbgPrint` at `0x1800405aa`
- `iisutil!PuDbgPrint` at `0x1800405aa`
- `iisutil!PuDbgPrintError` at `0x18003ffa5`
- `iisutil!PuDbgPrintError` at `0x180040088`
- `iisutil!PuDbgPrintError` at `0x1800400d8`
- `iisutil!PuDbgPrintError` at `0x1800402e1`
- `iisutil!PuDbgPrintError` at `0x18003ffa5`
- `iisutil!PuDbgPrintError` at `0x180040088`
- `iisutil!PuDbgPrintError` at `0x1800400d8`
- `iisutil!PuDbgPrintError` at `0x1800402e1`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180040604`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180040612`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180040604`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180040612`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800403f4`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800403f4`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18004034d`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18004034d`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18004029d`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18004044a`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18004047e`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x1800404b0`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180040512`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18004053f`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18004029d`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18004044a`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18004047e`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x1800404b0`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180040512`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18004053f`

## string_xrefs

- `0x18003ff9e`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\http_protocol_application.cxx`
- `0x18004005f`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\http_protocol_application.cxx`
- `0x1800400c3`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\http_protocol_application.cxx`
- `0x1800402d6`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\http_protocol_application.cxx`
- `0x180040587`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\http_protocol_application.cxx`

## pseudocode

```c

```
