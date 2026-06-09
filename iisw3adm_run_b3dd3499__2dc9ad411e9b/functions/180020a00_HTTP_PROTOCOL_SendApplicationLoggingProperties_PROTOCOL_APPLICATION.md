# HTTP_PROTOCOL::SendApplicationLoggingProperties(PROTOCOL_APPLICATION *)

- ea: `0x180020a00`
- end: `0x180020db6`
- name: `?SendApplicationLoggingProperties@HTTP_PROTOCOL@@UEAAXPEAVPROTOCOL_APPLICATION@@@Z`
- size: `950`
- prototype: `void __fastcall(HTTP_PROTOCOL *__hidden this, struct PROTOCOL_APPLICATION *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800058e4`
- `0x180020a00`
- `0x18005fa64`
- `0x18006101a`
- `0x180061060`

## import_xrefs

- `msvcrt!_ultow` at `0x180020d47`
- `msvcrt!_ultow` at `0x180020d47`
- `iisutil!PuDbgPrint` at `0x180020ad0`
- `iisutil!PuDbgPrint` at `0x180020b29`
- `iisutil!PuDbgPrint` at `0x180020b73`
- `iisutil!PuDbgPrint` at `0x180020be4`
- `iisutil!PuDbgPrint` at `0x180020ad0`
- `iisutil!PuDbgPrint` at `0x180020b29`
- `iisutil!PuDbgPrint` at `0x180020b73`
- `iisutil!PuDbgPrint` at `0x180020be4`
- `iisutil!PuDbgPrintError` at `0x180020ce6`
- `iisutil!PuDbgPrintError` at `0x180020ce6`
- `HTTPAPI!HttpSetUrlGroupProperty` at `0x180020c9b`
- `HTTPAPI!HttpSetUrlGroupProperty` at `0x180020c9b`

## string_xrefs

- `0x180020a8e`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\http_protocol.cxx`
- `0x180020a87`: `HTTP_PROTOCOL::SendApplicationLoggingProperties`
- `0x180020b1d`: `Log File Path: %S\n`
- `0x180020cca`: `Setting config group logging information failed\n`

## pseudocode

```c

```
