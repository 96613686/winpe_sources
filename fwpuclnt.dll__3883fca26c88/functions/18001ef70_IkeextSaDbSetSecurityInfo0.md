# IkeextSaDbSetSecurityInfo0

- ea: `0x18001ef70`
- end: `0x18001f09c`
- name: `IkeextSaDbSetSecurityInfo0`
- size: `300`
- prototype: `DWORD __stdcall(HANDLE engineHandle, SECURITY_INFORMATION securityInfo, const SID *sidOwner, const SID *sidGroup, const ACL *dacl, const ACL *sacl)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800034e0`
- `0x1800040a0`
- `0x18000438c`
- `0x180004540`
- `0x180010710`
- `0x180010b50`
- `0x180012bd0`
- `0x18001ef70`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18001f04a`
- `RPCRT4!NdrClientCall3` at `0x18001f04a`

## string_xrefs

- `0x18001efd3`: `IkeextSaDbSetSecurityInfo0`
- `0x18001f05d`: `FwppProxyIkeSaDbSetSecurityInfo`

## pseudocode

```c

```
