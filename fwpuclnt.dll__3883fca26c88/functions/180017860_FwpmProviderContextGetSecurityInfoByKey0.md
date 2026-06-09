# FwpmProviderContextGetSecurityInfoByKey0

- ea: `0x180017860`
- end: `0x180017972`
- name: `FwpmProviderContextGetSecurityInfoByKey0`
- size: `274`
- prototype: `DWORD __stdcall(HANDLE engineHandle, const GUID *key, SECURITY_INFORMATION securityInfo, PSID *sidOwner, PSID *sidGroup, PACL *dacl, PACL *sacl, PSECURITY_DESCRIPTOR *securityDescriptor)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800027f0`
- `0x1800034e0`
- `0x180004540`
- `0x180010584`
- `0x180012bd0`
- `0x180017860`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800178f0`
- `RPCRT4!NdrClientCall3` at `0x1800178f0`

## string_xrefs

- `0x1800178b5`: `FwpmProviderContextGetSecurityInfoByKey0`
- `0x180017903`: `FwppProxyProviderContextGetSecurityInfoByKey`

## pseudocode

```c

```
