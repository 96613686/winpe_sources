# AsyncRpcCall(ushort *,_CompiledRules *,_ErrorReport *)

- ea: `0x180433d38`
- end: `0x180433f51`
- name: `?AsyncRpcCall@@YAKPEAGPEAU_CompiledRules@@PEAU_ErrorReport@@@Z`
- size: `537`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _CompiledRules *, struct _ErrorReport *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180432e94`

## callees

- `0x18001e090`
- `0x18001ea60`
- `0x180433d38`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x180433eee`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180433eee`
- `RPCRT4!RpcAsyncCancelCall` at `0x180433ed7`
- `RPCRT4!RpcAsyncCancelCall` at `0x180433ed7`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180433e0c`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180433e0c`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180433e68`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180433e68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180433dfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180433dfa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180433dcd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180433f23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180433dcd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180433f23`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180433db7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180433db7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180433de7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180433de7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180433f16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180433f16`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180433ead`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180433ead`

## pseudocode

```c

```
