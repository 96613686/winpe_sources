# FwAuditShutdown

- ea: `0x18006d5b0`
- end: `0x18006d72f`
- name: `FwAuditShutdown`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18007a220`

## callees

- `0x1800093b0`
- `0x18006d5b0`
- `0x18006ffc8`
- `0x18007b514`
- `0x1800e6010`

## import_xrefs

- `ntdll!EtwEventUnregister` at `0x18006d6c5`
- `ntdll!EtwEventUnregister` at `0x18006d6c5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006d6aa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006d6aa`
- `AUTHZ!AuthzFreeResourceManager` at `0x18006d68f`
- `AUTHZ!AuthzFreeResourceManager` at `0x18006d68f`
- `fwbase!FwArrayDestroy` at `0x18006d615`
- `fwbase!FwArrayDestroy` at `0x18006d62b`
- `fwbase!FwArrayDestroy` at `0x18006d615`
- `fwbase!FwArrayDestroy` at `0x18006d62b`
- `fwbase!FwSidDestroy` at `0x18006d5d7`
- `fwbase!FwSidDestroy` at `0x18006d5d7`
- `fwbase!FwReportReturnError` at `0x18006d6f7`
- `fwbase!FwReportReturnError` at `0x18006d6f7`
- `fwbase!FwFree` at `0x18006d5bd`
- `fwbase!FwFree` at `0x18006d5ca`
- `fwbase!FwFree` at `0x18006d5ef`
- `fwbase!FwFree` at `0x18006d638`
- `fwbase!FwFree` at `0x18006d67d`
- `fwbase!FwFree` at `0x18006d5bd`
- `fwbase!FwFree` at `0x18006d5ca`
- `fwbase!FwFree` at `0x18006d5ef`
- `fwbase!FwFree` at `0x18006d638`
- `fwbase!FwFree` at `0x18006d67d`

## pseudocode

```c

```
