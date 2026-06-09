# ExtractAutoUpdateCtlFromCab(ulong,_CRYPT_BLOB_ARRAY *)

- ea: `0x18003a800`
- end: `0x18003a95e`
- name: `?ExtractAutoUpdateCtlFromCab@@YAPEBU_CTL_CONTEXT@@KPEAU_CRYPT_BLOB_ARRAY@@@Z`
- size: `350`
- prototype: `const struct _CTL_CONTEXT *__fastcall(int, struct _CRYPT_BLOB_ARRAY *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x18001c684`
- `0x18003a2bc`

## callees

- `0x18002c860`
- `0x180034270`
- `0x18003a800`
- `0x18003a964`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a8e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a8ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801177f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a8e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a8ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801177f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a8c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a8f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a952`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a8c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a8f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a952`
- `ntdll!ShipAssert` at `0x18003a8f1`
- `ntdll!ShipAssert` at `0x180117802`
- `ntdll!ShipAssert` at `0x18003a8f1`
- `ntdll!ShipAssert` at `0x180117802`

## pseudocode

```c

```
