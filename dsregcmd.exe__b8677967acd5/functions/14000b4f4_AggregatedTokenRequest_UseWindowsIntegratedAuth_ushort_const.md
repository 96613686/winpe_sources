# AggregatedTokenRequest::UseWindowsIntegratedAuth(ushort const *)

- ea: `0x14000b4f4`
- end: `0x14000b7da`
- name: `?UseWindowsIntegratedAuth@AggregatedTokenRequest@@QEAAXPEBG@Z`
- size: `742`
- prototype: `void __fastcall(AggregatedTokenRequest *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140006fb8`

## callees

- `0x140001814`
- `0x140005458`
- `0x14000579c`
- `0x140005c80`
- `0x1400061dc`
- `0x14000a28c`
- `0x14000a610`
- `0x14000ab04`
- `0x14000b3f8`
- `0x14000b4f4`
- `0x14000c7d8`
- `0x14000e000`
- `0x14001425c`
- `0x140016a04`
- `0x14002c3e8`
- `0x140030010`

## string_xrefs

- `0x14000b56a`: `onecore\ds\security\dsreg\win32\adal.native\aggregatedtokenrequest.cpp`
- `0x14000b54a`: `AggregatedTokenRequest::UseWindowsIntegratedAuth- received realm info`
- `0x14000b50d`: `AggregatedTokenRequest::UseWindowsIntegratedAuth w Tenant`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall AggregatedTokenRequest::UseWindowsIntegratedAuth(AggregatedTokenRequest *this, unsigned __int16 *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rdi
  __int64 *v6; // r14
  _QWORD *v7; // rsi
  __int64 v8; // rcx
  volatile signed __int32 *v9; // rdx
  FailedTokenRequest *v10; // rax
  __int64 *v11; // rax
  volatile signed __int32 *v12; // [rsp+30h] [rbp-B8h] BYREF
  __int64 v13; // [rsp+38h] [rbp-B0h] BYREF
  __int64 v14; // [rsp+40h] [rbp-A8h] BYREF
  _QWORD *v15; // [rsp+48h] [rbp-A0h]
  _DWORD v16[6]; // [rsp+50h] [rbp-98h] BYREF
  __int64 v17[3]; // [rsp+68h] [rbp-80h] BYREF
  const Exception *v18; // [rsp+80h] [rbp-68h] BYREF
  _BYTE v19[16]; // [rsp+88h] [rbp-60h] BYREF
  _BYTE v20[16]; // [rsp+98h] [rbp-50h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+A8h] [rbp-40h] BYREF
  void *v23; // [rsp+100h] [rbp+18h] BYREF
  FailedTokenRequest *v24; // [rsp+108h] [rbp+20h] BYREF

  Log::Verbose(this, L"AggregatedTokenRequest::UseWindowsIntegratedAuth w Tenant");
  if ( *((_QWORD *)this + 4) )
  {
    InvalidCallException::InvalidCallException((InvalidCallException *)v19, -895418313);
    throw (InvalidCallException *)v19;
  }
  try
  {
    if ( !a2 || !*a2 )
    {
      Log::Verbose(this, L"Error, tenantName MUST be provided.");
      InvalidCallException::InvalidCallException((InvalidCallException *)pExceptionObject, -2147024809);
      throw (InvalidCallException *)pExceptionObject;
    }
    AggregatedTokenRequest::GetRealmInfo((__int64)this, (__int64)v16, a2);
    Log::Verbose(this, L"AggregatedTokenRequest::UseWindowsIntegratedAuth- received realm info");
    if ( v16[0] != 2 )
    {
      InvalidCallException::InvalidCallException((InvalidCallException *)v20, -894894049);
      throw (InvalidCallException *)v20;
    }
    v4 = operator new(0x90u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\aggregatedtokenrequest.cpp");
    v5 = v4;
    v23 = v4;
    if ( v4 )
    {
      OAuthTokenRequestBase::OAuthTokenRequestBase(
        (__int64)v4,
        *((_QWORD *)this + 1),
        (__int64)this + 16,
        (__int64)this + 24);
      *v5 = &WSTrustTokenRequest::`vftable';
    }
    else
    {
      v5 = 0;
    }
    v15 = v5;
    AggregatedTokenRequest::GetAppliesTo(this, (void **)&v12);
    v17[1] = (__int64)&v13;
    v6 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
           &v13,
           (__int64 *)&v12);
    v17[2] = (__int64)&v14;
    v7 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
           &v14,
           v17);
    v24 = (FailedTokenRequest *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
            (void *const *)&v24,
            (__int64)&dword_14003353C) )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v24, &dword_14003353C, 0);
    v23 = (void *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
            &v23,
            (__int64)&dword_14003353C) )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v23, &dword_14003353C, 0);
    WSTrustTokenRequest::AcquireToken((__int64)v5, &v23, &v24, v7, v6, 1);
    CSecureString::~CSecureString((CSecureString *)&v23);
    CSecureString::~CSecureString((CSecureString *)&v24);
    v15 = 0;
    v8 = *((_QWORD *)this + 4);
    *((_QWORD *)this + 4) = v5;
    if ( v8 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 8LL))(v8, 1);
    AggregatedTokenRequest::UpdateContext(this, (const struct AggregatedTokenRequest::RealmInfo *)v16);
    v9 = v12 - 6;
    if ( _InterlockedExchangeAdd(v12 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v9 + 8LL))(*(_QWORD *)v9);
    AggregatedTokenRequest::RealmInfo::~RealmInfo((AggregatedTokenRequest::RealmInfo *)v16);
  }
  catch ( const Exception *v18 )
  {
    v10 = (FailedTokenRequest *)operator new(
                                  0x38u,
                                  1,
                                  "onecore\\ds\\security\\dsreg\\win32\\adal.native\\aggregatedtokenrequest.cpp");
    v24 = v10;
    if ( v10 )
      v10 = FailedTokenRequest::FailedTokenRequest(v10, this, v18);
    v11 = std::unique_ptr<TokenRequest>::unique_ptr<TokenRequest>(&v23, (__int64)v10);
    std::unique_ptr<TokenRequest>::operator=<std::default_delete<TokenRequest>,0>((__int64 *)this + 4, v11);
    std::unique_ptr<TokenRequest>::~unique_ptr<TokenRequest>((__int64 *)&v23);
    throw;
  }
}

```

## disassembly

```asm
0x14000b4f4  mov     [rsp+arg_0], rcx
0x14000b4f9  push    rbx
0x14000b4fa  push    rsi
0x14000b4fb  push    rdi
0x14000b4fc  push    r14
0x14000b4fe  push    r15
0x14000b500  sub     rsp, 0C0h
0x14000b507  mov     rdi, rdx
0x14000b50a  mov     rbx, rcx
0x14000b50d  lea     rdx, aAggregatedtoke_6; "AggregatedTokenRequest::UseWindowsInteg"...
0x14000b514  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x14000b519  xor     r15d, r15d
0x14000b51c  cmp     [rbx+20h], r15
0x14000b520  jnz     loc_14000B78B
0x14000b526  test    rdi, rdi
0x14000b529  jz      loc_14000B755
0x14000b52f  cmp     [rdi], r15w
0x14000b533  jz      loc_14000B755
0x14000b539  mov     r8, rdi
0x14000b53c  lea     rdx, [rsp+0E8h+var_98]
0x14000b541  mov     rcx, rbx
0x14000b544  call    ?GetRealmInfo@AggregatedTokenRequest@@AEAA?AURealmInfo@1@PEBG@Z; AggregatedTokenRequest::GetRealmInfo(ushort const *)
0x14000b549  nop
0x14000b54a  lea     rdx, aAggregatedtoke_5; "AggregatedTokenRequest::UseWindowsInteg"...
0x14000b551  mov     rcx, rbx; struct ILogContext *
0x14000b554  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x14000b559  cmp     [rsp+0E8h+var_98], 2
0x14000b55e  jnz     loc_14000B7B2
0x14000b564  mov     r9d, 0B0h; int
0x14000b56a  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14000b571  mov     edx, 1; int
0x14000b576  lea     ecx, [r9-20h]; unsigned __int64
0x14000b57a  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x14000b57f  mov     rdi, rax
0x14000b582  mov     [rsp+0E8h+arg_10], rax
0x14000b58a  test    rax, rax
0x14000b58d  jz      short loc_14000B5AF
0x14000b58f  lea     r9, [rbx+18h]
0x14000b593  lea     r8, [rbx+10h]
0x14000b597  mov     rdx, [rbx+8]
0x14000b59b  mov     rcx, rax
0x14000b59e  call    ??0OAuthTokenRequestBase@@QEAA@PEAVAuthenticationContext@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1@Z; OAuthTokenRequestBase::OAuthTokenRequestBase(AuthenticationContext *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000b5a3  lea     rax, ??_7WSTrustTokenRequest@@6B@; const WSTrustTokenRequest::`vftable'
0x14000b5aa  mov     [rdi], rax
0x14000b5ad  jmp     short loc_14000B5B2
0x14000b5af  mov     rdi, r15
0x14000b5b2  mov     [rsp+0E8h+var_A0], rdi
0x14000b5b7  lea     rdx, [rsp+0E8h+var_B8]
0x14000b5bc  mov     rcx, rbx; struct ILogContext *
0x14000b5bf  call    ?GetAppliesTo@AggregatedTokenRequest@@AEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; AggregatedTokenRequest::GetAppliesTo(void)
0x14000b5c4  nop
0x14000b5c5  lea     rax, [rsp+0E8h+var_B0]
0x14000b5ca  mov     [rsp+0E8h+var_78], rax
0x14000b5cf  lea     rdx, [rsp+0E8h+var_B8]
0x14000b5d4  lea     rcx, [rsp+0E8h+var_B0]
0x14000b5d9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000b5de  mov     r14, rax
0x14000b5e1  lea     rax, [rsp+0E8h+var_A8]
0x14000b5e6  mov     [rsp+0E8h+var_70], rax
0x14000b5eb  lea     rdx, [rsp+0E8h+var_80]
0x14000b5f0  lea     rcx, [rsp+0E8h+var_A8]
0x14000b5f5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000b5fa  mov     rsi, rax
0x14000b5fd  mov     rcx, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000b604  mov     rax, [rcx+18h]
0x14000b608  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000b60f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b614  add     rax, 18h
0x14000b618  mov     [rsp+0E8h+arg_18], rax
0x14000b620  lea     rdx, dword_14003353C
0x14000b627  lea     rcx, [rsp+0E8h+arg_18]
0x14000b62f  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14000b634  test    al, al
0x14000b636  jnz     short loc_14000B650
0x14000b638  xor     r8d, r8d
0x14000b63b  lea     rdx, dword_14003353C
0x14000b642  lea     rcx, [rsp+0E8h+arg_18]
0x14000b64a  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000b64f  nop
0x14000b650  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000b657  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000b65e  mov     rax, [rax+18h]
0x14000b662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b667  add     rax, 18h
0x14000b66b  mov     [rsp+0E8h+arg_10], rax
0x14000b673  lea     rdx, dword_14003353C
0x14000b67a  lea     rcx, [rsp+0E8h+arg_10]
0x14000b682  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14000b687  test    al, al
0x14000b689  jnz     short loc_14000B6A3
0x14000b68b  xor     r8d, r8d
0x14000b68e  lea     rdx, dword_14003353C
0x14000b695  lea     rcx, [rsp+0E8h+arg_10]
0x14000b69d  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000b6a2  nop
0x14000b6a3  mov     [rsp+0E8h+var_C0], 1
0x14000b6a8  mov     [rsp+0E8h+var_C8], r14
0x14000b6ad  mov     r9, rsi
0x14000b6b0  lea     r8, [rsp+0E8h+arg_18]
0x14000b6b8  lea     rdx, [rsp+0E8h+arg_10]
0x14000b6c0  mov     rcx, rdi
0x14000b6c3  call    ?AcquireToken@WSTrustTokenRequest@@QEAA_NAEBVCSecureString@@0V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1_N@Z; WSTrustTokenRequest::AcquireToken(CSecureString const &,CSecureString const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,bool)
0x14000b6c8  nop
0x14000b6c9  lea     rcx, [rsp+0E8h+arg_10]; this
0x14000b6d1  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x14000b6d6  nop
0x14000b6d7  lea     rcx, [rsp+0E8h+arg_18]; this
0x14000b6df  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x14000b6e4  mov     [rsp+0E8h+var_A0], r15
0x14000b6e9  mov     rcx, [rbx+20h]
0x14000b6ed  mov     [rbx+20h], rdi
0x14000b6f1  test    rcx, rcx
0x14000b6f4  jz      short loc_14000B707
0x14000b6f6  mov     rax, [rcx]
0x14000b6f9  mov     edx, 1
0x14000b6fe  mov     rax, [rax+8]
0x14000b702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b707  lea     rdx, [rsp+0E8h+var_98]; struct AggregatedTokenRequest::RealmInfo *
0x14000b70c  mov     rcx, rbx; this
0x14000b70f  call    ?UpdateContext@AggregatedTokenRequest@@AEAAXAEBURealmInfo@1@@Z; AggregatedTokenRequest::UpdateContext(AggregatedTokenRequest::RealmInfo const &)
0x14000b714  nop
0x14000b715  mov     rdx, [rsp+0E8h+var_B8]
0x14000b71a  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000b71e  or      eax, 0FFFFFFFFh
0x14000b721  lock xadd [rdx+10h], eax
0x14000b726  sub     eax, 1
0x14000b729  jg      short loc_14000B73B
0x14000b72b  mov     rcx, [rdx]
0x14000b72e  mov     rax, [rcx]
0x14000b731  mov     rax, [rax+8]
0x14000b735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b73a  nop
0x14000b73b  lea     rcx, [rsp+0E8h+var_98]; this
0x14000b740  call    ??1RealmInfo@AggregatedTokenRequest@@QEAA@XZ; AggregatedTokenRequest::RealmInfo::~RealmInfo(void)
0x14000b745  nop
0x14000b746  add     rsp, 0C0h
0x14000b74d  pop     r15
0x14000b74f  pop     r14
0x14000b751  pop     rdi
0x14000b752  pop     rsi
0x14000b753  pop     rbx
0x14000b754  retn
0x14000b755  lea     rdx, aErrorTenantnam; "Error, tenantName MUST be provided."
0x14000b75c  mov     rcx, rbx; struct ILogContext *
0x14000b75f  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x14000b764  mov     edx, 80070057h; unsigned int
0x14000b769  lea     rcx, [rsp+0E8h+pExceptionObject]; this
0x14000b771  call    ??0InvalidCallException@@QEAA@K@Z; InvalidCallException::InvalidCallException(ulong)
0x14000b776  lea     rdx, _TI3?AVInvalidCallException@@; pThrowInfo
0x14000b77d  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x14000b785  call    _CxxThrowException_0
0x14000b78b  mov     edx, 0CAA10037h; unsigned int
0x14000b790  lea     rcx, [rsp+0E8h+var_60]; this
0x14000b798  call    ??0InvalidCallException@@QEAA@K@Z; InvalidCallException::InvalidCallException(ulong)
0x14000b79d  lea     rdx, _TI3?AVInvalidCallException@@; pThrowInfo
0x14000b7a4  lea     rcx, [rsp+0E8h+var_60]; pExceptionObject
0x14000b7ac  call    _CxxThrowException_0
0x14000b7b2  mov     edx, 0CAA9001Fh; unsigned int
0x14000b7b7  lea     rcx, [rsp+0E8h+var_50]; this
0x14000b7bf  call    ??0InvalidCallException@@QEAA@K@Z; InvalidCallException::InvalidCallException(ulong)
0x14000b7c4  lea     rdx, _TI3?AVInvalidCallException@@; pThrowInfo
0x14000b7cb  lea     rcx, [rsp+0E8h+var_50]; pExceptionObject
0x14000b7d3  call    _CxxThrowException_0
```
