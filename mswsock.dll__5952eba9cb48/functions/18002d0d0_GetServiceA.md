# GetServiceA

- ea: `0x18002d0d0`
- end: `0x18002d17d`
- name: `GetServiceA`
- size: `173`
- prototype: `INT __stdcall(DWORD dwNameSpace, LPGUID lpGuid, LPSTR lpServiceName, DWORD dwProperties, LPVOID lpBuffer, LPDWORD lpdwBufferSize, LPSERVICE_ASYNC_INFO lpServiceAsyncInfo)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x18002cffc`
- `0x18002d0d0`
- `0x18002d1d0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18002d15e`
- `ntdll!RtlFreeHeap` at `0x18002d15e`

## pseudocode

```c

```
