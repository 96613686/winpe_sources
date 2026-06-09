# NegpBuildLogonSession(_LUID *,int,unsigned __int64,unsigned __int64)

- ea: `0x18008ac70`
- end: `0x18008ae6d`
- name: `?NegpBuildLogonSession@@YAPEAU_NEG_LOGON_SESSION@@PEAU_LUID@@H_K1@Z`
- size: `509`
- prototype: `struct _NEG_LOGON_SESSION *__fastcall(struct _LUID *, int, unsigned __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18009ac50`
- `0x1800d3a4c`

## callees

- `0x1800098c4`
- `0x180011278`
- `0x180016f70`
- `0x18008ac70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008acc0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008acc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008acd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ace5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008acf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008acd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ace5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008acf3`
- `ntdll!RtlInitializeResource` at `0x18008ad5b`
- `ntdll!RtlInitializeResource` at `0x18008ad5b`
- `ntdll!RtlAvlInsertNodeEx` at `0x18008ae2d`
- `ntdll!RtlAvlInsertNodeEx` at `0x18008ae2d`
- `ntdll!RtlLeaveCriticalSection` at `0x18008ae40`
- `ntdll!RtlLeaveCriticalSection` at `0x18008ae40`
- `ntdll!RtlEnterCriticalSection` at `0x18008adbd`
- `ntdll!RtlEnterCriticalSection` at `0x18008adbd`

## pseudocode

```c

```
