# ATL::IDispatchImpl<ICertEncodeBitString2,&_GUID const IID_ICertEncodeBitString2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x1800052a0`
- end: `0x1800052c9`
- name: `?GetTypeInfo@?$IDispatchImpl@UICertEncodeBitString2@@$1?IID_ICertEncodeBitString2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800043a0`
- `0x1800052a0`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<ICertEncodeBitString2,&_GUID const IID_ICertEncodeBitString2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
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
           (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<ICertEncodeBitString2,&_GUID const IID_ICertEncodeBitString2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::_tih,
           a3,
           a4);
}

```

## disassembly

```asm
0x1800052a0  mov     eax, r8d
0x1800052a3  test    r9, r9
0x1800052a6  jnz     short loc_1800052AE
0x1800052a8  mov     eax, 80004003h
0x1800052ad  retn
0x1800052ae  test    edx, edx
0x1800052b0  jz      short loc_1800052B8
0x1800052b2  mov     eax, 8002000Bh
0x1800052b7  retn
0x1800052b8  mov     r8, r9; struct ITypeInfo **
0x1800052bb  lea     rcx, ?_tih@?$IDispatchImpl@UICertEncodeBitString2@@$1?IID_ICertEncodeBitString2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x1800052c2  mov     edx, eax; unsigned int
0x1800052c4  jmp     ?GetTI@CComTypeInfoHolder@ATL@@QEAAJKPEAPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::GetTI(ulong,ITypeInfo * *)
```
