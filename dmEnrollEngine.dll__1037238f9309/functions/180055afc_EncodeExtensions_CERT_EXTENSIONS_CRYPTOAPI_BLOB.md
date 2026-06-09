# EncodeExtensions(_CERT_EXTENSIONS *,_CRYPTOAPI_BLOB *)

- ea: `0x180055afc`
- end: `0x180055bb0`
- name: `?EncodeExtensions@@YAJPEAU_CERT_EXTENSIONS@@PEAU_CRYPTOAPI_BLOB@@@Z`
- size: `180`
- prototype: `__int64 __fastcall(struct _CERT_EXTENSIONS *pvStructInfo, DWORD *pcbEncoded)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180056d24`

## callees

- `0x180014148`
- `0x18001ab40`
- `0x1800206a8`
- `0x180055afc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055b79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055b79`
- `CRYPT32!CryptEncodeObject` at `0x180055b30`
- `CRYPT32!CryptEncodeObject` at `0x180055b69`
- `CRYPT32!CryptEncodeObject` at `0x180055b30`
- `CRYPT32!CryptEncodeObject` at `0x180055b69`

## pseudocode

```c

```
