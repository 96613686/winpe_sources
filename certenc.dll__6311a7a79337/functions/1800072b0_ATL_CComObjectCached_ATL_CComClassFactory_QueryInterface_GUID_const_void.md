# ATL::CComObjectCached<ATL::CComClassFactory>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800072b0`
- end: `0x1800072c4`
- name: `?QueryInterface@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ATL!__imp_AtlInternalQueryInterface` at `0x1800072bd`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::QueryInterface(__int64 a1, __int64 a2, __int64 a3)
{
  return AtlInternalQueryInterface(a1, &`ATL::CComClassFactory::_GetEntries'::`2'::_entries, a2, a3);
}

```

## disassembly

```asm
0x1800072b0  mov     r9, r8
0x1800072b3  mov     r8, rdx
0x1800072b6  lea     rdx, ?_entries@?1??_GetEntries@CComClassFactory@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; ATL::_ATL_INTMAP_ENTRY const near * const `ATL::CComClassFactory::_GetEntries(void)'::`2'::_entries
0x1800072bd  jmp     cs:__imp_AtlInternalQueryInterface
```
