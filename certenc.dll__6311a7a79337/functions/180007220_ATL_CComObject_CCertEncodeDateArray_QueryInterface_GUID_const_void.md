# ATL::CComObject<CCertEncodeDateArray>::QueryInterface(_GUID const &,void * *)

- ea: `0x180007220`
- end: `0x180007234`
- name: `?QueryInterface@?$CComObject@VCCertEncodeDateArray@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180007240`

## import_xrefs

- `ATL!__imp_AtlInternalQueryInterface` at `0x18000722d`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCertEncodeDateArray>::QueryInterface(__int64 a1, __int64 a2, __int64 a3)
{
  return AtlInternalQueryInterface(a1, &`CCertEncodeDateArray::_GetEntries'::`2'::_entries, a2, a3);
}

```

## disassembly

```asm
0x180007220  mov     r9, r8
0x180007223  mov     r8, rdx
0x180007226  lea     rdx, ?_entries@?1??_GetEntries@CCertEncodeDateArray@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CCertEncodeDateArray::_GetEntries(void)'::`2'::_entries
0x18000722d  jmp     cs:__imp_AtlInternalQueryInterface
```
