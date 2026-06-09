# DllGetActivationFactory

- ea: `0x180012900`
- end: `0x180012ad0`
- name: `DllGetActivationFactory`
- size: `464`
- prototype: `__int64 __fastcall(HSTRING string, _QWORD *Ptr)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180004f70`
- `0x180011c4c`
- `0x180012900`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001293b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001293b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180012a2d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180012a2d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180012a9e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180012a9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18001297c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18001297c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180012960`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180012960`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800129a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800129a0`

## string_xrefs

- `0x180012a67`: `activatibleClassId`

## pseudocode

```c

```
