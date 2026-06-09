# ATL::CComObject<CCertEncodeAltName>::Release(void)

- ea: `0x1800072d0`
- end: `0x180007356`
- name: `?Release@?$CComObject@VCCertEncodeAltName@@@ATL@@UEAAKXZ`
- size: `134`
- prototype: `__int64 __fastcall(CCertEncodeAltName *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180007360`

## callees

- `0x180001008`
- `0x180002acc`
- `0x1800072d0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCertEncodeAltName>::Release(CCertEncodeAltName *this)
{
  signed __int32 i; // ecx
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)this + 4);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange((volatile signed __int32 *)this + 4, i - 1, i);
        i = *((_DWORD *)this + 4) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    _InterlockedIncrement(&dword_18000F8D8);
    if ( this )
    {
      *((_DWORD *)this + 4) = 1;
      *(_QWORD *)this = &ATL::CComObject<CCertEncodeAltName>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeAltName2,&_GUID const IID_ICertEncodeAltName2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'};
      *((_QWORD *)this + 1) = &ATL::CComObject<CCertEncodeAltName>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeAltName2>'};
      _InterlockedDecrement(&dword_18000F8D8);
      CCertEncodeAltName::~CCertEncodeAltName(this);
      operator delete(this);
    }
    _InterlockedDecrement(&dword_18000F8D8);
  }
  return v3;
}

```

## disassembly

```asm
0x1800072d0  mov     [rsp+arg_0], rbx
0x1800072d5  push    rdi
0x1800072d6  sub     rsp, 20h
0x1800072da  mov     rbx, rcx
0x1800072dd  mov     r8d, 7FFFFFFFh
0x1800072e3  mov     ecx, [rcx+10h]
0x1800072e6  jmp     short loc_1800072F7
0x1800072e8  lea     edx, [rcx-1]
0x1800072eb  mov     eax, ecx
0x1800072ed  lock cmpxchg [rbx+10h], edx
0x1800072f2  jz      short loc_1800072FC
0x1800072f4  mov     ecx, [rbx+10h]
0x1800072f7  cmp     ecx, r8d
0x1800072fa  jnz     short loc_1800072E8
0x1800072fc  lea     edi, [rcx-1]
0x1800072ff  test    edi, edi
0x180007301  jnz     short loc_180007349
0x180007303  lock inc cs:dword_18000F8D8
0x18000730a  test    rbx, rbx
0x18000730d  jz      short loc_180007342
0x18000730f  lea     rax, ??_7?$CComObject@VCCertEncodeAltName@@@ATL@@6B?$IDispatchImpl@UICertEncodeAltName2@@$1?IID_ICertEncodeAltName2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CCertEncodeAltName>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeAltName2,&_GUID const IID_ICertEncodeAltName2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'}
0x180007316  mov     dword ptr [rbx+10h], 1
0x18000731d  mov     [rbx], rax
0x180007320  mov     rcx, rbx; this
0x180007323  lea     rax, ??_7?$CComObject@VCCertEncodeAltName@@@ATL@@6B?$ISupportErrorInfoImpl@$1?IID_ICertEncodeAltName2@@3U_GUID@@B@1@@; const ATL::CComObject<CCertEncodeAltName>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeAltName2>'}
0x18000732a  mov     [rbx+8], rax
0x18000732e  lock dec cs:dword_18000F8D8
0x180007335  call    ??1CCertEncodeAltName@@QEAA@XZ; CCertEncodeAltName::~CCertEncodeAltName(void)
0x18000733a  mov     rcx, rbx; Block
0x18000733d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007342  lock dec cs:dword_18000F8D8
0x180007349  mov     rbx, [rsp+28h+arg_0]
0x18000734e  mov     eax, edi
0x180007350  add     rsp, 20h
0x180007354  pop     rdi
0x180007355  retn
```
