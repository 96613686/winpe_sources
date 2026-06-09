# CClfsLogFcbPhysical::ReadOneRawSectorSync(CClfsAuthContainer * &,ulong &,uchar *,_CLS_LSN &,uchar,_KEVENT *)

- ea: `0x140047450`
- end: `0x140047593`
- name: `?ReadOneRawSectorSync@CClfsLogFcbPhysical@@AEAAJAEAPEAVCClfsAuthContainer@@AEAKPEAEAEAT_CLS_LSN@@EPEAU_KEVENT@@@Z`
- size: `323`
- prototype: `__int64 __usercall@<rax>(CClfsLogFcbPhysical *__hidden this@<rcx>, struct CClfsAuthContainer **@<rdx>, unsigned int *@<r8>, unsigned __int8 *@<r9>, CLFS_LSN *plsn, unsigned __int8, struct _KEVENT *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400119a0`
- `0x140048404`

## callees

- `0x140005f00`
- `0x1400070bc`
- `0x140047450`
- `0x14006b3fc`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140047563`
- `ntoskrnl!KeWaitForSingleObject` at `0x140047563`
- `ntoskrnl!KeClearEvent` at `0x140047495`
- `ntoskrnl!KeClearEvent` at `0x140047495`

## pseudocode

```c

```
