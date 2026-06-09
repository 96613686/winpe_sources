# ATL::IDispatchImpl<ICertEncodeStringArray2,&_GUID const IID_ICertEncodeStringArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x180003d20`
- end: `0x180003d49`
- name: `?GetTypeInfo@?$IDispatchImpl@UICertEncodeStringArray2@@$1?IID_ICertEncodeStringArray2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003d20`
- `0x1800043a0`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<ICertEncodeStringArray2,&_GUID const IID_ICertEncodeStringArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
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
           (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<ICertEncodeStringArray2,&_GUID const IID_ICertEncodeStringArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::_tih,
           a3,
           a4);
}

```

## disassembly

```asm
0x180003d20  mov     eax, r8d
0x180003d23  test    r9, r9
0x180003d26  jnz     short loc_180003D2E
0x180003d28  mov     eax, 80004003h
0x180003d2d  retn
0x180003d2e  test    edx, edx
0x180003d30  jz      short loc_180003D38
0x180003d32  mov     eax, 8002000Bh
0x180003d37  retn
0x180003d38  mov     r8, r9; struct ITypeInfo **
0x180003d3b  lea     rcx, ?_tih@?$IDispatchImpl@UICertEncodeStringArray2@@$1?IID_ICertEncodeStringArray2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180003d42  mov     edx, eax; unsigned int
0x180003d44  jmp     ?GetTI@CComTypeInfoHolder@ATL@@QEAAJKPEAPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::GetTI(ulong,ITypeInfo * *)
```
