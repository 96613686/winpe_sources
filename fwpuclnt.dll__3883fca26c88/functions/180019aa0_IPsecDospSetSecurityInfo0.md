# IPsecDospSetSecurityInfo0

- ea: `0x180019aa0`
- end: `0x180019ba5`
- name: `IPsecDospSetSecurityInfo0`
- size: `261`
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
- `0x180019aa0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180019b59`
- `RPCRT4!NdrClientCall3` at `0x180019b59`

## string_xrefs

- `0x180019af4`: `IPsecDospSetSecurityInfo0`
- `0x180019b6c`: `FwppProxyBfeIPsecDospSetSecurityInfo`

## pseudocode

```c

```
