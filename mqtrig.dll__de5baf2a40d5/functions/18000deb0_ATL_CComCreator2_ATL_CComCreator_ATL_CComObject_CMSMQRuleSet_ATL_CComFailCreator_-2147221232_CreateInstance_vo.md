# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMSMQRuleSet>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000deb0`
- end: `0x18000ded2`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCMSMQRuleSet@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000deb0`
- `0x18000e388`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMSMQRuleSet>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<CMSMQRuleSet>>::CreateInstance();
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x18000deb0  test    rcx, rcx
0x18000deb3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCMSMQRuleSet@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CMSMQRuleSet>>::CreateInstance(void *,_GUID const &,void * *)
0x18000deb9  test    r8, r8
0x18000debc  jnz     short loc_18000DEC5
0x18000debe  mov     eax, 80004003h
0x18000dec3  jmp     short locret_18000DED1
0x18000dec5  mov     qword ptr [r8], 0
0x18000decc  mov     eax, 80040110h
0x18000ded1  retn
```
