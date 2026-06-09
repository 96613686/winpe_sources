# CCertEncodeCRLDistInfo::~CCertEncodeCRLDistInfo(void)

- ea: `0x180007a20`
- end: `0x180007a5e`
- name: `??1CCertEncodeCRLDistInfo@@QEAA@XZ`
- size: `62`
- prototype: `void __fastcall(CCertEncodeCRLDistInfo *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180006bc0`
- `0x180007410`

## callees

- `0x1800049c8`
- `0x180008360`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007a47`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007a47`

## pseudocode

```c
void __fastcall CCertEncodeCRLDistInfo::~CCertEncodeCRLDistInfo(CCertEncodeCRLDistInfo *this)
{
  *(_QWORD *)this = &CCertEncodeCRLDistInfo::`vftable'{for `ATL::IDispatchImpl<ICertEncodeCRLDistInfo2,&_GUID const IID_ICertEncodeCRLDistInfo2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)this + 1) = &CCertEncodeCRLDistInfo::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeCRLDistInfo2>'};
  CCertEncodeCRLDistInfo::_Cleanup(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  ATL::CComTypeInfoHolder::Release((ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<ICertEncodeCRLDistInfo2,&_GUID const IID_ICertEncodeCRLDistInfo2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::_tih);
}

```

## disassembly

```asm
0x180007a20  push    rbx
0x180007a22  sub     rsp, 20h
0x180007a26  lea     rax, ??_7CCertEncodeCRLDistInfo@@6B?$IDispatchImpl@UICertEncodeCRLDistInfo2@@$1?IID_ICertEncodeCRLDistInfo2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const CCertEncodeCRLDistInfo::`vftable'{for `ATL::IDispatchImpl<ICertEncodeCRLDistInfo2,&_GUID const IID_ICertEncodeCRLDistInfo2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'}
0x180007a2d  mov     rbx, rcx
0x180007a30  mov     [rcx], rax
0x180007a33  lea     rax, ??_7CCertEncodeCRLDistInfo@@6B?$ISupportErrorInfoImpl@$1?IID_ICertEncodeCRLDistInfo2@@3U_GUID@@B@ATL@@@; const CCertEncodeCRLDistInfo::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeCRLDistInfo2>'}
0x180007a3a  mov     [rcx+8], rax
0x180007a3e  call    ?_Cleanup@CCertEncodeCRLDistInfo@@AEAAXXZ; CCertEncodeCRLDistInfo::_Cleanup(void)
0x180007a43  lea     rcx, [rbx+18h]; lpCriticalSection
0x180007a47  call    cs:__imp_DeleteCriticalSection
0x180007a4d  lea     rcx, ?_tih@?$IDispatchImpl@UICertEncodeCRLDistInfo2@@$1?IID_ICertEncodeCRLDistInfo2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180007a54  add     rsp, 20h
0x180007a58  pop     rbx
0x180007a59  jmp     ?Release@CComTypeInfoHolder@ATL@@QEAAXXZ; ATL::CComTypeInfoHolder::Release(void)
```
