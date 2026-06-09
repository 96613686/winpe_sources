# EncodeExtensions(_CERT_EXTENSIONS *,_CRYPTOAPI_BLOB *)

- ea: `0x180033aa0`
- end: `0x180033baf`
- name: `?EncodeExtensions@@YAJPEAU_CERT_EXTENSIONS@@PEAU_CRYPTOAPI_BLOB@@@Z`
- size: `271`
- prototype: `__int64 __fastcall(struct _CERT_EXTENSIONS *pvStructInfo, DWORD *pcbEncoded)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180037648`

## callees

- `0x180033aa0`
- `0x180044e94`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033b07`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033b07`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033b88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033b88`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033af0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033b74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033af0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033b74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033b4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033b4c`
- `CRYPT32!CryptEncodeObject` at `0x180033ad9`
- `CRYPT32!CryptEncodeObject` at `0x180033b36`
- `CRYPT32!CryptEncodeObject` at `0x180033ad9`
- `CRYPT32!CryptEncodeObject` at `0x180033b36`

## pseudocode

```c

```
