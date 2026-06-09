# CClfsLogFcbVirtual::ReadLogBlock(_FILE_OBJECT *,_CLS_LSN const &,ulong,_CLFS_READ_BUFFER const &,ulong,IClfsRequestAsync *,ulong,_CLS_LSN &,ulong &)

- ea: `0x140072380`
- end: `0x1400725ed`
- name: `?ReadLogBlock@CClfsLogFcbVirtual@@UEAAJPEAU_FILE_OBJECT@@AEBT_CLS_LSN@@KAEBU_CLFS_READ_BUFFER@@KPEAUIClfsRequestAsync@@KAEAT3@AEAK@Z`
- size: `621`
- prototype: `__int64 __usercall@<rax>(CClfsLogFcbVirtual *__hidden this@<rcx>, struct _FILE_OBJECT *@<rdx>, const union _CLS_LSN *@<r8>, unsigned int@<r9d>, const struct _CLFS_READ_BUFFER *, unsigned int, struct IClfsRequestAsync *, unsigned int, union _CLS_LSN *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140005840`
- `0x140007294`
- `0x140008330`
- `0x140008c40`
- `0x14000d32c`
- `0x140017f20`
- `0x140072380`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140072408`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14007249a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140072408`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14007249a`

## pseudocode

```c

```
