# DllGetActivationFactory

- ea: `0x180010d90`
- end: `0x180010f62`
- name: `DllGetActivationFactory`
- size: `466`
- prototype: `__int64 __fastcall(HSTRING string, PVOID Ptr)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800053a0`
- `0x1800100cc`
- `0x180010d90`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180010dcb`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180010dcb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180010eb7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180010eb7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180010f30`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180010f30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180010e06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180010e06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180010dea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180010dea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180010e2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180010e2a`

## string_xrefs

- `0x180010ef1`: `activatibleClassId`

## pseudocode

```c

```
