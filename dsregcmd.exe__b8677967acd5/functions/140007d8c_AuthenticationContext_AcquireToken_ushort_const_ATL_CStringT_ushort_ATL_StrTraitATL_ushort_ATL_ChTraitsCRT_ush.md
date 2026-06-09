# AuthenticationContext::AcquireToken(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x140007d8c`
- end: `0x140008135`
- name: `?AcquireToken@AuthenticationContext@@QEAAPEAVTokenRequest@@PEBGAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `937`
- prototype: `AggregatedTokenRequest *__fastcall(struct ILogContext *, unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x14000651c`

## callees

- `0x140001814`
- `0x140005458`
- `0x1400054e8`
- `0x14000579c`
- `0x140007bf8`
- `0x140007d8c`
- `0x14000a34c`
- `0x14000be24`
- `0x14000c384`
- `0x14000c7d8`
- `0x14000caac`
- `0x14000e040`
- `0x14000f5f0`
- `0x14001088c`
- `0x14002c3e8`
- `0x140030010`

## string_xrefs

- `0x140007e91`: `onecore\ds\security\dsreg\win32\adal.native\authenticationcontext.cpp`
- `0x140008037`: `onecore\ds\security\dsreg\win32\adal.native\authenticationcontext.cpp`
- `0x140007fb2`: `Token is not available in the cache`
- `0x140008022`: `Authority validation is completed`

## pseudocode

```c
AggregatedTokenRequest *__fastcall AuthenticationContext::AcquireToken(
        struct ILogContext *a1,
        unsigned __int16 *a2,
        __int64 *a3)
{
  int v6; // esi
  bool v7; // bl
  _QWORD *v8; // rdx
  _QWORD *v9; // r14
  _QWORD *v10; // rdx
  _QWORD *v11; // rdx
  char IsValidAuthority; // bl
  _QWORD *v14; // rdx
  AggregatedTokenRequest *v15; // rbx
  _QWORD *v16; // rdx
  _QWORD *v17; // rdx
  __int64 v18; // [rsp+20h] [rbp-30h] BYREF
  _QWORD pExceptionObject[2]; // [rsp+28h] [rbp-28h] BYREF
  __int64 v20; // [rsp+38h] [rbp-18h] BYREF
  __int64 v21; // [rsp+40h] [rbp-10h] BYREF
  __int64 v22; // [rsp+48h] [rbp-8h]
  AggregatedTokenRequest *v23; // [rsp+98h] [rbp+48h] BYREF

  v6 = 0;
  LODWORD(v23) = 0;
  ArgumentException::ThrowIfNullOrEmpty(a2, 0xCAA1000A);
  v20 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v21 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v22 = 0;
  v7 = 0;
  if ( (*((_BYTE *)a1 + 296) & 8) == 0 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v18,
      (__int64)a2);
    v6 = 1;
    LODWORD(v23) = 1;
    if ( (unsigned __int8)TokenCache::Get((char *)a1 + 88, &v18, &v20, a1) )
      v7 = 1;
  }
  if ( (v6 & 1) != 0 )
  {
    v6 &= ~1u;
    v8 = (_QWORD *)(v18 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v18 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 8LL))(*v8);
  }
  if ( v7 )
  {
    Log::InfoInternal(a1, 1252589576, 0);
    v9 = operator new(0x38u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\authenticationcontext.cpp");
    pExceptionObject[0] = v9;
    if ( v9 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v18,
        (__int64)a2);
      v6 |= 2u;
      LODWORD(v23) = v6;
      TokenRequest::TokenRequest(v9, (__int64)a1, &v18, a3);
      *v9 = &CachedTokenRequest::`vftable';
      v9[4] = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      v9[5] = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      v9[6] = 0;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        v9 + 4,
        &v20);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        v9 + 5,
        &v21);
      v9[6] = v22;
    }
    else
    {
      v9 = 0;
    }
    if ( (v6 & 2) != 0 )
    {
      v10 = (_QWORD *)(v18 - 24);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v18 - 24 + 16), 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 8LL))(*v10);
    }
    CSecureString::~CSecureString((CSecureString *)&v21);
    v11 = (_QWORD *)(v20 - 24);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v20 - 24 + 16), 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 8LL))(*v11);
    return (AggregatedTokenRequest *)v9;
  }
  else
  {
    Log::Verbose(a1, L"Token is not available in the cache");
    if ( (*((_BYTE *)a1 + 296) & 1) != 0 )
    {
      Log::Verbose(a1, L"Authority validation is enabled");
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v23,
        (__int64 *)a1 + 1);
      v6 |= 8u;
      IsValidAuthority = Discovery::IsValidAuthority(&v23, a1);
      v14 = (_QWORD *)((char *)v23 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)v23 - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 8LL))(*v14);
      if ( !IsValidAuthority )
      {
        Exception::Exception((Exception *)pExceptionObject, -895418362);
        throw (Exception *)pExceptionObject;
      }
      Log::Verbose(a1, L"Authority validation is completed");
    }
    v15 = (AggregatedTokenRequest *)operator new(
                                      0x28u,
                                      1,
                                      "onecore\\ds\\security\\dsreg\\win32\\adal.native\\authenticationcontext.cpp");
    pExceptionObject[0] = v15;
    if ( v15 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v18,
        (__int64)a2);
      v6 |= 4u;
      LODWORD(v23) = v6;
      TokenRequest::TokenRequest(v15, (__int64)a1, &v18, a3);
      *(_QWORD *)v15 = &AggregatedTokenRequest::`vftable';
      *((_QWORD *)v15 + 4) = 0;
    }
    else
    {
      v15 = 0;
    }
    v23 = v15;
    if ( (v6 & 4) != 0 )
    {
      v16 = (_QWORD *)(v18 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v18 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v16 + 8LL))(*v16);
    }
    AggregatedTokenRequest::AcquireToken(v15);
    CSecureString::~CSecureString((CSecureString *)&v21);
    v17 = (_QWORD *)(v20 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v20 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v17 + 8LL))(*v17);
    return v15;
  }
}

```

## disassembly

```asm
0x140007d8c  mov     [rsp-28h+arg_0], rbx
0x140007d91  mov     [rsp-28h+arg_8], rsi
0x140007d96  push    rbp
0x140007d97  push    rdi
0x140007d98  push    r12
0x140007d9a  push    r14
0x140007d9c  push    r15
0x140007d9e  mov     rbp, rsp
0x140007da1  sub     rsp, 50h
0x140007da5  mov     r12, r8
0x140007da8  mov     r15, rdx
0x140007dab  mov     rdi, rcx
0x140007dae  xor     esi, esi
0x140007db0  mov     dword ptr [rbp+arg_18], esi
0x140007db3  mov     edx, 0CAA1000Ah; unsigned int
0x140007db8  mov     rcx, r15; unsigned __int16 *
0x140007dbb  call    ?ThrowIfNullOrEmpty@ArgumentException@@SAXPEBGK@Z; ArgumentException::ThrowIfNullOrEmpty(ushort const *,ulong)
0x140007dc0  nop
0x140007dc1  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140007dc8  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140007dcf  mov     rax, [rax+18h]
0x140007dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007dd8  add     rax, 18h
0x140007ddc  mov     [rbp+var_18], rax
0x140007de0  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140007de7  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140007dee  mov     rax, [rax+18h]
0x140007df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007df7  add     rax, 18h
0x140007dfb  mov     [rbp+var_10], rax
0x140007dff  mov     [rbp+var_8], rsi
0x140007e03  test    byte ptr [rdi+128h], 8
0x140007e0a  jnz     short loc_140007E3E
0x140007e0c  mov     rdx, r15
0x140007e0f  lea     rcx, [rbp+var_30]
0x140007e13  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140007e18  nop
0x140007e19  mov     esi, 1
0x140007e1e  mov     dword ptr [rbp+arg_18], esi
0x140007e21  lea     rcx, [rdi+58h]
0x140007e25  mov     r9, rdi
0x140007e28  lea     r8, [rbp+var_18]
0x140007e2c  lea     rdx, [rbp+var_30]
0x140007e30  call    ?Get@TokenCache@@QEAA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAVItem@1@PEAVILogContext@@@Z; TokenCache::Get(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,TokenCache::Item &,ILogContext *)
0x140007e35  test    al, al
0x140007e37  jz      short loc_140007E3E
0x140007e39  mov     bl, sil
0x140007e3c  jmp     short loc_140007E40
0x140007e3e  xor     bl, bl
0x140007e40  or      r14d, 0FFFFFFFFh
0x140007e44  test    sil, 1
0x140007e48  jz      short loc_140007E73
0x140007e4a  and     esi, 0FFFFFFFEh
0x140007e4d  mov     rdx, [rbp+var_30]
0x140007e51  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140007e55  mov     eax, r14d
0x140007e58  lock xadd [rdx+10h], eax
0x140007e5d  add     eax, r14d
0x140007e60  test    eax, eax
0x140007e62  jg      short loc_140007E73
0x140007e64  mov     rcx, [rdx]
0x140007e67  mov     rax, [rcx]
0x140007e6a  mov     rax, [rax+8]
0x140007e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007e73  mov     rcx, rdi; struct ILogContext *
0x140007e76  test    bl, bl
0x140007e78  jz      loc_140007FB2
0x140007e7e  xor     r8d, r8d
0x140007e81  mov     edx, 4AA90008h
0x140007e86  call    ?InfoInternal@Log@@CAXPEBVILogContext@@KVResourceId@@ZZ; Log::InfoInternal(ILogContext const *,ulong,ResourceId,...)
0x140007e8b  mov     r9d, 0A7h; int
0x140007e91  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x140007e98  mov     edx, 1; int
0x140007e9d  lea     ecx, [rdx+37h]; unsigned __int64
0x140007ea0  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x140007ea5  mov     r14, rax
0x140007ea8  mov     [rbp+pExceptionObject], rax
0x140007eac  test    rax, rax
0x140007eaf  jz      loc_140007F4F
0x140007eb5  mov     rdx, r15
0x140007eb8  lea     rcx, [rbp+var_30]
0x140007ebc  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140007ec1  nop
0x140007ec2  or      esi, 2
0x140007ec5  mov     dword ptr [rbp+arg_18], esi
0x140007ec8  mov     r9, r12
0x140007ecb  lea     r8, [rbp+var_30]
0x140007ecf  mov     rdx, rdi
0x140007ed2  mov     rcx, r14
0x140007ed5  call    ??0TokenRequest@@QEAA@PEAVAuthenticationContext@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1@Z; TokenRequest::TokenRequest(AuthenticationContext *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140007eda  nop
0x140007edb  lea     rax, ??_7CachedTokenRequest@@6B@; const CachedTokenRequest::`vftable'
0x140007ee2  mov     [r14], rax
0x140007ee5  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140007eec  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140007ef3  mov     rax, [rax+18h]
0x140007ef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007efc  add     rax, 18h
0x140007f00  mov     [r14+20h], rax
0x140007f04  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140007f0b  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140007f12  mov     rax, [rax+18h]
0x140007f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007f1b  add     rax, 18h
0x140007f1f  mov     [r14+28h], rax
0x140007f23  mov     qword ptr [r14+30h], 0
0x140007f2b  lea     rdx, [rbp+var_18]
0x140007f2f  lea     rcx, [r14+20h]
0x140007f33  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140007f38  lea     rdx, [rbp+var_10]
0x140007f3c  lea     rcx, [r14+28h]
0x140007f40  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140007f45  mov     rax, [rbp+var_8]
0x140007f49  mov     [r14+30h], rax
0x140007f4d  jmp     short loc_140007F52
0x140007f4f  xor     r14d, r14d
0x140007f52  test    sil, 2
0x140007f56  jz      short loc_140007F7D
0x140007f58  mov     rdx, [rbp+var_30]
0x140007f5c  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140007f60  or      eax, 0FFFFFFFFh
0x140007f63  lock xadd [rdx+10h], eax
0x140007f68  sub     eax, 1
0x140007f6b  jg      short loc_140007F7D
0x140007f6d  mov     rcx, [rdx]
0x140007f70  mov     rax, [rcx]
0x140007f73  mov     rax, [rax+8]
0x140007f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007f7c  nop
0x140007f7d  lea     rcx, [rbp+var_10]; this
0x140007f81  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x140007f86  mov     rdx, [rbp+var_18]
0x140007f8a  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140007f8e  or      ecx, 0FFFFFFFFh
0x140007f91  lock xadd [rdx+10h], ecx
0x140007f96  sub     ecx, 1
0x140007f99  jg      short loc_140007FAA
0x140007f9b  mov     rcx, [rdx]
0x140007f9e  mov     r8, [rcx]
0x140007fa1  mov     rax, [r8+8]
0x140007fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007faa  mov     rax, r14
0x140007fad  jmp     loc_1400080FD
0x140007fb2  lea     rdx, aTokenIsNotAvai; "Token is not available in the cache"
0x140007fb9  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x140007fbe  test    byte ptr [rdi+128h], 1
0x140007fc5  jz      short loc_140008031
0x140007fc7  lea     rdx, aAuthorityValid_0; "Authority validation is enabled"
0x140007fce  mov     rcx, rdi; struct ILogContext *
0x140007fd1  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x140007fd6  lea     rdx, [rdi+8]
0x140007fda  lea     rcx, [rbp+arg_18]
0x140007fde  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140007fe3  or      esi, 8
0x140007fe6  mov     rdx, rdi
0x140007fe9  lea     rcx, [rbp+arg_18]
0x140007fed  call    ?IsValidAuthority@Discovery@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBVAuthenticationContext@@@Z; Discovery::IsValidAuthority(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,AuthenticationContext const &)
0x140007ff2  mov     bl, al
0x140007ff4  mov     rdx, [rbp+arg_18]
0x140007ff8  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140007ffc  mov     ecx, r14d
0x140007fff  lock xadd [rdx+10h], ecx
0x140008004  add     ecx, r14d
0x140008007  test    ecx, ecx
0x140008009  jg      short loc_14000801A
0x14000800b  mov     rcx, [rdx]
0x14000800e  mov     r8, [rcx]
0x140008011  mov     rax, [r8+8]
0x140008015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000801a  test    bl, bl
0x14000801c  jz      loc_140008116
0x140008022  lea     rdx, aAuthorityValid; "Authority validation is completed"
0x140008029  mov     rcx, rdi; struct ILogContext *
0x14000802c  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x140008031  mov     r9d, 0B6h; int
0x140008037  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14000803e  mov     edx, 1; int
0x140008043  lea     ecx, [rdx+27h]; unsigned __int64
0x140008046  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x14000804b  mov     rbx, rax
0x14000804e  mov     [rbp+pExceptionObject], rax
0x140008052  test    rax, rax
0x140008055  jz      short loc_140008090
0x140008057  mov     rdx, r15
0x14000805a  lea     rcx, [rbp+var_30]
0x14000805e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140008063  nop
0x140008064  or      esi, 4
0x140008067  mov     dword ptr [rbp+arg_18], esi
0x14000806a  mov     r9, r12
0x14000806d  lea     r8, [rbp+var_30]
0x140008071  mov     rdx, rdi
0x140008074  mov     rcx, rbx
0x140008077  call    ??0TokenRequest@@QEAA@PEAVAuthenticationContext@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1@Z; TokenRequest::TokenRequest(AuthenticationContext *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000807c  lea     rax, ??_7AggregatedTokenRequest@@6B@; const AggregatedTokenRequest::`vftable'
0x140008083  mov     [rbx], rax
0x140008086  mov     qword ptr [rbx+20h], 0
0x14000808e  jmp     short loc_140008092
0x140008090  xor     ebx, ebx
0x140008092  mov     [rbp+arg_18], rbx
0x140008096  test    sil, 4
0x14000809a  jz      short loc_1400080C2
0x14000809c  mov     rdx, [rbp+var_30]
0x1400080a0  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400080a4  mov     eax, r14d
0x1400080a7  lock xadd [rdx+10h], eax
0x1400080ac  add     eax, r14d
0x1400080af  test    eax, eax
0x1400080b1  jg      short loc_1400080C2
0x1400080b3  mov     rcx, [rdx]
0x1400080b6  mov     rax, [rcx]
0x1400080b9  mov     rax, [rax+8]
0x1400080bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400080c2  mov     rcx, rbx; this
0x1400080c5  call    ?AcquireToken@AggregatedTokenRequest@@QEAA_NXZ; AggregatedTokenRequest::AcquireToken(void)
0x1400080ca  nop
0x1400080cb  lea     rcx, [rbp+var_10]; this
0x1400080cf  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x1400080d4  mov     rdx, [rbp+var_18]
0x1400080d8  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400080dc  mov     ecx, r14d
0x1400080df  lock xadd [rdx+10h], ecx
0x1400080e4  add     ecx, r14d
0x1400080e7  test    ecx, ecx
0x1400080e9  jg      short loc_1400080FA
0x1400080eb  mov     rcx, [rdx]
0x1400080ee  mov     r8, [rcx]
0x1400080f1  mov     rax, [r8+8]
0x1400080f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400080fa  mov     rax, rbx
0x1400080fd  lea     r11, [rsp+50h+var_s0]
0x140008102  mov     rbx, [r11+30h]
0x140008106  mov     rsi, [r11+38h]
0x14000810a  mov     rsp, r11
0x14000810d  pop     r15
0x14000810f  pop     r14
0x140008111  pop     r12
0x140008113  pop     rdi
0x140008114  pop     rbp
0x140008115  retn
0x140008116  mov     edx, 0CAA10006h; unsigned int
0x14000811b  lea     rcx, [rbp+pExceptionObject]; this
0x14000811f  call    ??0Exception@@QEAA@K@Z; Exception::Exception(ulong)
0x140008124  lea     rdx, _TI1?AVException@@; pThrowInfo
0x14000812b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000812f  call    _CxxThrowException_0
```
