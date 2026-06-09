# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CIisRestart>>,ATL::CComCreator<ATL::CComAggObject<CIisRestart>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x140001a90`
- end: `0x140001a9e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCIisRestart@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCIisRestart@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001aa4`
- `0x140001b98`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CIisRestart>>,ATL::CComCreator<ATL::CComAggObject<CIisRestart>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CIisRestart>>::CreateInstance(a1, a2, a3);
  else
    return ATL::CComCreator<ATL::CComObject<CIisRestart>>::CreateInstance(0, a2, a3);
}

```

## disassembly

```asm
0x140001a90  test    rcx, rcx
0x140001a93  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCIisRestart@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CIisRestart>>::CreateInstance(void *,_GUID const &,void * *)
0x140001a99  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCIisRestart@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CIisRestart>>::CreateInstance(void *,_GUID const &,void * *)
```
