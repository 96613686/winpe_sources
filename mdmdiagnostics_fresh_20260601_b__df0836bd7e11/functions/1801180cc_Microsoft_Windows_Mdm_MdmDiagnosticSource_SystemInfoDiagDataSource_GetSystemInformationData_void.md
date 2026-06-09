# Microsoft::Windows::Mdm::MdmDiagnosticSource::SystemInfoDiagDataSource::GetSystemInformationData(void)

- ea: `0x1801180cc`
- end: `0x1801183a7`
- name: `?GetSystemInformationData@SystemInfoDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJXZ`
- size: `731`
- prototype: `__int64 __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource::SystemInfoDiagDataSource *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180117f70`

## callees

- `0x180019000`
- `0x1800ece5c`
- `0x1800ed730`
- `0x1800f9558`
- `0x18010440c`
- `0x1801180cc`
- `0x1801183b0`
- `0x180191010`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18011822f`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18011822f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801182eb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801182eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18011814b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18011814b`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x180118184`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x180118184`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x1801181b4`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x1801181b4`
- `DMCmnUtils!DmGetSmbiosSerialNumber` at `0x18011832c`
- `DMCmnUtils!DmGetSmbiosSerialNumber` at `0x18011832c`

## string_xrefs

- `0x18011820a`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\systeminfodiagdata.cpp`

## pseudocode

```c

```
