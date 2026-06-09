# HTTP_PROTOCOL::SendApplicationUrls(HTTP_PROTOCOL_APPLICATION *,MULTISZ *)

- ea: `0x18002130c`
- end: `0x180021646`
- name: `?SendApplicationUrls@HTTP_PROTOCOL@@QEAAXPEAVHTTP_PROTOCOL_APPLICATION@@PEAVMULTISZ@@@Z`
- size: `826`
- prototype: `void __fastcall(HTTP_PROTOCOL *__hidden this, struct HTTP_PROTOCOL_APPLICATION *, struct MULTISZ *)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800144e0`
- `0x180016308`
- `0x1800205f0`
- `0x1800217e0`

## callees

- `0x1800058e4`
- `0x180014430`
- `0x1800144e0`
- `0x18002130c`
- `0x180061060`

## import_xrefs

- `msvcrt!_ultow` at `0x18002153d`
- `msvcrt!_ultow` at `0x1800215bf`
- `msvcrt!_ultow` at `0x18002153d`
- `msvcrt!_ultow` at `0x1800215bf`
- `iisutil!PuDbgPrint` at `0x180021458`
- `iisutil!PuDbgPrint` at `0x180021458`
- `iisutil!PuDbgPrintError` at `0x180021504`
- `iisutil!PuDbgPrintError` at `0x180021504`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x18002136a`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x18002136a`
- `HTTPAPI!HttpAddUrlToUrlGroup` at `0x180021485`
- `HTTPAPI!HttpAddUrlToUrlGroup` at `0x180021485`

## string_xrefs

- `0x180021436`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\http_protocol.cxx`
- `0x1800214f3`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\http_protocol.cxx`
- `0x180021428`: `HTTP_PROTOCOL::SendApplicationUrls`
- `0x1800214e7`: `HTTP_PROTOCOL::SendApplicationUrls`
- `0x1800214db`: `Adding URL to config group failed: %S\n`

## pseudocode

```c

```
