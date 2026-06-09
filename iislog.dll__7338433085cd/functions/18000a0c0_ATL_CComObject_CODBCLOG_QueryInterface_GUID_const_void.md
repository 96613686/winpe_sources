# ATL::CComObject<CODBCLOG>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000a0c0`
- end: `0x18000a0d4`
- name: `?QueryInterface@?$CComObject@VCODBCLOG@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ATL!__imp_AtlInternalQueryInterface` at `0x18000a0cd`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CODBCLOG>::QueryInterface(__int64 a1, __int64 a2, __int64 a3)
{
  return AtlInternalQueryInterface(a1, &`CODBCLOG::_GetEntries'::`2'::_entries, a2, a3);
}

```

## disassembly

```asm
0x18000a0c0  mov     r9, r8
0x18000a0c3  mov     r8, rdx
0x18000a0c6  lea     rdx, ?_entries@?1??_GetEntries@CODBCLOG@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `CODBCLOG::_GetEntries(void)'::`2'::_entries
0x18000a0cd  jmp     cs:__imp_AtlInternalQueryInterface
```
