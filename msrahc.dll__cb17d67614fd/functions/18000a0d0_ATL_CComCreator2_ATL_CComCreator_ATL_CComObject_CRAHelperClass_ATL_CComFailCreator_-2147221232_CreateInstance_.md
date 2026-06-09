# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CRAHelperClass>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000a0d0`
- end: `0x18000a0f2`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCRAHelperClass@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000a0d0`
- `0x18000a0f8`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CRAHelperClass>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<CRAHelperClass>>::CreateInstance();
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x18000a0d0  test    rcx, rcx
0x18000a0d3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCRAHelperClass@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CRAHelperClass>>::CreateInstance(void *,_GUID const &,void * *)
0x18000a0d9  test    r8, r8
0x18000a0dc  jnz     short loc_18000A0E5
0x18000a0de  mov     eax, 80004003h
0x18000a0e3  jmp     short locret_18000A0F1
0x18000a0e5  mov     qword ptr [r8], 0
0x18000a0ec  mov     eax, 80040110h
0x18000a0f1  retn
```
