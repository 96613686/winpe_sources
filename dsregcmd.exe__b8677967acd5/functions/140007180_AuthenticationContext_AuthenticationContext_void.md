# AuthenticationContext::AuthenticationContext(void)

- ea: `0x140007180`
- end: `0x14000758a`
- name: `??0AuthenticationContext@@QEAA@XZ`
- size: `1034`
- prototype: `AuthenticationContext *__fastcall(AuthenticationContext *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140006818`

## callees

- `0x1400017d4`
- `0x140001814`
- `0x140007180`
- `0x140009818`
- `0x14000e548`
- `0x140030010`

## string_xrefs

- `0x140007427`: `onecore\ds\security\dsreg\win32\adal.native\authenticationcontext.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
AuthenticationContext *__fastcall AuthenticationContext::AuthenticationContext(AuthenticationContext *this)
{
  int v2; // r11d
  int v3; // r10d
  int v4; // r9d
  IdToken *v5; // rax
  IdToken *v6; // rdi
  _DWORD *v7; // rax

  *(_QWORD *)this = &AuthenticationContext::`vftable';
  *((_QWORD *)this + 1) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 2) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 3) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 4) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 5) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 6) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 7) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 8) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 9) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 10) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 11) = &TokenCache::`vftable';
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 28) = 17;
  *((_QWORD *)this + 16) = 0xFFFFFFFFLL;
  *((_QWORD *)this + 17) = 0;
  *((_DWORD *)this + 36) = 0;
  *((_DWORD *)this + 37) = 10;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_DWORD *)this + 29) = 1061158912;
  *((_DWORD *)this + 30) = 1048576000;
  *((_DWORD *)this + 31) = 1074790400;
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::UpdateRehashThresholds();
  *((_QWORD *)this + 21) = &TokenCache::`vftable';
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_DWORD *)this + 48) = 17;
  *((_QWORD *)this + 26) = 0xFFFFFFFFLL;
  *((_QWORD *)this + 27) = 0;
  *((_DWORD *)this + 56) = 0;
  *((_DWORD *)this + 57) = 10;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_DWORD *)this + 49) = v2;
  *((_DWORD *)this + 50) = v3;
  *((_DWORD *)this + 51) = v4;
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::UpdateRehashThresholds();
  *((_QWORD *)this + 21) = &RefreshTokenCache::`vftable';
  *((_QWORD *)this + 31) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 32) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 33) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 34) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 35) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 36) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v5 = (IdToken *)operator new(
                    0x50u,
                    1,
                    "onecore\\ds\\security\\dsreg\\win32\\adal.native\\authenticationcontext.cpp",
                    43);
  if ( v5 )
    v6 = IdToken::IdToken(v5);
  else
    v6 = 0;
  *((_QWORD *)this + 38) = 0;
  *((_QWORD *)this + 39) = 0;
  v7 = operator new(0x18u);
  if ( v7 )
  {
    *(_OWORD *)v7 = 0;
    v7[2] = 1;
    v7[3] = 1;
    *(_QWORD *)v7 = &std::_Ref_count<IdToken>::`vftable';
    *((_QWORD *)v7 + 2) = v6;
  }
  else
  {
    v7 = 0;
  }
  *((_QWORD *)this + 38) = v6;
  *((_QWORD *)this + 39) = v7;
  *((_QWORD *)this + 40) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 41) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 42) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 43) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 44) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 45) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 37) = 3;
  _InterlockedIncrement((volatile signed __int32 *)&WebSessionManager::s_RefCount);
  return this;
}

```

## disassembly

```asm
0x140007180  mov     [rsp+arg_10], rbx
0x140007185  mov     [rsp+arg_0], rcx
0x14000718a  push    rbp
0x14000718b  push    rdi
0x14000718c  push    r12
0x14000718e  push    r14
0x140007190  push    r15
0x140007192  sub     rsp, 20h
0x140007196  mov     rbx, rcx
0x140007199  lea     rax, ??_7AuthenticationContext@@6B@; const AuthenticationContext::`vftable'
0x1400071a0  mov     [rcx], rax
0x1400071a3  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400071aa  lea     r12, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400071b1  mov     rcx, r12
0x1400071b4  mov     rax, [rax+18h]
0x1400071b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400071bd  add     rax, 18h
0x1400071c1  mov     [rbx+8], rax
0x1400071c5  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400071cc  mov     rcx, r12
0x1400071cf  mov     rax, [rax+18h]
0x1400071d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400071d8  add     rax, 18h
0x1400071dc  mov     [rbx+10h], rax
0x1400071e0  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400071e7  mov     rcx, r12
0x1400071ea  mov     rax, [rax+18h]
0x1400071ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400071f3  add     rax, 18h
0x1400071f7  mov     [rbx+18h], rax
0x1400071fb  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140007202  mov     rcx, r12
0x140007205  mov     rax, [rax+18h]
0x140007209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000720e  add     rax, 18h
0x140007212  mov     [rbx+20h], rax
0x140007216  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000721d  mov     rcx, r12
0x140007220  mov     rax, [rax+18h]
0x140007224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007229  add     rax, 18h
0x14000722d  mov     [rbx+28h], rax
0x140007231  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140007238  mov     rcx, r12
0x14000723b  mov     rax, [rax+18h]
0x14000723f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007244  add     rax, 18h
0x140007248  mov     [rbx+30h], rax
0x14000724c  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140007253  mov     rcx, r12
0x140007256  mov     rax, [rax+18h]
0x14000725a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000725f  add     rax, 18h
0x140007263  mov     [rbx+38h], rax
0x140007267  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000726e  mov     rcx, r12
0x140007271  mov     rax, [rax+18h]
0x140007275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000727a  add     rax, 18h
0x14000727e  mov     [rbx+40h], rax
0x140007282  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140007289  mov     rcx, r12
0x14000728c  mov     rax, [rax+18h]
0x140007290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007295  add     rax, 18h
0x140007299  mov     [rbx+48h], rax
0x14000729d  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400072a4  mov     rcx, r12
0x1400072a7  mov     rax, [rax+18h]
0x1400072ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400072b0  add     rax, 18h
0x1400072b4  mov     [rbx+50h], rax
0x1400072b8  lea     r14, ??_7TokenCache@@6B@; const TokenCache::`vftable'
0x1400072bf  mov     [rbx+58h], r14
0x1400072c3  lea     rcx, [rbx+60h]
0x1400072c7  xor     r15d, r15d
0x1400072ca  mov     [rcx], r15
0x1400072cd  mov     [rcx+8], r15
0x1400072d1  mov     dword ptr [rcx+10h], 11h
0x1400072d8  mov     ebp, 0FFFFFFFFh
0x1400072dd  mov     [rcx+20h], rbp
0x1400072e1  mov     [rcx+28h], r15
0x1400072e5  mov     [rcx+30h], r15d
0x1400072e9  lea     edi, [r15+0Ah]
0x1400072ed  mov     [rcx+34h], edi
0x1400072f0  mov     [rcx+38h], r15
0x1400072f4  mov     [rcx+40h], r15
0x1400072f8  mov     r11d, 3F400000h
0x1400072fe  mov     [rcx+14h], r11d
0x140007302  mov     r10d, 3E800000h
0x140007308  mov     [rcx+18h], r10d
0x14000730c  mov     r9d, 40100000h
0x140007312  mov     [rcx+1Ch], r9d
0x140007316  call    ?UpdateRehashThresholds@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UPolicyInfo@WSTrustMEX@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@UPolicyInfo@WSTrustMEX@@@2@@ATL@@AEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::UpdateRehashThresholds(void)
0x14000731b  nop
0x14000731c  mov     [rbx+0A8h], r14
0x140007323  lea     rcx, [rbx+0B0h]
0x14000732a  mov     [rcx], r15
0x14000732d  mov     [rcx+8], r15
0x140007331  mov     dword ptr [rcx+10h], 11h
0x140007338  mov     [rcx+20h], rbp
0x14000733c  mov     [rcx+28h], r15
0x140007340  mov     [rcx+30h], r15d
0x140007344  mov     [rcx+34h], edi
0x140007347  mov     [rcx+38h], r15
0x14000734b  mov     [rcx+40h], r15
0x14000734f  mov     [rcx+14h], r11d
0x140007353  mov     [rcx+18h], r10d
0x140007357  mov     [rcx+1Ch], r9d
0x14000735b  call    ?UpdateRehashThresholds@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UPolicyInfo@WSTrustMEX@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@UPolicyInfo@WSTrustMEX@@@2@@ATL@@AEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::UpdateRehashThresholds(void)
0x140007360  nop
0x140007361  lea     rax, ??_7RefreshTokenCache@@6B@; const RefreshTokenCache::`vftable'
0x140007368  mov     [rbx+0A8h], rax
0x14000736f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140007376  mov     rcx, r12
0x140007379  mov     rax, [rax+18h]
0x14000737d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007382  add     rax, 18h
0x140007386  mov     [rbx+0F8h], rax
0x14000738d  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140007394  mov     rcx, r12
0x140007397  mov     rax, [rax+18h]
0x14000739b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400073a0  add     rax, 18h
0x1400073a4  mov     [rbx+100h], rax
0x1400073ab  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400073b2  mov     rcx, r12
0x1400073b5  mov     rax, [rax+18h]
0x1400073b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400073be  add     rax, 18h
0x1400073c2  mov     [rbx+108h], rax
0x1400073c9  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400073d0  mov     rcx, r12
0x1400073d3  mov     rax, [rax+18h]
0x1400073d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400073dc  add     rax, 18h
0x1400073e0  mov     [rbx+110h], rax
0x1400073e7  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400073ee  mov     rcx, r12
0x1400073f1  mov     rax, [rax+18h]
0x1400073f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400073fa  add     rax, 18h
0x1400073fe  mov     [rbx+118h], rax
0x140007405  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000740c  mov     rcx, r12
0x14000740f  mov     rax, [rax+18h]
0x140007413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007418  add     rax, 18h
0x14000741c  mov     [rbx+120h], rax
0x140007423  lea     r9d, [r15+2Bh]; int
0x140007427  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14000742e  lea     edx, [rdi-9]; int
0x140007431  lea     ecx, [rdi+46h]; unsigned __int64
0x140007434  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x140007439  mov     [rsp+48h+arg_8], rax
0x14000743e  test    rax, rax
0x140007441  jz      short loc_140007450
0x140007443  mov     rcx, rax; this
0x140007446  call    ??0IdToken@@QEAA@XZ; IdToken::IdToken(void)
0x14000744b  mov     rdi, rax
0x14000744e  jmp     short loc_140007453
0x140007450  mov     rdi, r15
0x140007453  mov     [rbx+130h], r15
0x14000745a  mov     [rbx+138h], r15
0x140007461  mov     [rsp+48h+arg_8], rdi
0x140007466  mov     ecx, 18h; Size
0x14000746b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007470  mov     [rsp+48h+arg_0], rax
0x140007475  test    rax, rax
0x140007478  jz      short loc_14000749E
0x14000747a  xorps   xmm0, xmm0
0x14000747d  movups  xmmword ptr [rax], xmm0
0x140007480  mov     dword ptr [rax+8], 1
0x140007487  mov     dword ptr [rax+0Ch], 1
0x14000748e  lea     rcx, ??_7?$_Ref_count@VIdToken@@@std@@6B@; const std::_Ref_count<IdToken>::`vftable'
0x140007495  mov     [rax], rcx
0x140007498  mov     [rax+10h], rdi
0x14000749c  jmp     short loc_1400074A1
0x14000749e  mov     rax, r15
0x1400074a1  mov     [rbx+130h], rdi
0x1400074a8  mov     [rbx+138h], rax
0x1400074af  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400074b6  mov     rcx, r12
0x1400074b9  mov     rax, [rax+18h]
0x1400074bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400074c2  add     rax, 18h
0x1400074c6  mov     [rbx+140h], rax
0x1400074cd  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400074d4  mov     rcx, r12
0x1400074d7  mov     rax, [rax+18h]
0x1400074db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400074e0  add     rax, 18h
0x1400074e4  mov     [rbx+148h], rax
0x1400074eb  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400074f2  mov     rcx, r12
0x1400074f5  mov     rax, [rax+18h]
0x1400074f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400074fe  add     rax, 18h
0x140007502  mov     [rbx+150h], rax
0x140007509  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140007510  mov     rcx, r12
0x140007513  mov     rax, [rax+18h]
0x140007517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000751c  add     rax, 18h
0x140007520  mov     [rbx+158h], rax
0x140007527  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000752e  mov     rcx, r12
0x140007531  mov     rax, [rax+18h]
0x140007535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000753a  add     rax, 18h
0x14000753e  mov     [rbx+160h], rax
0x140007545  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000754c  mov     rcx, r12
0x14000754f  mov     rax, [rax+18h]
0x140007553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007558  add     rax, 18h
0x14000755c  mov     [rbx+168h], rax
0x140007563  mov     qword ptr [rbx+128h], 3
0x14000756e  lock inc cs:?s_RefCount@WebSessionManager@@0KC; ulong volatile WebSessionManager::s_RefCount
0x140007575  mov     rax, rbx
0x140007578  mov     rbx, [rsp+48h+arg_10]
0x14000757d  add     rsp, 20h
0x140007581  pop     r15
0x140007583  pop     r14
0x140007585  pop     r12
0x140007587  pop     rdi
0x140007588  pop     rbp
0x140007589  retn
```
