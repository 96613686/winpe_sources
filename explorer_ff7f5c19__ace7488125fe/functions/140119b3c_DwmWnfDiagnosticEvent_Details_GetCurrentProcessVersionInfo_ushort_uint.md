# DwmWnfDiagnosticEvent::Details::GetCurrentProcessVersionInfo(ushort *,uint)

- ea: `0x140119b3c`
- end: `0x140119d54`
- name: `?GetCurrentProcessVersionInfo@Details@DwmWnfDiagnosticEvent@@YAJPEAGI@Z`
- size: `536`
- prototype: `__int64 __fastcall(DwmWnfDiagnosticEvent::Details *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140117668`

## callees

- `0x140020580`
- `0x14009ac68`
- `0x14009de4c`
- `0x14010e160`
- `0x14010ed90`
- `0x140119b3c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140119b87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140119b87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140119cfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140119cfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140119bf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140119bf3`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x140119ba2`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x140119ba2`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x140119c34`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x140119c34`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x140119bd9`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x140119bd9`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x140119c6e`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x140119c6e`

## pseudocode

```c

```
