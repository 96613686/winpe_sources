# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CAdvancedConfig>>,ATL::CComCreator<ATL::CComAggObject<CAdvancedConfig>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003fe0`
- end: `0x180003fee`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCAdvancedConfig@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCAdvancedConfig@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003ff4`
- `0x180004120`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CAdvancedConfig>>,ATL::CComCreator<ATL::CComAggObject<CAdvancedConfig>>>::CreateInstance(
        __int64 a1)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CAdvancedConfig>>::CreateInstance();
  else
    return ATL::CComCreator<ATL::CComObject<CAdvancedConfig>>::CreateInstance();
}

```

## disassembly

```asm
0x180003fe0  test    rcx, rcx
0x180003fe3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCAdvancedConfig@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CAdvancedConfig>>::CreateInstance(void *,_GUID const &,void * *)
0x180003fe9  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCAdvancedConfig@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CAdvancedConfig>>::CreateInstance(void *,_GUID const &,void * *)
```
