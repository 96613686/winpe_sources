# BITSGetVolumeSerialNumber(ushort const *)

- ea: `0x1800141cc`
- end: `0x1800142fc`
- name: `?BITSGetVolumeSerialNumber@@YAKPEBG@Z`
- size: `304`
- prototype: `unsigned int __fastcall(LPCWSTR lpRootPathName)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c9c4`
- `0x180028d60`
- `0x180096bc4`

## callees

- `0x18000db20`
- `0x1800141cc`
- `0x180014310`
- `0x1800544a0`
- `0x18009e9c8`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800142da`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800142da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014207`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014289`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014207`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014289`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800141eb`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800141eb`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18001427f`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18001427f`

## pseudocode

```c

```
