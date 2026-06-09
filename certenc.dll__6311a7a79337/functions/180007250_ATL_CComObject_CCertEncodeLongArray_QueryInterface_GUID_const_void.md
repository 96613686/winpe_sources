# ATL::CComObject<CCertEncodeLongArray>::QueryInterface(_GUID const &,void * *)

- ea: `0x180007250`
- end: `0x180007264`
- name: `?QueryInterface@?$CComObject@VCCertEncodeLongArray@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180007270`

## import_xrefs

- `ATL!__imp_AtlInternalQueryInterface` at `0x18000725d`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCertEncodeLongArray>::QueryInterface(__int64 a1, __int64 a2, __int64 a3)
{
  return AtlInternalQueryInterface(a1, &`CCertEncodeLongArray::_GetEntries'::`2'::_entries, a2, a3);
}

```

## disassembly

```asm
0x180007250  mov     r9, r8
0x180007253  mov     r8, rdx
0x180007256  lea     rdx, ?_entries@?1??_GetEntries@CCertEncodeLongArray@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CCertEncodeLongArray::_GetEntries(void)'::`2'::_entries
0x18000725d  jmp     cs:__imp_AtlInternalQueryInterface
```
