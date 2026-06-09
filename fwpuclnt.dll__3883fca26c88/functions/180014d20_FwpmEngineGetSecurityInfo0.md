# FwpmEngineGetSecurityInfo0

- ea: `0x180014d20`
- end: `0x180014e27`
- name: `FwpmEngineGetSecurityInfo0`
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
- `0x180014d20`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180014da5`
- `RPCRT4!NdrClientCall3` at `0x180014da5`

## string_xrefs

- `0x180014d6f`: `FwpmEngineGetSecurityInfo0`
- `0x180014db8`: `FwppProxyEngineGetSecurityInfo`

## pseudocode

```c

```
