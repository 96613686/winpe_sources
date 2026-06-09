# CIXAConfig::GetFullAddressOfTheDll(_GUID,char *,long)

- ea: `0x18003abe0`
- end: `0x18003acf9`
- name: `?GetFullAddressOfTheDll@CIXAConfig@@AEAAJU_GUID@@PEADJ@Z`
- size: `281`
- prototype: `__int64 __fastcall(CIXAConfig *this, struct _GUID *, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003b518`

## callees

- `0x18002f534`
- `0x18003abe0`
- `0x180081dd0`

## import_xrefs

- `RPCRT4!RpcStringFreeA` at `0x18003ac6f`
- `RPCRT4!RpcStringFreeA` at `0x18003ac6f`
- `RPCRT4!UuidToStringA` at `0x18003ac3b`
- `RPCRT4!UuidToStringA` at `0x18003ac3b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18003ac94`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18003ac94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003accd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003accd`
- `ADVAPI32!RegQueryValueA` at `0x18003acb6`
- `ADVAPI32!RegQueryValueA` at `0x18003acb6`

## string_xrefs

- `0x18003ac54`: `CLSID\{%s}\InprocServer32`

## pseudocode

```c

```
