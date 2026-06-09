# TenantInfo::Discover(std::shared_ptr<TenantInfo> &,ushort const *,DsregServerResponse *)

- ea: `0x180032618`
- end: `0x1800332cb`
- name: `?Discover@TenantInfo@@SAJAEAV?$shared_ptr@VTenantInfo@@@std@@PEBGPEAVDsregServerResponse@@@Z`
- size: `3251`
- prototype: ``
- caller_count: `3`
- callee_count: `26`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027a74`
- `0x18002d2d8`
- `0x1800aee10`

## callees

- `0x180005ba0`
- `0x1800084f4`
- `0x18000eda4`
- `0x180012948`
- `0x180012c7c`
- `0x18001378c`
- `0x18001b560`
- `0x18001f9d0`
- `0x180026f8c`
- `0x1800276fc`
- `0x18002927c`
- `0x18002b9b4`
- `0x18002dd24`
- `0x1800325d4`
- `0x180032618`
- `0x18003c1cc`
- `0x180044300`
- `0x180044d30`
- `0x18004651c`
- `0x180046ae8`
- `0x180046b3c`
- `0x180057f2c`
- `0x1800695e8`
- `0x18009d7e0`
- `0x1800aae0c`
- `0x1800b93c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800327ec`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800327ec`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180032afd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180032afd`

## string_xrefs

- `0x18003274c`: `%s: Failed reading registration data from AD. Defaulting to autojoin disabled 0x%08x\n`
- `0x180032793`: `%s: Failed reading registration data from AD. Defaulting to autojoin disabled 0x%08x\n`
- `0x1800327b8`: `%s: Failed reading registration data from AD. Defaulting to autojoin disabled 0x%08x\n`
- `0x180032823`: `%s: Failed to create windows event for DsrBeginDiscover. 0x%08x\n`
- `0x180032860`: `%s: Failed to create windows event for DsrBeginDiscover. 0x%08x\n`
- `0x180032873`: `%s: Failed to create windows event for DsrBeginDiscover. 0x%08x\n`
- `0x180032d7b`: `%s: Failed to parse URL "%s". TenantInfo::GetUrlHostAndPath(discoveryMetadata_->pszAuthCodeUrl) failed with error 0x%08x\n`
- `0x180032dc7`: `%s: Failed to parse URL "%s". TenantInfo::GetUrlHostAndPath(discoveryMetadata_->pszAuthCodeUrl) failed with error 0x%08x\n`
- `0x180032def`: `%s: Failed to parse URL "%s". TenantInfo::GetUrlHostAndPath(discoveryMetadata_->pszAuthCodeUrl) failed with error 0x%08x\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall TenantInfo::Discover(unsigned __int64 *a1, unsigned __int16 *a2, __int64 a3)
{
  unsigned __int64 *v5; // r12
  char *v6; // rax
  char *v7; // rbx
  __int64 v8; // rdi
  std::_Ref_count_base *v9; // rcx
  unsigned int v10; // r13d
  unsigned int RegistrationData; // eax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rcx
  _QWORD *CurrentRef; // rax
  __int64 v16; // rdx
  _QWORD *v17; // rax
  __int64 v18; // rdx
  unsigned int v19; // ebx
  __int64 v20; // rax
  HANDLE Event; // rax
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rcx
  _QWORD *v25; // rax
  __int64 v26; // rdx
  _QWORD *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rax
  unsigned __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rcx
  _QWORD *v34; // rax
  __int64 v35; // rdx
  _QWORD *v36; // rax
  __int64 v37; // rdx
  unsigned int v38; // ebx
  __int64 v39; // rax
  __int64 v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // rdx
  __int64 v46; // rcx
  _QWORD *v47; // rax
  __int64 v48; // rdx
  _QWORD *v49; // rax
  __int64 v50; // rdx
  __int64 v51; // rax
  unsigned __int16 *v52; // rcx
  __int64 v53; // rdx
  __int64 v54; // rcx
  _QWORD *v55; // rax
  __int64 v56; // rdx
  _QWORD *v57; // rax
  __int64 v58; // rdx
  __int64 v59; // rax
  DWORD v60; // eax
  __int64 v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // rdx
  __int64 v64; // rcx
  _QWORD *v65; // rax
  __int64 v66; // rdx
  _QWORD *v67; // rax
  __int64 v68; // rdx
  __int64 v69; // rcx
  __int64 v70; // rdx
  __int64 v71; // rcx
  _QWORD *v72; // rax
  __int64 v73; // rdx
  _QWORD *v74; // rax
  __int64 v75; // rdx
  __int64 v76; // rax
  __int64 v77; // rdx
  __int64 v78; // rcx
  _QWORD *v79; // rax
  __int64 v80; // rdx
  _QWORD *v81; // rax
  __int64 v82; // rdx
  unsigned int v83; // ebx
  __int64 v84; // rax
  __int64 v85; // rdx
  __int64 v86; // rcx
  __int64 v87; // rdx
  __int64 v88; // rcx
  int UrlHostAndPath; // edi
  __int64 v90; // rdx
  __int64 v91; // rcx
  _QWORD *v92; // rax
  __int64 v93; // rdx
  __int64 v94; // rdx
  __int64 v95; // rcx
  __int64 v96; // rbx
  __int64 v97; // rcx
  unsigned __int16 *v98; // rcx
  __int64 v99; // rdx
  __int64 v100; // rcx
  __int64 v101; // rdx
  __int64 v102; // rcx
  _QWORD *v103; // rax
  __int64 v104; // rdx
  _QWORD *v105; // rax
  __int64 v106; // rdx
  __int64 v107; // rax
  const WCHAR *v108; // rcx
  const WCHAR *v109; // rcx
  __int64 v110; // rdx
  __int64 v111; // rcx
  LPCWCH *v112; // r8
  __int64 v113; // rdx
  __int64 v114; // rcx
  _QWORD *v115; // rax
  __int64 v116; // rdx
  _QWORD *v117; // rax
  __int64 v118; // rdx
  __int64 v119; // rbx
  LPCWCH *v120; // rdi
  __int64 v121; // rax
  LPCWCH *v122; // r8
  __int64 v123; // rdx
  __int64 v124; // rcx
  _QWORD *v125; // rax
  __int64 v126; // rdx
  _QWORD *v127; // rax
  __int64 v128; // rdx
  __int64 v129; // rax
  const wchar_t *v130; // rbx
  const wchar_t *v131; // rdi
  const unsigned __int16 *v132; // rax
  __int64 v133; // rdx
  __int64 v134; // rcx
  _QWORD *v135; // rax
  __int64 v136; // rdx
  unsigned __int64 v137; // rcx
  const wchar_t *v138; // r14
  const wchar_t *v139; // rsi
  const unsigned __int16 *v140; // rbx
  __int64 v141; // rdx
  __int64 v142; // rcx
  __int64 v143; // rax
  unsigned __int64 v144; // rcx
  const unsigned __int16 *v145; // rax
  __int64 v146; // r10
  __int64 v148; // rax
  const unsigned __int16 *v149; // r8
  __int64 v150; // rax
  const unsigned __int16 *v151; // r8
  unsigned __int16 *v152; // [rsp+20h] [rbp-E8h]
  int v153[2]; // [rsp+40h] [rbp-C8h] BYREF
  std::_Ref_count_base *v154; // [rsp+48h] [rbp-C0h]
  unsigned __int64 *v155; // [rsp+50h] [rbp-B8h]
  const std::bad_alloc *v156; // [rsp+58h] [rbp-B0h] BYREF
  const std::exception *v157; // [rsp+60h] [rbp-A8h] BYREF
  LPCWCH lpString1[3]; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int64 v159; // [rsp+80h] [rbp-88h]
  _QWORD Src[3]; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int64 v161; // [rsp+A0h] [rbp-68h]
  _BYTE v162[32]; // [rsp+A8h] [rbp-60h] BYREF

  v5 = a1;
  v155 = a1;
  if ( a3 )
    DsrFreeServerResponseContent(a3);
  v6 = (char *)operator new(0x108u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  *(_QWORD *)v153 = v6;
  v8 = -1;
  if ( v6 )
  {
    *(_QWORD *)v6 = 0;
    v6[8] = 0;
    *((_DWORD *)v6 + 3) = 2;
    *((_DWORD *)v6 + 4) = -2147467259;
    *((_QWORD *)v6 + 3) = -1;
    memset_0(v6 + 32, 0, 0xD8u);
    *((_DWORD *)v7 + 62) = -2147467259;
    *((_QWORD *)v7 + 32) = 0;
  }
  else
  {
    v7 = 0;
  }
  try
  {
    std::shared_ptr<TenantInfo>::shared_ptr<TenantInfo>(v153, v7);
    std::shared_ptr<_NgcPolicyCheckResult>::operator=(v5, v153);
    v9 = v154;
    if ( v154 )
      std::_Ref_count_base::_Decref(v154);
  }
  catch ( const std::bad_alloc *v156 )
  {
    v148 = (*(__int64 (__fastcall **)(const std::bad_alloc *))(*(_QWORD *)v156 + 8LL))(v156);
    v153[0] = -2147024882;
    v149 = &dword_1800D914C;
    if ( v148 )
      v149 = (const unsigned __int16 *)v148;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed. %hs.", L"TenantInfo::Discover", v149);
    v10 = v153[0];
    v5 = v155;
    goto LABEL_128;
  }
  catch ( const std::exception *v157 )
  {
    v153[0] = -2147418113;
    v150 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v157 + 8LL))(v157);
    v151 = &dword_1800D914C;
    if ( v150 )
      v151 = (const unsigned __int16 *)v150;
    Logger::TraceError(L"%s: Unhandled std::exception: %hs.", L"TenantInfo::Discover", v151);
    v10 = v153[0];
    v5 = v155;
    goto LABEL_128;
  }
  catch ( ... )
  {
    v153[0] = -2147418113;
    Logger::TraceError(L"%s: Unhandled exception.", L"TenantInfo::Discover");
    v10 = v153[0];
    v5 = v155;
    goto LABEL_128;
  }
  if ( !*v5 )
  {
    v10 = -2147024882;
    goto LABEL_128;
  }
  *(_QWORD *)(*v5 + 256) = a3;
  RegistrationData = RegistrationController::GetRegistrationData(
                       (const unsigned __int16 *)v9,
                       (struct _REGISTRATION_DATA *)(*v5 + 32));
  *(_DWORD *)(*v5 + 248) = RegistrationData;
  if ( *(int *)(*v5 + 248) < 0 )
  {
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(RegistrationData, v12) )
    {
      wprintf(
        L"%s: Failed reading registration data from AD. Defaulting to autojoin disabled 0x%08x\n",
        L"TenantInfo::Discover",
        *(unsigned int *)(*v5 + 248));
      CurrentRef = (_QWORD *)CmdOptions::GetCurrentRef(v14, v13);
      if ( *(_BYTE *)(*CurrentRef + 12LL) )
      {
        v17 = (_QWORD *)CmdOptions::GetCurrentRef(*CurrentRef, v16);
        if ( *(_QWORD *)(*v17 + 184LL) )
        {
          v19 = *(_DWORD *)(*v5 + 248);
          v20 = CmdOptions::GetCurrentRef(*v17, v18);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v20 + 184LL),
            L"%s: Failed reading registration data from AD. Defaulting to autojoin disabled 0x%08x\n",
            L"TenantInfo::Discover",
            v19);
        }
      }
    }
    Logger::TraceInformation(
      L"%s: Failed reading registration data from AD. Defaulting to autojoin disabled 0x%08x\n",
      L"TenantInfo::Discover",
      *(unsigned int *)(*v5 + 248));
    *(_BYTE *)(*v5 + 8) = 0;
LABEL_16:
    v10 = -2145648611;
    goto LABEL_128;
  }
  *(_BYTE *)(*v5 + 8) = 1;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  *(_QWORD *)(*v5 + 24) = Event;
  if ( !Event )
  {
    v10 = -2145648610;
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(0, v22) )
    {
      wprintf(
        L"%s: Failed to create windows event for DsrBeginDiscover. 0x%08x\n",
        L"TenantInfo::Discover",
        2149318686LL);
      v25 = (_QWORD *)CmdOptions::GetCurrentRef(v24, v23);
      if ( *(_BYTE *)(*v25 + 12LL) )
      {
        v27 = (_QWORD *)CmdOptions::GetCurrentRef(*v25, v26);
        if ( *(_QWORD *)(*v27 + 184LL) )
        {
          v29 = CmdOptions::GetCurrentRef(*v27, v28);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v29 + 184LL),
            L"%s: Failed to create windows event for DsrBeginDiscover. 0x%08x\n",
            L"TenantInfo::Discover",
            2149318686LL);
        }
      }
    }
    Logger::TraceInformation(
      L"%s: Failed to create windows event for DsrBeginDiscover. 0x%08x\n",
      L"TenantInfo::Discover",
      2149318686LL);
    goto LABEL_128;
  }
  v30 = *v5;
  v31 = *(unsigned int *)(*v5 + 240);
  if ( (_DWORD)v31 )
  {
    if ( (_DWORD)v31 != 1 )
      goto LABEL_25;
    v10 = DsrBeginDiscoverEnterprise(
            *(unsigned __int16 **)(v30 + 232),
            (void (__high *)(struct _DISCOVERY_METADATA *, struct struct_dsreg_server_response, unsigned __int64, int))&TenantInfo::DiscoverCallback,
            *v5,
            a2);
  }
  else
  {
    if ( (unsigned int)IsEmptyString(*(const unsigned __int16 **)(v30 + 208)) )
    {
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(v44, v43) )
      {
        wprintf(L"%s: Tenant domain name is empty\n", L"TenantInfo::Discover");
        v47 = (_QWORD *)CmdOptions::GetCurrentRef(v46, v45);
        if ( *(_BYTE *)(*v47 + 12LL) )
        {
          v49 = (_QWORD *)CmdOptions::GetCurrentRef(*v47, v48);
          if ( *(_QWORD *)(*v49 + 184LL) )
          {
            v51 = CmdOptions::GetCurrentRef(*v49, v50);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v51 + 184LL),
              L"%s: Tenant domain name is empty\n",
              L"TenantInfo::Discover");
          }
        }
      }
      Logger::TraceError(L"%s: Tenant domain name is empty\n", L"TenantInfo::Discover");
      goto LABEL_16;
    }
    std::wstring::wstring((__int64)Src, (__int64)L"user@");
    do
      ++v8;
    while ( *(_WORD *)(*(_QWORD *)(*v5 + 208) + 2 * v8) );
    std::wstring::_Append<unsigned short>(Src);
    v52 = (unsigned __int16 *)Src;
    if ( v161 > 7 )
      v52 = (unsigned __int16 *)Src[0];
    v10 = DsrBeginDiscoverEx(v52, a2);
    std::wstring::_Tidy_deallocate((__int64)Src);
  }
  if ( (v10 & 0x80000000) != 0 )
  {
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v42, v41) )
    {
      wprintf(L"%s: Call to DsrBeginDiscover failed before wait. 0x%08x\n", L"TenantInfo::Discover", v10);
      v55 = (_QWORD *)CmdOptions::GetCurrentRef(v54, v53);
      if ( *(_BYTE *)(*v55 + 12LL) )
      {
        v57 = (_QWORD *)CmdOptions::GetCurrentRef(*v55, v56);
        if ( *(_QWORD *)(*v57 + 184LL) )
        {
          v59 = CmdOptions::GetCurrentRef(*v57, v58);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v59 + 184LL),
            L"%s: Call to DsrBeginDiscover failed before wait. 0x%08x\n",
            L"TenantInfo::Discover",
            v10);
        }
      }
    }
    Logger::TraceInformation(L"%s: Call to DsrBeginDiscover failed before wait. 0x%08x\n", L"TenantInfo::Discover", v10);
    goto LABEL_128;
  }
  v60 = WaitForSingleObject(*(HANDLE *)(*v5 + 24), 0x1D4C0u);
  if ( v60 == 258 )
  {
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v62, v61) )
    {
      wprintf(L"%s: DsrBeginDiscover timed out. Timeout set to %d. 0x%08x\n", L"TenantInfo::Discover", 120000, 258);
      v65 = (_QWORD *)CmdOptions::GetCurrentRef(v64, v63);
      if ( *(_BYTE *)(*v65 + 12LL) )
      {
        v67 = (_QWORD *)CmdOptions::GetCurrentRef(*v65, v66);
        if ( *(_QWORD *)(*v67 + 184LL) )
        {
          v69 = *(_QWORD *)CmdOptions::GetCurrentRef(*v67, v68);
          LODWORD(v152) = 258;
          fwprintf_s(
            *(FILE *const *)(v69 + 184),
            L"%s: DsrBeginDiscover timed out. Timeout set to %d. 0x%08x\n",
            L"TenantInfo::Discover",
            120000,
            v152);
        }
      }
    }
    Logger::TraceInformation(
      L"%s: DsrBeginDiscover timed out. Timeout set to %d. 0x%08x\n",
      L"TenantInfo::Discover",
      120000,
      258);
    v10 = -2145648609;
    goto LABEL_128;
  }
  if ( v60 )
  {
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v62, v61) )
    {
      wprintf(L"%s: DsrBeginDiscover unknown wait error. 0x%08x\n", L"TenantInfo::Discover", 0xFFFFFFFFLL);
      v72 = (_QWORD *)CmdOptions::GetCurrentRef(v71, v70);
      if ( *(_BYTE *)(*v72 + 12LL) )
      {
        v74 = (_QWORD *)CmdOptions::GetCurrentRef(*v72, v73);
        if ( *(_QWORD *)(*v74 + 184LL) )
        {
          v76 = CmdOptions::GetCurrentRef(*v74, v75);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v76 + 184LL),
            L"%s: DsrBeginDiscover unknown wait error. 0x%08x\n",
            L"TenantInfo::Discover",
            0xFFFFFFFFLL);
        }
      }
    }
    Logger::TraceInformation(
      L"%s: DsrBeginDiscover unknown wait error. 0x%08x\n",
      L"TenantInfo::Discover",
      0xFFFFFFFFLL);
    v10 = -2145648608;
    goto LABEL_128;
  }
  v30 = *v5;
  if ( *(int *)(*v5 + 16) < 0 )
  {
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v30, v61) )
    {
      wprintf(L"%s: DsrBeginDiscover failed. 0x%08x\n", L"TenantInfo::Discover", *(unsigned int *)(*v5 + 16));
      v79 = (_QWORD *)CmdOptions::GetCurrentRef(v78, v77);
      if ( *(_BYTE *)(*v79 + 12LL) )
      {
        v81 = (_QWORD *)CmdOptions::GetCurrentRef(*v79, v80);
        if ( *(_QWORD *)(*v81 + 184LL) )
        {
          v83 = *(_DWORD *)(*v5 + 16);
          v84 = CmdOptions::GetCurrentRef(*v81, v82);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v84 + 184LL),
            L"%s: DsrBeginDiscover failed. 0x%08x\n",
            L"TenantInfo::Discover",
            v83);
        }
      }
    }
    Logger::TraceInformation(
      L"%s: DsrBeginDiscover failed. 0x%08x\n",
      L"TenantInfo::Discover",
      *(unsigned int *)(*v5 + 16));
    v10 = -2145648607;
    goto LABEL_128;
  }
  v31 = *(unsigned int *)(v30 + 240);
  if ( (_DWORD)v31 )
  {
    if ( (_DWORD)v31 != 1 )
    {
LABEL_25:
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(v30, v31) )
      {
        wprintf(L"%s: Invalid DSR_INSTANCE value %d.\n", L"TenantInfo::Discover", *(unsigned int *)(*v5 + 240));
        v34 = (_QWORD *)CmdOptions::GetCurrentRef(v33, v32);
        if ( *(_BYTE *)(*v34 + 12LL) )
        {
          v36 = (_QWORD *)CmdOptions::GetCurrentRef(*v34, v35);
          if ( *(_QWORD *)(*v36 + 184LL) )
          {
            v38 = *(_DWORD *)(*v5 + 240);
            v39 = CmdOptions::GetCurrentRef(*v36, v37);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v39 + 184LL),
              L"%s: Invalid DSR_INSTANCE value %d.\n",
              L"TenantInfo::Discover",
              v38);
          }
        }
      }
      Logger::TraceInformation(
        L"%s: Invalid DSR_INSTANCE value %d.\n",
        L"TenantInfo::Discover",
        *(unsigned int *)(*v5 + 240));
      MicrosoftTelemetryAssertTriggeredArgs(v40, *(unsigned int *)(*v5 + 240));
      goto LABEL_16;
    }
    *(_DWORD *)(v30 + 12) = 0;
    goto LABEL_113;
  }
  *(_DWORD *)(v30 + 12) = 1;
  if ( (unsigned int)IsEmptyString(*(const unsigned __int16 **)(*(_QWORD *)*v5 + 24LL)) )
  {
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v86, v85) )
    {
      wprintf(L"%s: IDP auth code URL is empty. Default tenant type to managed.\n", L"TenantInfo::Discover");
      v125 = (_QWORD *)CmdOptions::GetCurrentRef(v124, v123);
      if ( *(_BYTE *)(*v125 + 12LL) )
      {
        v127 = (_QWORD *)CmdOptions::GetCurrentRef(*v125, v126);
        if ( *(_QWORD *)(*v127 + 184LL) )
        {
          v129 = CmdOptions::GetCurrentRef(*v127, v128);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v129 + 184LL),
            L"%s: IDP auth code URL is empty. Default tenant type to managed.\n",
            L"TenantInfo::Discover");
        }
      }
    }
    Logger::TraceInformation(
      L"%s: IDP auth code URL is empty. Default tenant type to managed.\n",
      L"TenantInfo::Discover");
  }
  else
  {
    std::wstring::wstring((__int64)Src);
    std::wstring::wstring((__int64)v162);
    UrlHostAndPath = TenantInfo::GetUrlHostAndPath(*(LPCWSTR *)(*(_QWORD *)*v5 + 24LL));
    if ( UrlHostAndPath < 0 )
    {
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(v88, v87) )
      {
        wprintf(
          L"%s: Failed to parse URL \"%s\". TenantInfo::GetUrlHostAndPath(discoveryMetadata_->pszAuthCodeUrl) failed with error 0x%08x\n",
          L"TenantInfo::Discover",
          *(_QWORD *)(*(_QWORD *)*v5 + 24LL),
          (unsigned int)UrlHostAndPath);
        v92 = (_QWORD *)CmdOptions::GetCurrentRef(v91, v90);
        if ( *(_BYTE *)(*v92 + 12LL) )
        {
          if ( *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef(*v92, v93) + 184LL) )
          {
            v95 = *(_QWORD *)*v5;
            v96 = *(_QWORD *)(v95 + 24);
            v97 = *(_QWORD *)CmdOptions::GetCurrentRef(v95, v94);
            LODWORD(v152) = UrlHostAndPath;
            fwprintf_s(
              *(FILE *const *)(v97 + 184),
              L"%s: Failed to parse URL \"%s\". TenantInfo::GetUrlHostAndPath(discoveryMetadata_->pszAuthCodeUrl) failed w"
               "ith error 0x%08x\n",
              L"TenantInfo::Discover",
              v96,
              v152);
          }
        }
      }
      Logger::TraceInformation(
        L"%s: Failed to parse URL \"%s\". TenantInfo::GetUrlHostAndPath(discoveryMetadata_->pszAuthCodeUrl) failed with error 0x%08x\n",
        L"TenantInfo::Discover",
        *(_QWORD *)(*(_QWORD *)*v5 + 24LL),
        (unsigned int)UrlHostAndPath);
      *(_DWORD *)(*v5 + 16) = UrlHostAndPath;
      v10 = -2145648579;
      goto LABEL_76;
    }
    std::wstring::wstring((__int64)lpString1);
    v98 = (unsigned __int16 *)Src;
    if ( v161 > 7 )
      v98 = (unsigned __int16 *)Src[0];
    v10 = UserRealmHttpRequest::SendAndParseDomainType(v98, *(unsigned __int16 **)(*v5 + 208));
    if ( (v10 & 0x80000000) != 0 )
    {
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(v100, v99) )
      {
        wprintf(
          L"%s: UserRealmHttpRequest::SendAndParseDomainType() failed with error 0x%08x\n",
          L"TenantInfo::Discover",
          v10);
        v103 = (_QWORD *)CmdOptions::GetCurrentRef(v102, v101);
        if ( *(_BYTE *)(*v103 + 12LL) )
        {
          v105 = (_QWORD *)CmdOptions::GetCurrentRef(*v103, v104);
          if ( *(_QWORD *)(*v105 + 184LL) )
          {
            v107 = CmdOptions::GetCurrentRef(*v105, v106);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v107 + 184LL),
              L"%s: UserRealmHttpRequest::SendAndParseDomainType() failed with error 0x%08x\n",
              L"TenantInfo::Discover",
              v10);
          }
        }
      }
      Logger::TraceInformation(
        L"%s: UserRealmHttpRequest::SendAndParseDomainType() failed with error 0x%08x\n",
        L"TenantInfo::Discover",
        v10);
      *(_DWORD *)(*v5 + 16) = v10;
      v10 = -2145648579;
LABEL_85:
      std::wstring::_Tidy_deallocate((__int64)lpString1);
LABEL_76:
      std::wstring::_Tidy_deallocate((__int64)v162);
      std::wstring::_Tidy_deallocate((__int64)Src);
      goto LABEL_128;
    }
    v153[0] = 0;
    v108 = (const WCHAR *)lpString1;
    if ( v159 > 7 )
      v108 = lpString1[0];
    if ( (int)StringCompare(v108, L"federated", 1u, v153) >= 0 && v153[0] )
    {
      *(_DWORD *)(*v5 + 12) = 0;
    }
    else
    {
      v109 = (const WCHAR *)lpString1;
      if ( v159 > 7 )
        v109 = lpString1[0];
      if ( (int)StringCompare(v109, L"managed", 1u, v153) < 0 || !v153[0] )
      {
        if ( **(_BYTE **)CmdOptions::GetCurrentRef(v111, v110) )
        {
          v112 = lpString1;
          if ( v159 > 7 )
            v112 = (LPCWCH *)lpString1[0];
          wprintf(
            L"%s: Unexpected domain type (%s) returned by UserRealm endpoint for domain '%s'.\n",
            L"TenantInfo::Discover",
            v112,
            *(_QWORD *)(*v5 + 208));
          v115 = (_QWORD *)CmdOptions::GetCurrentRef(v114, v113);
          if ( *(_BYTE *)(*v115 + 12LL) )
          {
            v117 = (_QWORD *)CmdOptions::GetCurrentRef(*v115, v116);
            if ( *(_QWORD *)(*v117 + 184LL) )
            {
              v119 = *(_QWORD *)(*v5 + 208);
              v120 = lpString1;
              if ( v159 > 7 )
                v120 = (LPCWCH *)lpString1[0];
              v121 = CmdOptions::GetCurrentRef(*v117, v118);
              fwprintf_s(
                *(FILE *const *)(*(_QWORD *)v121 + 184LL),
                L"%s: Unexpected domain type (%s) returned by UserRealm endpoint for domain '%s'.\n",
                L"TenantInfo::Discover",
                v120,
                v119);
            }
          }
        }
        v122 = lpString1;
        if ( v159 > 7 )
          v122 = (LPCWCH *)lpString1[0];
        Logger::TraceInformation(
          L"%s: Unexpected domain type (%s) returned by UserRealm endpoint for domain '%s'.\n",
          L"TenantInfo::Discover",
          v122,
          *(_QWORD *)(*v5 + 208));
        v10 = -2145648576;
        goto LABEL_85;
      }
      *(_DWORD *)(*v5 + 12) = 1;
    }
    std::wstring::_Tidy_deallocate((__int64)lpString1);
    std::wstring::_Tidy_deallocate((__int64)v162);
    std::wstring::_Tidy_deallocate((__int64)Src);
  }
LABEL_113:
  v130 = L"<NULL>";
  v131 = L"TRUE";
  if ( **(_BYTE **)CmdOptions::GetCurrentRef(v30, v31) )
  {
    v132 = TenantInfo::TenantTypeName((TenantInfo *)*v5);
    wprintf(
      L"%s: Join Info { TenantType = %s; AutoJoinEnabled = %s; TenandID = %s; TenantName = %s }\n",
      L"TenantInfo::Discover",
      v132);
    v135 = (_QWORD *)CmdOptions::GetCurrentRef(v134, v133);
    if ( *(_BYTE *)(*v135 + 12LL) )
    {
      if ( *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef(*v135, v136) + 184LL) )
      {
        v137 = *v5;
        v138 = L"<NULL>";
        if ( *(_QWORD *)(*v5 + 208) )
          v138 = *(const wchar_t **)(*v5 + 208);
        v139 = L"<NULL>";
        if ( *(_QWORD *)(v137 + 216) )
          v139 = *(const wchar_t **)(v137 + 216);
        if ( !*(_BYTE *)(v137 + 8) )
          v131 = L"FALSE";
        v140 = TenantInfo::TenantTypeName((TenantInfo *)v137);
        v143 = CmdOptions::GetCurrentRef(v142, v141);
        fwprintf_s(
          *(FILE *const *)(*(_QWORD *)v143 + 184LL),
          L"%s: Join Info { TenantType = %s; AutoJoinEnabled = %s; TenandID = %s; TenantName = %s }\n",
          L"TenantInfo::Discover",
          v140,
          v131,
          v139,
          v138);
        v130 = L"<NULL>";
        v131 = L"TRUE";
      }
    }
  }
  v144 = *v5;
  if ( *(_QWORD *)(*v5 + 216) )
    v130 = *(const wchar_t **)(v144 + 216);
  if ( !*(_BYTE *)(v144 + 8) )
    v131 = L"FALSE";
  v145 = TenantInfo::TenantTypeName((TenantInfo *)v144);
  Logger::TraceInformation(
    L"%s: Join Info { TenantType = %s; AutoJoinEnabled = %s; TenandID = %s; TenantName = %s }\n",
    L"TenantInfo::Discover",
    v145,
    v131,
    v130,
    v146);
LABEL_128:
  if ( *v5 )
    *(_QWORD *)(*v5 + 256) = 0;
  return v10;
}

```

## disassembly

```asm
0x180032618  push    rbx
0x18003261a  push    rsi
0x18003261b  push    rdi
0x18003261c  push    r12
0x18003261e  push    r13
0x180032620  push    r14
0x180032622  push    r15
0x180032624  sub     rsp, 0D0h
0x18003262b  mov     rax, cs:__security_cookie
0x180032632  xor     rax, rsp
0x180032635  mov     [rsp+108h+var_40], rax
0x18003263d  mov     rsi, r8
0x180032640  mov     r14, rdx
0x180032643  mov     r12, rcx
0x180032646  mov     [rsp+108h+var_B8], rcx
0x18003264b  xor     r15d, r15d
0x18003264e  test    r8, r8
0x180032651  jz      short loc_18003265C
0x180032653  mov     rcx, r8
0x180032656  call    DsrFreeServerResponseContent
0x18003265b  nop
0x18003265c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180032663  mov     ecx, 108h; unsigned __int64
0x180032668  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003266d  mov     rbx, rax
0x180032670  mov     qword ptr [rsp+108h+var_C8], rax
0x180032675  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180032679  test    rax, rax
0x18003267c  jz      short loc_1800326BB
0x18003267e  mov     [rax], r15
0x180032681  mov     [rax+8], r15b
0x180032685  mov     dword ptr [rax+0Ch], 2
0x18003268c  mov     r13d, 80004005h
0x180032692  mov     [rax+10h], r13d
0x180032696  mov     [rax+18h], rdi
0x18003269a  lea     rcx, [rax+20h]; void *
0x18003269e  xor     edx, edx; Val
0x1800326a0  mov     r8d, 0D8h; Size
0x1800326a6  call    memset_0
0x1800326ab  mov     [rbx+0F8h], r13d
0x1800326b2  mov     [rbx+100h], r15
0x1800326b9  jmp     short loc_1800326BE
0x1800326bb  mov     rbx, r15
0x1800326be  mov     rdx, rbx
0x1800326c1  lea     rcx, [rsp+108h+var_C8]
0x1800326c6  call    ??$?0VTenantInfo@@$0A@@?$shared_ptr@VTenantInfo@@@std@@QEAA@PEAVTenantInfo@@@Z; std::shared_ptr<TenantInfo>::shared_ptr<TenantInfo>(TenantInfo *)
0x1800326cb  lea     rdx, [rsp+108h+var_C8]
0x1800326d0  mov     rcx, r12
0x1800326d3  call    ??4?$shared_ptr@U_NgcPolicyCheckResult@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<_NgcPolicyCheckResult>::operator=(std::shared_ptr<_NgcPolicyCheckResult> &&)
0x1800326d8  mov     rcx, [rsp+108h+var_C0]; this
0x1800326dd  test    rcx, rcx
0x1800326e0  jz      short loc_1800326E8
0x1800326e2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800326e7  nop
0x1800326e8  mov     rax, [r12]
0x1800326ec  test    rax, rax
0x1800326ef  jnz     short loc_1800326FC
0x1800326f1  mov     r13d, 8007000Eh
0x1800326f7  jmp     loc_180033295
0x1800326fc  mov     [rax+100h], rsi
0x180032703  mov     rdx, [r12]
0x180032707  add     rdx, 20h ; ' '; struct _REGISTRATION_DATA *
0x18003270b  call    ?GetRegistrationData@RegistrationController@@SAJPEBGPEAU_REGISTRATION_DATA@@@Z; RegistrationController::GetRegistrationData(ushort const *,_REGISTRATION_DATA *)
0x180032710  mov     ecx, eax
0x180032712  mov     rax, [r12]
0x180032716  mov     [rax+0F8h], ecx
0x18003271c  mov     rax, [r12]
0x180032720  cmp     [rax+0F8h], r15d
0x180032727  jge     loc_1800327D7
0x18003272d  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180032732  mov     rcx, [rax]
0x180032735  cmp     [rcx], r15b
0x180032738  jz      short loc_1800327A6
0x18003273a  mov     r8, [r12]
0x18003273e  mov     r8d, [r8+0F8h]
0x180032745  lea     rdx, aTenantinfoDisc; "TenantInfo::Discover"
0x18003274c  lea     rcx, aSFailedReading; "%s: Failed reading registration data fr"...
0x180032753  call    wprintf
0x180032758  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003275d  mov     rcx, [rax]
0x180032760  cmp     [rcx+0Ch], r15b
0x180032764  jz      short loc_1800327A6
0x180032766  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003276b  mov     rcx, [rax]
0x18003276e  cmp     [rcx+0B8h], r15
0x180032775  jz      short loc_1800327A6
0x180032777  mov     rax, [r12]
0x18003277b  mov     ebx, [rax+0F8h]
0x180032781  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180032786  mov     rcx, [rax]
0x180032789  mov     r9d, ebx
0x18003278c  lea     r8, aTenantinfoDisc; "TenantInfo::Discover"
0x180032793  lea     rdx, aSFailedReading; "%s: Failed reading registration data fr"...
0x18003279a  mov     rcx, [rcx+0B8h]; Stream
0x1800327a1  call    fwprintf_s
0x1800327a6  mov     r8, [r12]
0x1800327aa  mov     r8d, [r8+0F8h]
0x1800327b1  lea     rdx, aTenantinfoDisc; "TenantInfo::Discover"
0x1800327b8  lea     rcx, aSFailedReading; "%s: Failed reading registration data fr"...
0x1800327bf  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x1800327c4  mov     rax, [r12]
0x1800327c8  mov     [rax+8], r15b
0x1800327cc  mov     r13d, 801C001Dh
0x1800327d2  jmp     loc_180033295
0x1800327d7  mov     ebx, 1
0x1800327dc  mov     [rax+8], bl
0x1800327df  mov     r9d, 1F0003h; dwDesiredAccess
0x1800327e5  xor     r8d, r8d; dwFlags
0x1800327e8  xor     edx, edx; lpName
0x1800327ea  xor     ecx, ecx; lpEventAttributes
0x1800327ec  call    cs:__imp_CreateEventExW
0x1800327f2  mov     rcx, rax
0x1800327f5  mov     rax, [r12]
0x1800327f9  mov     [rax+18h], rcx
0x1800327fd  test    rcx, rcx
0x180032800  jnz     loc_18003288E
0x180032806  mov     r13d, 801C001Eh
0x18003280c  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180032811  mov     rcx, [rax]
0x180032814  cmp     [rcx], r15b
0x180032817  jz      short loc_180032873
0x180032819  mov     r8d, r13d
0x18003281c  lea     rdx, aTenantinfoDisc; "TenantInfo::Discover"
0x180032823  lea     rcx, aSFailedToCreat_1; "%s: Failed to create windows event for "...
0x18003282a  call    wprintf
0x18003282f  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180032834  mov     rcx, [rax]
0x180032837  cmp     [rcx+0Ch], r15b
0x18003283b  jz      short loc_180032873
0x18003283d  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180032842  mov     rcx, [rax]
0x180032845  cmp     [rcx+0B8h], r15
0x18003284c  jz      short loc_180032873
0x18003284e  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180032853  mov     rcx, [rax]
0x180032856  mov     r9d, r13d
0x180032859  lea     r8, aTenantinfoDisc; "TenantInfo::Discover"
0x180032860  lea     rdx, aSFailedToCreat_1; "%s: Failed to create windows event for "...
0x180032867  mov     rcx, [rcx+0B8h]; Stream
0x18003286e  call    fwprintf_s
0x180032873  lea     rcx, aSFailedToCreat_1; "%s: Failed to create windows event for "...
0x18003287a  lea     rdx, aTenantinfoDisc; "TenantInfo::Discover"
0x180032881  mov     r8d, r13d
0x180032884  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180032889  jmp     loc_180033295
0x18003288e  mov     rcx, [r12]
0x180032892  mov     edx, [rcx+0F0h]
0x180032898  test    edx, edx
0x18003289a  jz      loc_180032974
0x1800328a0  cmp     edx, ebx
0x1800328a2  jz      loc_180032953
0x1800328a8  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800328ad  mov     rcx, [rax]
0x1800328b0  cmp     [rcx], r15b
0x1800328b3  jz      short loc_180032921
0x1800328b5  mov     r8, [r12]
0x1800328b9  mov     r8d, [r8+0F0h]
0x1800328c0  lea     rdx, aTenantinfoDisc; "TenantInfo::Discover"
0x1800328c7  lea     rcx, aSInvalidDsrIns; "%s: Invalid DSR_INSTANCE value %d.\n"
0x1800328ce  call    wprintf
0x1800328d3  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800328d8  mov     rcx, [rax]
0x1800328db  cmp     [rcx+0Ch], r15b
0x1800328df  jz      short loc_180032921
0x1800328e1  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800328e6  mov     rcx, [rax]
0x1800328e9  cmp     [rcx+0B8h], r15
0x1800328f0  jz      short loc_180032921
0x1800328f2  mov     rax, [r12]
0x1800328f6  mov     ebx, [rax+0F0h]
0x1800328fc  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180032901  mov     rcx, [rax]
0x180032904  mov     r9d, ebx
0x180032907  lea     r8, aTenantinfoDisc; "TenantInfo::Discover"
0x18003290e  lea     rdx, aSInvalidDsrIns; "%s: Invalid DSR_INSTANCE value %d.\n"
0x180032915  mov     rcx, [rcx+0B8h]; Stream
0x18003291c  call    fwprintf_s
0x180032921  mov     r8, [r12]
0x180032925  mov     r8d, [r8+0F0h]
0x18003292c  lea     rdx, aTenantinfoDisc; "TenantInfo::Discover"
0x180032933  lea     rcx, aSInvalidDsrIns; "%s: Invalid DSR_INSTANCE value %d.\n"
0x18003293a  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18003293f  mov     rdx, [r12]
0x180032943  mov     edx, [rdx+0F0h]
0x180032949  call    MicrosoftTelemetryAssertTriggeredArgs
0x18003294e  jmp     loc_1800327CC
0x180032953  mov     r9, r14; unsigned __int16 *
0x180032956  mov     r8, rcx; unsigned __int64
0x180032959  lea     rdx, ?DiscoverCallback@TenantInfo@@CAXPEAU_DISCOVERY_METADATA@@Ustruct_dsreg_server_response@@_KJ@Z; void (__high *)(struct _DISCOVERY_METADATA *, struct struct_dsreg_server_response, unsigned __int64, int)
0x180032960  mov     rcx, [rcx+0E8h]; unsigned __int16 *
0x180032967  call    DsrBeginDiscoverEnterprise
0x18003296c  mov     r13d, eax
0x18003296f  jmp     loc_180032A76
0x180032974  mov     rcx, [rcx+0D0h]; unsigned __int16 *
0x18003297b  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180032980  test    eax, eax
0x180032982  jz      short loc_1800329FD
0x180032984  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180032989  mov     rcx, [rax]
0x18003298c  cmp     [rcx], r15b
0x18003298f  jz      short loc_1800329E5
0x180032991  lea     rdx, aTenantinfoDisc; "TenantInfo::Discover"
0x180032998  lea     rcx, aSTenantDomainN; "%s: Tenant domain name is empty\n"
0x18003299f  call    wprintf
0x1800329a4  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800329a9  mov     rcx, [rax]
0x1800329ac  cmp     [rcx+0Ch], r15b
0x1800329b0  jz      short loc_1800329E5
0x1800329b2  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800329b7  mov     rcx, [rax]
0x1800329ba  cmp     [rcx+0B8h], r15
0x1800329c1  jz      short loc_1800329E5
0x1800329c3  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800329c8  mov     rcx, [rax]
0x1800329cb  lea     r8, aTenantinfoDisc; "TenantInfo::Discover"
0x1800329d2  lea     rdx, aSTenantDomainN; "%s: Tenant domain name is empty\n"
0x1800329d9  mov     rcx, [rcx+0B8h]; Stream
0x1800329e0  call    fwprintf_s
0x1800329e5  lea     rdx, aTenantinfoDisc; "TenantInfo::Discover"
0x1800329ec  lea     rcx, aSTenantDomainN; "%s: Tenant domain name is empty\n"
0x1800329f3  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800329f8  jmp     loc_1800327CC
0x1800329fd  lea     rdx, aUser_0; "user@"
0x180032a04  lea     rcx, [rsp+108h+Src]
0x180032a0c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180032a11  nop
0x180032a12  mov     rax, [r12]
0x180032a16  mov     rdx, [rax+0D0h]
0x180032a1d  inc     rdi
0x180032a20  cmp     [rdx+rdi*2], r15w
0x180032a25  jnz     short loc_180032A1D
0x180032a27  mov     r8, rdi
0x180032a2a  lea     rcx, [rsp+108h+Src]; Src
0x180032a32  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180032a37  lea     rcx, [rsp+108h+Src]
0x180032a3f  cmp     [rsp+108h+var_68], 7
0x180032a48  cmova   rcx, [rsp+108h+Src]; unsigned __int16 *
0x180032a51  mov     [rsp+108h+var_E8], r14; unsigned __int16 *
0x180032a56  mov     r9, [r12]
0x180032a5a  lea     r8, ?DiscoverCallback@TenantInfo@@CAXPEAU_DISCOVERY_METADATA@@Ustruct_dsreg_server_response@@_KJ@Z; TenantInfo::DiscoverCallback(_DISCOVERY_METADATA *,struct_dsreg_server_response,unsigned __int64,long)
0x180032a61  call    DsrBeginDiscoverEx
0x180032a66  mov     r13d, eax
0x180032a69  lea     rcx, [rsp+108h+Src]
0x180032a71  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180032a76  test    r13d, r13d
0x180032a79  jns     short loc_180032AEE
0x180032a7b  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180032a80  mov     rcx, [rax]
0x180032a83  cmp     [rcx], r15b
0x180032a86  jz      short loc_180032AE2
0x180032a88  mov     r8d, r13d
0x180032a8b  lea     rdx, aTenantinfoDisc; "TenantInfo::Discover"
0x180032a92  lea     rcx, aSCallToDsrbegi; "%s: Call to DsrBeginDiscover failed bef"...
0x180032a99  call    wprintf
0x180032a9e  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180032aa3  mov     rcx, [rax]
0x180032aa6  cmp     [rcx+0Ch], r15b
0x180032aaa  jz      short loc_180032AE2
0x180032aac  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180032ab1  mov     rcx, [rax]
0x180032ab4  cmp     [rcx+0B8h], r15
0x180032abb  jz      short loc_180032AE2
0x180032abd  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180032ac2  mov     rcx, [rax]
0x180032ac5  mov     r9d, r13d
0x180032ac8  lea     r8, aTenantinfoDisc; "TenantInfo::Discover"
0x180032acf  lea     rdx, aSCallToDsrbegi; "%s: Call to DsrBeginDiscover failed bef"...
0x180032ad6  mov     rcx, [rcx+0B8h]; Stream
0x180032add  call    fwprintf_s
0x180032ae2  lea     rcx, aSCallToDsrbegi; "%s: Call to DsrBeginDiscover failed bef"...
0x180032ae9  jmp     loc_18003287A
0x180032aee  mov     rcx, [r12]
0x180032af2  mov     edi, 1D4C0h
0x180032af7  mov     edx, edi; dwMilliseconds
0x180032af9  mov     rcx, [rcx+18h]; hHandle
0x180032afd  call    cs:__imp_WaitForSingleObject
0x180032b03  mov     esi, 102h
0x180032b08  cmp     eax, esi
0x180032b0a  jnz     loc_180032BA2
0x180032b10  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180032b15  mov     rcx, [rax]
0x180032b18  cmp     [rcx], r15b
0x180032b1b  jz      short loc_180032B7E
0x180032b1d  mov     r9d, esi
0x180032b20  mov     r8d, edi
0x180032b23  lea     rdx, aTenantinfoDisc; "TenantInfo::Discover"
0x180032b2a  lea     rcx, aSDsrbegindisco_0; "%s: DsrBeginDiscover timed out. Timeout"...
0x180032b31  call    wprintf
0x180032b36  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180032b3b  mov     rcx, [rax]
0x180032b3e  cmp     [rcx+0Ch], r15b
0x180032b42  jz      short loc_180032B7E
0x180032b44  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180032b49  mov     rcx, [rax]
0x180032b4c  cmp     [rcx+0B8h], r15
0x180032b53  jz      short loc_180032B7E
0x180032b55  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180032b5a  mov     rcx, [rax]
0x180032b5d  mov     dword ptr [rsp+108h+var_E8], esi
0x180032b61  mov     r9d, edi
  ... truncated ...
```
