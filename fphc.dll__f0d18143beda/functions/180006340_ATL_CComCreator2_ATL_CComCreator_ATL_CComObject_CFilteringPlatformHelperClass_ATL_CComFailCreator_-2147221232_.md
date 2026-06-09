# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CFilteringPlatformHelperClass>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006340`
- end: `0x180006362`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCFilteringPlatformHelperClass@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006340`
- `0x180006368`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CFilteringPlatformHelperClass>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<CFilteringPlatformHelperClass>>::CreateInstance(0, a2, a3);
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x180006340  test    rcx, rcx
0x180006343  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCFilteringPlatformHelperClass@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CFilteringPlatformHelperClass>>::CreateInstance(void *,_GUID const &,void * *)
0x180006349  test    r8, r8
0x18000634c  jnz     short loc_180006355
0x18000634e  mov     eax, 80004003h
0x180006353  jmp     short locret_180006361
0x180006355  mov     qword ptr [r8], 0
0x18000635c  mov     eax, 80040110h
0x180006361  retn
```
