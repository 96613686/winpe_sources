# ClientSideConnection::GetCachedFile(_GUID const &,void const *,uint,bool,bool,AlpcReply<16> *)

- ea: `0x1801e81c4`
- end: `0x1801e8366`
- name: `?GetCachedFile@ClientSideConnection@@QEAAJAEBU_GUID@@PEBXI_N2PEAU?$AlpcReply@$0BA@@@@Z`
- size: `418`
- prototype: `__int64 __usercall@<rax>(ClientSideConnection *this@<rcx>, char, char, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1801e811c`
- `0x180235274`

## callees

- `0x18012a85c`
- `0x1801e81c4`
- `0x1801e836c`
- `0x1801e8410`
- `0x1801f37b0`
- `0x18021e1b6`
- `0x18028f248`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801e8218`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801e8218`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801e8299`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801e8299`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1801e82e0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1801e82e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801e8318`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801e8318`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1801e82c8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1801e82f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1801e82c8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1801e82f1`

## pseudocode

```c

```
