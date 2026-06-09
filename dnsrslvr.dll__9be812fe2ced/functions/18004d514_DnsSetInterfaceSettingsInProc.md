# DnsSetInterfaceSettingsInProc

- ea: `0x18004d514`
- end: `0x18004dfcd`
- name: `DnsSetInterfaceSettingsInProc`
- size: `2745`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x180038940`
- `0x1800449f0`
- `0x18004dfd4`

## callees

- `0x180004aa8`
- `0x180008b00`
- `0x18001f118`
- `0x18002025c`
- `0x180024e10`
- `0x180027900`
- `0x180031aa4`
- `0x180032dd4`
- `0x18003431c`
- `0x180038f28`
- `0x180046ec0`
- `0x180047818`
- `0x18004d514`
- `0x18007b1cc`
- `0x18007de18`
- `0x1800862fc`
- `0x1800864ac`
- `0x180086700`
- `0x180086b1c`
- `0x18008841c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004df2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004df3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004df4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004df2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004df3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004df4d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004da35`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004da99`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004dafd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004db65`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004dbcf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004de03`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004da35`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004da99`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004dafd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004db65`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004dbcf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004de03`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004d917`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004d917`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004deb1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004deb1`

## string_xrefs

- `0x18004d9ce`: `SYSTEM\CurrentControlSet\Services\Dnscache`
- `0x18004d9da`: `Dnscache`
- `0x18004d933`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces`
- `0x18004d976`: `System\CurrentControlSet\Services\Tcpip6\Parameters\Interfaces`
- `0x18004d93f`: `DnscacheTcpipInterfaces`
- `0x18004d982`: `DnscacheTcpip6Interfaces`

## pseudocode

```c
__int64 __fastcall DnsSetInterfaceSettingsInProc(__int64 a1, __int64 a2)
{
  __int64 v3; // r14
  const WCHAR *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // r12
  int v9; // eax
  unsigned int v10; // ebx
  BOOL v11; // ecx
  __int64 v12; // r13
  BOOL v13; // r14d
  BOOL v14; // edx
  __int64 v15; // r12
  unsigned int v16; // eax
  unsigned int v17; // eax
  __int64 v18; // rdx
  HRESULT v19; // eax
  unsigned int v20; // ebx
  int v21; // r14d
  HRESULT v22; // eax
  unsigned int v23; // ebx
  int v24; // r9d
  unsigned int PersistedRegistryKeyHelper; // eax
  int v26; // r9d
  __int64 v27; // rdx
  HKEY v28; // r13
  LSTATUS v29; // eax
  LSTATUS v30; // r14d
  LSTATUS v31; // eax
  LSTATUS v32; // r14d
  LSTATUS v33; // eax
  LSTATUS v34; // r14d
  LSTATUS v35; // eax
  LSTATUS v36; // r14d
  LSTATUS v37; // eax
  LSTATUS v38; // r14d
  unsigned int v39; // eax
  unsigned int v40; // r14d
  unsigned int v41; // eax
  unsigned int v42; // r14d
  BYTE *v43; // r15
  BYTE *v44; // r12
  unsigned int v45; // eax
  int v46; // ecx
  unsigned int v47; // r14d
  unsigned int v48; // eax
  int v49; // ecx
  unsigned int v50; // r14d
  unsigned int v51; // eax
  unsigned int v52; // r14d
  LSTATUS v53; // eax
  LSTATUS v54; // r14d
  unsigned int v55; // eax
  HKEY v56; // rcx
  __int64 v59; // [rsp+48h] [rbp-B8h]
  __int64 v60; // [rsp+50h] [rbp-B0h]
  __int64 v61; // [rsp+58h] [rbp-A8h]
  __int64 v62; // [rsp+60h] [rbp-A0h]
  HKEY v63; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  HKEY v65; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v66[160]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t pszDest[264]; // [rsp+120h] [rbp+20h] BYREF
  wchar_t v68[264]; // [rsp+330h] [rbp+230h] BYREF

  v3 = a1;
  memset_0(v66, 0, sizeof(v66));
  memset_0(pszDest, 0, 0x20Au);
  memset_0(v68, 0, 0x20Au);
  hKey = 0;
  v65 = 0;
  v63 = 0;
  if ( g_fVelocityFixForwarder )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      v5 = 199;
LABEL_6:
      WPP_SF__guid_(v4, v5, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v3);
    }
  }
  else if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    v5 = 200;
    goto LABEL_6;
  }
  if ( !a2 || *(_DWORD *)a2 != 1 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      v7 = 201;
      goto LABEL_147;
    }
    goto LABEL_148;
  }
  v6 = *(_QWORD *)(a2 + 8);
  if ( (v6 & 0x20) != 0 && !*(_QWORD *)(a2 + 16) )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      v7 = 202;
LABEL_147:
      WPP_SF_(1035, v7, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids);
      goto LABEL_148;
    }
    goto LABEL_148;
  }
  if ( (v6 & 4) != 0 && !*(_QWORD *)(a2 + 32) )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      v7 = 203;
      goto LABEL_147;
    }
LABEL_148:
    v10 = 87;
    goto LABEL_149;
  }
  if ( (v6 & 2) != 0 )
  {
    v4 = *(const WCHAR **)(a2 + 24);
    if ( v4 )
    {
      if ( !(unsigned int)Dns_ValidateIpListString(v4) )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        {
          v7 = 204;
          goto LABEL_147;
        }
        goto LABEL_148;
      }
    }
  }
  if ( (*(_QWORD *)(a2 + 8) & 0x200LL) != 0 )
  {
    v4 = *(const WCHAR **)(a2 + 56);
    if ( v4 )
    {
      if ( !(unsigned int)Dns_ValidateIpListString(v4) )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        {
          v7 = 205;
          goto LABEL_147;
        }
        goto LABEL_148;
      }
    }
  }
  v8 = *(_QWORD *)(a2 + 8);
  if ( (v8 & 0x4000) != 0 )
  {
    v9 = *(_DWORD *)(a2 + 112);
    if ( v9 == 2 || (v9 & 0xFFFFFFFC) != 0 )
    {
      v10 = 87;
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_Dd(v4, 206, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, 87, *(_DWORD *)(a2 + 112));
      goto LABEL_149;
    }
  }
  v60 = *(_QWORD *)(a2 + 8) & 0x1000LL;
  v11 = (v8 & 0x1000) != 0;
  v12 = *(_QWORD *)(a2 + 8) & 0x2000LL;
  v61 = v12;
  v13 = (v8 & 0x2000) != 0;
  v62 = *(_QWORD *)(a2 + 8) & 0x10000LL;
  v14 = (v8 & 0x10000) != 0;
  v15 = *(_QWORD *)(a2 + 8) & 0x20000LL;
  v59 = (unsigned int)v15;
  if ( !v60 && (*(_QWORD *)(a2 + 8) & 0x10000LL) == 0
    || (v16 = ValidateInterfaceProperties(v11, v14, *(_DWORD *)(a2 + 80), *(_QWORD *)(a2 + 88), *(wchar_t **)(a2 + 24)),
        (v10 = v16) == 0) )
  {
    if ( v12 || v15 )
    {
      v17 = ValidateInterfaceProperties(
              v13,
              v15 != 0,
              *(_DWORD *)(a2 + 96),
              *(_QWORD *)(a2 + 104),
              *(wchar_t **)(a2 + 56));
      v10 = v17;
      if ( v17 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
          goto LABEL_43;
        v18 = 208;
        goto LABEL_42;
      }
    }
    if ( !g_fVelocityFixForwarder )
    {
      v17 = Rpc_DnsRegistryAccessCheck(0x20006u, qword_180094C40);
      v10 = v17;
      if ( v17 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
        {
LABEL_43:
          v3 = a1;
          goto LABEL_149;
        }
        v18 = 209;
LABEL_42:
        WPP_SF_d(1035, v18, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v17);
        goto LABEL_43;
      }
    }
    v3 = a1;
    if ( !(unsigned int)Dns_GuidToString(a1, v66) )
    {
      v10 = 8;
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_(1035, 210, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids);
      goto LABEL_149;
    }
    v19 = StringCchPrintfExW(pszDest, 0x105u, 0, 0, 0, L"\\%s", v66);
    v20 = v19;
    if ( v19 < 0 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_d(1035, 211, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, (unsigned int)v19);
      v10 = WX_WIN32_FROM_HR(v20);
      goto LABEL_149;
    }
    if ( (*(_DWORD *)(a2 + 8) & 0x37C00) != 0 )
    {
      v21 = 1;
      v22 = StringCchPrintfExW(v68, 0x105u, 0, 0, 0, L"\\%s\\%s", L"InterfaceSpecificParameters", v66);
      v23 = v22;
      if ( v22 < 0 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_d(1035, 212, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, (unsigned int)v22);
        v10 = WX_WIN32_FROM_HR(v23);
        goto LABEL_43;
      }
    }
    else
    {
      v21 = 0;
    }
    AcquireSRWLockExclusive(&g_rwInterfaceSettingsLock);
    PersistedRegistryKeyHelper = CreatePersistedRegistryKeyHelper(
                                   (unsigned int)L"DnscacheTcpipInterfaces",
                                   (unsigned int)L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces",
                                   (unsigned int)pszDest,
                                   v24,
                                   131078,
                                   0,
                                   1,
                                   (__int64)&hKey);
    v10 = PersistedRegistryKeyHelper;
    if ( PersistedRegistryKeyHelper )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      {
        v27 = 213;
        goto LABEL_138;
      }
    }
    else if ( (*(_BYTE *)(a2 + 8) & 1) != 0
           && (PersistedRegistryKeyHelper = CreatePersistedRegistryKeyHelper(
                                              (unsigned int)L"DnscacheTcpip6Interfaces",
                                              (unsigned int)L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters\\Interfaces",
                                              (unsigned int)pszDest,
                                              v26,
                                              131078,
                                              0,
                                              1,
                                              (__int64)&v65),
               (v10 = PersistedRegistryKeyHelper) != 0) )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      {
        v27 = 214;
LABEL_138:
        WPP_SF_d(1035, v27, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, PersistedRegistryKeyHelper);
      }
    }
    else
    {
      if ( !v21
        || (PersistedRegistryKeyHelper = CreatePersistedRegistryKeyHelper(
                                           (unsigned int)L"Dnscache",
                                           (unsigned int)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
                                           (unsigned int)v68,
                                           v26,
                                           131078,
                                           0,
                                           1,
                                           (__int64)&v63),
            (v10 = PersistedRegistryKeyHelper) == 0) )
      {
        v28 = hKey;
        if ( (*(_BYTE *)(a2 + 8) & 8) != 0 )
        {
          v29 = RegSetValueExW(hKey, L"RegistrationEnabled", 0, 4u, (const BYTE *)(a2 + 40), 4u);
          v30 = v29;
          if ( v29 )
          {
            if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
              WPP_SF_SdD(
                *(_DWORD *)(a2 + 40),
                216,
                (unsigned int)WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids,
                (unsigned int)L"RegistrationEnabled",
                *(_DWORD *)(a2 + 40),
                v29);
            v10 = v30;
          }
        }
        if ( (*(_BYTE *)(a2 + 8) & 0x10) != 0 )
        {
          v31 = RegSetValueExW(v28, L"RegisterAdapterName", 0, 4u, (const BYTE *)(a2 + 44), 4u);
          v32 = v31;
          if ( v31 )
          {
            if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
              WPP_SF_SdD(
                *(_DWORD *)(a2 + 44),
                217,
                (unsigned int)WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids,
                (unsigned int)L"RegisterAdapterName",
                *(_DWORD *)(a2 + 44),
                v31);
            v10 = v32;
          }
        }
        if ( *(char *)(a2 + 8) < 0 )
        {
          v33 = RegSetValueExW(v28, L"EnableMulticast", 0, 4u, (const BYTE *)(a2 + 48), 4u);
          v34 = v33;
          if ( v33 )
          {
            if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
              WPP_SF_SdD(
                *(_DWORD *)(a2 + 48),
                218,
                (unsigned int)WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids,
                (unsigned int)L"EnableMulticast",
                *(_DWORD *)(a2 + 48),
                v33);
            v10 = v34;
          }
        }
        if ( (*(_DWORD *)(a2 + 8) & 0x100LL) != 0 )
        {
          v35 = RegSetValueExW(v28, L"QueryAdapterName", 0, 4u, (const BYTE *)(a2 + 52), 4u);
          v36 = v35;
          if ( v35 )
          {
            if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
              WPP_SF_SdD(
                *(_DWORD *)(a2 + 52),
                219,
                (unsigned int)WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids,
                (unsigned int)L"QueryAdapterName",
                *(_DWORD *)(a2 + 52),
                v35);
            v10 = v36;
          }
        }
        if ( (*(_DWORD *)(a2 + 8) & 0x400LL) != 0 )
        {
          v37 = RegSetValueExW(v63, L"DisableUnConstrainedQueries", 0, 4u, (const BYTE *)(a2 + 64), 4u);
          v38 = v37;
          if ( v37 )
          {
            if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
              WPP_SF_SdD(
                *(_DWORD *)(a2 + 64),
                220,
                (unsigned int)WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids,
                (unsigned int)L"DisableUnConstrainedQueries",
                *(_DWORD *)(a2 + 64),
                v37);
            v10 = v38;
          }
        }
        if ( (*(_BYTE *)(a2 + 8) & 0x20) != 0 )
        {
          v39 = SetRegistryString(v28, L"Domain", *(BYTE **)(a2 + 16));
          v40 = v39;
          if ( v39 )
          {
            if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
              WPP_SF_SSD(
                *(_QWORD *)(a2 + 16),
                221,
                (unsigned int)WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids,
                (unsigned int)L"Domain",
                *(_QWORD *)(a2 + 16),
                v39);
            v10 = v40;
          }
        }
        if ( (*(_BYTE *)(a2 + 8) & 1) != 0 )
          v28 = v65;
        if ( (*(_BYTE *)(a2 + 8) & 4) != 0 )
        {
          v41 = SetRegistryString(v28, L"SearchList", *(BYTE **)(a2 + 32));
          v42 = v41;
          if ( v41 )
          {
            if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
              WPP_SF_SSD(
                *(_QWORD *)(a2 + 32),
                222,
                (unsigned int)WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids,
                (unsigned int)L"SearchList",
                *(_QWORD *)(a2 + 32),
                v41);
            v10 = v42;
          }
        }
        v43 = (BYTE *)&WideCharStr;
        if ( (*(_BYTE *)(a2 + 8) & 2) != 0 )
        {
          v44 = (BYTE *)&WideCharStr;
          if ( *(_QWORD *)(a2 + 24) )
            v44 = *(BYTE **)(a2 + 24);
          v45 = SetRegistryString(v28, L"NameServer", v44);
          v47 = v45;
          if ( v45 )
          {
            if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
              WPP_SF_SSD(
                v46,
                223,
                (unsigned int)WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids,
                (unsigned int)L"NameServer",
                (__int64)v44,
                v45);
            v10 = v47;
          }
          v15 = v59;
        }
        if ( (*(_DWORD *)(a2 + 8) & 0x200LL) != 0 )
        {
          if ( *(_QWORD *)(a2 + 56) )
            v43 = *(BYTE **)(a2 + 56);
          v48 = SetRegistryString(v28, L"ProfileNameServer", v43);
          v50 = v48;
          if ( v48 )
          {
            if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
              WPP_SF_SSD(
                v49,
                224,
                (unsigned int)WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids,
                (unsigned int)L"ProfileNameServer",
                (__int64)v43,
                v48);
            v10 = v50;
          }
        }
        if ( (*(_DWORD *)(a2 + 8) & 0x800LL) != 0 )
        {
          v51 = SetRegistryString(v63, L"SupplementalSearchList", *(BYTE **)(a2 + 72));
          v52 = v51;
          if ( v51 )
          {
            if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
              WPP_SF_SSD(
                *(_QWORD *)(a2 + 72),
                225,
                (unsigned int)WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids,
                (unsigned int)L"SupplementalSearchList",
                *(_QWORD *)(a2 + 72),
                v51);
            v10 = v52;
          }
        }
        if ( (*(_DWORD *)(a2 + 8) & 0x4000LL) != 0 )
        {
          v53 = RegSetValueExW(v63, L"EncryptedDnsAdapterFlags", 0, 4u, (const BYTE *)(a2 + 112), 4u);
          v54 = v53;
          if ( v53 )
          {
            if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
              WPP_SF_SdD(
                *(_DWORD *)(a2 + 112),
                226,
                (unsigned int)WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids,
                (unsigned int)L"EncryptedDnsAdapterFlags",
                *(_DWORD *)(a2 + 112),
                v53);
            v10 = v54;
          }
        }
        if ( v60 || v61 || v62 || v15 )
        {
          v55 = DnsSetInterfaceSettingsSecure(v63);
          if ( v55 )
            v10 = v55;
        }
        if ( *(_QWORD *)(a2 + 8) )
        {
          UpdateNetworkInfo(0, 0);
          UpdateNetworkInfo(0, 1);
        }
        goto LABEL_139;
      }
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      {
        v27 = 215;
        goto LABEL_138;
      }
    }
LABEL_139:
    ReleaseSRWLockExclusive(&g_rwInterfaceSettingsLock);
    goto LABEL_43;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 207, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v16);
  v3 = a1;
LABEL_149:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v65 )
    RegCloseKey(v65);
  v56 = v63;
  if ( v63 )
    RegCloseKey(v63);
  if ( g_fVelocityFixForwarder )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 227, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v10);
  }
  else if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    WPP_SF__guid_D(v56, 228, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v3, v10);
  }
  return v10;
}

```

## disassembly

```asm
0x18004d514  mov     [rsp-8+arg_10], rbx
0x18004d519  push    rbp
0x18004d51a  push    rsi
0x18004d51b  push    rdi
0x18004d51c  push    r12
0x18004d51e  push    r13
0x18004d520  push    r14
0x18004d522  push    r15
0x18004d524  lea     rbp, [rsp-450h]
0x18004d52c  sub     rsp, 550h
0x18004d533  mov     rax, cs:__security_cookie
0x18004d53a  xor     rax, rsp
0x18004d53d  mov     [rbp+480h+var_40], rax
0x18004d544  mov     rsi, rdx
0x18004d547  mov     [rsp+580h+var_540], rcx
0x18004d54c  mov     r14, rcx
0x18004d54f  xor     edx, edx; Val
0x18004d551  lea     rcx, [rbp+480h+var_500]; void *
0x18004d555  mov     r8d, 0A0h; Size
0x18004d55b  call    memset_0
0x18004d560  mov     ebx, 20Ah
0x18004d565  lea     rcx, [rbp+480h+pszDest]; void *
0x18004d569  mov     r8d, ebx; Size
0x18004d56c  xor     edx, edx; Val
0x18004d56e  call    memset_0
0x18004d573  mov     r8d, ebx; Size
0x18004d576  lea     rcx, [rbp+480h+var_250]; void *
0x18004d57d  xor     edx, edx; Val
0x18004d57f  call    memset_0
0x18004d584  xor     r13d, r13d
0x18004d587  cmp     cs:g_fVelocityFixForwarder, r13d
0x18004d58e  mov     [rsp+580h+hKey], r13
0x18004d593  mov     [rsp+580h+var_508], r13
0x18004d598  mov     [rsp+580h+var_518], r13
0x18004d59d  jz      short loc_18004D5B3
0x18004d59f  lea     edi, [r13+8]
0x18004d5a3  test    byte ptr cs:xmmword_1800AB5A0+1, dil
0x18004d5aa  jz      short loc_18004D5D5
0x18004d5ac  mov     edx, 0C7h
0x18004d5b1  jmp     short loc_18004D5C6
0x18004d5b3  mov     edi, 8
0x18004d5b8  test    byte ptr cs:xmmword_1800AB5A0+1, dil
0x18004d5bf  jz      short loc_18004D5D5
0x18004d5c1  mov     edx, 0C8h
0x18004d5c6  mov     r9, r14
0x18004d5c9  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x18004d5d0  call    WPP_SF__guid_
0x18004d5d5  test    rsi, rsi
0x18004d5d8  jz      loc_18004DEFF
0x18004d5de  cmp     dword ptr [rsi], 1
0x18004d5e1  jnz     loc_18004DEFF
0x18004d5e7  mov     rdx, [rsi+8]
0x18004d5eb  test    dl, 20h
0x18004d5ee  jz      short loc_18004D60D
0x18004d5f0  cmp     [rsi+10h], r13
0x18004d5f4  jnz     short loc_18004D60D
0x18004d5f6  test    byte ptr cs:xmmword_1800AB5A0+1, dil
0x18004d5fd  jz      loc_18004DF1E
0x18004d603  mov     edx, 0CAh
0x18004d608  jmp     loc_18004DF0D
0x18004d60d  test    dl, 4
0x18004d610  jz      short loc_18004D62F
0x18004d612  cmp     [rsi+20h], r13
0x18004d616  jnz     short loc_18004D62F
0x18004d618  test    byte ptr cs:xmmword_1800AB5A0+1, dil
0x18004d61f  jz      loc_18004DF1E
0x18004d625  mov     edx, 0CBh
0x18004d62a  jmp     loc_18004DF0D
0x18004d62f  test    dl, 2
0x18004d632  jz      short loc_18004D660
0x18004d634  mov     rcx, [rsi+18h]; S
0x18004d638  test    rcx, rcx
0x18004d63b  jz      short loc_18004D660
0x18004d63d  and     edx, 1
0x18004d640  call    Dns_ValidateIpListString
0x18004d645  test    eax, eax
0x18004d647  jnz     short loc_18004D660
0x18004d649  test    byte ptr cs:xmmword_1800AB5A0+1, dil
0x18004d650  jz      loc_18004DF1E
0x18004d656  mov     edx, 0CCh
0x18004d65b  jmp     loc_18004DF0D
0x18004d660  mov     rdx, [rsi+8]
0x18004d664  bt      rdx, 9
0x18004d669  jnb     short loc_18004D697
0x18004d66b  mov     rcx, [rsi+38h]; S
0x18004d66f  test    rcx, rcx
0x18004d672  jz      short loc_18004D697
0x18004d674  and     edx, 1
0x18004d677  call    Dns_ValidateIpListString
0x18004d67c  test    eax, eax
0x18004d67e  jnz     short loc_18004D697
0x18004d680  test    byte ptr cs:xmmword_1800AB5A0+1, dil
0x18004d687  jz      loc_18004DF1E
0x18004d68d  mov     edx, 0CDh
0x18004d692  jmp     loc_18004DF0D
0x18004d697  mov     r12, [rsi+8]
0x18004d69b  bt      r12, 0Eh
0x18004d6a0  jnb     short loc_18004D6DE
0x18004d6a2  mov     eax, [rsi+70h]
0x18004d6a5  cmp     eax, 2
0x18004d6a8  jz      short loc_18004D6B1
0x18004d6aa  test    eax, 0FFFFFFFCh
0x18004d6af  jz      short loc_18004D6DE
0x18004d6b1  mov     ebx, 57h ; 'W'
0x18004d6b6  test    byte ptr cs:xmmword_1800AB5A0+1, dil
0x18004d6bd  jz      loc_18004DF23
0x18004d6c3  lea     edx, [rbx+77h]
0x18004d6c6  mov     [rsp+580h+dwFlags], eax
0x18004d6ca  mov     r9d, ebx
0x18004d6cd  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x18004d6d4  call    WPP_SF_Dd
0x18004d6d9  jmp     loc_18004DF23
0x18004d6de  mov     r8, r12
0x18004d6e1  mov     ecx, r13d
0x18004d6e4  and     r8d, 1000h
0x18004d6eb  mov     r13, r12
0x18004d6ee  mov     rax, r12
0x18004d6f1  mov     [rsp+580h+var_530], r8
0x18004d6f6  setnz   cl; int
0x18004d6f9  mov     r14d, 0
0x18004d6ff  and     r13d, 2000h
0x18004d706  mov     edx, 0
0x18004d70b  mov     r15d, 0
0x18004d711  mov     [rsp+580h+var_528], r13
0x18004d716  setnz   r14b
0x18004d71a  and     eax, 10000h
0x18004d71f  mov     [rsp+580h+var_520], rax
0x18004d724  setnz   dl; int
0x18004d727  and     r12d, 20000h
0x18004d72e  mov     [rsp+580h+var_538], r12
0x18004d733  setnz   r15b
0x18004d737  test    r8, r8
0x18004d73a  jnz     short loc_18004D741
0x18004d73c  test    rax, rax
0x18004d73f  jz      short loc_18004D761
0x18004d741  mov     rax, [rsi+18h]
0x18004d745  mov     r9, [rsi+58h]; int
0x18004d749  mov     r8d, [rsi+50h]; int
0x18004d74d  mov     qword ptr [rsp+580h+dwFlags], rax; String
0x18004d752  call    ValidateInterfaceProperties
0x18004d757  mov     ebx, eax
0x18004d759  test    eax, eax
0x18004d75b  jnz     loc_18004DED3
0x18004d761  test    r13, r13
0x18004d764  jnz     short loc_18004D76D
0x18004d766  test    r12, r12
0x18004d769  jz      short loc_18004D796
0x18004d76b  jmp     short loc_18004D770
0x18004d76d  xor     r13d, r13d
0x18004d770  mov     rax, [rsi+38h]
0x18004d774  mov     edx, r15d; int
0x18004d777  mov     r9, [rsi+68h]; int
0x18004d77b  mov     ecx, r14d; int
0x18004d77e  mov     r8d, [rsi+60h]; int
0x18004d782  mov     qword ptr [rsp+580h+dwFlags], rax; String
0x18004d787  call    ValidateInterfaceProperties
0x18004d78c  mov     ebx, eax
0x18004d78e  test    eax, eax
0x18004d790  jnz     loc_18004DEBC
0x18004d796  cmp     cs:g_fVelocityFixForwarder, r13d
0x18004d79d  mov     r15d, 20006h
0x18004d7a3  jnz     short loc_18004D7E6
0x18004d7a5  lea     rdx, qword_180094C40; pSecurityDescriptor
0x18004d7ac  mov     ecx, r15d; DesiredAccess
0x18004d7af  call    Rpc_DnsRegistryAccessCheck
0x18004d7b4  mov     ebx, eax
0x18004d7b6  test    eax, eax
0x18004d7b8  jz      short loc_18004D7E6
0x18004d7ba  test    byte ptr cs:xmmword_1800AB5A0+1, dil
0x18004d7c1  jz      short loc_18004D7DC
0x18004d7c3  mov     edx, 0D1h
0x18004d7c8  mov     ecx, 40Bh
0x18004d7cd  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x18004d7d4  mov     r9d, eax
0x18004d7d7  call    WPP_SF_d
0x18004d7dc  mov     r14, [rsp+580h+var_540]
0x18004d7e1  jmp     loc_18004DF23
0x18004d7e6  mov     r14, [rsp+580h+var_540]
0x18004d7eb  lea     rdx, [rbp+480h+var_500]
0x18004d7ef  mov     rcx, r14
0x18004d7f2  call    Dns_GuidToString
0x18004d7f7  test    eax, eax
0x18004d7f9  jnz     short loc_18004D825
0x18004d7fb  mov     ebx, edi
0x18004d7fd  test    byte ptr cs:xmmword_1800AB5A0+1, dil
0x18004d804  jz      loc_18004DF23
0x18004d80a  mov     edx, 0D2h
0x18004d80f  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x18004d816  mov     ecx, 40Bh
0x18004d81b  call    WPP_SF_
0x18004d820  jmp     loc_18004DF23
0x18004d825  lea     rax, [rbp+480h+var_500]
0x18004d829  xor     r9d, r9d; pcchRemaining
0x18004d82c  mov     [rsp+580h+var_550], rax
0x18004d831  lea     rcx, [rbp+480h+pszDest]; pszDest
0x18004d835  lea     rax, aS_0; "\\%s"
0x18004d83c  xor     r8d, r8d; ppszDestEnd
0x18004d83f  mov     [rsp+580h+pszFormat], rax; pszFormat
0x18004d844  mov     edx, 105h; cchDest
0x18004d849  mov     qword ptr [rsp+580h+dwFlags], r13; dwFlags
0x18004d84e  call    StringCchPrintfExW
0x18004d853  mov     ebx, eax
0x18004d855  test    eax, eax
0x18004d857  jns     short loc_18004D889
0x18004d859  test    byte ptr cs:xmmword_1800AB5A0+1, dil
0x18004d860  jz      short loc_18004D87B
0x18004d862  mov     edx, 0D3h
0x18004d867  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x18004d86e  mov     ecx, 40Bh
0x18004d873  mov     r9d, eax
0x18004d876  call    WPP_SF_d
0x18004d87b  mov     ecx, ebx
0x18004d87d  call    WX_WIN32_FROM_HR
0x18004d882  mov     ebx, eax
0x18004d884  jmp     loc_18004DF23
0x18004d889  mov     eax, [rsi+8]
0x18004d88c  test    rax, 37C00h
0x18004d892  jz      short loc_18004D90D
0x18004d894  lea     rax, [rbp+480h+var_500]
0x18004d898  xor     r9d, r9d; pcchRemaining
0x18004d89b  mov     [rsp+580h+var_548], rax
0x18004d8a0  lea     rcx, [rbp+480h+var_250]; pszDest
0x18004d8a7  lea     rax, aInterfacespeci; "InterfaceSpecificParameters"
0x18004d8ae  xor     r8d, r8d; ppszDestEnd
0x18004d8b1  mov     [rsp+580h+var_550], rax
0x18004d8b6  mov     edx, 105h; cchDest
0x18004d8bb  lea     rax, aSS; "\\%s\\%s"
0x18004d8c2  mov     r14d, 1
0x18004d8c8  mov     [rsp+580h+pszFormat], rax; pszFormat
0x18004d8cd  mov     qword ptr [rsp+580h+dwFlags], r13; dwFlags
0x18004d8d2  call    StringCchPrintfExW
0x18004d8d7  mov     ebx, eax
0x18004d8d9  test    eax, eax
0x18004d8db  jns     short loc_18004D910
0x18004d8dd  test    byte ptr cs:xmmword_1800AB5A0+1, dil
0x18004d8e4  jz      short loc_18004D8FF
0x18004d8e6  mov     edx, 0D4h
0x18004d8eb  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x18004d8f2  mov     ecx, 40Bh
0x18004d8f7  mov     r9d, eax
0x18004d8fa  call    WPP_SF_d
0x18004d8ff  mov     ecx, ebx
0x18004d901  call    WX_WIN32_FROM_HR
0x18004d906  mov     ebx, eax
0x18004d908  jmp     loc_18004D7DC
0x18004d90d  mov     r14d, r13d
0x18004d910  lea     rcx, g_rwInterfaceSettingsLock; SRWLock
0x18004d917  call    cs:__imp_AcquireSRWLockExclusive
0x18004d91d  lea     rax, [rsp+580h+hKey]
0x18004d922  mov     [rsp+580h+var_548], rax
0x18004d927  lea     r8, [rbp+480h+pszDest]
0x18004d92b  mov     dword ptr [rsp+580h+var_550], 1
0x18004d933  lea     rdx, aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\Tc"...
0x18004d93a  mov     [rsp+580h+pszFormat], r13
0x18004d93f  lea     rcx, aDnscachetcpipi; "DnscacheTcpipInterfaces"
0x18004d946  mov     [rsp+580h+dwFlags], r15d
0x18004d94b  call    CreatePersistedRegistryKeyHelper
0x18004d950  mov     ebx, eax
0x18004d952  test    eax, eax
0x18004d954  jnz     loc_18004DE88
0x18004d95a  test    byte ptr [rsi+8], 1
0x18004d95e  jz      short loc_18004D9B0
0x18004d960  lea     rax, [rsp+580h+var_508]
0x18004d965  mov     [rsp+580h+var_548], rax
0x18004d96a  lea     r8, [rbp+480h+pszDest]
0x18004d96e  mov     dword ptr [rsp+580h+var_550], 1
0x18004d976  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Tc"...
0x18004d97d  mov     [rsp+580h+pszFormat], r13
0x18004d982  lea     rcx, aDnscachetcpip6; "DnscacheTcpip6Interfaces"
0x18004d989  mov     [rsp+580h+dwFlags], r15d
0x18004d98e  call    CreatePersistedRegistryKeyHelper
0x18004d993  mov     ebx, eax
0x18004d995  test    eax, eax
0x18004d997  jz      short loc_18004D9B0
0x18004d999  test    byte ptr cs:xmmword_1800AB5A0+1, dil
0x18004d9a0  jz      loc_18004DEAA
0x18004d9a6  mov     edx, 0D6h
0x18004d9ab  jmp     loc_18004DE96
0x18004d9b0  test    r14d, r14d
0x18004d9b3  jz      short loc_18004DA08
0x18004d9b5  lea     rax, [rsp+580h+var_518]
0x18004d9ba  mov     [rsp+580h+var_548], rax
0x18004d9bf  lea     r8, [rbp+480h+var_250]
0x18004d9c6  mov     dword ptr [rsp+580h+var_550], 1
0x18004d9ce  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18004d9d5  mov     [rsp+580h+pszFormat], r13
0x18004d9da  lea     rcx, aDnscache_0; "Dnscache"
0x18004d9e1  mov     [rsp+580h+dwFlags], r15d
0x18004d9e6  call    CreatePersistedRegistryKeyHelper
0x18004d9eb  mov     ebx, eax
0x18004d9ed  test    eax, eax
0x18004d9ef  jz      short loc_18004DA08
0x18004d9f1  test    byte ptr cs:xmmword_1800AB5A0+1, dil
0x18004d9f8  jz      loc_18004DEAA
0x18004d9fe  mov     edx, 0D7h
0x18004da03  jmp     loc_18004DE96
0x18004da08  mov     r13, [rsp+580h+hKey]
0x18004da0d  test    [rsi+8], dil
0x18004da11  jz      short loc_18004DA71
0x18004da13  mov     rdx, cs:lpValueName; lpValueName
  ... truncated ...
```
