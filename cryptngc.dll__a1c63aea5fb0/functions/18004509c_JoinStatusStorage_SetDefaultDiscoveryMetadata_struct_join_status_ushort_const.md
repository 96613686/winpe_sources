# JoinStatusStorage::SetDefaultDiscoveryMetadata(struct_join_status *,ushort const *)

- ea: `0x18004509c`
- end: `0x180045e39`
- name: `?SetDefaultDiscoveryMetadata@JoinStatusStorage@@CAJPEAUstruct_join_status@@PEBG@Z`
- size: `3485`
- prototype: `static int(struct struct_join_status *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000c680`

## callees

- `0x180006620`
- `0x1800073c0`
- `0x18000bfc0`
- `0x18000c160`
- `0x18000c190`
- `0x18000ced0`
- `0x18000e248`
- `0x18000e298`
- `0x180019d40`
- `0x180027448`
- `0x18002918c`
- `0x18002bc58`
- `0x18002c23c`
- `0x18002e664`
- `0x18002e850`
- `0x180044364`
- `0x180044cd0`
- `0x180044ec0`
- `0x18004509c`
- `0x180045e40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800455d4`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800455d4`

## string_xrefs

- `0x180045bf1`: `WebAuthnServiceVersion`
- `0x180045aa3`: `DrsServiceVersion`
- `0x180045b0a`: `AccessTokenUrl`
- `0x180045c0b`: `DeviceManagementServiceVersion`
- `0x180045b6f`: `NgcServiceVersion`
- `0x180045b22`: `CdjServiceVersion`
- `0x1800452f0`: `https://login.microsoftonline.com/%s/oauth2/token`
- `0x1800452b2`: `https://login.microsoftonline.com/%s/oauth2/authorize`
- `0x180045347`: `https://enterpriseregistration.windows.net/EnrollmentServer/DeviceEnrollmentWebService.svc`
- `0x1800458f7`: `https://login.microsoftonline.com`

## pseudocode

```c
__int64 __fastcall JoinStatusStorage::SetDefaultDiscoveryMetadata(
        struct struct_join_status *a1,
        const unsigned __int16 *a2)
{
  wchar_t *v4; // r15
  unsigned __int16 *v5; // r13
  unsigned int v6; // ebx
  const unsigned __int16 *v7; // r14
  __int16 v8; // dx
  __int64 v9; // rsi
  __int64 v10; // r13
  const unsigned __int16 *v11; // rcx
  int DomainFromEmail; // eax
  const wchar_t *v13; // r8
  int v14; // r8d
  unsigned __int16 *v15; // rax
  int v16; // r8d
  int v17; // r8d
  int v18; // r8d
  int v19; // r8d
  int v20; // r8d
  int v21; // r8d
  int v22; // r8d
  int v23; // r8d
  int v24; // r8d
  int v25; // r8d
  int v26; // r8d
  unsigned __int64 v27; // rdx
  int BaseUrl; // eax
  wchar_t *v29; // r14
  wchar_t *v30; // rax
  const unsigned __int16 *v31; // rbx
  int v32; // r8d
  __int64 v33; // rax
  unsigned __int64 v34; // r13
  unsigned __int16 *v35; // rax
  const unsigned __int16 *v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // rax
  unsigned __int64 v40; // rbx
  __int64 v41; // rcx
  __int64 v42; // rax
  unsigned __int64 v43; // rbx
  __int64 v44; // rcx
  __int64 v45; // rax
  unsigned __int64 v46; // rbx
  const unsigned __int16 *v47; // rcx
  int v48; // r8d
  int v49; // r8d
  unsigned __int16 *v50; // rcx
  int v51; // r8d
  const unsigned __int16 *v52; // rcx
  wchar_t *v53; // r14
  __int16 v54; // dx
  __int64 v55; // rcx
  __int64 v56; // rax
  unsigned __int64 v57; // rbx
  int v58; // eax
  unsigned __int16 *v59; // rcx
  const unsigned __int16 *v60; // rcx
  unsigned __int16 *v61; // rcx
  const unsigned __int16 *v62; // rcx
  const unsigned __int16 *v63; // rcx
  unsigned __int16 *v65[2]; // [rsp+30h] [rbp-D0h] BYREF
  void *lpMem; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v67; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v68; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v69; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v70; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v71; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v72; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v73; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v74; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v75; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v76; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v77; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v78; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v79; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v80; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v81; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v82; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v83; // [rsp+100h] [rbp+0h]
  void *v84; // [rsp+108h] [rbp+8h]
  void *v85; // [rsp+110h] [rbp+10h]
  unsigned __int16 *v86; // [rsp+118h] [rbp+18h] BYREF
  unsigned __int16 *v87; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 *v88; // [rsp+128h] [rbp+28h] BYREF
  unsigned __int16 *v89; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 *v90; // [rsp+138h] [rbp+38h] BYREF
  unsigned __int16 *v91; // [rsp+180h] [rbp+80h] BYREF
  wchar_t *Str; // [rsp+190h] [rbp+90h] BYREF
  void *Block; // [rsp+198h] [rbp+98h] BYREF

  memset_0(&lpMem, 0, 0x100u);
  v4 = 0;
  Block = 0;
  v5 = 0;
  v91 = 0;
  Str = 0;
  v65[0] = 0;
  if ( *((_QWORD *)a1 + 9) )
  {
    if ( *((_QWORD *)a1 + 10) )
    {
      if ( *((_QWORD *)a1 + 11) )
      {
        if ( *((_QWORD *)a1 + 12) )
        {
          if ( *((_QWORD *)a1 + 13) )
          {
            if ( *((_QWORD *)a1 + 14) )
            {
              if ( *((_QWORD *)a1 + 15) )
              {
                if ( *((_QWORD *)a1 + 16) )
                {
                  if ( *((_QWORD *)a1 + 17) )
                  {
                    if ( *((_QWORD *)a1 + 18) )
                    {
                      if ( *((_QWORD *)a1 + 19) )
                      {
                        if ( *((_QWORD *)a1 + 20) )
                        {
                          if ( *((_QWORD *)a1 + 21) )
                          {
                            if ( *((_QWORD *)a1 + 22) )
                            {
                              if ( *((_QWORD *)a1 + 23) )
                              {
                                if ( *((_QWORD *)a1 + 24) )
                                {
                                  if ( *((_QWORD *)a1 + 25) )
                                  {
                                    if ( *((_QWORD *)a1 + 35) )
                                    {
                                      if ( *((_QWORD *)a1 + 36) )
                                      {
                                        if ( *((_QWORD *)a1 + 37) )
                                        {
                                          if ( *((_QWORD *)a1 + 38) )
                                          {
                                            v6 = 0;
                                            if ( *((_QWORD *)a1 + 39) )
                                              goto LABEL_127;
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  v7 = (const unsigned __int16 *)*((_QWORD *)a1 + 2);
  v9 = -1;
  if ( (unsigned int)IsEmptyString(v7) )
  {
    Logger::TraceWarning(L"%s: TenantId is empty.", L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
    if ( (unsigned int)IsEmptyString(*((const unsigned __int16 **)a1 + 3)) )
    {
      Logger::TraceWarning(L"%s: JoinUserEmail is empty.", L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
    }
    else
    {
      DomainFromEmail = GetDomainFromEmail(v11, (unsigned __int16 **)&Block, (unsigned __int64 *)v65);
      v6 = DomainFromEmail;
      if ( DomainFromEmail < 0 )
      {
        v13 = L"GetDomainFromEmail";
LABEL_31:
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"JoinStatusStorage::SetDefaultDiscoveryMetadata",
          v13,
          (unsigned int)DomainFromEmail);
        goto LABEL_127;
      }
      v7 = (const unsigned __int16 *)Block;
      v5 = v65[0];
    }
  }
  else
  {
    v10 = -1;
    do
      ++v10;
    while ( v7[v10] != v8 );
    v5 = (unsigned __int16 *)(v10 + 1);
  }
  if ( !(unsigned int)IsEmptyString(v7) )
  {
    v69 = (unsigned __int16 *)MIDL_user_allocate(2LL * (_QWORD)(v5 + 27));
    if ( !v69 )
    {
LABEL_35:
      v6 = -2147024882;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
      goto LABEL_127;
    }
    DomainFromEmail = StringCchPrintfW(
                        v69,
                        (unsigned __int64)(v5 + 27),
                        L"https://login.microsoftonline.com/%s/oauth2/authorize",
                        v7);
    v6 = DomainFromEmail;
    if ( DomainFromEmail < 0 )
      goto LABEL_37;
    v15 = (unsigned __int16 *)MIDL_user_allocate(2LL * (_QWORD)v5 + 100);
    v70 = v15;
    if ( !v15 )
      goto LABEL_35;
    DomainFromEmail = StringCchPrintfW(
                        v15,
                        (unsigned __int64)(v5 + 25),
                        L"https://login.microsoftonline.com/%s/oauth2/token",
                        v7);
    v6 = DomainFromEmail;
    if ( DomainFromEmail < 0 )
    {
LABEL_37:
      v13 = L"StringCchPrintfW";
      goto LABEL_31;
    }
  }
  DomainFromEmail = StringDup(L"1.0", &v91, v14);
  v6 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_41;
  lpMem = v91;
  v91 = 0;
  DomainFromEmail = StringDup(
                      L"https://enterpriseregistration.windows.net/EnrollmentServer/DeviceEnrollmentWebService.svc",
                      &v91,
                      v16);
  v6 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_41;
  v67 = v91;
  v91 = 0;
  DomainFromEmail = StringDup(L"urn:ms-drs:enterpriseregistration.windows.net", &v91, v17);
  v6 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_41;
  v68 = v91;
  v91 = 0;
  DomainFromEmail = StringDup(L"1.0", &v91, v18);
  v6 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_41;
  v71 = v91;
  v91 = 0;
  DomainFromEmail = StringDup(L"https://enterpriseregistration.windows.net/EnrollmentServer/device/", &v91, v19);
  v6 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_41;
  v72 = v91;
  v91 = 0;
  DomainFromEmail = StringDup(L"urn:ms-drs:enterpriseregistration.windows.net", &v91, v20);
  v6 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_41;
  v73 = v91;
  v91 = 0;
  DomainFromEmail = StringDup(L"1.0", &v91, v21);
  v6 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_41;
  v74 = v91;
  v91 = 0;
  DomainFromEmail = StringDup(L"https://enterpriseregistration.windows.net/EnrollmentServer/key/", &v91, v22);
  v6 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_41;
  v75 = v91;
  v91 = 0;
  DomainFromEmail = StringDup(L"urn:ms-drs:enterpriseregistration.windows.net", &v91, v23);
  v6 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_41;
  v76 = v91;
  v91 = 0;
  DomainFromEmail = StringDup(L"1.0", &v91, v24);
  v6 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_41;
  v77 = v91;
  v91 = 0;
  DomainFromEmail = StringDup(L"1.0", &v91, v25);
  v6 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_41;
  v80 = v91;
  v91 = 0;
  DomainFromEmail = StringDup(L"4.0", &v91, v26);
  v6 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_41;
  v85 = v91;
  v65[0] = *((unsigned __int16 **)a1 + 18);
  v65[1] = *((unsigned __int16 **)a1 + 15);
  v91 = 0;
  SafeFree(0);
  BaseUrl = GetBaseUrl((const unsigned __int16 **)v65, v27, &Str);
  v6 = BaseUrl;
  if ( BaseUrl < 0 )
  {
LABEL_54:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"JoinStatusStorage::SetDefaultDiscoveryMetadata",
      L"GetBaseUrl",
      (unsigned int)BaseUrl);
    v4 = Str;
    goto LABEL_127;
  }
  v4 = Str;
  v29 = Str;
  if ( (unsigned int)IsEmptyString(Str) )
  {
    Logger::TraceWarning(
      L"%s: Cannot parse NGC endpoint to get server string. Use default value.",
      L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
    v29 = L"https://enterpriseregistration.windows.net";
  }
  v30 = wcsstr(v29, L"://");
  v31 = v30 + 3;
  if ( !v30 )
    v31 = v29;
  if ( (unsigned int)IsEmptyString(v31) )
  {
    DomainFromEmail = StringDup(L"adrs/enterpriseregistration.windows.net", &v91, v32);
    v6 = DomainFromEmail;
    if ( DomainFromEmail >= 0 )
      goto LABEL_66;
LABEL_41:
    v13 = L"StringDup";
    goto LABEL_31;
  }
  v33 = -1;
  do
    ++v33;
  while ( v31[v33] );
  v34 = v33 + 7;
  v35 = (unsigned __int16 *)MIDL_user_allocate(2 * (v33 + 7));
  v91 = v35;
  if ( !v35 )
    goto LABEL_35;
  DomainFromEmail = StringCchPrintfW(v35, v34, L"adrs/%s", v31);
  v6 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_37;
LABEL_66:
  v36 = (const unsigned __int16 *)*((_QWORD *)a1 + 2);
  v86 = v91;
  v91 = 0;
  if ( (unsigned int)IsEmptyString(v36) )
  {
    Logger::TraceWarning(
      L"%s: Tenant ID is empty. Default WebAuthN and device management endpoint will not be set.",
      L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
  }
  else
  {
    v38 = -1;
    do
      ++v38;
    while ( v29[v38] );
    v39 = -1;
    do
      ++v39;
    while ( *(_WORD *)(v37 + 2 * v39) );
    v40 = v38 + v39 + 13;
    v91 = (unsigned __int16 *)MIDL_user_allocate(2 * v40);
    if ( !v91 )
      goto LABEL_35;
    DomainFromEmail = StringCchPrintfW(v91, v40, L"%s/webauthn/%s/", v29, *((_QWORD *)a1 + 2));
    v6 = DomainFromEmail;
    if ( DomainFromEmail < 0 )
      goto LABEL_37;
    v41 = -1;
    v78 = v91;
    do
      ++v41;
    while ( v29[v41] );
    v42 = -1;
    do
      ++v42;
    while ( *(_WORD *)(*((_QWORD *)a1 + 2) + 2 * v42) );
    v43 = v41 + v42 + 11;
    v91 = (unsigned __int16 *)MIDL_user_allocate(2 * v43);
    if ( !v91 )
      goto LABEL_35;
    DomainFromEmail = StringCchPrintfW(v91, v43, L"%s/manage/%s/", v29, *((_QWORD *)a1 + 2));
    v6 = DomainFromEmail;
    if ( DomainFromEmail < 0 )
      goto LABEL_37;
    v44 = -1;
    v81 = v91;
    do
      ++v44;
    while ( v29[v44] );
    v45 = -1;
    do
      ++v45;
    while ( *(_WORD *)(*((_QWORD *)a1 + 2) + 2 * v45) );
    v46 = v45 + v44 + 37;
    v91 = (unsigned __int16 *)MIDL_user_allocate(2 * v46);
    if ( !v91 )
      goto LABEL_35;
    DomainFromEmail = StringCchPrintfW(v91, v46, L"%s/EnrollmentServer/device/resource/%s/", v29, *((_QWORD *)a1 + 2));
    v6 = DomainFromEmail;
    if ( DomainFromEmail < 0 )
      goto LABEL_37;
    v83 = v91;
    v91 = 0;
  }
  if ( (unsigned int)IsEmptyString(*((const unsigned __int16 **)a1 + 19)) )
    v47 = L"urn:ms-drs:enterpriseregistration.windows.net";
  DomainFromEmail = StringDup(v47, &v91, v48);
  v6 = DomainFromEmail;
  if ( DomainFromEmail < 0 )
    goto LABEL_90;
  v50 = v91;
  v79 = v91;
  v91 = 0;
  DomainFromEmail = StringDup(v50, &v91, v49);
  v6 = DomainFromEmail;
  if ( DomainFromEmail < 0
    || (v82 = v91, v91 = 0, DomainFromEmail = StringDup(v79, &v91, v51), v6 = DomainFromEmail, DomainFromEmail < 0) )
  {
LABEL_90:
    v13 = L"StringDup";
    goto LABEL_31;
  }
  v84 = v91;
  v91 = 0;
  SafeFree(v4);
  v52 = (const unsigned __int16 *)*((_QWORD *)a1 + 12);
  Str = 0;
  BaseUrl = GetBaseUrl(v52, &Str);
  v6 = BaseUrl;
  if ( BaseUrl < 0 )
    goto LABEL_54;
  v4 = Str;
  v53 = Str;
  if ( (unsigned int)IsEmptyString(Str) )
  {
    Logger::TraceWarning(
      L"%s: Cannot parse AuthCodeUrl to get server string. Use default value.",
      L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
    v53 = L"https://login.microsoftonline.com";
  }
  if ( (unsigned int)IsEmptyString(*((const unsigned __int16 **)a1 + 2)) )
  {
    Logger::TraceWarning(
      L"%s: Tenant ID is empty. Default kerb endpoint will not be set.",
      L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
  }
  else
  {
    v56 = -1;
    do
      ++v56;
    while ( v53[v56] != v54 );
    do
      ++v9;
    while ( *(_WORD *)(v55 + 2 * v9) != v54 );
    v57 = v9 + v56 + 12;
    v91 = (unsigned __int16 *)MIDL_user_allocate(2 * v57);
    if ( !v91 )
      goto LABEL_35;
    DomainFromEmail = StringCchPrintfW(v91, v57, L"%s/%s/kerberos", v53, *((_QWORD *)a1 + 2));
    v6 = DomainFromEmail;
    if ( DomainFromEmail < 0 )
      goto LABEL_37;
    v87 = v91;
    v91 = 0;
  }
  v58 = IsEmptyString(*((const unsigned __int16 **)a1 + 15));
  v59 = v72;
  if ( !v58 )
    v59 = (unsigned __int16 *)*((_QWORD *)a1 + 15);
  if ( (unsigned int)IsEmptyString(v59) )
  {
    Logger::TraceWarning(
      L"%s: Device join endpoint is empty. Default device join endpoint for TSL will not be set.",
      L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
  }
  else
  {
    DomainFromEmail = GetCertAuthUrl(v60, &v91);
    v6 = DomainFromEmail;
    if ( DomainFromEmail < 0 )
      goto LABEL_109;
    v88 = v91;
    v91 = 0;
  }
  if ( (unsigned int)IsEmptyString(*((const unsigned __int16 **)a1 + 24)) )
    v61 = v81;
  if ( (unsigned int)IsEmptyString(v61) )
  {
    Logger::TraceWarning(
      L"%s: Device management endpoint is empty. Default device management endpoint for TSL will not be set.",
      L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
  }
  else
  {
    DomainFromEmail = GetCertAuthUrl(v62, &v91);
    v6 = DomainFromEmail;
    if ( DomainFromEmail < 0 )
      goto LABEL_109;
    v89 = v91;
    v91 = 0;
  }
  if ( !(unsigned int)IsEmptyString(v83) )
  {
    DomainFromEmail = GetCertAuthUrl(v63, &v91);
    v6 = DomainFromEmail;
    if ( DomainFromEmail >= 0 )
    {
      v90 = v91;
      v91 = 0;
      goto LABEL_121;
    }
LABEL_109:
    v13 = L"GetCertAuthUrl";
    goto LABEL_31;
  }
  Logger::TraceWarning(
    L"%s: Resource account join endpoint is empty. Default resource account join endpoint for TSL will not be set.",
    L"JoinStatusStorage::SetDefaultDiscoveryMetadata");
LABEL_121:
  FillJoinStatus((unsigned __int16 **)a1 + 9, (const unsigned __int16 **)&lpMem, a2, L"DrsServiceVersion");
  FillJoinStatus((unsigned __int16 **)a1 + 10, (const unsigned __int16 **)&v67, a2, L"DrsEndpoint");
  FillJoinStatus((unsigned __int16 **)a1 + 11, (const unsigned __int16 **)&v68, a2, L"DrsResourceId");
  FillJoinStatus((unsigned __int16 **)a1 + 12, (const unsigned __int16 **)&v69, a2, L"AuthCodeUrl");
  FillJoinStatus((unsigned __int16 **)a1 + 13, (const unsigned __int16 **)&v70, a2, L"AccessTokenUrl");
  FillJoinStatus((unsigned __int16 **)a1 + 14, (const unsigned __int16 **)&v71, a2, L"CdjServiceVersion");
  FillJoinStatus((unsigned __int16 **)a1 + 15, (const unsigned __int16 **)&v72, a2, L"CdjEndpoint");
  FillJoinStatus((unsigned __int16 **)a1 + 16, (const unsigned __int16 **)&v73, a2, L"CdjResourceId");
  FillJoinStatus((unsigned __int16 **)a1 + 17, (const unsigned __int16 **)&v74, a2, L"NgcServiceVersion");
  FillJoinStatus((unsigned __int16 **)a1 + 18, (const unsigned __int16 **)&v75, a2, L"NgcEndpoint");
  FillJoinStatus((unsigned __int16 **)a1 + 19, (const unsigned __int16 **)&v76, a2, L"NgcResourceId");
  FillJoinStatus((unsigned __int16 **)a1 + 21, (const unsigned __int16 **)&v78, a2, L"WebAuthnEndpoint");
  FillJoinStatus((unsigned __int16 **)a1 + 22, (const unsigned __int16 **)&v79, a2, L"WebAuthnResourceId");
  FillJoinStatus((unsigned __int16 **)a1 + 20, (const unsigned __int16 **)&v77, a2, L"WebAuthnServiceVersion");
  FillJoinStatus((unsigned __int16 **)a1 + 23, (const unsigned __int16 **)&v80, a2, L"DeviceManagementServiceVersion");
  FillJoinStatus((unsigned __int16 **)a1 + 24, (const unsigned __int16 **)&v81, a2, L"DeviceManagementEndpoint");
  FillJoinStatus((unsigned __int16 **)a1 + 25, (const unsigned __int16 **)&v82, a2, L"DeviceManagementResourceId");
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADCloudKerbHaadj>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AADCloudKerbHaadj>::GetImpl'::`2'::impl) )
  {
    FillJoinStatus((unsigned __int16 **)a1 + 35, (const unsigned __int16 **)&v86, a2, L"KerbSpn");
    FillJoinStatus((unsigned __int16 **)a1 + 36, (const unsigned __int16 **)&v87, a2, L"KerbEndpoint");
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADClientTLSOneDotThreeSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AADClientTLSOneDotThreeSupport>::GetImpl'::`2'::impl) )
  {
    FillJoinStatus((unsigned __int16 **)a1 + 37, (const unsigned __int16 **)&v88, a2, L"CdjEndpointTLS");
    FillJoinStatus((unsigned __int16 **)a1 + 38, (const unsigned __int16 **)&v89, a2, L"DeviceManagementEndpointTLS");
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RAforMTRW>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RAforMTRW>::GetImpl'::`2'::impl) )
    FillJoinStatus((unsigned __int16 **)a1 + 39, (const unsigned __int16 **)&v90, a2, L"DeviceJoinResourceEndpointTLS");
LABEL_127:
  operator delete(Block);
  SafeFree(v91);
  SafeFree(v4);
  SafeFree(lpMem);
  SafeFree(v67);
  SafeFree(v68);
  SafeFree(v69);
  SafeFree(v70);
  SafeFree(v71);
  SafeFree(v72);
  SafeFree(v73);
  SafeFree(v74);
  SafeFree(v75);
  SafeFree(v76);
  SafeFree(v77);
  SafeFree(v78);
  SafeFree(v79);
  SafeFree(v80);
  SafeFree(v81);
  SafeFree(v82);
  SafeFree(v85);
  SafeFree(v83);
  SafeFree(v84);
  SafeFree(v86);
  SafeFree(v87);
  SafeFree(v88);
  SafeFree(v89);
  SafeFree(v90);
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"JoinStatusStorage::SetDefaultDiscoveryMetadata", v6);
  return v6;
}

```

## disassembly

```asm
0x18004509c  mov     [rsp-8+arg_8], rbx
0x1800450a1  push    rbp
0x1800450a2  push    rsi
0x1800450a3  push    rdi
0x1800450a4  push    r12
0x1800450a6  push    r13
0x1800450a8  push    r14
0x1800450aa  push    r15
0x1800450ac  lea     rbp, [rsp-40h]
0x1800450b1  sub     rsp, 140h
0x1800450b8  mov     r12, rdx
0x1800450bb  mov     rdi, rcx
0x1800450be  xor     edx, edx; Val
0x1800450c0  lea     rcx, [rsp+170h+lpMem]; void *
0x1800450c5  mov     r8d, 100h; Size
0x1800450cb  call    memset_0
0x1800450d0  xor     edx, edx
0x1800450d2  mov     r15d, edx
0x1800450d5  mov     [rbp+70h+Block], rdx
0x1800450dc  mov     r13d, edx
0x1800450df  mov     [rbp+70h+arg_0], rdx
0x1800450e6  mov     [rbp+70h+Str], rdx
0x1800450ed  mov     [rsp+170h+var_140], rdx
0x1800450f2  cmp     [rdi+48h], rdx
0x1800450f6  jz      loc_1800451C9
0x1800450fc  cmp     [rdi+50h], rdx
0x180045100  jz      loc_1800451C9
0x180045106  cmp     [rdi+58h], rdx
0x18004510a  jz      loc_1800451C9
0x180045110  cmp     [rdi+60h], rdx
0x180045114  jz      loc_1800451C9
0x18004511a  cmp     [rdi+68h], rdx
0x18004511e  jz      loc_1800451C9
0x180045124  cmp     [rdi+70h], rdx
0x180045128  jz      loc_1800451C9
0x18004512e  cmp     [rdi+78h], rdx
0x180045132  jz      loc_1800451C9
0x180045138  cmp     [rdi+80h], rdx
0x18004513f  jz      loc_1800451C9
0x180045145  cmp     [rdi+88h], rdx
0x18004514c  jz      short loc_1800451C9
0x18004514e  cmp     [rdi+90h], rdx
0x180045155  jz      short loc_1800451C9
0x180045157  cmp     [rdi+98h], rdx
0x18004515e  jz      short loc_1800451C9
0x180045160  cmp     [rdi+0A0h], rdx
0x180045167  jz      short loc_1800451C9
0x180045169  cmp     [rdi+0A8h], rdx
0x180045170  jz      short loc_1800451C9
0x180045172  cmp     [rdi+0B0h], rdx
0x180045179  jz      short loc_1800451C9
0x18004517b  cmp     [rdi+0B8h], rdx
0x180045182  jz      short loc_1800451C9
0x180045184  cmp     [rdi+0C0h], rdx
0x18004518b  jz      short loc_1800451C9
0x18004518d  cmp     [rdi+0C8h], rdx
0x180045194  jz      short loc_1800451C9
0x180045196  cmp     [rdi+118h], rdx
0x18004519d  jz      short loc_1800451C9
0x18004519f  cmp     [rdi+120h], rdx
0x1800451a6  jz      short loc_1800451C9
0x1800451a8  cmp     [rdi+128h], rdx
0x1800451af  jz      short loc_1800451C9
0x1800451b1  cmp     [rdi+130h], rdx
0x1800451b8  jz      short loc_1800451C9
0x1800451ba  mov     ebx, edx
0x1800451bc  cmp     [rdi+138h], rdx
0x1800451c3  jnz     loc_180045CFD
0x1800451c9  mov     r14, [rdi+10h]
0x1800451cd  mov     rcx, r14; unsigned __int16 *
0x1800451d0  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x1800451d5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800451d9  test    eax, eax
0x1800451db  jnz     short loc_1800451EF
0x1800451dd  mov     r13, rsi
0x1800451e0  inc     r13
0x1800451e3  cmp     [r14+r13*2], dx
0x1800451e8  jnz     short loc_1800451E0
0x1800451ea  inc     r13
0x1800451ed  jmp     short loc_180045269
0x1800451ef  lea     rdx, aJoinstatusstor_3; "JoinStatusStorage::SetDefaultDiscoveryM"...
0x1800451f6  lea     rcx, aSTenantidIsEmp; "%s: TenantId is empty."
0x1800451fd  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180045202  mov     rcx, [rdi+18h]; unsigned __int16 *
0x180045206  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18004520b  test    eax, eax
0x18004520d  jz      short loc_180045224
0x18004520f  lea     rdx, aJoinstatusstor_3; "JoinStatusStorage::SetDefaultDiscoveryM"...
0x180045216  lea     rcx, aSJoinuseremail; "%s: JoinUserEmail is empty."
0x18004521d  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180045222  jmp     short loc_180045269
0x180045224  lea     r8, [rsp+170h+var_140]; unsigned __int64 *
0x180045229  lea     rdx, [rbp+70h+Block]; unsigned __int16 **
0x180045230  call    ?GetDomainFromEmail@@YAJPEBGPEAPEAGPEA_K@Z; GetDomainFromEmail(ushort const *,ushort * *,unsigned __int64 *)
0x180045235  mov     ebx, eax
0x180045237  test    eax, eax
0x180045239  jns     short loc_18004525D
0x18004523b  lea     r8, aGetdomainfrome; "GetDomainFromEmail"
0x180045242  lea     rdx, aJoinstatusstor_3; "JoinStatusStorage::SetDefaultDiscoveryM"...
0x180045249  mov     r9d, eax
0x18004524c  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180045253  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180045258  jmp     loc_180045CFD
0x18004525d  mov     r14, [rbp+70h+Block]
0x180045264  mov     r13, [rsp+170h+var_140]
0x180045269  mov     rcx, r14; unsigned __int16 *
0x18004526c  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180045271  test    eax, eax
0x180045273  jnz     loc_18004530E
0x180045279  lea     rbx, [r13+36h]
0x18004527d  lea     rcx, [rbx+rbx]; size
0x180045281  call    MIDL_user_allocate
0x180045286  mov     [rsp+170h+var_118], rax
0x18004528b  test    rax, rax
0x18004528e  jnz     short loc_1800452AD
0x180045290  lea     rdx, aJoinstatusstor_3; "JoinStatusStorage::SetDefaultDiscoveryM"...
0x180045297  mov     ebx, 8007000Eh
0x18004529c  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x1800452a3  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x1800452a8  jmp     loc_180045CFD
0x1800452ad  mov     rcx, [rsp+170h+var_118]; unsigned __int16 *
0x1800452b2  lea     r8, aHttpsLoginMicr; "https://login.microsoftonline.com/%s/oa"...
0x1800452b9  mov     r9, r14
0x1800452bc  mov     rdx, rbx; unsigned __int64
0x1800452bf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800452c4  mov     ebx, eax
0x1800452c6  test    eax, eax
0x1800452c8  jns     short loc_1800452D6
0x1800452ca  lea     r8, aStringcchprint; "StringCchPrintfW"
0x1800452d1  jmp     loc_180045242
0x1800452d6  lea     rcx, ds:64h[r13*2]; size
0x1800452de  call    MIDL_user_allocate
0x1800452e3  mov     [rsp+170h+var_110], rax
0x1800452e8  test    rax, rax
0x1800452eb  jz      short loc_180045290
0x1800452ed  mov     r9, r14
0x1800452f0  lea     r8, aHttpsLoginMicr_0; "https://login.microsoftonline.com/%s/oa"...
0x1800452f7  lea     rdx, [r13+32h]; unsigned __int64
0x1800452fb  mov     rcx, rax; unsigned __int16 *
0x1800452fe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180045303  xor     r13d, r13d
0x180045306  mov     ebx, eax
0x180045308  test    eax, eax
0x18004530a  jns     short loc_180045311
0x18004530c  jmp     short loc_1800452CA
0x18004530e  xor     r13d, r13d
0x180045311  lea     r14, a10; "1.0"
0x180045318  mov     rcx, r14; unsigned __int16 *
0x18004531b  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x180045322  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x180045327  mov     ebx, eax
0x180045329  test    eax, eax
0x18004532b  jns     short loc_180045339
0x18004532d  lea     r8, aStringdup; "StringDup"
0x180045334  jmp     loc_180045242
0x180045339  mov     rax, [rbp+70h+arg_0]
0x180045340  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x180045347  lea     rcx, aHttpsEnterpris; "https://enterpriseregistration.windows."...
0x18004534e  mov     [rsp+170h+lpMem], rax
0x180045353  mov     [rbp+70h+arg_0], r13
0x18004535a  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18004535f  mov     ebx, eax
0x180045361  test    eax, eax
0x180045363  js      short loc_18004532D
0x180045365  mov     rax, [rbp+70h+arg_0]
0x18004536c  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x180045373  lea     rcx, aUrnMsDrsEnterp; "urn:ms-drs:enterpriseregistration.windo"...
0x18004537a  mov     [rsp+170h+var_128], rax
0x18004537f  mov     [rbp+70h+arg_0], r13
0x180045386  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18004538b  mov     ebx, eax
0x18004538d  test    eax, eax
0x18004538f  js      short loc_18004532D
0x180045391  mov     rax, [rbp+70h+arg_0]
0x180045398  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18004539f  mov     rcx, r14; unsigned __int16 *
0x1800453a2  mov     [rsp+170h+var_120], rax
0x1800453a7  mov     [rbp+70h+arg_0], r13
0x1800453ae  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x1800453b3  mov     ebx, eax
0x1800453b5  test    eax, eax
0x1800453b7  js      loc_18004532D
0x1800453bd  mov     rax, [rbp+70h+arg_0]
0x1800453c4  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x1800453cb  lea     rcx, aHttpsEnterpris_2; "https://enterpriseregistration.windows."...
0x1800453d2  mov     [rsp+170h+var_108], rax
0x1800453d7  mov     [rbp+70h+arg_0], r13
0x1800453de  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x1800453e3  mov     ebx, eax
0x1800453e5  test    eax, eax
0x1800453e7  js      loc_18004532D
0x1800453ed  mov     rax, [rbp+70h+arg_0]
0x1800453f4  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x1800453fb  lea     rcx, aUrnMsDrsEnterp; "urn:ms-drs:enterpriseregistration.windo"...
0x180045402  mov     [rsp+170h+var_100], rax
0x180045407  mov     [rbp+70h+arg_0], r13
0x18004540e  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x180045413  mov     ebx, eax
0x180045415  test    eax, eax
0x180045417  js      loc_18004532D
0x18004541d  mov     rax, [rbp+70h+arg_0]
0x180045424  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18004542b  mov     rcx, r14; unsigned __int16 *
0x18004542e  mov     [rsp+170h+var_F8], rax
0x180045433  mov     [rbp+70h+arg_0], r13
0x18004543a  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18004543f  mov     ebx, eax
0x180045441  test    eax, eax
0x180045443  js      loc_18004532D
0x180045449  mov     rax, [rbp+70h+arg_0]
0x180045450  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x180045457  lea     rcx, aHttpsEnterpris_0; "https://enterpriseregistration.windows."...
0x18004545e  mov     [rbp+70h+var_F0], rax
0x180045462  mov     [rbp+70h+arg_0], r13
0x180045469  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18004546e  mov     ebx, eax
0x180045470  test    eax, eax
0x180045472  js      loc_18004532D
0x180045478  mov     rax, [rbp+70h+arg_0]
0x18004547f  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x180045486  lea     rcx, aUrnMsDrsEnterp; "urn:ms-drs:enterpriseregistration.windo"...
0x18004548d  mov     [rbp+70h+var_E8], rax
0x180045491  mov     [rbp+70h+arg_0], r13
0x180045498  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18004549d  mov     ebx, eax
0x18004549f  test    eax, eax
0x1800454a1  js      loc_18004532D
0x1800454a7  mov     rax, [rbp+70h+arg_0]
0x1800454ae  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x1800454b5  mov     rcx, r14; unsigned __int16 *
0x1800454b8  mov     [rbp+70h+var_E0], rax
0x1800454bc  mov     [rbp+70h+arg_0], r13
0x1800454c3  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x1800454c8  mov     ebx, eax
0x1800454ca  test    eax, eax
0x1800454cc  js      loc_18004532D
0x1800454d2  mov     rax, [rbp+70h+arg_0]
0x1800454d9  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x1800454e0  mov     rcx, r14; unsigned __int16 *
0x1800454e3  mov     [rbp+70h+var_D8], rax
0x1800454e7  mov     [rbp+70h+arg_0], r13
0x1800454ee  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x1800454f3  mov     ebx, eax
0x1800454f5  test    eax, eax
0x1800454f7  js      loc_18004532D
0x1800454fd  mov     rax, [rbp+70h+arg_0]
0x180045504  lea     rdx, [rbp+70h+arg_0]; unsigned __int16 **
0x18004550b  lea     rcx, a40; "4.0"
0x180045512  mov     [rbp+70h+var_C0], rax
0x180045516  mov     [rbp+70h+arg_0], r13
0x18004551d  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x180045522  mov     ebx, eax
0x180045524  test    eax, eax
0x180045526  js      loc_18004532D
0x18004552c  mov     rax, [rbp+70h+arg_0]
0x180045533  xor     ecx, ecx; lpMem
0x180045535  mov     [rbp+70h+var_60], rax
0x180045539  mov     rax, [rdi+90h]
0x180045540  mov     [rsp+170h+var_140], rax
0x180045545  mov     rax, [rdi+78h]
0x180045549  mov     [rsp+170h+var_138], rax
0x18004554e  mov     [rbp+70h+arg_0], r13
0x180045555  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18004555a  lea     r8, [rbp+70h+Str]; unsigned __int16 **
0x180045561  lea     rcx, [rsp+170h+var_140]; unsigned __int16 **
0x180045566  call    ?GetBaseUrl@@YAJPEAPEBG_KPEAPEAG@Z; GetBaseUrl(ushort const * *,unsigned __int64,ushort * *)
0x18004556b  mov     ebx, eax
0x18004556d  test    eax, eax
0x18004556f  jns     short loc_18004559A
0x180045571  lea     rdx, aJoinstatusstor_3; "JoinStatusStorage::SetDefaultDiscoveryM"...
0x180045578  lea     r8, aGetbaseurl; "GetBaseUrl"
0x18004557f  mov     r9d, eax
0x180045582  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180045589  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004558e  mov     r15, [rbp+70h+Str]
0x180045595  jmp     loc_180045CFD
0x18004559a  mov     r15, [rbp+70h+Str]
0x1800455a1  mov     rcx, r15; unsigned __int16 *
0x1800455a4  mov     r14, r15
0x1800455a7  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x1800455ac  test    eax, eax
0x1800455ae  jz      short loc_1800455CA
0x1800455b0  lea     rdx, aJoinstatusstor_3; "JoinStatusStorage::SetDefaultDiscoveryM"...
0x1800455b7  lea     rcx, aSCannotParseNg; "%s: Cannot parse NGC endpoint to get se"...
0x1800455be  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800455c3  lea     r14, aHttpsEnterpris_1; "https://enterpriseregistration.windows."...
0x1800455ca  lea     rdx, SubStr; "://"
0x1800455d1  mov     rcx, r14; Str
0x1800455d4  call    cs:__imp_wcsstr
0x1800455da  test    rax, rax
0x1800455dd  lea     rbx, [rax+6]
0x1800455e1  cmovz   rbx, r14
0x1800455e5  mov     rcx, rbx; unsigned __int16 *
0x1800455e8  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x1800455ed  test    eax, eax
0x1800455ef  jnz     short loc_180045642
0x1800455f1  mov     rax, rsi
0x1800455f4  inc     rax
0x1800455f7  cmp     [rbx+rax*2], r13w
0x1800455fc  jnz     short loc_1800455F4
  ... truncated ...
```
