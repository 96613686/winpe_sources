# CClfsRequest::WriteRestart(_IRP *,void *,ulong,__int64 const &,__int64 &,__int64 const &,_CLS_LSN const &,uchar,_CLS_LSN &,_KEVENT *,ulong &)

- ea: `0x14005c274`
- end: `0x14005c52f`
- name: `?WriteRestart@CClfsRequest@@QEAAJPEAU_IRP@@PEAXKAEB_JAEA_J2AEBT_CLS_LSN@@EAEAT3@PEAU_KEVENT@@AEAK@Z`
- size: `699`
- prototype: `__int64 __usercall@<rax>(CClfsRequest *__hidden this@<rcx>, struct _IRP *@<rdx>, void *@<r8>, unsigned int@<r9d>, const __int64 *, __int64 *, const __int64 *, const union _CLS_LSN *, char, union _CLS_LSN *, struct _KEVENT *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14005ba4c`

## callees

- `0x140007470`
- `0x14000f3d4`
- `0x14000f688`
- `0x140017f20`
- `0x14005c274`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14005c481`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005c481`
- `ntoskrnl!KeClearEvent` at `0x14005c380`
- `ntoskrnl!KeClearEvent` at `0x14005c380`

## pseudocode

```c

```
