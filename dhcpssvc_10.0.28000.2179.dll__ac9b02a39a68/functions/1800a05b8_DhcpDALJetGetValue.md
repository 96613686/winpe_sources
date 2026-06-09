# DhcpDALJetGetValue

- ea: `0x1800a05b8`
- end: `0x1800a0751`
- name: `DhcpDALJetGetValue`
- size: `409`
- prototype: `__int64 __usercall@<rax>(JET_SESID sesid@<rcx>, JET_TABLEID tableid@<rdx>, JET_COLUMNID columnid@<r8d>, __int64)`
- caller_count: `14`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000d028`
- `0x18004b1dc`
- `0x18005518c`
- `0x18009e38c`
- `0x18009e828`
- `0x18009ee38`
- `0x18009f1a0`
- `0x1800a8b80`
- `0x1800b6430`
- `0x1800b6664`
- `0x1800b6b38`
- `0x1800bf964`
- `0x1800c54a8`
- `0x1800c57f4`

## callees

- `0x1800a05b8`
- `0x1800a0bac`

## import_xrefs

- `ESENT!JetRetrieveColumn` at `0x1800a060a`
- `ESENT!JetRetrieveColumn` at `0x1800a063d`
- `ESENT!JetRetrieveColumn` at `0x1800a06e1`
- `ESENT!JetRetrieveColumn` at `0x1800a060a`
- `ESENT!JetRetrieveColumn` at `0x1800a063d`
- `ESENT!JetRetrieveColumn` at `0x1800a06e1`
- `KERNEL32!HeapAlloc` at `0x1800a069d`
- `KERNEL32!HeapAlloc` at `0x1800a069d`
- `KERNEL32!GetProcessHeap` at `0x1800a0689`
- `KERNEL32!GetProcessHeap` at `0x1800a0710`
- `KERNEL32!GetProcessHeap` at `0x1800a0689`
- `KERNEL32!GetProcessHeap` at `0x1800a0710`
- `KERNEL32!HeapFree` at `0x1800a0724`
- `KERNEL32!HeapFree` at `0x1800a0724`

## pseudocode

```c

```
