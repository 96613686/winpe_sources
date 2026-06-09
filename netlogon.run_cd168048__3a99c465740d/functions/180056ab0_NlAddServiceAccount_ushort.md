# NlAddServiceAccount(ushort *)

- ea: `0x180056ab0`
- end: `0x180056ba5`
- name: `?NlAddServiceAccount@@YAJPEAG@Z`
- size: `245`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180065520`

## callees

- `0x180007518`
- `0x18000da50`
- `0x180056ab0`
- `0x180056bac`
- `0x180056f70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180056b41`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180056b41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056b51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056b51`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180056b24`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180056b24`
- `ntdll!RtlLeaveCriticalSection` at `0x180056b78`
- `ntdll!RtlLeaveCriticalSection` at `0x180056b8b`
- `ntdll!RtlLeaveCriticalSection` at `0x180056b78`
- `ntdll!RtlLeaveCriticalSection` at `0x180056b8b`
- `ntdll!RtlEnterCriticalSection` at `0x180056ac4`
- `ntdll!RtlEnterCriticalSection` at `0x180056b11`
- `ntdll!RtlEnterCriticalSection` at `0x180056ac4`
- `ntdll!RtlEnterCriticalSection` at `0x180056b11`

## string_xrefs

- `0x180056b5d`: `NlAddServiceAccount: SetEvent failed %ld\n`

## pseudocode

```c

```
