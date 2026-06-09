# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CWFPClientsHelperClass>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180009b00`
- end: `0x180009b22`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCWFPClientsHelperClass@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009b00`
- `0x180009b28`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CWFPClientsHelperClass>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<CWFPClientsHelperClass>>::CreateInstance(0, a2, a3);
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x180009b00  test    rcx, rcx
0x180009b03  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCWFPClientsHelperClass@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CWFPClientsHelperClass>>::CreateInstance(void *,_GUID const &,void * *)
0x180009b09  test    r8, r8
0x180009b0c  jnz     short loc_180009B15
0x180009b0e  mov     eax, 80004003h
0x180009b13  jmp     short locret_180009B21
0x180009b15  mov     qword ptr [r8], 0
0x180009b1c  mov     eax, 80040110h
0x180009b21  retn
```
