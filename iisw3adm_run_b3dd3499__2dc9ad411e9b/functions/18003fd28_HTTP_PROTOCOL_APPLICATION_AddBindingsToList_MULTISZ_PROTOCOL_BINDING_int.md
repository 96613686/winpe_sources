# HTTP_PROTOCOL_APPLICATION::AddBindingsToList(MULTISZ *,PROTOCOL_BINDING *,int)

- ea: `0x18003fd28`
- end: `0x18003feba`
- name: `?AddBindingsToList@HTTP_PROTOCOL_APPLICATION@@AEAAJPEAVMULTISZ@@PEAVPROTOCOL_BINDING@@H@Z`
- size: `402`
- prototype: `int(HTTP_PROTOCOL_APPLICATION *__hidden this, struct MULTISZ *, struct PROTOCOL_BINDING *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016308`
- `0x1800406e0`

## callees

- `0x18003fd28`
- `0x18003fec0`
- `0x180051694`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fe6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fe6f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18003fe96`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18003fe96`
- `iisutil!PuDbgPrint` at `0x18003fdec`
- `iisutil!PuDbgPrint` at `0x18003fdec`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18003fd5d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18003fd5d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18003fe38`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18003fe38`
- `iisutil!?FastAppend@MULTISZ@@QEAAHPEBG@Z` at `0x18003fe4c`
- `iisutil!?FastAppend@MULTISZ@@QEAAHPEBG@Z` at `0x18003fe4c`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x18003fe8b`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x18003fe8b`

## string_xrefs

- `0x18003fdd4`: `HTTP_PROTOCOL_APPLICATION::GetUrl`
- `0x18003fde0`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\http_protocol_application.cxx`

## pseudocode

```c

```
