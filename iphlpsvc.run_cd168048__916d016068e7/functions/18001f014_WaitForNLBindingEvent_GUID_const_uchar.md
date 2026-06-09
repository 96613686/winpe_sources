# WaitForNLBindingEvent(_GUID const *,uchar)

- ea: `0x18001f014`
- end: `0x18001f1b3`
- name: `?WaitForNLBindingEvent@@YAXPEBU_GUID@@E@Z`
- size: `415`
- prototype: `void __fastcall(const struct _GUID *, unsigned __int8)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001e9bc`
- `0x18001f3f4`

## callees

- `0x18000d7b0`
- `0x18001f014`

## import_xrefs

- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18001f040`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18001f040`
- `IPHLPAPI!NotifyIpInterfaceChange` at `0x18001f0e0`
- `IPHLPAPI!NotifyIpInterfaceChange` at `0x18001f0e0`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x18001f185`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x18001f185`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f13b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f13b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f07d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f07d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f093`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f093`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f19b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f19b`

## string_xrefs

- `0x18001f0b6`: `%ws: CreateEvent failed:0x%x`

## pseudocode

```c

```
