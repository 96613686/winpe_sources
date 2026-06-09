# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CEnhancedStorageActEnumerator>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180009af0`
- end: `0x180009b12`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCEnhancedStorageActEnumerator@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009af0`
- `0x180009c6c`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CEnhancedStorageActEnumerator>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<CEnhancedStorageActEnumerator>>::CreateInstance(0, a2, a3);
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x180009af0  test    rcx, rcx
0x180009af3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCEnhancedStorageActEnumerator@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CEnhancedStorageActEnumerator>>::CreateInstance(void *,_GUID const &,void * *)
0x180009af9  test    r8, r8
0x180009afc  jnz     short loc_180009B05
0x180009afe  mov     eax, 80004003h
0x180009b03  jmp     short locret_180009B11
0x180009b05  mov     qword ptr [r8], 0
0x180009b0c  mov     eax, 80040110h
0x180009b11  retn
```
