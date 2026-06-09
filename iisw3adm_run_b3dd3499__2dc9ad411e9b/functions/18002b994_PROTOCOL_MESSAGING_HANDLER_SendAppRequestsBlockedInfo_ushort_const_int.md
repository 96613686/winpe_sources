# PROTOCOL_MESSAGING_HANDLER::SendAppRequestsBlockedInfo(ushort const *,int)

- ea: `0x18002b994`
- end: `0x18002bb0e`
- name: `?SendAppRequestsBlockedInfo@PROTOCOL_MESSAGING_HANDLER@@QEAAJPEBGH@Z`
- size: `378`
- prototype: `int(PROTOCOL_MESSAGING_HANDLER *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c8a0`

## callees

- `0x18002b994`
- `0x18002c2f4`
- `0x180061002`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ba47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ba47`
- `iisutil!PuDbgPrint` at `0x18002ba2f`
- `iisutil!PuDbgPrint` at `0x18002ba2f`
- `iisutil!PuDbgPrintError` at `0x18002bada`
- `iisutil!PuDbgPrintError` at `0x18002bada`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002bae5`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002bae5`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002ba3d`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002ba3d`

## string_xrefs

- `0x18002ba28`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol_messaging_handler.cxx`
- `0x18002bacf`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol_messaging_handler.cxx`
- `0x18002baaf`: `Failed copying data into buffer to send\n`
- `0x18002ba0f`: `PROTOCOL_MESSAGING_HANDLER::SendAppRequestsBlockedInfo called \n`
- `0x18002ba16`: `PROTOCOL_MESSAGING_HANDLER::SendAppRequestsBlockedInfo`
- `0x18002bac3`: `PROTOCOL_MESSAGING_HANDLER::SendAppRequestsBlockedInfo`

## pseudocode

```c

```
