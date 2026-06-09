# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<IASTL::IASComponentObject<InfoBase>>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000f4b0`
- end: `0x18000f4d2`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@V?$IASComponentObject@VInfoBase@@@IASTL@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000f4b0`
- `0x18000f538`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<IASTL::IASComponentObject<InfoBase>>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<IASTL::IASComponentObject<InfoBase>>>::CreateInstance(0, a2, a3);
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x18000f4b0  test    rcx, rcx
0x18000f4b3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@V?$IASComponentObject@VInfoBase@@@IASTL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<IASTL::IASComponentObject<InfoBase>>>::CreateInstance(void *,_GUID const &,void * *)
0x18000f4b9  test    r8, r8
0x18000f4bc  jnz     short loc_18000F4C5
0x18000f4be  mov     eax, 80004003h
0x18000f4c3  jmp     short locret_18000F4D1
0x18000f4c5  mov     qword ptr [r8], 0
0x18000f4cc  mov     eax, 80040110h
0x18000f4d1  retn
```
