# TeredoClientTimerCallback

- ea: `0x180009090`
- end: `0x1800091f5`
- name: `TeredoClientTimerCallback`
- size: `357`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180009090`
- `0x180009200`
- `0x18000d7b0`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18000910d`
- `ntdll!EtwEventActivityIdControl` at `0x18000910d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800091b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800091b2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009155`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009155`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800090c8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800090c8`

## string_xrefs

- `0x180009132`: `onecoreuap\net\netio\iphlpsvc\service\client.c`
- `0x18000916d`: `onecoreuap\net\netio\iphlpsvc\service\client.c`
- `0x1800091c2`: `onecoreuap\net\netio\iphlpsvc\service\client.c`

## pseudocode

```c

```
