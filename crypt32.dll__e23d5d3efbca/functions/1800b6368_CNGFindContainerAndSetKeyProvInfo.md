# CNGFindContainerAndSetKeyProvInfo

- ea: `0x1800b6368`
- end: `0x1800b64b9`
- name: `CNGFindContainerAndSetKeyProvInfo`
- size: `337`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, NCRYPT_PROV_HANDLE hProvider)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800b4580`

## callees

- `0x180014790`
- `0x1800700a0`
- `0x1800b6368`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6451`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6451`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b649d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b649d`
- `ncrypt!NCryptOpenKey` at `0x1800b63e9`
- `ncrypt!NCryptOpenKey` at `0x1800b63e9`
- `ncrypt!NCryptFreeObject` at `0x1800b6462`
- `ncrypt!NCryptFreeObject` at `0x1800b6462`
- `ncrypt!NCryptEnumKeys` at `0x1800b63c5`
- `ncrypt!NCryptEnumKeys` at `0x1800b63c5`
- `ncrypt!NCryptFreeBuffer` at `0x1800b6475`
- `ncrypt!NCryptFreeBuffer` at `0x1800b6491`
- `ncrypt!NCryptFreeBuffer` at `0x1800b6475`
- `ncrypt!NCryptFreeBuffer` at `0x1800b6491`

## pseudocode

```c

```
