# EapTlsBegin

- ea: `0x1800239a0`
- end: `0x1800244e4`
- name: `EapTlsBegin`
- size: `2884`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18005c4f0`

## callees

- `0x180004560`
- `0x180005010`
- `0x180007d00`
- `0x1800080a0`
- `0x180008420`
- `0x180010140`
- `0x18001e0c0`
- `0x1800206a0`
- `0x1800239a0`
- `0x180026768`
- `0x180033f40`
- `0x1800356f4`
- `0x180038270`
- `0x18003867c`
- `0x180038e4c`
- `0x180038e64`
- `0x18004ddec`
- `0x1800506d0`
- `0x180067e28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180023ec5`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180023ec5`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180023eb5`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180023eb5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023c54`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023c54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023c6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023c6c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023d72`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023db4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024375`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023d72`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023db4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024375`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024448`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024464`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024477`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002448a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002449d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024448`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024464`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024477`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002448a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002449d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002431d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002431d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023ef1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023ef1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023f2f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023f96`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002402e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800240da`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024156`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024202`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024287`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023f2f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023f96`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002402e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800240da`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024156`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024202`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024287`
- `eapputil!EapUseLegacyTlsStack` at `0x180023cf3`
- `eapputil!EapUseLegacyTlsStack` at `0x180023dfe`
- `eapputil!EapUseLegacyTlsStack` at `0x180023cf3`
- `eapputil!EapUseLegacyTlsStack` at `0x180023dfe`

## string_xrefs

- `0x180023ee3`: `System\CurrentControlSet\Services\Rasman\PPP\EAP\13`
- `0x1800241fb`: `UseSoftTokenWithMachineAuthentication`

## pseudocode

```c
__int64 __fastcall EapTlsBegin(_QWORD *a1, __int64 a2)
{
  char *v2; // rdi
  int v4; // eax
  unsigned int v5; // r13d
  const WCHAR *v6; // rbx
  const WCHAR *v7; // r9
  void *v8; // rcx
  int UserData; // esi
  struct _EAPTLS_CONTROL_BLOCK *v10; // rcx
  __int64 v11; // rdx
  void *v12; // rbx
  char *v13; // rax
  __int128 v14; // xmm0
  BOOL v15; // eax
  int v16; // ecx
  int v17; // eax
  int v18; // ecx
  int v19; // eax
  int v20; // ecx
  int v21; // edx
  int v22; // eax
  int v23; // ecx
  int v24; // eax
  int v25; // ecx
  struct _EAPTLS_CONTROL_BLOCK *v26; // rcx
  int v27; // eax
  int v28; // ecx
  int v29; // eax
  bool v30; // al
  int v31; // eax
  HLOCAL v32; // rax
  unsigned int v33; // edx
  _DWORD *v34; // rax
  bool v35; // al
  unsigned int v36; // r8d
  unsigned __int8 *v37; // rdx
  char v38; // dl
  __int16 v39; // r8
  int v40; // r9d
  __int64 v41; // rcx
  int v42; // eax
  struct _EAPTLS_CONTROL_BLOCK *v43; // rcx
  const char *v44; // rbx
  const char *v45; // r9
  int v46; // r13d
  int v47; // eax
  __int64 v48; // rcx
  const char *v49; // r9
  int v50; // eax
  const char *v51; // r9
  int v52; // eax
  unsigned int v53; // eax
  __int64 VendorSpecific; // rax
  HLOCAL v55; // rax
  unsigned int v56; // edx
  wchar_t phkResult; // [rsp+20h] [rbp-49h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-41h]
  DWORD cbData; // [rsp+30h] [rbp-39h] BYREF
  DWORD Type; // [rsp+34h] [rbp-35h] BYREF
  BYTE Data[4]; // [rsp+38h] [rbp-31h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-29h]
  HKEY hKey; // [rsp+48h] [rbp-21h] BYREF
  int v65; // [rsp+50h] [rbp-19h]
  struct _EAPTLS_CONN_PROPERTIES *v66; // [rsp+58h] [rbp-11h] BYREF
  _QWORD *v67; // [rsp+60h] [rbp-9h]
  int v68; // [rsp+68h] [rbp-1h] BYREF
  GUID v69; // [rsp+6Ch] [rbp+3h]
  int v70; // [rsp+7Ch] [rbp+13h]

  v67 = a1;
  v2 = 0;
  hKey = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  hMem = 0;
  v4 = 17;
  v68 = 17;
  v66 = 0;
  v70 = 1;
  v69 = GUID_NULL;
  if ( !a1 || !a2 )
  {
    UserData = 87;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
    goto LABEL_136;
  }
  v5 = 0x4000;
  if ( (*(_DWORD *)(a2 + 4) & 0x4000) != 0 )
    v4 = 19;
  v68 = v4;
  v6 = &String;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v7 = &String;
    if ( *(_QWORD *)(a2 + 16) )
      v7 = *(const WCHAR **)(a2 + 16);
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v7);
  }
  UserData = SetupMachineChangeNotification((PVOID)(*(_DWORD *)(a2 + 4) & 0x14000));
  if ( UserData )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v11 = 32;
LABEL_12:
      WPP_SF_(*((_QWORD *)v10 + 2), v11, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
    }
LABEL_13:
    v12 = hMem;
    goto LABEL_14;
  }
  UserData = VerifyCallerTrust(v8);
  if ( UserData )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_13;
    v11 = 33;
    goto LABEL_12;
  }
  v13 = (char *)operator new(0x380u, (const struct std::nothrow_t *)std::nothrow);
  v2 = v13;
  if ( !v13 )
  {
    UserData = 14;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, 14);
    v2 = 0;
LABEL_136:
    v12 = hMem;
    goto LABEL_137;
  }
  memset_0(v13, 0, 0x380u);
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      35,
      &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids,
      *(unsigned int *)(a2 + 144));
  *((_DWORD *)v2 + 199) = *(_DWORD *)(a2 + 144);
  *((_QWORD *)v2 + 100) = 0;
  *((_QWORD *)v2 + 102) = 0;
  *((_QWORD *)v2 + 101) = 0;
  *((_DWORD *)v2 + 158) = 0;
  *((_QWORD *)v2 + 80) = 0;
  v14 = *(_OWORD *)(a2 + 128);
  *((_QWORD *)v2 + 95) = 0;
  *(_DWORD *)v2 = 0;
  *(_OWORD *)(v2 + 780) = v14;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, g_szEapTlsState);
  v15 = *(_DWORD *)(a2 + 8) != 0;
  *((_DWORD *)v2 + 1) = v15;
  v16 = v15 | (2 * (*(_DWORD *)(a2 + 4) & 1));
  *((_DWORD *)v2 + 1) = v16;
  v17 = v16 | *(_DWORD *)(a2 + 4) & 4;
  *((_DWORD *)v2 + 1) = v17;
  v18 = v17 | ((*(_DWORD *)(a2 + 4) & 2) << 6);
  *((_DWORD *)v2 + 1) = v18;
  v19 = v18 | (16 * (*(_DWORD *)(a2 + 4) & 0x10));
  *((_DWORD *)v2 + 1) = v19;
  v20 = v19 | (32 * (*(_DWORD *)(a2 + 4) & 0x20));
  *((_DWORD *)v2 + 1) = v20;
  v21 = v20 | (32 * (*(_DWORD *)(a2 + 4) & 0x40));
  *((_DWORD *)v2 + 1) = v21;
  v22 = v21 | (32 * (*(_DWORD *)(a2 + 4) & 0x80));
  *((_DWORD *)v2 + 1) = v22;
  v23 = v22 | *(_DWORD *)(a2 + 4) & 0x4000;
  *((_DWORD *)v2 + 1) = v23;
  v24 = v23 | ((*(_DWORD *)(a2 + 4) & 0x100) << 8);
  *((_DWORD *)v2 + 1) = v24;
  v25 = v24 | *(_DWORD *)(a2 + 4) & 0x20000;
  *((_DWORD *)v2 + 1) = v25;
  *((_DWORD *)v2 + 1) = v25 | (*(_DWORD *)(a2 + 4) >> 3) & 0x40000;
  if ( (*(_DWORD *)(a2 + 4) & 0x200) != 0 )
  {
    EnterCriticalSection(&g_csProtectCachedCredentials);
    ClearCachedCredList();
    LeaveCriticalSection(&g_csProtectCachedCredentials);
  }
  if ( *(char *)(a2 + 4) < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_30;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
  }
  v26 = WPP_GLOBAL_Control;
LABEL_30:
  v27 = *((_DWORD *)v2 + 1);
  if ( (v27 & 0x14000) != 0 )
  {
    if ( v26 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      WPP_SF_(*((_QWORD *)v26 + 2), 38, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
      v27 = *((_DWORD *)v2 + 1);
    }
    v28 = 1;
  }
  else
  {
    v28 = 0;
  }
  v29 = v27 | 0x60;
  *((_DWORD *)v2 + 192) = v28;
  *((_DWORD *)v2 + 1) = v29;
  if ( (v29 & 1) != 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EapServerTls13>::GetImpl'::`2'::impl) )
      v30 = (unsigned int)EapUseLegacyTlsStack() != 0;
    else
      v30 = 1;
    v2[849] = v30;
    *((_QWORD *)v2 + 92) = *(_QWORD *)(a2 + 120);
    v31 = *((_DWORD *)v2 + 1) & 0x4000;
    *((_DWORD *)v2 + 166) = 98590;
    if ( ((*((_DWORD *)v2 + 1) & 0x800) != 0 || v31) && v31 )
    {
      UserData = EapTlsReadUserData(
                   *(unsigned __int8 **)(a2 + 104),
                   *(_DWORD *)(a2 + 112),
                   (struct _EAPTLS_USER_PROPERTIES **)v2 + 71);
      if ( UserData )
        goto LABEL_13;
      goto LABEL_53;
    }
    if ( *(_QWORD *)(a2 + 88) && *(_DWORD *)(a2 + 96) )
    {
      v32 = LocalAlloc(0x40u, *(unsigned int *)(a2 + 96));
      *((_QWORD *)v2 + 71) = v32;
      if ( !v32 )
      {
LABEL_47:
        UserData = -2147024882;
        goto LABEL_48;
      }
      memcpy_0(v32, *(const void **)(a2 + 88), *(unsigned int *)(a2 + 96));
    }
    else
    {
      v34 = LocalAlloc(0x40u, 0x48u);
      *((_QWORD *)v2 + 71) = v34;
      if ( !v34 )
        goto LABEL_47;
      v34[1] = 0;
      *(_DWORD *)(*((_QWORD *)v2 + 71) + 8LL) = 72;
      *(_WORD *)(*((_QWORD *)v2 + 71) + 70LL) = 0;
    }
LABEL_53:
    v2[721] = *(_BYTE *)(a2 + 32);
    v65 = 1;
    goto LABEL_55;
  }
  v65 = 0;
  v35 = (unsigned int)EapUseLegacyTlsStack() != 0;
  v2[849] = v35;
  v2[888] = !v35;
  *((_DWORD *)v2 + 166) = 49564;
  *((_QWORD *)v2 + 1) = *(_QWORD *)(a2 + 56);
  UserData = EapTlsReadUserData(
               *(unsigned __int8 **)(a2 + 104),
               *(_DWORD *)(a2 + 112),
               (struct _EAPTLS_USER_PROPERTIES **)v2 + 71);
  if ( UserData )
    goto LABEL_13;
LABEL_55:
  if ( (v2[4] & 1) != 0 )
  {
    v37 = 0;
    v36 = 0;
  }
  else
  {
    v36 = *(_DWORD *)(a2 + 96);
    v37 = *(unsigned __int8 **)(a2 + 88);
  }
  UserData = EapTlsReadConnectionData(*(_DWORD *)(a2 + 4), v37, v36, &v66);
  if ( UserData )
  {
    v12 = v66;
LABEL_14:
    if ( UserData <= 0 )
      goto LABEL_49;
LABEL_137:
    v33 = (unsigned __int16)UserData | 0x80070000;
    goto LABEL_138;
  }
  hMem = v66;
  UserData = ConnPropGetV1Struct(v66, (struct _EAPTLS_CONN_PROPERTIES_V1 **)v2 + 68);
  if ( UserData )
    goto LABEL_13;
  if ( *(_QWORD *)(a2 + 16) )
    v6 = *(const WCHAR **)(a2 + 16);
  _o_wcsncpy_s(v2 + 16, 257, v6, 256);
  o((_WORD)v2 + 16, v38, v39, v40, phkResult, *(long double *)&lpcbData);
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\Rasman\\PPP\\EAP\\13",
          0,
          0x20019u,
          &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"MaxTLSMessageLength", 0, &Type, Data, &cbData) && Type == 4 )
      v5 = *(_DWORD *)Data;
    g_dwMaxBlobSize = v5;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v5);
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"IgnoreNoRevocationCheck", 0, &Type, Data, &cbData) || Type != 4 )
    {
      g_fIgnoreNoRevocationCheck = 0;
      v42 = 0;
    }
    else
    {
      v42 = *(_DWORD *)Data;
      g_fIgnoreNoRevocationCheck = *(_DWORD *)Data;
    }
    v43 = WPP_GLOBAL_Control;
    v44 = "not ";
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v45 = (const char *)&dword_180087A9C;
      if ( !v42 )
        v45 = "not ";
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v45);
      v43 = WPP_GLOBAL_Control;
    }
    v46 = v65;
    if ( v65 )
    {
      cbData = 4;
      if ( RegQueryValueExW(hKey, L"IgnoreRevocationOffline", 0, &Type, Data, &cbData) || Type != 4 )
      {
        g_fIgnoreRevocationOffline = 0;
        v47 = 0;
      }
      else
      {
        v47 = *(_DWORD *)Data;
        g_fIgnoreRevocationOffline = *(_DWORD *)Data;
      }
      v43 = WPP_GLOBAL_Control;
    }
    else
    {
      if ( v43 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        WPP_SF_(*((_QWORD *)v43 + 2), 41, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
        v43 = WPP_GLOBAL_Control;
      }
      v47 = 1;
      g_fIgnoreRevocationOffline = 1;
    }
    if ( v43 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v48 = *((_QWORD *)v43 + 2);
      v49 = (const char *)&dword_180087A9C;
      if ( !v47 )
        v49 = "not ";
      WPP_SF_s(v48, 42, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v49);
    }
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"NoRootRevocationCheck", 0, &Type, Data, &cbData) || (v50 = *(_DWORD *)Data, Type != 4) )
      v50 = 1;
    g_fNoRootRevocationCheck = v50;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v51 = "not ";
      if ( !v50 )
        v51 = (const char *)&dword_180087A9C;
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v51);
    }
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"NoRevocationCheck", 0, &Type, Data, &cbData) || Type != 4 )
    {
      g_fNoRevocationCheck = 0;
      v52 = 0;
    }
    else
    {
      v52 = *(_DWORD *)Data;
      g_fNoRevocationCheck = *(_DWORD *)Data;
    }
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      if ( !v52 )
        v44 = (const char *)&dword_180087A9C;
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v44);
    }
    if ( !v46 && (*((_DWORD *)v2 + 1) & 0x400) != 0 && (*(_BYTE *)(*((_QWORD *)v2 + 68) + 8LL) & 1) == 0 )
    {
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"UseSoftTokenWithMachineAuthentication", 0, &Type, Data, &cbData)
        && Type == 4
        && *(_DWORD *)Data == 1 )
      {
        *(_DWORD *)(*((_QWORD *)v2 + 68) + 8LL) |= 0x100u;
        *(_DWORD *)(*((_QWORD *)v2 + 68) + 8LL) |= 1u;
        *(_DWORD *)(*((_QWORD *)v2 + 68) + 8LL) |= 0x10u;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
      }
    }
    cbData = 4;
    v53 = RegQueryValueExW(hKey, L"TlsVersion", 0, &Type, Data, &cbData);
    if ( v53 || Type != 4 )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v53);
    }
    else if ( (*(_DWORD *)Data | 0x3FC0) == 0x3FC0 && (*(_WORD *)Data & 0x3FC0) != 0 )
    {
      g_tlsVersionsToUse = *(_DWORD *)Data;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          46,
          &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids,
          *(unsigned int *)Data);
    }
    else if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
    }
    RegCloseKey(hKey);
  }
  if ( *(_QWORD *)(a2 + 40) )
  {
    VendorSpecific = RasAuthAttributeGetVendorSpecific(v41, 70);
    if ( VendorSpecific )
    {
      if ( *(_DWORD *)(VendorSpecific + 4) == 13 && !*(_DWORD *)(*(_QWORD *)(VendorSpecific + 8) + 9LL) )
      {
        *((_DWORD *)v2 + 158) = 16;
        v55 = LocalAlloc(0x40u, 0x300u);
        *((_QWORD *)v2 + 80) = v55;
        if ( v55 )
        {
          memcpy_0(v55, &g_wpa3SuiteBDisabledCrypto, 48LL * *((unsigned int *)v2 + 158));
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
          goto LABEL_48;
        }
        goto LABEL_47;
      }
    }
  }
LABEL_48:
  v12 = hMem;
LABEL_49:
  v33 = UserData;
LABEL_138:
  NetworkingTriageScenario::GetConnected::EAPTlsBeginAction(
    (const struct NetworkingTriageScenario::GetConnected::RequiredFields *)&v68,
    v33);
  LocalFree(v12);
  if ( UserData && v2 )
  {
    LocalFree(*((HLOCAL *)v2 + 71));
    LocalFree(*((HLOCAL *)v2 + 68));
    LocalFree(*((HLOCAL *)v2 + 72));
    LocalFree(*((HLOCAL *)v2 + 80));
    _EAPTLS_CONTROL_BLOCK::`scalar deleting destructor'((_EAPTLS_CONTROL_BLOCK *)v2, v56);
    v2 = 0;
  }
  *v67 = v2;
  return (unsigned int)UserData;
}

```

## disassembly

```asm
0x1800239a0  mov     [rsp-8+arg_10], rbx
0x1800239a5  push    rbp
0x1800239a6  push    rsi
0x1800239a7  push    rdi
0x1800239a8  push    r12
0x1800239aa  push    r13
0x1800239ac  push    r14
0x1800239ae  push    r15
0x1800239b0  lea     rbp, [rsp-27h]
0x1800239b5  sub     rsp, 90h
0x1800239bc  mov     rax, cs:__security_cookie
0x1800239c3  xor     rax, rsp
0x1800239c6  mov     [rbp+57h+var_40], rax
0x1800239ca  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800239d1  xor     r8d, r8d
0x1800239d4  mov     [rbp+57h+var_60], rcx
0x1800239d8  xor     edi, edi
0x1800239da  mov     [rbp+57h+hKey], 0
0x1800239e2  mov     [rbp+57h+Type], 0
0x1800239e9  mov     r14, rdx
0x1800239ec  mov     dword ptr [rbp+57h+Data], 0
0x1800239f3  mov     [rbp+57h+cbData], 0
0x1800239fa  mov     [rbp+57h+hMem], r8
0x1800239fe  lea     eax, [rdi+11h]
0x180023a01  mov     [rbp+57h+var_58], eax
0x180023a04  mov     [rbp+57h+var_68], r8
0x180023a08  mov     [rbp+57h+var_44], 1
0x180023a0f  movdqu  [rbp+57h+var_54], xmm0
0x180023a14  test    rcx, rcx
0x180023a17  jz      loc_180024404
0x180023a1d  test    rdx, rdx
0x180023a20  jz      loc_180024404
0x180023a26  mov     r13d, 4000h
0x180023a2c  lea     ecx, [rdi+13h]
0x180023a2f  test    [rdx+4], r13d
0x180023a33  cmovnz  eax, ecx
0x180023a36  mov     [rbp+57h+var_58], eax
0x180023a39  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a40  lea     r15, WPP_GLOBAL_Control
0x180023a47  lea     rbx, String
0x180023a4e  lea     r12, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180023a55  cmp     rcx, r15
0x180023a58  jz      short loc_180023A75
0x180023a5a  cmp     [rdx+10h], rdi
0x180023a5e  mov     r9, rbx
0x180023a61  mov     rcx, [rcx+10h]
0x180023a65  mov     r8, r12
0x180023a68  cmovnz  r9, [rdx+10h]
0x180023a6d  lea     edx, [rdi+1Fh]
0x180023a70  call    WPP_SF_S
0x180023a75  mov     ecx, [r14+4]
0x180023a79  and     ecx, 14000h; Context
0x180023a7f  call    ?SetupMachineChangeNotification@@YAKK@Z; SetupMachineChangeNotification(ulong)
0x180023a84  mov     esi, eax
0x180023a86  test    eax, eax
0x180023a88  jz      short loc_180023AB8
0x180023a8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a91  cmp     rcx, r15
0x180023a94  jz      short loc_180023AA7
0x180023a96  mov     edx, 20h ; ' '
0x180023a9b  mov     rcx, [rcx+10h]
0x180023a9f  mov     r8, r12
0x180023aa2  call    WPP_SF_
0x180023aa7  mov     rbx, [rbp+57h+hMem]
0x180023aab  test    esi, esi
0x180023aad  jg      loc_180024433
0x180023ab3  jmp     loc_180023D93
0x180023ab8  call    ?VerifyCallerTrust@@YAKPEAX@Z; VerifyCallerTrust(void *)
0x180023abd  mov     esi, eax
0x180023abf  test    eax, eax
0x180023ac1  jz      short loc_180023AD6
0x180023ac3  mov     rcx, cs:WPP_GLOBAL_Control
0x180023aca  cmp     rcx, r15
0x180023acd  jz      short loc_180023AA7
0x180023acf  mov     edx, 21h ; '!'
0x180023ad4  jmp     short loc_180023A9B
0x180023ad6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180023add  mov     ecx, 380h; unsigned __int64
0x180023ae2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180023ae7  xor     esi, esi
0x180023ae9  mov     rdi, rax
0x180023aec  test    rax, rax
0x180023aef  jz      loc_1800243DD
0x180023af5  xor     edx, edx; Val
0x180023af7  mov     r8d, 380h; Size
0x180023afd  mov     rcx, rax; void *
0x180023b00  call    memset_0
0x180023b05  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b0c  cmp     rcx, r15
0x180023b0f  jz      short loc_180023B27
0x180023b11  mov     r9d, [r14+90h]
0x180023b18  lea     edx, [rsi+23h]
0x180023b1b  mov     rcx, [rcx+10h]
0x180023b1f  mov     r8, r12
0x180023b22  call    WPP_SF_d
0x180023b27  mov     eax, [r14+90h]
0x180023b2e  mov     [rdi+31Ch], eax
0x180023b34  mov     [rdi+320h], rsi
0x180023b3b  mov     [rdi+330h], rsi
0x180023b42  mov     [rdi+328h], rsi
0x180023b49  mov     [rdi+278h], esi
0x180023b4f  mov     [rdi+280h], rsi
0x180023b56  movups  xmm0, xmmword ptr [r14+80h]
0x180023b5e  mov     [rdi+2F8h], rsi
0x180023b65  mov     [rdi], esi
0x180023b67  movdqu  xmmword ptr [rdi+30Ch], xmm0
0x180023b6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b76  cmp     rcx, r15
0x180023b79  jz      short loc_180023B93
0x180023b7b  mov     r9, cs:?g_szEapTlsState@@3PAPEADA; char * near * g_szEapTlsState
0x180023b82  mov     edx, 24h ; '$'
0x180023b87  mov     rcx, [rcx+10h]
0x180023b8b  mov     r8, r12
0x180023b8e  call    WPP_SF_s
0x180023b93  cmp     [r14+8], esi
0x180023b97  mov     eax, esi
0x180023b99  setnz   al
0x180023b9c  mov     [rdi+4], eax
0x180023b9f  mov     ecx, [r14+4]
0x180023ba3  and     ecx, 1
0x180023ba6  add     ecx, ecx
0x180023ba8  or      ecx, eax
0x180023baa  mov     [rdi+4], ecx
0x180023bad  mov     eax, [r14+4]
0x180023bb1  and     eax, 4
0x180023bb4  or      eax, ecx
0x180023bb6  mov     [rdi+4], eax
0x180023bb9  mov     ecx, [r14+4]
0x180023bbd  and     ecx, 2
0x180023bc0  shl     ecx, 6
0x180023bc3  or      ecx, eax
0x180023bc5  mov     [rdi+4], ecx
0x180023bc8  mov     eax, [r14+4]
0x180023bcc  and     eax, 10h
0x180023bcf  shl     eax, 4
0x180023bd2  or      eax, ecx
0x180023bd4  mov     [rdi+4], eax
0x180023bd7  mov     ecx, [r14+4]
0x180023bdb  and     ecx, 20h
0x180023bde  shl     ecx, 5
0x180023be1  or      ecx, eax
0x180023be3  mov     [rdi+4], ecx
0x180023be6  mov     edx, [r14+4]
0x180023bea  and     edx, 40h
0x180023bed  shl     edx, 5
0x180023bf0  or      edx, ecx
0x180023bf2  mov     [rdi+4], edx
0x180023bf5  mov     eax, [r14+4]
0x180023bf9  and     eax, 80h
0x180023bfe  shl     eax, 5
0x180023c01  or      eax, edx
0x180023c03  mov     [rdi+4], eax
0x180023c06  mov     ecx, [r14+4]
0x180023c0a  and     ecx, r13d
0x180023c0d  or      ecx, eax
0x180023c0f  mov     [rdi+4], ecx
0x180023c12  mov     eax, [r14+4]
0x180023c16  and     eax, 100h
0x180023c1b  shl     eax, 8
0x180023c1e  or      eax, ecx
0x180023c20  mov     [rdi+4], eax
0x180023c23  mov     ecx, [r14+4]
0x180023c27  and     ecx, 20000h
0x180023c2d  or      ecx, eax
0x180023c2f  mov     [rdi+4], ecx
0x180023c32  mov     eax, [r14+4]
0x180023c36  shr     eax, 3
0x180023c39  and     eax, 40000h
0x180023c3e  or      eax, ecx
0x180023c40  mov     [rdi+4], eax
0x180023c43  test    dword ptr [r14+4], 200h
0x180023c4b  jz      short loc_180023C78
0x180023c4d  lea     rcx, ?g_csProtectCachedCredentials@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180023c54  call    cs:__imp_EnterCriticalSection
0x180023c5b  nop     dword ptr [rax+rax+00h]
0x180023c60  call    ?ClearCachedCredList@@YAXXZ; ClearCachedCredList(void)
0x180023c65  lea     rcx, ?g_csProtectCachedCredentials@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180023c6c  call    cs:__imp_LeaveCriticalSection
0x180023c73  nop     dword ptr [rax+rax+00h]
0x180023c78  test    byte ptr [r14+4], 80h
0x180023c7d  jz      short loc_180023C9C
0x180023c7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180023c86  cmp     rcx, r15
0x180023c89  jz      short loc_180023CA3
0x180023c8b  mov     rcx, [rcx+10h]
0x180023c8f  mov     edx, 25h ; '%'
0x180023c94  mov     r8, r12
0x180023c97  call    WPP_SF_
0x180023c9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ca3  mov     eax, [rdi+4]
0x180023ca6  test    eax, 14000h
0x180023cab  jnz     short loc_180023CB1
0x180023cad  mov     ecx, esi
0x180023caf  jmp     short loc_180023CCF
0x180023cb1  cmp     rcx, r15
0x180023cb4  jz      short loc_180023CCA
0x180023cb6  mov     rcx, [rcx+10h]
0x180023cba  mov     edx, 26h ; '&'
0x180023cbf  mov     r8, r12
0x180023cc2  call    WPP_SF_
0x180023cc7  mov     eax, [rdi+4]
0x180023cca  mov     ecx, 1
0x180023ccf  or      eax, 60h
0x180023cd2  mov     [rdi+300h], ecx
0x180023cd8  mov     [rdi+4], eax
0x180023cdb  test    al, 1
0x180023cdd  jz      loc_180023DFB
0x180023ce3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EapServerTls13@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13> `wil::Feature<__WilFeatureTraits_Feature_EapServerTls13>::GetImpl(void)'::`2'::impl
0x180023cea  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::__private_IsEnabled(void)
0x180023cef  test    al, al
0x180023cf1  jz      short loc_180023D06
0x180023cf3  call    cs:__imp_EapUseLegacyTlsStack
0x180023cfa  nop     dword ptr [rax+rax+00h]
0x180023cff  test    eax, eax
0x180023d01  setnz   al
0x180023d04  jmp     short loc_180023D08
0x180023d06  mov     al, 1
0x180023d08  mov     [rdi+351h], al
0x180023d0e  mov     rax, [r14+78h]
0x180023d12  mov     [rdi+2E0h], rax
0x180023d19  mov     eax, [rdi+4]
0x180023d1c  and     eax, r13d
0x180023d1f  mov     dword ptr [rdi+298h], 1811Eh
0x180023d29  test    dword ptr [rdi+4], 800h
0x180023d30  jnz     short loc_180023D36
0x180023d32  test    eax, eax
0x180023d34  jz      short loc_180023D5D
0x180023d36  test    eax, eax
0x180023d38  jz      short loc_180023D5D
0x180023d3a  mov     edx, [r14+70h]; unsigned int
0x180023d3e  lea     r8, [rdi+238h]; struct _EAPTLS_USER_PROPERTIES **
0x180023d45  mov     rcx, [r14+68h]; Src
0x180023d49  call    ?EapTlsReadUserData@@YAKPEAEKPEAPEAU_EAPTLS_USER_PROPERTIES@@@Z; EapTlsReadUserData(uchar *,ulong,_EAPTLS_USER_PROPERTIES * *)
0x180023d4e  mov     esi, eax
0x180023d50  test    eax, eax
0x180023d52  jnz     loc_180023AA7
0x180023d58  jmp     loc_180023DE8
0x180023d5d  cmp     [r14+58h], rsi
0x180023d61  jz      short loc_180023DAC
0x180023d63  cmp     [r14+60h], esi
0x180023d67  jz      short loc_180023DAC
0x180023d69  mov     edx, [r14+60h]; uBytes
0x180023d6d  mov     ecx, 40h ; '@'; uFlags
0x180023d72  call    cs:__imp_LocalAlloc
0x180023d79  nop     dword ptr [rax+rax+00h]
0x180023d7e  mov     [rdi+238h], rax
0x180023d85  test    rax, rax
0x180023d88  jnz     short loc_180023D9A
0x180023d8a  mov     esi, 8007000Eh
0x180023d8f  mov     rbx, [rbp+57h+hMem]
0x180023d93  mov     edx, esi
0x180023d95  jmp     loc_18002443C
0x180023d9a  mov     r8d, [r14+60h]; Size
0x180023d9e  mov     rcx, rax; void *
0x180023da1  mov     rdx, [r14+58h]; Src
0x180023da5  call    memcpy_0
0x180023daa  jmp     short loc_180023DE8
0x180023dac  mov     edx, 48h ; 'H'; uBytes
0x180023db1  lea     ecx, [rdx-8]; uFlags
0x180023db4  call    cs:__imp_LocalAlloc
0x180023dbb  nop     dword ptr [rax+rax+00h]
0x180023dc0  mov     [rdi+238h], rax
0x180023dc7  test    rax, rax
0x180023dca  jz      short loc_180023D8A
0x180023dcc  mov     [rax+4], esi
0x180023dcf  mov     rax, [rdi+238h]
0x180023dd6  mov     dword ptr [rax+8], 48h ; 'H'
0x180023ddd  mov     rcx, [rdi+238h]
0x180023de4  mov     [rcx+46h], si
0x180023de8  mov     al, [r14+20h]
0x180023dec  mov     [rdi+2D1h], al
0x180023df2  mov     [rbp+57h+var_70], 1
0x180023df9  jmp     short loc_180023E4D
0x180023dfb  mov     [rbp+57h+var_70], esi
0x180023dfe  call    cs:__imp_EapUseLegacyTlsStack
0x180023e05  nop     dword ptr [rax+rax+00h]
0x180023e0a  test    eax, eax
0x180023e0c  lea     r8, [rdi+238h]; struct _EAPTLS_USER_PROPERTIES **
0x180023e13  setnz   al
0x180023e16  mov     [rdi+351h], al
0x180023e1c  xor     al, 1
0x180023e1e  mov     [rdi+378h], al
0x180023e24  mov     dword ptr [rdi+298h], 0C19Ch
0x180023e2e  mov     rax, [r14+38h]
0x180023e32  mov     [rdi+8], rax
0x180023e36  mov     edx, [r14+70h]; unsigned int
0x180023e3a  mov     rcx, [r14+68h]; Src
0x180023e3e  call    ?EapTlsReadUserData@@YAKPEAEKPEAPEAU_EAPTLS_USER_PROPERTIES@@@Z; EapTlsReadUserData(uchar *,ulong,_EAPTLS_USER_PROPERTIES * *)
0x180023e43  mov     esi, eax
0x180023e45  test    eax, eax
0x180023e47  jnz     loc_180023AA7
0x180023e4d  test    byte ptr [rdi+4], 1
0x180023e51  jnz     short loc_180023E5D
0x180023e53  mov     r8d, [r14+60h]
0x180023e57  mov     rdx, [r14+58h]
0x180023e5b  jmp     short loc_180023E62
0x180023e5d  xor     edx, edx; unsigned __int8 *
0x180023e5f  xor     r8d, r8d; unsigned int
0x180023e62  mov     ecx, [r14+4]; unsigned int
0x180023e66  lea     r9, [rbp+57h+var_68]; struct _EAPTLS_CONN_PROPERTIES **
  ... truncated ...
```
