# ATL::CComObject<CRAHelperClass>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000aed0`
- end: `0x18000aee2`
- name: `?QueryInterface@?$CComObject@VCRAHelperClass@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: `int __fastcall(void *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000aef0`
- `0x18000af00`

## callees

- `0x180009730`

## pseudocode

```c
int __fastcall ATL::CComObject<CRAHelperClass>::QueryInterface(void *a1, const struct _GUID *a2, void **a3)
{
  return ATL::AtlInternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CNetDiagHelperEx::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x18000aed0  mov     r9, r8; void **
0x18000aed3  mov     r8, rdx; struct _GUID *
0x18000aed6  lea     rdx, ?_entries@?1??_GetEntries@CNetDiagHelperEx@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000aedd  jmp     ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
