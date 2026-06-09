# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CEnhancedStorageSilo>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180009b20`
- end: `0x180009b42`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCEnhancedStorageSilo@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009b20`
- `0x180009d90`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CEnhancedStorageSilo>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<CEnhancedStorageSilo>>::CreateInstance(0, a2, a3);
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x180009b20  test    rcx, rcx
0x180009b23  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCEnhancedStorageSilo@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CEnhancedStorageSilo>>::CreateInstance(void *,_GUID const &,void * *)
0x180009b29  test    r8, r8
0x180009b2c  jnz     short loc_180009B35
0x180009b2e  mov     eax, 80004003h
0x180009b33  jmp     short locret_180009B41
0x180009b35  mov     qword ptr [r8], 0
0x180009b3c  mov     eax, 80040110h
0x180009b41  retn
```
