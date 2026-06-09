# ATL::CComObject<CCertEncodeCRLDistInfo>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800071f0`
- end: `0x180007204`
- name: `?QueryInterface@?$CComObject@VCCertEncodeCRLDistInfo@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180007210`

## import_xrefs

- `ATL!__imp_AtlInternalQueryInterface` at `0x1800071fd`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCertEncodeCRLDistInfo>::QueryInterface(__int64 a1, __int64 a2, __int64 a3)
{
  return AtlInternalQueryInterface(a1, &`CCertEncodeCRLDistInfo::_GetEntries'::`2'::_entries, a2, a3);
}

```

## disassembly

```asm
0x1800071f0  mov     r9, r8
0x1800071f3  mov     r8, rdx
0x1800071f6  lea     rdx, ?_entries@?1??_GetEntries@CCertEncodeCRLDistInfo@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CCertEncodeCRLDistInfo::_GetEntries(void)'::`2'::_entries
0x1800071fd  jmp     cs:__imp_AtlInternalQueryInterface
```
