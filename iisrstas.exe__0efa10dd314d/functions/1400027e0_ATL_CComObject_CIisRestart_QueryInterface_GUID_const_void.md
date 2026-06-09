# ATL::CComObject<CIisRestart>::QueryInterface(_GUID const &,void * *)

- ea: `0x1400027e0`
- end: `0x1400027f4`
- name: `?QueryInterface@?$CComObject@VCIisRestart@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ATL!__imp_AtlInternalQueryInterface` at `0x1400027ed`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CIisRestart>::QueryInterface(__int64 a1, __int64 a2, __int64 a3)
{
  return AtlInternalQueryInterface(a1, &`CIisRestart::_GetEntries'::`2'::_entries, a2, a3);
}

```

## disassembly

```asm
0x1400027e0  mov     r9, r8
0x1400027e3  mov     r8, rdx
0x1400027e6  lea     rdx, ?_entries@?1??_GetEntries@CIisRestart@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CIisRestart::_GetEntries(void)'::`2'::_entries
0x1400027ed  jmp     cs:__imp_AtlInternalQueryInterface
```
