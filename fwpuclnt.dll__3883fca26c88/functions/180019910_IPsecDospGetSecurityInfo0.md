# IPsecDospGetSecurityInfo0

- ea: `0x180019910`
- end: `0x180019a17`
- name: `IPsecDospGetSecurityInfo0`
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
- `0x180019910`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180019995`
- `RPCRT4!NdrClientCall3` at `0x180019995`

## string_xrefs

- `0x18001995f`: `IPsecDospGetSecurityInfo0`
- `0x1800199a8`: `FwppProxyBfeIPsecDospGetSecurityInfo`

## pseudocode

```c

```
