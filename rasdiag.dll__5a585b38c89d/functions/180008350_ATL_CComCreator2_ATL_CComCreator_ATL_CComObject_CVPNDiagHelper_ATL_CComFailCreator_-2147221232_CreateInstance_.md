# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CVPNDiagHelper>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180008350`
- end: `0x180008372`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCVPNDiagHelper@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008350`
- `0x18000837c`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CVPNDiagHelper>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<CVPNDiagHelper>>::CreateInstance();
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x180008350  test    rcx, rcx
0x180008353  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCVPNDiagHelper@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CVPNDiagHelper>>::CreateInstance(void *,_GUID const &,void * *)
0x180008359  test    r8, r8
0x18000835c  jnz     short loc_180008365
0x18000835e  mov     eax, 80004003h
0x180008363  jmp     short locret_180008371
0x180008365  mov     qword ptr [r8], 0
0x18000836c  mov     eax, 80040110h
0x180008371  retn
```
