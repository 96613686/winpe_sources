# TeredoClientTimerCallback

- ea: `0x1800090a0`
- end: `0x180009205`
- name: `TeredoClientTimerCallback`
- size: `357`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x1800090a0`
- `0x180009210`
- `0x18000d7c0`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18000911d`
- `ntdll!EtwEventActivityIdControl` at `0x18000911d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800091c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800091c2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009165`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009165`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800090d8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800090d8`

## string_xrefs

- `0x180009142`: `onecoreuap\net\netio\iphlpsvc\service\client.c`
- `0x18000917d`: `onecoreuap\net\netio\iphlpsvc\service\client.c`
- `0x1800091d2`: `onecoreuap\net\netio\iphlpsvc\service\client.c`

## pseudocode

```c

```
