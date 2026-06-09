# DsrCmdStatusHelper::GetUrlsWinhttpProxyConfigMessage(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,DiscoverTenantResult &,_WINHTTP_CURRENT_USER_IE_PROXY_CONFIG const &)

- ea: `0x18002d2d8`
- end: `0x18002dd1c`
- name: `?GetUrlsWinhttpProxyConfigMessage@DsrCmdStatusHelper@@CAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUDiscoverTenantResult@@AEBU_WINHTTP_CURRENT_USER_IE_PROXY_CONFIG@@@Z`
- size: `2628`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002a7e8`

## callees

- `0x18000eda4`
- `0x180012948`
- `0x180012c7c`
- `0x18001378c`
- `0x180015f3c`
- `0x180016190`
- `0x180016ae0`
- `0x180016b90`
- `0x18001a7e8`
- `0x18001a900`
- `0x18001b560`
- `0x18002927c`
- `0x1800292ac`
- `0x1800294cc`
- `0x180029554`
- `0x18002b9b4`
- `0x18002b9f4`
- `0x18002ba70`
- `0x18002d2d8`
- `0x18002dec0`
- `0x18002deec`
- `0x1800319ac`
- `0x180032618`
- `0x180035fc8`
- `0x180044300`
- `0x180046ae8`
- `0x180046b3c`
- `0x18004c490`
- `0x1800a1a50`
- `0x1800a1dd8`
- `0x1800a70fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d76a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002daac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d76a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002daac`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002d7ab`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002db1a`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002dc2a`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002d7ab`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002db1a`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002dc2a`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x18002d7b6`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x18002db25`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x18002dc35`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x18002d7b6`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x18002db25`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x18002dc35`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002d754`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002da8a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002da95`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002d754`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002da8a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002da95`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18002d952`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18002d952`
- `WINHTTP!WinHttpDetectAutoProxyConfigUrl` at `0x18002d727`
- `WINHTTP!WinHttpDetectAutoProxyConfigUrl` at `0x18002d727`

## string_xrefs

- `0x18002d77f`: `Failed to auto detect the Proxy Auto-Configuration (PAC) script using WPAD. code: `
- `0x18002d6a9`: `https://login.microsoftonline.com`
- `0x18002d9cd`: `Access Type`
- `0x18002d88c`: `Proxy Auto-Config URL`
- `0x18002dc01`: `Failed trying to get URL specific WinHTTP proxy config with error code: `

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall DsrCmdStatusHelper::GetUrlsWinhttpProxyConfigMessage(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  std::_Ref_count_base *v8; // rbx
  unsigned int v9; // ebx
  __int64 v10; // rbx
  LPCWCH *v11; // rdi
  _QWORD *v12; // rdx
  _QWORD *v13; // r8
  _QWORD *v14; // rdx
  _QWORD *v15; // r8
  _QWORD *v16; // r8
  int v17; // eax
  int v18; // edx
  __int64 v19; // rdx
  __int64 v20; // rcx
  _QWORD *CurrentRef; // rax
  __int64 v22; // rdx
  _QWORD *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rcx
  _QWORD *v28; // rax
  __int64 v29; // rdx
  _QWORD *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 v33; // rbx
  __int64 v34; // rax
  __int64 v35; // rax
  WCHAR *v36; // rax
  __int64 v37; // rdi
  __int64 v38; // rsi
  __int64 v39; // r8
  _BYTE *v40; // rax
  const wchar_t *v41; // rdx
  signed int LastError; // eax
  unsigned int v43; // ebx
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  _QWORD *MsgRow; // rax
  _WORD *v48; // rdx
  _QWORD *v49; // rax
  int v50; // ebx
  unsigned __int64 v51; // rdi
  const WCHAR *v52; // rax
  unsigned __int64 i; // rsi
  __int64 v54; // rbx
  _QWORD *v55; // rax
  __int64 v56; // rbx
  _QWORD *v57; // rax
  _QWORD *v58; // rax
  signed int v59; // eax
  unsigned int v60; // ebx
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rbx
  _QWORD *v67; // rax
  _QWORD *v68; // rax
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // rax
  LPWSTR ppwstrAutoConfigUrl; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v75; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD *v76; // [rsp+38h] [rbp-C8h]
  WINHTTP_PROXY_INFO pProxyInfo; // [rsp+40h] [rbp-C0h] BYREF
  void **v78; // [rsp+58h] [rbp-A8h] BYREF
  HINTERNET hSession; // [rsp+60h] [rbp-A0h]
  int v80; // [rsp+68h] [rbp-98h]
  std::_Ref_count_base *v81[2]; // [rsp+70h] [rbp-90h] BYREF
  WINHTTP_AUTOPROXY_OPTIONS pAutoProxyOptions; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v83[8]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v84[232]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v85[8]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v86[232]; // [rsp+198h] [rbp+98h] BYREF
  _BYTE v87[8]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v88[232]; // [rsp+288h] [rbp+188h] BYREF
  _BYTE v89[32]; // [rsp+370h] [rbp+270h] BYREF
  _BYTE v90[32]; // [rsp+390h] [rbp+290h] BYREF
  char *v91[2]; // [rsp+3B0h] [rbp+2B0h] BYREF
  __int64 v92; // [rsp+3C0h] [rbp+2C0h]
  unsigned __int64 v93; // [rsp+3C8h] [rbp+2C8h]
  _BYTE v94[32]; // [rsp+3D0h] [rbp+2D0h] BYREF
  _QWORD v95[4]; // [rsp+3F0h] [rbp+2F0h] BYREF

  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>((__int64)v83);
  std::wstring::wstring((__int64)v91);
  memset(&pProxyInfo, 0, sizeof(pProxyInfo));
  memset(&pAutoProxyOptions, 0, sizeof(pAutoProxyOptions));
  hSession = 0;
  v78 = &WinHttpSession::`vftable';
  v80 = 0;
  *(_OWORD *)v81 = 0;
  std::vector<DsrHKeyUserHandle>::vector<DsrHKeyUserHandle>(&v75);
  std::wstring::wstring((__int64)v95);
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>((__int64)v87);
  if ( *(_BYTE *)(a2 + 16) )
  {
    if ( *(int *)(a2 + 20) < 0 )
      goto LABEL_32;
    v8 = *(std::_Ref_count_base **)a2;
  }
  else
  {
    v9 = TenantInfo::Discover((unsigned __int64 *)v81, 0, 0);
    if ( (v9 & 0x80000000) != 0 )
    {
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(v7, v6) )
      {
        wprintf(L"Tenant discovery failed with error code: 0x%08x\n", v9);
        CurrentRef = (_QWORD *)CmdOptions::GetCurrentRef(v20, v19);
        if ( *(_BYTE *)(*CurrentRef + 12LL) )
        {
          v23 = (_QWORD *)CmdOptions::GetCurrentRef(*CurrentRef, v22);
          if ( *(_QWORD *)(*v23 + 184LL) )
          {
            v25 = CmdOptions::GetCurrentRef(*v23, v24);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v25 + 184LL),
              L"Tenant discovery failed with error code: 0x%08x\n",
              v9);
          }
        }
      }
      Logger::TraceInformation(L"Tenant discovery failed with error code: 0x%08x\n", v9);
      goto LABEL_32;
    }
    v8 = v81[0];
  }
  v10 = *(_QWORD *)v8;
  if ( v10 )
  {
    v11 = (LPCWCH *)(v10 + 48);
    if ( *((_QWORD **)&v75 + 1) == v76 )
    {
      std::vector<unsigned short const *>::_Emplace_reallocate<unsigned short const * const &>(
        &v75,
        *((_QWORD *)&v75 + 1),
        v10 + 48);
      v12 = (_QWORD *)*((_QWORD *)&v75 + 1);
    }
    else
    {
      **((_QWORD **)&v75 + 1) = *v11;
      v12 = (_QWORD *)(*((_QWORD *)&v75 + 1) + 8LL);
      *((_QWORD *)&v75 + 1) += 8LL;
    }
    v13 = (_QWORD *)(v10 + 24);
    if ( v12 == v76 )
    {
      std::vector<unsigned short const *>::_Emplace_reallocate<unsigned short const * const &>(&v75, v12, v13);
      v14 = (_QWORD *)*((_QWORD *)&v75 + 1);
    }
    else
    {
      *v12 = *v13;
      v14 = (_QWORD *)(*((_QWORD *)&v75 + 1) + 8LL);
      *((_QWORD *)&v75 + 1) += 8LL;
    }
    v15 = (_QWORD *)(v10 + 32);
    if ( v14 == v76 )
    {
      std::vector<unsigned short const *>::_Emplace_reallocate<unsigned short const * const &>(&v75, v14, v15);
    }
    else
    {
      *v14 = *v15;
      *((_QWORD *)&v75 + 1) += 8LL;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADCloudKerbHaadj>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AADCloudKerbHaadj>::GetImpl'::`2'::impl) )
    {
      v16 = (_QWORD *)(v10 + 224);
      if ( *((_QWORD **)&v75 + 1) == v76 )
      {
        std::vector<unsigned short const *>::_Emplace_reallocate<unsigned short const * const &>(
          &v75,
          *((_QWORD *)&v75 + 1),
          v16);
      }
      else
      {
        **((_QWORD **)&v75 + 1) = *v16;
        *((_QWORD *)&v75 + 1) += 8LL;
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADClientTLSOneDotThreeSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AADClientTLSOneDotThreeSupport>::GetImpl'::`2'::impl) )
    {
      LODWORD(ppwstrAutoConfigUrl) = 0;
      v17 = StringCompare(*v11, *(const unsigned __int16 **)(v10 + 232), 0x30001u, (int *)&ppwstrAutoConfigUrl);
      v18 = (int)ppwstrAutoConfigUrl;
      if ( v17 < 0 )
        v18 = 0;
      if ( !v18 )
      {
        if ( *((_QWORD **)&v75 + 1) == v76 )
        {
          std::vector<unsigned short const *>::_Emplace_reallocate<unsigned short const * const &>(
            &v75,
            *((_QWORD *)&v75 + 1),
            v10 + 232);
        }
        else
        {
          **((_QWORD **)&v75 + 1) = *(_QWORD *)(v10 + 232);
          *((_QWORD *)&v75 + 1) += 8LL;
        }
      }
    }
    goto LABEL_44;
  }
LABEL_32:
  if ( **(_BYTE **)CmdOptions::GetCurrentRef(v7, v6) )
  {
    wprintf(L"Finding the proxy for the default Urls because tenant discovery failed.\n");
    v28 = (_QWORD *)CmdOptions::GetCurrentRef(v27, v26);
    if ( *(_BYTE *)(*v28 + 12LL) )
    {
      v30 = (_QWORD *)CmdOptions::GetCurrentRef(*v28, v29);
      if ( *(_QWORD *)(*v30 + 184LL) )
      {
        v32 = CmdOptions::GetCurrentRef(*v30, v31);
        fwprintf_s(
          *(FILE *const *)(*(_QWORD *)v32 + 184LL),
          L"Finding the proxy for the default Urls because tenant discovery failed.\n");
      }
    }
  }
  Logger::TraceInformation(L"Finding the proxy for the default Urls because tenant discovery failed.\n");
  if ( *(_QWORD *)a2 )
  {
    v33 = *(_QWORD *)a2 + 32LL;
    if ( *(_QWORD *)a2 != -32 )
    {
      if ( *(_QWORD *)(*(_QWORD *)a2 + 208LL) )
      {
        v34 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                (__int64)v87,
                (__int64)L"https://enterpriseregistration.windows.net/");
        v35 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v34, *(_QWORD *)(v33 + 176));
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v35, (__int64)L"/Discover");
        std::basic_stringbuf<unsigned short>::str(v88, v94);
        std::wstring::operator=((__int64)v95, (__int64)v94);
        std::wstring::_Tidy_deallocate((__int64)v94);
        v36 = (WCHAR *)v95;
        if ( v95[3] > 7u )
          v36 = (WCHAR *)v95[0];
        ppwstrAutoConfigUrl = v36;
        std::vector<unsigned short const *>::push_back(&v75, &ppwstrAutoConfigUrl);
      }
    }
  }
  ppwstrAutoConfigUrl = L"https://enterpriseregistration.windows.net/EnrollmentServer/device";
  std::vector<unsigned short const *>::push_back(&v75, &ppwstrAutoConfigUrl);
  ppwstrAutoConfigUrl = (LPWSTR)L"https://enterpriseregistration.windows.net";
  std::vector<unsigned short const *>::push_back(&v75, &ppwstrAutoConfigUrl);
  ppwstrAutoConfigUrl = L"https://login.microsoftonline.com";
  std::vector<unsigned short const *>::push_back(&v75, &ppwstrAutoConfigUrl);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADClientTLSOneDotThreeSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AADClientTLSOneDotThreeSupport>::GetImpl'::`2'::impl) )
  {
    ppwstrAutoConfigUrl = L"https://certauth.enterpriseregistration.windows.net/EnrollmentServer/device";
    std::vector<unsigned short const *>::push_back(&v75, &ppwstrAutoConfigUrl);
  }
LABEL_44:
  v37 = *((_QWORD *)&v75 + 1) - v75;
  v38 = -1;
  if ( *(_DWORD *)a3 )
  {
    ppwstrAutoConfigUrl = 0;
    std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>((__int64)v85);
    if ( WinHttpDetectAutoProxyConfigUrl(3u, &ppwstrAutoConfigUrl) )
    {
      v39 = -1;
      do
        ++v39;
      while ( ppwstrAutoConfigUrl[v39] );
      std::wstring::_Assign<unsigned short>(v91, ppwstrAutoConfigUrl, (char *)v39);
      GlobalFree(ppwstrAutoConfigUrl);
      v40 = v85;
      v41 = L"Success";
    }
    else
    {
      LastError = GetLastError();
      v43 = LastError;
      if ( LastError > 0 )
        v43 = (unsigned __int16)LastError | 0x80070000;
      v44 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
              (__int64)v85,
              (__int64)L"Failed to auto detect the Proxy Auto-Configuration (PAC) script using WPAD. code: ");
      v45 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v44, (__int64)L"0x");
      v46 = std::basic_ostream<unsigned short>::operator<<(v45, std::hex);
      v40 = (_BYTE *)std::basic_ostream<unsigned short>::operator<<(v46, v43);
      v41 = L"\n";
    }
    std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64)v40, (__int64)v41);
    std::basic_stringbuf<unsigned short>::str(v86, v89);
    std::wstring::wstring((__int64)v94, (__int64)L"Auto Detect PAC Status");
    MsgRow = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v90, v94, v89);
    std::operator<<<unsigned short>((__int64)v83, MsgRow);
    std::wstring::_Tidy_deallocate((__int64)v90);
    std::wstring::_Tidy_deallocate((__int64)v94);
    std::wstring::_Tidy_deallocate((__int64)v89);
    std::basic_ostringstream<unsigned short>::`vbase destructor'((__int64)v85);
  }
  if ( v92 )
    goto LABEL_57;
  v48 = *(_WORD **)(a3 + 8);
  if ( v48 )
  {
    do
      ++v38;
    while ( v48[v38] );
    std::wstring::_Assign<unsigned short>(v91, v48, (char *)v38);
    if ( v92 )
    {
LABEL_57:
      std::wstring::wstring((__int64)v89, (__int64)L"Proxy Auto-Config URL");
      v49 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v90, v89, v91);
      std::operator<<<unsigned short>((__int64)v83, v49);
      std::wstring::_Tidy_deallocate((__int64)v90);
      std::wstring::_Tidy_deallocate((__int64)v89);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64)v83, (__int64)L"\n");
      v50 = WinHttpSession::Initialize((WinHttpSession *)&v78);
      if ( v50 < 0 )
      {
        v69 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                (__int64)v83,
                (__int64)L"Failed trying to get URL specific WinHTTP proxy config with error code: ");
        v70 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v69, (__int64)L"0x");
        v71 = std::basic_ostream<unsigned short>::operator<<(v70, std::hex);
        v72 = std::basic_ostream<unsigned short>::operator<<(v71, (unsigned int)v50);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v72, (__int64)L"\n");
      }
      else
      {
        v51 = v37 >> 3;
        *(_QWORD *)&pAutoProxyOptions.dwFlags = 2;
        v52 = (const WCHAR *)v91;
        if ( v93 > 7 )
          v52 = (const WCHAR *)v91[0];
        pAutoProxyOptions.lpszAutoConfigUrl = v52;
        pAutoProxyOptions.fAutoLogonIfChallenged = 1;
        for ( i = 0; i < v51; ++i )
        {
          if ( WinHttpGetProxyForUrl(hSession, *(LPCWSTR *)(v75 + 8 * i), &pAutoProxyOptions, &pProxyInfo) )
          {
            v54 = *(_QWORD *)(v75 + 8 * i);
            std::wstring::wstring((__int64)v89, (__int64)L"URL");
            v55 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v90, v89, v54);
            std::operator<<<unsigned short>((__int64)v83, v55);
            std::wstring::_Tidy_deallocate((__int64)v90);
            std::wstring::_Tidy_deallocate((__int64)v89);
            v56 = AccessTypeToString(v94, pProxyInfo.dwAccessType);
            std::wstring::wstring((__int64)v89, (__int64)L"Access Type");
            v57 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v90, v89, v56);
            std::operator<<<unsigned short>((__int64)v83, v57);
            std::wstring::_Tidy_deallocate((__int64)v90);
            std::wstring::_Tidy_deallocate((__int64)v89);
            std::wstring::_Tidy_deallocate((__int64)v94);
            if ( pProxyInfo.dwAccessType != 1 )
            {
              std::wstring::wstring((__int64)v89, (__int64)L"Proxy Server List");
              v58 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v90, v89, pProxyInfo.lpszProxy);
              std::operator<<<unsigned short>((__int64)v83, v58);
              std::wstring::_Tidy_deallocate((__int64)v90);
              std::wstring::_Tidy_deallocate((__int64)v89);
            }
            GlobalFree(pProxyInfo.lpszProxy);
            GlobalFree(pProxyInfo.lpszProxyBypass);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64)v83, (__int64)L"\n");
          }
          else
          {
            v59 = GetLastError();
            v60 = v59;
            if ( v59 > 0 )
              v60 = (unsigned __int16)v59 | 0x80070000;
            std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>((__int64)v85);
            v61 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                    (__int64)v85,
                    (__int64)L"Failed trying to find the proxy for the URL ");
            v62 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v61, *(_QWORD *)(v75 + 8 * i));
            v63 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v62, (__int64)L" with error code ");
            v64 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v63, (__int64)L"0x");
            v65 = std::basic_ostream<unsigned short>::operator<<(v64, std::hex);
            std::basic_ostream<unsigned short>::operator<<(v65, v60);
            v66 = *(_QWORD *)(v75 + 8 * i);
            std::wstring::wstring((__int64)v89, (__int64)L"URL");
            v67 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v90, v89, v66);
            std::operator<<<unsigned short>((__int64)v83, v67);
            std::wstring::_Tidy_deallocate((__int64)v90);
            std::wstring::_Tidy_deallocate((__int64)v89);
            std::wstring::wstring((__int64)v89, (__int64)L"Error");
            v68 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v90, v89, v85);
            std::operator<<<unsigned short>((__int64)v83, v68);
            std::wstring::_Tidy_deallocate((__int64)v90);
            std::wstring::_Tidy_deallocate((__int64)v89);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64)v83, (__int64)L"\n");
            std::basic_ostringstream<unsigned short>::`vbase destructor'((__int64)v85);
          }
        }
      }
    }
  }
  std::basic_stringbuf<unsigned short>::str(v84, v89);
  std::wstring::operator=(a1, (__int64)v89);
  std::wstring::_Tidy_deallocate((__int64)v89);
  std::basic_ostringstream<unsigned short>::`vbase destructor'((__int64)v87);
  std::wstring::_Tidy_deallocate((__int64)v95);
  if ( (_QWORD)v75 )
  {
    std::_Deallocate<16>((void *)v75, ((unsigned __int64)v76 - v75) & 0xFFFFFFFFFFFFFFF8uLL);
    v75 = 0;
    v76 = 0;
  }
  if ( v81[1] )
    std::_Ref_count_base::_Decref(v81[1]);
  v78 = &WinHttpHandle::`vftable';
  WinHttpHandle::Close((WinHttpHandle *)&v78);
  std::wstring::_Tidy_deallocate((__int64)v91);
  return std::basic_ostringstream<unsigned short>::`vbase destructor'((__int64)v83);
}

```

## disassembly

```asm
0x18002d2d8  mov     [rsp-8+arg_18], rbx
0x18002d2dd  push    rbp
0x18002d2de  push    rsi
0x18002d2df  push    rdi
0x18002d2e0  push    r12
0x18002d2e2  push    r13
0x18002d2e4  push    r14
0x18002d2e6  push    r15
0x18002d2e8  lea     rbp, [rsp-320h]
0x18002d2f0  sub     rsp, 420h
0x18002d2f7  mov     rax, cs:__security_cookie
0x18002d2fe  xor     rax, rsp
0x18002d301  mov     [rbp+350h+var_40], rax
0x18002d308  mov     r14, r8
0x18002d30b  mov     rdi, rdx
0x18002d30e  mov     r15, rcx
0x18002d311  xor     r12d, r12d
0x18002d314  lea     rcx, [rbp+350h+var_3B0]
0x18002d318  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18002d31d  nop
0x18002d31e  lea     rcx, [rbp+350h+var_A0]
0x18002d325  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002d32a  nop
0x18002d32b  xorps   xmm1, xmm1
0x18002d32e  xor     eax, eax
0x18002d330  movups  xmmword ptr [rsp+450h+pProxyInfo.dwAccessType], xmm1
0x18002d335  mov     [rsp+450h+pProxyInfo.lpszProxyBypass], rax
0x18002d33a  xorps   xmm0, xmm0
0x18002d33d  movups  xmmword ptr [rbp+350h+pAutoProxyOptions.dwFlags], xmm0
0x18002d341  movups  xmmword ptr [rbp+350h+pAutoProxyOptions.lpvReserved], xmm0
0x18002d345  mov     [rsp+450h+hSession], r12
0x18002d34a  lea     rax, ??_7WinHttpSession@@6B@; const WinHttpSession::`vftable'
0x18002d351  mov     [rsp+450h+var_3F8], rax
0x18002d356  mov     [rsp+450h+var_3E8], r12d
0x18002d35b  movdqu  xmmword ptr [rsp+450h+var_3E0], xmm0
0x18002d361  lea     rcx, [rsp+450h+var_428]; void *
0x18002d366  call    ??0?$vector@VDsrHKeyUserHandle@@V?$allocator@VDsrHKeyUserHandle@@@std@@@std@@QEAA@XZ; std::vector<DsrHKeyUserHandle>::vector<DsrHKeyUserHandle>(void)
0x18002d36b  nop
0x18002d36c  lea     rcx, [rbp+350h+var_60]
0x18002d373  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002d378  nop
0x18002d379  lea     rcx, [rbp+350h+var_1D0]
0x18002d380  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18002d385  nop
0x18002d386  cmp     [rdi+10h], r12b
0x18002d38a  jz      short loc_18002D39B
0x18002d38c  cmp     [rdi+14h], r12d
0x18002d390  jl      loc_18002D568
0x18002d396  mov     rbx, [rdi]
0x18002d399  jmp     short loc_18002D3B9
0x18002d39b  xor     r8d, r8d
0x18002d39e  xor     edx, edx
0x18002d3a0  lea     rcx, [rsp+450h+var_3E0]
0x18002d3a5  call    ?Discover@TenantInfo@@SAJAEAV?$shared_ptr@VTenantInfo@@@std@@PEBGPEAVDsregServerResponse@@@Z; TenantInfo::Discover(std::shared_ptr<TenantInfo> &,ushort const *,DsregServerResponse *)
0x18002d3aa  mov     ebx, eax
0x18002d3ac  test    eax, eax
0x18002d3ae  js      loc_18002D507
0x18002d3b4  mov     rbx, [rsp+450h+var_3E0]
0x18002d3b9  mov     rbx, [rbx]
0x18002d3bc  test    rbx, rbx
0x18002d3bf  jz      loc_18002D568
0x18002d3c5  lea     rdi, [rbx+30h]
0x18002d3c9  mov     rdx, qword ptr [rsp+450h+var_428+8]
0x18002d3ce  cmp     rdx, [rsp+450h+var_418]
0x18002d3d3  jz      short loc_18002D3EB
0x18002d3d5  mov     rax, [rdi]
0x18002d3d8  mov     [rdx], rax
0x18002d3db  mov     rdx, qword ptr [rsp+450h+var_428+8]
0x18002d3e0  add     rdx, 8
0x18002d3e4  mov     qword ptr [rsp+450h+var_428+8], rdx
0x18002d3e9  jmp     short loc_18002D3FD
0x18002d3eb  mov     r8, rdi
0x18002d3ee  lea     rcx, [rsp+450h+var_428]
0x18002d3f3  call    ??$_Emplace_reallocate@AEBQEBG@?$vector@PEBGV?$allocator@PEBG@std@@@std@@AEAAPEAPEBGQEAPEBGAEBQEBG@Z; std::vector<ushort const *>::_Emplace_reallocate<ushort const * const &>(ushort const * * const,ushort const * const &)
0x18002d3f8  mov     rdx, qword ptr [rsp+450h+var_428+8]
0x18002d3fd  lea     r8, [rbx+18h]
0x18002d401  cmp     rdx, [rsp+450h+var_418]
0x18002d406  jz      short loc_18002D41E
0x18002d408  mov     rax, [r8]
0x18002d40b  mov     [rdx], rax
0x18002d40e  mov     rdx, qword ptr [rsp+450h+var_428+8]
0x18002d413  add     rdx, 8
0x18002d417  mov     qword ptr [rsp+450h+var_428+8], rdx
0x18002d41c  jmp     short loc_18002D42D
0x18002d41e  lea     rcx, [rsp+450h+var_428]
0x18002d423  call    ??$_Emplace_reallocate@AEBQEBG@?$vector@PEBGV?$allocator@PEBG@std@@@std@@AEAAPEAPEBGQEAPEBGAEBQEBG@Z; std::vector<ushort const *>::_Emplace_reallocate<ushort const * const &>(ushort const * * const,ushort const * const &)
0x18002d428  mov     rdx, qword ptr [rsp+450h+var_428+8]
0x18002d42d  lea     r8, [rbx+20h]
0x18002d431  cmp     rdx, [rsp+450h+var_418]
0x18002d436  jz      short loc_18002D446
0x18002d438  mov     rax, [r8]
0x18002d43b  mov     [rdx], rax
0x18002d43e  add     qword ptr [rsp+450h+var_428+8], 8
0x18002d444  jmp     short loc_18002D450
0x18002d446  lea     rcx, [rsp+450h+var_428]
0x18002d44b  call    ??$_Emplace_reallocate@AEBQEBG@?$vector@PEBGV?$allocator@PEBG@std@@@std@@AEAAPEAPEBGQEAPEBGAEBQEBG@Z; std::vector<ushort const *>::_Emplace_reallocate<ushort const * const &>(ushort const * * const,ushort const * const &)
0x18002d450  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AADCloudKerbHaadj@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AADCloudKerbHaadj@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADCloudKerbHaadj> `wil::Feature<__WilFeatureTraits_Feature_AADCloudKerbHaadj>::GetImpl(void)'::`2'::impl
0x18002d457  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AADCloudKerbHaadj@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADCloudKerbHaadj>::__private_IsEnabled(void)
0x18002d45c  test    al, al
0x18002d45e  jz      short loc_18002D48B
0x18002d460  lea     r8, [rbx+0E0h]
0x18002d467  mov     rdx, qword ptr [rsp+450h+var_428+8]
0x18002d46c  cmp     rdx, [rsp+450h+var_418]
0x18002d471  jz      short loc_18002D481
0x18002d473  mov     rax, [r8]
0x18002d476  mov     [rdx], rax
0x18002d479  add     qword ptr [rsp+450h+var_428+8], 8
0x18002d47f  jmp     short loc_18002D48B
0x18002d481  lea     rcx, [rsp+450h+var_428]
0x18002d486  call    ??$_Emplace_reallocate@AEBQEBG@?$vector@PEBGV?$allocator@PEBG@std@@@std@@AEAAPEAPEBGQEAPEBGAEBQEBG@Z; std::vector<ushort const *>::_Emplace_reallocate<ushort const * const &>(ushort const * * const,ushort const * const &)
0x18002d48b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AADClientTLSOneDotThreeSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AADClientTLSOneDotThreeSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADClientTLSOneDotThreeSupport> `wil::Feature<__WilFeatureTraits_Feature_AADClientTLSOneDotThreeSupport>::GetImpl(void)'::`2'::impl
0x18002d492  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AADClientTLSOneDotThreeSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADClientTLSOneDotThreeSupport>::__private_IsEnabled(void)
0x18002d497  test    al, al
0x18002d499  jz      loc_18002D6EF
0x18002d49f  mov     dword ptr [rsp+450h+ppwstrAutoConfigUrl], r12d
0x18002d4a4  lea     r9, [rsp+450h+ppwstrAutoConfigUrl]; int *
0x18002d4a9  mov     r8d, 30001h; unsigned int
0x18002d4af  mov     rdx, [rbx+0E8h]; unsigned __int16 *
0x18002d4b6  mov     rcx, [rdi]; lpString1
0x18002d4b9  call    ?StringCompare@@YAJPEBG0KPEAH@Z; StringCompare(ushort const *,ushort const *,ulong,int *)
0x18002d4be  mov     edx, dword ptr [rsp+450h+ppwstrAutoConfigUrl]
0x18002d4c2  test    eax, eax
0x18002d4c4  cmovs   edx, r12d
0x18002d4c8  test    edx, edx
0x18002d4ca  jnz     loc_18002D6EF
0x18002d4d0  mov     rdx, qword ptr [rsp+450h+var_428+8]
0x18002d4d5  cmp     rdx, [rsp+450h+var_418]
0x18002d4da  jz      short loc_18002D4F1
0x18002d4dc  mov     rax, [rbx+0E8h]
0x18002d4e3  mov     [rdx], rax
0x18002d4e6  add     qword ptr [rsp+450h+var_428+8], 8
0x18002d4ec  jmp     loc_18002D6EF
0x18002d4f1  lea     r8, [rbx+0E8h]
0x18002d4f8  lea     rcx, [rsp+450h+var_428]
0x18002d4fd  call    ??$_Emplace_reallocate@AEBQEBG@?$vector@PEBGV?$allocator@PEBG@std@@@std@@AEAAPEAPEBGQEAPEBGAEBQEBG@Z; std::vector<ushort const *>::_Emplace_reallocate<ushort const * const &>(ushort const * * const,ushort const * const &)
0x18002d502  jmp     loc_18002D6EF
0x18002d507  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002d50c  mov     rcx, [rax]
0x18002d50f  lea     rsi, aTenantDiscover; "Tenant discovery failed with error code"...
0x18002d516  cmp     [rcx], r12b
0x18002d519  jz      short loc_18002D55E
0x18002d51b  mov     edx, ebx
0x18002d51d  mov     rcx, rsi; Format
0x18002d520  call    wprintf
0x18002d525  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002d52a  mov     rcx, [rax]
0x18002d52d  cmp     [rcx+0Ch], r12b
0x18002d531  jz      short loc_18002D55E
0x18002d533  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002d538  mov     rcx, [rax]
0x18002d53b  cmp     [rcx+0B8h], r12
0x18002d542  jz      short loc_18002D55E
0x18002d544  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002d549  mov     rcx, [rax]
0x18002d54c  mov     r8d, ebx
0x18002d54f  mov     rdx, rsi; Format
0x18002d552  mov     rcx, [rcx+0B8h]; Stream
0x18002d559  call    fwprintf_s
0x18002d55e  mov     edx, ebx
0x18002d560  mov     rcx, rsi; unsigned __int16 *
0x18002d563  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18002d568  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002d56d  mov     rcx, [rax]
0x18002d570  lea     rbx, aFindingTheProx; "Finding the proxy for the default Urls "...
0x18002d577  cmp     [rcx], r12b
0x18002d57a  jz      short loc_18002D5BA
0x18002d57c  mov     rcx, rbx; Format
0x18002d57f  call    wprintf
0x18002d584  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002d589  mov     rcx, [rax]
0x18002d58c  cmp     [rcx+0Ch], r12b
0x18002d590  jz      short loc_18002D5BA
0x18002d592  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002d597  mov     rcx, [rax]
0x18002d59a  cmp     [rcx+0B8h], r12
0x18002d5a1  jz      short loc_18002D5BA
0x18002d5a3  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18002d5a8  mov     rcx, [rax]
0x18002d5ab  mov     rdx, rbx; Format
0x18002d5ae  mov     rcx, [rcx+0B8h]; Stream
0x18002d5b5  call    fwprintf_s
0x18002d5ba  mov     rcx, rbx; unsigned __int16 *
0x18002d5bd  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18002d5c2  mov     rbx, [rdi]
0x18002d5c5  test    rbx, rbx
0x18002d5c8  jz      loc_18002D673
0x18002d5ce  add     rbx, 20h ; ' '
0x18002d5d2  jz      loc_18002D673
0x18002d5d8  cmp     [rbx+0B0h], r12
0x18002d5df  jz      loc_18002D673
0x18002d5e5  lea     rdx, aHttpsEnterpris_1; "https://enterpriseregistration.windows."...
0x18002d5ec  lea     rcx, [rbp+350h+var_1D0]
0x18002d5f3  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002d5f8  mov     rdx, [rbx+0B0h]
0x18002d5ff  mov     rcx, rax
0x18002d602  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002d607  mov     rcx, rax
0x18002d60a  lea     rdx, aDiscover_1; "/Discover"
0x18002d611  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002d616  lea     rdx, [rbp+350h+var_80]
0x18002d61d  lea     rcx, [rbp+350h+var_1C8]
0x18002d624  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18002d629  lea     rdx, [rbp+350h+var_80]
0x18002d630  lea     rcx, [rbp+350h+var_60]
0x18002d637  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002d63c  lea     rcx, [rbp+350h+var_80]
0x18002d643  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d648  lea     rax, [rbp+350h+var_60]
0x18002d64f  cmp     [rbp+350h+var_48], 7
0x18002d657  cmova   rax, [rbp+350h+var_60]
0x18002d65f  mov     [rsp+450h+ppwstrAutoConfigUrl], rax
0x18002d664  lea     rdx, [rsp+450h+ppwstrAutoConfigUrl]
0x18002d669  lea     rcx, [rsp+450h+var_428]
0x18002d66e  call    ?push_back@?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAAX$$QEAPEBG@Z; std::vector<ushort const *>::push_back(ushort const * &&)
0x18002d673  lea     rax, aHttpsEnterpris_2; "https://enterpriseregistration.windows."...
0x18002d67a  mov     [rsp+450h+ppwstrAutoConfigUrl], rax
0x18002d67f  lea     rdx, [rsp+450h+ppwstrAutoConfigUrl]
0x18002d684  lea     rcx, [rsp+450h+var_428]
0x18002d689  call    ?push_back@?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAAX$$QEAPEBG@Z; std::vector<ushort const *>::push_back(ushort const * &&)
0x18002d68e  lea     rax, aHttpsEnterpris_3; "https://enterpriseregistration.windows."...
0x18002d695  mov     [rsp+450h+ppwstrAutoConfigUrl], rax
0x18002d69a  lea     rdx, [rsp+450h+ppwstrAutoConfigUrl]
0x18002d69f  lea     rcx, [rsp+450h+var_428]
0x18002d6a4  call    ?push_back@?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAAX$$QEAPEBG@Z; std::vector<ushort const *>::push_back(ushort const * &&)
0x18002d6a9  lea     rax, aHttpsLoginMicr_3; "https://login.microsoftonline.com"
0x18002d6b0  mov     [rsp+450h+ppwstrAutoConfigUrl], rax
0x18002d6b5  lea     rdx, [rsp+450h+ppwstrAutoConfigUrl]
0x18002d6ba  lea     rcx, [rsp+450h+var_428]
0x18002d6bf  call    ?push_back@?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAAX$$QEAPEBG@Z; std::vector<ushort const *>::push_back(ushort const * &&)
0x18002d6c4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AADClientTLSOneDotThreeSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AADClientTLSOneDotThreeSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADClientTLSOneDotThreeSupport> `wil::Feature<__WilFeatureTraits_Feature_AADClientTLSOneDotThreeSupport>::GetImpl(void)'::`2'::impl
0x18002d6cb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AADClientTLSOneDotThreeSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADClientTLSOneDotThreeSupport>::__private_IsEnabled(void)
0x18002d6d0  test    al, al
0x18002d6d2  jz      short loc_18002D6EF
0x18002d6d4  lea     rax, aHttpsCertauthE; "https://certauth.enterpriseregistration"...
0x18002d6db  mov     [rsp+450h+ppwstrAutoConfigUrl], rax
0x18002d6e0  lea     rdx, [rsp+450h+ppwstrAutoConfigUrl]
0x18002d6e5  lea     rcx, [rsp+450h+var_428]
0x18002d6ea  call    ?push_back@?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAAX$$QEAPEBG@Z; std::vector<ushort const *>::push_back(ushort const * &&)
0x18002d6ef  mov     rdi, qword ptr [rsp+450h+var_428+8]
0x18002d6f4  sub     rdi, qword ptr [rsp+450h+var_428]
0x18002d6f9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002d6fd  lea     r13, asc_1800C6838; "\n"
0x18002d704  cmp     [r14], r12d
0x18002d707  jz      loc_18002D84A
0x18002d70d  mov     [rsp+450h+ppwstrAutoConfigUrl], r12
0x18002d712  lea     rcx, [rbp+350h+var_2C0]
0x18002d719  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18002d71e  nop
0x18002d71f  lea     rdx, [rsp+450h+ppwstrAutoConfigUrl]; ppwstrAutoConfigUrl
0x18002d724  lea     ecx, [rsi+4]; dwAutoDetectFlags
0x18002d727  call    cs:__imp_WinHttpDetectAutoProxyConfigUrl
0x18002d72d  test    eax, eax
0x18002d72f  jz      short loc_18002D76A
0x18002d731  mov     rdx, [rsp+450h+ppwstrAutoConfigUrl]
0x18002d736  mov     r8, rsi
0x18002d739  inc     r8
0x18002d73c  cmp     [rdx+r8*2], r12w
0x18002d741  jnz     short loc_18002D739
0x18002d743  lea     rcx, [rbp+350h+var_A0]
0x18002d74a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002d74f  mov     rcx, [rsp+450h+ppwstrAutoConfigUrl]; hMem
0x18002d754  call    cs:__imp_GlobalFree
0x18002d75a  lea     rax, [rbp+350h+var_2C0]
0x18002d761  lea     rdx, aSuccess_0; "Success"
0x18002d768  jmp     short loc_18002D7BF
0x18002d76a  call    cs:__imp_GetLastError
0x18002d770  mov     ebx, eax
0x18002d772  test    eax, eax
0x18002d774  jle     short loc_18002D77F
0x18002d776  movzx   ebx, ax
0x18002d779  or      ebx, 80070000h
0x18002d77f  lea     rdx, aFailedToAutoDe; "Failed to auto detect the Proxy Auto-Co"...
0x18002d786  lea     rcx, [rbp+350h+var_2C0]
0x18002d78d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002d792  mov     rcx, rax
0x18002d795  lea     rdx, a0x; "0x"
0x18002d79c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002d7a1  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18002d7a8  mov     rcx, rax
0x18002d7ab  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::basic_ostream<ushort>::operator<<(std::ios_base & (*)(std::ios_base &))
0x18002d7b1  mov     edx, ebx
0x18002d7b3  mov     rcx, rax
0x18002d7b6  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z; std::basic_ostream<ushort>::operator<<(long)
0x18002d7bc  mov     rdx, r13
0x18002d7bf  mov     rcx, rax
0x18002d7c2  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002d7c7  lea     rdx, [rbp+350h+var_E0]
0x18002d7ce  lea     rcx, [rbp+350h+var_2B8]
0x18002d7d5  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18002d7da  nop
0x18002d7db  lea     rdx, aAutoDetectPacS; "Auto Detect PAC Status"
0x18002d7e2  lea     rcx, [rbp+350h+var_80]
0x18002d7e9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002d7ee  nop
0x18002d7ef  lea     r8, [rbp+350h+var_E0]
0x18002d7f6  lea     rdx, [rbp+350h+var_80]
0x18002d7fd  lea     rcx, [rbp+350h+var_C0]
0x18002d804  call    ?CreateMsgRow@DsrCmdStatusHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@0@Z; DsrCmdStatusHelper::CreateMsgRow(std::wstring const &,std::wstring const &)
0x18002d809  nop
0x18002d80a  mov     rdx, rax
  ... truncated ...
```
