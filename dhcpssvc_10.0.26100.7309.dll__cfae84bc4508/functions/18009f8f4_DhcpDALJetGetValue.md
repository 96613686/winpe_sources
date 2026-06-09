# DhcpDALJetGetValue

- ea: `0x18009f8f4`
- end: `0x18009fa8d`
- name: `DhcpDALJetGetValue`
- size: `409`
- prototype: `__int64 __usercall@<rax>(JET_SESID sesid@<rcx>, JET_TABLEID tableid@<rdx>, JET_COLUMNID columnid@<r8d>, __int64)`
- caller_count: `14`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000d97c`
- `0x18004b51c`
- `0x180055478`
- `0x18009d6d4`
- `0x18009db78`
- `0x18009e198`
- `0x18009e4f8`
- `0x1800a7e5c`
- `0x1800b5590`
- `0x1800b57b8`
- `0x1800b5c8c`
- `0x1800be94c`
- `0x1800c44ac`
- `0x1800c47f4`

## callees

- `0x18009f8f4`
- `0x18009fee0`

## import_xrefs

- `ESENT!JetRetrieveColumn` at `0x18009f946`
- `ESENT!JetRetrieveColumn` at `0x18009f979`
- `ESENT!JetRetrieveColumn` at `0x18009fa1d`
- `ESENT!JetRetrieveColumn` at `0x18009f946`
- `ESENT!JetRetrieveColumn` at `0x18009f979`
- `ESENT!JetRetrieveColumn` at `0x18009fa1d`
- `KERNEL32!HeapAlloc` at `0x18009f9d9`
- `KERNEL32!HeapAlloc` at `0x18009f9d9`
- `KERNEL32!GetProcessHeap` at `0x18009f9c5`
- `KERNEL32!GetProcessHeap` at `0x18009fa4c`
- `KERNEL32!GetProcessHeap` at `0x18009f9c5`
- `KERNEL32!GetProcessHeap` at `0x18009fa4c`
- `KERNEL32!HeapFree` at `0x18009fa60`
- `KERNEL32!HeapFree` at `0x18009fa60`

## pseudocode

```c

```
