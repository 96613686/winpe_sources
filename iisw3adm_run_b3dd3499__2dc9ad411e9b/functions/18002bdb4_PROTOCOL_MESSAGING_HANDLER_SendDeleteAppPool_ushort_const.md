# PROTOCOL_MESSAGING_HANDLER::SendDeleteAppPool(ushort const *)

- ea: `0x18002bdb4`
- end: `0x18002bf19`
- name: `?SendDeleteAppPool@PROTOCOL_MESSAGING_HANDLER@@QEAAJPEBG@Z`
- size: `357`
- prototype: `int(PROTOCOL_MESSAGING_HANDLER *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c550`

## callees

- `0x18002bdb4`
- `0x18002c2f4`
- `0x180061002`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002be5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002be5d`
- `iisutil!PuDbgPrint` at `0x18002be46`
- `iisutil!PuDbgPrint` at `0x18002be46`
- `iisutil!PuDbgPrintError` at `0x18002bee9`
- `iisutil!PuDbgPrintError` at `0x18002bee9`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002bef4`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002bef4`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002be53`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002be53`

## string_xrefs

- `0x18002be3f`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol_messaging_handler.cxx`
- `0x18002bede`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol_messaging_handler.cxx`
- `0x18002bebe`: `Failed copying data into buffer to send\n`
- `0x18002be26`: `PROTOCOL_MESSAGING_HANDLER::SendDeleteAppPool called \n`
- `0x18002be2d`: `PROTOCOL_MESSAGING_HANDLER::SendDeleteAppPool`
- `0x18002bed2`: `PROTOCOL_MESSAGING_HANDLER::SendDeleteAppPool`

## pseudocode

```c

```
