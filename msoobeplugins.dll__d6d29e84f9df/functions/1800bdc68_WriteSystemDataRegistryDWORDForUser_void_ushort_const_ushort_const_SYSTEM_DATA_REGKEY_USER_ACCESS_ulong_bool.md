# _WriteSystemDataRegistryDWORDForUser(void *,ushort const *,ushort const *,SYSTEM_DATA_REGKEY_USER_ACCESS,ulong,bool)

- ea: `0x1800bdc68`
- end: `0x1800bdd5e`
- name: `?_WriteSystemDataRegistryDWORDForUser@@YAJPEAXPEBG1W4SYSTEM_DATA_REGKEY_USER_ACCESS@@K_N@Z`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005400c`

## callees

- `0x180003470`
- `0x180008b98`
- `0x18000ac48`
- `0x180046c9c`
- `0x1800bdb48`
- `0x1800bdc68`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800bdc91`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800bdc91`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bdd3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bdd3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bdd32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bdd32`

## string_xrefs

- `0x1800bdcbb`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SystemProtectedUserData`

## pseudocode

```c

```
