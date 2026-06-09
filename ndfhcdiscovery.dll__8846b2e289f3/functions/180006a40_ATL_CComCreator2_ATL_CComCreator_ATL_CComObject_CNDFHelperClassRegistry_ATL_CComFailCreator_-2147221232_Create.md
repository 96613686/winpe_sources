# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CNDFHelperClassRegistry>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006a40`
- end: `0x180006a62`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCNDFHelperClassRegistry@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006a40`
- `0x180006c9c`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CNDFHelperClassRegistry>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<CNDFHelperClassRegistry>>::CreateInstance(0, a2, a3);
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x180006a40  test    rcx, rcx
0x180006a43  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCNDFHelperClassRegistry@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CNDFHelperClassRegistry>>::CreateInstance(void *,_GUID const &,void * *)
0x180006a49  test    r8, r8
0x180006a4c  jnz     short loc_180006A55
0x180006a4e  mov     eax, 80004003h
0x180006a53  jmp     short locret_180006A61
0x180006a55  mov     qword ptr [r8], 0
0x180006a5c  mov     eax, 80040110h
0x180006a61  retn
```
