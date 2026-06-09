# DllGetActivationFactory

- ea: `0x18003de40`
- end: `0x18003e12b`
- name: `DllGetActivationFactory`
- size: `747`
- prototype: `__int64 __fastcall(HSTRING string)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18003de40`
- `0x180083c10`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003e07d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003e07d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003df92`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003df92`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003e0aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003e0aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003dfd7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003e0fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003dfd7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003e0fe`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18003de7b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18003de7b`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18003dfa8`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18003e0d8`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18003dfa8`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18003e0d8`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18003e095`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18003e095`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18003deae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18003deae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003decb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003decb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18003de99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18003de99`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18003e032`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18003e032`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18003e0cd`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18003e0cd`

## string_xrefs

- `0x18003dfff`: `activatibleClassId`

## pseudocode

```c

```
