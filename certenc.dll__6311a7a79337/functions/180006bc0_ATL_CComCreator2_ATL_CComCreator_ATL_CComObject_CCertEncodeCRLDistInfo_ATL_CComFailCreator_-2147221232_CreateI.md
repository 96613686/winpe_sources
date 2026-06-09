# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CCertEncodeCRLDistInfo>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006bc0`
- end: `0x180006cc2`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCCertEncodeCRLDistInfo@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `258`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180001008`
- `0x180001014`
- `0x18000413c`
- `0x180006bc0`
- `0x180007a20`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006c24`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006c24`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CCertEncodeCRLDistInfo>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // ebx
  char *v6; // rdi

  if ( a1 )
  {
    if ( a3 )
    {
      *a3 = 0;
      return (unsigned int)-2147221232;
    }
    return (unsigned int)-2147467261;
  }
  if ( !a3 )
    return (unsigned int)-2147467261;
  *a3 = 0;
  v5 = -2147024882;
  v6 = (char *)operator new(0x60u);
  if ( v6 )
  {
    ATL::CComTypeInfoHolder::AddRef((ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<ICertEncodeCRLDistInfo2,&_GUID const IID_ICertEncodeCRLDistInfo2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::_tih);
    *((_DWORD *)v6 + 4) = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v6 + 24));
    *((_QWORD *)v6 + 8) = 0;
    *(_QWORD *)v6 = &ATL::CComObject<CCertEncodeCRLDistInfo>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeCRLDistInfo2,&_GUID const IID_ICertEncodeCRLDistInfo2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v6 + 1) = &ATL::CComObject<CCertEncodeCRLDistInfo>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeCRLDistInfo2>'};
    *((_QWORD *)v6 + 10) = 0;
    *((_DWORD *)v6 + 22) = 0;
    _InterlockedIncrement(&dword_18000F8D8);
    v5 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v6)(v6, a2, a3);
    if ( v5 )
    {
      *(_QWORD *)v6 = &ATL::CComObject<CCertEncodeCRLDistInfo>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeCRLDistInfo2,&_GUID const IID_ICertEncodeCRLDistInfo2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'};
      *((_QWORD *)v6 + 1) = &ATL::CComObject<CCertEncodeCRLDistInfo>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeCRLDistInfo2>'};
      *((_DWORD *)v6 + 4) = 1;
      _InterlockedDecrement(&dword_18000F8D8);
      CCertEncodeCRLDistInfo::~CCertEncodeCRLDistInfo((CCertEncodeCRLDistInfo *)v6);
      operator delete(v6);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180006bc0  push    rbx
0x180006bc2  push    rbp
0x180006bc3  push    rsi
0x180006bc4  push    rdi
0x180006bc5  push    r12
0x180006bc7  push    r15
0x180006bc9  sub     rsp, 28h
0x180006bcd  mov     rsi, r8
0x180006bd0  mov     rbp, rdx
0x180006bd3  test    rcx, rcx
0x180006bd6  jnz     loc_180006C9E
0x180006bdc  test    r8, r8
0x180006bdf  jnz     short loc_180006BEB
0x180006be1  mov     ebx, 80004003h
0x180006be6  jmp     loc_180006CB3
0x180006beb  mov     ecx, 60h ; '`'; Size
0x180006bf0  mov     qword ptr [r8], 0
0x180006bf7  mov     ebx, 8007000Eh
0x180006bfc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006c01  mov     rdi, rax
0x180006c04  test    rax, rax
0x180006c07  jz      loc_180006CB3
0x180006c0d  lea     rcx, ?_tih@?$IDispatchImpl@UICertEncodeCRLDistInfo2@@$1?IID_ICertEncodeCRLDistInfo2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180006c14  call    ?AddRef@CComTypeInfoHolder@ATL@@QEAAXXZ; ATL::CComTypeInfoHolder::AddRef(void)
0x180006c19  lea     rcx, [rdi+18h]; lpCriticalSection
0x180006c1d  mov     dword ptr [rdi+10h], 0
0x180006c24  call    cs:__imp_InitializeCriticalSection
0x180006c2a  lea     r15, ??_7?$CComObject@VCCertEncodeCRLDistInfo@@@ATL@@6B?$IDispatchImpl@UICertEncodeCRLDistInfo2@@$1?IID_ICertEncodeCRLDistInfo2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CCertEncodeCRLDistInfo>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeCRLDistInfo2,&_GUID const IID_ICertEncodeCRLDistInfo2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'}
0x180006c31  mov     qword ptr [rdi+40h], 0
0x180006c39  lea     r12, ??_7?$CComObject@VCCertEncodeCRLDistInfo@@@ATL@@6B?$ISupportErrorInfoImpl@$1?IID_ICertEncodeCRLDistInfo2@@3U_GUID@@B@1@@; const ATL::CComObject<CCertEncodeCRLDistInfo>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeCRLDistInfo2>'}
0x180006c40  mov     [rdi], r15
0x180006c43  mov     [rdi+8], r12
0x180006c47  mov     qword ptr [rdi+50h], 0
0x180006c4f  mov     dword ptr [rdi+58h], 0
0x180006c56  lock inc cs:dword_18000F8D8
0x180006c5d  mov     rax, [rdi]
0x180006c60  mov     r8, rsi
0x180006c63  mov     rdx, rbp
0x180006c66  mov     rcx, rdi
0x180006c69  mov     rax, [rax]
0x180006c6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c71  mov     ebx, eax
0x180006c73  test    eax, eax
0x180006c75  jz      short loc_180006CB3
0x180006c77  mov     [rdi], r15
0x180006c7a  mov     rcx, rdi; this
0x180006c7d  mov     [rdi+8], r12
0x180006c81  mov     dword ptr [rdi+10h], 1
0x180006c88  lock dec cs:dword_18000F8D8
0x180006c8f  call    ??1CCertEncodeCRLDistInfo@@QEAA@XZ; CCertEncodeCRLDistInfo::~CCertEncodeCRLDistInfo(void)
0x180006c94  mov     rcx, rdi; Block
0x180006c97  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006c9c  jmp     short loc_180006CB3
0x180006c9e  test    rsi, rsi
0x180006ca1  jz      loc_180006BE1
0x180006ca7  mov     qword ptr [r8], 0
0x180006cae  mov     ebx, 80040110h
0x180006cb3  mov     eax, ebx
0x180006cb5  add     rsp, 28h
0x180006cb9  pop     r15
0x180006cbb  pop     r12
0x180006cbd  pop     rdi
0x180006cbe  pop     rsi
0x180006cbf  pop     rbp
0x180006cc0  pop     rbx
0x180006cc1  retn
```
