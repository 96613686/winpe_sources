# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMSDiscRecorderObj>>,ATL::CComCreator<ATL::CComAggObject<CMSDiscRecorderObj>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006210`
- end: `0x18000621e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCMSDiscRecorderObj@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCMSDiscRecorderObj@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006224`
- `0x180006320`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMSDiscRecorderObj>>,ATL::CComCreator<ATL::CComAggObject<CMSDiscRecorderObj>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CMSDiscRecorderObj>>::CreateInstance(a1, a2, a3);
  else
    return ATL::CComCreator<ATL::CComObject<CMSDiscRecorderObj>>::CreateInstance(0, a2, a3);
}

```

## disassembly

```asm
0x180006210  test    rcx, rcx
0x180006213  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCMSDiscRecorderObj@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CMSDiscRecorderObj>>::CreateInstance(void *,_GUID const &,void * *)
0x180006219  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCMSDiscRecorderObj@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CMSDiscRecorderObj>>::CreateInstance(void *,_GUID const &,void * *)
```
