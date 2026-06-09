# DllGetClassObject

- ea: `0x180039ed0`
- end: `0x18003a222`
- name: `DllGetClassObject`
- size: `850`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180034240`
- `0x1800381f8`
- `0x180039ed0`
- `0x18003a290`
- `0x18003d8dc`
- `0x18003d92c`
- `0x18004bfd4`
- `0x18005e9e8`
- `0x18005f9b8`
- `0x180064034`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x18003a05b`
- `msvcrt!_resetstkoflw` at `0x18003a142`
- `msvcrt!_resetstkoflw` at `0x18003a05b`
- `msvcrt!_resetstkoflw` at `0x18003a142`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003a0ae`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003a195`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003a0ae`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003a195`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003a049`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003a130`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003a1d0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003a049`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003a130`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003a1d0`

## pseudocode

```c

```
