# RefreshTokenRequest::RefreshTokenRequest(AuthenticationContext *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x140015dfc`
- end: `0x140015f23`
- name: `??0RefreshTokenRequest@@QEAA@PEAVAuthenticationContext@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1@Z`
- size: `295`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000a34c`

## callees

- `0x140001814`
- `0x1400028ac`
- `0x14000579c`
- `0x1400061dc`
- `0x140007bf8`
- `0x140008a5c`
- `0x14001425c`
- `0x140015dfc`
- `0x140025bd4`
- `0x140030010`

## string_xrefs

- `0x140015e58`: `onecore\ds\security\dsreg\win32\adal.native\refreshtokenrequest.cpp`
- `0x140015ea1`: `onecore\ds\security\dsreg\win32\adal.native\challengeresponsebuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall RefreshTokenRequest::RefreshTokenRequest(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  _QWORD *v6; // rbx
  _QWORD *v7; // rax
  ChallengeResponseBuilder *v8; // rsi
  _BYTE v10[56]; // [rsp+30h] [rbp-38h] BYREF

  OAuthTokenRequestBase::OAuthTokenRequestBase(a1, a2, a3, a4);
  *(_QWORD *)a1 = &RefreshTokenRequest::`vftable';
  *(_QWORD *)(a1 + 144) = 0;
  AuthenticationContext::GetRefreshTokenInfo(*(_QWORD *)(a1 + 8), v10, *(_QWORD *)(a1 + 16));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    a1 + 48,
    v10);
  *(_BYTE *)(a1 + 56) = v10[8];
  v6 = operator new(0x18u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\refreshtokenrequest.cpp", 26);
  if ( v6 )
  {
    v6[1] = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    v6[2] = a2;
    v7 = operator new(8u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\challengeresponsebuilder.cpp", 25);
    if ( v7 )
      *v7 = v6[2];
    *v6 = v7;
    ATL::CSimpleStringT<unsigned short,0>::SetString(v6 + 1, L"SHA256", 6);
  }
  else
  {
    v6 = 0;
  }
  v8 = *(ChallengeResponseBuilder **)(a1 + 144);
  *(_QWORD *)(a1 + 144) = v6;
  if ( v8 )
  {
    ChallengeResponseBuilder::~ChallengeResponseBuilder(v8);
    operator delete(v8);
  }
  CSecureString::~CSecureString((CSecureString *)v10);
  return a1;
}

```

## disassembly

```asm
0x140015dfc  mov     [rsp+arg_0], rcx
0x140015e01  push    rbx
0x140015e02  push    rbp
0x140015e03  push    rsi
0x140015e04  push    rdi
0x140015e05  sub     rsp, 48h
0x140015e09  mov     rbp, rdx
0x140015e0c  mov     rdi, rcx
0x140015e0f  call    ??0OAuthTokenRequestBase@@QEAA@PEAVAuthenticationContext@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1@Z; OAuthTokenRequestBase::OAuthTokenRequestBase(AuthenticationContext *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140015e14  nop
0x140015e15  lea     rax, ??_7RefreshTokenRequest@@6B@; const RefreshTokenRequest::`vftable'
0x140015e1c  mov     [rdi], rax
0x140015e1f  mov     qword ptr [rdi+90h], 0
0x140015e2a  mov     r8, [rdi+10h]
0x140015e2e  lea     rdx, [rsp+68h+var_38]
0x140015e33  mov     rcx, [rdi+8]
0x140015e37  call    ?GetRefreshTokenInfo@AuthenticationContext@@QEAA?AURefreshTokenInfo@@PEBG@Z; AuthenticationContext::GetRefreshTokenInfo(ushort const *)
0x140015e3c  nop
0x140015e3d  lea     rcx, [rdi+30h]
0x140015e41  lea     rdx, [rsp+68h+var_38]
0x140015e46  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140015e4b  mov     al, [rsp+68h+var_30]
0x140015e4f  mov     [rdi+38h], al
0x140015e52  mov     r9d, 1Ah; int
0x140015e58  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x140015e5f  lea     edx, [r9-19h]; int
0x140015e63  lea     ecx, [rdx+17h]; unsigned __int64
0x140015e66  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x140015e6b  mov     rbx, rax
0x140015e6e  mov     [rsp+68h+var_48], rax
0x140015e73  test    rax, rax
0x140015e76  jz      short loc_140015EE1
0x140015e78  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140015e7f  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140015e86  mov     rax, [rax+18h]
0x140015e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015e8f  add     rax, 18h
0x140015e93  mov     [rbx+8], rax
0x140015e97  mov     [rbx+10h], rbp
0x140015e9b  mov     r9d, 19h; int
0x140015ea1  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x140015ea8  lea     edx, [r9-18h]; int
0x140015eac  lea     ecx, [rdx+7]; unsigned __int64
0x140015eaf  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x140015eb4  mov     [rsp+68h+var_40], rax
0x140015eb9  test    rax, rax
0x140015ebc  jz      short loc_140015EC5
0x140015ebe  mov     rcx, [rbx+10h]
0x140015ec2  mov     [rax], rcx
0x140015ec5  mov     [rbx], rax
0x140015ec8  mov     r8d, 6
0x140015ece  lea     rdx, aSha256; "SHA256"
0x140015ed5  lea     rcx, [rbx+8]
0x140015ed9  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140015ede  nop
0x140015edf  jmp     short loc_140015EE3
0x140015ee1  xor     ebx, ebx
0x140015ee3  mov     rsi, [rdi+90h]
0x140015eea  mov     [rdi+90h], rbx
0x140015ef1  test    rsi, rsi
0x140015ef4  jz      short loc_140015F0C
0x140015ef6  mov     rcx, rsi; this
0x140015ef9  call    ??1ChallengeResponseBuilder@@QEAA@XZ; ChallengeResponseBuilder::~ChallengeResponseBuilder(void)
0x140015efe  mov     edx, 18h
0x140015f03  mov     rcx, rsi; Block
0x140015f06  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x140015f0b  nop
0x140015f0c  lea     rcx, [rsp+68h+var_38]; this
0x140015f11  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x140015f16  nop
0x140015f17  mov     rax, rdi
0x140015f1a  add     rsp, 48h
0x140015f1e  pop     rdi
0x140015f1f  pop     rsi
0x140015f20  pop     rbp
0x140015f21  pop     rbx
0x140015f22  retn
```
