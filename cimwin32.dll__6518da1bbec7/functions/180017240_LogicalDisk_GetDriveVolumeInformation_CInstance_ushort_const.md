# LogicalDisk::GetDriveVolumeInformation(CInstance *,ushort const *)

- ea: `0x180017240`
- end: `0x180017670`
- name: `?GetDriveVolumeInformation@LogicalDisk@@QEAAKPEAVCInstance@@PEBG@Z`
- size: `1072`
- prototype: `unsigned int(LogicalDisk *__hidden this, struct CInstance *, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `6`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180017cb4`
- `0x180053480`
- `0x18005688c`
- `0x180057088`
- `0x1800a64b0`

## callees

- `0x180014c58`
- `0x180016900`
- `0x180017240`
- `0x180017f84`
- `0x1800fc980`
- `0x180110010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800175a6`
- `ntdll!RtlFreeUnicodeString` at `0x1800175a6`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180017552`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180017552`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800174d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800174d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017662`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1800172c9`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1800172c9`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18001743f`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18001743f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800173f4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800173f4`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180017409`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180017409`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x18001741f`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x18001741f`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180017381`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800174a4`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180017381`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800174a4`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18001734f`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18001736c`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18001739e`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180017509`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800175f5`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180017629`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180017646`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18001734f`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18001736c`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18001739e`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180017509`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800175f5`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180017629`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180017646`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x18001742c`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x18001753e`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x18001742c`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x18001753e`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800172e8`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800172ff`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180017332`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800172e8`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800172ff`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180017332`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180017528`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180017587`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180017528`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180017587`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18001747a`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180017515`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800175ba`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18001747a`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180017515`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800175ba`

## string_xrefs

- `0x18001749a`: `Access`
- `0x180017377`: `MaximumComponentLength`
- `0x180017362`: `SupportsFileBasedCompression`
- `0x180017345`: `Compressed`
- `0x18001761f`: `QuotasIncomplete`

## pseudocode

```c

```
