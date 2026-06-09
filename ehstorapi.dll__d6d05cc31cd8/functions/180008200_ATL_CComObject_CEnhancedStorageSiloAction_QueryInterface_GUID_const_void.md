# ATL::CComObject<CEnhancedStorageSiloAction>::QueryInterface(_GUID const &,void * *)

- ea: `0x180008200`
- end: `0x180008212`
- name: `?QueryInterface@?$CComObject@VCEnhancedStorageSiloAction@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000225c`

## pseudocode

```c
int __fastcall ATL::CComObject<CEnhancedStorageSiloAction>::QueryInterface(void *a1, const struct _GUID *a2, void **a3)
{
  return ATL::AtlInternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CEnhancedStorageSiloAction::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180008200  mov     r9, r8; void **
0x180008203  mov     r8, rdx; struct _GUID *
0x180008206  lea     rdx, ?_entries@?1??_GetEntries@CEnhancedStorageSiloAction@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000820d  jmp     ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
