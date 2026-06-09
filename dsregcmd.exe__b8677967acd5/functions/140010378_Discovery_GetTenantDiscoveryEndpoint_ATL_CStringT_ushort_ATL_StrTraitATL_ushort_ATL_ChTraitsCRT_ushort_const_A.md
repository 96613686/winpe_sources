# Discovery::GetTenantDiscoveryEndpoint(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,AuthenticationContext const &)

- ea: `0x140010378`
- end: `0x140010886`
- name: `?GetTenantDiscoveryEndpoint@Discovery@@CA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV23@00AEBVAuthenticationContext@@@Z`
- size: `1294`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14001088c`

## callees

- `0x1400017d4`
- `0x140001814`
- `0x1400028ac`
- `0x140005458`
- `0x14000579c`
- `0x140005c80`
- `0x1400061dc`
- `0x14000813c`
- `0x14000f978`
- `0x14000ff6c`
- `0x140010378`
- `0x1400116bc`
- `0x14001e1a8`
- `0x1400249f0`
- `0x140030010`

## string_xrefs

- `0x1400105a3`: `onecore\ds\security\dsreg\win32\adal.native\discovery.cpp`
- `0x14001070c`: `onecore\ds\security\dsreg\win32\adal.native\webcall.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Discovery::GetTenantDiscoveryEndpoint(_QWORD *a1, __int64 *a2, _QWORD *a3, __int64 a4, __int64 a5)
{
  volatile signed __int32 *v9; // r14
  volatile signed __int32 *v10; // rdx
  _QWORD *v11; // rdx
  __int64 (__fastcall *v12)(void ***); // rax
  _QWORD *v13; // rdx
  _QWORD *v14; // rax
  _QWORD *v15; // rbx
  _QWORD *v16; // rax
  _QWORD *v17; // rdi
  _QWORD *v18; // rax
  void **v19; // rsi
  volatile signed __int32 *v20; // rdx
  _QWORD *v21; // rdx
  WebRequest *v23; // [rsp+20h] [rbp-71h] BYREF
  volatile signed __int32 *v24; // [rsp+28h] [rbp-69h] BYREF
  __int64 v25[2]; // [rsp+30h] [rbp-61h] BYREF
  _QWORD *v26; // [rsp+40h] [rbp-51h] BYREF
  int v27; // [rsp+48h] [rbp-49h] BYREF
  __int64 v28; // [rsp+50h] [rbp-41h] BYREF
  __int64 v29; // [rsp+58h] [rbp-39h] BYREF
  void *Block; // [rsp+60h] [rbp-31h]
  _QWORD v31[15]; // [rsp+68h] [rbp-29h] BYREF

  v9 = (volatile signed __int32 *)((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
  v31[3] = v9 + 6;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v25,
    a2);
  ATL::CSimpleStringT<unsigned short,0>::Append(v25, (__int64)L"?", 1);
  v23 = (WebRequest *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v23,
          (__int64)L"1.0") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v23, L"1.0", 3);
  v24 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v24,
          (__int64)L"api-version") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v24, L"api-version", 11);
  StringUtility::AddQueryString(v25, &v24, &v23);
  v10 = v24 - 6;
  if ( _InterlockedDecrement(v24 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v10 + 8LL))(*(_QWORD *)v10);
  v11 = (_QWORD *)((char *)v23 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)v23 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 8LL))(*v11);
  v12 = (__int64 (__fastcall *)(void ***))ATL::g_strmgr[3];
  if ( *(_DWORD *)(*a3 - 16LL) )
  {
    v23 = (WebRequest *)(v12(&ATL::g_strmgr) + 24);
    if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
            (void *const *)&v23,
            (__int64)L"issuer") )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v23, L"issuer", 6);
    StringUtility::AddQueryString(v25, &v23, a3);
  }
  else
  {
    v23 = (WebRequest *)(v12(&ATL::g_strmgr) + 24);
    if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
            (void *const *)&v23,
            (__int64)L"authorization_endpoint") )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v23, L"authorization_endpoint", 22);
    StringUtility::AddQueryString(v25, &v23, a4);
  }
  v13 = (_QWORD *)((char *)v23 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)v23 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 8LL))(*v13);
  v14 = operator new(0x28u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\discovery.cpp");
  v15 = v14;
  if ( v14 )
  {
    v14[1] = 0;
    v14[2] = 0;
    v14[3] = 0;
    v14[4] = 0;
    *v14 = &DiscoveryResponse::`vftable';
    v14[1] = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    v15[2] = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    v15[3] = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    v15[4] = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  }
  else
  {
    v15 = 0;
  }
  v26 = v15;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v24,
    (__int64 *)(a5 + 40));
  v23 = (WebRequest *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v23,
          (__int64)&dword_14003353C) )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v23, &dword_14003353C, 0);
  v31[4] = 0;
  v27 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v28,
    v25);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v29,
    (__int64 *)&v23);
  Block = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v31,
    (__int64 *)&v24);
  v31[1] = 0;
  v31[2] = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v16 = operator new(0x10u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\webcall.cpp");
  v17 = v16;
  v31[5] = v16;
  if ( v16 )
  {
    *v16 = 0;
    v16[1] = 0;
    v18 = operator new(0x30u);
    *v18 = v18;
    v18[1] = v18;
    v18[2] = v18;
    *((_WORD *)v18 + 12) = 257;
    *v17 = v18;
  }
  else
  {
    v17 = 0;
  }
  v19 = (void **)Block;
  Block = v17;
  if ( v19 )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,void *>>>(
      (__int64)v19,
      (__int64)v19,
      *((__int64 **)*v19 + 1));
    operator delete(*v19);
    operator delete(v19);
  }
  CSecureString::~CSecureString((CSecureString *)&v23);
  v20 = v24 - 6;
  if ( _InterlockedDecrement(v24 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v20 + 8LL))(*(_QWORD *)v20);
  WebRequestFactory::CreateBasicConnection(&v23, a5, 0);
  WebCall::SendRequest(&v27, &v23, &v26);
  if ( v23 )
    (**(void (__fastcall ***)(WebRequest *, __int64))v23)(v23, 1);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    a1,
    v15 + 1);
  WebCall::~WebCall((WebCall *)&v27);
  if ( v15 )
    (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
  v21 = (_QWORD *)(v25[0] - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v25[0] - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v21 + 8LL))(*v21);
  if ( _InterlockedDecrement(v9 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v9 + 8LL))(*(_QWORD *)v9, v9);
  return a1;
}

```

## disassembly

```asm
0x140010378  push    rbp
0x14001037a  push    rbx
0x14001037b  push    rsi
0x14001037c  push    rdi
0x14001037d  push    r12
0x14001037f  push    r13
0x140010381  push    r14
0x140010383  push    r15
0x140010385  lea     rbp, [rsp-17h]
0x14001038a  sub     rsp, 0A8h
0x140010391  mov     rsi, r9
0x140010394  mov     rdi, r8
0x140010397  mov     rbx, rdx
0x14001039a  mov     r12, rcx
0x14001039d  xor     r13d, r13d
0x1400103a0  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400103a7  lea     r15, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400103ae  mov     rcx, r15
0x1400103b1  mov     rax, [rax+18h]
0x1400103b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400103ba  mov     r14, rax
0x1400103bd  lea     rcx, [rax+18h]
0x1400103c1  mov     [rbp+4Fh+var_60], rcx
0x1400103c5  mov     rdx, rbx
0x1400103c8  lea     rcx, [rbp+4Fh+var_B0]
0x1400103cc  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400103d1  nop
0x1400103d2  lea     r8d, [r13+1]
0x1400103d6  lea     rdx, asc_140034D04; "?"
0x1400103dd  lea     rcx, [rbp+4Fh+var_B0]
0x1400103e1  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1400103e6  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400103ed  mov     rcx, r15
0x1400103f0  mov     rax, [rax+18h]
0x1400103f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400103f9  add     rax, 18h
0x1400103fd  mov     [rbp+4Fh+var_C0], rax
0x140010401  lea     rdx, a10; "1.0"
0x140010408  lea     rcx, [rbp+4Fh+var_C0]
0x14001040c  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140010411  test    al, al
0x140010413  jnz     short loc_14001042A
0x140010415  lea     r8d, [r13+3]
0x140010419  lea     rdx, a10; "1.0"
0x140010420  lea     rcx, [rbp+4Fh+var_C0]
0x140010424  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140010429  nop
0x14001042a  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140010431  mov     rcx, r15
0x140010434  mov     rax, [rax+18h]
0x140010438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001043d  add     rax, 18h
0x140010441  mov     [rbp+4Fh+var_B8], rax
0x140010445  lea     rdx, aApiVersion; "api-version"
0x14001044c  lea     rcx, [rbp+4Fh+var_B8]
0x140010450  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140010455  test    al, al
0x140010457  jnz     short loc_140010470
0x140010459  mov     r8d, 0Bh
0x14001045f  lea     rdx, aApiVersion; "api-version"
0x140010466  lea     rcx, [rbp+4Fh+var_B8]
0x14001046a  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001046f  nop
0x140010470  lea     r8, [rbp+4Fh+var_C0]
0x140010474  lea     rdx, [rbp+4Fh+var_B8]
0x140010478  lea     rcx, [rbp+4Fh+var_B0]
0x14001047c  call    ?AddQueryString@StringUtility@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV23@1@Z; StringUtility::AddQueryString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140010481  nop
0x140010482  mov     rdx, [rbp+4Fh+var_B8]
0x140010486  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001048a  or      ebx, 0FFFFFFFFh
0x14001048d  mov     eax, ebx
0x14001048f  lock xadd [rdx+10h], eax
0x140010494  add     eax, ebx
0x140010496  test    eax, eax
0x140010498  jg      short loc_1400104AA
0x14001049a  mov     rcx, [rdx]
0x14001049d  mov     rax, [rcx]
0x1400104a0  mov     rax, [rax+8]
0x1400104a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400104a9  nop
0x1400104aa  mov     rdx, [rbp+4Fh+var_C0]
0x1400104ae  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400104b2  mov     eax, ebx
0x1400104b4  lock xadd [rdx+10h], eax
0x1400104b9  add     eax, ebx
0x1400104bb  test    eax, eax
0x1400104bd  jg      short loc_1400104CE
0x1400104bf  mov     rcx, [rdx]
0x1400104c2  mov     rax, [rcx]
0x1400104c5  mov     rax, [rax+8]
0x1400104c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400104ce  mov     rax, [rdi]
0x1400104d1  mov     rcx, r15
0x1400104d4  cmp     [rax-10h], r13d
0x1400104d8  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400104df  mov     rax, [rax+18h]
0x1400104e3  jz      short loc_140010530
0x1400104e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400104ea  add     rax, 18h
0x1400104ee  mov     [rbp+4Fh+var_C0], rax
0x1400104f2  lea     rdx, aIssuer; "issuer"
0x1400104f9  lea     rcx, [rbp+4Fh+var_C0]
0x1400104fd  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140010502  test    al, al
0x140010504  jnz     short loc_14001051D
0x140010506  mov     r8d, 6
0x14001050c  lea     rdx, aIssuer; "issuer"
0x140010513  lea     rcx, [rbp+4Fh+var_C0]
0x140010517  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001051c  nop
0x14001051d  mov     r8, rdi
0x140010520  lea     rdx, [rbp+4Fh+var_C0]
0x140010524  lea     rcx, [rbp+4Fh+var_B0]
0x140010528  call    ?AddQueryString@StringUtility@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV23@1@Z; StringUtility::AddQueryString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001052d  nop
0x14001052e  jmp     short loc_140010579
0x140010530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010535  add     rax, 18h
0x140010539  mov     [rbp+4Fh+var_C0], rax
0x14001053d  lea     rdx, aAuthorizationE; "authorization_endpoint"
0x140010544  lea     rcx, [rbp+4Fh+var_C0]
0x140010548  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14001054d  test    al, al
0x14001054f  jnz     short loc_140010568
0x140010551  mov     r8d, 16h
0x140010557  lea     rdx, aAuthorizationE; "authorization_endpoint"
0x14001055e  lea     rcx, [rbp+4Fh+var_C0]
0x140010562  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140010567  nop
0x140010568  mov     r8, rsi
0x14001056b  lea     rdx, [rbp+4Fh+var_C0]
0x14001056f  lea     rcx, [rbp+4Fh+var_B0]
0x140010573  call    ?AddQueryString@StringUtility@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV23@1@Z; StringUtility::AddQueryString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140010578  nop
0x140010579  mov     rdx, [rbp+4Fh+var_C0]
0x14001057d  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140010581  mov     eax, ebx
0x140010583  lock xadd [rdx+10h], eax
0x140010588  add     eax, ebx
0x14001058a  test    eax, eax
0x14001058c  jg      short loc_14001059D
0x14001058e  mov     rcx, [rdx]
0x140010591  mov     rax, [rcx]
0x140010594  mov     rax, [rax+8]
0x140010598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001059d  mov     r9d, 8Bh; int
0x1400105a3  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x1400105aa  mov     esi, 1
0x1400105af  mov     edx, esi; int
0x1400105b1  lea     ecx, [rsi+27h]; unsigned __int64
0x1400105b4  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x1400105b9  mov     rbx, rax
0x1400105bc  test    rax, rax
0x1400105bf  jz      loc_14001064D
0x1400105c5  mov     [rax+8], r13
0x1400105c9  mov     [rax+10h], r13
0x1400105cd  mov     [rax+18h], r13
0x1400105d1  mov     [rax+20h], r13
0x1400105d5  lea     rax, ??_7DiscoveryResponse@@6B@; const DiscoveryResponse::`vftable'
0x1400105dc  mov     [rbx], rax
0x1400105df  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400105e6  mov     rcx, r15
0x1400105e9  mov     rax, [rax+18h]
0x1400105ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400105f2  add     rax, 18h
0x1400105f6  mov     [rbx+8], rax
0x1400105fa  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140010601  mov     rcx, r15
0x140010604  mov     rax, [rax+18h]
0x140010608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001060d  add     rax, 18h
0x140010611  mov     [rbx+10h], rax
0x140010615  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001061c  mov     rcx, r15
0x14001061f  mov     rax, [rax+18h]
0x140010623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010628  add     rax, 18h
0x14001062c  mov     [rbx+18h], rax
0x140010630  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140010637  mov     rcx, r15
0x14001063a  mov     rax, [rax+18h]
0x14001063e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010643  add     rax, 18h
0x140010647  mov     [rbx+20h], rax
0x14001064b  jmp     short loc_140010650
0x14001064d  mov     rbx, r13
0x140010650  mov     [rbp+4Fh+var_A0], rbx
0x140010654  mov     r15, [rbp+4Fh+arg_20]
0x140010658  lea     rdx, [r15+28h]
0x14001065c  lea     rcx, [rbp+4Fh+var_B8]
0x140010660  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140010665  nop
0x140010666  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001066d  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140010674  mov     rax, [rax+18h]
0x140010678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001067d  add     rax, 18h
0x140010681  mov     [rbp+4Fh+var_C0], rax
0x140010685  lea     rdx, dword_14003353C
0x14001068c  lea     rcx, [rbp+4Fh+var_C0]
0x140010690  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140010695  test    al, al
0x140010697  jnz     short loc_1400106AD
0x140010699  xor     r8d, r8d
0x14001069c  lea     rdx, dword_14003353C
0x1400106a3  lea     rcx, [rbp+4Fh+var_C0]
0x1400106a7  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400106ac  nop
0x1400106ad  mov     [rbp+4Fh+var_58], r13
0x1400106b1  mov     [rbp+4Fh+var_98], r13d
0x1400106b5  lea     rdx, [rbp+4Fh+var_B0]
0x1400106b9  lea     rcx, [rbp+4Fh+var_90]
0x1400106bd  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400106c2  nop
0x1400106c3  lea     rdx, [rbp+4Fh+var_C0]
0x1400106c7  lea     rcx, [rbp+4Fh+var_88]
0x1400106cb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400106d0  nop
0x1400106d1  mov     [rbp+4Fh+Block], r13
0x1400106d5  lea     rdx, [rbp+4Fh+var_B8]
0x1400106d9  lea     rcx, [rbp+4Fh+var_78]
0x1400106dd  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400106e2  nop
0x1400106e3  mov     [rbp+4Fh+var_70], r13
0x1400106e7  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400106ee  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400106f5  mov     rax, [rax+18h]
0x1400106f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400106fe  add     rax, 18h
0x140010702  mov     [rbp+4Fh+var_68], rax
0x140010706  mov     r9d, 11h; int
0x14001070c  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x140010713  mov     edx, esi; int
0x140010715  lea     ecx, [r9-1]; unsigned __int64
0x140010719  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x14001071e  mov     rdi, rax
0x140010721  mov     [rbp+4Fh+var_50], rax
0x140010725  test    rax, rax
0x140010728  jz      short loc_140010751
0x14001072a  mov     [rax], r13
0x14001072d  mov     [rax+8], r13
0x140010731  mov     ecx, 30h ; '0'; Size
0x140010736  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001073b  mov     [rax], rax
0x14001073e  mov     [rax+8], rax
0x140010742  mov     [rax+10h], rax
0x140010746  mov     word ptr [rax+18h], 101h
0x14001074c  mov     [rdi], rax
0x14001074f  jmp     short loc_140010754
0x140010751  mov     rdi, r13
0x140010754  mov     rsi, [rbp+4Fh+Block]
0x140010758  mov     [rbp+4Fh+Block], rdi
0x14001075c  test    rsi, rsi
0x14001075f  jz      short loc_14001078E
0x140010761  mov     r8, [rsi]
0x140010764  mov     r8, [r8+8]
0x140010768  mov     rdx, rsi
0x14001076b  mov     rcx, rsi
0x14001076e  call    ??$_Erase_tree_and_orphan@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *>> &,std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *)
0x140010773  mov     edx, 30h ; '0'
0x140010778  mov     rcx, [rsi]; Block
0x14001077b  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x140010780  mov     edx, 10h
0x140010785  mov     rcx, rsi; Block
0x140010788  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14001078d  nop
0x14001078e  lea     rcx, [rbp+4Fh+var_C0]; this
0x140010792  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x140010797  nop
0x140010798  mov     rdx, [rbp+4Fh+var_B8]
0x14001079c  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400107a0  or      edi, 0FFFFFFFFh
0x1400107a3  mov     eax, edi
0x1400107a5  lock xadd [rdx+10h], eax
0x1400107aa  add     eax, edi
0x1400107ac  test    eax, eax
0x1400107ae  jg      short loc_1400107BF
0x1400107b0  mov     rcx, [rdx]
0x1400107b3  mov     rax, [rcx]
0x1400107b6  mov     rax, [rax+8]
0x1400107ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400107bf  xor     r8d, r8d
0x1400107c2  mov     rdx, r15
0x1400107c5  lea     rcx, [rbp+4Fh+var_C0]
0x1400107c9  call    ?CreateBasicConnection@WebRequestFactory@@CA?AV?$unique_ptr@VWebRequest@@U?$default_delete@VWebRequest@@@std@@@std@@AEBVAuthenticationContext@@_N@Z; WebRequestFactory::CreateBasicConnection(AuthenticationContext const &,bool)
0x1400107ce  nop
0x1400107cf  lea     r8, [rbp+4Fh+var_A0]
0x1400107d3  lea     rdx, [rbp+4Fh+var_C0]
0x1400107d7  lea     rcx, [rbp+4Fh+var_98]
0x1400107db  call    ?SendRequest@WebCall@@QEAAXAEBV?$unique_ptr@VWebRequest@@U?$default_delete@VWebRequest@@@std@@@std@@AEBV?$unique_ptr@VWebCallResponse@@U?$default_delete@VWebCallResponse@@@std@@@3@@Z; WebCall::SendRequest(std::unique_ptr<WebRequest> const &,std::unique_ptr<WebCallResponse> const &)
0x1400107e0  nop
0x1400107e1  mov     rcx, [rbp+4Fh+var_C0]
0x1400107e5  test    rcx, rcx
0x1400107e8  jz      short loc_1400107FA
0x1400107ea  mov     rax, [rcx]
0x1400107ed  mov     edx, 1
0x1400107f2  mov     rax, [rax]
0x1400107f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400107fa  lea     rdx, [rbx+8]
  ... truncated ...
```
