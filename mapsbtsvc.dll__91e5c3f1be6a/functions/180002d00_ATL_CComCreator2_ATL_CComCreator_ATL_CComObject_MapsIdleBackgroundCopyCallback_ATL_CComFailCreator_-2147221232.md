# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<MapsIdleBackgroundCopyCallback>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180002d00`
- end: `0x180002d22`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VMapsIdleBackgroundCopyCallback@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002d00`
- `0x180002d28`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<MapsIdleBackgroundCopyCallback>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<MapsIdleBackgroundCopyCallback>>::CreateInstance();
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x180002d00  test    rcx, rcx
0x180002d03  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VMapsIdleBackgroundCopyCallback@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<MapsIdleBackgroundCopyCallback>>::CreateInstance(void *,_GUID const &,void * *)
0x180002d09  test    r8, r8
0x180002d0c  jnz     short loc_180002D15
0x180002d0e  mov     eax, 80004003h
0x180002d13  jmp     short locret_180002D21
0x180002d15  mov     qword ptr [r8], 0
0x180002d1c  mov     eax, 80040110h
0x180002d21  retn
```
