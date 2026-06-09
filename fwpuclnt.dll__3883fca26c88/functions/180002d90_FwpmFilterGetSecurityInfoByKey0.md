# FwpmFilterGetSecurityInfoByKey0

- ea: `0x180002d90`
- end: `0x180002ea2`
- name: `FwpmFilterGetSecurityInfoByKey0`
- size: `274`
- prototype: `DWORD __stdcall(HANDLE engineHandle, const GUID *key, SECURITY_INFORMATION securityInfo, PSID *sidOwner, PSID *sidGroup, PACL *dacl, PACL *sacl, PSECURITY_DESCRIPTOR *securityDescriptor)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800027f0`
- `0x180002d90`
- `0x1800034e0`
- `0x180004540`
- `0x180010584`
- `0x180012bd0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180002e0f`
- `RPCRT4!NdrClientCall3` at `0x180002e0f`

## string_xrefs

- `0x180002e22`: `FwppProxyFilterGetSecurityInfoByKey`
- `0x180002e5f`: `FwpmFilterGetSecurityInfoByKey0`

## pseudocode

```c

```
