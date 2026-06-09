# HNS::Service::Resource::HostPortResource::WaitForInterface(HNS::AdapterMonitor &,ushort)

- ea: `0x1801d4254`
- end: `0x1801d44b0`
- name: `?WaitForInterface@HostPortResource@Resource@Service@HNS@@IEBAXAEAVAdapterMonitor@4@G@Z`
- size: `604`
- prototype: `void __fastcall(HNS::Service::Resource::HostPortResource *__hidden this, struct HNS::AdapterMonitor *, unsigned __int16)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18012ddf4`
- `0x1801d1aa0`

## callees

- `0x180001b68`
- `0x18005f0c0`
- `0x180061dc4`
- `0x1800666b4`
- `0x1800677fc`
- `0x1801d4254`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1801d42f8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1801d42f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1801d43b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1801d4405`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1801d43b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1801d4405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d436c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d436c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1801d42bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1801d437d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1801d42bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1801d437d`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1801d4362`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1801d4362`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1801d42ad`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1801d42ad`

## string_xrefs

- `0x1801d4482`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x1801d4498`: `onecore\vm\dv\net\hns\service\resourcemgr\resources\src\hostportresource.cpp`

## pseudocode

```c

```
