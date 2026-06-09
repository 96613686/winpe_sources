# ATL::CComObject<CGameExplorer>::QueryInterface(_GUID const &,void * *)

- ea: `0x180002310`
- end: `0x180002322`
- name: `?QueryInterface@?$CComObject@VCGameExplorer@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002330`

## callees

- `0x180001e28`

## pseudocode

```c
int __fastcall ATL::CComObject<CGameExplorer>::QueryInterface(void *a1, const struct _GUID *a2, void **a3)
{
  return ATL::AtlInternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CGameExplorer::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180002310  mov     r9, r8; void **
0x180002313  mov     r8, rdx; struct _GUID *
0x180002316  lea     rdx, ?_entries@?1??_GetEntries@CGameExplorer@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000231d  jmp     ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
