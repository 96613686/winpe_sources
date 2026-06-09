# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<AuditChannel>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000f510`
- end: `0x18000f532`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VAuditChannel@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000f510`
- `0x18000f828`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<AuditChannel>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<AuditChannel>>::CreateInstance();
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x18000f510  test    rcx, rcx
0x18000f513  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VAuditChannel@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<AuditChannel>>::CreateInstance(void *,_GUID const &,void * *)
0x18000f519  test    r8, r8
0x18000f51c  jnz     short loc_18000F525
0x18000f51e  mov     eax, 80004003h
0x18000f523  jmp     short locret_18000F531
0x18000f525  mov     qword ptr [r8], 0
0x18000f52c  mov     eax, 80040110h
0x18000f531  retn
```
