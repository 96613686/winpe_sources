# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CExtractIcon>>,ATL::CComCreator<ATL::CComAggObject<CExtractIcon>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003a20`
- end: `0x180003a2e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCExtractIcon@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCExtractIcon@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003b30`
- `0x180003c40`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CExtractIcon>>,ATL::CComCreator<ATL::CComAggObject<CExtractIcon>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CExtractIcon>>::CreateInstance(a1, a2, a3);
  else
    return ATL::CComCreator<ATL::CComObject<CExtractIcon>>::CreateInstance(0, a2, a3);
}

```

## disassembly

```asm
0x180003a20  test    rcx, rcx
0x180003a23  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCExtractIcon@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CExtractIcon>>::CreateInstance(void *,_GUID const &,void * *)
0x180003a29  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCExtractIcon@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CExtractIcon>>::CreateInstance(void *,_GUID const &,void * *)
```
