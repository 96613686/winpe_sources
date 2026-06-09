# FwpmConnectionGetSecurityInfo0

- ea: `0x1800146f0`
- end: `0x1800147f8`
- name: `FwpmConnectionGetSecurityInfo0`
- size: `264`
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
- `0x1800146f0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180014776`
- `RPCRT4!NdrClientCall3` at `0x180014776`

## string_xrefs

- `0x18001473f`: `FwpmConnectionGetSecurityInfo0`
- `0x180014789`: `FwppProxyConnectionGetSecurityInfo`

## pseudocode

```c

```
