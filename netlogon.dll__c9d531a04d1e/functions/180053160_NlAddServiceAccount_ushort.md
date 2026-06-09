# NlAddServiceAccount(ushort *)

- ea: `0x180053160`
- end: `0x180053223`
- name: `?NlAddServiceAccount@@YAJPEAG@Z`
- size: `195`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180060fa4`

## callees

- `0x180007278`
- `0x18000d4c4`
- `0x180053160`
- `0x18005322c`
- `0x1800535b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800531d8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800531d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800531e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800531e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800531c1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800531c1`
- `ntdll!RtlLeaveCriticalSection` at `0x180053203`
- `ntdll!RtlLeaveCriticalSection` at `0x180053210`
- `ntdll!RtlLeaveCriticalSection` at `0x180053203`
- `ntdll!RtlLeaveCriticalSection` at `0x180053210`
- `ntdll!RtlEnterCriticalSection` at `0x180053174`
- `ntdll!RtlEnterCriticalSection` at `0x1800531b4`
- `ntdll!RtlEnterCriticalSection` at `0x180053174`
- `ntdll!RtlEnterCriticalSection` at `0x1800531b4`

## string_xrefs

- `0x1800531e8`: `NlAddServiceAccount: SetEvent failed %ld\n`

## pseudocode

```c

```
