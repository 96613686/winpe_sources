# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CGameStatisticsMgr>>,ATL::CComCreator<ATL::CComAggObject<CGameStatisticsMgr>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180002850`
- end: `0x18000285e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCGameStatisticsMgr@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCGameStatisticsMgr@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002864`
- `0x180002914`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CGameStatisticsMgr>>,ATL::CComCreator<ATL::CComAggObject<CGameStatisticsMgr>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CGameStatisticsMgr>>::CreateInstance(a1, a2, a3);
  else
    return ATL::CComCreator<ATL::CComObject<CGameStatisticsMgr>>::CreateInstance(0, a2, a3);
}

```

## disassembly

```asm
0x180002850  test    rcx, rcx
0x180002853  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCGameStatisticsMgr@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CGameStatisticsMgr>>::CreateInstance(void *,_GUID const &,void * *)
0x180002859  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCGameStatisticsMgr@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CGameStatisticsMgr>>::CreateInstance(void *,_GUID const &,void * *)
```
