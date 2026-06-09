# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CRasDiagHelper>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800063b0`
- end: `0x1800063d2`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCRasDiagHelper@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800063b0`
- `0x1800063dc`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CRasDiagHelper>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<CRasDiagHelper>>::CreateInstance();
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x1800063b0  test    rcx, rcx
0x1800063b3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCRasDiagHelper@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CRasDiagHelper>>::CreateInstance(void *,_GUID const &,void * *)
0x1800063b9  test    r8, r8
0x1800063bc  jnz     short loc_1800063C5
0x1800063be  mov     eax, 80004003h
0x1800063c3  jmp     short locret_1800063D1
0x1800063c5  mov     qword ptr [r8], 0
0x1800063cc  mov     eax, 80040110h
0x1800063d1  retn
```
