# FwpmSubLayerSetSecurityInfoByKey0

- ea: `0x1800184d0`
- end: `0x1800185ec`
- name: `FwpmSubLayerSetSecurityInfoByKey0`
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
- `0x1800184d0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18001859e`
- `RPCRT4!NdrClientCall3` at `0x18001859e`

## string_xrefs

- `0x180018531`: `FwpmSubLayerSetSecurityInfoByKey0`
- `0x1800185b1`: `FwppProxySubLayerSetSecurityInfoByKey`

## pseudocode

```c

```
