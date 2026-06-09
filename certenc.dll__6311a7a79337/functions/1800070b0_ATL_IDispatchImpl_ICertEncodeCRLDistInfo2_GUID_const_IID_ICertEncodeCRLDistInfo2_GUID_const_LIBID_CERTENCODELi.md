# ATL::IDispatchImpl<ICertEncodeCRLDistInfo2,&_GUID const IID_ICertEncodeCRLDistInfo2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x1800070b0`
- end: `0x1800070d9`
- name: `?GetTypeInfo@?$IDispatchImpl@UICertEncodeCRLDistInfo2@@$1?IID_ICertEncodeCRLDistInfo2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800043a0`
- `0x1800070b0`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<ICertEncodeCRLDistInfo2,&_GUID const IID_ICertEncodeCRLDistInfo2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
        __int64 a1,
        int a2,
        LCID a3,
        struct ITypeInfo **a4)
{
  if ( !a4 )
    return 2147500035LL;
  if ( a2 )
    return 2147614731LL;
  return ATL::CComTypeInfoHolder::GetTI(
           (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<ICertEncodeCRLDistInfo2,&_GUID const IID_ICertEncodeCRLDistInfo2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::_tih,
           a3,
           a4);
}

```

## disassembly

```asm
0x1800070b0  mov     eax, r8d
0x1800070b3  test    r9, r9
0x1800070b6  jnz     short loc_1800070BE
0x1800070b8  mov     eax, 80004003h
0x1800070bd  retn
0x1800070be  test    edx, edx
0x1800070c0  jz      short loc_1800070C8
0x1800070c2  mov     eax, 8002000Bh
0x1800070c7  retn
0x1800070c8  mov     r8, r9; struct ITypeInfo **
0x1800070cb  lea     rcx, ?_tih@?$IDispatchImpl@UICertEncodeCRLDistInfo2@@$1?IID_ICertEncodeCRLDistInfo2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x1800070d2  mov     edx, eax; unsigned int
0x1800070d4  jmp     ?GetTI@CComTypeInfoHolder@ATL@@QEAAJKPEAPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::GetTI(ulong,ITypeInfo * *)
```
