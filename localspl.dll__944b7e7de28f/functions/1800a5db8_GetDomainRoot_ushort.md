# GetDomainRoot(ushort * *)

- ea: `0x1800a5db8`
- end: `0x1800a5f8a`
- name: `?GetDomainRoot@@YAKPEAPEAG@Z`
- size: `466`
- prototype: `unsigned int __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800a7810`

## callees

- `0x18000edc4`
- `0x180046650`
- `0x1800a4750`
- `0x1800a558c`
- `0x1800a57f4`
- `0x1800a5db8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5eb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5eb8`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x1800a5f3b`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x1800a5f3b`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x1800a5f29`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x1800a5f29`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x1800a5eae`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x1800a5eae`
- `SPOOLSS!DllAllocSplMem` at `0x1800a5ef3`
- `SPOOLSS!DllAllocSplMem` at `0x1800a5ef3`
- `netutils!NetApiBufferFree` at `0x1800a5f4b`
- `netutils!NetApiBufferFree` at `0x1800a5f4b`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x1800a5e23`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x1800a5e23`
- `DSROLE!DsRoleFreeMemory` at `0x1800a5f5b`
- `DSROLE!DsRoleFreeMemory` at `0x1800a5f5b`

## pseudocode

```c

```
