# NPackageInstallLocalspl::TLinkedDriverPackage::GetCabPath(ushort const *,NPackageInstallLocalspl::CabGeneration::Enum,ushort *,ulong,ulong *)

- ea: `0x18000f270`
- end: `0x18000f4ad`
- name: `?GetCabPath@TLinkedDriverPackage@NPackageInstallLocalspl@@QEAAJPEBGW4Enum@CabGeneration@2@PEAGKPEAK@Z`
- size: `573`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000d1b8`

## callees

- `0x18000c7ec`
- `0x18000d944`
- `0x18000f270`
- `0x180011f00`
- `0x180012510`
- `0x180013c90`
- `0x180015e28`
- `0x18003ea2c`
- `0x1800aca48`
- `0x1800b8b94`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f3c0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f3d4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f3e8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f3fc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f410`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f3c0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f3d4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f3e8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f3fc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f410`
- `SPOOLSS!DllFreeSplMem` at `0x18000f498`
- `SPOOLSS!DllFreeSplMem` at `0x18000f498`
- `SPOOLSS!RevertToPrinterSelf` at `0x18000f369`
- `SPOOLSS!RevertToPrinterSelf` at `0x18000f369`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18000f387`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18000f387`

## string_xrefs

- `0x18000f429`: `Error in RemovePreviousCab (m_strDriverStorePath='%ws') during remove previous cab for offline printer: hr: 0x%x`
- `0x18000f443`: `NPackageInstallLocalspl::TLinkedDriverPackage::GetCabPath`
- `0x18000f438`: `Error in FindFileName (m_strDriverStorePath='%ws') during remove previous cab for offline printer: hr: 0x%x`

## pseudocode

```c

```
