# DhcpJetGetValueV6

- ea: `0x180013134`
- end: `0x180013304`
- name: `DhcpJetGetValueV6`
- size: `464`
- prototype: `__int64 __usercall@<rax>(JET_COLUMNID columnid@<ecx>, void *pvData@<rdx>, unsigned int *pcbActual@<r8>, JET_SESID sesid)`
- caller_count: `8`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180011ea8`
- `0x180012338`
- `0x1800417c0`
- `0x18007ab8c`
- `0x18007b118`
- `0x18007b6ac`
- `0x18007b994`
- `0x18007bfc0`

## callees

- `0x18000282c`
- `0x18000e814`
- `0x180013134`

## import_xrefs

- `ESENT!JetRetrieveColumn` at `0x180013199`
- `ESENT!JetRetrieveColumn` at `0x1800131da`
- `ESENT!JetRetrieveColumn` at `0x18001327e`
- `ESENT!JetRetrieveColumn` at `0x180013199`
- `ESENT!JetRetrieveColumn` at `0x1800131da`
- `ESENT!JetRetrieveColumn` at `0x18001327e`
- `KERNEL32!LocalAlloc` at `0x180013228`
- `KERNEL32!LocalAlloc` at `0x180013228`
- `KERNEL32!LocalFree` at `0x1800132b0`
- `KERNEL32!LocalFree` at `0x1800132b0`

## pseudocode

```c

```
