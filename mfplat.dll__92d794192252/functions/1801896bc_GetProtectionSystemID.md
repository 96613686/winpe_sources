# GetProtectionSystemID

- ea: `0x1801896bc`
- end: `0x180189869`
- name: `GetProtectionSystemID`
- size: `429`
- prototype: `__int64 __fastcall(LPIID lpiid)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800fcd50`
- `0x18018ae70`

## callees

- `0x1800255b0`
- `0x180038bf0`
- `0x1801200d0`
- `0x180120ecc`
- `0x180125958`
- `0x1801896bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18018976b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18018976b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18018983f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18018983f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18018971f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18018971f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801897c4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801897c4`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1801897dc`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1801897dc`

## string_xrefs

- `0x180189711`: `Software\Microsoft\MediaEngine\MediaExtensions\EME\CDMS`

## pseudocode

```c

```
