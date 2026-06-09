# CMessageCall::ClientAllocateRequestBuffer(ulong,_GUID const &)

- ea: `0x1800cca80`
- end: `0x1800ccedc`
- name: `?ClientAllocateRequestBuffer@CMessageCall@@AEAAJKAEBU_GUID@@@Z`
- size: `1116`
- prototype: `HRESULT __fastcall(CMessageCall *this, unsigned int size, const _GUID *moidForTracing)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18009eed4`
- `0x1801b1a50`

## callees

- `0x18000712c`
- `0x18001d0e8`
- `0x18003a8bc`
- `0x1800472a0`
- `0x1800874e0`
- `0x1800cca80`
- `0x1801999b0`

## import_xrefs

- `RPCRT4!I_RpcGetBufferWithObject` at `0x1800ccbdc`
- `RPCRT4!I_RpcGetBufferWithObject` at `0x1800ccbdc`
- `ntdll!EtwEventActivityIdControl` at `0x1800ccba6`
- `ntdll!EtwEventActivityIdControl` at `0x1800ccbbc`
- `ntdll!EtwEventActivityIdControl` at `0x1800cce97`
- `ntdll!EtwEventActivityIdControl` at `0x1800cceb2`
- `ntdll!EtwEventActivityIdControl` at `0x1800ccba6`
- `ntdll!EtwEventActivityIdControl` at `0x1800ccbbc`
- `ntdll!EtwEventActivityIdControl` at `0x1800cce97`
- `ntdll!EtwEventActivityIdControl` at `0x1800cceb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ccb05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ccb05`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ccb21`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ccb21`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ccaf0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ccaf0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ccb19`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ccb19`

## string_xrefs

- `0x1800ccb45`: `onecore\com\combase\dcomrem\call.cxx`
- `0x1800ccd1e`: `onecore\com\combase\dcomrem\call.cxx`
- `0x1800cce48`: `onecore\com\combase\dcomrem\call.cxx`

## pseudocode

```c

```
