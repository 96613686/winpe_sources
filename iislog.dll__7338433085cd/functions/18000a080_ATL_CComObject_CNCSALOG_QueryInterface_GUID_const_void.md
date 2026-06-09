# ATL::CComObject<CNCSALOG>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000a080`
- end: `0x18000a094`
- name: `?QueryInterface@?$CComObject@VCNCSALOG@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a0a0`

## import_xrefs

- `ATL!__imp_AtlInternalQueryInterface` at `0x18000a08d`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CNCSALOG>::QueryInterface(__int64 a1, __int64 a2, __int64 a3)
{
  return AtlInternalQueryInterface(a1, &`CNCSALOG::_GetEntries'::`2'::_entries, a2, a3);
}

```

## disassembly

```asm
0x18000a080  mov     r9, r8
0x18000a083  mov     r8, rdx
0x18000a086  lea     rdx, ?_entries@?1??_GetEntries@CNCSALOG@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CNCSALOG::_GetEntries(void)'::`2'::_entries
0x18000a08d  jmp     cs:__imp_AtlInternalQueryInterface
```
