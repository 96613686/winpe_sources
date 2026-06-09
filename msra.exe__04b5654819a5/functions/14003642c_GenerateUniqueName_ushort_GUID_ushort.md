# GenerateUniqueName(ushort *,_GUID *,ushort * *)

- ea: `0x14003642c`
- end: `0x1400365f2`
- name: `?GenerateUniqueName@@YAJPEAGPEAU_GUID@@PEAPEAG@Z`
- size: `454`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _GUID *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140030f70`

## callees

- `0x1400080fc`
- `0x140034ce4`
- `0x14003642c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400365cc`
- `KERNEL32!HeapFree` at `0x1400365cc`
- `KERNEL32!GetProcessHeap` at `0x1400364aa`
- `KERNEL32!GetProcessHeap` at `0x1400365b8`
- `KERNEL32!GetProcessHeap` at `0x1400364aa`
- `KERNEL32!GetProcessHeap` at `0x1400365b8`
- `KERNEL32!HeapAlloc` at `0x1400364c1`
- `KERNEL32!HeapAlloc` at `0x1400364c1`

## string_xrefs

- `0x140036598`: `base\diagnosis\ra\racommon\src\stringutils.cpp`

## pseudocode

```c

```
