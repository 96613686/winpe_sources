# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CDetectionAndSharing>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180001e20`
- end: `0x180001e42`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCDetectionAndSharing@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001e20`
- `0x180001e48`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CDetectionAndSharing>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<CDetectionAndSharing>>::CreateInstance(0, a2, a3);
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x180001e20  test    rcx, rcx
0x180001e23  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCDetectionAndSharing@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CDetectionAndSharing>>::CreateInstance(void *,_GUID const &,void * *)
0x180001e29  test    r8, r8
0x180001e2c  jnz     short loc_180001E35
0x180001e2e  mov     eax, 80004003h
0x180001e33  jmp     short locret_180001E41
0x180001e35  mov     qword ptr [r8], 0
0x180001e3c  mov     eax, 80040110h
0x180001e41  retn
```
