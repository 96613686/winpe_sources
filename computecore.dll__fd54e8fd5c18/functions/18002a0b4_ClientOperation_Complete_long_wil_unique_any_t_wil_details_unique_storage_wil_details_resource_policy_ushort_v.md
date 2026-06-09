# ClientOperation::Complete(long,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ProcessInformation *)

- ea: `0x18002a0b4`
- end: `0x18002a608`
- name: `?Complete@ClientOperation@@QEAA_NJV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUProcessInformation@@@Z`
- size: `1364`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180035ef0`
- `0x180035fd0`
- `0x180049a58`
- `0x180049b6c`

## callees

- `0x1800016ec`
- `0x180001d20`
- `0x1800067c0`
- `0x180006d0c`
- `0x180009e8c`
- `0x180014184`
- `0x180014de4`
- `0x1800188dc`
- `0x180018f60`
- `0x18002a03c`
- `0x18002a0b4`
- `0x18002a610`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002a308`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002a4b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002a308`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002a4b6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a202`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a49a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a202`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a49a`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18002a4ad`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18002a4ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a28d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a28d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a27a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a27a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002a356`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002a356`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a285`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a595`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a285`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a595`

## string_xrefs

- `0x18002a5c6`: `onecore\vm\compute\dll\lib\core\clientoperation.cpp`
- `0x18002a5de`: `onecore\vm\compute\dll\lib\core\clientoperation.cpp`
- `0x18002a5f6`: `onecore\vm\compute\dll\lib\core\clientoperation.cpp`

## pseudocode

```c

```
