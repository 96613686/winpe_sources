# FwpmLayerSetSecurityInfoByKey0

- ea: `0x180015b70`
- end: `0x180015c8c`
- name: `FwpmLayerSetSecurityInfoByKey0`
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
- `0x180015b70`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180015c3e`
- `RPCRT4!NdrClientCall3` at `0x180015c3e`

## string_xrefs

- `0x180015bd1`: `FwpmLayerSetSecurityInfoByKey0`
- `0x180015c51`: `FwppProxyLayerSetSecurityInfoByKey`

## pseudocode

```c

```
