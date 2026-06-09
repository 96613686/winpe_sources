# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMSDiscMasterObj>>,ATL::CComCreator<ATL::CComAggObject<CMSDiscMasterObj>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180008770`
- end: `0x18000877e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCMSDiscMasterObj@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCMSDiscMasterObj@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008784`
- `0x1800088b8`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMSDiscMasterObj>>,ATL::CComCreator<ATL::CComAggObject<CMSDiscMasterObj>>>::CreateInstance(
        ULONG_PTR a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CMSDiscMasterObj>>::CreateInstance(a1, a2, a3);
  else
    return ATL::CComCreator<ATL::CComObject<CMSDiscMasterObj>>::CreateInstance(0, a2, a3);
}

```

## disassembly

```asm
0x180008770  test    rcx, rcx
0x180008773  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCMSDiscMasterObj@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CMSDiscMasterObj>>::CreateInstance(void *,_GUID const &,void * *)
0x180008779  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCMSDiscMasterObj@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CMSDiscMasterObj>>::CreateInstance(void *,_GUID const &,void * *)
```
