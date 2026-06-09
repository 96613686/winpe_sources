# EapTlsBegin

- ea: `0x180023b60`
- end: `0x180024634`
- name: `EapTlsBegin`
- size: `2772`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180059200`

## callees

- `0x1800041c0`
- `0x180004bd0`
- `0x1800075b0`
- `0x180007910`
- `0x180007c60`
- `0x18000f350`
- `0x18001c680`
- `0x18001e960`
- `0x180023b60`
- `0x1800246f4`
- `0x1800316cc`
- `0x180032acc`
- `0x180035680`
- `0x180035a8c`
- `0x18003623c`
- `0x180036254`
- `0x18004b4ec`
- `0x18004dbc8`
- `0x180064384`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18002407a`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18002407a`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180024070`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180024070`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023e33`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023e33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023e45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023e45`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023f3f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023f7b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800244ea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023f3f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023f7b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800244ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800245b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800245cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800245da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800245e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800245f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800245b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800245cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800245da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800245e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800245f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024498`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024498`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800240a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800240a0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800240d8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024139`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800241cb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024271`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800242e7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024389`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024408`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800240d8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024139`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800241cb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024271`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800242e7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024389`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024408`
- `eapputil!EapUseLegacyTlsStack` at `0x180023ec6`
- `eapputil!EapUseLegacyTlsStack` at `0x180023fbf`
- `eapputil!EapUseLegacyTlsStack` at `0x180023ec6`
- `eapputil!EapUseLegacyTlsStack` at `0x180023fbf`

## string_xrefs

- `0x180024092`: `System\CurrentControlSet\Services\Rasman\PPP\EAP\13`
- `0x180024382`: `UseSoftTokenWithMachineAuthentication`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
  int v42; // ebx
  int v43; // eax
  struct _EAPTLS_CONTROL_BLOCK *v44; // rcx
  const char *v45; // rbx
  const char *v46; // r9
  int v47; // r13d
  int v48; // eax
  __int64 v49; // rcx
  const char *v50; // r9
  int v51; // eax
  const char *v52; // r9
  int v53; // eax
  unsigned int v54; // eax
  __int64 VendorSpecific; // rax
  HLOCAL v56; // rax
  unsigned int v57; // edx
  wchar_t phkResult; // [rsp+20h] [rbp-49h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-41h]
  DWORD cbData; // [rsp+30h] [rbp-39h] BYREF
  DWORD Type; // [rsp+34h] [rbp-35h] BYREF
  BYTE Data[4]; // [rsp+38h] [rbp-31h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-29h]
  HKEY hKey; // [rsp+48h] [rbp-21h] BYREF
  int v66; // [rsp+50h] [rbp-19h]
  struct _EAPTLS_CONN_PROPERTIES *v67; // [rsp+58h] [rbp-11h] BYREF
  _QWORD *v68; // [rsp+60h] [rbp-9h]
  int v69; // [rsp+68h] [rbp-1h] BYREF
  GUID v70; // [rsp+6Ch] [rbp+3h]
  int v71; // [rsp+7Ch] [rbp+13h]

  v68 = a1;
  v2 = 0;
  hKey = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  hMem = 0;
  v4 = 17;
  v69 = 17;
  v67 = 0;
  v71 = 1;
  v70 = GUID_NULL;
  if ( !a1 || !a2 )
  {
    UserData = 87;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
    goto LABEL_138;
  }
  v5 = 0x4000;
  if ( (*(_DWORD *)(a2 + 4) & 0x4000) != 0 )
    v4 = 19;
  v69 = v4;
  v6 = &String;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v7 = &String;
    if ( *(_QWORD *)(a2 + 16) )
      v7 = *(const WCHAR **)(a2 + 16);
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v7);
  }
  UserData = SetupMachineChangeNotification((PVOID)(*(_DWORD *)(a2 + 4) & 0x14000));
  if ( UserData )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v11 = 32;
LABEL_12:
      WPP_SF_(*((_QWORD *)v10 + 2), v11, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, 14);
    v2 = 0;
LABEL_138:
    v12 = hMem;
    goto LABEL_139;
  }
  memset_0(v13, 0, 0x380u);
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      35,
      &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
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
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, g_szEapTlsState);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EapServerTls13>::GetImpl'::`2'::impl) )
    *((_DWORD *)v2 + 1) |= (*(_DWORD *)(a2 + 4) >> 2) & 0x1000000;
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
      goto LABEL_32;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
  }
  v26 = WPP_GLOBAL_Control;
LABEL_32:
  v27 = *((_DWORD *)v2 + 1);
  if ( (v27 & 0x14000) != 0 )
  {
    if ( v26 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      WPP_SF_(*((_QWORD *)v26 + 2), 38, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
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
      goto LABEL_55;
    }
    if ( *(_QWORD *)(a2 + 88) && *(_DWORD *)(a2 + 96) )
    {
      v32 = LocalAlloc(0x40u, *(unsigned int *)(a2 + 96));
      *((_QWORD *)v2 + 71) = v32;
      if ( !v32 )
      {
LABEL_49:
        UserData = -2147024882;
        goto LABEL_50;
      }
      memcpy_0(v32, *(const void **)(a2 + 88), *(unsigned int *)(a2 + 96));
    }
    else
    {
      v34 = LocalAlloc(0x40u, 0x48u);
      *((_QWORD *)v2 + 71) = v34;
      if ( !v34 )
        goto LABEL_49;
      v34[1] = 0;
      *(_DWORD *)(*((_QWORD *)v2 + 71) + 8LL) = 72;
      *(_WORD *)(*((_QWORD *)v2 + 71) + 70LL) = 0;
    }
LABEL_55:
    v2[721] = *(_BYTE *)(a2 + 32);
    v66 = 1;
    goto LABEL_57;
  }
  v66 = 0;
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
LABEL_57:
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
  UserData = EapTlsReadConnectionData(*(_DWORD *)(a2 + 4), v37, v36, &v67);
  if ( UserData )
  {
    v12 = v67;
LABEL_14:
    if ( UserData <= 0 )
      goto LABEL_51;
LABEL_139:
    v33 = (unsigned __int16)UserData | 0x80070000;
    goto LABEL_140;
  }
  hMem = v67;
  UserData = ConnPropGetV1Struct(v67, (struct _EAPTLS_CONN_PROPERTIES_V1 **)v2 + 68);
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
    v42 = UserData + 4;
    cbData = UserData + 4;
    if ( !RegQueryValueExW(hKey, L"MaxTLSMessageLength", 0, &Type, Data, &cbData) && Type == v42 )
      v5 = *(_DWORD *)Data;
    g_dwMaxBlobSize = v5;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v5);
    cbData = UserData + 4;
    if ( RegQueryValueExW(hKey, L"IgnoreNoRevocationCheck", 0, &Type, Data, &cbData) || Type != v42 )
    {
      g_fIgnoreNoRevocationCheck = 0;
      v43 = 0;
    }
    else
    {
      v43 = *(_DWORD *)Data;
      g_fIgnoreNoRevocationCheck = *(_DWORD *)Data;
    }
    v44 = WPP_GLOBAL_Control;
    v45 = "not ";
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v46 = (const char *)&dword_180081A9C;
      if ( !v43 )
        v46 = "not ";
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v46);
      v44 = WPP_GLOBAL_Control;
    }
    v47 = v66;
    if ( v66 )
    {
      cbData = 4;
      if ( RegQueryValueExW(hKey, L"IgnoreRevocationOffline", 0, &Type, Data, &cbData) || Type != 4 )
      {
        g_fIgnoreRevocationOffline = 0;
        v48 = 0;
      }
      else
      {
        v48 = *(_DWORD *)Data;
        g_fIgnoreRevocationOffline = *(_DWORD *)Data;
      }
      v44 = WPP_GLOBAL_Control;
    }
    else
    {
      if ( v44 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        WPP_SF_(*((_QWORD *)v44 + 2), 41, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
        v44 = WPP_GLOBAL_Control;
      }
      v48 = 1;
      g_fIgnoreRevocationOffline = 1;
    }
    if ( v44 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v49 = *((_QWORD *)v44 + 2);
      v50 = (const char *)&dword_180081A9C;
      if ( !v48 )
        v50 = "not ";
      WPP_SF_s(v49, 42, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v50);
    }
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"NoRootRevocationCheck", 0, &Type, Data, &cbData) || (v51 = *(_DWORD *)Data, Type != 4) )
      v51 = 1;
    g_fNoRootRevocationCheck = v51;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v52 = "not ";
      if ( !v51 )
        v52 = (const char *)&dword_180081A9C;
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v52);
    }
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"NoRevocationCheck", 0, &Type, Data, &cbData) || Type != 4 )
    {
      g_fNoRevocationCheck = 0;
      v53 = 0;
    }
    else
    {
      v53 = *(_DWORD *)Data;
      g_fNoRevocationCheck = *(_DWORD *)Data;
    }
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      if ( !v53 )
        v45 = (const char *)&dword_180081A9C;
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v45);
    }
    if ( !v47 && (*((_DWORD *)v2 + 1) & 0x400) != 0 && (*(_BYTE *)(*((_QWORD *)v2 + 68) + 8LL) & 1) == 0 )
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
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
      }
    }
    cbData = 4;
    v54 = RegQueryValueExW(hKey, L"TlsVersion", 0, &Type, Data, &cbData);
    if ( v54 || Type != 4 )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v54);
    }
    else if ( (*(_DWORD *)Data | 0x3FC0) == 0x3FC0 && (*(_WORD *)Data & 0x3FC0) != 0 )
    {
      g_tlsVersionsToUse = *(_DWORD *)Data;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          46,
          &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
          *(unsigned int *)Data);
    }
    else if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
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
        v56 = LocalAlloc(0x40u, 0x300u);
        *((_QWORD *)v2 + 80) = v56;
        if ( v56 )
        {
          memcpy_0(v56, &g_wpa3SuiteBDisabledCrypto, 48LL * *((unsigned int *)v2 + 158));
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
          goto LABEL_50;
        }
        goto LABEL_49;
      }
    }
  }
LABEL_50:
  v12 = hMem;
LABEL_51:
  v33 = UserData;
LABEL_140:
  NetworkingTriageScenario::GetConnected::EAPTlsBeginAction(
    (const struct NetworkingTriageScenario::GetConnected::RequiredFields *)&v69,
    v33);
  LocalFree(v12);
  if ( UserData && v2 )
  {
    LocalFree(*((HLOCAL *)v2 + 71));
    LocalFree(*((HLOCAL *)v2 + 68));
    LocalFree(*((HLOCAL *)v2 + 72));
    LocalFree(*((HLOCAL *)v2 + 80));
    _EAPTLS_CONTROL_BLOCK::`scalar deleting destructor'((_EAPTLS_CONTROL_BLOCK *)v2, v57);
    v2 = 0;
  }
  *v68 = v2;
  return (unsigned int)UserData;
}

```

## disassembly

```asm
0x180023b60  mov     [rsp-8+arg_10], rbx
0x180023b65  push    rbp
0x180023b66  push    rsi
0x180023b67  push    rdi
0x180023b68  push    r12
0x180023b6a  push    r13
0x180023b6c  push    r14
0x180023b6e  push    r15
0x180023b70  lea     rbp, [rsp-27h]
0x180023b75  sub     rsp, 90h
0x180023b7c  mov     rax, cs:__security_cookie
0x180023b83  xor     rax, rsp
0x180023b86  mov     [rbp+57h+var_40], rax
0x180023b8a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180023b91  xor     r8d, r8d
0x180023b94  mov     [rbp+57h+var_60], rcx
0x180023b98  xor     edi, edi
0x180023b9a  mov     [rbp+57h+hKey], 0
0x180023ba2  mov     [rbp+57h+Type], 0
0x180023ba9  mov     r14, rdx
0x180023bac  mov     dword ptr [rbp+57h+Data], 0
0x180023bb3  mov     [rbp+57h+cbData], 0
0x180023bba  mov     [rbp+57h+hMem], r8
0x180023bbe  lea     eax, [rdi+11h]
0x180023bc1  mov     [rbp+57h+var_58], eax
0x180023bc4  mov     [rbp+57h+var_68], r8
0x180023bc8  mov     [rbp+57h+var_44], 1
0x180023bcf  movdqu  [rbp+57h+var_54], xmm0
0x180023bd4  test    rcx, rcx
0x180023bd7  jz      loc_180024573
0x180023bdd  test    rdx, rdx
0x180023be0  jz      loc_180024573
0x180023be6  mov     r13d, 4000h
0x180023bec  lea     ecx, [rdi+13h]
0x180023bef  test    [rdx+4], r13d
0x180023bf3  cmovnz  eax, ecx
0x180023bf6  mov     [rbp+57h+var_58], eax
0x180023bf9  mov     rcx, cs:WPP_GLOBAL_Control
0x180023c00  lea     r15, WPP_GLOBAL_Control
0x180023c07  lea     rbx, String
0x180023c0e  lea     r12, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180023c15  cmp     rcx, r15
0x180023c18  jz      short loc_180023C35
0x180023c1a  cmp     [rdx+10h], rdi
0x180023c1e  mov     r9, rbx
0x180023c21  mov     rcx, [rcx+10h]
0x180023c25  mov     r8, r12
0x180023c28  cmovnz  r9, [rdx+10h]
0x180023c2d  lea     edx, [rdi+1Fh]
0x180023c30  call    WPP_SF_S
0x180023c35  mov     ecx, [r14+4]
0x180023c39  and     ecx, 14000h; Context
0x180023c3f  call    ?SetupMachineChangeNotification@@YAKK@Z; SetupMachineChangeNotification(ulong)
0x180023c44  mov     esi, eax
0x180023c46  test    eax, eax
0x180023c48  jz      short loc_180023C78
0x180023c4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180023c51  cmp     rcx, r15
0x180023c54  jz      short loc_180023C67
0x180023c56  mov     edx, 20h ; ' '
0x180023c5b  mov     rcx, [rcx+10h]
0x180023c5f  mov     r8, r12
0x180023c62  call    WPP_SF_
0x180023c67  mov     rbx, [rbp+57h+hMem]
0x180023c6b  test    esi, esi
0x180023c6d  jg      loc_1800245A2
0x180023c73  jmp     loc_180023F5A
0x180023c78  call    ?VerifyCallerTrust@@YAKPEAX@Z; VerifyCallerTrust(void *)
0x180023c7d  mov     esi, eax
0x180023c7f  test    eax, eax
0x180023c81  jz      short loc_180023C96
0x180023c83  mov     rcx, cs:WPP_GLOBAL_Control
0x180023c8a  cmp     rcx, r15
0x180023c8d  jz      short loc_180023C67
0x180023c8f  mov     edx, 21h ; '!'
0x180023c94  jmp     short loc_180023C5B
0x180023c96  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180023c9d  mov     ecx, 380h; unsigned __int64
0x180023ca2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180023ca7  xor     esi, esi
0x180023ca9  mov     rdi, rax
0x180023cac  test    rax, rax
0x180023caf  jz      loc_18002454C
0x180023cb5  xor     edx, edx; Val
0x180023cb7  mov     r8d, 380h; Size
0x180023cbd  mov     rcx, rax; void *
0x180023cc0  call    memset_0
0x180023cc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ccc  cmp     rcx, r15
0x180023ccf  jz      short loc_180023CE7
0x180023cd1  mov     r9d, [r14+90h]
0x180023cd8  lea     edx, [rsi+23h]
0x180023cdb  mov     rcx, [rcx+10h]
0x180023cdf  mov     r8, r12
0x180023ce2  call    WPP_SF_d
0x180023ce7  mov     eax, [r14+90h]
0x180023cee  mov     [rdi+31Ch], eax
0x180023cf4  mov     [rdi+320h], rsi
0x180023cfb  mov     [rdi+330h], rsi
0x180023d02  mov     [rdi+328h], rsi
0x180023d09  mov     [rdi+278h], esi
0x180023d0f  mov     [rdi+280h], rsi
0x180023d16  movups  xmm0, xmmword ptr [r14+80h]
0x180023d1e  mov     [rdi+2F8h], rsi
0x180023d25  mov     [rdi], esi
0x180023d27  movdqu  xmmword ptr [rdi+30Ch], xmm0
0x180023d2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d36  cmp     rcx, r15
0x180023d39  jz      short loc_180023D53
0x180023d3b  mov     r9, cs:?g_szEapTlsState@@3PAPEADA; char * near * g_szEapTlsState
0x180023d42  mov     edx, 24h ; '$'
0x180023d47  mov     rcx, [rcx+10h]
0x180023d4b  mov     r8, r12
0x180023d4e  call    WPP_SF_s
0x180023d53  cmp     [r14+8], esi
0x180023d57  mov     eax, esi
0x180023d59  setnz   al
0x180023d5c  mov     [rdi+4], eax
0x180023d5f  mov     ecx, [r14+4]
0x180023d63  and     ecx, 1
0x180023d66  add     ecx, ecx
0x180023d68  or      ecx, eax
0x180023d6a  mov     [rdi+4], ecx
0x180023d6d  mov     eax, [r14+4]
0x180023d71  and     eax, 4
0x180023d74  or      eax, ecx
0x180023d76  mov     [rdi+4], eax
0x180023d79  mov     ecx, [r14+4]
0x180023d7d  and     ecx, 2
0x180023d80  shl     ecx, 6
0x180023d83  or      ecx, eax
0x180023d85  mov     [rdi+4], ecx
0x180023d88  mov     eax, [r14+4]
0x180023d8c  and     eax, 10h
0x180023d8f  shl     eax, 4
0x180023d92  or      eax, ecx
0x180023d94  mov     [rdi+4], eax
0x180023d97  mov     ecx, [r14+4]
0x180023d9b  and     ecx, 20h
0x180023d9e  shl     ecx, 5
0x180023da1  or      ecx, eax
0x180023da3  mov     [rdi+4], ecx
0x180023da6  mov     edx, [r14+4]
0x180023daa  and     edx, 40h
0x180023dad  shl     edx, 5
0x180023db0  or      edx, ecx
0x180023db2  mov     [rdi+4], edx
0x180023db5  mov     eax, [r14+4]
0x180023db9  and     eax, 80h
0x180023dbe  shl     eax, 5
0x180023dc1  or      eax, edx
0x180023dc3  mov     [rdi+4], eax
0x180023dc6  mov     ecx, [r14+4]
0x180023dca  and     ecx, r13d
0x180023dcd  or      ecx, eax
0x180023dcf  mov     [rdi+4], ecx
0x180023dd2  mov     eax, [r14+4]
0x180023dd6  and     eax, 100h
0x180023ddb  shl     eax, 8
0x180023dde  or      eax, ecx
0x180023de0  mov     [rdi+4], eax
0x180023de3  mov     ecx, [r14+4]
0x180023de7  and     ecx, 20000h
0x180023ded  or      ecx, eax
0x180023def  mov     [rdi+4], ecx
0x180023df2  mov     eax, [r14+4]
0x180023df6  shr     eax, 3
0x180023df9  and     eax, 40000h
0x180023dfe  or      eax, ecx
0x180023e00  mov     [rdi+4], eax
0x180023e03  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EapServerTls13@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13> `wil::Feature<__WilFeatureTraits_Feature_EapServerTls13>::GetImpl(void)'::`2'::impl
0x180023e0a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::__private_IsEnabled(void)
0x180023e0f  test    al, al
0x180023e11  jz      short loc_180023E22
0x180023e13  mov     eax, [r14+4]
0x180023e17  shr     eax, 2
0x180023e1a  and     eax, 1000000h
0x180023e1f  or      [rdi+4], eax
0x180023e22  test    dword ptr [r14+4], 200h
0x180023e2a  jz      short loc_180023E4B
0x180023e2c  lea     rcx, ?g_csProtectCachedCredentials@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180023e33  call    cs:__imp_EnterCriticalSection
0x180023e39  call    ?ClearCachedCredList@@YAXXZ; ClearCachedCredList(void)
0x180023e3e  lea     rcx, ?g_csProtectCachedCredentials@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180023e45  call    cs:__imp_LeaveCriticalSection
0x180023e4b  test    byte ptr [r14+4], 80h
0x180023e50  jz      short loc_180023E6F
0x180023e52  mov     rcx, cs:WPP_GLOBAL_Control
0x180023e59  cmp     rcx, r15
0x180023e5c  jz      short loc_180023E76
0x180023e5e  mov     rcx, [rcx+10h]
0x180023e62  mov     edx, 25h ; '%'
0x180023e67  mov     r8, r12
0x180023e6a  call    WPP_SF_
0x180023e6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180023e76  mov     eax, [rdi+4]
0x180023e79  test    eax, 14000h
0x180023e7e  jnz     short loc_180023E84
0x180023e80  mov     ecx, esi
0x180023e82  jmp     short loc_180023EA2
0x180023e84  cmp     rcx, r15
0x180023e87  jz      short loc_180023E9D
0x180023e89  mov     rcx, [rcx+10h]
0x180023e8d  mov     edx, 26h ; '&'
0x180023e92  mov     r8, r12
0x180023e95  call    WPP_SF_
0x180023e9a  mov     eax, [rdi+4]
0x180023e9d  mov     ecx, 1
0x180023ea2  or      eax, 60h
0x180023ea5  mov     [rdi+300h], ecx
0x180023eab  mov     [rdi+4], eax
0x180023eae  test    al, 1
0x180023eb0  jz      loc_180023FBC
0x180023eb6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EapServerTls13@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13> `wil::Feature<__WilFeatureTraits_Feature_EapServerTls13>::GetImpl(void)'::`2'::impl
0x180023ebd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::__private_IsEnabled(void)
0x180023ec2  test    al, al
0x180023ec4  jz      short loc_180023ED3
0x180023ec6  call    cs:__imp_EapUseLegacyTlsStack
0x180023ecc  test    eax, eax
0x180023ece  setnz   al
0x180023ed1  jmp     short loc_180023ED5
0x180023ed3  mov     al, 1
0x180023ed5  mov     [rdi+351h], al
0x180023edb  mov     rax, [r14+78h]
0x180023edf  mov     [rdi+2E0h], rax
0x180023ee6  mov     eax, [rdi+4]
0x180023ee9  and     eax, r13d
0x180023eec  mov     dword ptr [rdi+298h], 1811Eh
0x180023ef6  test    dword ptr [rdi+4], 800h
0x180023efd  jnz     short loc_180023F03
0x180023eff  test    eax, eax
0x180023f01  jz      short loc_180023F2A
0x180023f03  test    eax, eax
0x180023f05  jz      short loc_180023F2A
0x180023f07  mov     edx, [r14+70h]; unsigned int
0x180023f0b  lea     r8, [rdi+238h]; struct _EAPTLS_USER_PROPERTIES **
0x180023f12  mov     rcx, [r14+68h]; Src
0x180023f16  call    ?EapTlsReadUserData@@YAKPEAEKPEAPEAU_EAPTLS_USER_PROPERTIES@@@Z; EapTlsReadUserData(uchar *,ulong,_EAPTLS_USER_PROPERTIES * *)
0x180023f1b  mov     esi, eax
0x180023f1d  test    eax, eax
0x180023f1f  jz      loc_180023FA9
0x180023f25  jmp     loc_180023C67
0x180023f2a  cmp     [r14+58h], rsi
0x180023f2e  jz      short loc_180023F73
0x180023f30  cmp     [r14+60h], esi
0x180023f34  jz      short loc_180023F73
0x180023f36  mov     edx, [r14+60h]; uBytes
0x180023f3a  mov     ecx, 40h ; '@'; uFlags
0x180023f3f  call    cs:__imp_LocalAlloc
0x180023f45  mov     [rdi+238h], rax
0x180023f4c  test    rax, rax
0x180023f4f  jnz     short loc_180023F61
0x180023f51  mov     esi, 8007000Eh
0x180023f56  mov     rbx, [rbp+57h+hMem]
0x180023f5a  mov     edx, esi
0x180023f5c  jmp     loc_1800245AB
0x180023f61  mov     r8d, [r14+60h]; Size
0x180023f65  mov     rcx, rax; void *
0x180023f68  mov     rdx, [r14+58h]; Src
0x180023f6c  call    memcpy_0
0x180023f71  jmp     short loc_180023FA9
0x180023f73  mov     edx, 48h ; 'H'; uBytes
0x180023f78  lea     ecx, [rdx-8]; uFlags
0x180023f7b  call    cs:__imp_LocalAlloc
0x180023f81  mov     [rdi+238h], rax
0x180023f88  test    rax, rax
0x180023f8b  jz      short loc_180023F51
0x180023f8d  mov     [rax+4], esi
0x180023f90  mov     rax, [rdi+238h]
0x180023f97  mov     dword ptr [rax+8], 48h ; 'H'
0x180023f9e  mov     rcx, [rdi+238h]
0x180023fa5  mov     [rcx+46h], si
0x180023fa9  mov     al, [r14+20h]
0x180023fad  mov     [rdi+2D1h], al
0x180023fb3  mov     [rbp+57h+var_70], 1
0x180023fba  jmp     short loc_180024008
0x180023fbc  mov     [rbp+57h+var_70], esi
0x180023fbf  call    cs:__imp_EapUseLegacyTlsStack
0x180023fc5  test    eax, eax
0x180023fc7  lea     r8, [rdi+238h]; struct _EAPTLS_USER_PROPERTIES **
0x180023fce  setnz   al
0x180023fd1  mov     [rdi+351h], al
0x180023fd7  xor     al, 1
0x180023fd9  mov     [rdi+378h], al
0x180023fdf  mov     dword ptr [rdi+298h], 0C19Ch
0x180023fe9  mov     rax, [r14+38h]
0x180023fed  mov     [rdi+8], rax
0x180023ff1  mov     edx, [r14+70h]; unsigned int
0x180023ff5  mov     rcx, [r14+68h]; Src
0x180023ff9  call    ?EapTlsReadUserData@@YAKPEAEKPEAPEAU_EAPTLS_USER_PROPERTIES@@@Z; EapTlsReadUserData(uchar *,ulong,_EAPTLS_USER_PROPERTIES * *)
0x180023ffe  mov     esi, eax
0x180024000  test    eax, eax
0x180024002  jnz     loc_180023C67
0x180024008  test    byte ptr [rdi+4], 1
0x18002400c  jnz     short loc_180024018
0x18002400e  mov     r8d, [r14+60h]
0x180024012  mov     rdx, [r14+58h]
0x180024016  jmp     short loc_18002401D
0x180024018  xor     edx, edx; unsigned __int8 *
0x18002401a  xor     r8d, r8d; unsigned int
  ... truncated ...
```
