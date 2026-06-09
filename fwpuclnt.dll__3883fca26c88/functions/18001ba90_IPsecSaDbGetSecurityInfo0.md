# IPsecSaDbGetSecurityInfo0

- ea: `0x18001ba90`
- end: `0x18001bb97`
- name: `IPsecSaDbGetSecurityInfo0`
- size: `263`
- prototype: `DWORD __stdcall(HANDLE engineHandle, SECURITY_INFORMATION securityInfo, PSID *sidOwner, PSID *sidGroup, PACL *dacl, PACL *sacl, PSECURITY_DESCRIPTOR *securityDescriptor)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800027f0`
- `0x1800034e0`
- `0x180004540`
- `0x180010584`
- `0x180012bd0`
- `0x18001ba90`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18001bb15`
- `RPCRT4!NdrClientCall3` at `0x18001bb15`

## string_xrefs

- `0x18001badf`: `IPsecSaDbGetSecurityInfo0`
- `0x18001bb28`: `FwppProxyBfeIPsecSaDbGetSecurityInfo`

## pseudocode

```c

```
