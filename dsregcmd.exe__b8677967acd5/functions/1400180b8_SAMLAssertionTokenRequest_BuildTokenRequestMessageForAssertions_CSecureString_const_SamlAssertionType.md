# SAMLAssertionTokenRequest::BuildTokenRequestMessageForAssertions(CSecureString const &,SamlAssertionType)

- ea: `0x1400180b8`
- end: `0x1400188a1`
- name: `?BuildTokenRequestMessageForAssertions@SAMLAssertionTokenRequest@@AEAA?AVCSecureString@@AEBV2@W4SamlAssertionType@@@Z`
- size: `2025`
- prototype: `__int64 *__fastcall(__int64, __int64 *, _QWORD *, int)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x140018000`

## callees

- `0x140005458`
- `0x14000579c`
- `0x140005c80`
- `0x1400061dc`
- `0x14000813c`
- `0x14000caac`
- `0x1400116bc`
- `0x14001366c`
- `0x140017e8c`
- `0x140017f28`
- `0x1400180b8`
- `0x1400188a8`
- `0x14002c3e8`
- `0x140030010`

## string_xrefs

- `0x140018737`: `openid`
- `0x140018751`: `openid`

## pseudocode

```c
__int64 *__fastcall SAMLAssertionTokenRequest::BuildTokenRequestMessageForAssertions(
        __int64 a1,
        __int64 *a2,
        _QWORD *a3,
        int a4)
{
  __int64 v8; // rbx
  _QWORD *v9; // rdx
  __int64 v10; // rbx
  _QWORD *v11; // rdx
  _QWORD *v12; // rdx
  _QWORD *v13; // rdx
  int v14; // r14d
  bool v15; // bl
  __int64 v16; // rdx
  _QWORD *v17; // rdx
  _QWORD *v18; // rdx
  _QWORD *v19; // rdx
  _QWORD *v20; // rdx
  _QWORD *v21; // rdx
  int v22; // r14d
  _QWORD *v23; // rdx
  _QWORD *v24; // rdx
  __int64 v25; // rbx
  int v27; // [rsp+20h] [rbp-30h]
  __int64 v28; // [rsp+28h] [rbp-28h] BYREF
  __int64 v29; // [rsp+30h] [rbp-20h] BYREF
  __int64 *v30; // [rsp+38h] [rbp-18h] BYREF
  _BYTE pExceptionObject[16]; // [rsp+40h] [rbp-10h] BYREF

  v27 = 0;
  *a2 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v27 = 1;
  if ( !*(_DWORD *)(*a3 - 16LL) )
  {
    Exception::Exception((Exception *)pExceptionObject, -894894078);
    throw (Exception *)pExceptionObject;
  }
  if ( a4 )
  {
    if ( a4 != 1 )
    {
      Exception::Exception((Exception *)pExceptionObject, -894894078);
      throw (Exception *)pExceptionObject;
    }
    ATL::CSimpleStringT<unsigned short,0>::SetString(
      a2,
      L"grant_type=urn%3Aietf%3Aparams%3Aoauth%3Agrant-type%3Asaml2-bearer",
      66);
    v10 = *(_QWORD *)SAMLAssertionTokenRequest::GetBase64EncodedAssertion(&v30, a3);
    v28 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                             &v28,
                             v10) )
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        &v28,
        v10);
    v29 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                             &v29,
                             L"assertion") )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v29, L"assertion", 9);
    StringUtility::AddQueryString(a2, &v29, &v28);
    v11 = (_QWORD *)(v29 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v29 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 8LL))(*v11);
    CSecureString::~CSecureString((CSecureString *)&v28);
  }
  else
  {
    ATL::CSimpleStringT<unsigned short,0>::SetString(
      a2,
      L"grant_type=urn%3Aietf%3Aparams%3Aoauth%3Agrant-type%3Asaml1_1-bearer",
      68);
    v8 = *(_QWORD *)SAMLAssertionTokenRequest::GetBase64EncodedAssertion(&v30, a3);
    v29 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                             &v29,
                             v8) )
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        &v29,
        v8);
    v28 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                             &v28,
                             L"assertion") )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v28, L"assertion", 9);
    StringUtility::AddQueryString(a2, &v28, &v29);
    v9 = (_QWORD *)(v28 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v28 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 8LL))(*v9);
    CSecureString::~CSecureString((CSecureString *)&v29);
  }
  CSecureStringA::~CSecureStringA((CSecureStringA *)&v30);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v28,
    (__int64 *)(*(_QWORD *)(a1 + 8) + 16LL));
  v27 = 3;
  v29 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                           &v29,
                           L"client_id") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v29, L"client_id", 9);
  StringUtility::AddQueryString(a2, &v29, &v28);
  v12 = (_QWORD *)(v29 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v29 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v12 + 8LL))(*v12);
  v13 = (_QWORD *)(v28 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v28 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 8LL))(*v13);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v29,
    (__int64 *)(*(_QWORD *)(a1 + 8) + 288LL));
  v14 = 7;
  v27 = 7;
  v15 = *(_DWORD *)(v29 - 16) != 0;
  CSecureString::~CSecureString((CSecureString *)&v29);
  if ( v15 )
  {
    v16 = *(_QWORD *)(a1 + 8);
    if ( (*(_BYTE *)(v16 + 296) & 0x10) != 0 )
    {
      v28 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                               &v28,
                               L"urn:ietf:params:oauth:client-assertion-type:jwt-bearer") )
        ATL::CSimpleStringT<unsigned short,0>::SetString(
          &v28,
          L"urn:ietf:params:oauth:client-assertion-type:jwt-bearer",
          54);
      v29 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                               &v29,
                               L"client_assertion_type") )
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v29, L"client_assertion_type", 21);
      StringUtility::AddQueryString(a2, &v29, &v28);
      v17 = (_QWORD *)(v29 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v29 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v17 + 8LL))(*v17);
      v18 = (_QWORD *)(v28 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v28 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 8LL))(*v18);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v28,
        (__int64 *)(*(_QWORD *)(a1 + 8) + 288LL));
      v14 = 15;
      v27 = 15;
      v29 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                               &v29,
                               L"client_assertion") )
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v29, L"client_assertion", 16);
      StringUtility::AddQueryString(a2, &v29, &v28);
      v19 = (_QWORD *)(v29 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v29 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v19 + 8LL))(*v19);
    }
    else
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v28,
        (__int64 *)(v16 + 288));
      v14 = 23;
      v27 = 23;
      v29 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                               &v29,
                               L"client_secret") )
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v29, L"client_secret", 13);
      StringUtility::AddQueryString(a2, &v29, &v28);
      v20 = (_QWORD *)(v29 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v29 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v20 + 8LL))(*v20);
    }
    CSecureString::~CSecureString((CSecureString *)&v28);
  }
  v29 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                           &v29,
                           L"resource") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v29, L"resource", 8);
  StringUtility::AddQueryString(a2, &v29, a1 + 16);
  v21 = (_QWORD *)(v29 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v29 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v21 + 8LL))(*v21);
  v30 = &v29;
  v29 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                           &v29,
                           L"scope") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v29, L"scope", 5);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v28,
    (__int64 *)(*(_QWORD *)(a1 + 8) + 64LL));
  v22 = v14 | 0x20;
  v27 = v22;
  if ( !(unsigned __int8)StringUtility::QueryStringContains(&v28, &v29) )
  {
    v28 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                             &v28,
                             L"openid") )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v28, L"openid", 6);
    v29 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                             &v29,
                             L"scope") )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v29, L"scope", 5);
    StringUtility::AddQueryString(a2, &v29, &v28);
    v23 = (_QWORD *)(v29 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v29 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v23 + 8LL))(*v23);
    v24 = (_QWORD *)(v28 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v28 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v24 + 8LL))(*v24);
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v30,
    (__int64 *)(*(_QWORD *)(a1 + 8) + 64LL));
  v27 = v22 | 0x40;
  v25 = (__int64)v30;
  ATL::CSimpleStringT<unsigned short,0>::Append(a2, (__int64)v30, *((unsigned int *)v30 - 4));
  if ( _InterlockedDecrement((volatile signed __int32 *)(v25 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v25 - 24) + 8LL))(*(_QWORD *)(v25 - 24));
  return a2;
}

```

## disassembly

```asm
0x1400180b8  mov     [rsp-28h+arg_0], rbx
0x1400180bd  mov     [rsp-28h+arg_10], rsi
0x1400180c2  mov     [rsp-28h+arg_8], rdx
0x1400180c7  push    rbp
0x1400180c8  push    rdi
0x1400180c9  push    r13
0x1400180cb  push    r14
0x1400180cd  push    r15
0x1400180cf  mov     rbp, rsp
0x1400180d2  sub     rsp, 50h
0x1400180d6  mov     ebx, r9d
0x1400180d9  mov     rdi, r8
0x1400180dc  mov     rsi, rdx
0x1400180df  mov     r15, rcx
0x1400180e2  mov     [rbp+var_30], 0
0x1400180e9  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400180f0  lea     r13, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400180f7  mov     rcx, r13
0x1400180fa  mov     rax, [rax+18h]
0x1400180fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018103  add     rax, 18h
0x140018107  mov     [rsi], rax
0x14001810a  mov     [rbp+var_30], 1
0x140018111  mov     rax, [rdi]
0x140018114  cmp     dword ptr [rax-10h], 0
0x140018118  jz      loc_140018863
0x14001811e  test    ebx, ebx
0x140018120  jnz     loc_14001820F
0x140018126  lea     r8d, [rbx+44h]
0x14001812a  lea     rdx, aGrantTypeUrn3a_0; "grant_type=urn%3Aietf%3Aparams%3Aoauth%"...
0x140018131  mov     rcx, rsi
0x140018134  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140018139  mov     rdx, rdi
0x14001813c  lea     rcx, [rbp+var_18]
0x140018140  call    ?GetBase64EncodedAssertion@SAMLAssertionTokenRequest@@CA?AVCSecureStringA@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; SAMLAssertionTokenRequest::GetBase64EncodedAssertion(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140018145  nop
0x140018146  mov     rbx, [rax]
0x140018149  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140018150  mov     rcx, r13
0x140018153  mov     rax, [rax+18h]
0x140018157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001815c  add     rax, 18h
0x140018160  mov     [rbp+var_20], rax
0x140018164  mov     rdx, rbx
0x140018167  lea     rcx, [rbp+var_20]
0x14001816b  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140018170  test    al, al
0x140018172  jnz     short loc_140018181
0x140018174  mov     rdx, rbx
0x140018177  lea     rcx, [rbp+var_20]
0x14001817b  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(char const *)
0x140018180  nop
0x140018181  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140018188  mov     rcx, r13
0x14001818b  mov     rax, [rax+18h]
0x14001818f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018194  add     rax, 18h
0x140018198  mov     [rbp+var_28], rax
0x14001819c  lea     rdx, aAssertion; "assertion"
0x1400181a3  lea     rcx, [rbp+var_28]
0x1400181a7  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x1400181ac  test    al, al
0x1400181ae  jnz     short loc_1400181C7
0x1400181b0  mov     r8d, 9
0x1400181b6  lea     rdx, aAssertion; "assertion"
0x1400181bd  lea     rcx, [rbp+var_28]
0x1400181c1  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400181c6  nop
0x1400181c7  lea     r8, [rbp+var_20]
0x1400181cb  lea     rdx, [rbp+var_28]
0x1400181cf  mov     rcx, rsi
0x1400181d2  call    ?AddQueryString@StringUtility@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV23@1@Z; StringUtility::AddQueryString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400181d7  nop
0x1400181d8  mov     rdx, [rbp+var_28]
0x1400181dc  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400181e0  or      edi, 0FFFFFFFFh
0x1400181e3  mov     eax, edi
0x1400181e5  lock xadd [rdx+10h], eax
0x1400181ea  add     eax, edi
0x1400181ec  test    eax, eax
0x1400181ee  jg      short loc_140018200
0x1400181f0  mov     rcx, [rdx]
0x1400181f3  mov     rax, [rcx]
0x1400181f6  mov     rax, [rax+8]
0x1400181fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400181ff  nop
0x140018200  lea     rcx, [rbp+var_20]; this
0x140018204  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x140018209  nop
0x14001820a  jmp     loc_1400182FC
0x14001820f  cmp     ebx, 1
0x140018212  jnz     loc_140018882
0x140018218  lea     r8d, [rbx+41h]
0x14001821c  lea     rdx, aGrantTypeUrn3a; "grant_type=urn%3Aietf%3Aparams%3Aoauth%"...
0x140018223  mov     rcx, rsi
0x140018226  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001822b  mov     rdx, rdi
0x14001822e  lea     rcx, [rbp+var_18]
0x140018232  call    ?GetBase64EncodedAssertion@SAMLAssertionTokenRequest@@CA?AVCSecureStringA@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; SAMLAssertionTokenRequest::GetBase64EncodedAssertion(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140018237  nop
0x140018238  mov     rbx, [rax]
0x14001823b  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140018242  mov     rcx, r13
0x140018245  mov     rax, [rax+18h]
0x140018249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001824e  add     rax, 18h
0x140018252  mov     [rbp+var_28], rax
0x140018256  mov     rdx, rbx
0x140018259  lea     rcx, [rbp+var_28]
0x14001825d  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140018262  test    al, al
0x140018264  jnz     short loc_140018273
0x140018266  mov     rdx, rbx
0x140018269  lea     rcx, [rbp+var_28]
0x14001826d  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(char const *)
0x140018272  nop
0x140018273  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001827a  mov     rcx, r13
0x14001827d  mov     rax, [rax+18h]
0x140018281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018286  add     rax, 18h
0x14001828a  mov     [rbp+var_20], rax
0x14001828e  lea     rdx, aAssertion; "assertion"
0x140018295  lea     rcx, [rbp+var_20]
0x140018299  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14001829e  test    al, al
0x1400182a0  jnz     short loc_1400182B9
0x1400182a2  mov     r8d, 9
0x1400182a8  lea     rdx, aAssertion; "assertion"
0x1400182af  lea     rcx, [rbp+var_20]
0x1400182b3  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400182b8  nop
0x1400182b9  lea     r8, [rbp+var_28]
0x1400182bd  lea     rdx, [rbp+var_20]
0x1400182c1  mov     rcx, rsi
0x1400182c4  call    ?AddQueryString@StringUtility@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV23@1@Z; StringUtility::AddQueryString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400182c9  nop
0x1400182ca  mov     rdx, [rbp+var_20]
0x1400182ce  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400182d2  or      edi, 0FFFFFFFFh
0x1400182d5  mov     eax, edi
0x1400182d7  lock xadd [rdx+10h], eax
0x1400182dc  add     eax, edi
0x1400182de  test    eax, eax
0x1400182e0  jg      short loc_1400182F2
0x1400182e2  mov     rcx, [rdx]
0x1400182e5  mov     rax, [rcx]
0x1400182e8  mov     rax, [rax+8]
0x1400182ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400182f1  nop
0x1400182f2  lea     rcx, [rbp+var_28]; this
0x1400182f6  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x1400182fb  nop
0x1400182fc  lea     rcx, [rbp+var_18]; this
0x140018300  call    ??1CSecureStringA@@QEAA@XZ; CSecureStringA::~CSecureStringA(void)
0x140018305  mov     rdx, [r15+8]
0x140018309  add     rdx, 10h
0x14001830d  lea     rcx, [rbp+var_28]
0x140018311  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140018316  mov     [rbp+var_30], 3
0x14001831d  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140018324  mov     rcx, r13
0x140018327  mov     rax, [rax+18h]
0x14001832b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018330  add     rax, 18h
0x140018334  mov     [rbp+var_20], rax
0x140018338  lea     rdx, aClientId; "client_id"
0x14001833f  lea     rcx, [rbp+var_20]
0x140018343  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140018348  test    al, al
0x14001834a  jnz     short loc_140018363
0x14001834c  mov     r8d, 9
0x140018352  lea     rdx, aClientId; "client_id"
0x140018359  lea     rcx, [rbp+var_20]
0x14001835d  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140018362  nop
0x140018363  lea     r8, [rbp+var_28]
0x140018367  lea     rdx, [rbp+var_20]
0x14001836b  mov     rcx, rsi
0x14001836e  call    ?AddQueryString@StringUtility@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV23@1@Z; StringUtility::AddQueryString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140018373  nop
0x140018374  mov     rdx, [rbp+var_20]
0x140018378  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001837c  mov     eax, edi
0x14001837e  lock xadd [rdx+10h], eax
0x140018383  add     eax, edi
0x140018385  test    eax, eax
0x140018387  jg      short loc_140018399
0x140018389  mov     rcx, [rdx]
0x14001838c  mov     rax, [rcx]
0x14001838f  mov     rax, [rax+8]
0x140018393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018398  nop
0x140018399  mov     rdx, [rbp+var_28]
0x14001839d  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400183a1  mov     eax, edi
0x1400183a3  lock xadd [rdx+10h], eax
0x1400183a8  add     eax, edi
0x1400183aa  test    eax, eax
0x1400183ac  jg      short loc_1400183BD
0x1400183ae  mov     rcx, [rdx]
0x1400183b1  mov     rax, [rcx]
0x1400183b4  mov     rax, [rax+8]
0x1400183b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400183bd  mov     rdx, [r15+8]
0x1400183c1  add     rdx, 120h
0x1400183c8  lea     rcx, [rbp+var_20]
0x1400183cc  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400183d1  mov     r14d, 7
0x1400183d7  mov     [rbp+var_30], r14d
0x1400183db  mov     rax, [rbp+var_20]
0x1400183df  cmp     dword ptr [rax-10h], 0
0x1400183e3  setnz   bl
0x1400183e6  lea     rcx, [rbp+var_20]; this
0x1400183ea  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x1400183ef  test    bl, bl
0x1400183f1  jz      loc_140018626
0x1400183f7  mov     rdx, [r15+8]
0x1400183fb  test    byte ptr [rdx+128h], 10h
0x140018402  jz      loc_140018589
0x140018408  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001840f  mov     rcx, r13
0x140018412  mov     rax, [rax+18h]
0x140018416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001841b  add     rax, 18h
0x14001841f  mov     [rbp+var_28], rax
0x140018423  lea     rdx, aUrnIetfParamsO; "urn:ietf:params:oauth:client-assertion-"...
0x14001842a  lea     rcx, [rbp+var_28]
0x14001842e  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140018433  test    al, al
0x140018435  jnz     short loc_14001844C
0x140018437  lea     r8d, [r14+2Fh]
0x14001843b  lea     rdx, aUrnIetfParamsO; "urn:ietf:params:oauth:client-assertion-"...
0x140018442  lea     rcx, [rbp+var_28]
0x140018446  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001844b  nop
0x14001844c  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140018453  mov     rcx, r13
0x140018456  mov     rax, [rax+18h]
0x14001845a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001845f  add     rax, 18h
0x140018463  mov     [rbp+var_20], rax
0x140018467  lea     rdx, aClientAssertio_0; "client_assertion_type"
0x14001846e  lea     rcx, [rbp+var_20]
0x140018472  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140018477  test    al, al
0x140018479  jnz     short loc_140018492
0x14001847b  mov     r8d, 15h
0x140018481  lea     rdx, aClientAssertio_0; "client_assertion_type"
0x140018488  lea     rcx, [rbp+var_20]
0x14001848c  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140018491  nop
0x140018492  lea     r8, [rbp+var_28]
0x140018496  lea     rdx, [rbp+var_20]
0x14001849a  mov     rcx, rsi
0x14001849d  call    ?AddQueryString@StringUtility@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV23@1@Z; StringUtility::AddQueryString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400184a2  nop
0x1400184a3  mov     rdx, [rbp+var_20]
0x1400184a7  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400184ab  mov     eax, edi
0x1400184ad  lock xadd [rdx+10h], eax
0x1400184b2  add     eax, edi
0x1400184b4  test    eax, eax
0x1400184b6  jg      short loc_1400184C8
0x1400184b8  mov     rcx, [rdx]
0x1400184bb  mov     rax, [rcx]
0x1400184be  mov     rax, [rax+8]
0x1400184c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400184c7  nop
0x1400184c8  mov     rdx, [rbp+var_28]
0x1400184cc  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400184d0  mov     eax, edi
0x1400184d2  lock xadd [rdx+10h], eax
0x1400184d7  add     eax, edi
0x1400184d9  test    eax, eax
0x1400184db  jg      short loc_1400184EC
0x1400184dd  mov     rcx, [rdx]
0x1400184e0  mov     rax, [rcx]
0x1400184e3  mov     rax, [rax+8]
0x1400184e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400184ec  mov     rdx, [r15+8]
0x1400184f0  add     rdx, 120h
0x1400184f7  lea     rcx, [rbp+var_28]
0x1400184fb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140018500  mov     r14d, 0Fh
0x140018506  mov     [rbp+var_30], r14d
0x14001850a  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140018511  mov     rcx, r13
0x140018514  mov     rax, [rax+18h]
0x140018518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001851d  add     rax, 18h
0x140018521  mov     [rbp+var_20], rax
0x140018525  lea     rdx, aClientAssertio; "client_assertion"
0x14001852c  lea     rcx, [rbp+var_20]
0x140018530  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140018535  test    al, al
0x140018537  jnz     short loc_14001854E
0x140018539  lea     r8d, [r14+1]
0x14001853d  lea     rdx, aClientAssertio; "client_assertion"
0x140018544  lea     rcx, [rbp+var_20]
  ... truncated ...
```
