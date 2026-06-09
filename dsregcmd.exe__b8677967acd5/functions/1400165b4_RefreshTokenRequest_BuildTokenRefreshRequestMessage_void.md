# RefreshTokenRequest::BuildTokenRefreshRequestMessage(void)

- ea: `0x1400165b4`
- end: `0x1400168a2`
- name: `?BuildTokenRefreshRequestMessage@RefreshTokenRequest@@AEAA?AVCSecureString@@XZ`
- size: `750`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14001604c`

## callees

- `0x140005458`
- `0x140005c80`
- `0x1400061dc`
- `0x1400116bc`
- `0x1400165b4`
- `0x140030010`

## string_xrefs

- `0x1400165f4`: `grant_type=refresh_token`
- `0x14001660d`: `grant_type=refresh_token`
- `0x1400166d5`: `redirect_uri`
- `0x1400166ef`: `redirect_uri`
- `0x14001663f`: `refresh_token`
- `0x140016659`: `refresh_token`

## pseudocode

```c
_QWORD *__fastcall RefreshTokenRequest::BuildTokenRefreshRequestMessage(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rdx
  _QWORD *v5; // rdx
  _QWORD *v6; // rdx
  _QWORD *v7; // rdx
  _QWORD *v8; // rdx
  _QWORD *v9; // rdx
  __int64 v11; // [rsp+70h] [rbp+40h] BYREF
  __int64 v12; // [rsp+78h] [rbp+48h] BYREF

  *a2 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                           a2,
                           L"grant_type=refresh_token") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(a2, L"grant_type=refresh_token", 24);
  v11 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                           &v11,
                           L"refresh_token") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v11, L"refresh_token", 13);
  StringUtility::AddQueryString(a2, &v11, a1 + 48);
  v4 = (_QWORD *)(v11 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v11 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 8LL))(*v4);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v12,
    (__int64 *)(*(_QWORD *)(a1 + 8) + 24LL));
  v11 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                           &v11,
                           L"redirect_uri") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v11, L"redirect_uri", 12);
  StringUtility::AddQueryString(a2, &v11, &v12);
  v5 = (_QWORD *)(v11 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v11 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 8LL))(*v5);
  v6 = (_QWORD *)(v12 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v12 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 8LL))(*v6);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v12,
    (__int64 *)(*(_QWORD *)(a1 + 8) + 16LL));
  v11 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                           &v11,
                           L"client_id") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v11, L"client_id", 9);
  StringUtility::AddQueryString(a2, &v11, &v12);
  v7 = (_QWORD *)(v11 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v11 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 8LL))(*v7);
  v8 = (_QWORD *)(v12 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v12 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 8LL))(*v8);
  if ( *(_BYTE *)(a1 + 56) )
  {
    v11 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                             &v11,
                             L"resource") )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v11, L"resource", 8);
    StringUtility::AddQueryString(a2, &v11, a1 + 16);
    v9 = (_QWORD *)(v11 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v11 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 8LL))(*v9);
  }
  return a2;
}

```

## disassembly

```asm
0x1400165b4  mov     [rsp-28h+arg_8], rdx
0x1400165b9  push    rbp
0x1400165ba  push    rbx
0x1400165bb  push    rsi
0x1400165bc  push    rdi
0x1400165bd  push    r14
0x1400165bf  mov     rbp, rsp
0x1400165c2  sub     rsp, 30h
0x1400165c6  mov     rbx, rdx
0x1400165c9  mov     rdi, rcx
0x1400165cc  mov     [rbp+var_10], 0
0x1400165d3  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400165da  lea     r14, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400165e1  mov     rcx, r14
0x1400165e4  mov     rax, [rax+18h]
0x1400165e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400165ed  add     rax, 18h
0x1400165f1  mov     [rbx], rax
0x1400165f4  lea     rdx, aGrantTypeRefre; "grant_type=refresh_token"
0x1400165fb  mov     rcx, rbx
0x1400165fe  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140016603  test    al, al
0x140016605  jnz     short loc_14001661D
0x140016607  mov     r8d, 18h
0x14001660d  lea     rdx, aGrantTypeRefre; "grant_type=refresh_token"
0x140016614  mov     rcx, rbx
0x140016617  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001661c  nop
0x14001661d  mov     [rbp+var_10], 1
0x140016624  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001662b  mov     rcx, r14
0x14001662e  mov     rax, [rax+18h]
0x140016632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016637  add     rax, 18h
0x14001663b  mov     [rbp+arg_10], rax
0x14001663f  lea     rdx, aRefreshToken; "refresh_token"
0x140016646  lea     rcx, [rbp+arg_10]
0x14001664a  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14001664f  test    al, al
0x140016651  jnz     short loc_14001666A
0x140016653  mov     r8d, 0Dh
0x140016659  lea     rdx, aRefreshToken; "refresh_token"
0x140016660  lea     rcx, [rbp+arg_10]
0x140016664  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140016669  nop
0x14001666a  lea     r8, [rdi+30h]
0x14001666e  lea     rdx, [rbp+arg_10]
0x140016672  mov     rcx, rbx
0x140016675  call    ?AddQueryString@StringUtility@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV23@1@Z; StringUtility::AddQueryString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001667a  nop
0x14001667b  mov     rdx, [rbp+arg_10]
0x14001667f  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140016683  or      esi, 0FFFFFFFFh
0x140016686  mov     eax, esi
0x140016688  lock xadd [rdx+10h], eax
0x14001668d  add     eax, esi
0x14001668f  test    eax, eax
0x140016691  jg      short loc_1400166A2
0x140016693  mov     rcx, [rdx]
0x140016696  mov     rax, [rcx]
0x140016699  mov     rax, [rax+8]
0x14001669d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400166a2  mov     rdx, [rdi+8]
0x1400166a6  add     rdx, 18h
0x1400166aa  lea     rcx, [rbp+arg_18]
0x1400166ae  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400166b3  mov     [rbp+var_10], 3
0x1400166ba  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400166c1  mov     rcx, r14
0x1400166c4  mov     rax, [rax+18h]
0x1400166c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400166cd  add     rax, 18h
0x1400166d1  mov     [rbp+arg_10], rax
0x1400166d5  lea     rdx, aRedirectUri; "redirect_uri"
0x1400166dc  lea     rcx, [rbp+arg_10]
0x1400166e0  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x1400166e5  test    al, al
0x1400166e7  jnz     short loc_140016700
0x1400166e9  mov     r8d, 0Ch
0x1400166ef  lea     rdx, aRedirectUri; "redirect_uri"
0x1400166f6  lea     rcx, [rbp+arg_10]
0x1400166fa  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400166ff  nop
0x140016700  lea     r8, [rbp+arg_18]
0x140016704  lea     rdx, [rbp+arg_10]
0x140016708  mov     rcx, rbx
0x14001670b  call    ?AddQueryString@StringUtility@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV23@1@Z; StringUtility::AddQueryString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140016710  nop
0x140016711  mov     rdx, [rbp+arg_10]
0x140016715  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140016719  mov     eax, esi
0x14001671b  lock xadd [rdx+10h], eax
0x140016720  add     eax, esi
0x140016722  test    eax, eax
0x140016724  jg      short loc_140016736
0x140016726  mov     rcx, [rdx]
0x140016729  mov     rax, [rcx]
0x14001672c  mov     rax, [rax+8]
0x140016730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016735  nop
0x140016736  mov     rdx, [rbp+arg_18]
0x14001673a  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001673e  mov     eax, esi
0x140016740  lock xadd [rdx+10h], eax
0x140016745  add     eax, esi
0x140016747  test    eax, eax
0x140016749  jg      short loc_14001675A
0x14001674b  mov     rcx, [rdx]
0x14001674e  mov     rax, [rcx]
0x140016751  mov     rax, [rax+8]
0x140016755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001675a  mov     rdx, [rdi+8]
0x14001675e  add     rdx, 10h
0x140016762  lea     rcx, [rbp+arg_18]
0x140016766  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001676b  mov     [rbp+var_10], 7
0x140016772  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140016779  mov     rcx, r14
0x14001677c  mov     rax, [rax+18h]
0x140016780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016785  add     rax, 18h
0x140016789  mov     [rbp+arg_10], rax
0x14001678d  lea     rdx, aClientId; "client_id"
0x140016794  lea     rcx, [rbp+arg_10]
0x140016798  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14001679d  test    al, al
0x14001679f  jnz     short loc_1400167B8
0x1400167a1  mov     r8d, 9
0x1400167a7  lea     rdx, aClientId; "client_id"
0x1400167ae  lea     rcx, [rbp+arg_10]
0x1400167b2  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400167b7  nop
0x1400167b8  lea     r8, [rbp+arg_18]
0x1400167bc  lea     rdx, [rbp+arg_10]
0x1400167c0  mov     rcx, rbx
0x1400167c3  call    ?AddQueryString@StringUtility@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV23@1@Z; StringUtility::AddQueryString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400167c8  nop
0x1400167c9  mov     rdx, [rbp+arg_10]
0x1400167cd  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400167d1  mov     eax, esi
0x1400167d3  lock xadd [rdx+10h], eax
0x1400167d8  add     eax, esi
0x1400167da  test    eax, eax
0x1400167dc  jg      short loc_1400167EE
0x1400167de  mov     rcx, [rdx]
0x1400167e1  mov     rax, [rcx]
0x1400167e4  mov     rax, [rax+8]
0x1400167e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400167ed  nop
0x1400167ee  mov     rdx, [rbp+arg_18]
0x1400167f2  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400167f6  mov     eax, esi
0x1400167f8  lock xadd [rdx+10h], eax
0x1400167fd  add     eax, esi
0x1400167ff  test    eax, eax
0x140016801  jg      short loc_140016812
0x140016803  mov     rcx, [rdx]
0x140016806  mov     rax, [rcx]
0x140016809  mov     rax, [rax+8]
0x14001680d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016812  cmp     byte ptr [rdi+38h], 0
0x140016816  jz      short loc_140016893
0x140016818  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001681f  mov     rcx, r14
0x140016822  mov     rax, [rax+18h]
0x140016826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001682b  add     rax, 18h
0x14001682f  mov     [rbp+arg_10], rax
0x140016833  lea     rdx, aResource; "resource"
0x14001683a  lea     rcx, [rbp+arg_10]
0x14001683e  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140016843  test    al, al
0x140016845  jnz     short loc_14001685E
0x140016847  mov     r8d, 8
0x14001684d  lea     rdx, aResource; "resource"
0x140016854  lea     rcx, [rbp+arg_10]
0x140016858  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001685d  nop
0x14001685e  lea     r8, [rdi+10h]
0x140016862  lea     rdx, [rbp+arg_10]
0x140016866  mov     rcx, rbx
0x140016869  call    ?AddQueryString@StringUtility@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV23@1@Z; StringUtility::AddQueryString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001686e  nop
0x14001686f  mov     rdx, [rbp+arg_10]
0x140016873  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140016877  mov     eax, esi
0x140016879  lock xadd [rdx+10h], eax
0x14001687e  add     eax, esi
0x140016880  test    eax, eax
0x140016882  jg      short loc_140016893
0x140016884  mov     rcx, [rdx]
0x140016887  mov     rax, [rcx]
0x14001688a  mov     rax, [rax+8]
0x14001688e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016893  mov     rax, rbx
0x140016896  add     rsp, 30h
0x14001689a  pop     r14
0x14001689c  pop     rdi
0x14001689d  pop     rsi
0x14001689e  pop     rbx
0x14001689f  pop     rbp
0x1400168a0  retn
```
