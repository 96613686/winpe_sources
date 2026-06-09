# CCertEncodeAltName::~CCertEncodeAltName(void)

- ea: `0x180002acc`
- end: `0x180002b0a`
- name: `??1CCertEncodeAltName@@QEAA@XZ`
- size: `62`
- prototype: `void __fastcall(CCertEncodeAltName *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800069b0`
- `0x1800072d0`

## callees

- `0x1800035e0`
- `0x1800049c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002af3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002af3`

## pseudocode

```c
void __fastcall CCertEncodeAltName::~CCertEncodeAltName(CCertEncodeAltName *this)
{
  *(_QWORD *)this = &CCertEncodeAltName::`vftable'{for `ATL::IDispatchImpl<ICertEncodeAltName2,&_GUID const IID_ICertEncodeAltName2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)this + 1) = &CCertEncodeAltName::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeAltName2>'};
  CCertEncodeAltName::_Cleanup(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  ATL::CComTypeInfoHolder::Release((ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<ICertEncodeAltName2,&_GUID const IID_ICertEncodeAltName2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::_tih);
}

```

## disassembly

```asm
0x180002acc  push    rbx
0x180002ace  sub     rsp, 20h
0x180002ad2  lea     rax, ??_7CCertEncodeAltName@@6B?$IDispatchImpl@UICertEncodeAltName2@@$1?IID_ICertEncodeAltName2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const CCertEncodeAltName::`vftable'{for `ATL::IDispatchImpl<ICertEncodeAltName2,&_GUID const IID_ICertEncodeAltName2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'}
0x180002ad9  mov     rbx, rcx
0x180002adc  mov     [rcx], rax
0x180002adf  lea     rax, ??_7CCertEncodeAltName@@6B?$ISupportErrorInfoImpl@$1?IID_ICertEncodeAltName2@@3U_GUID@@B@ATL@@@; const CCertEncodeAltName::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeAltName2>'}
0x180002ae6  mov     [rcx+8], rax
0x180002aea  call    ?_Cleanup@CCertEncodeAltName@@AEAAXXZ; CCertEncodeAltName::_Cleanup(void)
0x180002aef  lea     rcx, [rbx+18h]; lpCriticalSection
0x180002af3  call    cs:__imp_DeleteCriticalSection
0x180002af9  lea     rcx, ?_tih@?$IDispatchImpl@UICertEncodeAltName2@@$1?IID_ICertEncodeAltName2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180002b00  add     rsp, 20h
0x180002b04  pop     rbx
0x180002b05  jmp     ?Release@CComTypeInfoHolder@ATL@@QEAAXXZ; ATL::CComTypeInfoHolder::Release(void)
```
