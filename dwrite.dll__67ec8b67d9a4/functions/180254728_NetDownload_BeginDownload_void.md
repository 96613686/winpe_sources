# NetDownload::BeginDownload(void)

- ea: `0x180254728`
- end: `0x1802547da`
- name: `?BeginDownload@NetDownload@@QEAAJXZ`
- size: `178`
- prototype: `__int64 __fastcall(NetDownload *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180253ca0`
- `0x180253e50`

## callees

- `0x18012a85c`
- `0x1801cd438`
- `0x18020f4b8`
- `0x180254728`

## import_xrefs

- `kernel32!GetLastError` at `0x1802547a9`
- `kernel32!GetLastError` at `0x1802547a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802547c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802547c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18025474b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18025474b`
- `WININET!HttpSendRequestW` at `0x180254795`
- `WININET!HttpSendRequestW` at `0x180254795`

## string_xrefs

- `0x180254768`: `Accept-Encoding: gzip, deflate\nOrigin: file:\nUser-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/51.0.2704.79 Safari/537.36 Edge/14.14931`

## pseudocode

```c

```
