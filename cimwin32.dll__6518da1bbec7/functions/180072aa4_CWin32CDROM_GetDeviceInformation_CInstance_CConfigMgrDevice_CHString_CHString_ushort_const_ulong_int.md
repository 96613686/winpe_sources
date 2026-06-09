# CWin32CDROM::GetDeviceInformation(CInstance *,CConfigMgrDevice *,CHString,CHString &,ushort const *,ulong,int &)

- ea: `0x180072aa4`
- end: `0x1800730c6`
- name: `?GetDeviceInformation@CWin32CDROM@@IEAAJPEAVCInstance@@PEAVCConfigMgrDevice@@VCHString@@AEAV4@PEBGKAEAH@Z`
- size: `1570`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180070208`

## callees

- `0x18000ab30`
- `0x1800127e0`
- `0x180013ae0`
- `0x180016900`
- `0x180017680`
- `0x180021f34`
- `0x180031800`
- `0x180046c9c`
- `0x180072aa4`
- `0x1800fc980`
- `0x180110010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072bc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072e50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073014`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073024`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073085`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072bc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072e50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073014`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073024`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073085`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180072d63`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180072d63`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x180072b9a`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x18007306b`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x180072b9a`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x18007306b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180072dcc`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180072ea8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180072fb9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180072dcc`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180072ea8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180072fb9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180072b89`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180073058`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180072b89`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180073058`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072ba9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180073076`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072ba9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180073076`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180072c34`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180072cc7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180072c34`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180072cc7`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180072b0e`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180072b0e`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180072ed0`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180072ed0`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x180072b70`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x180072b70`
- `framedynos!??0CHString@@QEAA@AEBV0@@Z` at `0x180072b2e`
- `framedynos!??0CHString@@QEAA@AEBV0@@Z` at `0x180072b2e`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180072b61`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180072e14`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180072b61`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180072e14`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x180072bf5`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x180072bf5`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x180072ef5`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x180072f1a`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x180072f3f`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x180072ef5`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x180072f1a`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x180072f3f`
- `framedynos!??0CHString@@QEAA@PEBD@Z` at `0x180072be1`
- `framedynos!??0CHString@@QEAA@PEBD@Z` at `0x180072be1`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGPEBD@Z` at `0x180072fe9`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGPEBD@Z` at `0x18007300c`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGPEBD@Z` at `0x180072fe9`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGPEBD@Z` at `0x18007300c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180072b7c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180072c01`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18007303e`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180073091`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18007309b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180072b7c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180072c01`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18007303e`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180073091`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18007309b`

## string_xrefs

- `0x180072b55`: `WMI_CDROMDEVICE_SYBOLICLINK`

## pseudocode

```c

```
