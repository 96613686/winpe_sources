# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CDpUrlAccessor>>,ATL::CComCreator<ATL::CComAggObject<CDpUrlAccessor>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004210`
- end: `0x18000421e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCDpUrlAccessor@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCDpUrlAccessor@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004350`
- `0x180004628`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CDpUrlAccessor>>,ATL::CComCreator<ATL::CComAggObject<CDpUrlAccessor>>>::CreateInstance(
        __int64 a1)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CDpUrlAccessor>>::CreateInstance();
  else
    return ATL::CComCreator<ATL::CComObject<CDpUrlAccessor>>::CreateInstance();
}

```

## disassembly

```asm
0x180004210  test    rcx, rcx
0x180004213  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCDpUrlAccessor@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CDpUrlAccessor>>::CreateInstance(void *,_GUID const &,void * *)
0x180004219  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCDpUrlAccessor@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CDpUrlAccessor>>::CreateInstance(void *,_GUID const &,void * *)
```
