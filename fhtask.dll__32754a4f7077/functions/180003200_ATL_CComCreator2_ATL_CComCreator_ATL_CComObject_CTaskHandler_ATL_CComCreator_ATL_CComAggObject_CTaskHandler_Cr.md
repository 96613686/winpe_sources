# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CTaskHandler>>,ATL::CComCreator<ATL::CComAggObject<CTaskHandler>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003200`
- end: `0x18000320e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCTaskHandler@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCTaskHandler@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180003358`
- `0x180003600`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CTaskHandler>>,ATL::CComCreator<ATL::CComAggObject<CTaskHandler>>>::CreateInstance(
        __int64 a1)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CTaskHandler>>::CreateInstance();
  else
    return ATL::CComCreator<ATL::CComObject<CTaskHandler>>::CreateInstance();
}

```

## disassembly

```asm
0x180003200  test    rcx, rcx
0x180003203  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCTaskHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CTaskHandler>>::CreateInstance(void *,_GUID const &,void * *)
0x180003209  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCTaskHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CTaskHandler>>::CreateInstance(void *,_GUID const &,void * *)
```
