# FwpmSubLayerGetSecurityInfoByKey0

- ea: `0x1800183b0`
- end: `0x1800184c2`
- name: `FwpmSubLayerGetSecurityInfoByKey0`
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
- `0x1800183b0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180018440`
- `RPCRT4!NdrClientCall3` at `0x180018440`

## string_xrefs

- `0x180018405`: `FwpmSubLayerGetSecurityInfoByKey0`
- `0x180018453`: `FwppProxySubLayerGetSecurityInfoByKey`

## pseudocode

```c

```
