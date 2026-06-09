# DAS::ProviderManagement::ProviderManager::RegisterProviderStatic(_DAF_PROVIDER_PATH,ulong,ulong,ulong,ulong,ushort const *,ushort const *,_GUID const *,ushort const *,_GUID const *)

- ea: `0x180060ec0`
- end: `0x1800618ad`
- name: `?RegisterProviderStatic@ProviderManager@ProviderManagement@DAS@@SAJW4_DAF_PROVIDER_PATH@@KKKKPEBG1PEBU_GUID@@12@Z`
- size: `2541`
- prototype: `__int64 __fastcall(unsigned int, int, int, int, BYTE, wchar_t *Str, BYTE *, struct _GUID *, unsigned __int16 *, struct _GUID *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180028ce8`
- `0x180060360`

## callees

- `0x1800074c0`
- `0x18001eae0`
- `0x18002a948`
- `0x18003a3ec`
- `0x180042bc8`
- `0x180049834`
- `0x180060b60`
- `0x180060ec0`
- `0x1800618b4`
- `0x180061b2c`
- `0x180061c40`
- `0x180061c68`
- `0x180061cc8`
- `0x180061d74`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800615b6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800615b6`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18006132b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18006133f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18006132b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18006133f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800611e8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800612b1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006136d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800613ce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006142f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180061490`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180061505`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180061594`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180061728`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006178f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800617c5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800617fb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800611e8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800612b1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006136d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800613ce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006142f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180061490`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180061505`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180061594`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180061728`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006178f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800617c5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800617fb`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180060fe3`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800610b7`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180061610`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800616cc`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180060fe3`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800610b7`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180061610`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800616cc`

## string_xrefs

- `0x18006119b`: `CLSID`
- `0x1800611d1`: `CLSID`
- `0x18006126d`: `ProtocolId`
- `0x18006129f`: `ProtocolId`
- `0x18006177d`: `federated store path`
- `0x1800617b3`: `copy from path`
- `0x1800615af`: `FileCopy`
- `0x1800615f8`: `SOFTWARE\Microsoft\File Copy Provider`
- `0x180061721`: `copy to path`
- `0x180061396`: `SecurityContext`
- `0x1800613bc`: `SecurityContext`
- `0x180061458`: `ImpersonateCaller`
- `0x18006147e`: `ImpersonateCaller`
- `0x1800612f4`: `DllPath`
- `0x18006135a`: `DllPath`

## pseudocode

```c
__int64 __fastcall DAS::ProviderManagement::ProviderManager::RegisterProviderStatic(
        unsigned int a1,
        int a2,
        int a3,
        int a4,
        BYTE a5,
        wchar_t *Str,
        BYTE *a7,
        struct _GUID *a8,
        unsigned __int16 *a9,
        struct _GUID *a10)
{
  __int64 v10; // rbx
  const wchar_t *v11; // rax
  __int64 v12; // rsi
  int v13; // eax
  unsigned int v14; // ebx
  const WCHAR *v15; // rbx
  LSTATUS v16; // eax
  signed int v17; // edi
  __int64 v18; // rdx
  unsigned int v19; // eax
  void *p_hKey; // rcx
  int GuidStringStatic; // eax
  int v22; // r8d
  BYTE *v23; // rbx
  __int64 v24; // rsi
  __int64 v25; // rax
  unsigned int v26; // eax
  int v27; // eax
  int v28; // r8d
  BYTE *v29; // rbx
  __int64 v30; // rax
  unsigned int v31; // eax
  int v32; // r8d
  __int64 v33; // rdx
  wchar_t *v34; // rbx
  __int64 v35; // rax
  DWORD cbData; // edi
  wchar_t *v37; // rax
  wchar_t *v38; // rax
  DWORD v39; // r9d
  int v40; // r8d
  int v41; // r8d
  int v42; // r8d
  int v43; // r8d
  BYTE *v44; // rbx
  PVOID *v45; // rcx
  LSTATUS v46; // eax
  int v47; // eax
  __int64 v48; // rdx
  unsigned int v49; // eax
  unsigned int v50; // eax
  __int64 v51; // rdx
  unsigned int lpData; // [rsp+20h] [rbp-40h]
  unsigned int lpDataa; // [rsp+20h] [rbp-40h]
  unsigned int lpDatab; // [rsp+20h] [rbp-40h]
  unsigned int lpDatac; // [rsp+20h] [rbp-40h]
  HKEY phkResult; // [rsp+30h] [rbp-30h] BYREF
  BYTE *v58; // [rsp+38h] [rbp-28h] BYREF
  BYTE *v59; // [rsp+40h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-18h] BYREF
  LPWSTR pObjectName; // [rsp+50h] [rbp-10h] BYREF
  LPCWSTR lpSubKey; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  int Data; // [rsp+A8h] [rbp+48h] BYREF
  int v65; // [rsp+B0h] [rbp+50h] BYREF
  int v66; // [rsp+B8h] [rbp+58h] BYREF

  v66 = a4;
  v65 = a3;
  Data = a2;
  v10 = (int)a1;
  if ( a1 > 1 )
  {
    v14 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB7,
      (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
      (const char *)0x80070057LL,
      lpData);
    return v14;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v11 = L"inbox";
    if ( !*((_BYTE *)&DAS::ProviderManagement::c_providerRegistrationPaths + 24 * (int)a1 + 16) )
      v11 = (const wchar_t *)L"3rd party";
    WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, (unsigned int)L"3rd party", (_DWORD)a9, (__int64)v11);
  }
  lpSubKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpSubKey,
    0);
  v12 = 3 * v10;
  v13 = DafConcatenateWithDelimiter_3(
          (unsigned __int16 *)*(&DAS::ProviderManagement::c_providerRegistrationPaths + 3 * v10 + 1),
          a9,
          L"\\");
  v14 = v13;
  if ( v13 >= 0 )
  {
    v15 = lpSubKey;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_c259ffd365a33e780ba81409624fcc4e_Traceguids, lpSubKey);
    phkResult = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v16 = RegCreateKeyW((HKEY)*(&DAS::ProviderManagement::c_providerRegistrationPaths + v12), v15, &phkResult);
    v17 = v16;
    if ( v16 == 5 )
    {
      hKey = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &hKey,
        0);
      v17 = DafConcatenateWithDelimiter_3(
              L"MACHINE",
              (unsigned __int16 *)*(&DAS::ProviderManagement::c_providerRegistrationPaths + v12 + 1),
              L"\\");
      if ( v17 < 0 )
      {
        v18 = 204;
LABEL_15:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
          (const char *)(unsigned int)v17,
          lpData);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hKey);
LABEL_16:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
        v14 = v17;
        goto LABEL_127;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_c259ffd365a33e780ba81409624fcc4e_Traceguids, hKey);
      v17 = DAS::ProviderManagement::ProviderManager::TakeKeyOwnership((LPWSTR)hKey);
      if ( v17 < 0 )
      {
        v18 = 206;
        goto LABEL_15;
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &phkResult,
        0);
      v19 = RegCreateKeyW(HKEY_LOCAL_MACHINE, v15, &phkResult);
      if ( v19 )
      {
        v14 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0xCF,
                (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
                (const char *)v19,
                lpData);
        p_hKey = &hKey;
LABEL_126:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(p_hKey);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
        goto LABEL_127;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hKey);
    }
    else
    {
      if ( v16 > 0 )
        v17 = (unsigned __int16)v16 | 0x80070000;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD3,
          (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
          (const char *)(unsigned int)v17,
          lpData);
        goto LABEL_16;
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_c259ffd365a33e780ba81409624fcc4e_Traceguids);
    v58 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v58,
      0);
    GuidStringStatic = DAS::ProviderManagement::ProviderManager::MakeGuidStringStatic(a8, (unsigned __int16 **)&v58);
    v14 = GuidStringStatic;
    if ( GuidStringStatic < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD8,
        (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
        (const char *)(unsigned int)GuidStringStatic,
        lpData);
LABEL_125:
      p_hKey = &v58;
      goto LABEL_126;
    }
    v23 = v58;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v22, (unsigned int)L"CLSID", (__int64)v58);
    v24 = -1;
    v25 = -1;
    do
      ++v25;
    while ( *(_WORD *)&v23[2 * v25] );
    v26 = RegSetValueExW(phkResult, L"CLSID", 0, 1u, v23, 2 * v25 + 2);
    if ( v26 )
    {
      v14 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xDA,
              (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
              (const char *)v26,
              lpDataa);
      goto LABEL_125;
    }
    v59 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v59,
      0);
    v27 = DAS::ProviderManagement::ProviderManager::MakeGuidStringStatic(a10, (unsigned __int16 **)&v59);
    v14 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDC,
        (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
        (const char *)(unsigned int)v27,
        lpDataa);
LABEL_124:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v59);
      goto LABEL_125;
    }
    v29 = v59;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, v28, (unsigned int)L"ProtocolId", (__int64)v59);
    v30 = -1;
    do
      ++v30;
    while ( *(_WORD *)&v29[2 * v30] );
    v31 = RegSetValueExW(phkResult, L"ProtocolId", 0, 1u, v29, 2 * v30 + 2);
    if ( v31 )
    {
      v33 = 222;
LABEL_50:
      v14 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v33,
              (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
              (const char *)v31,
              lpDatab);
      goto LABEL_124;
    }
    v34 = Str;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v32, (unsigned int)L"DllPath", (__int64)Str);
    v35 = -1;
    do
      ++v35;
    while ( v34[v35] );
    cbData = 2 * v35 + 2;
    if ( !v34 || (v37 = wcschr(v34, 0x25u)) == 0 || (v38 = wcschr(v37 + 1, 0x25u), v39 = 2, !v38) )
      v39 = 1;
    v31 = RegSetValueExW(phkResult, L"DllPath", 0, v39, (const BYTE *)v34, cbData);
    if ( v31 )
    {
      v33 = 224;
      goto LABEL_50;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, v40, (unsigned int)L"SecurityContext", Data);
    v31 = RegSetValueExW(phkResult, L"SecurityContext", 0, 4u, (const BYTE *)&Data, 4u);
    if ( v31 )
    {
      v33 = 226;
      goto LABEL_50;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, v41, (unsigned int)L"PropertyRank", v65);
    v31 = RegSetValueExW(phkResult, L"PropertyRank", 0, 4u, (const BYTE *)&v65, 4u);
    if ( v31 )
    {
      v33 = 228;
      goto LABEL_50;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, v42, (unsigned int)L"ImpersonateCaller", v66);
    v31 = RegSetValueExW(phkResult, L"ImpersonateCaller", 0, 4u, (const BYTE *)&v66, 4u);
    if ( v31 )
    {
      v33 = 230;
      goto LABEL_50;
    }
    v44 = a7;
    if ( a7 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          v43,
          (unsigned int)L"FederatedAepStoreLocations",
          (__int64)a7);
      do
        ++v24;
      while ( *(_WORD *)&v44[2 * v24] );
      v31 = RegSetValueExW(phkResult, L"FederatedAepStoreLocations", 1u, 0, v44, 2 * v24 + 2);
      if ( v31 )
      {
        v33 = 235;
        goto LABEL_50;
      }
    }
    else
    {
      v45 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_91;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
LABEL_88:
        if ( v45 != &WPP_GLOBAL_Control && *((_BYTE *)v45 + 25) >= 4u )
          WPP_SF_Sd((unsigned int)v45[2], 25, v43, (unsigned int)L"Capabilities", a5);
LABEL_91:
        v31 = RegSetValueExW(phkResult, L"Capabilities", 0, 4u, &a5, 4u);
        if ( v31 )
        {
          v33 = 243;
          goto LABEL_50;
        }
        if ( !(unsigned int)_o__wcsicmp(a9, L"FileCopy") )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_c259ffd365a33e780ba81409624fcc4e_Traceguids);
          hKey = 0;
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
            &hKey,
            0);
          v46 = RegCreateKeyW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\File Copy Provider", &hKey);
          v14 = v46;
          if ( v46 == 5 )
          {
            pObjectName = 0;
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &pObjectName,
              0);
            v47 = DafConcatenateWithDelimiter_3(
                    L"MACHINE",
                    L"SOFTWARE\\Microsoft\\File Copy Provider",
                    (unsigned __int16 *)&dword_18008C97C);
            v14 = v47;
            if ( v47 < 0 )
            {
              v48 = 254;
LABEL_100:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v48,
                (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
                (const char *)(unsigned int)v47,
                lpDatab);
LABEL_101:
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pObjectName);
LABEL_123:
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
              goto LABEL_124;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                27,
                &WPP_c259ffd365a33e780ba81409624fcc4e_Traceguids,
                pObjectName);
            v47 = DAS::ProviderManagement::ProviderManager::TakeKeyOwnership(pObjectName);
            v14 = v47;
            if ( v47 < 0 )
            {
              v48 = 256;
              goto LABEL_100;
            }
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
              &hKey,
              0);
            v49 = RegCreateKeyW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\File Copy Provider", &hKey);
            if ( v49 )
            {
              v14 = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x101,
                      (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
                      (const char *)v49,
                      lpDatab);
              goto LABEL_101;
            }
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pObjectName);
          }
          else
          {
            if ( v46 > 0 )
              v14 = (unsigned __int16)v46 | 0x80070000;
            if ( (v14 & 0x80000000) != 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x105,
                (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
                (const char *)v14,
                lpDatab);
              goto LABEL_123;
            }
          }
          v50 = RegSetValueExW(hKey, L"copy to path", 0, 1u, L"c:\\to\\", 0xEu);
          if ( v50 )
          {
            v51 = 264;
LABEL_122:
            v14 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)v51,
                    (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
                    (const char *)v50,
                    lpDatac);
            goto LABEL_123;
          }
          v50 = RegSetValueExW(hKey, L"federated store path", 0, 1u, L"c:\\store\\", 0x14u);
          if ( v50 )
          {
            v51 = 265;
            goto LABEL_122;
          }
          v50 = RegSetValueExW(hKey, L"copy from path", 0, 1u, L"c:\\from\\", 0x12u);
          if ( v50 )
          {
            v51 = 266;
            goto LABEL_122;
          }
          v50 = RegSetValueExW(hKey, L"search pattern", 0, 1u, L"*.txt", 0xCu);
          if ( v50 )
          {
            v51 = 267;
            goto LABEL_122;
          }
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v59);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v58);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
        return 0;
      }
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        &WPP_c259ffd365a33e780ba81409624fcc4e_Traceguids,
        L"FederatedAepStoreLocations");
    }
    v45 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_88;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC0,
    (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
    (const char *)(unsigned int)v13,
    lpData);
LABEL_127:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
  return v14;
}

```

## disassembly

```asm
0x180060ec0  mov     [rsp-38h+arg_18], r9d
0x180060ec5  mov     [rsp-38h+arg_10], r8d
0x180060eca  mov     [rsp-38h+Data], edx
0x180060ece  push    rbp
0x180060ecf  push    rbx
0x180060ed0  push    rsi
0x180060ed1  push    rdi
0x180060ed2  push    r12
0x180060ed4  push    r13
0x180060ed6  push    r15
0x180060ed8  mov     rbp, rsp
0x180060edb  sub     rsp, 60h
0x180060edf  movsxd  rbx, ecx
0x180060ee2  cmp     ebx, 1
0x180060ee5  ja      loc_18006187F
0x180060eeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180060ef2  lea     r13, WPP_GLOBAL_Control
0x180060ef9  xor     r15d, r15d
0x180060efc  lea     rdi, ?c_providerRegistrationPaths@ProviderManagement@DAS@@3PAU_PROVIDER_REGISTRATION_PATH@12@A; DAS::ProviderManagement::_PROVIDER_REGISTRATION_PATH near * DAS::ProviderManagement::c_providerRegistrationPaths
0x180060f03  mov     r12d, 4
0x180060f09  cmp     rcx, r13
0x180060f0c  jz      short loc_180060F49
0x180060f0e  cmp     [rcx+19h], r12b
0x180060f12  jb      short loc_180060F49
0x180060f14  mov     r9, [rbp+arg_40]
0x180060f1b  lea     rdx, [rbx+rbx*2]
0x180060f1f  cmp     [rdi+rdx*8+10h], r15b
0x180060f24  lea     r8, a3rdParty; "3rd party"
0x180060f2b  mov     rcx, [rcx+10h]
0x180060f2f  lea     rax, aInbox_0; "inbox"
0x180060f36  cmovz   rax, r8
0x180060f3a  lea     edx, [r12+9]
0x180060f3f  mov     [rsp+60h+lpData], rax; int
0x180060f44  call    WPP_SF_SS
0x180060f49  xor     edx, edx
0x180060f4b  mov     [rbp+lpSubKey], r15
0x180060f4f  lea     rcx, [rbp+lpSubKey]
0x180060f53  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180060f58  mov     rdx, [rbp+arg_40]; unsigned __int16 *
0x180060f5f  lea     rsi, [rbx+rbx*2]
0x180060f63  mov     rcx, [rdi+rsi*8+8]; unsigned __int16 *
0x180060f68  lea     r9, [rbp+lpSubKey]
0x180060f6c  lea     r8, asc_18008CA3C; "\\"
0x180060f73  call    DafConcatenateWithDelimiter_3
0x180060f78  mov     ebx, eax
0x180060f7a  test    eax, eax
0x180060f7c  jns     short loc_180060F9B
0x180060f7e  mov     rcx, [rbp+38h]; this
0x180060f82  lea     r8, aOnecoreBaseDev_4; "onecore\\base\\devices\\association\\li"...
0x180060f89  mov     r9d, eax; char *
0x180060f8c  mov     edx, 0C0h; void *
0x180060f91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060f96  jmp     loc_180061843
0x180060f9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180060fa2  mov     rbx, [rbp+lpSubKey]
0x180060fa6  cmp     rcx, r13
0x180060fa9  jz      short loc_180060FC9
0x180060fab  cmp     [rcx+19h], r12b
0x180060faf  jb      short loc_180060FC9
0x180060fb1  mov     rcx, [rcx+10h]
0x180060fb5  lea     r8, WPP_c259ffd365a33e780ba81409624fcc4e_Traceguids
0x180060fbc  mov     edx, 0Eh
0x180060fc1  mov     r9, rbx
0x180060fc4  call    WPP_SF_S
0x180060fc9  xor     edx, edx
0x180060fcb  mov     [rbp+phkResult], r15
0x180060fcf  lea     rcx, [rbp+phkResult]
0x180060fd3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180060fd8  mov     rcx, [rdi+rsi*8]; hKey
0x180060fdc  lea     r8, [rbp+phkResult]; phkResult
0x180060fe0  mov     rdx, rbx; lpSubKey
0x180060fe3  call    cs:__imp_RegCreateKeyW
0x180060fe9  mov     edi, eax
0x180060feb  cmp     eax, 5
0x180060fee  jnz     loc_180061153
0x180060ff4  xor     edx, edx
0x180060ff6  mov     [rbp+hKey], r15
0x180060ffa  lea     rcx, [rbp+hKey]
0x180060ffe  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180061003  lea     rdx, ?c_providerRegistrationPaths@ProviderManagement@DAS@@3PAU_PROVIDER_REGISTRATION_PATH@12@A; DAS::ProviderManagement::_PROVIDER_REGISTRATION_PATH near * DAS::ProviderManagement::c_providerRegistrationPaths
0x18006100a  mov     rdx, [rdx+rsi*8+8]; unsigned __int16 *
0x18006100f  lea     r9, [rbp+hKey]
0x180061013  lea     r8, asc_18008CA3C; "\\"
0x18006101a  lea     rcx, aMachine; "MACHINE"
0x180061021  call    DafConcatenateWithDelimiter_3
0x180061026  mov     edi, eax
0x180061028  test    eax, eax
0x18006102a  jns     short loc_18006105D
0x18006102c  mov     edx, 0CCh; void *
0x180061031  mov     rcx, [rbp+38h]; this
0x180061035  lea     r8, aOnecoreBaseDev_4; "onecore\\base\\devices\\association\\li"...
0x18006103c  mov     r9d, edi; char *
0x18006103f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061044  lea     rcx, [rbp+hKey]
0x180061048  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006104d  lea     rcx, [rbp+phkResult]
0x180061051  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180061056  mov     ebx, edi
0x180061058  jmp     loc_180061843
0x18006105d  mov     rcx, cs:WPP_GLOBAL_Control
0x180061064  cmp     rcx, r13
0x180061067  jz      short loc_180061088
0x180061069  cmp     [rcx+19h], r12b
0x18006106d  jb      short loc_180061088
0x18006106f  mov     r9, [rbp+hKey]
0x180061073  lea     r8, WPP_c259ffd365a33e780ba81409624fcc4e_Traceguids
0x18006107a  mov     rcx, [rcx+10h]
0x18006107e  mov     edx, 0Fh
0x180061083  call    WPP_SF_S
0x180061088  mov     rcx, [rbp+hKey]; pObjectName
0x18006108c  call    ?TakeKeyOwnership@ProviderManager@ProviderManagement@DAS@@CAJPEAG@Z; DAS::ProviderManagement::ProviderManager::TakeKeyOwnership(ushort *)
0x180061091  mov     edi, eax
0x180061093  test    eax, eax
0x180061095  jns     short loc_18006109E
0x180061097  mov     edx, 0CEh
0x18006109c  jmp     short loc_180061031
0x18006109e  xor     edx, edx
0x1800610a0  lea     rcx, [rbp+phkResult]
0x1800610a4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800610a9  lea     r8, [rbp+phkResult]; phkResult
0x1800610ad  mov     rdx, rbx; lpSubKey
0x1800610b0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800610b7  call    cs:__imp_RegCreateKeyW
0x1800610bd  test    eax, eax
0x1800610bf  jz      short loc_1800610E4
0x1800610c1  mov     rcx, [rbp+38h]; this
0x1800610c5  lea     r8, aOnecoreBaseDev_4; "onecore\\base\\devices\\association\\li"...
0x1800610cc  mov     r9d, eax; char *
0x1800610cf  mov     edx, 0CFh; void *
0x1800610d4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800610d9  mov     ebx, eax
0x1800610db  lea     rcx, [rbp+hKey]
0x1800610df  jmp     loc_180061835
0x1800610e4  lea     rcx, [rbp+hKey]
0x1800610e8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800610ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800610f4  cmp     rcx, r13
0x1800610f7  jz      short loc_180061114
0x1800610f9  cmp     [rcx+19h], r12b
0x1800610fd  jb      short loc_180061114
0x1800610ff  mov     rcx, [rcx+10h]
0x180061103  lea     r8, WPP_c259ffd365a33e780ba81409624fcc4e_Traceguids
0x18006110a  mov     edx, 10h
0x18006110f  call    WPP_SF_
0x180061114  xor     edx, edx
0x180061116  mov     [rbp+var_28], r15
0x18006111a  lea     rcx, [rbp+var_28]
0x18006111e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180061123  mov     rcx, [rbp+arg_38]; struct _GUID *
0x180061127  lea     rdx, [rbp+var_28]; unsigned __int16 **
0x18006112b  call    ?MakeGuidStringStatic@ProviderManager@ProviderManagement@DAS@@SAJPEBU_GUID@@PEAPEAG@Z; DAS::ProviderManagement::ProviderManager::MakeGuidStringStatic(_GUID const *,ushort * *)
0x180061130  mov     ebx, eax
0x180061132  test    eax, eax
0x180061134  jns     short loc_180061181
0x180061136  mov     rcx, [rbp+38h]; this
0x18006113a  lea     r8, aOnecoreBaseDev_4; "onecore\\base\\devices\\association\\li"...
0x180061141  mov     r9d, eax; char *
0x180061144  mov     edx, 0D8h; void *
0x180061149  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006114e  jmp     loc_180061831
0x180061153  test    eax, eax
0x180061155  jle     short loc_180061160
0x180061157  movzx   edi, ax
0x18006115a  or      edi, 80070000h
0x180061160  test    edi, edi
0x180061162  jns     short loc_1800610ED
0x180061164  mov     rcx, [rbp+38h]; this
0x180061168  lea     r8, aOnecoreBaseDev_4; "onecore\\base\\devices\\association\\li"...
0x18006116f  mov     r9d, edi; char *
0x180061172  mov     edx, 0D3h; void *
0x180061177  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006117c  jmp     loc_18006104D
0x180061181  mov     rcx, cs:WPP_GLOBAL_Control
0x180061188  mov     rbx, [rbp+var_28]
0x18006118c  cmp     rcx, r13
0x18006118f  jz      short loc_1800611B1
0x180061191  cmp     [rcx+19h], r12b
0x180061195  jb      short loc_1800611B1
0x180061197  mov     rcx, [rcx+10h]
0x18006119b  lea     r9, ValueName; "CLSID"
0x1800611a2  mov     edx, 11h
0x1800611a7  mov     [rsp+60h+lpData], rbx
0x1800611ac  call    WPP_SF_SS
0x1800611b1  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800611b5  mov     rax, rsi
0x1800611b8  inc     rax
0x1800611bb  cmp     [rbx+rax*2], r15w
0x1800611c0  jnz     short loc_1800611B8
0x1800611c2  mov     rcx, [rbp+phkResult]; hKey
0x1800611c6  lea     eax, ds:2[rax*2]
0x1800611cd  mov     [rsp+60h+cbData], eax; cbData
0x1800611d1  lea     rdx, ValueName; "CLSID"
0x1800611d8  mov     edi, 1
0x1800611dd  mov     [rsp+60h+lpData], rbx; int
0x1800611e2  mov     r9d, edi; dwType
0x1800611e5  xor     r8d, r8d; Reserved
0x1800611e8  call    cs:__imp_RegSetValueExW
0x1800611ee  test    eax, eax
0x1800611f0  jz      short loc_180061211
0x1800611f2  mov     rcx, [rbp+38h]; this
0x1800611f6  lea     r8, aOnecoreBaseDev_4; "onecore\\base\\devices\\association\\li"...
0x1800611fd  mov     r9d, eax; char *
0x180061200  mov     edx, 0DAh; void *
0x180061205  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006120a  mov     ebx, eax
0x18006120c  jmp     loc_180061831
0x180061211  xor     edx, edx
0x180061213  mov     [rbp+var_20], r15
0x180061217  lea     rcx, [rbp+var_20]
0x18006121b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180061220  mov     rcx, [rbp+arg_48]; struct _GUID *
0x180061227  lea     rdx, [rbp+var_20]; unsigned __int16 **
0x18006122b  call    ?MakeGuidStringStatic@ProviderManager@ProviderManagement@DAS@@SAJPEBU_GUID@@PEAPEAG@Z; DAS::ProviderManagement::ProviderManager::MakeGuidStringStatic(_GUID const *,ushort * *)
0x180061230  mov     ebx, eax
0x180061232  test    eax, eax
0x180061234  jns     short loc_180061253
0x180061236  mov     rcx, [rbp+38h]; this
0x18006123a  lea     r8, aOnecoreBaseDev_4; "onecore\\base\\devices\\association\\li"...
0x180061241  mov     r9d, eax; char *
0x180061244  mov     edx, 0DCh; void *
0x180061249  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006124e  jmp     loc_180061828
0x180061253  mov     rcx, cs:WPP_GLOBAL_Control
0x18006125a  mov     rbx, [rbp+var_20]
0x18006125e  cmp     rcx, r13
0x180061261  jz      short loc_180061283
0x180061263  cmp     [rcx+19h], r12b
0x180061267  jb      short loc_180061283
0x180061269  mov     rcx, [rcx+10h]
0x18006126d  lea     r9, aProtocolid; "ProtocolId"
0x180061274  mov     edx, 12h
0x180061279  mov     [rsp+60h+lpData], rbx
0x18006127e  call    WPP_SF_SS
0x180061283  mov     rax, rsi
0x180061286  inc     rax
0x180061289  cmp     [rbx+rax*2], r15w
0x18006128e  jnz     short loc_180061286
0x180061290  mov     rcx, [rbp+phkResult]; hKey
0x180061294  lea     eax, ds:2[rax*2]
0x18006129b  mov     [rsp+60h+cbData], eax; cbData
0x18006129f  lea     rdx, aProtocolid; "ProtocolId"
0x1800612a6  mov     r9d, edi; dwType
0x1800612a9  mov     [rsp+60h+lpData], rbx; unsigned int
0x1800612ae  xor     r8d, r8d; Reserved
0x1800612b1  call    cs:__imp_RegSetValueExW
0x1800612b7  test    eax, eax
0x1800612b9  jz      short loc_1800612DA
0x1800612bb  mov     edx, 0DEh; void *
0x1800612c0  mov     rcx, [rbp+38h]; this
0x1800612c4  lea     r8, aOnecoreBaseDev_4; "onecore\\base\\devices\\association\\li"...
0x1800612cb  mov     r9d, eax; char *
0x1800612ce  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800612d3  mov     ebx, eax
0x1800612d5  jmp     loc_180061828
0x1800612da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800612e1  mov     rbx, [rbp+Str]
0x1800612e5  cmp     rcx, r13
0x1800612e8  jz      short loc_18006130A
0x1800612ea  cmp     [rcx+19h], r12b
0x1800612ee  jb      short loc_18006130A
0x1800612f0  mov     rcx, [rcx+10h]
0x1800612f4  lea     r9, aDllpath; "DllPath"
0x1800612fb  mov     edx, 13h
0x180061300  mov     [rsp+60h+lpData], rbx
0x180061305  call    WPP_SF_SS
0x18006130a  mov     rax, rsi
0x18006130d  inc     rax
0x180061310  cmp     [rbx+rax*2], r15w
0x180061315  jnz     short loc_18006130D
0x180061317  lea     edi, ds:2[rax*2]
0x18006131e  test    rbx, rbx
0x180061321  jz      short loc_180061350
0x180061323  mov     edx, 25h ; '%'; Ch
0x180061328  mov     rcx, rbx; Str
0x18006132b  call    cs:__imp_wcschr
0x180061331  test    rax, rax
0x180061334  jz      short loc_180061350
0x180061336  mov     edx, 25h ; '%'; Ch
0x18006133b  lea     rcx, [rax+2]; Str
0x18006133f  call    cs:__imp_wcschr
0x180061345  mov     r9d, 2
0x18006134b  test    rax, rax
0x18006134e  jnz     short loc_180061356
0x180061350  mov     r9d, 1; dwType
0x180061356  mov     rcx, [rbp+phkResult]; hKey
0x18006135a  lea     rdx, aDllpath; "DllPath"
0x180061361  mov     [rsp+60h+cbData], edi; cbData
0x180061365  xor     r8d, r8d; Reserved
0x180061368  mov     [rsp+60h+lpData], rbx; lpData
0x18006136d  call    cs:__imp_RegSetValueExW
0x180061373  test    eax, eax
0x180061375  jz      short loc_180061381
0x180061377  mov     edx, 0E0h
0x18006137c  jmp     loc_1800612C0
0x180061381  mov     rcx, cs:WPP_GLOBAL_Control
0x180061388  cmp     rcx, r13
0x18006138b  jz      short loc_1800613AF
0x18006138d  cmp     [rcx+19h], r12b
0x180061391  jb      short loc_1800613AF
0x180061393  mov     eax, [rbp+Data]
  ... truncated ...
```
