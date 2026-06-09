# FwpmProviderSetSecurityInfoByKey0

- ea: `0x180017e40`
- end: `0x180017f5c`
- name: `FwpmProviderSetSecurityInfoByKey0`
- size: `284`
- prototype: `DWORD __stdcall(HANDLE engineHandle, const GUID *key, SECURITY_INFORMATION securityInfo, const SID *sidOwner, const SID *sidGroup, const ACL *dacl, const ACL *sacl)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800034e0`
- `0x1800040a0`
- `0x18000438c`
- `0x180004540`
- `0x180010b50`
- `0x180012bd0`
- `0x180017e40`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180017f0e`
- `RPCRT4!NdrClientCall3` at `0x180017f0e`

## string_xrefs

- `0x180017ea1`: `FwpmProviderSetSecurityInfoByKey0`
- `0x180017f21`: `FwppProxyProviderSetSecurityInfoByKey`

## pseudocode

```c

```
