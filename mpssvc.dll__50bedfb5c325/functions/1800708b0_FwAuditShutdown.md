# FwAuditShutdown

- ea: `0x1800708b0`
- end: `0x180070a78`
- name: `FwAuditShutdown`
- size: `456`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18007df70`

## callees

- `0x1800089bc`
- `0x1800708b0`
- `0x180073488`
- `0x18007f404`
- `0x1800ec010`

## import_xrefs

- `ntdll!EtwEventUnregister` at `0x180070a01`
- `ntdll!EtwEventUnregister` at `0x180070a01`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800709e0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800709e0`
- `AUTHZ!AuthzFreeResourceManager` at `0x1800709bf`
- `AUTHZ!AuthzFreeResourceManager` at `0x1800709bf`
- `fwbase!FwSidDestroy` at `0x1800708e3`
- `fwbase!FwSidDestroy` at `0x1800708e3`
- `fwbase!FwReportReturnError` at `0x180070a39`
- `fwbase!FwReportReturnError` at `0x180070a39`
- `fwbase!FwFree` at `0x1800708bd`
- `fwbase!FwFree` at `0x1800708d0`
- `fwbase!FwFree` at `0x180070901`
- `fwbase!FwFree` at `0x18007095c`
- `fwbase!FwFree` at `0x1800709a7`
- `fwbase!FwFree` at `0x1800708bd`
- `fwbase!FwFree` at `0x1800708d0`
- `fwbase!FwFree` at `0x180070901`
- `fwbase!FwFree` at `0x18007095c`
- `fwbase!FwFree` at `0x1800709a7`
- `fwbase!FwArrayDestroy` at `0x18007092d`
- `fwbase!FwArrayDestroy` at `0x180070949`
- `fwbase!FwArrayDestroy` at `0x18007092d`
- `fwbase!FwArrayDestroy` at `0x180070949`

## pseudocode

```c

```
