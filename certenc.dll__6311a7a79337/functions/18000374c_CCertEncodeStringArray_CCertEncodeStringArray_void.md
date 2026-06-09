# CCertEncodeStringArray::~CCertEncodeStringArray(void)

- ea: `0x18000374c`
- end: `0x18000378a`
- name: `??1CCertEncodeStringArray@@QEAA@XZ`
- size: `62`
- prototype: `void __fastcall(CCertEncodeStringArray *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180006ed0`
- `0x1800075f0`

## callees

- `0x18000405c`
- `0x1800049c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003773`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003773`

## pseudocode

```c
void __fastcall CCertEncodeStringArray::~CCertEncodeStringArray(CCertEncodeStringArray *this)
{
  *(_QWORD *)this = &CCertEncodeStringArray::`vftable'{for `ATL::IDispatchImpl<ICertEncodeStringArray2,&_GUID const IID_ICertEncodeStringArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)this + 1) = &CCertEncodeStringArray::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeStringArray2>'};
  CCertEncodeStringArray::_Cleanup(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  ATL::CComTypeInfoHolder::Release((ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<ICertEncodeStringArray2,&_GUID const IID_ICertEncodeStringArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::_tih);
}

```

## disassembly

```asm
0x18000374c  push    rbx
0x18000374e  sub     rsp, 20h
0x180003752  lea     rax, ??_7CCertEncodeStringArray@@6B?$IDispatchImpl@UICertEncodeStringArray2@@$1?IID_ICertEncodeStringArray2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const CCertEncodeStringArray::`vftable'{for `ATL::IDispatchImpl<ICertEncodeStringArray2,&_GUID const IID_ICertEncodeStringArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'}
0x180003759  mov     rbx, rcx
0x18000375c  mov     [rcx], rax
0x18000375f  lea     rax, ??_7CCertEncodeStringArray@@6B?$ISupportErrorInfoImpl@$1?IID_ICertEncodeStringArray2@@3U_GUID@@B@ATL@@@; const CCertEncodeStringArray::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeStringArray2>'}
0x180003766  mov     [rcx+8], rax
0x18000376a  call    ?_Cleanup@CCertEncodeStringArray@@AEAAXXZ; CCertEncodeStringArray::_Cleanup(void)
0x18000376f  lea     rcx, [rbx+18h]; lpCriticalSection
0x180003773  call    cs:__imp_DeleteCriticalSection
0x180003779  lea     rcx, ?_tih@?$IDispatchImpl@UICertEncodeStringArray2@@$1?IID_ICertEncodeStringArray2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180003780  add     rsp, 20h
0x180003784  pop     rbx
0x180003785  jmp     ?Release@CComTypeInfoHolder@ATL@@QEAAXXZ; ATL::CComTypeInfoHolder::Release(void)
```
