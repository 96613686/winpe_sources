# ModifyEntryListInRegistry

- ea: `0x180040a68`
- end: `0x180042c65`
- name: `ModifyEntryListInRegistry`
- size: `8701`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180005af0`

## callees

- `0x180006514`
- `0x18000b0f4`
- `0x180015f3c`
- `0x1800300ec`
- `0x180040a68`
- `0x18004e580`
- `0x18004e984`
- `0x18007e5f0`
- `0x1800da068`
- `0x1800da2bc`
- `0x1800da370`
- `0x1800da4fc`
- `0x1800da778`
- `0x1800da7ec`
- `0x1800dbed8`
- `0x1800dbefc`
- `0x1800dbf74`
- `0x1800dc6f0`
- `0x1800dc7dc`
- `0x1800dc948`
- `0x1800dcb24`
- `0x1800dcbd4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180040c82`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180040c82`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180040c5a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180040cd7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18004219d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180042208`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180040c5a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180040cd7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18004219d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180042208`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004229b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800422ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800422bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800422f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042345`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042a7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042aed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004229b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800422ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800422bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800422f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042345`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042a7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042aed`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180040cea`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004221b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180040cea`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004221b`
- `rtutils!TracePrintfExA` at `0x180040b65`
- `rtutils!TracePrintfExA` at `0x180042c0c`
- `rtutils!TracePrintfExA` at `0x180040b65`
- `rtutils!TracePrintfExA` at `0x180042c0c`

## string_xrefs

- `0x180041cf6`: `ApnInfoCompression`
- `0x180040fed`: `CustomDialDll`
- `0x180041d38`: `DeviceComplianceSsoEnabled`
- `0x1800412d5`: `ShowMonitorIconInTaskBar`
- `0x180040f48`: `RedialAttempts`
- `0x180040e61`: `LcpExtensions`
- `0x180041203`: `PreferredCompression`
- `0x180041d59`: `DeviceComplianceSsoEku`
- `0x180040fab`: `RedialOnLinkFailure`
- `0x180041cb4`: `ApnInfoAccessPoint`
- `0x180041d17`: `DeviceComplianceEnabled`
- `0x18004123f`: `PreferredMdmProtocol`
- `0x180040ea3`: `SwCompression`
- `0x180041d7a`: `DeviceComplianceSsoIssuer`
- `0x1800411e5`: `PreferredProtocol`
- `0x18004102f`: `CustomRasDialDll`
- `0x180040e40`: `ExcludedProtocols`
- `0x180040ec4`: `NegotiateMultilinkAlways`
- `0x1800413a7`: `IpHeaderCompression`
- `0x180041c30`: `SecurityDescriptor`
- `0x180041ed0`: `PowershellCreatedProfile`
- `0x180042121`: `PluginStorage`
- `0x1800417d6`: `ImsConfig`
- `0x18004187b`: `CacheCredentials`
- `0x180041050`: `ForceSecureCompartment`
- `0x180041fab`: `AutoConfigScript`
- `0x180042bfe`: `ModifyEntryListInRegistry: Number of connections written %d`

## pseudocode

```c
__int64 __fastcall ModifyEntryListInRegistry(__int64 a1, unsigned int *a2)
{
  _QWORD *v3; // rcx
  __int64 *v4; // rax
  unsigned int PathFromEntry; // ebx
  int v6; // r14d
  __int64 i; // r12
  __int64 v8; // rdi
  __int64 v9; // r8
  __int64 result; // rax
  const CHAR *v11; // rsi
  CHAR *v12; // rsi
  unsigned int v13; // eax
  unsigned int inserted; // eax
  __int64 v15; // r8
  __int64 v16; // r8
  const WCHAR *v17; // r8
  const WCHAR *v18; // r8
  const WCHAR *v19; // r8
  const WCHAR *v20; // r8
  const WCHAR *v21; // r8
  const WCHAR *v22; // r8
  const WCHAR *v23; // r8
  const WCHAR *v24; // r8
  __int64 v25; // r8
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // r8
  __int64 v31; // r8
  void *v32; // rcx
  CHAR *v33; // rsi
  unsigned int v34; // eax
  void *v35; // rcx
  CHAR *v36; // rsi
  __int64 v37; // r8
  __int64 v38; // r8
  __int64 v39; // r8
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 *v44; // rax
  __int64 j; // r15
  __int64 v46; // rsi
  CHAR *v47; // r14
  __int64 v48; // r8
  _QWORD *v49; // rcx
  __int64 v50; // rdx
  __int64 v51; // r9
  _QWORD *v52; // rcx
  __int64 v53; // rdx
  __int64 v54; // rdx
  unsigned int v55; // edi
  HKEY phkResult; // [rsp+50h] [rbp-19h] BYREF
  LPCWCH lpWideCharStr; // [rsp+58h] [rbp-11h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-9h]
  HKEY v59; // [rsp+68h] [rbp-1h] BYREF
  LPCSTR lpSubKey; // [rsp+70h] [rbp+7h]
  int v61; // [rsp+D0h] [rbp+67h]
  HKEY v63; // [rsp+E0h] [rbp+77h] BYREF
  HKEY v64; // [rsp+E8h] [rbp+7Fh] BYREF

  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids);
    v3 = WPP_GLOBAL_Control;
  }
  v4 = *(__int64 **)(a1 + 16);
  phkResult = 0;
  PathFromEntry = 0;
  v63 = 0;
  v6 = 0;
  v61 = 0;
  for ( i = *v4; ; i = *(_QWORD *)(i + 8) )
  {
    if ( !i )
    {
      if ( !PathFromEntry )
      {
        v55 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 16LL) - v6;
        if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x80) != 0 && *((_BYTE *)v3 + 25) >= 5u )
        {
          WPP_SF_d(v3[2], 177, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v55);
          v3 = WPP_GLOBAL_Control;
        }
        if ( g_dwTraceId != -1 )
        {
          TracePrintfExA(g_dwTraceId, 0xCu, "ModifyEntryListInRegistry: Number of connections written %d", v55);
          v3 = WPP_GLOBAL_Control;
        }
        *a2 = v55;
      }
      if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x80) != 0 && *((_BYTE *)v3 + 25) >= 6u )
      {
        v54 = 178;
        goto LABEL_430;
      }
      return PathFromEntry;
    }
    v8 = *(_QWORD *)(i + 16);
    if ( *(_DWORD *)(v8 + 532) || *(_DWORD *)(v8 + 540) )
      break;
LABEL_251:
    ;
  }
  if ( (*(_DWORD *)(a1 + 32) & 0x100) != 0 && *(_DWORD *)(v8 + 548) )
  {
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x80) != 0 && *((_BYTE *)v3 + 25) >= 5u )
      WPP_SF_S(v3[2], 135, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, *(_QWORD *)(v8 + 8));
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "Entry %S not written to hidden pbk", *(const wchar_t **)(v8 + 8));
    *(_DWORD *)(v8 + 532) = 0;
    *(_DWORD *)(v8 + 540) = 0;
    goto LABEL_250;
  }
  v9 = *(_QWORD *)(i + 16);
  lpWideCharStr = 0;
  lpSubKey = 0;
  hKey = 0;
  PathFromEntry = GetPathFromEntry(a1, &lpWideCharStr, v9);
  if ( PathFromEntry )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v54 = 136;
      goto LABEL_430;
    }
    return PathFromEntry;
  }
  PathFromEntry = RegistryPathConverter(lpWideCharStr);
  Free0(lpWideCharStr);
  result = 235;
  if ( PathFromEntry == 235 )
    return result;
  v11 = lpSubKey;
  if ( !(unsigned int)RegSetKeySecurityInfo(lpSubKey) )
    goto LABEL_25;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 137, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids);
LABEL_25:
    v3 = WPP_GLOBAL_Control;
  }
  if ( PathFromEntry )
  {
    if ( v3 != &WPP_GLOBAL_Control && *((char *)v3 + 28) < 0 && *((_BYTE *)v3 + 25) >= 2u )
    {
      v54 = 138;
      goto LABEL_430;
    }
    return PathFromEntry;
  }
  PathFromEntry = RegCreateKeyExA(hKey, v11, 0, 0, 0, 0x20206u, 0, &phkResult, 0);
  Free0(v11);
  if ( !PathFromEntry )
  {
    UpdateEntryTimeStamp(v8);
    RegDeleteTreeW(phkResult, *(LPCWSTR *)(v8 + 8));
    if ( !*(_DWORD *)(v8 + 540) )
    {
      v12 = (CHAR *)StrdupWtoA(*(LPCWCH *)(v8 + 8));
      if ( v12 )
      {
        v13 = RegCreateKeyExA(phkResult, v12, 0, 0, 0, 0x20206u, 0, &v63, 0);
        PathFromEntry = v13;
        if ( !v13 )
        {
          GlobalFree(v12);
          inserted = RegInsertLong(v63, "Encoding", 1);
          PathFromEntry = inserted;
          if ( inserted )
          {
            v49 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || *((char *)WPP_GLOBAL_Control + 28) >= 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_392;
            }
            v50 = 142;
          }
          else
          {
            inserted = RegInsertLong(v63, "PBVersion", 8);
            PathFromEntry = inserted;
            if ( inserted )
            {
              v49 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || *((char *)WPP_GLOBAL_Control + 28) >= 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_392;
              }
              v50 = 143;
            }
            else
            {
              inserted = RegInsertLong(v63, "Type", *(unsigned int *)(v8 + 24));
              PathFromEntry = inserted;
              if ( inserted )
              {
                v49 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || *((char *)WPP_GLOBAL_Control + 28) >= 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_392;
                }
                v50 = 144;
              }
              else
              {
                inserted = RegInsertFlag(v63, "AutoLogon", *(unsigned int *)(v8 + 176));
                PathFromEntry = inserted;
                if ( inserted )
                {
                  v49 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                    || *((char *)WPP_GLOBAL_Control + 28) >= 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    goto LABEL_392;
                  }
                  v50 = 145;
                }
                else
                {
                  inserted = RegInsertFlag(v63, "UseRasCredentials", *(unsigned int *)(v8 + 180));
                  PathFromEntry = inserted;
                  if ( inserted )
                  {
                    v49 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                      || *((char *)WPP_GLOBAL_Control + 28) >= 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                    {
                      goto LABEL_392;
                    }
                    v50 = 146;
                  }
                  else
                  {
                    inserted = RegInsertLong(v63, "LowDateTime", *(unsigned int *)(v8 + 16));
                    PathFromEntry = inserted;
                    if ( inserted )
                    {
                      v49 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                        || *((char *)WPP_GLOBAL_Control + 28) >= 0
                        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                      {
                        goto LABEL_392;
                      }
                      v50 = 147;
                    }
                    else
                    {
                      inserted = RegInsertLong(v63, "HighDateTime", *(unsigned int *)(v8 + 20));
                      PathFromEntry = inserted;
                      if ( inserted )
                      {
                        v49 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                          || *((char *)WPP_GLOBAL_Control + 28) >= 0
                          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                        {
                          goto LABEL_392;
                        }
                        v50 = 148;
                      }
                      else
                      {
                        inserted = RegInsertLong(v63, "DialParamsUID", *(unsigned int *)(v8 + 456));
                        PathFromEntry = inserted;
                        if ( inserted )
                        {
                          v49 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                            || *((char *)WPP_GLOBAL_Control + 28) >= 0
                            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                          {
                            goto LABEL_392;
                          }
                          v50 = 149;
                        }
                        else
                        {
                          v15 = *(_QWORD *)(v8 + 464);
                          if ( v15
                            && (inserted = RegInsertBinary(v63, "Guid", v15, 16), (PathFromEntry = inserted) != 0) )
                          {
                            v49 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                              || *((char *)WPP_GLOBAL_Control + 28) >= 0
                              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                            {
                              goto LABEL_392;
                            }
                            v50 = 150;
                          }
                          else
                          {
                            inserted = RegInsertLong(v63, "VpnStrategy", *(unsigned int *)(v8 + 168));
                            PathFromEntry = inserted;
                            if ( inserted )
                            {
                              v49 = WPP_GLOBAL_Control;
                              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                || *((char *)WPP_GLOBAL_Control + 28) >= 0
                                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                              {
                                goto LABEL_392;
                              }
                              v50 = 151;
                            }
                            else
                            {
                              inserted = RegInsertLong(v63, "ExcludedProtocols", *(unsigned int *)(v8 + 236));
                              PathFromEntry = inserted;
                              if ( inserted )
                              {
                                v49 = WPP_GLOBAL_Control;
                                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                  || *((char *)WPP_GLOBAL_Control + 28) >= 0
                                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                {
                                  goto LABEL_392;
                                }
                                v50 = 152;
                              }
                              else
                              {
                                inserted = RegInsertFlag(v63, "LcpExtensions", *(unsigned int *)(v8 + 240));
                                PathFromEntry = inserted;
                                if ( inserted )
                                {
                                  v49 = WPP_GLOBAL_Control;
                                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                    || *((char *)WPP_GLOBAL_Control + 28) >= 0
                                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                  {
                                    goto LABEL_392;
                                  }
                                  v50 = 153;
                                }
                                else
                                {
                                  inserted = RegInsertLong(v63, "DataEncryption", *(unsigned int *)(v8 + 172));
                                  PathFromEntry = inserted;
                                  if ( !inserted )
                                  {
                                    PathFromEntry = RegInsertFlag(v63, "SwCompression", *(unsigned int *)(v8 + 244));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(
                                                      v63,
                                                      "NegotiateMultilinkAlways",
                                                      *(unsigned int *)(v8 + 248));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(
                                                      v63,
                                                      "SkipDoubleDialDialog",
                                                      *(unsigned int *)(v8 + 252));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertLong(v63, "DialMode", *(unsigned int *)(v8 + 132));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertLong(v63, "OverridePref", *(unsigned int *)(v8 + 144));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertLong(v63, "RedialAttempts", *(unsigned int *)(v8 + 148));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertLong(v63, "RedialSeconds", *(unsigned int *)(v8 + 152));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertLong(
                                                      v63,
                                                      "IdleDisconnectSeconds",
                                                      *(unsigned int *)(v8 + 156));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(
                                                      v63,
                                                      "RedialOnLinkFailure",
                                                      *(unsigned int *)(v8 + 160));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertLong(v63, "CallbackMode", *(unsigned int *)(v8 + 420));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertString(v63, "CustomDialDll", *(_QWORD *)(v8 + 432));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertString(v63, "CustomDialFunc", *(_QWORD *)(v8 + 440));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertString(v63, "CustomRasDialDll", *(_QWORD *)(v8 + 448));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    *(_DWORD *)(v8 + 184) = 0;
                                    PathFromEntry = RegInsertFlag(v63, "ForceSecureCompartment", 0);
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(
                                                      v63,
                                                      "DisableIKENameEkuCheck",
                                                      *(unsigned int *)(v8 + 188));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(
                                                      v63,
                                                      "AuthenticateServer",
                                                      *(unsigned int *)(v8 + 424));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(v63, "ShareMsFilePrint", *(unsigned int *)(v8 + 256));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(v63, "BindMsNetClient", *(unsigned int *)(v8 + 260));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(v63, "SharedPhoneNumbers", *(unsigned int *)(v8 + 40));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(
                                                      v63,
                                                      "GlobalDeviceSettings",
                                                      *(unsigned int *)(v8 + 44));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertString(v63, "PrerequisiteEntry", *(_QWORD *)(v8 + 56));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertString(v63, "PrerequisitePbk", *(_QWORD *)(v8 + 64));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertString(v63, "PreferredPort", *(_QWORD *)(v8 + 72));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertString(v63, "PreferredDevice", *(_QWORD *)(v8 + 80));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertLong(v63, "PreferredBps", *(unsigned int *)(v8 + 88));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(v63, "PreferredHwFlow", *(unsigned int *)(v8 + 92));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(v63, "PreferredProtocol", *(unsigned int *)(v8 + 96));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(
                                                      v63,
                                                      "PreferredCompression",
                                                      *(unsigned int *)(v8 + 100));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertLong(v63, "PreferredSpeaker", *(unsigned int *)(v8 + 104));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertLong(
                                                      v63,
                                                      "PreferredMdmProtocol",
                                                      *(unsigned int *)(v8 + 108));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(v63, "PreviewUserPw", *(unsigned int *)(v8 + 116));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(v63, "PreviewDomain", *(unsigned int *)(v8 + 120));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(
                                                      v63,
                                                      "PreviewPhoneNumber",
                                                      *(unsigned int *)(v8 + 124));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(
                                                      v63,
                                                      "ShowDialingProgress",
                                                      *(unsigned int *)(v8 + 112));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(
                                                      v63,
                                                      "ShowMonitorIconInTaskBar",
                                                      *(unsigned int *)(v8 + 48));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertLong(v63, "CustomAuthKey", *(unsigned int *)(v8 + 192));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    v16 = *(_QWORD *)(v8 + 200);
                                    if ( v16 )
                                    {
                                      PathFromEntry = RegInsertBinary(
                                                        v63,
                                                        "CustomAuthData",
                                                        v16,
                                                        *(unsigned int *)(v8 + 208));
                                      if ( PathFromEntry )
                                        goto LABEL_392;
                                    }
                                    PathFromEntry = RegInsertLong(v63, "AuthRestrictions", *(unsigned int *)(v8 + 164));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(
                                                      v63,
                                                      "IpPrioritizeRemote",
                                                      *(unsigned int *)(v8 + 272));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertLong(v63, "IpInterfaceMetric", *(unsigned int *)(v8 + 352));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(
                                                      v63,
                                                      "IpHeaderCompression",
                                                      *(unsigned int *)(v8 + 276));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    v17 = L"0.0.0.0";
                                    if ( *(_QWORD *)(v8 + 280) )
                                      v17 = *(const WCHAR **)(v8 + 280);
                                    PathFromEntry = RegInsertString(v63, "IpAddress", v17);
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    v18 = L"0.0.0.0";
                                    if ( *(_QWORD *)(v8 + 288) )
                                      v18 = *(const WCHAR **)(v8 + 288);
                                    PathFromEntry = RegInsertString(v63, "IpDnsAddress", v18);
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    v19 = L"0.0.0.0";
                                    if ( *(_QWORD *)(v8 + 296) )
                                      v19 = *(const WCHAR **)(v8 + 296);
                                    PathFromEntry = RegInsertString(v63, "IpDns2Address", v19);
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    v20 = L"0.0.0.0";
                                    if ( *(_QWORD *)(v8 + 304) )
                                      v20 = *(const WCHAR **)(v8 + 304);
                                    PathFromEntry = RegInsertString(v63, "IpWinsAddress", v20);
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    v21 = L"0.0.0.0";
                                    if ( *(_QWORD *)(v8 + 312) )
                                      v21 = *(const WCHAR **)(v8 + 312);
                                    PathFromEntry = RegInsertString(v63, "IpWins2Address", v21);
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertLong(v63, "IpAssign", *(unsigned int *)(v8 + 320));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertLong(v63, "IpNameAssign", *(unsigned int *)(v8 + 324));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertLong(v63, "IpDnsFlags", *(unsigned int *)(v8 + 328));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertLong(v63, "IpNBTFlags", *(unsigned int *)(v8 + 332));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertLong(v63, "TcpWindowSize", *(unsigned int *)(v8 + 336));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertLong(v63, "UseFlags", *(unsigned int *)(v8 + 136));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertLong(v63, "IpSecFlags", *(unsigned int *)(v8 + 140));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertString(v63, "IpDnsSuffix", *(_QWORD *)(v8 + 344));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertLong(v63, "Ipv6Assign", *(unsigned int *)(v8 + 356));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    v22 = L"::";
                                    if ( *(_QWORD *)(v8 + 360) )
                                      v22 = *(const WCHAR **)(v8 + 360);
                                    PathFromEntry = RegInsertString(v63, "Ipv6Address", v22);
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertLong(v63, "Ipv6PrefixLength", *(unsigned int *)(v8 + 368));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(
                                                      v63,
                                                      "Ipv6PrioritizeRemote",
                                                      *(unsigned int *)(v8 + 372));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertLong(
                                                      v63,
                                                      "Ipv6InterfaceMetric",
                                                      *(unsigned int *)(v8 + 416));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertLong(v63, "Ipv6NameAssign", *(unsigned int *)(v8 + 376));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    v23 = L"::";
                                    if ( *(_QWORD *)(v8 + 384) )
                                      v23 = *(const WCHAR **)(v8 + 384);
                                    PathFromEntry = RegInsertString(v63, "Ipv6DnsAddress", v23);
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    v24 = L"::";
                                    if ( *(_QWORD *)(v8 + 392) )
                                      v24 = *(const WCHAR **)(v8 + 392);
                                    PathFromEntry = RegInsertString(v63, "Ipv6Dns2Address", v24);
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertBinary(v63, "Ipv6Prefix", v8 + 408, 8);
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertBinary(v63, "Ipv6InterfaceId", v8 + 400, 8);
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(
                                                      v63,
                                                      "DisableClassBasedDefaultRoute",
                                                      *(unsigned int *)(v8 + 544));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(v63, "DisableMobility", *(unsigned int *)(v8 + 488));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertLong(v63, "NetworkOutageTime", *(unsigned int *)(v8 + 492));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    if ( (unsigned int)RegInsertString(v63, "IDI", *(_QWORD *)(v8 + 496)) )
                                    {
                                      PathFromEntry = 1;
                                      v49 = WPP_GLOBAL_Control;
                                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                        && *((char *)WPP_GLOBAL_Control + 28) < 0
                                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                      {
                                        v50 = 155;
LABEL_341:
                                        v51 = 1;
LABEL_387:
                                        WPP_SF_d(v49[2], v50, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v51);
                                      }
LABEL_392:
                                      RegCloseKey(v63);
LABEL_402:
                                      RegCloseKey(phkResult);
                                      v3 = WPP_GLOBAL_Control;
                                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                        && *((char *)WPP_GLOBAL_Control + 28) < 0
                                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
                                      {
                                        v54 = 179;
LABEL_430:
                                        WPP_SF_d(
                                          v3[2],
                                          v54,
                                          WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids,
                                          PathFromEntry);
                                        return PathFromEntry;
                                      }
                                      return PathFromEntry;
                                    }
                                    if ( (unsigned int)RegInsertString(v63, "IDR", *(_QWORD *)(v8 + 504)) )
                                    {
                                      PathFromEntry = 1;
                                      v49 = WPP_GLOBAL_Control;
                                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                        && *((char *)WPP_GLOBAL_Control + 28) < 0
                                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                      {
                                        v50 = 156;
                                        goto LABEL_341;
                                      }
                                      goto LABEL_392;
                                    }
                                    inserted = RegInsertFlag(v63, "ImsConfig", *(unsigned int *)(v8 + 512));
                                    PathFromEntry = inserted;
                                    if ( inserted )
                                    {
                                      v49 = WPP_GLOBAL_Control;
                                      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                        || *((char *)WPP_GLOBAL_Control + 28) >= 0
                                        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                      {
                                        goto LABEL_392;
                                      }
                                      v50 = 157;
                                      goto LABEL_386;
                                    }
                                    inserted = RegInsertLong(v63, "IdiType", *(unsigned int *)(v8 + 516));
                                    PathFromEntry = inserted;
                                    if ( inserted )
                                    {
                                      v49 = WPP_GLOBAL_Control;
                                      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                        || *((char *)WPP_GLOBAL_Control + 28) >= 0
                                        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                      {
                                        goto LABEL_392;
                                      }
                                      v50 = 158;
                                      goto LABEL_386;
                                    }
                                    inserted = RegInsertLong(v63, "IdrType", *(unsigned int *)(v8 + 520));
                                    PathFromEntry = inserted;
                                    if ( inserted )
                                    {
                                      v49 = WPP_GLOBAL_Control;
                                      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                        || *((char *)WPP_GLOBAL_Control + 28) >= 0
                                        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                      {
                                        goto LABEL_392;
                                      }
                                      v50 = 159;
                                      goto LABEL_386;
                                    }
                                    PathFromEntry = RegInsertLong(v63, "ProvisionType", *(unsigned int *)(v8 + 548));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertString(v63, "PreSharedKey", *(_QWORD *)(v8 + 552));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(v63, "CacheCredentials", *(unsigned int *)(v8 + 128));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertLong(v63, "NumCustomPolicy", *(unsigned int *)(v8 + 596));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    v25 = *(_QWORD *)(v8 + 608);
                                    if ( v25 )
                                    {
                                      if ( *(_DWORD *)(v8 + 596) )
                                      {
                                        PathFromEntry = RegInsertBinary(
                                                          v63,
                                                          "CustomIPSecPolicies",
                                                          v25,
                                                          *(unsigned int *)(v8 + 600));
                                        if ( PathFromEntry )
                                          goto LABEL_392;
                                      }
                                    }
                                    PathFromEntry = RegInsertLong(v63, "NumEku", *(unsigned int *)(v8 + 616));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    v26 = *(_QWORD *)(v8 + 624);
                                    if ( v26 )
                                    {
                                      if ( *(_DWORD *)(v8 + 616) )
                                      {
                                        v27 = *(unsigned int *)(v8 + 620);
                                        if ( (_DWORD)v27 )
                                        {
                                          PathFromEntry = RegInsertBinary(v63, "CertificateEKU", v26, v27);
                                          if ( PathFromEntry )
                                            goto LABEL_392;
                                        }
                                      }
                                    }
                                    PathFromEntry = RegInsertFlag(
                                                      v63,
                                                      "UseMachineRootCert",
                                                      *(unsigned int *)(v8 + 632));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    if ( *(_DWORD *)(v8 + 632) == 1 )
                                    {
                                      v28 = *(_QWORD *)(v8 + 648);
                                      if ( v28 )
                                      {
                                        v29 = *(unsigned int *)(v8 + 640);
                                        if ( (_DWORD)v29 )
                                        {
                                          PathFromEntry = RegInsertBinary(v63, "RootCertificate", v28, v29);
                                          if ( PathFromEntry )
                                            goto LABEL_392;
                                        }
                                      }
                                    }
                                    inserted = RegInsertFlag(
                                                 v63,
                                                 "Disable_IKEv2_Fragmentation",
                                                 *(unsigned int *)(v8 + 524));
                                    PathFromEntry = inserted;
                                    if ( inserted )
                                    {
                                      v49 = WPP_GLOBAL_Control;
                                      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                        || *((char *)WPP_GLOBAL_Control + 28) >= 0
                                        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                      {
                                        goto LABEL_392;
                                      }
                                      v50 = 160;
                                      goto LABEL_386;
                                    }
                                    inserted = RegInsertFlag(v63, "PlumbIKEv2TSAsRoutes", *(unsigned int *)(v8 + 528));
                                    PathFromEntry = inserted;
                                    if ( inserted )
                                    {
                                      v49 = WPP_GLOBAL_Control;
                                      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                        || *((char *)WPP_GLOBAL_Control + 28) >= 0
                                        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                      {
                                        goto LABEL_392;
                                      }
                                      v50 = 161;
                                      goto LABEL_386;
                                    }
                                    PathFromEntry = RegInsertLong(v63, "NumServers", *(unsigned int *)(v8 + 656));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    if ( *(_QWORD *)(v8 + 664) )
                                    {
                                      if ( *(_DWORD *)(v8 + 656) )
                                      {
                                        inserted = RegCreateServerLists(v63);
                                        PathFromEntry = inserted;
                                        if ( inserted )
                                        {
                                          v49 = WPP_GLOBAL_Control;
                                          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                            || *((char *)WPP_GLOBAL_Control + 28) >= 0
                                            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                          {
                                            goto LABEL_392;
                                          }
                                          v50 = 162;
                                          goto LABEL_386;
                                        }
                                      }
                                    }
                                    inserted = RegInsertLong(v63, "RouteVersion", 1);
                                    PathFromEntry = inserted;
                                    if ( inserted )
                                    {
                                      v49 = WPP_GLOBAL_Control;
                                      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                        || *((char *)WPP_GLOBAL_Control + 28) >= 0
                                        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                      {
                                        goto LABEL_392;
                                      }
                                      v50 = 163;
                                      goto LABEL_386;
                                    }
                                    inserted = RegInsertLong(v63, "NumRoutes", *(unsigned int *)(v8 + 672));
                                    PathFromEntry = inserted;
                                    if ( inserted )
                                    {
                                      v49 = WPP_GLOBAL_Control;
                                      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                        || *((char *)WPP_GLOBAL_Control + 28) >= 0
                                        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                      {
                                        goto LABEL_392;
                                      }
                                      v50 = 164;
                                      goto LABEL_386;
                                    }
                                    v30 = *(_QWORD *)(v8 + 680);
                                    if ( v30 )
                                    {
                                      if ( *(_DWORD *)(v8 + 672) )
                                      {
                                        inserted = RegInsertBinary(v63, "Routes", v30, *(unsigned int *)(v8 + 676));
                                        PathFromEntry = inserted;
                                        if ( inserted )
                                        {
                                          v49 = WPP_GLOBAL_Control;
                                          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                            || *((char *)WPP_GLOBAL_Control + 28) >= 0
                                            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                          {
                                            goto LABEL_392;
                                          }
                                          v50 = 165;
                                          goto LABEL_386;
                                        }
                                      }
                                    }
                                    inserted = RegInsertLong(v63, "NumNrptRules", *(unsigned int *)(v8 + 688));
                                    PathFromEntry = inserted;
                                    if ( inserted )
                                    {
                                      v49 = WPP_GLOBAL_Control;
                                      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                        || *((char *)WPP_GLOBAL_Control + 28) >= 0
                                        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                      {
                                        goto LABEL_392;
                                      }
                                      v50 = 166;
                                      goto LABEL_386;
                                    }
                                    v31 = *(_QWORD *)(v8 + 696);
                                    if ( v31 )
                                    {
                                      if ( *(_DWORD *)(v8 + 688) )
                                      {
                                        inserted = RegInsertBinary(v63, "NrptRules", v31, *(unsigned int *)(v8 + 692));
                                        PathFromEntry = inserted;
                                        if ( inserted )
                                        {
                                          v49 = WPP_GLOBAL_Control;
                                          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                            || *((char *)WPP_GLOBAL_Control + 28) >= 0
                                            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                          {
                                            goto LABEL_392;
                                          }
                                          v50 = 167;
                                          goto LABEL_386;
                                        }
                                      }
                                    }
                                    inserted = RegInsertFlag(v63, "AutoTiggerCapable", *(unsigned int *)(v8 + 704));
                                    PathFromEntry = inserted;
                                    if ( inserted )
                                    {
                                      v49 = WPP_GLOBAL_Control;
                                      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                        || *((char *)WPP_GLOBAL_Control + 28) >= 0
                                        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                      {
                                        goto LABEL_392;
                                      }
                                      v50 = 168;
                                      goto LABEL_386;
                                    }
                                    PathFromEntry = RegInsertLong(v63, "NumAppIds", *(unsigned int *)(v8 + 728));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    v32 = *(void **)(v8 + 736);
                                    if ( v32 && *(_DWORD *)(v8 + 728) )
                                    {
                                      lpSubKey = 0;
                                      inserted = RegCreateDtlList(v32);
                                      PathFromEntry = inserted;
                                      if ( inserted )
                                      {
                                        v49 = WPP_GLOBAL_Control;
                                        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                          || *((char *)WPP_GLOBAL_Control + 28) >= 0
                                          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                        {
                                          goto LABEL_392;
                                        }
                                        v50 = 169;
                                        goto LABEL_386;
                                      }
                                      v33 = (CHAR *)lpSubKey;
                                      v34 = RegInsertStringList(v63, "ApplicationIds");
                                      PathFromEntry = v34;
                                      if ( v34 )
                                      {
                                        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                          && *((char *)WPP_GLOBAL_Control + 28) < 0
                                          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                        {
                                          WPP_SF_d(
                                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                                            170,
                                            WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids,
                                            v34);
                                        }
                                        DtlDestroyList(v33);
                                        goto LABEL_392;
                                      }
                                      DtlDestroyList(v33);
                                    }
                                    PathFromEntry = RegInsertLong(v63, "NumClassicAppIds", *(unsigned int *)(v8 + 708));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    v35 = *(void **)(v8 + 720);
                                    if ( v35 && *(_DWORD *)(v8 + 708) )
                                    {
                                      lpSubKey = 0;
                                      inserted = RegCreateDtlList(v35);
                                      PathFromEntry = inserted;
                                      if ( inserted )
                                      {
                                        v49 = WPP_GLOBAL_Control;
                                        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                          || *((char *)WPP_GLOBAL_Control + 28) >= 0
                                          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                        {
                                          goto LABEL_392;
                                        }
                                        v50 = 171;
                                        goto LABEL_386;
                                      }
                                      v36 = (CHAR *)lpSubKey;
                                      PathFromEntry = RegInsertStringList(v63, "ClassicApplicationIds");
                                      if ( PathFromEntry )
                                      {
                                        DtlDestroyList(v36);
                                        v49 = WPP_GLOBAL_Control;
                                        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                          && *((char *)WPP_GLOBAL_Control + 28) < 0
                                          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                        {
                                          v50 = 172;
                                          v51 = PathFromEntry;
                                          goto LABEL_387;
                                        }
                                        goto LABEL_392;
                                      }
                                      DtlDestroyList(v36);
                                    }
                                    inserted = RegInsertString(v63, "SecurityDescriptor", *(_QWORD *)(v8 + 744));
                                    PathFromEntry = inserted;
                                    if ( inserted )
                                    {
                                      v49 = WPP_GLOBAL_Control;
                                      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                        || *((char *)WPP_GLOBAL_Control + 28) >= 0
                                        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                      {
                                        goto LABEL_392;
                                      }
                                      v50 = 173;
                                      goto LABEL_386;
                                    }
                                    PathFromEntry = RegInsertString(v63, "ApnInfoProviderId", *(_QWORD *)(v8 + 864));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertString(v63, "ApnInfoUsername", *(_QWORD *)(v8 + 880));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertString(v63, "ApnInfoPassword", *(_QWORD *)(v8 + 888));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertString(v63, "ApnInfoAccessPoint", *(_QWORD *)(v8 + 872));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertLong(
                                                      v63,
                                                      "ApnInfoAuthentication",
                                                      *(unsigned int *)(v8 + 900));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(
                                                      v63,
                                                      "ApnInfoCompression",
                                                      *(unsigned int *)(v8 + 896));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(
                                                      v63,
                                                      "DeviceComplianceEnabled",
                                                      *(unsigned int *)(v8 + 904));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(
                                                      v63,
                                                      "DeviceComplianceSsoEnabled",
                                                      *(unsigned int *)(v8 + 912));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertString(
                                                      v63,
                                                      "DeviceComplianceSsoEku",
                                                      *(_QWORD *)(v8 + 920));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertString(
                                                      v63,
                                                      "DeviceComplianceSsoIssuer",
                                                      *(_QWORD *)(v8 + 928));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertLong(v63, "FlagsSet", *(unsigned int *)(v8 + 952));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertLong(v63, "Options", *(unsigned int *)(v8 + 956));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(
                                                      v63,
                                                      "DisableDefaultDnsSuffixes",
                                                      *(unsigned int *)(v8 + 788));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertLong(
                                                      v63,
                                                      "NumTrustedNetworks",
                                                      *(unsigned int *)(v8 + 792));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    v37 = *(_QWORD *)(v8 + 800);
                                    if ( v37 )
                                    {
                                      if ( *(_DWORD *)(v8 + 792) )
                                      {
                                        PathFromEntry = RegInsertBinary(
                                                          v63,
                                                          "TrustedNetworks",
                                                          v37,
                                                          *(unsigned int *)(v8 + 796));
                                        if ( PathFromEntry )
                                          goto LABEL_392;
                                      }
                                    }
                                    v38 = *(_QWORD *)(v8 + 760);
                                    if ( v38 )
                                    {
                                      PathFromEntry = RegInsertBinary(
                                                        v63,
                                                        "ThirdPartyProfileInfo",
                                                        v38,
                                                        *(unsigned int *)(v8 + 752));
                                      if ( PathFromEntry )
                                        goto LABEL_392;
                                    }
                                    PathFromEntry = RegInsertLong(
                                                      v63,
                                                      "NumDnsSearchSuffixes",
                                                      *(unsigned int *)(v8 + 768));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    v39 = *(_QWORD *)(v8 + 776);
                                    if ( v39 )
                                    {
                                      PathFromEntry = RegInsertBinary(
                                                        v63,
                                                        "DnsSuffixSearchList",
                                                        v39,
                                                        *(unsigned int *)(v8 + 772));
                                      if ( PathFromEntry )
                                        goto LABEL_392;
                                    }
                                    PathFromEntry = RegInsertFlag(
                                                      v63,
                                                      "PowershellCreatedProfile",
                                                      *(unsigned int *)(v8 + 784));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertLong(v63, "ProxyFlags", *(unsigned int *)(v8 + 560));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(
                                                      v63,
                                                      "ProxySettingsModified",
                                                      *(unsigned int *)(v8 + 820));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    if ( (*(_BYTE *)(v8 + 560) & 2) != 0 )
                                    {
                                      PathFromEntry = RegInsertString(v63, "Proxy", *(_QWORD *)(v8 + 576));
                                      if ( PathFromEntry )
                                        goto LABEL_392;
                                      PathFromEntry = RegInsertString(v63, "ExcludeList", *(_QWORD *)(v8 + 584));
                                      if ( PathFromEntry )
                                        goto LABEL_392;
                                      PathFromEntry = RegInsertFlag(
                                                        v63,
                                                        "BypassProxyForLocal",
                                                        *(unsigned int *)(v8 + 592));
                                      if ( PathFromEntry )
                                        goto LABEL_392;
                                    }
                                    if ( (*(_BYTE *)(v8 + 560) & 4) != 0 )
                                    {
                                      PathFromEntry = RegInsertString(v63, "AutoConfigScript", *(_QWORD *)(v8 + 568));
                                      if ( PathFromEntry )
                                        goto LABEL_392;
                                    }
                                    PathFromEntry = RegInsertString(v63, "ProvisioningAuthority", *(_QWORD *)(v8 + 808));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(v63, "AuthTypeOTP", *(unsigned int *)(v8 + 816));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    PathFromEntry = RegInsertFlag(v63, "GREKeyDefined", *(unsigned int *)(v8 + 824));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    if ( *(_DWORD *)(v8 + 824) )
                                    {
                                      PathFromEntry = RegInsertULong(v63, v40, *(unsigned int *)(v8 + 828));
                                      if ( PathFromEntry )
                                        goto LABEL_392;
                                    }
                                    PathFromEntry = RegInsertLong(
                                                      v63,
                                                      "NumPerAppTrafficFilters",
                                                      *(unsigned int *)(v8 + 832));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    v41 = *(_QWORD *)(v8 + 840);
                                    if ( v41 )
                                    {
                                      if ( *(_DWORD *)(v8 + 832) )
                                      {
                                        PathFromEntry = RegInsertBinary(
                                                          v63,
                                                          "PerAppTrafficFilters",
                                                          v41,
                                                          *(unsigned int *)(v8 + 836));
                                        if ( PathFromEntry )
                                          goto LABEL_392;
                                      }
                                    }
                                    PathFromEntry = RegInsertFlag(v63, "AlwaysOnCapable", *(unsigned int *)(v8 + 848));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    inserted = RegInsertFlag(v63, "DeviceTunnel", *(unsigned int *)(v8 + 856));
                                    PathFromEntry = inserted;
                                    if ( inserted )
                                    {
                                      v49 = WPP_GLOBAL_Control;
                                      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                        || *((char *)WPP_GLOBAL_Control + 28) >= 0
                                        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                      {
                                        goto LABEL_392;
                                      }
                                      v50 = 174;
                                      goto LABEL_386;
                                    }
                                    PathFromEntry = RegInsertFlag(v63, "PrivateNetwork", *(unsigned int *)(v8 + 852));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    v42 = *(_QWORD *)(v8 + 944);
                                    if ( v42 )
                                    {
                                      v43 = *(unsigned int *)(v8 + 936);
                                      if ( (_DWORD)v43 )
                                      {
                                        PathFromEntry = RegInsertBinary(v63, "PluginStorage", v42, v43);
                                        if ( PathFromEntry )
                                          goto LABEL_392;
                                      }
                                    }
                                    PathFromEntry = RegInsertString(v63, "ManagementApp", *(_QWORD *)(v8 + 960));
                                    if ( PathFromEntry )
                                      goto LABEL_392;
                                    RegInsertNetComponents(v63);
                                    v59 = 0;
                                    inserted = RegCreateKeyExA(v63, "MEDIA", 0, 0, 0, 0x20206u, 0, &v59, 0);
                                    PathFromEntry = inserted;
                                    if ( inserted )
                                    {
                                      v49 = WPP_GLOBAL_Control;
                                      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                        || *((char *)WPP_GLOBAL_Control + 28) >= 0
                                        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                      {
                                        goto LABEL_392;
                                      }
                                      v50 = 175;
                                      goto LABEL_386;
                                    }
                                    v44 = *(__int64 **)(v8 + 32);
                                    v64 = 0;
                                    for ( j = *v44; j; j = *(_QWORD *)(j + 8) )
                                    {
                                      v46 = *(_QWORD *)(j + 16);
                                      v47 = (CHAR *)StrdupWtoA(*(LPCWCH *)(v46 + 24));
                                      if ( !v47 )
                                      {
                                        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                          && *((char *)WPP_GLOBAL_Control + 28) < 0
                                          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                        {
                                          WPP_SF_d(
                                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                                            176,
                                            WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids,
                                            8);
                                        }
                                        break;
                                      }
                                      PathFromEntry = RegCreateKeyExA(v59, v47, 0, 0, 0, 0x20206u, 0, &v64, 0);
                                      if ( PathFromEntry )
                                        break;
                                      GlobalFree(v47);
                                      PathFromEntry = RegInsertString(v64, "Port", *(_QWORD *)v46);
                                      if ( PathFromEntry
                                        || (v48 = *(_QWORD *)(v46 + 16)) != 0
                                        && (PathFromEntry = RegInsertString(v64, "Device", v48)) != 0
                                        || (*(_DWORD *)(v46 + 40) == 3 || (*(_BYTE *)(v46 + 48) & 4) != 0)
                                        && (PathFromEntry = RegInsertLong(
                                                              v64,
                                                              "ConnectBPS",
                                                              *(unsigned int *)(v46 + 104))) != 0
                                        || (PathFromEntry = RegInsertDeviceList(a1, v64, v8, v46)) != 0 )
                                      {
                                        RegCloseKey(v64);
                                        break;
                                      }
                                      RegCloseKey(v64);
                                    }
                                    RegCloseKey(v59);
                                    if ( *(_DWORD *)(v8 + 548) )
                                    {
                                      PathFromEntry = RegInsertProxySettings(v63, v8);
                                      if ( PathFromEntry )
                                        goto LABEL_392;
                                    }
                                    *(_DWORD *)(v8 + 532) = 0;
                                    RegCloseKey(v63);
                                    v6 = v61;
                                    goto LABEL_249;
                                  }
                                  v49 = WPP_GLOBAL_Control;
                                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                                    || *((char *)WPP_GLOBAL_Control + 28) >= 0
                                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                  {
                                    goto LABEL_392;
                                  }
                                  v50 = 154;
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
LABEL_386:
          v51 = inserted;
          goto LABEL_387;
        }
        v52 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || *((char *)WPP_GLOBAL_Control + 28) >= 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_402;
        }
        v53 = 141;
      }
      else
      {
        v13 = 8;
        PathFromEntry = 8;
        v52 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || *((char *)WPP_GLOBAL_Control + 28) >= 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_402;
        }
        v53 = 140;
      }
      WPP_SF_d(v52[2], v53, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v13);
      goto LABEL_402;
    }
    v61 = ++v6;
LABEL_249:
    RegCloseKey(phkResult);
LABEL_250:
    v3 = WPP_GLOBAL_Control;
    goto LABEL_251;
  }
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v54 = 139;
    goto LABEL_430;
  }
  return PathFromEntry;
}

```

## disassembly

```asm
0x180040a68  mov     [rsp-8+arg_8], rdx
0x180040a6d  push    rbp
0x180040a6e  push    rbx
0x180040a6f  push    rsi
0x180040a70  push    rdi
0x180040a71  push    r12
0x180040a73  push    r13
0x180040a75  push    r14
0x180040a77  push    r15
0x180040a79  lea     rbp, [rsp-1Fh]
0x180040a7e  sub     rsp, 88h
0x180040a85  mov     r13, rcx
0x180040a88  mov     rcx, cs:WPP_GLOBAL_Control
0x180040a8f  lea     rdx, WPP_GLOBAL_Control
0x180040a96  mov     sil, 80h
0x180040a99  cmp     rcx, rdx
0x180040a9c  jz      short loc_180040ACD
0x180040a9e  test    [rcx+1Ch], sil
0x180040aa2  jz      short loc_180040ACD
0x180040aa4  cmp     byte ptr [rcx+19h], 6
0x180040aa8  jb      short loc_180040ACD
0x180040aaa  mov     rcx, [rcx+10h]
0x180040aae  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x180040ab5  mov     edx, 86h
0x180040aba  call    WPP_SF_
0x180040abf  mov     rcx, cs:WPP_GLOBAL_Control
0x180040ac6  lea     rdx, WPP_GLOBAL_Control
0x180040acd  mov     rax, [r13+10h]
0x180040ad1  xor     r15d, r15d
0x180040ad4  mov     [rbp+57h+var_70], r15
0x180040ad8  mov     ebx, r15d
0x180040adb  mov     [rbp+57h+arg_10], r15
0x180040adf  mov     r14d, r15d
0x180040ae2  mov     [rbp+57h+arg_0], r15d
0x180040ae6  mov     r12, [rax]
0x180040ae9  test    r12, r12
0x180040aec  jz      loc_180042BB2
0x180040af2  mov     rdi, [r12+10h]
0x180040af7  cmp     [rdi+214h], r15d
0x180040afe  jnz     short loc_180040B0D
0x180040b00  cmp     [rdi+21Ch], r15d
0x180040b07  jz      loc_180042355
0x180040b0d  test    dword ptr [r13+20h], 100h
0x180040b15  jz      short loc_180040B7E
0x180040b17  cmp     [rdi+224h], r15d
0x180040b1e  jz      short loc_180040B7E
0x180040b20  cmp     rcx, rdx
0x180040b23  jz      short loc_180040B4A
0x180040b25  test    [rcx+1Ch], sil
0x180040b29  jz      short loc_180040B4A
0x180040b2b  cmp     byte ptr [rcx+19h], 5
0x180040b2f  jb      short loc_180040B4A
0x180040b31  mov     r9, [rdi+8]
0x180040b35  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x180040b3c  mov     rcx, [rcx+10h]
0x180040b40  mov     edx, 87h
0x180040b45  call    WPP_SF_S
0x180040b4a  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180040b50  cmp     ecx, 0FFFFFFFFh
0x180040b53  jz      short loc_180040B6B
0x180040b55  mov     r9, [rdi+8]
0x180040b59  lea     r8, aEntrySNotWritt; "Entry %S not written to hidden pbk"
0x180040b60  mov     edx, 0Ch; dwFlags
0x180040b65  call    cs:__imp_TracePrintfExA
0x180040b6b  mov     [rdi+214h], r15d
0x180040b72  mov     [rdi+21Ch], r15d
0x180040b79  jmp     loc_18004234E
0x180040b7e  mov     r8, rdi
0x180040b81  mov     [rbp+57h+lpWideCharStr], r15
0x180040b85  lea     rdx, [rbp+57h+lpWideCharStr]
0x180040b89  mov     [rbp+57h+lpSubKey], r15
0x180040b8d  mov     rcx, r13
0x180040b90  mov     [rbp+57h+hKey], r15
0x180040b94  call    GetPathFromEntry
0x180040b99  mov     ebx, eax
0x180040b9b  test    eax, eax
0x180040b9d  jnz     loc_180042B7D
0x180040ba3  mov     rcx, [rbp+57h+lpWideCharStr]; lpWideCharStr
0x180040ba7  lea     r9, [rbp+57h+lpSubKey]
0x180040bab  lea     r8, [rbp+57h+hKey]
0x180040baf  mov     rdx, r13
0x180040bb2  call    RegistryPathConverter
0x180040bb7  mov     rcx, [rbp+57h+lpWideCharStr]
0x180040bbb  mov     ebx, eax
0x180040bbd  call    Free0
0x180040bc2  mov     eax, 0EBh
0x180040bc7  cmp     ebx, eax
0x180040bc9  jz      loc_180042C51
0x180040bcf  mov     rsi, [rbp+57h+lpSubKey]
0x180040bd3  mov     rdx, [rbp+57h+hKey]
0x180040bd7  mov     rcx, rsi; lpSubKey
0x180040bda  call    RegSetKeySecurityInfo
0x180040bdf  test    eax, eax
0x180040be1  jz      short loc_180040C17
0x180040be3  mov     rcx, cs:WPP_GLOBAL_Control
0x180040bea  lea     rax, WPP_GLOBAL_Control
0x180040bf1  cmp     rcx, rax
0x180040bf4  jz      short loc_180040C25
0x180040bf6  test    byte ptr [rcx+1Ch], 80h
0x180040bfa  jz      short loc_180040C25
0x180040bfc  cmp     byte ptr [rcx+19h], 2
0x180040c00  jb      short loc_180040C25
0x180040c02  mov     rcx, [rcx+10h]
0x180040c06  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x180040c0d  mov     edx, 89h
0x180040c12  call    WPP_SF_
0x180040c17  mov     rcx, cs:WPP_GLOBAL_Control
0x180040c1e  lea     rax, WPP_GLOBAL_Control
0x180040c25  test    ebx, ebx
0x180040c27  jnz     loc_180042B56
0x180040c2d  mov     rcx, [rbp+57h+hKey]; hKey
0x180040c31  lea     rax, [rbp+57h+var_70]
0x180040c35  mov     [rsp+0C0h+lpdwDisposition], r15; lpdwDisposition
0x180040c3a  xor     r9d, r9d; lpClass
0x180040c3d  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180040c42  xor     r8d, r8d; Reserved
0x180040c45  mov     [rsp+0C0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180040c4a  mov     rdx, rsi; lpSubKey
0x180040c4d  mov     [rsp+0C0h+samDesired], 20206h; samDesired
0x180040c55  mov     [rsp+0C0h+dwOptions], r15d; dwOptions
0x180040c5a  call    cs:__imp_RegCreateKeyExA
0x180040c60  mov     rcx, rsi
0x180040c63  mov     ebx, eax
0x180040c65  call    Free0
0x180040c6a  test    ebx, ebx
0x180040c6c  jnz     loc_180042B21
0x180040c72  mov     rcx, rdi
0x180040c75  call    UpdateEntryTimeStamp
0x180040c7a  mov     rdx, [rdi+8]; lpSubKey
0x180040c7e  mov     rcx, [rbp+57h+var_70]; hKey
0x180040c82  call    cs:__imp_RegDeleteTreeW
0x180040c88  cmp     [rdi+21Ch], r15d
0x180040c8f  jnz     loc_18004233A
0x180040c95  mov     rcx, [rdi+8]; lpWideCharStr
0x180040c99  call    _StrdupWtoA
0x180040c9e  mov     rsi, rax
0x180040ca1  test    rax, rax
0x180040ca4  jz      loc_180042AAB
0x180040caa  mov     rcx, [rbp+57h+var_70]; hKey
0x180040cae  lea     rax, [rbp+57h+arg_10]
0x180040cb2  mov     [rsp+0C0h+lpdwDisposition], r15; lpdwDisposition
0x180040cb7  xor     r9d, r9d; lpClass
0x180040cba  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180040cbf  xor     r8d, r8d; Reserved
0x180040cc2  mov     [rsp+0C0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180040cc7  mov     rdx, rsi; lpSubKey
0x180040cca  mov     [rsp+0C0h+samDesired], 20206h; samDesired
0x180040cd2  mov     [rsp+0C0h+dwOptions], r15d; dwOptions
0x180040cd7  call    cs:__imp_RegCreateKeyExA
0x180040cdd  mov     ebx, eax
0x180040cdf  test    eax, eax
0x180040ce1  jnz     loc_180042A85
0x180040ce7  mov     rcx, rsi; hMem
0x180040cea  call    cs:__imp_GlobalFree
0x180040cf0  mov     rcx, [rbp+57h+arg_10]
0x180040cf4  lea     esi, [rbx+1]
0x180040cf7  mov     r8d, esi
0x180040cfa  lea     rdx, aEncoding; "Encoding"
0x180040d01  call    RegInsertLong
0x180040d06  mov     ebx, eax
0x180040d08  test    eax, eax
0x180040d0a  jnz     loc_180042A4C
0x180040d10  mov     rcx, [rbp+57h+arg_10]
0x180040d14  lea     r14d, [rsi+7]
0x180040d18  mov     r8d, r14d
0x180040d1b  lea     rdx, aPbversion; "PBVersion"
0x180040d22  call    RegInsertLong
0x180040d27  mov     ebx, eax
0x180040d29  test    eax, eax
0x180040d2b  jnz     loc_180042A13
0x180040d31  mov     r8d, [rdi+18h]
0x180040d35  lea     rdx, aType; "Type"
0x180040d3c  mov     rcx, [rbp+57h+arg_10]
0x180040d40  call    RegInsertLong
0x180040d45  mov     ebx, eax
0x180040d47  test    eax, eax
0x180040d49  jnz     loc_1800429ED
0x180040d4f  mov     r8d, [rdi+0B0h]
0x180040d56  lea     rdx, aAutologon; "AutoLogon"
0x180040d5d  mov     rcx, [rbp+57h+arg_10]
0x180040d61  call    RegInsertFlag
0x180040d66  mov     ebx, eax
0x180040d68  test    eax, eax
0x180040d6a  jnz     loc_1800429BB
0x180040d70  mov     r8d, [rdi+0B4h]
0x180040d77  lea     rdx, aUserascredenti_0; "UseRasCredentials"
0x180040d7e  mov     rcx, [rbp+57h+arg_10]
0x180040d82  call    RegInsertFlag
0x180040d87  mov     ebx, eax
0x180040d89  test    eax, eax
0x180040d8b  jnz     loc_180042989
0x180040d91  mov     r8d, [rdi+10h]
0x180040d95  lea     rdx, aLowdatetime; "LowDateTime"
0x180040d9c  mov     rcx, [rbp+57h+arg_10]
0x180040da0  call    RegInsertLong
0x180040da5  mov     ebx, eax
0x180040da7  test    eax, eax
0x180040da9  jnz     loc_180042954
0x180040daf  mov     r8d, [rdi+14h]
0x180040db3  lea     rdx, aHighdatetime; "HighDateTime"
0x180040dba  mov     rcx, [rbp+57h+arg_10]
0x180040dbe  call    RegInsertLong
0x180040dc3  mov     ebx, eax
0x180040dc5  test    eax, eax
0x180040dc7  jnz     loc_18004291F
0x180040dcd  mov     r8d, [rdi+1C8h]
0x180040dd4  lea     rdx, aDialparamsuid; "DialParamsUID"
0x180040ddb  mov     rcx, [rbp+57h+arg_10]
0x180040ddf  call    RegInsertLong
0x180040de4  mov     ebx, eax
0x180040de6  test    eax, eax
0x180040de8  jnz     loc_1800428EA
0x180040dee  mov     r8, [rdi+1D0h]
0x180040df5  test    r8, r8
0x180040df8  jz      short loc_180040E18
0x180040dfa  mov     rcx, [rbp+57h+arg_10]
0x180040dfe  lea     r9d, [rsi+0Fh]
0x180040e02  lea     rdx, aGuid; "Guid"
0x180040e09  call    RegInsertBinary
0x180040e0e  mov     ebx, eax
0x180040e10  test    eax, eax
0x180040e12  jnz     loc_180042366
0x180040e18  mov     r8d, [rdi+0A8h]
0x180040e1f  lea     rdx, aVpnstrategy; "VpnStrategy"
0x180040e26  mov     rcx, [rbp+57h+arg_10]
0x180040e2a  call    RegInsertLong
0x180040e2f  mov     ebx, eax
0x180040e31  test    eax, eax
0x180040e33  jnz     loc_1800428B5
0x180040e39  mov     r8d, [rdi+0ECh]
0x180040e40  lea     rdx, aExcludedprotoc; "ExcludedProtocols"
0x180040e47  mov     rcx, [rbp+57h+arg_10]
0x180040e4b  call    RegInsertLong
0x180040e50  mov     ebx, eax
0x180040e52  test    eax, eax
0x180040e54  jnz     loc_180042880
0x180040e5a  mov     r8d, [rdi+0F0h]
0x180040e61  lea     rdx, aLcpextensions; "LcpExtensions"
0x180040e68  mov     rcx, [rbp+57h+arg_10]
0x180040e6c  call    RegInsertFlag
0x180040e71  mov     ebx, eax
0x180040e73  test    eax, eax
0x180040e75  jnz     loc_18004284B
0x180040e7b  mov     r8d, [rdi+0ACh]
0x180040e82  lea     rdx, aDataencryption; "DataEncryption"
0x180040e89  mov     rcx, [rbp+57h+arg_10]
0x180040e8d  call    RegInsertLong
0x180040e92  mov     ebx, eax
0x180040e94  test    eax, eax
0x180040e96  jnz     loc_180042816
0x180040e9c  mov     r8d, [rdi+0F4h]
0x180040ea3  lea     rdx, aSwcompression; "SwCompression"
0x180040eaa  mov     rcx, [rbp+57h+arg_10]
0x180040eae  call    RegInsertFlag
0x180040eb3  mov     ebx, eax
0x180040eb5  test    eax, eax
0x180040eb7  jnz     loc_180042A72
0x180040ebd  mov     r8d, [rdi+0F8h]
0x180040ec4  lea     rdx, aNegotiatemulti; "NegotiateMultilinkAlways"
0x180040ecb  mov     rcx, [rbp+57h+arg_10]
0x180040ecf  call    RegInsertFlag
0x180040ed4  mov     ebx, eax
0x180040ed6  test    eax, eax
0x180040ed8  jnz     loc_180042A72
0x180040ede  mov     r8d, [rdi+0FCh]
0x180040ee5  lea     rdx, aSkipdoubledial; "SkipDoubleDialDialog"
0x180040eec  mov     rcx, [rbp+57h+arg_10]
0x180040ef0  call    RegInsertFlag
0x180040ef5  mov     ebx, eax
0x180040ef7  test    eax, eax
0x180040ef9  jnz     loc_180042A72
0x180040eff  mov     r8d, [rdi+84h]
0x180040f06  lea     rdx, aDialmode; "DialMode"
0x180040f0d  mov     rcx, [rbp+57h+arg_10]
0x180040f11  call    RegInsertLong
0x180040f16  mov     ebx, eax
0x180040f18  test    eax, eax
0x180040f1a  jnz     loc_180042A72
0x180040f20  mov     r8d, [rdi+90h]
0x180040f27  lea     rdx, aOverridepref; "OverridePref"
0x180040f2e  mov     rcx, [rbp+57h+arg_10]
0x180040f32  call    RegInsertLong
0x180040f37  mov     ebx, eax
0x180040f39  test    eax, eax
0x180040f3b  jnz     loc_180042A72
0x180040f41  mov     r8d, [rdi+94h]
0x180040f48  lea     rdx, aRedialattempts; "RedialAttempts"
0x180040f4f  mov     rcx, [rbp+57h+arg_10]
0x180040f53  call    RegInsertLong
0x180040f58  mov     ebx, eax
0x180040f5a  test    eax, eax
0x180040f5c  jnz     loc_180042A72
0x180040f62  mov     r8d, [rdi+98h]
0x180040f69  lea     rdx, aRedialseconds_0; "RedialSeconds"
0x180040f70  mov     rcx, [rbp+57h+arg_10]
0x180040f74  call    RegInsertLong
0x180040f79  mov     ebx, eax
0x180040f7b  test    eax, eax
0x180040f7d  jnz     loc_180042A72
0x180040f83  mov     r8d, [rdi+9Ch]
  ... truncated ...
```
