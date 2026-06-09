# FwpsAleEndpointSetSecurityInfo0

- ea: `0x180019590`
- end: `0x180019697`
- name: `FwpsAleEndpointSetSecurityInfo0`
- size: `263`
- prototype: `DWORD __stdcall(HANDLE engineHandle, SECURITY_INFORMATION securityInfo, const SID *sidOwner, const SID *sidGroup, const ACL *dacl, const ACL *sacl)`
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
- `0x180019590`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18001964b`
- `RPCRT4!NdrClientCall3` at `0x18001964b`

## string_xrefs

- `0x1800195e4`: `FwpsAleEndpointSetSecurityInfo0`
- `0x18001965e`: `FwppProxyAleEndpointSetSecurityInfo`

## pseudocode

```c

```
