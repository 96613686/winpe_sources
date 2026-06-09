# WaitForNLBindingEvent(_GUID const *,uchar)

- ea: `0x18001f024`
- end: `0x18001f1c3`
- name: `?WaitForNLBindingEvent@@YAXPEBU_GUID@@E@Z`
- size: `415`
- prototype: `void __fastcall(const struct _GUID *, char)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001e9cc`
- `0x18001f404`

## callees

- `0x18000d7c0`
- `0x18001f024`

## import_xrefs

- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18001f050`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18001f050`
- `IPHLPAPI!NotifyIpInterfaceChange` at `0x18001f0f0`
- `IPHLPAPI!NotifyIpInterfaceChange` at `0x18001f0f0`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x18001f195`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x18001f195`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f14b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f14b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f08d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f08d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f0a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f0a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f1ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f1ab`

## string_xrefs

- `0x18001f0c6`: `%ws: CreateEvent failed:0x%x`

## pseudocode

```c

```
