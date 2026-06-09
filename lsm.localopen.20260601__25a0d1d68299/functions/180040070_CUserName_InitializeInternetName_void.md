# CUserName::InitializeInternetName(void)

- ea: `0x180040070`
- end: `0x180040396`
- name: `?InitializeInternetName@CUserName@@AEAAJXZ`
- size: `806`
- prototype: `__int64 __fastcall(CUserName *__hidden this)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180087890`
- `0x180087980`
- `0x180087c40`

## callees

- `0x180003478`
- `0x1800077a0`
- `0x180008f40`
- `0x180009580`
- `0x180028bd8`
- `0x180040070`
- `0x18004ec5c`
- `0x180083a94`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180040130`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180040130`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040367`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040367`
- `samcli!NetUserGetInfo` at `0x180040212`
- `samcli!NetUserGetInfo` at `0x180040212`
- `DSROLE!DsRoleFreeMemory` at `0x18004037c`
- `DSROLE!DsRoleFreeMemory` at `0x18004037c`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x18004015a`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x18004015a`

## string_xrefs

- `0x1800400ad`: `No token`
- `0x1800402c0`: `StringCchCopy failed: 0x%x in %s`
- `0x180040119`: `CUtils::GetComputerName failed: 0x%x in %s`

## pseudocode

```c

```
