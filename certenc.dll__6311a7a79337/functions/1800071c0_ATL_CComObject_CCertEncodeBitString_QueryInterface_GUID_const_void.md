# ATL::CComObject<CCertEncodeBitString>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800071c0`
- end: `0x1800071d4`
- name: `?QueryInterface@?$CComObject@VCCertEncodeBitString@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800071e0`

## import_xrefs

- `ATL!__imp_AtlInternalQueryInterface` at `0x1800071cd`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCertEncodeBitString>::QueryInterface(__int64 a1, __int64 a2, __int64 a3)
{
  return AtlInternalQueryInterface(a1, &`CCertEncodeBitString::_GetEntries'::`2'::_entries, a2, a3);
}

```

## disassembly

```asm
0x1800071c0  mov     r9, r8
0x1800071c3  mov     r8, rdx
0x1800071c6  lea     rdx, ?_entries@?1??_GetEntries@CCertEncodeBitString@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CCertEncodeBitString::_GetEntries(void)'::`2'::_entries
0x1800071cd  jmp     cs:__imp_AtlInternalQueryInterface
```
