# CCertEncodeBitString::~CCertEncodeBitString(void)

- ea: `0x180004bc8`
- end: `0x180004c18`
- name: `??1CCertEncodeBitString@@QEAA@XZ`
- size: `80`
- prototype: `void __fastcall(CCertEncodeBitString *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180006ac0`
- `0x180007370`

## callees

- `0x1800049c8`
- `0x180004bc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004c01`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004c01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004bef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004bef`

## pseudocode

```c
void __fastcall CCertEncodeBitString::~CCertEncodeBitString(CCertEncodeBitString *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &CCertEncodeBitString::`vftable'{for `ATL::IDispatchImpl<ICertEncodeBitString2,&_GUID const IID_ICertEncodeBitString2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)this + 1) = &CCertEncodeBitString::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeBitString2>'};
  v2 = (void *)*((_QWORD *)this + 8);
  if ( v2 )
  {
    LocalFree(v2);
    *((_QWORD *)this + 8) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  ATL::CComTypeInfoHolder::Release((ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<ICertEncodeBitString2,&_GUID const IID_ICertEncodeBitString2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::_tih);
}

```

## disassembly

```asm
0x180004bc8  push    rbx
0x180004bca  sub     rsp, 20h
0x180004bce  lea     rax, ??_7CCertEncodeBitString@@6B?$IDispatchImpl@UICertEncodeBitString2@@$1?IID_ICertEncodeBitString2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const CCertEncodeBitString::`vftable'{for `ATL::IDispatchImpl<ICertEncodeBitString2,&_GUID const IID_ICertEncodeBitString2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'}
0x180004bd5  mov     rbx, rcx
0x180004bd8  mov     [rcx], rax
0x180004bdb  lea     rax, ??_7CCertEncodeBitString@@6B?$ISupportErrorInfoImpl@$1?IID_ICertEncodeBitString2@@3U_GUID@@B@ATL@@@; const CCertEncodeBitString::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeBitString2>'}
0x180004be2  mov     [rcx+8], rax
0x180004be6  mov     rcx, [rcx+40h]; hMem
0x180004bea  test    rcx, rcx
0x180004bed  jz      short loc_180004BFD
0x180004bef  call    cs:__imp_LocalFree
0x180004bf5  mov     qword ptr [rbx+40h], 0
0x180004bfd  lea     rcx, [rbx+18h]; lpCriticalSection
0x180004c01  call    cs:__imp_DeleteCriticalSection
0x180004c07  lea     rcx, ?_tih@?$IDispatchImpl@UICertEncodeBitString2@@$1?IID_ICertEncodeBitString2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180004c0e  add     rsp, 20h
0x180004c12  pop     rbx
0x180004c13  jmp     ?Release@CComTypeInfoHolder@ATL@@QEAAXXZ; ATL::CComTypeInfoHolder::Release(void)
```
