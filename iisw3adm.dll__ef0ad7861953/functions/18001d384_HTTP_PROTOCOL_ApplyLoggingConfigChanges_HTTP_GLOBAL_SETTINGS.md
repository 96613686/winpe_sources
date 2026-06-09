# HTTP_PROTOCOL::ApplyLoggingConfigChanges(HTTP_GLOBAL_SETTINGS *)

- ea: `0x18001d384`
- end: `0x18001d682`
- name: `?ApplyLoggingConfigChanges@HTTP_PROTOCOL@@AEAAXPEAVHTTP_GLOBAL_SETTINGS@@@Z`
- size: `766`
- prototype: `void __fastcall(HTTP_WRAPPER **this, struct HTTP_GLOBAL_SETTINGS *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001d170`

## callees

- `0x1800058e4`
- `0x18001d384`
- `0x18005fccc`
- `0x18005fee8`
- `0x180061060`

## import_xrefs

- `msvcrt!_ultow` at `0x18001d46d`
- `msvcrt!_ultow` at `0x18001d47d`
- `msvcrt!_ultow` at `0x18001d58e`
- `msvcrt!_ultow` at `0x18001d59e`
- `msvcrt!_ultow` at `0x18001d46d`
- `msvcrt!_ultow` at `0x18001d47d`
- `msvcrt!_ultow` at `0x18001d58e`
- `msvcrt!_ultow` at `0x18001d59e`
- `iisutil!PuDbgPrintError` at `0x18001d654`
- `iisutil!PuDbgPrintError` at `0x18001d654`

## string_xrefs

- `0x18001d63f`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\http_protocol.cxx`
- `0x18001d508`: `Changing binary control channel logging info failed\n   LogPeriod = %d \n   LogFileTruncateSize = %d \n   LogFileDirectory = %S \n   LocalFiletimeRollover = %S \n`
- `0x18001d633`: `HTTP_PROTOCOL::ApplyLoggingConfigChanges`
- `0x18001d625`: `Changing w3c control channel logging info failed\n   LogPeriod = %d \n   LogFileTruncateSize = %d \n   LogFileDirectory = %S \n   LocalFiletimeRollover = %S \n`

## pseudocode

```c

```
