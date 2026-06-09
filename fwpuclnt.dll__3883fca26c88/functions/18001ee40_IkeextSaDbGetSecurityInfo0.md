# IkeextSaDbGetSecurityInfo0

- ea: `0x18001ee40`
- end: `0x18001ef5e`
- name: `IkeextSaDbGetSecurityInfo0`
- size: `286`
- prototype: `DWORD __stdcall(HANDLE engineHandle, SECURITY_INFORMATION securityInfo, PSID *sidOwner, PSID *sidGroup, PACL *dacl, PACL *sacl, PSECURITY_DESCRIPTOR *securityDescriptor)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800027f0`
- `0x1800034e0`
- `0x180004540`
- `0x180010584`
- `0x180010710`
- `0x180012bd0`
- `0x18001ee40`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18001eeda`
- `RPCRT4!NdrClientCall3` at `0x18001eeda`

## string_xrefs

- `0x18001ee9a`: `IkeextSaDbGetSecurityInfo0`
- `0x18001eeed`: `FwppProxyIkeSaDbGetSecurityInfo`

## pseudocode

```c

```
