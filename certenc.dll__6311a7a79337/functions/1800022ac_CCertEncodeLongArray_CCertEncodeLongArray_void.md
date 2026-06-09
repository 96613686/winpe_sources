# CCertEncodeLongArray::~CCertEncodeLongArray(void)

- ea: `0x1800022ac`
- end: `0x1800022ea`
- name: `??1CCertEncodeLongArray@@QEAA@XZ`
- size: `62`
- prototype: `void __fastcall(CCertEncodeLongArray *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180006dd0`
- `0x180007550`

## callees

- `0x180002228`
- `0x1800049c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800022d3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800022d3`

## pseudocode

```c
void __fastcall CCertEncodeLongArray::~CCertEncodeLongArray(CCertEncodeLongArray *this)
{
  *(_QWORD *)this = &CCertEncodeLongArray::`vftable'{for `ATL::IDispatchImpl<ICertEncodeLongArray2,&_GUID const IID_ICertEncodeLongArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)this + 1) = &CCertEncodeLongArray::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeLongArray2>'};
  CCertEncodeDateArray::_Cleanup(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  ATL::CComTypeInfoHolder::Release((ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<ICertEncodeLongArray2,&_GUID const IID_ICertEncodeLongArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::_tih);
}

```

## disassembly

```asm
0x1800022ac  push    rbx
0x1800022ae  sub     rsp, 20h
0x1800022b2  lea     rax, ??_7CCertEncodeLongArray@@6B?$IDispatchImpl@UICertEncodeLongArray2@@$1?IID_ICertEncodeLongArray2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const CCertEncodeLongArray::`vftable'{for `ATL::IDispatchImpl<ICertEncodeLongArray2,&_GUID const IID_ICertEncodeLongArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'}
0x1800022b9  mov     rbx, rcx
0x1800022bc  mov     [rcx], rax
0x1800022bf  lea     rax, ??_7CCertEncodeLongArray@@6B?$ISupportErrorInfoImpl@$1?IID_ICertEncodeLongArray2@@3U_GUID@@B@ATL@@@; const CCertEncodeLongArray::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeLongArray2>'}
0x1800022c6  mov     [rcx+8], rax
0x1800022ca  call    ?_Cleanup@CCertEncodeDateArray@@AEAAXXZ; CCertEncodeDateArray::_Cleanup(void)
0x1800022cf  lea     rcx, [rbx+18h]; lpCriticalSection
0x1800022d3  call    cs:__imp_DeleteCriticalSection
0x1800022d9  lea     rcx, ?_tih@?$IDispatchImpl@UICertEncodeLongArray2@@$1?IID_ICertEncodeLongArray2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x1800022e0  add     rsp, 20h
0x1800022e4  pop     rbx
0x1800022e5  jmp     ?Release@CComTypeInfoHolder@ATL@@QEAAXXZ; ATL::CComTypeInfoHolder::Release(void)
```
