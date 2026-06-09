# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CAccClientDocMgr>>,ATL::CComCreator<ATL::CComAggObject<CAccClientDocMgr>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000f2d0`
- end: `0x18000f2de`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCAccClientDocMgr@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCAccClientDocMgr@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000f698`
- `0x18000f8fc`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CAccClientDocMgr>>,ATL::CComCreator<ATL::CComAggObject<CAccClientDocMgr>>>::CreateInstance(
        void *a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CAccClientDocMgr>>::CreateInstance(a1, a2, a3);
  else
    return ATL::CComCreator<ATL::CComObject<CAccClientDocMgr>>::CreateInstance(0, a2, a3);
}

```

## disassembly

```asm
0x18000f2d0  test    rcx, rcx
0x18000f2d3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCAccClientDocMgr@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CAccClientDocMgr>>::CreateInstance(void *,_GUID const &,void * *)
0x18000f2d9  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCAccClientDocMgr@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CAccClientDocMgr>>::CreateInstance(void *,_GUID const &,void * *)
```
