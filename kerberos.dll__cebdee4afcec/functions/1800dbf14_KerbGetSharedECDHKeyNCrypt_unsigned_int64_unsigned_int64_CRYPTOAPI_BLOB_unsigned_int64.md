# KerbGetSharedECDHKeyNCrypt(unsigned __int64,unsigned __int64,_CRYPTOAPI_BLOB *,unsigned __int64 *)

- ea: `0x1800dbf14`
- end: `0x1800dc114`
- name: `?KerbGetSharedECDHKeyNCrypt@@YAH_K0PEAU_CRYPTOAPI_BLOB@@PEA_K@Z`
- size: `512`
- prototype: `__int64 __fastcall(NCRYPT_PROV_HANDLE hProvider, NCRYPT_KEY_HANDLE hPrivKey, struct _CRYPTOAPI_BLOB *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180068b20`
- `0x1800690cc`

## callees

- `0x180070680`
- `0x18007108c`
- `0x1800744cf`
- `0x180090aac`
- `0x1800dbf14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dc0de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dc0de`
- `ntdll!RtlNtStatusToDosError` at `0x1800dbfc9`
- `ntdll!RtlNtStatusToDosError` at `0x1800dbfc9`
- `ncrypt!NCryptExportKey` at `0x1800dbfbd`
- `ncrypt!NCryptExportKey` at `0x1800dbfbd`
- `ncrypt!NCryptImportKey` at `0x1800dc0a8`
- `ncrypt!NCryptImportKey` at `0x1800dc0a8`
- `ncrypt!NCryptDeleteKey` at `0x1800dc0f0`
- `ncrypt!NCryptDeleteKey` at `0x1800dc0f0`
- `ncrypt!NCryptSecretAgreement` at `0x1800dc0c4`
- `ncrypt!NCryptSecretAgreement` at `0x1800dc0c4`
- `ncrypt!NCryptGetProperty` at `0x1800dc05a`
- `ncrypt!NCryptGetProperty` at `0x1800dc05a`

## pseudocode

```c

```
