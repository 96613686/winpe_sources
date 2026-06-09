# CClfsLogFcbPhysical::OpenClient(_UNICODE_STRING const &,void *,_SECURITY_SUBJECT_CONTEXT &,ulong,ulong,_ACCESS_STATE *,char,_FILE_OBJECT *,_FILE_OBJECT *)

- ea: `0x140007f2c`
- end: `0x14000831f`
- name: `?OpenClient@CClfsLogFcbPhysical@@QEAAJAEBU_UNICODE_STRING@@PEAXAEAU_SECURITY_SUBJECT_CONTEXT@@KKPEAU_ACCESS_STATE@@DPEAU_FILE_OBJECT@@4@Z`
- size: `1011`
- prototype: `__int64 __usercall@<rax>(CClfsLogFcbPhysical *__hidden this@<rcx>, const struct _UNICODE_STRING *@<rdx>, void *@<r8>, struct _SECURITY_SUBJECT_CONTEXT *@<r9>, ACCESS_MASK, ULONG, struct _ACCESS_STATE *, char, struct _FILE_OBJECT *, struct _FILE_OBJECT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14006d048`

## callees

- `0x1400011c0`
- `0x140005840`
- `0x140007200`
- `0x140007f2c`
- `0x140015394`
- `0x140017f20`
- `0x140034610`
- `0x140059e80`
- `0x140074c68`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140007f81`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140007f81`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140008190`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140008190`

## pseudocode

```c

```
