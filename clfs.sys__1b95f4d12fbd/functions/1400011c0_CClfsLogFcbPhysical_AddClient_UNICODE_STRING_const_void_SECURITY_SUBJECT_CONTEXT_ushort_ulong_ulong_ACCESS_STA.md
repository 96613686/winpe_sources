# CClfsLogFcbPhysical::AddClient(_UNICODE_STRING const &,void *,_SECURITY_SUBJECT_CONTEXT &,ushort,ulong,ulong,_ACCESS_STATE *,char,_FILE_OBJECT *,_FILE_OBJECT *)

- ea: `0x1400011c0`
- end: `0x14000146d`
- name: `?AddClient@CClfsLogFcbPhysical@@QEAAJAEBU_UNICODE_STRING@@PEAXAEAU_SECURITY_SUBJECT_CONTEXT@@GKKPEAU_ACCESS_STATE@@DPEAU_FILE_OBJECT@@4@Z`
- size: `685`
- prototype: `__int64 __fastcall(CClfsLogFcbPhysical *__hidden this, const struct _UNICODE_STRING *, void *, struct _SECURITY_SUBJECT_CONTEXT *, unsigned __int16, ACCESS_MASK, ULONG, struct _ACCESS_STATE *, char, struct _FILE_OBJECT *, struct _FILE_OBJECT *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140007f2c`
- `0x14006d048`

## callees

- `0x1400011c0`
- `0x140005840`
- `0x140007200`
- `0x140017f20`
- `0x140034918`
- `0x140036aa8`
- `0x140059e80`
- `0x140073a28`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140001219`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140001219`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x1400012eb`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x1400012eb`

## pseudocode

```c

```
