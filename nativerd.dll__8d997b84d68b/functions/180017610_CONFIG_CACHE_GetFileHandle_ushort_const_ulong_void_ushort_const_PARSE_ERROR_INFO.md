# CONFIG_CACHE::GetFileHandle(ushort const *,ulong *,void * *,ushort const *,PARSE_ERROR_INFO *)

- ea: `0x180017610`
- end: `0x180017805`
- name: `?GetFileHandle@CONFIG_CACHE@@SAJPEBGPEAKPEAPEAX0PEAVPARSE_ERROR_INFO@@@Z`
- size: `501`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *, void **, const unsigned __int16 *, struct PARSE_ERROR_INFO *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x180027888`
- `0x180050238`

## callees

- `0x1800100d0`
- `0x180010468`
- `0x180017610`
- `0x18001bd7c`
- `0x1800412fc`
- `0x1800501d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017645`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017755`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017645`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017755`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001762d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001762d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180017775`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180017775`

## string_xrefs

- `0x18001772a`: `CONFIG_CACHE::GetFileHandle`

## pseudocode

```c

```
