# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CDict>>,ATL::CComCreator<ATL::CComAggObject<CDict>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000f590`
- end: `0x18000f59e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCDict@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCDict@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000f7e8`
- `0x18000fb44`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CDict>>,ATL::CComCreator<ATL::CComAggObject<CDict>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CDict>>::CreateInstance(a1, a2, a3);
  else
    return ATL::CComCreator<ATL::CComObject<CDict>>::CreateInstance(0, a2, a3);
}

```

## disassembly

```asm
0x18000f590  test    rcx, rcx
0x18000f593  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCDict@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CDict>>::CreateInstance(void *,_GUID const &,void * *)
0x18000f599  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCDict@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CDict>>::CreateInstance(void *,_GUID const &,void * *)
```
