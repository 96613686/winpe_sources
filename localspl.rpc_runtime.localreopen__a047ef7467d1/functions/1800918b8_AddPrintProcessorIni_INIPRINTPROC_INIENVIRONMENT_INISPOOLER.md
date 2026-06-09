# AddPrintProcessorIni(INIPRINTPROC *,_INIENVIRONMENT *,_INISPOOLER *)

- ea: `0x1800918b8`
- end: `0x180091a5e`
- name: `?AddPrintProcessorIni@@YAHPEAVINIPRINTPROC@@PEAU_INIENVIRONMENT@@PEAU_INISPOOLER@@@Z`
- size: `422`
- prototype: `int(struct INIPRINTPROC *, struct _INIENVIRONMENT *, struct _INISPOOLER *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180090304`

## callees

- `0x180005d90`
- `0x18003e984`
- `0x180045010`
- `0x1800918b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180091a16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180091a20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180091a2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180091a34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180091a16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180091a20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180091a2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180091a34`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009194c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091977`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009194c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091977`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800918f0`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800918f0`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180091a3d`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180091a3d`

## pseudocode

```c

```
