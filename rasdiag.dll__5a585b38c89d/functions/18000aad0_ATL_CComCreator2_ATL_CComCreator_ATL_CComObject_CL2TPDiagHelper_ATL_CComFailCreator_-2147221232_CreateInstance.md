# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CL2TPDiagHelper>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000aad0`
- end: `0x18000aaf2`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCL2TPDiagHelper@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000aad0`
- `0x18000aafc`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CL2TPDiagHelper>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<CL2TPDiagHelper>>::CreateInstance();
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x18000aad0  test    rcx, rcx
0x18000aad3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCL2TPDiagHelper@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CL2TPDiagHelper>>::CreateInstance(void *,_GUID const &,void * *)
0x18000aad9  test    r8, r8
0x18000aadc  jnz     short loc_18000AAE5
0x18000aade  mov     eax, 80004003h
0x18000aae3  jmp     short locret_18000AAF1
0x18000aae5  mov     qword ptr [r8], 0
0x18000aaec  mov     eax, 80040110h
0x18000aaf1  retn
```
