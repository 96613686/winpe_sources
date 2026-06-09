# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CGameExplorer>>,ATL::CComCreator<ATL::CComAggObject<CGameExplorer>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180001f30`
- end: `0x180001f3e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCGameExplorer@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCGameExplorer@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001f44`
- `0x18000203c`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CGameExplorer>>,ATL::CComCreator<ATL::CComAggObject<CGameExplorer>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CGameExplorer>>::CreateInstance(a1, a2, a3);
  else
    return ATL::CComCreator<ATL::CComObject<CGameExplorer>>::CreateInstance(0, a2, a3);
}

```

## disassembly

```asm
0x180001f30  test    rcx, rcx
0x180001f33  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCGameExplorer@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CGameExplorer>>::CreateInstance(void *,_GUID const &,void * *)
0x180001f39  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCGameExplorer@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CGameExplorer>>::CreateInstance(void *,_GUID const &,void * *)
```
