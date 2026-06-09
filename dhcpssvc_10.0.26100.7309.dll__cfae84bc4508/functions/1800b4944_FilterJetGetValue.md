# FilterJetGetValue

- ea: `0x1800b4944`
- end: `0x1800b4ad9`
- name: `FilterJetGetValue`
- size: `405`
- prototype: `__int64 __usercall@<rax>(JET_SESID sesid@<rcx>, JET_TABLEID tableid@<rdx>, JET_COLUMNID columnid@<r8d>, unsigned int *)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800b31a0`
- `0x1800b3480`
- `0x1800b36e4`
- `0x1800b3e40`
- `0x1800b50e0`

## callees

- `0x1800b4944`
- `0x1800b4f88`

## import_xrefs

- `ESENT!JetRetrieveColumn` at `0x1800b4998`
- `ESENT!JetRetrieveColumn` at `0x1800b49db`
- `ESENT!JetRetrieveColumn` at `0x1800b4a7c`
- `ESENT!JetRetrieveColumn` at `0x1800b4998`
- `ESENT!JetRetrieveColumn` at `0x1800b49db`
- `ESENT!JetRetrieveColumn` at `0x1800b4a7c`
- `KERNEL32!LocalAlloc` at `0x1800b4a37`
- `KERNEL32!LocalAlloc` at `0x1800b4a37`
- `KERNEL32!LocalFree` at `0x1800b4aab`
- `KERNEL32!LocalFree` at `0x1800b4aab`

## pseudocode

```c

```
