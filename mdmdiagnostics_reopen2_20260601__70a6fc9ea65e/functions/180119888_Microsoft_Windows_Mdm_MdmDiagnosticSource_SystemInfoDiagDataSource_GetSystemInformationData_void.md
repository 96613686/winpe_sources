# Microsoft::Windows::Mdm::MdmDiagnosticSource::SystemInfoDiagDataSource::GetSystemInformationData(void)

- ea: `0x180119888`
- end: `0x180119b88`
- name: `?GetSystemInformationData@SystemInfoDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJXZ`
- size: `768`
- prototype: `__int64 __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource::SystemInfoDiagDataSource *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180119720`

## callees

- `0x180019080`
- `0x1800ed46c`
- `0x1800edd78`
- `0x1800fa538`
- `0x18010562c`
- `0x180119888`
- `0x180119b90`
- `0x180193010`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1801199fd`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1801199fd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180119abf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180119abf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180119907`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180119907`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x180119946`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x180119946`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x18011997c`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x18011997c`
- `DMCmnUtils!DmGetSmbiosSerialNumber` at `0x180119b06`
- `DMCmnUtils!DmGetSmbiosSerialNumber` at `0x180119b06`

## string_xrefs

- `0x1801199d8`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\systeminfodiagdata.cpp`

## pseudocode

```c

```
