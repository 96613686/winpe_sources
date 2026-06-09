# CCertEncodeDateArray::~CCertEncodeDateArray(void)

- ea: `0x180001a2c`
- end: `0x180001a6a`
- name: `??1CCertEncodeDateArray@@QEAA@XZ`
- size: `62`
- prototype: `void __fastcall(CCertEncodeDateArray *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180006cd0`
- `0x1800074b0`

## callees

- `0x180002228`
- `0x1800049c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001a53`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001a53`

## pseudocode

```c
void __fastcall CCertEncodeDateArray::~CCertEncodeDateArray(CCertEncodeDateArray *this)
{
  *(_QWORD *)this = &CCertEncodeDateArray::`vftable'{for `ATL::IDispatchImpl<ICertEncodeDateArray2,&_GUID const IID_ICertEncodeDateArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)this + 1) = &CCertEncodeDateArray::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeDateArray2>'};
  CCertEncodeDateArray::_Cleanup(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  ATL::CComTypeInfoHolder::Release((ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<ICertEncodeDateArray2,&_GUID const IID_ICertEncodeDateArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::_tih);
}

```

## disassembly

```asm
0x180001a2c  push    rbx
0x180001a2e  sub     rsp, 20h
0x180001a32  lea     rax, ??_7CCertEncodeDateArray@@6B?$IDispatchImpl@UICertEncodeDateArray2@@$1?IID_ICertEncodeDateArray2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const CCertEncodeDateArray::`vftable'{for `ATL::IDispatchImpl<ICertEncodeDateArray2,&_GUID const IID_ICertEncodeDateArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'}
0x180001a39  mov     rbx, rcx
0x180001a3c  mov     [rcx], rax
0x180001a3f  lea     rax, ??_7CCertEncodeDateArray@@6B?$ISupportErrorInfoImpl@$1?IID_ICertEncodeDateArray2@@3U_GUID@@B@ATL@@@; const CCertEncodeDateArray::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeDateArray2>'}
0x180001a46  mov     [rcx+8], rax
0x180001a4a  call    ?_Cleanup@CCertEncodeDateArray@@AEAAXXZ; CCertEncodeDateArray::_Cleanup(void)
0x180001a4f  lea     rcx, [rbx+18h]; lpCriticalSection
0x180001a53  call    cs:__imp_DeleteCriticalSection
0x180001a59  lea     rcx, ?_tih@?$IDispatchImpl@UICertEncodeDateArray2@@$1?IID_ICertEncodeDateArray2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180001a60  add     rsp, 20h
0x180001a64  pop     rbx
0x180001a65  jmp     ?Release@CComTypeInfoHolder@ATL@@QEAAXXZ; ATL::CComTypeInfoHolder::Release(void)
```
