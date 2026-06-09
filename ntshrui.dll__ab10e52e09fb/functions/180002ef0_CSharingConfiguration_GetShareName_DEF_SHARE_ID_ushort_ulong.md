# CSharingConfiguration::_GetShareName(DEF_SHARE_ID,ushort *,ulong)

- ea: `0x180002ef0`
- end: `0x180002fbd`
- name: `?_GetShareName@CSharingConfiguration@@AEAAJW4DEF_SHARE_ID@@PEAGK@Z`
- size: `205`
- prototype: `int(CSharingConfiguration *__hidden this, enum DEF_SHARE_ID, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180003010`

## callees

- `0x180002ef0`
- `0x180023f4c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002f34`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002f34`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002f82`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002f82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002fa5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002fa5`

## pseudocode

```c

```
