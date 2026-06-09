# ATL::CComObject<CCertEncodeStringArray>::QueryInterface(_GUID const &,void * *)

- ea: `0x180007280`
- end: `0x180007294`
- name: `?QueryInterface@?$CComObject@VCCertEncodeStringArray@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800072a0`

## import_xrefs

- `ATL!__imp_AtlInternalQueryInterface` at `0x18000728d`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCertEncodeStringArray>::QueryInterface(__int64 a1, __int64 a2, __int64 a3)
{
  return AtlInternalQueryInterface(a1, &`CCertEncodeStringArray::_GetEntries'::`2'::_entries, a2, a3);
}

```

## disassembly

```asm
0x180007280  mov     r9, r8
0x180007283  mov     r8, rdx
0x180007286  lea     rdx, ?_entries@?1??_GetEntries@CCertEncodeStringArray@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CCertEncodeStringArray::_GetEntries(void)'::`2'::_entries
0x18000728d  jmp     cs:__imp_AtlInternalQueryInterface
```
