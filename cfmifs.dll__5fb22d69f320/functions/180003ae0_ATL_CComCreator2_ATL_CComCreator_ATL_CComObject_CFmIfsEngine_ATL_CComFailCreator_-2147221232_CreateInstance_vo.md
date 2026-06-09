# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CFmIfsEngine>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003ae0`
- end: `0x180003b02`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCFmIfsEngine@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003ae0`
- `0x180003b08`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CFmIfsEngine>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<CFmIfsEngine>>::CreateInstance(0, a2, a3);
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x180003ae0  test    rcx, rcx
0x180003ae3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCFmIfsEngine@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CFmIfsEngine>>::CreateInstance(void *,_GUID const &,void * *)
0x180003ae9  test    r8, r8
0x180003aec  jnz     short loc_180003AF5
0x180003aee  mov     eax, 80004003h
0x180003af3  jmp     short locret_180003B01
0x180003af5  mov     qword ptr [r8], 0
0x180003afc  mov     eax, 80040110h
0x180003b01  retn
```
