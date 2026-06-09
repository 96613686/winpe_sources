# DisableDynamicDnsRegistration

- ea: `0x18008a94c`
- end: `0x18008c0e8`
- name: `DisableDynamicDnsRegistration`
- size: `6044`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800881d4`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ed84`
- `0x18000ff94`
- `0x180010510`
- `0x18001e090`
- `0x180030af8`
- `0x180030bd4`
- `0x18008a94c`
- `0x1800a137c`
- `0x1800a1458`
- `0x1800a1694`
- `0x1800a1744`
- `0x18016fd6c`
- `0x180170a38`
- `0x180180c50`
- `0x180181ae0`
- `0x180181bf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008beb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008beb6`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18008bae7`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18008bae7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18008bb1b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18008bb1b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18008b608`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18008b608`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18008b5ed`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18008b5ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008aced`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008b4d4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008aced`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008b4d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008ac8d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008bed3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008bee2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008bef1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008ac8d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008bed3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008bee2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008bef1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008ae55`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008b0a1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008ae55`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008b0a1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008aa33`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008aa33`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008acc1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008ad21`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008acc1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008ad21`

## string_xrefs

- `0x18008a97c`: `\system32\config\netlogon.dns`
- `0x18008a993`: `\system32\config\netlogon.dnb`
- `0x18008b4bb`: `SYSTEM\CurrentControlSet\Services\Tcpip\Parameters\DNSRegisteredAdapters`
- `0x18008a9a1`: `SYSTEM\CurrentControlSet\Services\Dnscache\Parameters`
- `0x18008a9c6`: `SYSTEM\CurrentControlSet\Services\Netlogon\Parameters`
- `0x18008a9eb`: `SYSTEM\CurrentControlSet\Services\Tcpip\Parameters`
- `0x18008a9f6`: `DisableDynamicUpdate`
- `0x18008a987`: `SYSTEM\CurrentControlSet\Services\NTDS\Parameters\PostCloningRestore`
- `0x18008ab0f`: `SYSTEM\CurrentControlSet\Services\NTDS\Parameters\PostCloningRestore`
- `0x18008abd3`: `SYSTEM\CurrentControlSet\Services\NTDS\Parameters\PostCloningRestore`
- `0x18008afcb`: `SYSTEM\CurrentControlSet\Services\NTDS\Parameters\PostCloningRestore`
- `0x18008abde`: `<create>`

## pseudocode

```c
__int64 DisableDynamicDnsRegistration()
{
  __int64 v0; // r13
  int v1; // edi
  unsigned int Key; // eax
  __int64 v3; // rsi
  BOOL v4; // r15d
  bool v5; // zf
  int v6; // eax
  LPOVERLAPPED v7; // r15
  unsigned __int64 v8; // r15
  const WCHAR *v9; // rdx
  const WCHAR *v10; // rdx
  LSTATUS v11; // r14d
  BOOL v12; // esi
  int v13; // r8d
  BOOL v14; // ecx
  unsigned int v15; // eax
  __int64 v16; // r14
  BOOL v17; // esi
  BOOL v18; // ecx
  LPOVERLAPPED v19; // rsi
  unsigned int *v20; // r12
  unsigned int v21; // eax
  __int64 v22; // r14
  BOOL v23; // esi
  int v24; // eax
  LPOVERLAPPED v25; // rsi
  BOOL v26; // esi
  BOOL v27; // ecx
  LPOVERLAPPED v28; // rsi
  BOOL v29; // esi
  int v30; // eax
  unsigned int v31; // eax
  BOOL v32; // esi
  int v33; // eax
  LPOVERLAPPED v34; // rsi
  BOOL v35; // r14d
  int v36; // eax
  LPOVERLAPPED v37; // r14
  BOOL v38; // r14d
  int v39; // eax
  unsigned int v40; // r12d
  int v41; // eax
  unsigned int v42; // eax
  BOOL v43; // r15d
  int v44; // eax
  LPOVERLAPPED v45; // r15
  BOOL v46; // r15d
  int v47; // eax
  LPOVERLAPPED v48; // r15
  BOOL v49; // r14d
  BOOL v50; // r15d
  __int64 v52; // [rsp+60h] [rbp-A0h] BYREF
  int v53; // [rsp+68h] [rbp-98h]
  DWORD Offset; // [rsp+6Ch] [rbp-94h]
  __int64 v55; // [rsp+70h] [rbp-90h]
  int v56; // [rsp+78h] [rbp-88h]
  int v57; // [rsp+7Ch] [rbp-84h]
  __int64 v58; // [rsp+80h] [rbp-80h]
  __int64 v59; // [rsp+88h] [rbp-78h]
  __int64 v60; // [rsp+90h] [rbp-70h]
  __int64 v61; // [rsp+98h] [rbp-68h]
  __int64 v62; // [rsp+A0h] [rbp-60h]
  int v63; // [rsp+A8h] [rbp-58h]
  __int64 v64; // [rsp+ACh] [rbp-54h]
  int v65; // [rsp+B4h] [rbp-4Ch]
  int *v66; // [rsp+B8h] [rbp-48h]
  BYTE Data[4]; // [rsp+C0h] [rbp-40h] BYREF
  DWORD cbData; // [rsp+C4h] [rbp-3Ch] BYREF
  DWORD Type; // [rsp+C8h] [rbp-38h] BYREF
  DWORD cchName; // [rsp+CCh] [rbp-34h] BYREF
  HKEY hKey; // [rsp+D0h] [rbp-30h] BYREF
  HKEY v72; // [rsp+D8h] [rbp-28h] BYREF
  HKEY phkResult[4]; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD v74[2]; // [rsp+100h] [rbp+0h] BYREF
  LPCWSTR lpSubKey; // [rsp+108h] [rbp+8h]
  LPCWSTR lpValueName; // [rsp+110h] [rbp+10h]
  int v77; // [rsp+118h] [rbp+18h]
  const wchar_t *v78; // [rsp+120h] [rbp+20h]
  const wchar_t *v79; // [rsp+128h] [rbp+28h]
  int v80; // [rsp+130h] [rbp+30h]
  const wchar_t *v81; // [rsp+138h] [rbp+38h]
  const wchar_t *v82; // [rsp+140h] [rbp+40h]
  int v83; // [rsp+150h] [rbp+50h] BYREF
  WCHAR *v84; // [rsp+158h] [rbp+58h]
  int v85; // [rsp+170h] [rbp+70h]
  WCHAR *v86; // [rsp+178h] [rbp+78h]
  __int64 v87; // [rsp+188h] [rbp+88h] BYREF
  int v88; // [rsp+190h] [rbp+90h]
  __int64 *v89; // [rsp+198h] [rbp+98h]
  __int64 v90; // [rsp+1A8h] [rbp+A8h] BYREF
  int v91; // [rsp+1B0h] [rbp+B0h]
  __int64 *v92; // [rsp+1B8h] [rbp+B8h]
  __int64 v93; // [rsp+1C8h] [rbp+C8h] BYREF
  int v94; // [rsp+1D0h] [rbp+D0h]
  _QWORD *v95; // [rsp+1D8h] [rbp+D8h]
  _QWORD v96[49]; // [rsp+1E8h] [rbp+E8h] BYREF
  WCHAR Name[64]; // [rsp+370h] [rbp+270h] BYREF
  WCHAR Buffer[264]; // [rsp+3F0h] [rbp+2F0h] BYREF
  wchar_t NewFileName[264]; // [rsp+600h] [rbp+500h] BYREF

  v0 = 0;
  phkResult[1] = (HKEY)L"\\system32\\config\\netlogon.dns";
  phkResult[2] = (HKEY)L"\\system32\\config\\netlogon.dnb";
  hKey = 0;
  lpSubKey = L"SYSTEM\\CurrentControlSet\\Services\\Dnscache\\Parameters";
  v1 = 1;
  phkResult[0] = 0;
  lpValueName = L"RegistrationEnabled";
  v72 = 0;
  v78 = L"SYSTEM\\CurrentControlSet\\Services\\Netlogon\\Parameters";
  cchName = 0;
  v79 = L"UseDynamicDns";
  v81 = L"SYSTEM\\CurrentControlSet\\Services\\Tcpip\\Parameters";
  v82 = L"DisableDynamicUpdate";
  cbData = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  v74[0] = 0;
  v77 = 0;
  v80 = 1;
  Key = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\NTDS\\Parameters\\PostCloningRestore",
          0,
          0,
          0,
          0x20007u,
          0,
          phkResult,
          0);
  v3 = Key;
  if ( !Key )
  {
    v8 = 0;
    while ( 1 )
    {
      if ( hKey )
      {
        RegCloseKey(hKey);
        hKey = 0;
      }
      v9 = (&lpValueName)[v8 / 8];
      cbData = 4;
      if ( !RegQueryValueExW(phkResult[0], v9, 0, &Type, Data, &cbData)
        || RegOpenKeyExW(HKEY_LOCAL_MACHINE, (&lpSubKey)[v8 / 8], 0, 0x20007u, &hKey) )
      {
        goto LABEL_127;
      }
      v10 = (&lpValueName)[v8 / 8];
      cbData = 4;
      v11 = RegQueryValueExW(hKey, v10, 0, &Type, Data, &cbData);
      if ( (unsigned int)THStateCheckForTraceOverride()
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride()
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
      {
        v12 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride()
            || (unsigned int)ThStateCheckIfTraceToSecondProvier()
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
        v14 = (unsigned int)THStateCheckForTraceOverride()
           || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3);
        WPP_SF_Sdd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51188234,
          v13,
          3,
          v14,
          v12,
          98,
          &WPP_17642f48579431367eaf2b8a741d67ec_Traceguids,
          (__int64)(&lpValueName)[v8 / 8],
          v11,
          Type);
      }
      if ( v11 )
      {
        *(_DWORD *)Data = 0;
      }
      else if ( Type != 4 )
      {
        goto LABEL_78;
      }
      v15 = RegSetValueExW(phkResult[0], (&lpValueName)[v8 / 8], 0, 4 - (v11 != 0), Data, 4u);
      v16 = v15;
      if ( v15 )
      {
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
          || (unsigned int)THStateCheckForTraceOverride()
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride()
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
        {
          v17 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride()
              || (unsigned int)ThStateCheckIfTraceToSecondProvier()
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
          v18 = (unsigned int)THStateCheckForTraceOverride()
             || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3);
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51188259,
            3,
            3,
            v18,
            v17,
            99,
            &WPP_17642f48579431367eaf2b8a741d67ec_Traceguids,
            (__int64)(&lpValueName)[v8 / 8],
            v16);
        }
        v19 = gpDsEventConfig;
        if ( gpDsEventConfig )
        {
          if ( (gpDsEventConfig[3].OffsetHigh & 0x80000000) != 0
            && (!HIDWORD(gpDsEventConfig->Internal) || !(unsigned int)DoLogOverride(781, 0)) )
          {
            if ( !(unsigned int)DoLogMsgOverride(3221227664LL) )
              goto LABEL_78;
            v19 = gpDsEventConfig;
          }
          v53 = -1073739632;
          v55 = 0;
          v61 = 0;
          v64 = 0;
          v65 = 0;
          Offset = v19[3].Offset;
          v66 = &v83;
          v84 = (WCHAR *)L"SYSTEM\\CurrentControlSet\\Services\\NTDS\\Parameters\\PostCloningRestore";
          v86 = (WCHAR *)(&lpValueName)[v8 / 8];
          v90 = *(unsigned int *)Data;
          v89 = &v90;
          v93 = v16;
          v96[0] = v16;
          v91 = 5;
          v52 = 5;
          v95 = v96;
          v56 = 0;
          v57 = 1;
          v83 = 1;
          v85 = 1;
          v88 = 4;
          v92 = &v93;
          v94 = 10;
          v60 = 0;
          v59 = 781;
          v58 = 1;
          v62 = 0;
          v63 = 0;
          DoLogEventAndTrace(&v52);
        }
      }
LABEL_78:
      v20 = &v74[v8 / 4];
      v21 = RegSetValueExW(hKey, (&lpValueName)[v8 / 8], 0, 4u, (const BYTE *)&v74[v8 / 4], 4u);
      v22 = v21;
      if ( v21 )
      {
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
          || (unsigned int)THStateCheckForTraceOverride()
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride()
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
        {
          v26 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride()
              || (unsigned int)ThStateCheckIfTraceToSecondProvier()
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
          v27 = (unsigned int)THStateCheckForTraceOverride()
             || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3);
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51188296,
            3,
            3,
            v27,
            v26,
            101,
            &WPP_17642f48579431367eaf2b8a741d67ec_Traceguids,
            (__int64)(&lpValueName)[v8 / 8],
            v22);
        }
        v28 = gpDsEventConfig;
        if ( !gpDsEventConfig )
          goto LABEL_127;
        if ( (gpDsEventConfig[3].OffsetHigh & 0x80000000) == 0
          || HIDWORD(gpDsEventConfig->Internal) && (unsigned int)DoLogOverride(781, 0) )
        {
          goto LABEL_126;
        }
        if ( (unsigned int)DoLogMsgOverride(3221227664LL) )
        {
          v28 = gpDsEventConfig;
LABEL_126:
          v53 = -1073739632;
          v55 = 0;
          v61 = 0;
          v64 = 0;
          v65 = 0;
          Offset = v28[3].Offset;
          v66 = &v83;
          v84 = (WCHAR *)(&lpSubKey)[v8 / 8];
          v86 = (WCHAR *)(&lpValueName)[v8 / 8];
          v90 = *v20;
          v89 = &v90;
          v93 = v22;
          v96[0] = v22;
          v92 = &v93;
          v95 = v96;
          v56 = 0;
          v57 = 1;
          v83 = 1;
          v85 = 1;
          v88 = 4;
          v91 = 5;
          v94 = 10;
          v52 = 5;
          v60 = 0;
          v59 = 781;
          v58 = 1;
          v62 = 0;
          v63 = 0;
          DoLogEventAndTrace(&v52);
        }
      }
      else
      {
        if ( (unsigned int)THStateCheckForTraceOverride()
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride()
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
        {
          v23 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride()
              || (unsigned int)ThStateCheckIfTraceToSecondProvier()
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
          if ( (unsigned int)THStateCheckForTraceOverride()
            || (v24 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)) != 0 )
          {
            v24 = 1;
          }
          WPP_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51188283,
            4,
            3,
            v24,
            v23,
            100,
            &WPP_17642f48579431367eaf2b8a741d67ec_Traceguids);
        }
        v25 = gpDsEventConfig;
        if ( !gpDsEventConfig )
          goto LABEL_127;
        if ( (gpDsEventConfig[3].OffsetHigh & 0x80000000) == 0
          || HIDWORD(gpDsEventConfig->Internal) && (unsigned int)DoLogOverride(781, 0) )
        {
          goto LABEL_101;
        }
        if ( (unsigned int)DoLogMsgOverride(1073744015) )
        {
          v25 = gpDsEventConfig;
LABEL_101:
          v53 = 1073744015;
          v55 = 0;
          v61 = 0;
          v64 = 0;
          v65 = 0;
          Offset = v25[3].Offset;
          v66 = &v83;
          v84 = (WCHAR *)(&lpSubKey)[v8 / 8];
          v86 = (WCHAR *)(&lpValueName)[v8 / 8];
          v90 = *v20;
          v89 = &v90;
          v56 = 0;
          v57 = 1;
          v83 = 1;
          v85 = 1;
          v88 = 4;
          v52 = 3;
          v60 = 0;
          v59 = 781;
          v58 = 1;
          v62 = 0;
          v63 = 0;
          DoLogEventAndTrace(&v52);
        }
      }
LABEL_127:
      ++v0;
      v8 += 24LL;
      if ( v0 == 3 )
      {
        LODWORD(v3) = RegOpenKeyExW(
                        HKEY_LOCAL_MACHINE,
                        L"SYSTEM\\CurrentControlSet\\Services\\Tcpip\\Parameters\\DNSRegisteredAdapters",
                        0,
                        0x10009u,
                        &v72);
        if ( (_DWORD)v3 )
        {
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
            || (unsigned int)THStateCheckForTraceOverride()
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride()
             || (unsigned int)ThStateCheckIfTraceToSecondProvier()
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
          {
            v38 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride()
                || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
            if ( (unsigned int)THStateCheckForTraceOverride()
              || (v5 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3) == 0, v39 = 0, !v5) )
            {
              v39 = 1;
            }
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              51188398,
              3,
              3,
              v39,
              v38,
              105,
              &WPP_17642f48579431367eaf2b8a741d67ec_Traceguids,
              (__int64)L"SYSTEM\\CurrentControlSet\\Services\\Tcpip\\Parameters\\DNSRegisteredAdapters",
              v3);
          }
          goto LABEL_211;
        }
        if ( (unsigned int)THStateCheckForTraceOverride()
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride()
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
        {
          v29 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride()
              || (unsigned int)ThStateCheckIfTraceToSecondProvier()
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
          if ( (unsigned int)THStateCheckForTraceOverride()
            || (v5 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3) == 0, v30 = 0, !v5) )
          {
            v30 = 1;
          }
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51188329,
            4,
            3,
            v30,
            v29,
            102,
            &WPP_17642f48579431367eaf2b8a741d67ec_Traceguids,
            (__int64)L"SYSTEM\\CurrentControlSet\\Services\\Tcpip\\Parameters\\DNSRegisteredAdapters");
        }
        while ( 1 )
        {
          do
          {
LABEL_145:
            cchName = 64;
            LODWORD(v3) = RegEnumKeyExW(v72, 0, Name, &cchName, 0, 0, 0, 0);
            if ( (_DWORD)v3 )
              goto LABEL_211;
            v31 = RegDeleteTreeW(v72, Name);
            v3 = v31;
            if ( v31 )
            {
              if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
                || (unsigned int)THStateCheckForTraceOverride()
                || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
                || gfTraceToSecondProvider
                && ((unsigned int)THStateCheckForTraceOverride()
                 || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                 && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
              {
                v35 = gfTraceToSecondProvider
                   && ((unsigned int)THStateCheckForTraceOverride()
                    || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                    && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
                if ( (unsigned int)THStateCheckForTraceOverride()
                  || (v5 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3) == 0, v36 = 0, !v5) )
                {
                  v36 = 1;
                }
                WPP_SF_SSd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v36,
                  v35,
                  104,
                  &WPP_17642f48579431367eaf2b8a741d67ec_Traceguids,
                  (__int64)L"SYSTEM\\CurrentControlSet\\Services\\Tcpip\\Parameters\\DNSRegisteredAdapters",
                  (__int64)Name,
                  v3);
              }
              v37 = gpDsEventConfig;
              if ( gpDsEventConfig )
              {
                if ( (gpDsEventConfig[3].OffsetHigh & 0x80000000) == 0
                  || HIDWORD(gpDsEventConfig->Internal) && (unsigned int)DoLogOverride(781, 0) )
                {
LABEL_193:
                  v53 = -1073739632;
                  v55 = 0;
                  v61 = 0;
                  v64 = 0;
                  v65 = 0;
                  Offset = v37[3].Offset;
                  v66 = &v83;
                  v86 = Name;
                  v89 = &v90;
                  v93 = v3;
                  v96[0] = v3;
                  v92 = &v93;
                  v95 = v96;
                  v56 = 0;
                  v57 = 1;
                  v83 = 1;
                  v84 = (WCHAR *)L"SYSTEM\\CurrentControlSet\\Services\\Tcpip\\Parameters\\DNSRegisteredAdapters";
                  v85 = 1;
                  v88 = 4;
                  v90 = 0;
                  v91 = 5;
                  v94 = 10;
                  v52 = 5;
                  v60 = 0;
                  v59 = 781;
                  v58 = 1;
                  v62 = 0;
                  v63 = 0;
                  DoLogEventAndTrace(&v52);
                }
                else if ( (unsigned int)DoLogMsgOverride(3221227664LL) )
                {
                  v37 = gpDsEventConfig;
                  goto LABEL_193;
                }
              }
LABEL_211:
              v40 = 0;
              while ( 2 )
              {
                if ( v40 >= 2 )
                  goto LABEL_268;
                cchName = GetWindowsDirectoryW(Buffer, 0x105u);
                if ( !cchName )
                {
                  LODWORD(v3) = GetLastError();
                  goto LABEL_268;
                }
                v41 = AddFilePathName(Buffer);
                if ( v41 < 0 )
                {
                  LODWORD(v3) = (unsigned __int16)v41;
                  goto LABEL_268;
                }
                LODWORD(v3) = GetFileAttributesW(Buffer);
                if ( (_DWORD)v3 == -1 )
                  goto LABEL_265;
                v42 = RenameFileByInsertingCurrentTime(Buffer, NewFileName);
                v3 = v42;
                if ( v42 )
                {
                  if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
                    || (unsigned int)THStateCheckForTraceOverride()
                    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
                    || gfTraceToSecondProvider
                    && ((unsigned int)THStateCheckForTraceOverride()
                     || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
                  {
                    v46 = gfTraceToSecondProvider
                       && ((unsigned int)THStateCheckForTraceOverride()
                        || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
                    if ( (unsigned int)THStateCheckForTraceOverride()
                      || (v5 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3) == 0, v47 = 0, !v5) )
                    {
                      v47 = 1;
                    }
                    WPP_SF__ATTRTYP_LOG_(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      51188448,
                      3,
                      3,
                      v47,
                      v46,
                      107,
                      (__int64)&WPP_17642f48579431367eaf2b8a741d67ec_Traceguids);
                  }
                  v48 = gpDsEventConfig;
                  if ( !gpDsEventConfig )
                    goto LABEL_265;
                  if ( (gpDsEventConfig[3].OffsetHigh & 0x80000000) != 0
                    && (!HIDWORD(gpDsEventConfig->Internal) || !(unsigned int)DoLogOverride(781, 0)) )
                  {
                    if ( !(unsigned int)DoLogMsgOverride(3221227649LL) )
                      goto LABEL_265;
                    v48 = gpDsEventConfig;
                  }
                  v53 = -1073739647;
                  v55 = 0;
                  v61 = 0;
                  v64 = 0;
                  v65 = 0;
                  Offset = v48[3].Offset;
                  v66 = &v83;
                  v84 = Buffer;
                  v87 = v3;
                  v90 = v3;
                  v89 = &v90;
                  v85 = 5;
                  v86 = (WCHAR *)&v87;
                  v88 = 10;
                  v52 = 3;
                }
                else
                {
                  if ( (unsigned int)THStateCheckForTraceOverride()
                    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
                    || gfTraceToSecondProvider
                    && ((unsigned int)THStateCheckForTraceOverride()
                     || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
                  {
                    v43 = gfTraceToSecondProvider
                       && ((unsigned int)THStateCheckForTraceOverride()
                        || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
                    if ( (unsigned int)THStateCheckForTraceOverride()
                      || (v5 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3) == 0, v44 = 0, !v5) )
                    {
                      v44 = 1;
                    }
                    WPP_SF_SS(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      v44,
                      v43,
                      106,
                      &WPP_17642f48579431367eaf2b8a741d67ec_Traceguids,
                      (__int64)Buffer,
                      (__int64)NewFileName);
                  }
                  v45 = gpDsEventConfig;
                  if ( !gpDsEventConfig )
                    goto LABEL_265;
                  if ( (gpDsEventConfig[3].OffsetHigh & 0x80000000) != 0
                    && (!HIDWORD(gpDsEventConfig->Internal) || !(unsigned int)DoLogOverride(781, 0)) )
                  {
                    if ( (unsigned int)DoLogMsgOverride(1073744000) )
                    {
                      v45 = gpDsEventConfig;
                      goto LABEL_239;
                    }
LABEL_265:
                    ++v40;
                    continue;
                  }
LABEL_239:
                  v53 = 1073744000;
                  v55 = 0;
                  v61 = 0;
                  v64 = 0;
                  v65 = 0;
                  Offset = v45[3].Offset;
                  v66 = &v83;
                  v84 = Buffer;
                  v86 = NewFileName;
                  v85 = 1;
                  v52 = 2;
                }
                break;
              }
              v56 = 0;
              v57 = 1;
              v83 = 1;
              v60 = 0;
              v59 = 781;
              v58 = 1;
              v62 = 0;
              v63 = 0;
              DoLogEventAndTrace(&v52);
              goto LABEL_265;
            }
            if ( (unsigned int)THStateCheckForTraceOverride()
              || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
              || gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride()
               || (unsigned int)ThStateCheckIfTraceToSecondProvier()
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
            {
              v32 = gfTraceToSecondProvider
                 && ((unsigned int)THStateCheckForTraceOverride()
                  || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                  && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
              if ( (unsigned int)THStateCheckForTraceOverride()
                || (v5 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3) == 0, v33 = 0, !v5) )
              {
                v33 = 1;
              }
              WPP_SF_SS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v33,
                v32,
                103,
                &WPP_17642f48579431367eaf2b8a741d67ec_Traceguids,
                (__int64)L"SYSTEM\\CurrentControlSet\\Services\\Tcpip\\Parameters\\DNSRegisteredAdapters",
                (__int64)Name);
            }
            v34 = gpDsEventConfig;
          }
          while ( !gpDsEventConfig );
          if ( (gpDsEventConfig[3].OffsetHigh & 0x80000000) != 0
            && (!HIDWORD(gpDsEventConfig->Internal) || !(unsigned int)DoLogOverride(781, 0)) )
          {
            if ( !(unsigned int)DoLogMsgOverride(1073744015) )
              goto LABEL_145;
            v34 = gpDsEventConfig;
          }
          v53 = 1073744015;
          v55 = 0;
          v61 = 0;
          v64 = 0;
          v65 = 0;
          Offset = v34[3].Offset;
          v66 = &v83;
          v86 = Name;
          v89 = &v90;
          v56 = 0;
          v57 = 1;
          v83 = 1;
          v84 = (WCHAR *)L"SYSTEM\\CurrentControlSet\\Services\\Tcpip\\Parameters\\DNSRegisteredAdapters";
          v85 = 1;
          v88 = 4;
          v90 = 0;
          v52 = 3;
          v60 = 0;
          v59 = 781;
          v58 = 1;
          v62 = 0;
          v63 = 0;
          DoLogEventAndTrace(&v52);
        }
      }
    }
  }
  if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
    || (unsigned int)THStateCheckForTraceOverride()
    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
    || gfTraceToSecondProvider
    && ((unsigned int)THStateCheckForTraceOverride()
     || (unsigned int)ThStateCheckIfTraceToSecondProvier()
     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
  {
    v4 = gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride()
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
    if ( (unsigned int)THStateCheckForTraceOverride()
      || (v5 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) == 0, v6 = 0, !v5) )
    {
      v6 = 1;
    }
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      51188167,
      2,
      3,
      v6,
      v4,
      97,
      &WPP_17642f48579431367eaf2b8a741d67ec_Traceguids,
      (__int64)L"SYSTEM\\CurrentControlSet\\Services\\NTDS\\Parameters\\PostCloningRestore",
      v3);
  }
  v7 = gpDsEventConfig;
  if ( gpDsEventConfig )
  {
    if ( (gpDsEventConfig[3].OffsetHigh & 0x80000000) != 0
      && (!HIDWORD(gpDsEventConfig->Internal) || !(unsigned int)DoLogOverride(781, 0)) )
    {
      if ( !(unsigned int)DoLogMsgOverride(3221227664LL) )
        goto LABEL_268;
      v7 = gpDsEventConfig;
    }
    v59 = 781;
    v55 = 0;
    v61 = 0;
    v64 = 0;
    v65 = 0;
    Offset = v7[3].Offset;
    v66 = &v83;
    v84 = (WCHAR *)L"SYSTEM\\CurrentControlSet\\Services\\NTDS\\Parameters\\PostCloningRestore";
    v86 = L"<create>";
    v89 = &v90;
    v93 = v3;
    v96[0] = v3;
    v91 = 5;
    v52 = 5;
    v95 = v96;
    v53 = -1073739632;
    v56 = 0;
    v57 = 1;
    v83 = 1;
    v85 = 1;
    v88 = 4;
    v90 = 0;
    v92 = &v93;
    v94 = 10;
    v60 = 0;
    v58 = 1;
    v62 = 0;
    v63 = 0;
    DoLogEventAndTrace(&v52);
  }
LABEL_268:
  if ( v72 )
    RegCloseKey(v72);
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult[0] )
    RegCloseKey(phkResult[0]);
  if ( (_DWORD)v3 )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride()
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride()
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
    {
      v50 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride()
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
      if ( !(unsigned int)THStateCheckForTraceOverride() && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
        v1 = 0;
      WPP_SF__ATTRTYP_LOG_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        51188480,
        2,
        3,
        v1,
        v50,
        109,
        (__int64)&WPP_17642f48579431367eaf2b8a741d67ec_Traceguids);
    }
  }
  else if ( (unsigned int)THStateCheckForTraceOverride()
         || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
         || gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride()
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
  {
    v49 = gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride()
        || (unsigned int)ThStateCheckIfTraceToSecondProvier()
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
    if ( !(unsigned int)THStateCheckForTraceOverride() && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3) )
      v1 = 0;
    WPP_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      51188477,
      4,
      3,
      v1,
      v49,
      108,
      &WPP_17642f48579431367eaf2b8a741d67ec_Traceguids);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18008a94c  push    rbp
0x18008a94e  push    rbx
0x18008a94f  push    rsi
0x18008a950  push    rdi
0x18008a951  push    r12
0x18008a953  push    r13
0x18008a955  push    r14
0x18008a957  push    r15
0x18008a959  lea     rbp, [rsp-728h]
0x18008a961  sub     rsp, 828h
0x18008a968  mov     rax, cs:__security_cookie
0x18008a96f  xor     rax, rsp
0x18008a972  mov     [rbp+760h+var_50], rax
0x18008a979  xor     r13d, r13d
0x18008a97c  lea     rax, aSystem32Config_1; "\\system32\\config\\netlogon.dns"
0x18008a983  mov     [rbp+760h+var_778], rax
0x18008a987  lea     rdx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Services\\NT"...
0x18008a98e  mov     [rsp+860h+lpdwDisposition], r13; lpdwDisposition
0x18008a993  lea     rax, aSystem32Config; "\\system32\\config\\netlogon.dnb"
0x18008a99a  mov     [rbp+760h+var_770], rax
0x18008a99e  xor     r9d, r9d; lpClass
0x18008a9a1  lea     rax, aSystemCurrentc_15; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18008a9a8  mov     [rbp+760h+hKey], r13
0x18008a9ac  mov     [rbp+760h+lpSubKey], rax
0x18008a9b0  lea     edi, [r13+1]
0x18008a9b4  lea     rax, aRegistrationen; "RegistrationEnabled"
0x18008a9bb  mov     [rbp+760h+var_780], r13
0x18008a9bf  mov     [rbp+760h+lpValueName], rax
0x18008a9c3  xor     r8d, r8d; Reserved
0x18008a9c6  lea     rax, aSystemCurrentc_17; "SYSTEM\\CurrentControlSet\\Services\\Ne"...
0x18008a9cd  mov     [rbp+760h+var_788], r13
0x18008a9d1  mov     [rbp+760h+var_740], rax
0x18008a9d5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008a9dc  lea     rax, aUsedynamicdns; "UseDynamicDns"
0x18008a9e3  mov     [rbp+760h+cchName], r13d
0x18008a9e7  mov     [rbp+760h+var_738], rax
0x18008a9eb  lea     rax, aSystemCurrentc_11; "SYSTEM\\CurrentControlSet\\Services\\Tc"...
0x18008a9f2  mov     [rbp+760h+var_728], rax
0x18008a9f6  lea     rax, aDisabledynamic; "DisableDynamicUpdate"
0x18008a9fd  mov     [rbp+760h+var_720], rax
0x18008aa01  lea     rax, [rbp+760h+var_780]
0x18008aa05  mov     [rsp+860h+phkResult], rax; phkResult
0x18008aa0a  mov     [rsp+860h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18008aa0f  mov     [rsp+860h+samDesired], 20007h; samDesired
0x18008aa17  mov     [rsp+860h+dwOptions], r13d; dwOptions
0x18008aa1c  mov     [rbp+760h+cbData], r13d
0x18008aa20  mov     [rbp+760h+Type], r13d
0x18008aa24  mov     dword ptr [rbp+760h+Data], r13d
0x18008aa28  mov     [rbp+760h+var_760], r13d
0x18008aa2c  mov     [rbp+760h+var_748], r13d
0x18008aa30  mov     [rbp+760h+var_730], edi
0x18008aa33  call    cs:__imp_RegCreateKeyExW
0x18008aa39  mov     esi, eax
0x18008aa3b  lea     r14d, [r13+4]
0x18008aa3f  test    eax, eax
0x18008aa41  jz      loc_18008AC76
0x18008aa47  lea     r14d, [r13+2]
0x18008aa4b  mov     ecx, r14d
0x18008aa4e  call    IncrementWPPPerfCountersForLevel
0x18008aa53  lea     r12, WPP_17642f48579431367eaf2b8a741d67ec_Traceguids
0x18008aa5a  lea     ebx, [rdi+2]
0x18008aa5d  test    eax, eax
0x18008aa5f  jnz     short loc_18008AAB4
0x18008aa61  call    THStateCheckForTraceOverride
0x18008aa66  test    eax, eax
0x18008aa68  jnz     short loc_18008AAB4
0x18008aa6a  mov     r8d, ebx
0x18008aa6d  mov     edx, r14d
0x18008aa70  xor     ecx, ecx
0x18008aa72  call    CheckWPPLevelFlagsEnabledForProvider
0x18008aa77  test    eax, eax
0x18008aa79  jnz     short loc_18008AAB4
0x18008aa7b  mov     eax, cs:gfTraceToSecondProvider
0x18008aa81  test    eax, eax
0x18008aa83  jz      loc_18008AB48
0x18008aa89  call    THStateCheckForTraceOverride
0x18008aa8e  test    eax, eax
0x18008aa90  jnz     short loc_18008AAB4
0x18008aa92  call    ThStateCheckIfTraceToSecondProvier
0x18008aa97  test    eax, eax
0x18008aa99  jz      loc_18008AB48
0x18008aa9f  mov     r8d, ebx
0x18008aaa2  mov     edx, r14d
0x18008aaa5  mov     ecx, edi
0x18008aaa7  call    CheckWPPLevelFlagsEnabledForProvider
0x18008aaac  test    eax, eax
0x18008aaae  jz      loc_18008AB48
0x18008aab4  mov     eax, cs:gfTraceToSecondProvider
0x18008aaba  test    eax, eax
0x18008aabc  jz      short loc_18008AAE6
0x18008aabe  call    THStateCheckForTraceOverride
0x18008aac3  test    eax, eax
0x18008aac5  jnz     short loc_18008AAE1
0x18008aac7  call    ThStateCheckIfTraceToSecondProvier
0x18008aacc  test    eax, eax
0x18008aace  jz      short loc_18008AAE6
0x18008aad0  mov     r8d, ebx
0x18008aad3  mov     edx, r14d
0x18008aad6  mov     ecx, edi
0x18008aad8  call    CheckWPPLevelFlagsEnabledForProvider
0x18008aadd  test    eax, eax
0x18008aadf  jz      short loc_18008AAE6
0x18008aae1  mov     r15d, edi
0x18008aae4  jmp     short loc_18008AAE9
0x18008aae6  mov     r15d, r13d
0x18008aae9  call    THStateCheckForTraceOverride
0x18008aaee  test    eax, eax
0x18008aaf0  jnz     short loc_18008AB06
0x18008aaf2  mov     r8d, ebx
0x18008aaf5  mov     edx, r14d
0x18008aaf8  xor     ecx, ecx
0x18008aafa  call    CheckWPPLevelFlagsEnabledForProvider
0x18008aaff  test    eax, eax
0x18008ab01  mov     eax, r13d
0x18008ab04  jz      short loc_18008AB08
0x18008ab06  mov     eax, edi
0x18008ab08  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ab0f  lea     rdx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Services\\NT"...
0x18008ab16  mov     dword ptr [rsp+860h+var_818], esi; char
0x18008ab1a  mov     r9d, ebx; int
0x18008ab1d  mov     [rsp+860h+lpdwDisposition], rdx; __int64
0x18008ab22  mov     r8d, r14d; int
0x18008ab25  mov     [rsp+860h+phkResult], r12; LPCGUID
0x18008ab2a  mov     edx, 30D11C7h; int
0x18008ab2f  mov     rcx, [rcx+10h]; int
0x18008ab33  mov     word ptr [rsp+860h+lpSecurityAttributes], 61h ; 'a'; __int16
0x18008ab3a  mov     [rsp+860h+samDesired], r15d; int
0x18008ab3f  mov     [rsp+860h+dwOptions], eax; int
0x18008ab43  call    WPP_SF_Sd
0x18008ab48  mov     r15, cs:gpDsEventConfig
0x18008ab4f  test    r15, r15
0x18008ab52  jz      loc_18008BECA
0x18008ab58  xor     r8d, r8d
0x18008ab5b  mov     r13d, 30Dh
0x18008ab61  mov     r12d, 0C0000890h
0x18008ab67  cmp     [r15+74h], r8d
0x18008ab6b  jge     short loc_18008AB9E
0x18008ab6d  cmp     [r15+4], r8d
0x18008ab71  jz      short loc_18008AB84
0x18008ab73  xor     edx, edx
0x18008ab75  mov     ecx, r13d
0x18008ab78  call    DoLogOverride
0x18008ab7d  xor     r8d, r8d
0x18008ab80  test    eax, eax
0x18008ab82  jnz     short loc_18008AB9E
0x18008ab84  mov     ecx, r12d
0x18008ab87  call    DoLogMsgOverride
0x18008ab8c  xor     r8d, r8d
0x18008ab8f  test    eax, eax
0x18008ab91  jz      loc_18008BEC0
0x18008ab97  mov     r15, cs:gpDsEventConfig
0x18008ab9e  xor     eax, eax
0x18008aba0  mov     [rbp+760h+var_7D8], r13
0x18008aba4  mov     [rsp+860h+var_7F0], rax
0x18008aba9  lea     rdx, [rbp+760h+var_698]
0x18008abb0  mov     [rbp+760h+var_7C8], rax
0x18008abb4  mov     ecx, 5
0x18008abb9  mov     [rbp+760h+var_7B4], rax
0x18008abbd  xor     r13d, r13d
0x18008abc0  mov     [rbp+760h+var_7AC], eax
0x18008abc3  mov     eax, [r15+70h]
0x18008abc7  mov     [rsp+860h+var_7F4], eax
0x18008abcb  lea     rax, [rbp+760h+var_710]
0x18008abcf  mov     [rbp+760h+var_7A8], rax
0x18008abd3  lea     rax, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Services\\NT"...
0x18008abda  mov     [rbp+760h+var_708], rax
0x18008abde  lea     rax, aCreate; "<create>"
0x18008abe5  mov     [rbp+760h+var_6E8], rax
0x18008abe9  lea     rax, [rbp+760h+var_6B8]
0x18008abf0  mov     [rbp+760h+var_6C8], rax
0x18008abf7  mov     rax, rsi
0x18008abfa  mov     [rbp+760h+var_698], rax
0x18008ac01  mov     [rbp+760h+var_678], rax
0x18008ac08  lea     rax, [rbp+760h+var_678]
0x18008ac0f  mov     [rbp+760h+var_6B0], ecx
0x18008ac15  mov     [rsp+860h+var_800], rcx
0x18008ac1a  lea     rcx, [rsp+860h+var_800]
0x18008ac1f  mov     [rbp+760h+var_688], rax
0x18008ac26  mov     [rsp+860h+var_7F8], r12d
0x18008ac2b  mov     [rsp+860h+var_7E8], r8d
0x18008ac30  mov     [rsp+860h+var_7E4], edi
0x18008ac34  mov     [rbp+760h+var_710], edi
0x18008ac37  mov     [rbp+760h+var_6F0], edi
0x18008ac3a  mov     [rbp+760h+var_6D0], 4
0x18008ac44  mov     [rbp+760h+var_6B8], r8
0x18008ac4b  mov     [rbp+760h+var_6A8], rdx
0x18008ac52  mov     [rbp+760h+var_690], 0Ah
0x18008ac5c  mov     [rbp+760h+var_7D0], r8
0x18008ac60  mov     [rbp+760h+var_7E0], rdi
0x18008ac64  mov     [rbp+760h+var_7C0], r13
0x18008ac68  mov     [rbp+760h+var_7B8], r13d
0x18008ac6c  call    DoLogEventAndTrace
0x18008ac71  jmp     loc_18008BEC3
0x18008ac76  xor     r15d, r15d
0x18008ac79  lea     r12, WPP_17642f48579431367eaf2b8a741d67ec_Traceguids
0x18008ac80  lea     ebx, [r15+3]
0x18008ac84  mov     rcx, [rbp+760h+hKey]; hKey
0x18008ac88  test    rcx, rcx
0x18008ac8b  jz      short loc_18008AC9B
0x18008ac8d  call    cs:__imp_RegCloseKey
0x18008ac93  mov     [rbp+760h+hKey], 0
0x18008ac9b  mov     rdx, [rbp+r15+760h+lpValueName]; lpValueName
0x18008aca0  lea     rax, [rbp+760h+cbData]
0x18008aca4  mov     rcx, [rbp+760h+var_780]; hKey
0x18008aca8  lea     r9, [rbp+760h+Type]; lpType
0x18008acac  mov     qword ptr [rsp+860h+samDesired], rax; lpcbData
0x18008acb1  xor     r8d, r8d; lpReserved
0x18008acb4  lea     rax, [rbp+760h+Data]
0x18008acb8  mov     [rbp+760h+cbData], r14d
0x18008acbc  mov     qword ptr [rsp+860h+dwOptions], rax; lpData
0x18008acc1  call    cs:__imp_RegQueryValueExW
0x18008acc7  test    eax, eax
0x18008acc9  jz      loc_18008B4A1
0x18008accf  mov     rdx, [rbp+r15+760h+lpSubKey]; lpSubKey
0x18008acd4  lea     rax, [rbp+760h+hKey]
0x18008acd8  mov     r9d, 20007h; samDesired
0x18008acde  mov     qword ptr [rsp+860h+dwOptions], rax; phkResult
0x18008ace3  xor     r8d, r8d; ulOptions
0x18008ace6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008aced  call    cs:__imp_RegOpenKeyExW
0x18008acf3  test    eax, eax
0x18008acf5  jnz     loc_18008B4A1
0x18008acfb  mov     rdx, [rbp+r15+760h+lpValueName]; lpValueName
0x18008ad00  lea     rax, [rbp+760h+cbData]
0x18008ad04  mov     rcx, [rbp+760h+hKey]; hKey
0x18008ad08  lea     r9, [rbp+760h+Type]; lpType
0x18008ad0c  mov     qword ptr [rsp+860h+samDesired], rax; lpcbData
0x18008ad11  xor     r8d, r8d; lpReserved
0x18008ad14  lea     rax, [rbp+760h+Data]
0x18008ad18  mov     [rbp+760h+cbData], r14d
0x18008ad1c  mov     qword ptr [rsp+860h+dwOptions], rax; lpData
0x18008ad21  call    cs:__imp_RegQueryValueExW
0x18008ad27  mov     r14d, eax
0x18008ad2a  call    THStateCheckForTraceOverride
0x18008ad2f  test    eax, eax
0x18008ad31  jnz     short loc_18008AD7F
0x18008ad33  mov     r8d, ebx
0x18008ad36  lea     edx, [rax+4]
0x18008ad39  xor     ecx, ecx
0x18008ad3b  call    CheckWPPLevelFlagsEnabledForProvider
0x18008ad40  test    eax, eax
0x18008ad42  jnz     short loc_18008AD7F
0x18008ad44  mov     eax, cs:gfTraceToSecondProvider
0x18008ad4a  test    eax, eax
0x18008ad4c  jz      loc_18008AE16
0x18008ad52  call    THStateCheckForTraceOverride
0x18008ad57  test    eax, eax
0x18008ad59  jnz     short loc_18008AD7F
0x18008ad5b  call    ThStateCheckIfTraceToSecondProvier
0x18008ad60  test    eax, eax
0x18008ad62  jz      loc_18008AE16
0x18008ad68  mov     r8d, ebx
0x18008ad6b  mov     edx, 4
0x18008ad70  mov     ecx, edi
0x18008ad72  call    CheckWPPLevelFlagsEnabledForProvider
0x18008ad77  test    eax, eax
0x18008ad79  jz      loc_18008AE16
0x18008ad7f  mov     eax, cs:gfTraceToSecondProvider
0x18008ad85  test    eax, eax
0x18008ad87  jz      short loc_18008ADB2
0x18008ad89  call    THStateCheckForTraceOverride
0x18008ad8e  test    eax, eax
0x18008ad90  jnz     short loc_18008ADAE
0x18008ad92  call    ThStateCheckIfTraceToSecondProvier
0x18008ad97  test    eax, eax
0x18008ad99  jz      short loc_18008ADB2
0x18008ad9b  mov     r8d, ebx
0x18008ad9e  mov     edx, 4
0x18008ada3  mov     ecx, edi
0x18008ada5  call    CheckWPPLevelFlagsEnabledForProvider
0x18008adaa  test    eax, eax
0x18008adac  jz      short loc_18008ADB2
0x18008adae  mov     esi, edi
0x18008adb0  jmp     short loc_18008ADB4
0x18008adb2  xor     esi, esi
0x18008adb4  call    THStateCheckForTraceOverride
0x18008adb9  test    eax, eax
0x18008adbb  jnz     short loc_18008ADD2
0x18008adbd  mov     r8d, ebx
0x18008adc0  lea     edx, [rax+4]
0x18008adc3  xor     ecx, ecx
0x18008adc5  call    CheckWPPLevelFlagsEnabledForProvider
0x18008adca  test    eax, eax
0x18008adcc  jnz     short loc_18008ADD2
0x18008adce  xor     ecx, ecx
0x18008add0  jmp     short loc_18008ADD4
0x18008add2  mov     ecx, edi
0x18008add4  mov     eax, [rbp+760h+Type]
0x18008add7  mov     r9d, ebx; int
0x18008adda  mov     dword ptr [rsp+860h+var_810], eax; char
0x18008adde  mov     edx, 30D120Ah; int
0x18008ade3  mov     rax, [rbp+r15+760h+lpValueName]
0x18008ade8  mov     dword ptr [rsp+860h+var_818], r14d; char
0x18008aded  mov     [rsp+860h+lpdwDisposition], rax; __int64
0x18008adf2  mov     [rsp+860h+phkResult], r12; LPCGUID
0x18008adf7  mov     word ptr [rsp+860h+lpSecurityAttributes], 62h ; 'b'; __int16
0x18008adfe  mov     [rsp+860h+samDesired], esi; int
0x18008ae02  mov     [rsp+860h+dwOptions], ecx; int
0x18008ae06  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ae0d  mov     rcx, [rcx+10h]; int
  ... truncated ...
```
