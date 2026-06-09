# WciSetupFilter

- ea: `0x1800ab010`
- end: `0x1800ab1c7`
- name: `WciSetupFilter`
- size: `439`
- prototype: `__int64 __usercall@<rax>(LPSECURITY_ATTRIBUTES lpSecurityAttributes@<rcx>, DWORD BytesReturned)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002ece8`

## callees

- `0x1800aae10`
- `0x1800ab010`
- `0x1800ab1d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800ab053`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800ab053`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ab14e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ab15d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ab174`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ab188`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ab14e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ab15d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ab174`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ab188`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab19e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab19e`
- `ntdll!RtlNtStatusToDosError` at `0x1800ab12b`
- `ntdll!RtlNtStatusToDosError` at `0x1800ab12b`
- `FLTLIB!FilterSendMessage` at `0x1800ab112`
- `FLTLIB!FilterSendMessage` at `0x1800ab112`
- `FLTLIB!FilterConnectCommunicationPort` at `0x1800ab0e4`
- `FLTLIB!FilterConnectCommunicationPort` at `0x1800ab0e4`

## pseudocode

```c

```
