# ATL::CComObject<CASCLOG>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000a000`
- end: `0x18000a014`
- name: `?QueryInterface@?$CComObject@VCASCLOG@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a020`

## import_xrefs

- `ATL!__imp_AtlInternalQueryInterface` at `0x18000a00d`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CASCLOG>::QueryInterface(__int64 a1, __int64 a2, __int64 a3)
{
  return AtlInternalQueryInterface(a1, &`CASCLOG::_GetEntries'::`2'::_entries, a2, a3);
}

```

## disassembly

```asm
0x18000a000  mov     r9, r8
0x18000a003  mov     r8, rdx
0x18000a006  lea     rdx, ?_entries@?1??_GetEntries@CASCLOG@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CASCLOG::_GetEntries(void)'::`2'::_entries
0x18000a00d  jmp     cs:__imp_AtlInternalQueryInterface
```
