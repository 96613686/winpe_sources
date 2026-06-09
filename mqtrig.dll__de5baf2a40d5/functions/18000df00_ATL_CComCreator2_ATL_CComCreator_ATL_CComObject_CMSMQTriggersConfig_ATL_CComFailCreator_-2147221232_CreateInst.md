# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMSMQTriggersConfig>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000df00`
- end: `0x18000df22`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCMSMQTriggersConfig@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000df00`
- `0x18000e570`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMSMQTriggersConfig>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<CMSMQTriggersConfig>>::CreateInstance();
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x18000df00  test    rcx, rcx
0x18000df03  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCMSMQTriggersConfig@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CMSMQTriggersConfig>>::CreateInstance(void *,_GUID const &,void * *)
0x18000df09  test    r8, r8
0x18000df0c  jnz     short loc_18000DF15
0x18000df0e  mov     eax, 80004003h
0x18000df13  jmp     short locret_18000DF21
0x18000df15  mov     qword ptr [r8], 0
0x18000df1c  mov     eax, 80040110h
0x18000df21  retn
```
