# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CCertEncodeAltName>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800069b0`
- end: `0x180006ab6`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCCertEncodeAltName@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `262`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180001008`
- `0x180001014`
- `0x180002acc`
- `0x18000413c`
- `0x1800069b0`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006a14`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006a14`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CCertEncodeAltName>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
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
  v6 = (char *)operator new(0x68u);
  if ( v6 )
  {
    ATL::CComTypeInfoHolder::AddRef((ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<ICertEncodeAltName2,&_GUID const IID_ICertEncodeAltName2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::_tih);
    *((_DWORD *)v6 + 4) = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v6 + 24));
    *((_QWORD *)v6 + 8) = 0;
    *(_QWORD *)v6 = &ATL::CComObject<CCertEncodeAltName>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeAltName2,&_GUID const IID_ICertEncodeAltName2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v6 + 1) = &ATL::CComObject<CCertEncodeAltName>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeAltName2>'};
    *((_QWORD *)v6 + 10) = 0;
    *((_DWORD *)v6 + 23) = 0;
    v6[96] = 0;
    _InterlockedIncrement(&dword_18000F8D8);
    v5 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v6)(v6, a2, a3);
    if ( v5 )
    {
      *(_QWORD *)v6 = &ATL::CComObject<CCertEncodeAltName>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeAltName2,&_GUID const IID_ICertEncodeAltName2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'};
      *((_QWORD *)v6 + 1) = &ATL::CComObject<CCertEncodeAltName>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeAltName2>'};
      *((_DWORD *)v6 + 4) = 1;
      _InterlockedDecrement(&dword_18000F8D8);
      CCertEncodeAltName::~CCertEncodeAltName((CCertEncodeAltName *)v6);
      operator delete(v6);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800069b0  push    rbx
0x1800069b2  push    rbp
0x1800069b3  push    rsi
0x1800069b4  push    rdi
0x1800069b5  push    r12
0x1800069b7  push    r15
0x1800069b9  sub     rsp, 28h
0x1800069bd  mov     rsi, r8
0x1800069c0  mov     rbp, rdx
0x1800069c3  test    rcx, rcx
0x1800069c6  jnz     loc_180006A92
0x1800069cc  test    r8, r8
0x1800069cf  jnz     short loc_1800069DB
0x1800069d1  mov     ebx, 80004003h
0x1800069d6  jmp     loc_180006AA7
0x1800069db  mov     ecx, 68h ; 'h'; Size
0x1800069e0  mov     qword ptr [r8], 0
0x1800069e7  mov     ebx, 8007000Eh
0x1800069ec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800069f1  mov     rdi, rax
0x1800069f4  test    rax, rax
0x1800069f7  jz      loc_180006AA7
0x1800069fd  lea     rcx, ?_tih@?$IDispatchImpl@UICertEncodeAltName2@@$1?IID_ICertEncodeAltName2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180006a04  call    ?AddRef@CComTypeInfoHolder@ATL@@QEAAXXZ; ATL::CComTypeInfoHolder::AddRef(void)
0x180006a09  lea     rcx, [rdi+18h]; lpCriticalSection
0x180006a0d  mov     dword ptr [rdi+10h], 0
0x180006a14  call    cs:__imp_InitializeCriticalSection
0x180006a1a  lea     r15, ??_7?$CComObject@VCCertEncodeAltName@@@ATL@@6B?$IDispatchImpl@UICertEncodeAltName2@@$1?IID_ICertEncodeAltName2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CCertEncodeAltName>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeAltName2,&_GUID const IID_ICertEncodeAltName2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'}
0x180006a21  mov     qword ptr [rdi+40h], 0
0x180006a29  lea     r12, ??_7?$CComObject@VCCertEncodeAltName@@@ATL@@6B?$ISupportErrorInfoImpl@$1?IID_ICertEncodeAltName2@@3U_GUID@@B@1@@; const ATL::CComObject<CCertEncodeAltName>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeAltName2>'}
0x180006a30  mov     [rdi], r15
0x180006a33  mov     [rdi+8], r12
0x180006a37  mov     qword ptr [rdi+50h], 0
0x180006a3f  mov     dword ptr [rdi+5Ch], 0
0x180006a46  mov     byte ptr [rdi+60h], 0
0x180006a4a  lock inc cs:dword_18000F8D8
0x180006a51  mov     rax, [rdi]
0x180006a54  mov     r8, rsi
0x180006a57  mov     rdx, rbp
0x180006a5a  mov     rcx, rdi
0x180006a5d  mov     rax, [rax]
0x180006a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a65  mov     ebx, eax
0x180006a67  test    eax, eax
0x180006a69  jz      short loc_180006AA7
0x180006a6b  mov     [rdi], r15
0x180006a6e  mov     rcx, rdi; this
0x180006a71  mov     [rdi+8], r12
0x180006a75  mov     dword ptr [rdi+10h], 1
0x180006a7c  lock dec cs:dword_18000F8D8
0x180006a83  call    ??1CCertEncodeAltName@@QEAA@XZ; CCertEncodeAltName::~CCertEncodeAltName(void)
0x180006a88  mov     rcx, rdi; Block
0x180006a8b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006a90  jmp     short loc_180006AA7
0x180006a92  test    rsi, rsi
0x180006a95  jz      loc_1800069D1
0x180006a9b  mov     qword ptr [r8], 0
0x180006aa2  mov     ebx, 80040110h
0x180006aa7  mov     eax, ebx
0x180006aa9  add     rsp, 28h
0x180006aad  pop     r15
0x180006aaf  pop     r12
0x180006ab1  pop     rdi
0x180006ab2  pop     rsi
0x180006ab3  pop     rbp
0x180006ab4  pop     rbx
0x180006ab5  retn
```
