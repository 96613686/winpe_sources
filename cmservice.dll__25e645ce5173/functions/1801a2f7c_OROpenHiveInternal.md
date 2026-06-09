# OROpenHiveInternal

- ea: `0x1801a2f7c`
- end: `0x1801a3181`
- name: `OROpenHiveInternal`
- size: `517`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180199f54`

## callees

- `0x1800055d0`
- `0x1800055dc`
- `0x180037bc4`
- `0x1801a2ee0`
- `0x1801a2f7c`
- `0x1801a57f8`
- `0x1801a69d4`
- `0x1801a6a14`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1801a30df`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1801a30df`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801a310e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801a310e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a301b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a309a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a30f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a301b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a309a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a30f0`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801a308a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801a308a`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1801a300b`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1801a300b`

## string_xrefs

- `0x1801a30d3`: `ntdll.dll`
- `0x1801a3104`: `RtlValidRelativeSecurityDescriptor`

## pseudocode

```c

```
