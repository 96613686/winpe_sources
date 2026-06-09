# RefreshTokenRequest::AcquireToken(void)

- ea: `0x14001604c`
- end: `0x1400165ad`
- name: `?AcquireToken@RefreshTokenRequest@@QEAA_NXZ`
- size: `1377`
- prototype: `char __fastcall(RefreshTokenRequest *this)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation`

## callers

- `0x14000a34c`

## callees

- `0x140005458`
- `0x14000579c`
- `0x140005c80`
- `0x1400061dc`
- `0x140008ba8`
- `0x14000c13c`
- `0x14000c384`
- `0x14000c7d8`
- `0x14000c8cc`
- `0x140014ea4`
- `0x14001604c`
- `0x1400165b4`
- `0x14001e1a8`
- `0x1400231f8`
- `0x140025ccc`
- `0x140030010`

## string_xrefs

- `0x1400161b0`: `Processing token request`
- `0x140016530`: `Refresh token request is failed`

## pseudocode

```c
char __fastcall RefreshTokenRequest::AcquireToken(RefreshTokenRequest *this)
{
  _QWORD *v2; // r15
  void (__fastcall ***v3)(_QWORD, __int64); // r14
  _QWORD *v4; // rdx
  _QWORD *v5; // rdx
  char v6; // si
  ChallengeResponseBuilder *v7; // rbx
  __int64 v8; // r9
  int v9; // ebx
  _QWORD *v10; // rdx
  __int64 v11; // rbx
  void (__fastcall ***v12)(_QWORD, __int64); // rbx
  _QWORD *v13; // rdx
  _QWORD *v14; // rdx
  _QWORD *v15; // rdx
  _QWORD *v16; // rdx
  _QWORD *v17; // rdx
  _QWORD *v18; // rdx
  _QWORD *v19; // rdx
  void (__fastcall ***v21)(_QWORD, __int64); // [rsp+20h] [rbp-20h] BYREF
  void (__fastcall ***v22)(_QWORD, __int64); // [rsp+28h] [rbp-18h] BYREF
  __int64 v23; // [rsp+30h] [rbp-10h]
  __int64 v24; // [rsp+38h] [rbp-8h] BYREF
  __int64 v25; // [rsp+80h] [rbp+40h] BYREF
  __int64 v26; // [rsp+88h] [rbp+48h] BYREF
  __int64 v27; // [rsp+90h] [rbp+50h] BYREF
  char v28; // [rsp+98h] [rbp+58h] BYREF

  *((_DWORD *)this + 15) = -895418323;
  RefreshTokenRequest::BuildTokenRefreshRequestMessage(this, &v28);
  AuthenticationContext::GetTokenEndpoint(*((_QWORD *)this + 1), &v27);
  v2 = (_QWORD *)((char *)this + 96);
  ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 96, &dword_14003353C, 0);
  WebRequestFactory::CreateBasicConnection(&v21, *((_QWORD *)this + 1), 0);
  Log::Verbose(this, L"Set request header");
  v26 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                           &v26,
                           L"1.0") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v26, L"1.0", 3);
  v3 = v21;
  v25 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                           &v25,
                           L"x-ms-PKeyAuth") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v25, L"x-ms-PKeyAuth", 13);
  WebRequest::SetRequestHeader(v3, &v25, &v26);
  v4 = (_QWORD *)(v25 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v25 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 8LL))(*v4);
  v5 = (_QWORD *)(v26 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v26 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 8LL))(*v5);
  Log::Verbose(this, L"Processing token request");
  v6 = OAuthTokenRequestBase::ProcessTokenRequest(this);
  if ( !v6 )
  {
    if ( !*(_DWORD *)(*v2 - 16LL) )
    {
      Log::WarnInternal(this, 3400073220LL, 0);
LABEL_41:
      Log::Verbose(this, L"Refresh token request is failed");
      goto LABEL_43;
    }
    Log::InfoInternal(this, 1252589676, 0);
    Log::Verbose(this, L"Challenge info:%s", *v2);
    v7 = (ChallengeResponseBuilder *)*((_QWORD *)this + 18);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v25,
      (__int64 *)this + 12);
    ChallengeResponseBuilder::CreateChallengeResponseForHeader(v7);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v26,
      &v24);
    v9 = *(_DWORD *)(v26 - 16);
    v10 = (_QWORD *)(v26 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v26 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 8LL))(*v10);
    if ( v9 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v26,
        &v24);
      v11 = v26;
      Log::Verbose(this, L"Sending response headers:%s", v26);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v11 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v11 - 24) + 8LL))(*(_QWORD *)(v11 - 24));
      Log::InfoInternal(this, 1252589677, 0);
      WebRequestFactory::CreateBasicConnection(&v22, *((_QWORD *)this + 1), 0);
      v26 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                               &v26,
                               L"1.0") )
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v26, L"1.0", 3);
      v12 = v22;
      v25 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                               &v25,
                               L"x-ms-PKeyAuth") )
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v25, L"x-ms-PKeyAuth", 13);
      WebRequest::SetRequestHeader(v12, &v25, &v26);
      v13 = (_QWORD *)(v25 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v25 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 8LL))(*v13);
      v14 = (_QWORD *)(v26 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v26 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 8LL))(*v14);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v26,
        &v24);
      v25 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                               &v25,
                               L"Authorization") )
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v25, L"Authorization", 13);
      WebRequest::SetRequestHeader(v12, &v25, &v26);
      v15 = (_QWORD *)(v25 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v25 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v15 + 8LL))(*v15);
      v16 = (_QWORD *)(v26 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v26 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v16 + 8LL))(*v16);
      v6 = OAuthTokenRequestBase::ProcessTokenRequest(this);
      if ( !v6 )
        Log::WarnInternal(this, 3400073220LL, 0);
      if ( v12 )
        (**v12)(v12, 1);
    }
    else
    {
      Log::ErrorInternal(this, 3400073267LL, 0, v8);
    }
    v17 = (_QWORD *)(v24 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v24 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v17 + 8LL))(*v17);
    v18 = (_QWORD *)(v23 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v23 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 8LL))(*v18);
    if ( !v6 )
      goto LABEL_41;
  }
  Log::InfoInternal(this, 1252589578, 0);
LABEL_43:
  if ( v3 )
    (**v3)(v3, 1);
  v19 = (_QWORD *)(v27 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v27 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v19 + 8LL))(*v19);
  CSecureString::~CSecureString((CSecureString *)&v28);
  return v6;
}

```

## disassembly

```asm
0x14001604c  push    rbp
0x14001604e  push    rbx
0x14001604f  push    rsi
0x140016050  push    rdi
0x140016051  push    r12
0x140016053  push    r14
0x140016055  push    r15
0x140016057  mov     rbp, rsp
0x14001605a  sub     rsp, 40h
0x14001605e  mov     rdi, rcx
0x140016061  mov     dword ptr [rcx+3Ch], 0CAA1002Dh
0x140016068  lea     rdx, [rbp+arg_18]
0x14001606c  call    ?BuildTokenRefreshRequestMessage@RefreshTokenRequest@@AEAA?AVCSecureString@@XZ; RefreshTokenRequest::BuildTokenRefreshRequestMessage(void)
0x140016071  nop
0x140016072  lea     rdx, [rbp+arg_10]
0x140016076  mov     rcx, [rdi+8]
0x14001607a  call    ?GetTokenEndpoint@AuthenticationContext@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; AuthenticationContext::GetTokenEndpoint(void)
0x14001607f  nop
0x140016080  lea     r15, [rdi+60h]
0x140016084  xor     r8d, r8d
0x140016087  lea     rdx, dword_14003353C
0x14001608e  mov     rcx, r15
0x140016091  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140016096  xor     r8d, r8d
0x140016099  mov     rdx, [rdi+8]
0x14001609d  lea     rcx, [rbp+var_20]
0x1400160a1  call    ?CreateBasicConnection@WebRequestFactory@@CA?AV?$unique_ptr@VWebRequest@@U?$default_delete@VWebRequest@@@std@@@std@@AEBVAuthenticationContext@@_N@Z; WebRequestFactory::CreateBasicConnection(AuthenticationContext const &,bool)
0x1400160a6  nop
0x1400160a7  lea     rdx, aSetRequestHead; "Set request header"
0x1400160ae  mov     rcx, rdi; struct ILogContext *
0x1400160b1  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x1400160b6  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400160bd  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400160c4  mov     rax, [rax+18h]
0x1400160c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400160cd  add     rax, 18h
0x1400160d1  mov     [rbp+arg_8], rax
0x1400160d5  lea     rdx, a10; "1.0"
0x1400160dc  lea     rcx, [rbp+arg_8]
0x1400160e0  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x1400160e5  test    al, al
0x1400160e7  jnz     short loc_140016100
0x1400160e9  mov     r8d, 3
0x1400160ef  lea     rdx, a10; "1.0"
0x1400160f6  lea     rcx, [rbp+arg_8]
0x1400160fa  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400160ff  nop
0x140016100  mov     r14, [rbp+var_20]
0x140016104  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001610b  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140016112  mov     rax, [rax+18h]
0x140016116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001611b  add     rax, 18h
0x14001611f  mov     [rbp+arg_0], rax
0x140016123  lea     rdx, aXMsPkeyauth; "x-ms-PKeyAuth"
0x14001612a  lea     rcx, [rbp+arg_0]
0x14001612e  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140016133  test    al, al
0x140016135  jnz     short loc_14001614E
0x140016137  mov     r8d, 0Dh
0x14001613d  lea     rdx, aXMsPkeyauth; "x-ms-PKeyAuth"
0x140016144  lea     rcx, [rbp+arg_0]
0x140016148  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001614d  nop
0x14001614e  lea     r8, [rbp+arg_8]
0x140016152  lea     rdx, [rbp+arg_0]
0x140016156  mov     rcx, r14
0x140016159  call    ?SetRequestHeader@WebRequest@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; WebRequest::SetRequestHeader(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001615e  nop
0x14001615f  mov     rdx, [rbp+arg_0]
0x140016163  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140016167  or      r12d, 0FFFFFFFFh
0x14001616b  mov     eax, r12d
0x14001616e  lock xadd [rdx+10h], eax
0x140016173  add     eax, r12d
0x140016176  test    eax, eax
0x140016178  jg      short loc_14001618A
0x14001617a  mov     rcx, [rdx]
0x14001617d  mov     rax, [rcx]
0x140016180  mov     rax, [rax+8]
0x140016184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016189  nop
0x14001618a  mov     rdx, [rbp+arg_8]
0x14001618e  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140016192  mov     eax, r12d
0x140016195  lock xadd [rdx+10h], eax
0x14001619a  add     eax, r12d
0x14001619d  test    eax, eax
0x14001619f  jg      short loc_1400161B0
0x1400161a1  mov     rcx, [rdx]
0x1400161a4  mov     rax, [rcx]
0x1400161a7  mov     rax, [rax+8]
0x1400161ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400161b0  lea     rdx, aProcessingToke; "Processing token request"
0x1400161b7  mov     rcx, rdi; struct ILogContext *
0x1400161ba  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x1400161bf  lea     r9, [rbp+arg_10]
0x1400161c3  lea     r8, [rbp+arg_18]
0x1400161c7  lea     rdx, [rbp+var_20]
0x1400161cb  mov     rcx, rdi; struct OAuthTokenRequestBase *
0x1400161ce  call    ?ProcessTokenRequest@OAuthTokenRequestBase@@IEAA_NAEBV?$unique_ptr@VWebRequest@@U?$default_delete@VWebRequest@@@std@@@std@@AEBVCSecureString@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; OAuthTokenRequestBase::ProcessTokenRequest(std::unique_ptr<WebRequest> const &,CSecureString const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400161d3  mov     sil, al
0x1400161d6  test    al, al
0x1400161d8  jnz     loc_140016541
0x1400161de  mov     rcx, [r15]
0x1400161e1  xor     r8d, r8d
0x1400161e4  cmp     [rcx-10h], r8d
0x1400161e8  mov     rcx, rdi
0x1400161eb  jnz     short loc_1400161FC
0x1400161ed  mov     edx, 0CAA90004h
0x1400161f2  call    ?WarnInternal@Log@@CAXPEBVILogContext@@KVResourceId@@ZZ; Log::WarnInternal(ILogContext const *,ulong,ResourceId,...)
0x1400161f7  jmp     loc_140016530
0x1400161fc  mov     edx, 4AA9006Ch
0x140016201  call    ?InfoInternal@Log@@CAXPEBVILogContext@@KVResourceId@@ZZ; Log::InfoInternal(ILogContext const *,ulong,ResourceId,...)
0x140016206  mov     r8, [r15]
0x140016209  lea     rdx, aChallengeInfoS; "Challenge info:%s"
0x140016210  mov     rcx, rdi; struct ILogContext *
0x140016213  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x140016218  mov     rbx, [rdi+90h]
0x14001621f  mov     rdx, r15
0x140016222  lea     rcx, [rbp+arg_0]
0x140016226  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001622b  mov     r8, rax
0x14001622e  lea     rdx, [rbp+var_10]
0x140016232  mov     rcx, rbx; this
0x140016235  call    ?CreateChallengeResponseForHeader@ChallengeResponseBuilder@@QEAA?AVChallengeResponse@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; ChallengeResponseBuilder::CreateChallengeResponseForHeader(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x14001623a  nop
0x14001623b  lea     rdx, [rbp+var_8]
0x14001623f  lea     rcx, [rbp+arg_8]
0x140016243  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140016248  mov     rax, [rbp+arg_8]
0x14001624c  mov     ebx, [rax-10h]
0x14001624f  lea     rdx, [rax-18h]
0x140016253  mov     eax, r12d
0x140016256  lock xadd [rdx+10h], eax
0x14001625b  add     eax, r12d
0x14001625e  test    eax, eax
0x140016260  jg      short loc_140016271
0x140016262  mov     rcx, [rdx]
0x140016265  mov     rax, [rcx]
0x140016268  mov     rax, [rax+8]
0x14001626c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016271  test    ebx, ebx
0x140016273  jz      loc_1400164CE
0x140016279  lea     rdx, [rbp+var_8]
0x14001627d  lea     rcx, [rbp+arg_8]
0x140016281  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140016286  nop
0x140016287  mov     rbx, [rbp+arg_8]
0x14001628b  mov     r8, rbx
0x14001628e  lea     rdx, aSendingRespons; "Sending response headers:%s"
0x140016295  mov     rcx, rdi; struct ILogContext *
0x140016298  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x14001629d  nop
0x14001629e  lea     rdx, [rbx-18h]
0x1400162a2  mov     eax, r12d
0x1400162a5  lock xadd [rdx+10h], eax
0x1400162aa  add     eax, r12d
0x1400162ad  test    eax, eax
0x1400162af  jg      short loc_1400162C0
0x1400162b1  mov     rcx, [rdx]
0x1400162b4  mov     rax, [rcx]
0x1400162b7  mov     rax, [rax+8]
0x1400162bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400162c0  xor     r8d, r8d
0x1400162c3  mov     edx, 4AA9006Dh
0x1400162c8  mov     rcx, rdi
0x1400162cb  call    ?InfoInternal@Log@@CAXPEBVILogContext@@KVResourceId@@ZZ; Log::InfoInternal(ILogContext const *,ulong,ResourceId,...)
0x1400162d0  xor     r8d, r8d
0x1400162d3  mov     rdx, [rdi+8]
0x1400162d7  lea     rcx, [rbp+var_18]
0x1400162db  call    ?CreateBasicConnection@WebRequestFactory@@CA?AV?$unique_ptr@VWebRequest@@U?$default_delete@VWebRequest@@@std@@@std@@AEBVAuthenticationContext@@_N@Z; WebRequestFactory::CreateBasicConnection(AuthenticationContext const &,bool)
0x1400162e0  nop
0x1400162e1  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400162e8  lea     rsi, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400162ef  mov     rcx, rsi
0x1400162f2  mov     rax, [rax+18h]
0x1400162f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400162fb  add     rax, 18h
0x1400162ff  mov     [rbp+arg_8], rax
0x140016303  lea     rdx, a10; "1.0"
0x14001630a  lea     rcx, [rbp+arg_8]
0x14001630e  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140016313  test    al, al
0x140016315  jnz     short loc_14001632E
0x140016317  mov     r8d, 3
0x14001631d  lea     rdx, a10; "1.0"
0x140016324  lea     rcx, [rbp+arg_8]
0x140016328  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001632d  nop
0x14001632e  mov     rbx, [rbp+var_18]
0x140016332  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140016339  mov     rcx, rsi
0x14001633c  mov     rax, [rax+18h]
0x140016340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016345  add     rax, 18h
0x140016349  mov     [rbp+arg_0], rax
0x14001634d  lea     rdx, aXMsPkeyauth; "x-ms-PKeyAuth"
0x140016354  lea     rcx, [rbp+arg_0]
0x140016358  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14001635d  test    al, al
0x14001635f  jnz     short loc_140016378
0x140016361  mov     r8d, 0Dh
0x140016367  lea     rdx, aXMsPkeyauth; "x-ms-PKeyAuth"
0x14001636e  lea     rcx, [rbp+arg_0]
0x140016372  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140016377  nop
0x140016378  lea     r8, [rbp+arg_8]
0x14001637c  lea     rdx, [rbp+arg_0]
0x140016380  mov     rcx, rbx
0x140016383  call    ?SetRequestHeader@WebRequest@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; WebRequest::SetRequestHeader(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140016388  nop
0x140016389  mov     rdx, [rbp+arg_0]
0x14001638d  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140016391  mov     eax, r12d
0x140016394  lock xadd [rdx+10h], eax
0x140016399  add     eax, r12d
0x14001639c  test    eax, eax
0x14001639e  jg      short loc_1400163B0
0x1400163a0  mov     rcx, [rdx]
0x1400163a3  mov     rax, [rcx]
0x1400163a6  mov     rax, [rax+8]
0x1400163aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400163af  nop
0x1400163b0  mov     rdx, [rbp+arg_8]
0x1400163b4  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400163b8  mov     eax, r12d
0x1400163bb  lock xadd [rdx+10h], eax
0x1400163c0  add     eax, r12d
0x1400163c3  test    eax, eax
0x1400163c5  jg      short loc_1400163D6
0x1400163c7  mov     rcx, [rdx]
0x1400163ca  mov     rax, [rcx]
0x1400163cd  mov     rax, [rax+8]
0x1400163d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400163d6  lea     rdx, [rbp+var_8]
0x1400163da  lea     rcx, [rbp+arg_8]
0x1400163de  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400163e3  nop
0x1400163e4  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400163eb  mov     rcx, rsi
0x1400163ee  mov     rax, [rax+18h]
0x1400163f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400163f7  add     rax, 18h
0x1400163fb  mov     [rbp+arg_0], rax
0x1400163ff  lea     rdx, aAuthorization; "Authorization"
0x140016406  lea     rcx, [rbp+arg_0]
0x14001640a  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14001640f  test    al, al
0x140016411  jnz     short loc_14001642A
0x140016413  mov     r8d, 0Dh
0x140016419  lea     rdx, aAuthorization; "Authorization"
0x140016420  lea     rcx, [rbp+arg_0]
0x140016424  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140016429  nop
0x14001642a  lea     r8, [rbp+arg_8]
0x14001642e  lea     rdx, [rbp+arg_0]
0x140016432  mov     rcx, rbx
0x140016435  call    ?SetRequestHeader@WebRequest@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; WebRequest::SetRequestHeader(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001643a  nop
0x14001643b  mov     rdx, [rbp+arg_0]
0x14001643f  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140016443  mov     eax, r12d
0x140016446  lock xadd [rdx+10h], eax
0x14001644b  add     eax, r12d
0x14001644e  test    eax, eax
0x140016450  jg      short loc_140016462
0x140016452  mov     rcx, [rdx]
0x140016455  mov     rax, [rcx]
0x140016458  mov     rax, [rax+8]
0x14001645c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016461  nop
0x140016462  mov     rdx, [rbp+arg_8]
0x140016466  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001646a  mov     eax, r12d
0x14001646d  lock xadd [rdx+10h], eax
0x140016472  add     eax, r12d
0x140016475  test    eax, eax
0x140016477  jg      short loc_140016488
0x140016479  mov     rcx, [rdx]
0x14001647c  mov     rax, [rcx]
0x14001647f  mov     rax, [rax+8]
0x140016483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016488  lea     r9, [rbp+arg_10]
0x14001648c  lea     r8, [rbp+arg_18]
0x140016490  lea     rdx, [rbp+var_18]
0x140016494  mov     rcx, rdi; struct OAuthTokenRequestBase *
0x140016497  call    ?ProcessTokenRequest@OAuthTokenRequestBase@@IEAA_NAEBV?$unique_ptr@VWebRequest@@U?$default_delete@VWebRequest@@@std@@@std@@AEBVCSecureString@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; OAuthTokenRequestBase::ProcessTokenRequest(std::unique_ptr<WebRequest> const &,CSecureString const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001649c  mov     sil, al
0x14001649f  test    al, al
0x1400164a1  jnz     short loc_1400164B4
0x1400164a3  xor     r8d, r8d
0x1400164a6  mov     edx, 0CAA90004h
0x1400164ab  mov     rcx, rdi
0x1400164ae  call    ?WarnInternal@Log@@CAXPEBVILogContext@@KVResourceId@@ZZ; Log::WarnInternal(ILogContext const *,ulong,ResourceId,...)
0x1400164b3  nop
0x1400164b4  test    rbx, rbx
0x1400164b7  jz      short loc_1400164DF
0x1400164b9  mov     rax, [rbx]
0x1400164bc  mov     edx, 1
  ... truncated ...
```
