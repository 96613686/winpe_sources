# AggregatedTokenRequest::AcquireToken(void)

- ea: `0x14000a34c`
- end: `0x14000a5af`
- name: `?AcquireToken@AggregatedTokenRequest@@QEAA_NXZ`
- size: `611`
- prototype: `char __fastcall(AggregatedTokenRequest *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140007d8c`

## callees

- `0x140001814`
- `0x14000579c`
- `0x140008a5c`
- `0x14000a34c`
- `0x14000c7d8`
- `0x140015dfc`
- `0x14001604c`
- `0x140030010`

## string_xrefs

- `0x14000a35b`: `AggregatedTokenRequest::AcquireToken get refresh token info`
- `0x14000a39a`: `AggregatedTokenRequest::AcquireToken- Sending Refresh request`
- `0x14000a3af`: `onecore\ds\security\dsreg\win32\adal.native\aggregatedtokenrequest.cpp`
- `0x14000a3fc`: `AggregatedTokenRequest::AcquireToken: token is received`
- `0x14000a441`: `AggregatedTokenRequest::AcquireToken: token is not received`
- `0x14000a57c`: `AggregatedTokenRequest::AcquireToken- refresh token is not available`
- `0x14000a58b`: `AggregatedTokenRequest::AcquireToken- returns false`

## pseudocode

```c
char __fastcall AggregatedTokenRequest::AcquireToken(AggregatedTokenRequest *this)
{
  void *v2; // rax
  RefreshTokenRequest *refreshed; // rdi
  __int64 v4; // rcx
  __int64 v6; // rcx
  __int64 v7; // rsi
  _QWORD *v8; // rax
  _QWORD *v9; // rdx
  _QWORD *v10; // rdx
  __int64 v11; // rcx
  _QWORD v12[6]; // [rsp+28h] [rbp-30h] BYREF
  __int64 v13; // [rsp+70h] [rbp+18h] BYREF
  __int64 v14; // [rsp+78h] [rbp+20h] BYREF

  Log::Verbose(this, L"AggregatedTokenRequest::AcquireToken get refresh token info");
  AuthenticationContext::GetRefreshTokenInfo(*((_QWORD *)this + 1), v12, *((_QWORD *)this + 2));
  if ( (*(_BYTE *)(*((_QWORD *)this + 1) + 296LL) & 8) != 0 || !*(_DWORD *)(v12[0] - 16LL) )
  {
    Log::Verbose(this, L"AggregatedTokenRequest::AcquireToken- refresh token is not available");
LABEL_21:
    Log::Verbose(this, L"AggregatedTokenRequest::AcquireToken- returns false");
    CSecureString::~CSecureString((CSecureString *)v12);
    return 0;
  }
  Log::Verbose(this, L"AggregatedTokenRequest::AcquireToken- Sending Refresh request");
  v2 = operator new(0x98u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\aggregatedtokenrequest.cpp");
  if ( v2 )
    refreshed = (RefreshTokenRequest *)RefreshTokenRequest::RefreshTokenRequest(
                                         (__int64)v2,
                                         *((_QWORD *)this + 1),
                                         (__int64)this + 16,
                                         (__int64)this + 24);
  else
    refreshed = 0;
  if ( RefreshTokenRequest::AcquireToken(refreshed) )
  {
    Log::Verbose(this, L"AggregatedTokenRequest::AcquireToken: token is received");
    v4 = *((_QWORD *)this + 4);
    *((_QWORD *)this + 4) = refreshed;
    if ( v4 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 8LL))(v4, 1);
    CSecureString::~CSecureString((CSecureString *)v12);
    return 1;
  }
  Log::Verbose(this, L"AggregatedTokenRequest::AcquireToken: token is not received");
  if ( !*((_BYTE *)refreshed + 136) )
  {
    v7 = *(_QWORD *)(*(__int64 (__fastcall **)(RefreshTokenRequest *, __int64 *))(*(_QWORD *)refreshed + 32LL))(
                      refreshed,
                      &v14);
    v8 = (_QWORD *)(*(__int64 (__fastcall **)(RefreshTokenRequest *, __int64 *))(*(_QWORD *)refreshed + 40LL))(
                     refreshed,
                     &v13);
    Log::Verbose(this, L"Refresh request errorcode:%s description:%s", *v8, v7);
    v9 = (_QWORD *)(v13 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v13 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 8LL))(*v9);
    v10 = (_QWORD *)(v14 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v14 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 8LL))(*v10);
    v11 = *((_QWORD *)this + 4);
    *((_QWORD *)this + 4) = refreshed;
    if ( v11 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 8LL))(v11, 1);
    goto LABEL_21;
  }
  Log::Verbose(this, L"Fatal network error returned");
  v6 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = refreshed;
  if ( v6 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 8LL))(v6, 1);
  CSecureString::~CSecureString((CSecureString *)v12);
  return 0;
}

```

## disassembly

```asm
0x14000a34c  mov     [rsp+arg_0], rcx
0x14000a351  push    rbx
0x14000a352  push    rsi
0x14000a353  push    rdi
0x14000a354  sub     rsp, 40h
0x14000a358  mov     rbx, rcx
0x14000a35b  lea     rdx, aAggregatedtoke_4; "AggregatedTokenRequest::AcquireToken ge"...
0x14000a362  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x14000a367  mov     r8, [rbx+10h]
0x14000a36b  lea     rdx, [rsp+58h+var_30]
0x14000a370  mov     rcx, [rbx+8]
0x14000a374  call    ?GetRefreshTokenInfo@AuthenticationContext@@QEAA?AURefreshTokenInfo@@PEBG@Z; AuthenticationContext::GetRefreshTokenInfo(ushort const *)
0x14000a379  nop
0x14000a37a  mov     rax, [rbx+8]
0x14000a37e  test    byte ptr [rax+128h], 8
0x14000a385  jnz     loc_14000A57C
0x14000a38b  mov     rax, [rsp+58h+var_30]
0x14000a390  cmp     dword ptr [rax-10h], 0
0x14000a394  jz      loc_14000A57C
0x14000a39a  lea     rdx, aAggregatedtoke_3; "AggregatedTokenRequest::AcquireToken- S"...
0x14000a3a1  mov     rcx, rbx; struct ILogContext *
0x14000a3a4  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x14000a3a9  mov     r9d, 2Ah ; '*'; int
0x14000a3af  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14000a3b6  lea     edx, [r9-29h]; int
0x14000a3ba  lea     ecx, [r9+6Eh]; unsigned __int64
0x14000a3be  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x14000a3c3  mov     [rsp+58h+arg_8], rax
0x14000a3c8  test    rax, rax
0x14000a3cb  jz      short loc_14000A3E6
0x14000a3cd  lea     r9, [rbx+18h]
0x14000a3d1  lea     r8, [rbx+10h]
0x14000a3d5  mov     rdx, [rbx+8]
0x14000a3d9  mov     rcx, rax
0x14000a3dc  call    ??0RefreshTokenRequest@@QEAA@PEAVAuthenticationContext@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1@Z; RefreshTokenRequest::RefreshTokenRequest(AuthenticationContext *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000a3e1  mov     rdi, rax
0x14000a3e4  jmp     short loc_14000A3E8
0x14000a3e6  xor     edi, edi
0x14000a3e8  mov     [rsp+58h+arg_8], rdi
0x14000a3ed  mov     rcx, rdi; this
0x14000a3f0  call    ?AcquireToken@RefreshTokenRequest@@QEAA_NXZ; RefreshTokenRequest::AcquireToken(void)
0x14000a3f5  mov     rcx, rbx; struct ILogContext *
0x14000a3f8  test    al, al
0x14000a3fa  jz      short loc_14000A441
0x14000a3fc  lea     rdx, aAggregatedtoke_8; "AggregatedTokenRequest::AcquireToken: t"...
0x14000a403  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x14000a408  mov     [rsp+58h+arg_8], 0
0x14000a411  mov     rcx, [rbx+20h]
0x14000a415  mov     [rbx+20h], rdi
0x14000a419  test    rcx, rcx
0x14000a41c  jz      short loc_14000A430
0x14000a41e  mov     rax, [rcx]
0x14000a421  mov     edx, 1
0x14000a426  mov     rax, [rax+8]
0x14000a42a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a42f  nop
0x14000a430  lea     rcx, [rsp+58h+var_30]; this
0x14000a435  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x14000a43a  mov     al, 1
0x14000a43c  jmp     loc_14000A5A7
0x14000a441  lea     rdx, aAggregatedtoke_7; "AggregatedTokenRequest::AcquireToken: t"...
0x14000a448  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x14000a44d  cmp     byte ptr [rdi+88h], 0
0x14000a454  jz      short loc_14000A49E
0x14000a456  lea     rdx, aFatalNetworkEr; "Fatal network error returned"
0x14000a45d  mov     rcx, rbx; struct ILogContext *
0x14000a460  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x14000a465  mov     [rsp+58h+arg_8], 0
0x14000a46e  mov     rcx, [rbx+20h]
0x14000a472  mov     [rbx+20h], rdi
0x14000a476  test    rcx, rcx
0x14000a479  jz      short loc_14000A48D
0x14000a47b  mov     rax, [rcx]
0x14000a47e  mov     edx, 1
0x14000a483  mov     rax, [rax+8]
0x14000a487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a48c  nop
0x14000a48d  lea     rcx, [rsp+58h+var_30]; this
0x14000a492  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x14000a497  xor     al, al
0x14000a499  jmp     loc_14000A5A7
0x14000a49e  mov     rax, [rdi]
0x14000a4a1  lea     rdx, [rsp+58h+arg_18]
0x14000a4a6  mov     rcx, rdi
0x14000a4a9  mov     rax, [rax+20h]
0x14000a4ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a4b2  nop
0x14000a4b3  mov     rsi, [rax]
0x14000a4b6  mov     rax, [rdi]
0x14000a4b9  lea     rdx, [rsp+58h+arg_10]
0x14000a4be  mov     rcx, rdi
0x14000a4c1  mov     rax, [rax+28h]
0x14000a4c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a4ca  nop
0x14000a4cb  mov     r9, rsi
0x14000a4ce  mov     r8, [rax]
0x14000a4d1  lea     rdx, aRefreshRequest; "Refresh request errorcode:%s descriptio"...
0x14000a4d8  mov     rcx, rbx; struct ILogContext *
0x14000a4db  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x14000a4e0  nop
0x14000a4e1  mov     rdx, [rsp+58h+arg_10]
0x14000a4e6  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000a4ea  or      esi, 0FFFFFFFFh
0x14000a4ed  mov     eax, esi
0x14000a4ef  lock xadd [rdx+10h], eax
0x14000a4f4  add     eax, esi
0x14000a4f6  test    eax, eax
0x14000a4f8  jg      short loc_14000A50A
0x14000a4fa  mov     rcx, [rdx]
0x14000a4fd  mov     rax, [rcx]
0x14000a500  mov     rax, [rax+8]
0x14000a504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a509  nop
0x14000a50a  mov     rdx, [rsp+58h+arg_18]
0x14000a50f  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000a513  mov     eax, esi
0x14000a515  lock xadd [rdx+10h], eax
0x14000a51a  add     eax, esi
0x14000a51c  test    eax, eax
0x14000a51e  jg      short loc_14000A52F
0x14000a520  mov     rcx, [rdx]
0x14000a523  mov     rax, [rcx]
0x14000a526  mov     rax, [rax+8]
0x14000a52a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a52f  xor     esi, esi
0x14000a531  mov     [rsp+58h+arg_8], rsi
0x14000a536  mov     rcx, [rbx+20h]
0x14000a53a  mov     [rbx+20h], rdi
0x14000a53e  test    rcx, rcx
0x14000a541  jz      short loc_14000A553
0x14000a543  mov     rax, [rcx]
0x14000a546  lea     edx, [rsi+1]
0x14000a549  mov     rax, [rax+8]
0x14000a54d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a552  nop
0x14000a553  jmp     short loc_14000A561
0x14000a555  jmp     short loc_14000A59B
0x14000a557  mov     rbx, [rsp+58h+arg_0]
0x14000a55c  mov     rsi, [rsp+58h+arg_8]
0x14000a561  test    rsi, rsi
0x14000a564  jz      short loc_14000A58B
0x14000a566  mov     rax, [rsi]
0x14000a569  mov     edx, 1
0x14000a56e  mov     rcx, rsi
0x14000a571  mov     rax, [rax+8]
0x14000a575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a57a  jmp     short loc_14000A58B
0x14000a57c  lea     rdx, aAggregatedtoke_0; "AggregatedTokenRequest::AcquireToken- r"...
0x14000a583  mov     rcx, rbx; struct ILogContext *
0x14000a586  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x14000a58b  lea     rdx, aAggregatedtoke; "AggregatedTokenRequest::AcquireToken- r"...
0x14000a592  mov     rcx, rbx; struct ILogContext *
0x14000a595  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x14000a59a  nop
0x14000a59b  lea     rcx, [rsp+58h+var_30]; this
0x14000a5a0  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x14000a5a5  xor     al, al
0x14000a5a7  add     rsp, 40h
0x14000a5ab  pop     rdi
0x14000a5ac  pop     rsi
0x14000a5ad  pop     rbx
0x14000a5ae  retn
```
