# ATL::CComObject<CMSMQPropertyBag>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000f660`
- end: `0x18000f674`
- name: `?QueryInterface@?$CComObject@VCMSMQPropertyBag@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `20`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000f680`

## import_xrefs

- `ATL!__imp_AtlInternalQueryInterface` at `0x18000f66d`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMSMQPropertyBag>::QueryInterface(__int64 a1, __int64 a2, __int64 a3)
{
  return AtlInternalQueryInterface(a1, &`CMSMQPropertyBag::_GetEntries'::`2'::_entries, a2, a3);
}

```

## disassembly

```asm
0x18000f660  mov     r9, r8
0x18000f663  mov     r8, rdx
0x18000f666  lea     rdx, ?_entries@?1??_GetEntries@CMSMQPropertyBag@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CMSMQPropertyBag::_GetEntries(void)'::`2'::_entries
0x18000f66d  jmp     cs:__imp_AtlInternalQueryInterface
```
