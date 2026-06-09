# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CDpSearchProtocol>>,ATL::CComCreator<ATL::CComAggObject<CDpSearchProtocol>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800041f0`
- end: `0x1800041fe`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCDpSearchProtocol@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCDpSearchProtocol@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004224`
- `0x1800044dc`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CDpSearchProtocol>>,ATL::CComCreator<ATL::CComAggObject<CDpSearchProtocol>>>::CreateInstance(
        __int64 a1)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CDpSearchProtocol>>::CreateInstance();
  else
    return ATL::CComCreator<ATL::CComObject<CDpSearchProtocol>>::CreateInstance();
}

```

## disassembly

```asm
0x1800041f0  test    rcx, rcx
0x1800041f3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCDpSearchProtocol@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CDpSearchProtocol>>::CreateInstance(void *,_GUID const &,void * *)
0x1800041f9  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCDpSearchProtocol@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CDpSearchProtocol>>::CreateInstance(void *,_GUID const &,void * *)
```
