# ATL::CComObject<CPersistDSO>::QueryInterface(_GUID const &,void * *)

- ea: `0x180019ad0`
- end: `0x180019af1`
- name: `?QueryInterface@?$CComObject@VCPersistDSO@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `33`
- prototype: `__int64 __fastcall(struct CProviderDSO *, struct _GUID *, void **)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180019b00`
- `0x180019b10`
- `0x180019b20`
- `0x180019b40`
- `0x180019b60`
- `0x180019b80`
- `0x180019ba0`
- `0x180019bb0`
- `0x180019bc0`

## callees

- `0x18002e0a4`

## pseudocode

```c
int __fastcall ATL::CComObject<CPersistDSO>::QueryInterface(struct CProviderDSO *a1, struct _GUID *a2, void **a3)
{
  return CProviderDSO::InternalQueryInterface(
           a1,
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CPersistDSO::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180019ad0  sub     rsp, 38h
0x180019ad4  mov     [rsp+38h+var_18], r8; void **
0x180019ad9  mov     r9, rdx; struct _GUID *
0x180019adc  lea     r8, ?_entries@?1??_GetEntries@CPersistDSO@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180019ae3  mov     rdx, rcx; struct CProviderDSO *
0x180019ae6  call    ?InternalQueryInterface@CProviderDSO@@IEAAJPEAV1@PEBU_ATL_INTMAP_ENTRY@ATL@@AEBU_GUID@@PEAPEAX@Z; CProviderDSO::InternalQueryInterface(CProviderDSO *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180019aeb  add     rsp, 38h
0x180019aef  retn
```
