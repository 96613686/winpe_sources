# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CEnhancedStorageAct>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180009ac0`
- end: `0x180009ae2`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCEnhancedStorageAct@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009ac0`
- `0x180009b78`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CEnhancedStorageAct>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<CEnhancedStorageAct>>::CreateInstance(0, a2, a3);
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x180009ac0  test    rcx, rcx
0x180009ac3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCEnhancedStorageAct@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CEnhancedStorageAct>>::CreateInstance(void *,_GUID const &,void * *)
0x180009ac9  test    r8, r8
0x180009acc  jnz     short loc_180009AD5
0x180009ace  mov     eax, 80004003h
0x180009ad3  jmp     short locret_180009AE1
0x180009ad5  mov     qword ptr [r8], 0
0x180009adc  mov     eax, 80040110h
0x180009ae1  retn
```
