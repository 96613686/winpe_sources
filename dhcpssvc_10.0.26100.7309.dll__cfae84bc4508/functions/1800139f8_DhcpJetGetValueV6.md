# DhcpJetGetValueV6

- ea: `0x1800139f8`
- end: `0x180013bb0`
- name: `DhcpJetGetValueV6`
- size: `440`
- prototype: `__int64 __usercall@<rax>(JET_COLUMNID columnid@<ecx>, void *pvData@<rdx>, unsigned int *pcbActual@<r8>, JET_SESID sesid)`
- caller_count: `8`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180012778`
- `0x180012c00`
- `0x180041ce0`
- `0x18007ad70`
- `0x18007b2e4`
- `0x18007b878`
- `0x18007bb54`
- `0x18007c168`

## callees

- `0x180002854`
- `0x18000f144`
- `0x1800139f8`

## import_xrefs

- `ESENT!JetRetrieveColumn` at `0x180013a51`
- `ESENT!JetRetrieveColumn` at `0x180013a8f`
- `ESENT!JetRetrieveColumn` at `0x180013b2a`
- `ESENT!JetRetrieveColumn` at `0x180013a51`
- `ESENT!JetRetrieveColumn` at `0x180013a8f`
- `ESENT!JetRetrieveColumn` at `0x180013b2a`
- `KERNEL32!LocalAlloc` at `0x180013ada`
- `KERNEL32!LocalAlloc` at `0x180013ada`
- `KERNEL32!LocalFree` at `0x180013b5c`
- `KERNEL32!LocalFree` at `0x180013b5c`

## pseudocode

```c

```
