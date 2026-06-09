# CWin32TapeDrive::GetDeviceInformation(CInstance *,CConfigMgrDevice *,CHString,CHString &,ushort const *,unsigned __int64)

- ea: `0x1800eacd4`
- end: `0x1800eb21d`
- name: `?GetDeviceInformation@CWin32TapeDrive@@AEAAJPEAVCInstance@@PEAVCConfigMgrDevice@@VCHString@@AEAV4@PEBG_K@Z`
- size: `1353`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800eb7e4`

## callees

- `0x180016900`
- `0x180031800`
- `0x180036818`
- `0x180046c9c`
- `0x1800eacd4`
- `0x1800fc980`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eade0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eaf36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eb0e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eb19c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eade0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eaf36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eb0e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eb19c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800eae7c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800eae7c`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x1800eadbf`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x1800eb185`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x1800eadbf`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x1800eb185`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800eaeda`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800eaeda`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetTapeParameters` at `0x1800eafaa`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetTapeParameters` at `0x1800eafaa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eadcc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eb192`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eadcc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eb192`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBGHW4LogLevel@1@0ZZ` at `0x1800eae0d`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBGHW4LogLevel@1@0ZZ` at `0x1800eaf66`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBGHW4LogLevel@1@0ZZ` at `0x1800eb124`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBGHW4LogLevel@1@0ZZ` at `0x1800eb1ca`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBGHW4LogLevel@1@0ZZ` at `0x1800eae0d`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBGHW4LogLevel@1@0ZZ` at `0x1800eaf66`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBGHW4LogLevel@1@0ZZ` at `0x1800eb124`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBGHW4LogLevel@1@0ZZ` at `0x1800eb1ca`
- `framedynos!?captainsLog@@3VProviderLog@@A` at `0x1800eae06`
- `framedynos!?captainsLog@@3VProviderLog@@A` at `0x1800eaf5f`
- `framedynos!?captainsLog@@3VProviderLog@@A` at `0x1800eb11d`
- `framedynos!?captainsLog@@3VProviderLog@@A` at `0x1800eb1c3`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800ead24`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800ead24`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800eada2`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800eadb0`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800eae52`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800eb166`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800eb174`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800eada2`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800eadb0`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800eae52`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800eb166`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800eb174`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800eafce`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800eafea`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800eb006`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800eb022`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800eb08e`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800eb0a9`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800eb0c4`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800eb0df`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800eafce`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800eafea`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800eb006`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800eb022`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800eb08e`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800eb0a9`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800eb0c4`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800eb0df`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x1800ead7e`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x1800ead7e`
- `framedynos!??0CHString@@QEAA@AEBV0@@Z` at `0x1800ead3d`
- `framedynos!??0CHString@@QEAA@AEBV0@@Z` at `0x1800ead3d`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x1800eb03d`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x1800eb058`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x1800eb073`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x1800eb03d`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x1800eb058`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBG_K@Z` at `0x1800eb073`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800ead6f`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800eae27`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800eaf0d`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800ead6f`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800eae27`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800eaf0d`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x1800eae3b`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x1800eae3b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ead8a`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800eae47`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800eb13b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800eb1e4`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800eb1ee`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800ead8a`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800eae47`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800eb13b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800eb1e4`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800eb1ee`

## string_xrefs

- `0x1800ead63`: `WMI_TAPEDEVICE_SYBOLICLINK`
- `0x1800eb0fe`: `Failed to CreateFile (%d)`
- `0x1800eb1a6`: `Failed to Delete DOS Device (%d)`
- `0x1800eafe0`: `Compression`

## pseudocode

```c

```
