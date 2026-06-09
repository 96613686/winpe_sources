# FwpmNetEventsGetSecurityInfo0

- ea: `0x180016940`
- end: `0x180016a47`
- name: `FwpmNetEventsGetSecurityInfo0`
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
- `0x180016940`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800169c5`
- `RPCRT4!NdrClientCall3` at `0x1800169c5`

## string_xrefs

- `0x18001698f`: `FwpmNetEventsGetSecurityInfo0`
- `0x1800169d8`: `FwppProxyNetEventsGetSecurityInfo`

## pseudocode

```c

```
