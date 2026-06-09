# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CEnhancedStorageSiloAction>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180009b50`
- end: `0x180009b72`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCEnhancedStorageSiloAction@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009b50`
- `0x180009e88`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CEnhancedStorageSiloAction>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<CEnhancedStorageSiloAction>>::CreateInstance(0, a2, a3);
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x180009b50  test    rcx, rcx
0x180009b53  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCEnhancedStorageSiloAction@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CEnhancedStorageSiloAction>>::CreateInstance(void *,_GUID const &,void * *)
0x180009b59  test    r8, r8
0x180009b5c  jnz     short loc_180009B65
0x180009b5e  mov     eax, 80004003h
0x180009b63  jmp     short locret_180009B71
0x180009b65  mov     qword ptr [r8], 0
0x180009b6c  mov     eax, 80040110h
0x180009b71  retn
```
