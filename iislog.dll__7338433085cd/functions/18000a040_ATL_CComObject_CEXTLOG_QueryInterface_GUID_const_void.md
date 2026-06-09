# ATL::CComObject<CEXTLOG>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000a040`
- end: `0x18000a054`
- name: `?QueryInterface@?$CComObject@VCEXTLOG@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a060`

## import_xrefs

- `ATL!__imp_AtlInternalQueryInterface` at `0x18000a04d`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEXTLOG>::QueryInterface(__int64 a1, __int64 a2, __int64 a3)
{
  return AtlInternalQueryInterface(a1, &`CEXTLOG::_GetEntries'::`2'::_entries, a2, a3);
}

```

## disassembly

```asm
0x18000a040  mov     r9, r8
0x18000a043  mov     r8, rdx
0x18000a046  lea     rdx, ?_entries@?1??_GetEntries@CEXTLOG@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CEXTLOG::_GetEntries(void)'::`2'::_entries
0x18000a04d  jmp     cs:__imp_AtlInternalQueryInterface
```
