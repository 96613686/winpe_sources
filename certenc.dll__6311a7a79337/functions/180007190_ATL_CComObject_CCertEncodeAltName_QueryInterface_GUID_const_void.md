# ATL::CComObject<CCertEncodeAltName>::QueryInterface(_GUID const &,void * *)

- ea: `0x180007190`
- end: `0x1800071a4`
- name: `?QueryInterface@?$CComObject@VCCertEncodeAltName@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800071b0`

## import_xrefs

- `ATL!__imp_AtlInternalQueryInterface` at `0x18000719d`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCertEncodeAltName>::QueryInterface(__int64 a1, __int64 a2, __int64 a3)
{
  return AtlInternalQueryInterface(a1, &`CCertEncodeAltName::_GetEntries'::`2'::_entries, a2, a3);
}

```

## disassembly

```asm
0x180007190  mov     r9, r8
0x180007193  mov     r8, rdx
0x180007196  lea     rdx, ?_entries@?1??_GetEntries@CCertEncodeAltName@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CCertEncodeAltName::_GetEntries(void)'::`2'::_entries
0x18000719d  jmp     cs:__imp_AtlInternalQueryInterface
```
