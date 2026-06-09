# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CPPTPDiagHelper>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180009b40`
- end: `0x180009b62`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCPPTPDiagHelper@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009b40`
- `0x180009b6c`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CPPTPDiagHelper>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<CPPTPDiagHelper>>::CreateInstance();
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x180009b40  test    rcx, rcx
0x180009b43  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCPPTPDiagHelper@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CPPTPDiagHelper>>::CreateInstance(void *,_GUID const &,void * *)
0x180009b49  test    r8, r8
0x180009b4c  jnz     short loc_180009B55
0x180009b4e  mov     eax, 80004003h
0x180009b53  jmp     short locret_180009B61
0x180009b55  mov     qword ptr [r8], 0
0x180009b5c  mov     eax, 80040110h
0x180009b61  retn
```
