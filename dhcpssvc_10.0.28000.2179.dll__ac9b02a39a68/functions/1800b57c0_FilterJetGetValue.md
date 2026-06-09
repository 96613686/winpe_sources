# FilterJetGetValue

- ea: `0x1800b57c0`
- end: `0x1800b596d`
- name: `FilterJetGetValue`
- size: `429`
- prototype: `__int64 __usercall@<rax>(JET_SESID sesid@<rcx>, JET_TABLEID tableid@<rdx>, JET_COLUMNID columnid@<r8d>, unsigned int *)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800b4000`
- `0x1800b42e0`
- `0x1800b454c`
- `0x1800b4cac`
- `0x1800b5f7c`

## callees

- `0x1800b57c0`
- `0x1800b5e24`

## import_xrefs

- `ESENT!JetRetrieveColumn` at `0x1800b5820`
- `ESENT!JetRetrieveColumn` at `0x1800b5866`
- `ESENT!JetRetrieveColumn` at `0x1800b5910`
- `ESENT!JetRetrieveColumn` at `0x1800b5820`
- `ESENT!JetRetrieveColumn` at `0x1800b5866`
- `ESENT!JetRetrieveColumn` at `0x1800b5910`
- `KERNEL32!LocalAlloc` at `0x1800b58c5`
- `KERNEL32!LocalAlloc` at `0x1800b58c5`
- `KERNEL32!LocalFree` at `0x1800b593f`
- `KERNEL32!LocalFree` at `0x1800b593f`

## pseudocode

```c

```
