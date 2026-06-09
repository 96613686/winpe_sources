# CLogonTaskFramework::_ReportLogonTaskPerformanceResult(LogonTaskId)

- ea: `0x140011094`
- end: `0x140011205`
- name: `?_ReportLogonTaskPerformanceResult@CLogonTaskFramework@@AEAAXW4LogonTaskId@@@Z`
- size: `369`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x140010430`
- `0x14008c73c`

## callees

- `0x140011094`
- `0x14001120c`
- `0x140011360`
- `0x1400113e0`
- `0x1401040e0`
- `0x1401a1b94`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegGetBoolUSValueW` at `0x140011189`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegGetBoolUSValueW` at `0x140011189`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400111c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400111c6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400111b1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400111b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140011102`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140011102`

## string_xrefs

- `0x1400111a4`: `faultrep.dll`
- `0x140011178`: `CaptureLogonTaskFailureCab`

## pseudocode

```c

```
