# ExpandCommandLinePiece(ushort *,_UNICODE_STRING *,void *)

- ea: `0x18002354c`
- end: `0x1800236a3`
- name: `?ExpandCommandLinePiece@@YAJPEAGPEAU_UNICODE_STRING@@PEAX@Z`
- size: `343`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PUNICODE_STRING Destination, PWSTR Environment)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800259d8`

## callees

- `0x18002354c`

## import_xrefs

- `ntdll!RtlExpandEnvironmentStrings_U` at `0x180023633`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x180023633`
- `ntdll!RtlInitUnicodeStringEx` at `0x180023583`
- `ntdll!RtlInitUnicodeStringEx` at `0x180023583`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800235cb`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800235cb`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002368a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002368a`
- `iisutil!PuDbgPrintError` at `0x18002361b`
- `iisutil!PuDbgPrintError` at `0x180023677`
- `iisutil!PuDbgPrintError` at `0x18002361b`
- `iisutil!PuDbgPrintError` at `0x180023677`

## string_xrefs

- `0x180023614`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x18002366c`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x1800235ff`: `ExpandCommandLinePiece`
- `0x180023660`: `ExpandCommandLinePiece`

## pseudocode

```c

```
