# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CRehydrationTaskHandler>>,ATL::CComCreator<ATL::CComAggObject<CRehydrationTaskHandler>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800031e0`
- end: `0x1800031ee`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCRehydrationTaskHandler@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCRehydrationTaskHandler@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180003214`
- `0x18000349c`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CRehydrationTaskHandler>>,ATL::CComCreator<ATL::CComAggObject<CRehydrationTaskHandler>>>::CreateInstance(
        __int64 a1)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CRehydrationTaskHandler>>::CreateInstance();
  else
    return ATL::CComCreator<ATL::CComObject<CRehydrationTaskHandler>>::CreateInstance();
}

```

## disassembly

```asm
0x1800031e0  test    rcx, rcx
0x1800031e3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCRehydrationTaskHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CRehydrationTaskHandler>>::CreateInstance(void *,_GUID const &,void * *)
0x1800031e9  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCRehydrationTaskHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CRehydrationTaskHandler>>::CreateInstance(void *,_GUID const &,void * *)
```
