# DotSymAuthCache(_DOT_COMMAND *,DebugClient *)

- ea: `0x1801f8e40`
- end: `0x1801f8fae`
- name: `?DotSymAuthCache@@YAXPEAU_DOT_COMMAND@@PEAVDebugClient@@@Z`
- size: `366`
- prototype: `void __fastcall(struct _DOT_COMMAND *, struct DebugClient *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800727b8`
- `0x1800b94c4`
- `0x1801f8e40`
- `0x1801fb6f4`
- `0x1801fb9a8`
- `0x1801fba8c`
- `0x1801fbb00`
- `0x1801fbc6c`
- `0x1801fbcf0`
- `0x1801fbe44`
- `0x1801fbef8`
- `0x180281aac`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801f8e80`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801f8ea4`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801f8ec8`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801f8eec`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801f8f12`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801f8f38`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801f8f59`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801f8e80`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801f8ea4`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801f8ec8`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801f8eec`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801f8f12`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801f8f38`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801f8f59`

## string_xrefs

- `0x1801f8f70`: `This command allows the user to manage the symbol negative authentication cache.\nThe cache stores URL prefixes (host and path) to skip authentication attempts for servers\nthat repeatedly fail authentication. Protocol and port are automatically stripped.\n\nValid parameters are:\nlist                         List the items in the cache.\nclear                        Clear all items in the cache.\nremove <index>               Removes cached item with given index.\nadd <urlprefix>              Ad`
- `0x1801f8ebe`: `remove`

## pseudocode

```c

```
