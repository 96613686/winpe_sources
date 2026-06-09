# FwpsAleEndpointGetSecurityInfo0

- ea: `0x180019480`
- end: `0x180019588`
- name: `FwpsAleEndpointGetSecurityInfo0`
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
- `0x180019480`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180019506`
- `RPCRT4!NdrClientCall3` at `0x180019506`

## string_xrefs

- `0x1800194cf`: `FwpsAleEndpointGetSecurityInfo0`
- `0x180019519`: `FwppProxyAleEndpointGetSecurityInfo`

## pseudocode

```c

```
