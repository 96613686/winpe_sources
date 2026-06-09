# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<DataStoreComServer>>,ATL::CComCreator<ATL::CComAggObject<DataStoreComServer>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003bd0`
- end: `0x180003bde`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VDataStoreComServer@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VDataStoreComServer@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003be4`
- `0x180003d18`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<DataStoreComServer>>,ATL::CComCreator<ATL::CComAggObject<DataStoreComServer>>>::CreateInstance(
        ULONG_PTR a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<DataStoreComServer>>::CreateInstance(a1, a2, a3);
  else
    return ATL::CComCreator<ATL::CComObject<DataStoreComServer>>::CreateInstance(0, a2, a3);
}

```

## disassembly

```asm
0x180003bd0  test    rcx, rcx
0x180003bd3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VDataStoreComServer@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<DataStoreComServer>>::CreateInstance(void *,_GUID const &,void * *)
0x180003bd9  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VDataStoreComServer@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<DataStoreComServer>>::CreateInstance(void *,_GUID const &,void * *)
```
