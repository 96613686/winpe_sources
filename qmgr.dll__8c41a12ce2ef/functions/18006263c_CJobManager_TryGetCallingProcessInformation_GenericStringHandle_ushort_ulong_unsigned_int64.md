# CJobManager::TryGetCallingProcessInformation(GenericStringHandle<ushort> &,ulong *,unsigned __int64 &)

- ea: `0x18006263c`
- end: `0x180062958`
- name: `?TryGetCallingProcessInformation@CJobManager@@SAXAEAV?$GenericStringHandle@G@@PEAKAEA_K@Z`
- size: `796`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180016ee0`
- `0x180036504`
- `0x18008bd40`
- `0x18008c040`
- `0x18009651c`
- `0x18009871c`

## callees

- `0x18000c7d0`
- `0x18002c6ac`
- `0x18006263c`
- `0x180062960`
- `0x180080430`
- `0x18009b668`
- `0x18009e9c8`
- `0x1800a3444`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x18006284d`
- `ntdll!NtQueryInformationProcess` at `0x18006284d`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800627c3`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800627c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180062735`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180062937`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180062735`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180062937`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800626c4`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800626c4`

## pseudocode

```c

```
