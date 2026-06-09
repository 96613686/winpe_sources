# OAuthTokenRequestBase::OAuthTokenRequestBase(AuthenticationContext *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x14001425c`
- end: `0x14001440d`
- name: `??0OAuthTokenRequestBase@@QEAA@PEAVAuthenticationContext@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1@Z`
- size: `433`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000b4f4`
- `0x14000b7e0`
- `0x140015dfc`

## callees

- `0x1400017d4`
- `0x140001814`
- `0x14000e040`
- `0x14000e548`
- `0x14001425c`
- `0x140030010`

## string_xrefs

- `0x140014333`: `onecore\ds\security\dsreg\win32\adal.native\oauthtokenrequestbase.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall OAuthTokenRequestBase::OAuthTokenRequestBase(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  IdToken *v5; // rax
  IdToken *v6; // rdi
  _DWORD *v7; // rax

  TokenRequest::TokenRequest(a1, a2, a3, a4);
  *(_QWORD *)a1 = &OAuthTokenRequestBase::`vftable';
  *(_QWORD *)(a1 + 32) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *(_QWORD *)(a1 + 48) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *(_QWORD *)(a1 + 64) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *(_QWORD *)(a1 + 72) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *(_QWORD *)(a1 + 88) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *(_QWORD *)(a1 + 96) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v5 = (IdToken *)operator new(
                    0x50u,
                    1,
                    "onecore\\ds\\security\\dsreg\\win32\\adal.native\\oauthtokenrequestbase.cpp",
                    21);
  if ( v5 )
    v6 = IdToken::IdToken(v5);
  else
    v6 = 0;
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  v7 = operator new(0x18u);
  if ( v7 )
  {
    *(_OWORD *)v7 = 0;
    v7[2] = 1;
    v7[3] = 1;
    *(_QWORD *)v7 = &std::_Ref_count<IdToken>::`vftable';
    *((_QWORD *)v7 + 2) = v6;
  }
  *(_QWORD *)(a1 + 104) = v6;
  *(_QWORD *)(a1 + 112) = v7;
  *(_QWORD *)(a1 + 128) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *(_BYTE *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_DWORD *)(a1 + 60) = 0;
  *(_BYTE *)(a1 + 56) = 0;
  *(_DWORD *)(a1 + 120) = 0;
  *(_BYTE *)(a1 + 124) = 0;
  *(_BYTE *)(a1 + 136) = 0;
  return a1;
}

```

## disassembly

```asm
0x14001425c  mov     [rsp+arg_8], rbx
0x140014261  mov     [rsp+arg_10], rdi
0x140014266  mov     [rsp+arg_0], rcx
0x14001426b  push    r14
0x14001426d  sub     rsp, 30h
0x140014271  mov     rbx, rcx
0x140014274  call    ??0TokenRequest@@QEAA@PEAVAuthenticationContext@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1@Z; TokenRequest::TokenRequest(AuthenticationContext *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140014279  nop
0x14001427a  lea     rax, ??_7OAuthTokenRequestBase@@6B@; const OAuthTokenRequestBase::`vftable'
0x140014281  mov     [rbx], rax
0x140014284  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001428b  lea     r14, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140014292  mov     rcx, r14
0x140014295  mov     rax, [rax+18h]
0x140014299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001429e  add     rax, 18h
0x1400142a2  mov     [rbx+20h], rax
0x1400142a6  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400142ad  mov     rcx, r14
0x1400142b0  mov     rax, [rax+18h]
0x1400142b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400142b9  add     rax, 18h
0x1400142bd  mov     [rbx+30h], rax
0x1400142c1  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400142c8  mov     rcx, r14
0x1400142cb  mov     rax, [rax+18h]
0x1400142cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400142d4  add     rax, 18h
0x1400142d8  mov     [rbx+40h], rax
0x1400142dc  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400142e3  mov     rcx, r14
0x1400142e6  mov     rax, [rax+18h]
0x1400142ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400142ef  add     rax, 18h
0x1400142f3  mov     [rbx+48h], rax
0x1400142f7  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400142fe  mov     rcx, r14
0x140014301  mov     rax, [rax+18h]
0x140014305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001430a  add     rax, 18h
0x14001430e  mov     [rbx+58h], rax
0x140014312  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140014319  mov     rcx, r14
0x14001431c  mov     rax, [rax+18h]
0x140014320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014325  add     rax, 18h
0x140014329  mov     [rbx+60h], rax
0x14001432d  mov     r9d, 15h; int
0x140014333  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14001433a  lea     edx, [r9-14h]; int
0x14001433e  lea     ecx, [rdx+4Fh]; unsigned __int64
0x140014341  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x140014346  mov     [rsp+38h+var_18], rax
0x14001434b  test    rax, rax
0x14001434e  jz      short loc_14001435D
0x140014350  mov     rcx, rax; this
0x140014353  call    ??0IdToken@@QEAA@XZ; IdToken::IdToken(void)
0x140014358  mov     rdi, rax
0x14001435b  jmp     short loc_14001435F
0x14001435d  xor     edi, edi
0x14001435f  mov     qword ptr [rbx+68h], 0
0x140014367  mov     qword ptr [rbx+70h], 0
0x14001436f  mov     [rsp+38h+var_18], rdi
0x140014374  mov     ecx, 18h; Size
0x140014379  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001437e  mov     [rsp+38h+arg_0], rax
0x140014383  test    rax, rax
0x140014386  jz      short loc_1400143AA
0x140014388  xorps   xmm0, xmm0
0x14001438b  movups  xmmword ptr [rax], xmm0
0x14001438e  mov     dword ptr [rax+8], 1
0x140014395  mov     dword ptr [rax+0Ch], 1
0x14001439c  lea     rcx, ??_7?$_Ref_count@VIdToken@@@std@@6B@; const std::_Ref_count<IdToken>::`vftable'
0x1400143a3  mov     [rax], rcx
0x1400143a6  mov     [rax+10h], rdi
0x1400143aa  mov     [rbx+68h], rdi
0x1400143ae  mov     [rbx+70h], rax
0x1400143b2  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400143b9  mov     rcx, r14
0x1400143bc  mov     rax, [rax+18h]
0x1400143c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400143c5  add     rax, 18h
0x1400143c9  mov     [rbx+80h], rax
0x1400143d0  mov     byte ptr [rbx+50h], 0
0x1400143d4  mov     qword ptr [rbx+28h], 0
0x1400143dc  mov     dword ptr [rbx+3Ch], 0
0x1400143e3  mov     byte ptr [rbx+38h], 0
0x1400143e7  mov     dword ptr [rbx+78h], 0
0x1400143ee  mov     byte ptr [rbx+7Ch], 0
0x1400143f2  mov     byte ptr [rbx+88h], 0
0x1400143f9  mov     rax, rbx
0x1400143fc  mov     rbx, [rsp+38h+arg_8]
0x140014401  mov     rdi, [rsp+38h+arg_10]
0x140014406  add     rsp, 30h
0x14001440a  pop     r14
0x14001440c  retn
```
