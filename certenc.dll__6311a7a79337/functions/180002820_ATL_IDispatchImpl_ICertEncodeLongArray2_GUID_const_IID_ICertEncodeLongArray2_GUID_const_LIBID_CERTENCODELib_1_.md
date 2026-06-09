# ATL::IDispatchImpl<ICertEncodeLongArray2,&_GUID const IID_ICertEncodeLongArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x180002820`
- end: `0x180002849`
- name: `?GetTypeInfo@?$IDispatchImpl@UICertEncodeLongArray2@@$1?IID_ICertEncodeLongArray2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002820`
- `0x1800043a0`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<ICertEncodeLongArray2,&_GUID const IID_ICertEncodeLongArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
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
           (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<ICertEncodeLongArray2,&_GUID const IID_ICertEncodeLongArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::_tih,
           a3,
           a4);
}

```

## disassembly

```asm
0x180002820  mov     eax, r8d
0x180002823  test    r9, r9
0x180002826  jnz     short loc_18000282E
0x180002828  mov     eax, 80004003h
0x18000282d  retn
0x18000282e  test    edx, edx
0x180002830  jz      short loc_180002838
0x180002832  mov     eax, 8002000Bh
0x180002837  retn
0x180002838  mov     r8, r9; struct ITypeInfo **
0x18000283b  lea     rcx, ?_tih@?$IDispatchImpl@UICertEncodeLongArray2@@$1?IID_ICertEncodeLongArray2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180002842  mov     edx, eax; unsigned int
0x180002844  jmp     ?GetTI@CComTypeInfoHolder@ATL@@QEAAJKPEAPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::GetTI(ulong,ITypeInfo * *)
```
