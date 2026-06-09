# OAuthTokenRequestBase::ProcessTokenRequest(std::unique_ptr<WebRequest,std::default_delete<WebRequest>> const &,CSecureString const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x140014ea4`
- end: `0x140015b10`
- name: `?ProcessTokenRequest@OAuthTokenRequestBase@@IEAA_NAEBV?$unique_ptr@VWebRequest@@U?$default_delete@VWebRequest@@@std@@@std@@AEBVCSecureString@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `3180`
- prototype: `__int64 __fastcall(struct OAuthTokenRequestBase *)`
- caller_count: `2`
- callee_count: `29`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x14001604c`
- `0x140018000`

## callees

- `0x1400028ac`
- `0x140005458`
- `0x1400054e8`
- `0x14000579c`
- `0x140005c80`
- `0x1400061dc`
- `0x140007bf8`
- `0x14000813c`
- `0x140009518`
- `0x14000c13c`
- `0x14000c384`
- `0x14000c7d8`
- `0x14000d310`
- `0x14000e000`
- `0x14000f978`
- `0x140014498`
- `0x140014730`
- `0x140014988`
- `0x140014ea4`
- `0x1400223d0`
- `0x1400224fc`
- `0x14002266c`
- `0x140022b14`
- `0x140022bd8`
- `0x140022f3c`
- `0x1400231f8`
- `0x140024ee8`
- `0x14002c3e8`
- `0x140030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1400155b4`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1400155db`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1400155b4`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1400155db`

## string_xrefs

- `0x140014eeb`: `Webrequest opening connection`
- `0x140015439`: `Token response is not successfull. Status:%hu ResponseText:%s`

## pseudocode

```c
// Hidden C++ exception states: #wind=36
char __fastcall OAuthTokenRequestBase::ProcessTokenRequest(
        struct OAuthTokenRequestBase *a1,
        __int64 *a2,
        __int64 *a3,
        __int64 *a4)
{
  OAuthTokenRequestBase *v7; // r14
  __int64 v8; // rbx
  __int64 v9; // rsi
  OAuthTokenRequestBase **v10; // rdx
  _QWORD *v11; // rdx
  __int64 v12; // r15
  wchar_t *v13; // rdx
  volatile signed __int32 *v14; // rdx
  __int64 v15; // r15
  OAuthTokenRequestBase **v16; // rdx
  _WORD *v17; // rdx
  __int64 v18; // r15
  volatile signed __int32 *v19; // rdx
  OAuthTokenRequestBase **v20; // rdx
  __int64 v21; // r15
  const wchar_t *v22; // rdx
  volatile signed __int32 *v23; // rdx
  OAuthTokenRequestBase **v24; // rdx
  volatile signed __int32 **v25; // r15
  volatile signed __int32 *v26; // rdx
  volatile signed __int32 *v27; // rdx
  struct WebRequest *v28; // r15
  OAuthTokenRequestBase **v29; // rdx
  _QWORD *v30; // rax
  void *v31; // r15
  __int64 *v32; // rax
  volatile signed __int32 *v33; // rdx
  wchar_t *v34; // rcx
  void *v35; // r15
  __int64 Lower; // rax
  _QWORD *v37; // rax
  volatile signed __int32 *v38; // rdx
  wchar_t *v39; // rax
  wchar_t *v40; // rax
  char v41; // r15
  __int64 *v42; // rax
  volatile signed __int32 *v43; // rdx
  __int64 v44; // rcx
  volatile signed __int32 *v45; // r15
  volatile signed __int32 *v46; // rdx
  _QWORD *v47; // r12
  _QWORD *v48; // rax
  wchar_t *v49; // rdx
  void **v50; // r12
  OAuthTokenRequestBase **v51; // rdx
  volatile signed __int32 ***v52; // rdx
  _QWORD *v53; // r13
  volatile signed __int32 *v54; // r12
  OAuthTokenRequestBase **v55; // rbx
  volatile signed __int32 *v56; // rdx
  volatile signed __int32 *v57; // rdx
  volatile signed __int32 *v58; // rdx
  OAuthTokenRequestBase *v60; // rbx
  const struct Exception *v61; // rdx
  volatile signed __int32 *v62; // [rsp+38h] [rbp-110h] BYREF
  OAuthTokenRequestBase **v63; // [rsp+40h] [rbp-108h] BYREF
  wchar_t *Str; // [rsp+48h] [rbp-100h] BYREF
  volatile signed __int32 *v65; // [rsp+50h] [rbp-F8h] BYREF
  void *Block; // [rsp+58h] [rbp-F0h] BYREF
  volatile signed __int32 ***v67; // [rsp+60h] [rbp-E8h] BYREF
  volatile signed __int32 **v68; // [rsp+68h] [rbp-E0h] BYREF
  __int64 v69; // [rsp+70h] [rbp-D8h] BYREF
  unsigned int *v70; // [rsp+78h] [rbp-D0h]
  const HttpException *v71; // [rsp+80h] [rbp-C8h] BYREF
  const Exception *v72; // [rsp+88h] [rbp-C0h] BYREF
  _BYTE pExceptionObject[16]; // [rsp+90h] [rbp-B8h] BYREF
  _BYTE v74[32]; // [rsp+A0h] [rbp-A8h] BYREF
  __int16 v75; // [rsp+C0h] [rbp-88h]
  __int64 v76; // [rsp+C8h] [rbp-80h] BYREF
  _QWORD v77[2]; // [rsp+D0h] [rbp-78h] BYREF
  __int64 v78; // [rsp+E0h] [rbp-68h] BYREF
  __int64 v79; // [rsp+E8h] [rbp-60h] BYREF
  __int64 v80; // [rsp+F0h] [rbp-58h] BYREF
  char v81; // [rsp+F8h] [rbp-50h]
  int v82; // [rsp+FCh] [rbp-4Ch]
  char v83; // [rsp+100h] [rbp-48h]
  __int64 v84[2]; // [rsp+108h] [rbp-40h] BYREF
  __int64 v85; // [rsp+118h] [rbp-30h]
  OAuthTokenRequestBase *v86; // [rsp+150h] [rbp+8h] BYREF
  __int64 *v87; // [rsp+168h] [rbp+20h]

  v87 = a4;
  v86 = a1;
  try
  {
    v7 = a1;
    *((_BYTE *)a1 + 136) = 0;
    v70 = (unsigned int *)((char *)a1 + 60);
    *((_DWORD *)a1 + 15) = -895418323;
    Log::Verbose(a1, L"Webrequest opening connection");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v67,
      a4);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v69,
      (__int64 *)(*((_QWORD *)v7 + 1) + 64LL));
    v8 = v69;
    if ( *(_DWORD *)(v69 - 16) )
    {
      ATL::CSimpleStringT<unsigned short,0>::Append((__int64 *)&v67, (__int64)L"?", 1);
      ATL::CSimpleStringT<unsigned short,0>::Append((__int64 *)&v67, v8, *(unsigned int *)(v8 - 16));
    }
    v9 = *a2;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &Block,
      (__int64 *)(*((_QWORD *)v7 + 1) + 40LL));
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v63,
      (__int64)v67);
    WebRequest::Open(v9, &WebRequest::MethodPost, &v63, &Block);
    v10 = v63 - 3;
    if ( _InterlockedDecrement((volatile signed __int32 *)v63 - 2) <= 0 )
      (*(void (__fastcall **)(OAuthTokenRequestBase *))(*(_QWORD *)*v10 + 8LL))(*v10);
    v11 = (char *)Block - 24;
    if ( _InterlockedDecrement((volatile signed __int32 *)Block - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 8LL))(*v11);
    v12 = *a2;
    v62 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
            (void *const *)&v62,
            (__int64)L"application/x-www-form-urlencoded") )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v62, L"application/x-www-form-urlencoded", 33);
    Str = (wchar_t *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
            (void *const *)&Str,
            (__int64)L"Content-Type") )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&Str, L"Content-Type", 12);
    WebRequest::SetRequestHeader(v12, &Str, &v62);
    v13 = Str - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)Str - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v13 + 8LL))(*(_QWORD *)v13);
    v14 = v62 - 6;
    if ( _InterlockedDecrement(v62 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v14 + 8LL))(*(_QWORD *)v14);
    v15 = *a2;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v63,
      (__int64 *)(*((_QWORD *)v7 + 1) + 72LL));
    WebRequest::SetAdditionalRequestHeaders(v15, &v63);
    v16 = v63 - 3;
    if ( _InterlockedDecrement((volatile signed __int32 *)v63 - 2) <= 0 )
      (*(void (__fastcall **)(OAuthTokenRequestBase *))(*(_QWORD *)*v16 + 8LL))(*v16);
    v17 = (_WORD *)*((_QWORD *)v7 + 3);
    if ( *v17 && *((_DWORD *)v17 - 4) == 36 )
    {
      v18 = *a2;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v63,
        (__int64)v17);
      v62 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
      if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
              (void *const *)&v62,
              (__int64)L"client-request-id") )
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v62, L"client-request-id", 17);
      WebRequest::SetRequestHeader(v18, &v62, &v63);
      v19 = v62 - 6;
      if ( _InterlockedDecrement(v62 - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v19 + 8LL))(*(_QWORD *)v19);
      v20 = v63 - 3;
      if ( _InterlockedDecrement((volatile signed __int32 *)v63 - 2) <= 0 )
        (*(void (__fastcall **)(OAuthTokenRequestBase *))(*(_QWORD *)*v20 + 8LL))(*v20);
      v21 = *a2;
      v22 = L"true";
      if ( !*((_BYTE *)v7 + 80) )
        v22 = L"false";
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v63,
        (__int64)v22);
      v62 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
      if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
              (void *const *)&v62,
              (__int64)L"return-client-request-id") )
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v62, L"return-client-request-id", 24);
      WebRequest::SetRequestHeader(v21, &v62, &v63);
      v23 = v62 - 6;
      if ( _InterlockedDecrement(v62 - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v23 + 8LL))(*(_QWORD *)v23);
      v24 = v63 - 3;
      if ( _InterlockedDecrement((volatile signed __int32 *)v63 - 2) <= 0 )
        (*(void (__fastcall **)(OAuthTokenRequestBase *))(*(_QWORD *)*v24 + 8LL))(*v24);
    }
    v68 = &v62;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v62,
      (__int64 *)(*((_QWORD *)v7 + 1) + 40LL));
    Block = &v62;
    v25 = (volatile signed __int32 **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                                        &v63,
                                        v87);
    v68 = v25;
    Log::InfoInternal((__int64)v7, 0x4AA90010u, 0x4AAE0005u, *v25, v62);
    v26 = *v25 - 6;
    if ( _InterlockedDecrement(v26 + 4) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v26 + 8LL))(*(_QWORD *)v26);
    v27 = v62 - 6;
    if ( _InterlockedDecrement(v62 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v27 + 8LL))(*(_QWORD *)v27);
    v28 = (struct WebRequest *)*a2;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v63,
      *a3);
    WebRequest::Send(v28);
    v29 = v63 - 3;
    if ( _InterlockedDecrement((volatile signed __int32 *)v63 - 2) <= 0 )
      (*(void (__fastcall **)(OAuthTokenRequestBase *))(*(_QWORD *)*v29 + 8LL))(*v29);
    if ( *(_WORD *)(*a2 + 88) != 4 )
    {
      Log::Verbose(v7, L"Webrequest has invalid state");
      InvalidCallException::InvalidCallException((InvalidCallException *)pExceptionObject, -895418365);
      throw (InvalidCallException *)pExceptionObject;
    }
    Log::Verbose(v7, L"Webrequest has valid state");
    WebRequest::GetHeaderValue(*a2, &v63, L"client-request-id");
    if ( *((_DWORD *)v63 - 4) )
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        (_QWORD *)v7 + 11,
        &v63);
    Log::Verbose(v7, L"WebRequest Status:%hu", *(unsigned __int16 *)(*a2 + 92));
    if ( *(_WORD *)(*a2 + 92) != 200 )
    {
      v30 = (_QWORD *)WebRequest::ResponseText(*a2, &v65);
      Log::Verbose(
        v7,
        L"Token response is not successfull. Status:%hu ResponseText:%s",
        *(unsigned __int16 *)(*a2 + 92),
        *v30);
      CSecureString::~CSecureString((CSecureString *)&v65);
    }
    WebRequest::GetResponseHeaders(*a2, &Block);
    v31 = Block;
    v62 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
            (void *const *)&v62,
            (__int64)L"WWW-Authenticate") )
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v62, L"WWW-Authenticate", 16);
    v32 = (__int64 *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::operator[](
                       v31,
                       &v62);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &Str,
      v32);
    v33 = v62 - 6;
    if ( _InterlockedDecrement(v62 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v33 + 8LL))(*(_QWORD *)v33);
    v34 = Str;
    if ( !*((_DWORD *)Str - 4) )
    {
      v35 = Block;
      v65 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
      if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
              (void *const *)&v65,
              (__int64)L"WWW-Authenticate") )
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v65, L"WWW-Authenticate", 16);
      Lower = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(&v65);
      v37 = (_QWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::operator[](
                        v35,
                        Lower);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        &Str,
        v37);
      v38 = v65 - 6;
      if ( _InterlockedDecrement(v65 - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v38 + 8LL))(*(_QWORD *)v38);
      v34 = Str;
    }
    if ( *(_WORD *)(*a2 + 92) == 401
      && *((int *)v34 - 4) >= 1
      && (v39 = wcsstr(v34, L"PKeyAuth")) != 0
      && (int)(v39 - Str) > -1
      && *((int *)Str - 4) >= 0
      && (v40 = wcsstr(Str, L"Context")) != 0
      && (int)(v40 - Str) > 0 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        (_QWORD *)v7 + 12,
        &Str);
      v41 = 0;
      Log::Verbose(v7, L"Webrequest returns PkeyAuth challange");
    }
    else if ( *(_WORD *)(*a2 + 92) < 0x1F4u )
    {
      v42 = (__int64 *)WebRequest::ResponseText(*a2, &v68);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v65,
        *v42);
      OAuthResponse::OAuthResponse(
        (unsigned int)v74,
        (_DWORD)v7,
        (_DWORD)v7 + 24,
        *(unsigned __int16 *)(*a2 + 92),
        (__int64)&v65);
      v43 = v65 - 6;
      if ( _InterlockedDecrement(v65 - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v43 + 8LL))(*(_QWORD *)v43);
      CSecureString::~CSecureString((CSecureString *)&v68);
      if ( v75 == 200 )
      {
        Log::Verbose(v7, L"Webrequest returns success for oauth response");
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
          (_QWORD *)v7 + 4,
          &v76);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
          (_QWORD *)v7 + 6,
          v77);
        *((_QWORD *)v7 + 5) = v77[1];
        *((_BYTE *)v7 + 56) = v81;
        v44 = v85;
        if ( v85 )
        {
          _InterlockedIncrement((volatile signed __int32 *)(v85 + 8));
          v44 = v85;
        }
        *((_QWORD *)v7 + 13) = v84[1];
        v45 = (volatile signed __int32 *)*((_QWORD *)v7 + 14);
        *((_QWORD *)v7 + 14) = v44;
        if ( v45 )
        {
          if ( _InterlockedExchangeAdd(v45 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v45)(v45);
            if ( _InterlockedExchangeAdd(v45 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 8LL))(v45);
          }
        }
        *((_DWORD *)v7 + 30) = v82;
        *((_BYTE *)v7 + 124) = v83;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v62,
          v84);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
          (_QWORD *)v7 + 16,
          &v62);
        v46 = v62 - 6;
        if ( _InterlockedDecrement(v62 - 2) <= 0 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v46 + 8LL))(*(_QWORD *)v46);
        *((_DWORD *)v7 + 15) = 0;
        ATL::CSimpleStringT<unsigned short,0>::SetString((char *)v7 + 64, &dword_14003353C, 0);
        ATL::CSimpleStringT<unsigned short,0>::SetString((char *)v7 + 72, &dword_14003353C, 0);
        AuthenticationContext::Update(*((AuthenticationContext **)v7 + 1), v7);
        v41 = 1;
      }
      else
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
          (_QWORD *)v7 + 8,
          &v78);
        v47 = (_QWORD *)((char *)v7 + 72);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
          (_QWORD *)v7 + 9,
          &v79);
        if ( !*(_DWORD *)(*((_QWORD *)v7 + 8) - 16LL) && !*(_DWORD *)(*v47 - 16LL) )
        {
          v48 = (_QWORD *)WebRequest::ResponseText(*a2, &v62);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
            (_QWORD *)v7 + 9,
            v48);
          CSecureString::~CSecureString((CSecureString *)&v62);
          ATL::CSimpleStringT<unsigned short,0>::SetString((char *)v7 + 64, L"authentication_failed", 21);
        }
        *((_DWORD *)v7 + 15) = OAuthTokenRequestBase::GetErrorCodeForOAuthError((const wchar_t **)v7 + 8);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
          (_QWORD *)v7 + 11,
          &v80);
        Log::Verbose(v7, L"Webrequest returns error code:%s and error description:%s", *((_QWORD *)v7 + 8), *v47);
        v41 = 0;
      }
      OAuthResponse::~OAuthResponse((OAuthResponse *)v74);
    }
    else
    {
      Log::Verbose(v7, L"Set to fatal network error since status code >= 500");
      v41 = 0;
      *((_BYTE *)v7 + 136) = 1;
    }
    v49 = Str - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)Str - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v49 + 8LL))(*(_QWORD *)v49);
    v50 = (void **)Block;
    if ( Block )
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,void *>>>(
        (__int64)Block,
        (__int64)Block,
        *(__int64 **)(*(_QWORD *)Block + 8LL));
      operator delete(*v50);
      operator delete(v50);
    }
    v51 = v63 - 3;
    if ( _InterlockedDecrement((volatile signed __int32 *)v63 - 2) <= 0 )
      (*(void (__fastcall **)(OAuthTokenRequestBase *))(*(_QWORD *)*v51 + 8LL))(*v51);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v8 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v8 - 24) + 8LL))(*(_QWORD *)(v8 - 24));
    v52 = v67 - 3;
    if ( _InterlockedDecrement((volatile signed __int32 *)v67 - 2) <= 0 )
      (*((void (__fastcall **)(volatile signed __int32 **))**v52 + 1))(*v52);
  }
  catch ( const HttpException *v71 )
  {
    v60 = v86;
    Log::Verbose(v86, L"Setting http exception fields");
    v61 = v71;
    *((_BYTE *)v60 + 136) = *((_BYTE *)v71 + 24);
    OAuthTokenRequestBase::SetExceptionFields(v60, v61);
    v41 = 0;
    v7 = v86;
    goto LABEL_94;
  }
  catch ( const Exception *v72 )
  {
    OAuthTokenRequestBase::SetExceptionFields(v86, v72);
    v41 = 0;
    v7 = v86;
    goto LABEL_94;
  }
  if ( v41 )
  {
    Log::InfoInternal((__int64)v7, 0x4AA9000Fu, 0);
  }
  else
  {
LABEL_94:
    v63 = &v86;
    v53 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &v86,
            (__int64 *)v7 + 11);
    Block = v53;
    v67 = &v68;
    v54 = (volatile signed __int32 *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                                       &v68,
                                       (__int64 *)v7 + 9);
    v65 = v54;
    v55 = (OAuthTokenRequestBase **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                                      &v69,
                                      v87);
    v63 = v55;
    Log::ErrorInternal((__int64)v7, *v70, 0x4AAE0017u, *v55, *(_QWORD *)v54, *v53);
    v56 = (volatile signed __int32 *)((char *)*v55 - 24);
    if ( _InterlockedDecrement(v56 + 4) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v56 + 8LL))(*(_QWORD *)v56);
    v57 = (volatile signed __int32 *)(*(_QWORD *)v54 - 24LL);
    if ( _InterlockedDecrement(v57 + 4) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v57 + 8LL))(*(_QWORD *)v57);
    v58 = (volatile signed __int32 *)(*v53 - 24LL);
    if ( _InterlockedDecrement(v58 + 4) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v58 + 8LL))(*(_QWORD *)v58);
  }
  return v41;
}

```

## disassembly

```asm
0x140014ea4  mov     rax, rsp
0x140014ea7  mov     [rax+10h], rbx
0x140014eab  mov     [rax+18h], rsi
0x140014eaf  mov     [rax+20h], r9
0x140014eb3  mov     [rax+8], rcx
0x140014eb7  push    rdi
0x140014eb8  push    r12
0x140014eba  push    r13
0x140014ebc  push    r14
0x140014ebe  push    r15
0x140014ec0  sub     rsp, 120h
0x140014ec7  mov     rbx, r9
0x140014eca  mov     r12, r8
0x140014ecd  mov     r13, rdx
0x140014ed0  mov     r14, rcx
0x140014ed3  xor     edi, edi
0x140014ed5  mov     [rcx+88h], dil
0x140014edc  lea     rax, [rcx+3Ch]
0x140014ee0  mov     [rsp+148h+var_D0], rax
0x140014ee5  mov     dword ptr [rax], 0CAA1002Dh
0x140014eeb  lea     rdx, aWebrequestOpen; "Webrequest opening connection"
0x140014ef2  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x140014ef7  mov     rdx, rbx
0x140014efa  lea     rcx, [rsp+148h+var_E8]
0x140014eff  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140014f04  nop
0x140014f05  mov     rdx, [r14+8]
0x140014f09  add     rdx, 40h ; '@'
0x140014f0d  lea     rcx, [rsp+148h+var_D8]
0x140014f12  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140014f17  nop
0x140014f18  mov     rbx, [rsp+148h+var_D8]
0x140014f1d  cmp     [rbx-10h], edi
0x140014f20  jz      short loc_140014F48
0x140014f22  lea     r8d, [rdi+1]
0x140014f26  lea     rdx, asc_140034D04; "?"
0x140014f2d  lea     rcx, [rsp+148h+var_E8]
0x140014f32  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x140014f37  mov     r8d, [rbx-10h]
0x140014f3b  mov     rdx, rbx
0x140014f3e  lea     rcx, [rsp+148h+var_E8]
0x140014f43  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x140014f48  mov     rsi, [r13+0]
0x140014f4c  mov     rdx, [r14+8]
0x140014f50  add     rdx, 28h ; '('
0x140014f54  lea     rcx, [rsp+148h+Block]
0x140014f59  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140014f5e  nop
0x140014f5f  mov     rdx, [rsp+148h+var_E8]
0x140014f64  lea     rcx, [rsp+148h+var_108]
0x140014f69  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140014f6e  nop
0x140014f6f  lea     r9, [rsp+148h+Block]
0x140014f74  lea     r8, [rsp+148h+var_108]
0x140014f79  lea     rdx, ?MethodPost@WebRequest@@2V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@B; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const WebRequest::MethodPost
0x140014f80  mov     rcx, rsi
0x140014f83  call    ?Open@WebRequest@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@00_NP6AX_KJ@Z@Z; WebRequest::Open(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool,void (*)(unsigned __int64,long))
0x140014f88  nop
0x140014f89  mov     rdx, [rsp+148h+var_108]
0x140014f8e  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140014f92  or      esi, 0FFFFFFFFh
0x140014f95  mov     eax, esi
0x140014f97  lock xadd [rdx+10h], eax
0x140014f9c  add     eax, esi
0x140014f9e  test    eax, eax
0x140014fa0  jg      short loc_140014FB2
0x140014fa2  mov     rcx, [rdx]
0x140014fa5  mov     rax, [rcx]
0x140014fa8  mov     rax, [rax+8]
0x140014fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014fb1  nop
0x140014fb2  mov     rdx, [rsp+148h+Block]
0x140014fb7  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140014fbb  mov     eax, esi
0x140014fbd  lock xadd [rdx+10h], eax
0x140014fc2  add     eax, esi
0x140014fc4  test    eax, eax
0x140014fc6  jg      short loc_140014FD7
0x140014fc8  mov     rcx, [rdx]
0x140014fcb  mov     rax, [rcx]
0x140014fce  mov     rax, [rax+8]
0x140014fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014fd7  mov     r15, [r13+0]
0x140014fdb  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140014fe2  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140014fe9  mov     rax, [rax+18h]
0x140014fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014ff2  add     rax, 18h
0x140014ff6  mov     [rsp+148h+var_110], rax
0x140014ffb  lea     rdx, aApplicationXWw; "application/x-www-form-urlencoded"
0x140015002  lea     rcx, [rsp+148h+var_110]
0x140015007  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14001500c  test    al, al
0x14001500e  jnz     short loc_140015028
0x140015010  mov     r8d, 21h ; '!'
0x140015016  lea     rdx, aApplicationXWw; "application/x-www-form-urlencoded"
0x14001501d  lea     rcx, [rsp+148h+var_110]
0x140015022  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140015027  nop
0x140015028  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001502f  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140015036  mov     rax, [rax+18h]
0x14001503a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001503f  add     rax, 18h
0x140015043  mov     [rsp+148h+Str], rax
0x140015048  lea     rdx, aContentType_0; "Content-Type"
0x14001504f  lea     rcx, [rsp+148h+Str]
0x140015054  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140015059  test    al, al
0x14001505b  jnz     short loc_140015075
0x14001505d  mov     r8d, 0Ch
0x140015063  lea     rdx, aContentType_0; "Content-Type"
0x14001506a  lea     rcx, [rsp+148h+Str]
0x14001506f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140015074  nop
0x140015075  lea     r8, [rsp+148h+var_110]
0x14001507a  lea     rdx, [rsp+148h+Str]
0x14001507f  mov     rcx, r15
0x140015082  call    ?SetRequestHeader@WebRequest@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; WebRequest::SetRequestHeader(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140015087  nop
0x140015088  mov     rdx, [rsp+148h+Str]
0x14001508d  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140015091  mov     eax, esi
0x140015093  lock xadd [rdx+10h], eax
0x140015098  add     eax, esi
0x14001509a  test    eax, eax
0x14001509c  jg      short loc_1400150AE
0x14001509e  mov     rcx, [rdx]
0x1400150a1  mov     rax, [rcx]
0x1400150a4  mov     rax, [rax+8]
0x1400150a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400150ad  nop
0x1400150ae  mov     rdx, [rsp+148h+var_110]
0x1400150b3  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400150b7  mov     eax, esi
0x1400150b9  lock xadd [rdx+10h], eax
0x1400150be  add     eax, esi
0x1400150c0  test    eax, eax
0x1400150c2  jg      short loc_1400150D3
0x1400150c4  mov     rcx, [rdx]
0x1400150c7  mov     rax, [rcx]
0x1400150ca  mov     rax, [rax+8]
0x1400150ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400150d3  mov     r15, [r13+0]
0x1400150d7  mov     rdx, [r14+8]
0x1400150db  add     rdx, 48h ; 'H'
0x1400150df  lea     rcx, [rsp+148h+var_108]
0x1400150e4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400150e9  nop
0x1400150ea  lea     rdx, [rsp+148h+var_108]
0x1400150ef  mov     rcx, r15
0x1400150f2  call    ?SetAdditionalRequestHeaders@WebRequest@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebRequest::SetAdditionalRequestHeaders(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400150f7  nop
0x1400150f8  mov     rdx, [rsp+148h+var_108]
0x1400150fd  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140015101  mov     eax, esi
0x140015103  lock xadd [rdx+10h], eax
0x140015108  add     eax, esi
0x14001510a  test    eax, eax
0x14001510c  jg      short loc_14001511E
0x14001510e  mov     rcx, [rdx]
0x140015111  mov     rax, [rcx]
0x140015114  mov     rax, [rax+8]
0x140015118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001511d  nop
0x14001511e  mov     rdx, [r14+18h]
0x140015122  cmp     [rdx], di
0x140015125  jz      loc_1400152BF
0x14001512b  cmp     dword ptr [rdx-10h], 24h ; '$'
0x14001512f  jnz     loc_1400152BF
0x140015135  mov     r15, [r13+0]
0x140015139  lea     rcx, [rsp+148h+var_108]
0x14001513e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140015143  nop
0x140015144  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001514b  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140015152  mov     rax, [rax+18h]
0x140015156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001515b  add     rax, 18h
0x14001515f  mov     [rsp+148h+var_110], rax
0x140015164  lea     rdx, aClientRequestI; "client-request-id"
0x14001516b  lea     rcx, [rsp+148h+var_110]
0x140015170  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140015175  test    al, al
0x140015177  jnz     short loc_140015191
0x140015179  mov     r8d, 11h
0x14001517f  lea     rdx, aClientRequestI; "client-request-id"
0x140015186  lea     rcx, [rsp+148h+var_110]
0x14001518b  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140015190  nop
0x140015191  lea     r8, [rsp+148h+var_108]
0x140015196  lea     rdx, [rsp+148h+var_110]
0x14001519b  mov     rcx, r15
0x14001519e  call    ?SetRequestHeader@WebRequest@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; WebRequest::SetRequestHeader(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400151a3  nop
0x1400151a4  mov     rdx, [rsp+148h+var_110]
0x1400151a9  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400151ad  mov     eax, esi
0x1400151af  lock xadd [rdx+10h], eax
0x1400151b4  add     eax, esi
0x1400151b6  test    eax, eax
0x1400151b8  jg      short loc_1400151CA
0x1400151ba  mov     rcx, [rdx]
0x1400151bd  mov     rax, [rcx]
0x1400151c0  mov     rax, [rax+8]
0x1400151c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400151c9  nop
0x1400151ca  mov     rdx, [rsp+148h+var_108]
0x1400151cf  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400151d3  mov     eax, esi
0x1400151d5  lock xadd [rdx+10h], eax
0x1400151da  add     eax, esi
0x1400151dc  test    eax, eax
0x1400151de  jg      short loc_1400151EF
0x1400151e0  mov     rcx, [rdx]
0x1400151e3  mov     rax, [rcx]
0x1400151e6  mov     rax, [rax+8]
0x1400151ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400151ef  mov     r15, [r13+0]
0x1400151f3  lea     rax, aFalse; "false"
0x1400151fa  lea     rdx, aTrue; "true"
0x140015201  cmp     [r14+50h], dil
0x140015205  cmovz   rdx, rax
0x140015209  lea     rcx, [rsp+148h+var_108]
0x14001520e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140015213  nop
0x140015214  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001521b  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140015222  mov     rax, [rax+18h]
0x140015226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001522b  add     rax, 18h
0x14001522f  mov     [rsp+148h+var_110], rax
0x140015234  lea     rdx, aReturnClientRe; "return-client-request-id"
0x14001523b  lea     rcx, [rsp+148h+var_110]
0x140015240  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140015245  test    al, al
0x140015247  jnz     short loc_140015261
0x140015249  mov     r8d, 18h
0x14001524f  lea     rdx, aReturnClientRe; "return-client-request-id"
0x140015256  lea     rcx, [rsp+148h+var_110]
0x14001525b  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140015260  nop
0x140015261  lea     r8, [rsp+148h+var_108]
0x140015266  lea     rdx, [rsp+148h+var_110]
0x14001526b  mov     rcx, r15
0x14001526e  call    ?SetRequestHeader@WebRequest@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; WebRequest::SetRequestHeader(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140015273  nop
0x140015274  mov     rdx, [rsp+148h+var_110]
0x140015279  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001527d  mov     eax, esi
0x14001527f  lock xadd [rdx+10h], eax
0x140015284  add     eax, esi
0x140015286  test    eax, eax
0x140015288  jg      short loc_14001529A
0x14001528a  mov     rcx, [rdx]
0x14001528d  mov     rax, [rcx]
0x140015290  mov     rax, [rax+8]
0x140015294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015299  nop
0x14001529a  mov     rdx, [rsp+148h+var_108]
0x14001529f  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400152a3  mov     eax, esi
0x1400152a5  lock xadd [rdx+10h], eax
0x1400152aa  add     eax, esi
0x1400152ac  test    eax, eax
0x1400152ae  jg      short loc_1400152BF
0x1400152b0  mov     rcx, [rdx]
0x1400152b3  mov     rax, [rcx]
0x1400152b6  mov     rax, [rax+8]
0x1400152ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400152bf  lea     rax, [rsp+148h+var_110]
0x1400152c4  mov     [rsp+148h+var_E0], rax
0x1400152c9  mov     rdx, [r14+8]
0x1400152cd  add     rdx, 28h ; '('
0x1400152d1  lea     rcx, [rsp+148h+var_110]
0x1400152d6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400152db  lea     rax, [rsp+148h+var_110]
0x1400152e0  mov     [rsp+148h+Block], rax
0x1400152e5  mov     rdx, [rsp+148h+arg_18]
0x1400152ed  lea     rcx, [rsp+148h+var_108]
0x1400152f2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400152f7  mov     r15, rax
0x1400152fa  mov     [rsp+148h+var_E0], rax
0x1400152ff  mov     rcx, [rsp+148h+var_110]
0x140015304  mov     [rsp+148h+var_128], rcx
0x140015309  mov     r9, [rax]
0x14001530c  mov     edx, 4AA90010h
0x140015311  mov     r8d, 4AAE0005h
0x140015317  mov     rcx, r14
0x14001531a  call    ?InfoInternal@Log@@CAXPEBVILogContext@@KVResourceId@@ZZ; Log::InfoInternal(ILogContext const *,ulong,ResourceId,...)
0x14001531f  nop
0x140015320  mov     rdx, [r15]
0x140015323  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140015327  mov     eax, esi
0x140015329  lock xadd [rdx+10h], eax
0x14001532e  add     eax, esi
0x140015330  test    eax, eax
0x140015332  jg      short loc_140015344
0x140015334  mov     rcx, [rdx]
0x140015337  mov     rax, [rcx]
  ... truncated ...
```
