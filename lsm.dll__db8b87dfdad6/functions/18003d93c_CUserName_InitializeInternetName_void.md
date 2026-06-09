# CUserName::InitializeInternetName(void)

- ea: `0x18003d93c`
- end: `0x18003dc43`
- name: `?InitializeInternetName@CUserName@@AEAAJXZ`
- size: `775`
- prototype: `__int64 __fastcall(CUserName *__hidden this)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180082c20`
- `0x180082d00`
- `0x180082f90`

## callees

- `0x18000345c`
- `0x1800074c0`
- `0x180008b20`
- `0x18001aa50`
- `0x180026e00`
- `0x18003d93c`
- `0x18004b86c`
- `0x18007ef08`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003d9fc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003d9fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003dc21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003dc21`
- `samcli!NetUserGetInfo` at `0x18003dad2`
- `samcli!NetUserGetInfo` at `0x18003dad2`
- `DSROLE!DsRoleFreeMemory` at `0x18003dc30`
- `DSROLE!DsRoleFreeMemory` at `0x18003dc30`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x18003da20`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x18003da20`

## string_xrefs

- `0x18003d979`: `No token`
- `0x18003db7a`: `StringCchCopy failed: 0x%x in %s`
- `0x18003d9e5`: `CUtils::GetComputerName failed: 0x%x in %s`

## pseudocode

```c

```
