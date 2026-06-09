# ServiceControlHandler(ulong,ulong,void *,void *)

- ea: `0x180007e50`
- end: `0x180007e9d`
- name: `?ServiceControlHandler@@YAKKKPEAX0@Z`
- size: `77`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180007cec`
- `0x180007e50`
- `0x180008128`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007e90`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007e90`

## pseudocode

```c

```
