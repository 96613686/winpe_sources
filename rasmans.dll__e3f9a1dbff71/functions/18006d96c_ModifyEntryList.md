# ModifyEntryList

- ea: `0x18006d96c`
- end: `0x180070bcc`
- name: `ModifyEntryList`
- size: `12896`
- prototype: `__int64 __fastcall(__int64, unsigned int *)`
- caller_count: `1`
- callee_count: `32`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18007b698`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18000e5f0`
- `0x18005cb9c`
- `0x18005cc20`
- `0x18005d1e0`
- `0x18005d5f8`
- `0x18005d748`
- `0x1800671c8`
- `0x1800675a8`
- `0x180067d64`
- `0x18006ae54`
- `0x18006b02c`
- `0x18006c57c`
- `0x18006c6c0`
- `0x18006c734`
- `0x18006cda4`
- `0x18006d00c`
- `0x18006d11c`
- `0x18006d24c`
- `0x18006d3b0`
- `0x18006d740`
- `0x18006d96c`
- `0x18007be38`
- `0x18007c0c8`
- `0x18007c5d8`
- `0x18007d338`
- `0x180080e7c`
- `0x18008ecb8`
- `0x18008fec8`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f59d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f59d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006dbe5`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006dd38`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006dbe5`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006dd38`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18006f593`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18006f593`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006f511`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006f511`

## string_xrefs

- `0x18006df67`: `NegotiateMultilinkAlways`
- `0x18006df3d`: `SwCompression`
- `0x18006dff2`: `RedialAttempts`
- `0x18006dece`: `ExcludedProtocols`
- `0x18006def4`: `LcpExtensions`
- `0x18006e056`: `RedialOnLinkFailure`
- `0x18006e098`: `CustomDialDll`
- `0x18006e0f8`: `ForceSecureCompartment`
- `0x18006e0d6`: `CustomRasDialDll`
- `0x18006e3e6`: `ShowMonitorIconInTaskBar`
- `0x18006e2eb`: `PreferredCompression`
- `0x18006e2c4`: `PreferredProtocol`
- `0x18006e327`: `PreferredMdmProtocol`
- `0x18006e4c2`: `IpHeaderCompression`
- `0x18006e8e5`: `ImsConfig`
- `0x18006e98b`: `CacheCredentials`
- `0x18006edd8`: `ApnInfoAccessPoint`
- `0x18006ee4e`: `DeviceComplianceEnabled`
- `0x18006ee2a`: `ApnInfoCompression`
- `0x18006ee9b`: `DeviceComplianceSsoEku`
- `0x18006ee78`: `DeviceComplianceSsoEnabled`
- `0x18006ed5c`: `SecurityDescriptor`
- `0x18006f010`: `PowershellCreatedProfile`
- `0x18006f0f6`: `AutoConfigScript`
- `0x18006f49f`: `AutoConfigScript`
- `0x18006eeba`: `DeviceComplianceSsoIssuer`
- `0x18006f292`: `PluginStorage`
- `0x18006f2dd`: `ProtocolListLength`
- `0x18006f31f`: `ProtocolListRetryTimeInHours`
- `0x18006f302`: `ProtocolList`
- `0x18006f35d`: `ProtocolListTimeOfLastProtocolSelectionLow`
- `0x18006f33e`: `ProtocolListCurrentProtocol`
- `0x18006f37c`: `ProtocolListTimeOfLastProtocolSelectionHigh`

## pseudocode

```c
__int64 __fastcall ModifyEntryList(__int64 a1, unsigned int *a2)
{
  unsigned int *v2; // rsi
  __int64 v3; // rbx
  struct _LIST_ENTRY *v4; // rcx
  unsigned int v5; // r15d
  int v6; // edx
  unsigned int LUAPhonebookPath; // edi
  __int64 v8; // r8
  PCNZWCH *v9; // r13
  __int64 v10; // rsi
  _DWORD *v11; // r12
  WCHAR *v12; // r14
  __int64 *v13; // rbx
  __int64 v14; // rbx
  const WCHAR *v15; // rcx
  int v16; // ebx
  unsigned int v17; // ebx
  __int64 HRasfileNode; // rax
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 *v21; // rax
  __int64 v22; // rax
  unsigned int v23; // ebx
  __int64 v24; // rax
  void *v25; // r14
  int v26; // edx
  int v27; // r9d
  unsigned int inserted; // eax
  const char *v29; // r8
  const char *v30; // r8
  __int64 v31; // r8
  unsigned int v32; // eax
  const char *v33; // r8
  const char *v34; // r8
  const char *v35; // r8
  const char *v36; // r8
  const char *v37; // r8
  const char *v38; // r8
  const char *v39; // r8
  const char *v40; // r8
  const char *v41; // r8
  const char *v42; // r8
  const char *v43; // r8
  const char *v44; // r8
  const char *v45; // r8
  const char *v46; // r8
  const char *v47; // r8
  const char *v48; // r8
  const char *v49; // r8
  const char *v50; // r8
  const char *v51; // r8
  __int64 v52; // r8
  const char *v53; // r8
  const char *v54; // r8
  const WCHAR *v55; // r8
  const WCHAR *v56; // r8
  const WCHAR *v57; // r8
  const WCHAR *v58; // r8
  const WCHAR *v59; // r8
  const WCHAR *v60; // r8
  const char *v61; // r8
  const WCHAR *v62; // r8
  const WCHAR *v63; // r8
  const char *v64; // r8
  const char *v65; // r8
  const char *v66; // r8
  unsigned int v67; // eax
  unsigned int v68; // eax
  unsigned int v69; // eax
  const char *v70; // r8
  __int64 v71; // r8
  __int64 v72; // r8
  __int64 v73; // r9
  const char *v74; // r8
  __int64 v75; // r8
  __int64 v76; // r9
  const char *v77; // r8
  const char *v78; // r8
  __int64 v79; // r8
  __int64 v80; // r8
  const char *v81; // r8
  __int64 v82; // rcx
  __int64 v83; // rdx
  unsigned int v84; // eax
  __int64 v85; // rcx
  __int64 v86; // rdx
  const char *v87; // r8
  const char *v88; // r8
  const char *v89; // r8
  const char *v90; // r8
  __int64 v91; // r8
  __int64 v92; // r8
  __int64 v93; // r8
  const char *v94; // r8
  const char *v95; // r8
  const char *v96; // r8
  const char *v97; // r8
  const char *v98; // r8
  __int64 v99; // r8
  const char *v100; // r8
  const char *v101; // r8
  const char *v102; // r8
  __int64 v103; // r8
  __int64 v104; // r9
  __int64 v105; // r15
  __int64 v106; // r14
  int v107; // edx
  int v108; // r9d
  __int64 v109; // r8
  const WCHAR *v110; // r15
  unsigned int v111; // r14d
  __int64 cbMultiByte; // r12
  __int64 v113; // rdx
  __int64 v114; // rdx
  __int64 v115; // r9
  struct _LIST_ENTRY *v116; // rcx
  __int64 v117; // rdx
  unsigned int v119; // ebx
  int v120; // [rsp+40h] [rbp-C0h]
  __int64 v121; // [rsp+50h] [rbp-B0h]
  PCNZWCH *v122; // [rsp+58h] [rbp-A8h]
  CHAR MultiByteStr[272]; // [rsp+70h] [rbp-90h] BYREF

  v2 = a2;
  v3 = a1;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 230, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = 0;
  v6 = 0;
  LUAPhonebookPath = 0;
  v120 = 0;
  v8 = **(_QWORD **)(v3 + 16);
  v121 = v8;
  if ( !v8 )
  {
LABEL_798:
    v119 = *(_DWORD *)(*(_QWORD *)(v3 + 16) + 16LL) - v6;
    if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 5u )
      WPP_SF_d(v4[1].Flink, 336, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v119);
    *v2 = v119;
LABEL_803:
    v4 = WPP_GLOBAL_Control;
    goto LABEL_804;
  }
  v9 = 0;
  v122 = 0;
  while ( 1 )
  {
    v10 = *(_QWORD *)(v8 + 16);
    v11 = (_DWORD *)(v10 + 540);
    if ( !*(_DWORD *)(v10 + 532) && !*v11 )
      goto LABEL_48;
    if ( (*(_DWORD *)(v3 + 32) & 0x100) == 0 || !*(_DWORD *)(v10 + 548) )
      break;
    if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 5u )
    {
      WPP_SF_S(v4[1].Flink, 231, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, *(_QWORD *)(v10 + 8));
      v6 = v120;
      v8 = v121;
    }
    *(_DWORD *)(v10 + 532) = 0;
    *(_DWORD *)(v10 + 540) = 0;
    v4 = WPP_GLOBAL_Control;
LABEL_48:
    v8 = *(_QWORD *)(v8 + 8);
    v121 = v8;
    if ( !v8 )
    {
      if ( LUAPhonebookPath )
        goto LABEL_804;
      v3 = a1;
      v2 = a2;
      goto LABEL_798;
    }
    v3 = a1;
  }
  if ( *(_DWORD *)v10 == -1 )
  {
    if ( !*(_DWORD *)(v10 + 548) || (v5 = 1, *(_DWORD *)(v3 + 8) == 4) )
    {
      v15 = *(const WCHAR **)v3;
      if ( (*(_DWORD *)(v3 + 32) & 0x100) != 0 )
      {
        LUAPhonebookPath = GetLUAPhonebookPath(v15);
        if ( LUAPhonebookPath )
          goto LABEL_26;
        v12 = 0;
      }
      else
      {
        LUAPhonebookPath = 0;
        v12 = (WCHAR *)StrDup(v15);
      }
      if ( v12 )
      {
LABEL_21:
        v13 = *(__int64 **)(v3 + 48);
        v9 = 0;
        v122 = 0;
        if ( !v13 )
          goto LABEL_35;
        v14 = *v13;
        while ( v14 )
        {
          v9 = *(PCNZWCH **)(v14 + 16);
          v122 = v9;
          if ( !v9 )
            goto LABEL_35;
          if ( !(unsigned int)CompareStringWrapW(v9[1], v12) )
            break;
          v14 = *(_QWORD *)(v14 + 8);
          v9 = 0;
          v122 = 0;
        }
        if ( !v9 )
        {
LABEL_35:
          v16 = *(_DWORD *)(*(_QWORD *)(a1 + 48) + 16LL);
          LUAPhonebookPath = CreateProfileDirAndSetAcls(*(char **)(a1 + 40), (__int64)v12, *(_DWORD *)(a1 + 8), v5, 1);
          if ( !LUAPhonebookPath )
          {
            LUAPhonebookPath = LoadFile(v12);
            if ( !LUAPhonebookPath )
            {
              v17 = v16 + 1;
              HRasfileNode = CreateHRasfileNode(0xFFFFFFFFLL, v12, v17);
              *(_DWORD *)v10 = v17;
              DtlAddNodeLast(*(_QWORD *)(a1 + 48), HRasfileNode);
              v9 = *(PCNZWCH **)(v19 + 16);
              v122 = v9;
            }
          }
        }
      }
      else
      {
        LUAPhonebookPath = 8;
      }
    }
    else
    {
      LUAPhonebookPath = GetProvisionedProfilePath(*(STRSAFE_LPCWSTR *)v3, *(STRSAFE_LPCWSTR *)(v10 + 8));
      if ( !LUAPhonebookPath )
      {
        v12 = 0;
        goto LABEL_21;
      }
LABEL_26:
      v12 = 0;
    }
    v5 = 0;
    if ( v12 )
      GlobalFree(v12);
    if ( LUAPhonebookPath )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v20 = 232;
        goto LABEL_45;
      }
      goto LABEL_46;
    }
    v4 = WPP_GLOBAL_Control;
  }
  else
  {
    v21 = *(__int64 **)(v3 + 48);
    v9 = 0;
    v122 = 0;
    if ( v21 )
    {
      v22 = *v21;
      while ( v22 )
      {
        v9 = *(PCNZWCH **)(v22 + 16);
        v122 = v9;
        if ( !v9 )
          goto LABEL_58;
        if ( *((_DWORD *)v9 + 4) == *(_DWORD *)v10 )
          break;
        v22 = *(_QWORD *)(v22 + 8);
        v9 = 0;
        v122 = 0;
      }
    }
  }
  if ( !v9 )
  {
LABEL_58:
    if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 5u )
    {
      WPP_SF_S(v4[1].Flink, 233, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, *(_QWORD *)(v10 + 8));
      v4 = WPP_GLOBAL_Control;
    }
    LUAPhonebookPath = 622;
    if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 2u )
    {
      v20 = 234;
LABEL_45:
      WPP_SF_d(v4[1].Flink, v20, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, LUAPhonebookPath);
      v4 = WPP_GLOBAL_Control;
    }
LABEL_46:
    v6 = v120;
LABEL_47:
    v8 = v121;
    goto LABEL_48;
  }
  v23 = *(_DWORD *)v9;
  UpdateEntryTimeStamp(v10);
  v24 = StrDupAFromTInternal(*(LPCWCH *)(v10 + 8));
  v25 = (void *)v24;
  if ( !v24 )
  {
    inserted = 8;
    LUAPhonebookPath = 8;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_804;
    v114 = 235;
    goto LABEL_407;
  }
  if ( (unsigned int)RasfileFindSectionLine(v23, v24) )
    DeleteCurrentSection(v23);
  GlobalFree(v25);
  if ( *v11 )
  {
    *((_DWORD *)v9 + 5) |= 1u;
    v4 = WPP_GLOBAL_Control;
    v6 = ++v120;
    goto LABEL_47;
  }
  LOBYTE(v27) = 2;
  LOBYTE(v26) = 63;
  rasFindLine(v23, v26, 0, v27, 2);
  inserted = InsertSection(v23, *(_QWORD *)(v10 + 8));
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_804;
    v114 = 236;
    goto LABEL_407;
  }
  inserted = InsertLong(v23, "Encoding", 1);
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_804;
    v114 = 237;
    goto LABEL_407;
  }
  inserted = InsertLong(v23, "PBVersion", 8);
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_804;
    v114 = 238;
    goto LABEL_407;
  }
  inserted = InsertLong(v23, "Type", *(unsigned int *)(v10 + 24));
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_804;
    v114 = 239;
    goto LABEL_407;
  }
  v29 = "1";
  if ( !*(_DWORD *)(v10 + 176) )
    v29 = "0";
  inserted = InsertStringA(v23, "AutoLogon", v29);
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_804;
    v114 = 240;
    goto LABEL_407;
  }
  v30 = "1";
  if ( !*(_DWORD *)(v10 + 180) )
    v30 = "0";
  inserted = InsertStringA(v23, "UseRasCredentials", v30);
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_804;
    v114 = 241;
    goto LABEL_407;
  }
  inserted = InsertLong(v23, "LowDateTime", *(unsigned int *)(v10 + 16));
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_804;
    v114 = 242;
    goto LABEL_407;
  }
  inserted = InsertLong(v23, "HighDateTime", *(unsigned int *)(v10 + 20));
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_804;
    v114 = 243;
    goto LABEL_407;
  }
  inserted = InsertLong(v23, "DialParamsUID", *(unsigned int *)(v10 + 456));
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_804;
    v114 = 244;
LABEL_407:
    v115 = inserted;
    goto LABEL_408;
  }
  v31 = *(_QWORD *)(v10 + 464);
  if ( v31 )
  {
    v32 = InsertBinary(v23, "Guid", v31, 16);
    LUAPhonebookPath = v32;
    if ( v32 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      {
        if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 245, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v32);
          v4 = WPP_GLOBAL_Control;
        }
        if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 6u )
        {
          v113 = 246;
          goto LABEL_808;
        }
      }
      return LUAPhonebookPath;
    }
  }
  inserted = InsertLong(v23, "VpnStrategy", *(unsigned int *)(v10 + 168));
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v114 = 247;
      goto LABEL_407;
    }
    goto LABEL_804;
  }
  inserted = InsertLong(v23, "ExcludedProtocols", *(unsigned int *)(v10 + 236));
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v114 = 248;
      goto LABEL_407;
    }
    goto LABEL_804;
  }
  v33 = "1";
  if ( !*(_DWORD *)(v10 + 240) )
    v33 = "0";
  inserted = InsertStringA(v23, "LcpExtensions", v33);
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v114 = 249;
      goto LABEL_407;
    }
    goto LABEL_804;
  }
  inserted = InsertLong(v23, "DataEncryption", *(unsigned int *)(v10 + 172));
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v114 = 250;
      goto LABEL_407;
    }
LABEL_804:
    if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 6u )
    {
      v113 = 337;
LABEL_808:
      WPP_SF_d(v4[1].Flink, v113, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, LUAPhonebookPath);
    }
    return LUAPhonebookPath;
  }
  v34 = "1";
  if ( !*(_DWORD *)(v10 + 244) )
    v34 = "0";
  LUAPhonebookPath = InsertStringA(v23, "SwCompression", v34);
  if ( LUAPhonebookPath )
    goto LABEL_803;
  v35 = "1";
  if ( !*(_DWORD *)(v10 + 248) )
    v35 = "0";
  LUAPhonebookPath = InsertStringA(v23, "NegotiateMultilinkAlways", v35);
  if ( LUAPhonebookPath )
    goto LABEL_803;
  v36 = "1";
  if ( !*(_DWORD *)(v10 + 252) )
    v36 = "0";
  LUAPhonebookPath = InsertStringA(v23, "SkipDoubleDialDialog", v36);
  if ( LUAPhonebookPath )
    goto LABEL_803;
  LUAPhonebookPath = InsertLong(v23, "DialMode", *(unsigned int *)(v10 + 132));
  if ( LUAPhonebookPath )
    goto LABEL_803;
  LUAPhonebookPath = InsertLong(v23, "OverridePref", *(unsigned int *)(v10 + 144));
  if ( LUAPhonebookPath )
    goto LABEL_803;
  LUAPhonebookPath = InsertLong(v23, "RedialAttempts", *(unsigned int *)(v10 + 148));
  if ( LUAPhonebookPath )
    goto LABEL_803;
  LUAPhonebookPath = InsertLong(v23, "RedialSeconds", *(unsigned int *)(v10 + 152));
  if ( LUAPhonebookPath )
    goto LABEL_803;
  LUAPhonebookPath = InsertLong(v23, "IdleDisconnectSeconds", *(unsigned int *)(v10 + 156));
  if ( LUAPhonebookPath )
    goto LABEL_803;
  v37 = "1";
  if ( !*(_DWORD *)(v10 + 160) )
    v37 = "0";
  LUAPhonebookPath = InsertStringA(v23, "RedialOnLinkFailure", v37);
  if ( LUAPhonebookPath )
    goto LABEL_803;
  LUAPhonebookPath = InsertLong(v23, "CallbackMode", *(unsigned int *)(v10 + 420));
  if ( LUAPhonebookPath )
    goto LABEL_803;
  LUAPhonebookPath = InsertString(v23, "CustomDialDll", *(_QWORD *)(v10 + 432));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 251;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertString(v23, "CustomDialFunc", *(_QWORD *)(v10 + 440));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 252;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertString(v23, "CustomRasDialDll", *(_QWORD *)(v10 + 448));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 253;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  *(_DWORD *)(v10 + 184) = 0;
  LUAPhonebookPath = InsertStringA(v23, "ForceSecureCompartment", "0");
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 254;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  v38 = "1";
  if ( !*(_DWORD *)(v10 + 188) )
    v38 = "0";
  LUAPhonebookPath = InsertStringA(v23, "DisableIKENameEkuCheck", v38);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 255;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  v39 = "1";
  if ( !*(_DWORD *)(v10 + 424) )
    v39 = "0";
  LUAPhonebookPath = InsertStringA(v23, "AuthenticateServer", v39);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 256;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  v40 = "1";
  if ( !*(_DWORD *)(v10 + 256) )
    v40 = "0";
  LUAPhonebookPath = InsertStringA(v23, "ShareMsFilePrint", v40);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 257;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  v41 = "1";
  if ( !*(_DWORD *)(v10 + 260) )
    v41 = "0";
  LUAPhonebookPath = InsertStringA(v23, "BindMsNetClient", v41);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 258;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  v42 = "1";
  if ( !*(_DWORD *)(v10 + 40) )
    v42 = "0";
  LUAPhonebookPath = InsertStringA(v23, "SharedPhoneNumbers", v42);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 259;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  v43 = "1";
  if ( !*(_DWORD *)(v10 + 44) )
    v43 = "0";
  LUAPhonebookPath = InsertStringA(v23, "GlobalDeviceSettings", v43);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 260;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertString(v23, "PrerequisiteEntry", *(_QWORD *)(v10 + 56));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 261;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertString(v23, "PrerequisitePbk", *(_QWORD *)(v10 + 64));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 262;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertString(v23, "PreferredPort", *(_QWORD *)(v10 + 72));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 263;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertString(v23, "PreferredDevice", *(_QWORD *)(v10 + 80));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 264;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v23, "PreferredBps", *(unsigned int *)(v10 + 88));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 265;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  v44 = "1";
  if ( !*(_DWORD *)(v10 + 92) )
    v44 = "0";
  LUAPhonebookPath = InsertStringA(v23, "PreferredHwFlow", v44);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 266;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  v45 = "1";
  if ( !*(_DWORD *)(v10 + 96) )
    v45 = "0";
  LUAPhonebookPath = InsertStringA(v23, "PreferredProtocol", v45);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 267;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  v46 = "1";
  if ( !*(_DWORD *)(v10 + 100) )
    v46 = "0";
  LUAPhonebookPath = InsertStringA(v23, "PreferredCompression", v46);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 268;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v23, "PreferredSpeaker", *(unsigned int *)(v10 + 104));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 269;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v23, "PreferredMdmProtocol", *(unsigned int *)(v10 + 108));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 270;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  v47 = "1";
  if ( !*(_DWORD *)(v10 + 116) )
    v47 = "0";
  LUAPhonebookPath = InsertStringA(v23, "PreviewUserPw", v47);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 271;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  v48 = "1";
  if ( !*(_DWORD *)(v10 + 120) )
    v48 = "0";
  LUAPhonebookPath = InsertStringA(v23, "PreviewDomain", v48);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 272;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  v49 = "1";
  if ( !*(_DWORD *)(v10 + 124) )
    v49 = "0";
  LUAPhonebookPath = InsertStringA(v23, "PreviewPhoneNumber", v49);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 273;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  v50 = "1";
  if ( !*(_DWORD *)(v10 + 112) )
    v50 = "0";
  LUAPhonebookPath = InsertStringA(v23, "ShowDialingProgress", v50);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 274;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  v51 = "1";
  if ( !*(_DWORD *)(v10 + 48) )
    v51 = "0";
  LUAPhonebookPath = InsertStringA(v23, "ShowMonitorIconInTaskBar", v51);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 275;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v23, "CustomAuthKey", *(unsigned int *)(v10 + 192));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 276;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  v52 = *(_QWORD *)(v10 + 200);
  if ( v52 )
  {
    LUAPhonebookPath = InsertBinary(v23, "CustomAuthData", v52, *(unsigned int *)(v10 + 208));
    if ( LUAPhonebookPath )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
      {
        v113 = 277;
        goto LABEL_808;
      }
      return LUAPhonebookPath;
    }
  }
  LUAPhonebookPath = InsertLong(v23, "AuthRestrictions", *(unsigned int *)(v10 + 164));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 278;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  v53 = "1";
  if ( !*(_DWORD *)(v10 + 272) )
    v53 = "0";
  LUAPhonebookPath = InsertStringA(v23, "IpPrioritizeRemote", v53);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 279;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v23, "IpInterfaceMetric", *(unsigned int *)(v10 + 352));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 280;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  v54 = "1";
  if ( !*(_DWORD *)(v10 + 276) )
    v54 = "0";
  LUAPhonebookPath = InsertStringA(v23, "IpHeaderCompression", v54);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 281;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  v55 = L"0.0.0.0";
  if ( *(_QWORD *)(v10 + 280) )
    v55 = *(const WCHAR **)(v10 + 280);
  LUAPhonebookPath = InsertString(v23, "IpAddress", v55);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 282;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  v56 = L"0.0.0.0";
  if ( *(_QWORD *)(v10 + 288) )
    v56 = *(const WCHAR **)(v10 + 288);
  LUAPhonebookPath = InsertString(v23, "IpDnsAddress", v56);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 283;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  v57 = L"0.0.0.0";
  if ( *(_QWORD *)(v10 + 296) )
    v57 = *(const WCHAR **)(v10 + 296);
  LUAPhonebookPath = InsertString(v23, "IpDns2Address", v57);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 284;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  v58 = L"0.0.0.0";
  if ( *(_QWORD *)(v10 + 304) )
    v58 = *(const WCHAR **)(v10 + 304);
  LUAPhonebookPath = InsertString(v23, "IpWinsAddress", v58);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 285;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  v59 = L"0.0.0.0";
  if ( *(_QWORD *)(v10 + 312) )
    v59 = *(const WCHAR **)(v10 + 312);
  LUAPhonebookPath = InsertString(v23, "IpWins2Address", v59);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 286;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v23, "IpAssign", *(unsigned int *)(v10 + 320));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 287;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v23, "IpNameAssign", *(unsigned int *)(v10 + 324));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 288;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v23, "IpDnsFlags", *(unsigned int *)(v10 + 328));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 289;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v23, "IpNBTFlags", *(unsigned int *)(v10 + 332));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 290;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v23, "TcpWindowSize", *(unsigned int *)(v10 + 336));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 291;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v23, "UseFlags", *(unsigned int *)(v10 + 136));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 292;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v23, "IpSecFlags", *(unsigned int *)(v10 + 140));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 293;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertString(v23, "IpDnsSuffix", *(_QWORD *)(v10 + 344));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 294;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v23, "Ipv6Assign", *(unsigned int *)(v10 + 356));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 295;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  v60 = L"::";
  if ( *(_QWORD *)(v10 + 360) )
    v60 = *(const WCHAR **)(v10 + 360);
  LUAPhonebookPath = InsertString(v23, "Ipv6Address", v60);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 296;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v23, "Ipv6PrefixLength", *(unsigned int *)(v10 + 368));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 297;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  v61 = "1";
  if ( !*(_DWORD *)(v10 + 372) )
    v61 = "0";
  LUAPhonebookPath = InsertStringA(v23, "Ipv6PrioritizeRemote", v61);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 298;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v23, "Ipv6InterfaceMetric", *(unsigned int *)(v10 + 416));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 299;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v23, "Ipv6NameAssign", *(unsigned int *)(v10 + 376));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 300;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  v62 = L"::";
  if ( *(_QWORD *)(v10 + 384) )
    v62 = *(const WCHAR **)(v10 + 384);
  LUAPhonebookPath = InsertString(v23, "Ipv6DnsAddress", v62);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 301;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  v63 = L"::";
  if ( *(_QWORD *)(v10 + 392) )
    v63 = *(const WCHAR **)(v10 + 392);
  LUAPhonebookPath = InsertString(v23, "Ipv6Dns2Address", v63);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 302;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertBinary(v23, "Ipv6Prefix", v10 + 408, 8);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 303;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertBinary(v23, "Ipv6InterfaceId", v10 + 400, 8);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 304;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  v64 = "1";
  if ( !*(_DWORD *)(v10 + 544) )
    v64 = "0";
  LUAPhonebookPath = InsertStringA(v23, "DisableClassBasedDefaultRoute", v64);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 305;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  v65 = "1";
  if ( !*(_DWORD *)(v10 + 488) )
    v65 = "0";
  LUAPhonebookPath = InsertStringA(v23, "DisableMobility", v65);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 306;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v23, "NetworkOutageTime", *(unsigned int *)(v10 + 492));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v113 = 307;
      goto LABEL_808;
    }
    return LUAPhonebookPath;
  }
  if ( !(unsigned int)InsertString(v23, "IDI", *(_QWORD *)(v10 + 496)) )
  {
    if ( (unsigned int)InsertString(v23, "IDR", *(_QWORD *)(v10 + 504)) )
    {
      v116 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      {
        if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 310, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 1);
          v116 = WPP_GLOBAL_Control;
        }
        if ( v116 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && SBYTE4(v116[1].Blink) < 0
          && BYTE1(v116[1].Blink) >= 6u )
        {
          v117 = 311;
          goto LABEL_518;
        }
      }
      return 1;
    }
    v66 = "1";
    if ( !*(_DWORD *)(v10 + 512) )
      v66 = "0";
    v67 = InsertStringA(v23, "ImsConfig", v66);
    LUAPhonebookPath = v67;
    if ( v67 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      {
        if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 312, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v67);
          v4 = WPP_GLOBAL_Control;
        }
        if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 6u )
        {
          v113 = 313;
          goto LABEL_808;
        }
      }
      return LUAPhonebookPath;
    }
    v68 = InsertLong(v23, "IdiType", *(unsigned int *)(v10 + 516));
    LUAPhonebookPath = v68;
    if ( v68 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      {
        if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 314, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v68);
          v4 = WPP_GLOBAL_Control;
        }
        if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 6u )
        {
          v113 = 315;
          goto LABEL_808;
        }
      }
      return LUAPhonebookPath;
    }
    v69 = InsertLong(v23, "IdrType", *(unsigned int *)(v10 + 520));
    LUAPhonebookPath = v69;
    if ( v69 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      {
        if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 316, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v69);
          v4 = WPP_GLOBAL_Control;
        }
        if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 6u )
        {
          v113 = 317;
          goto LABEL_808;
        }
      }
      return LUAPhonebookPath;
    }
    LUAPhonebookPath = InsertLong(v23, "ProvisionType", *(unsigned int *)(v10 + 548));
    if ( LUAPhonebookPath )
      goto LABEL_803;
    LUAPhonebookPath = InsertString(v23, "PreSharedKey", *(_QWORD *)(v10 + 552));
    if ( LUAPhonebookPath )
      goto LABEL_803;
    v70 = "1";
    if ( !*(_DWORD *)(v10 + 128) )
      v70 = "0";
    LUAPhonebookPath = InsertStringA(v23, "CacheCredentials", v70);
    if ( LUAPhonebookPath )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
      {
        v113 = 318;
        goto LABEL_808;
      }
      return LUAPhonebookPath;
    }
    LUAPhonebookPath = InsertLong(v23, "NumCustomPolicy", *(unsigned int *)(v10 + 596));
    if ( LUAPhonebookPath )
      goto LABEL_803;
    v71 = *(_QWORD *)(v10 + 608);
    if ( v71 )
    {
      if ( *(_DWORD *)(v10 + 596) )
      {
        LUAPhonebookPath = InsertBinary(v23, "CustomIPSecPolicies", v71, *(unsigned int *)(v10 + 600));
        if ( LUAPhonebookPath )
          goto LABEL_803;
      }
    }
    LUAPhonebookPath = InsertLong(v23, "NumEku", *(unsigned int *)(v10 + 616));
    if ( LUAPhonebookPath )
      goto LABEL_803;
    v72 = *(_QWORD *)(v10 + 624);
    if ( v72 )
    {
      if ( *(_DWORD *)(v10 + 616) )
      {
        v73 = *(unsigned int *)(v10 + 620);
        if ( (_DWORD)v73 )
        {
          LUAPhonebookPath = InsertBinary(v23, "CertificateEKU", v72, v73);
          if ( LUAPhonebookPath )
            goto LABEL_803;
        }
      }
    }
    v74 = "1";
    if ( !*(_DWORD *)(v10 + 632) )
      v74 = "0";
    LUAPhonebookPath = InsertStringA(v23, "UseMachineRootCert", v74);
    if ( LUAPhonebookPath )
      goto LABEL_803;
    if ( *(_DWORD *)(v10 + 632) == 1 )
    {
      v75 = *(_QWORD *)(v10 + 648);
      if ( v75 )
      {
        v76 = *(unsigned int *)(v10 + 640);
        if ( (_DWORD)v76 )
        {
          LUAPhonebookPath = InsertBinary(v23, "RootCertificate", v75, v76);
          if ( LUAPhonebookPath )
            goto LABEL_803;
        }
      }
    }
    v77 = "1";
    if ( !*(_DWORD *)(v10 + 524) )
      v77 = "0";
    inserted = InsertStringA(v23, "Disable_IKEv2_Fragmentation", v77);
    LUAPhonebookPath = inserted;
    if ( inserted )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return LUAPhonebookPath;
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v114 = 319;
        goto LABEL_407;
      }
      goto LABEL_804;
    }
    v78 = "1";
    if ( !*(_DWORD *)(v10 + 528) )
      v78 = "0";
    inserted = InsertStringA(v23, "PlumbIKEv2TSAsRoutes", v78);
    LUAPhonebookPath = inserted;
    if ( inserted )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return LUAPhonebookPath;
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v114 = 320;
        goto LABEL_407;
      }
      goto LABEL_804;
    }
    LUAPhonebookPath = InsertLong(v23, "NumServers", *(unsigned int *)(v10 + 656));
    if ( LUAPhonebookPath )
      goto LABEL_803;
    if ( *(_QWORD *)(v10 + 664) )
    {
      if ( *(_DWORD *)(v10 + 656) )
      {
        inserted = CreateServerLists(v23);
        LUAPhonebookPath = inserted;
        if ( inserted )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            return LUAPhonebookPath;
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            v114 = 321;
            goto LABEL_407;
          }
          goto LABEL_804;
        }
      }
    }
    inserted = InsertLong(v23, "RouteVersion", 1);
    LUAPhonebookPath = inserted;
    if ( inserted )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return LUAPhonebookPath;
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v114 = 322;
        goto LABEL_407;
      }
      goto LABEL_804;
    }
    inserted = InsertLong(v23, "NumRoutes", *(unsigned int *)(v10 + 672));
    LUAPhonebookPath = inserted;
    if ( inserted )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return LUAPhonebookPath;
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v114 = 323;
        goto LABEL_407;
      }
      goto LABEL_804;
    }
    v79 = *(_QWORD *)(v10 + 680);
    if ( v79 )
    {
      if ( *(_DWORD *)(v10 + 672) )
      {
        inserted = InsertBinary(v23, "Routes", v79, *(unsigned int *)(v10 + 676));
        LUAPhonebookPath = inserted;
        if ( inserted )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            return LUAPhonebookPath;
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            v114 = 324;
            goto LABEL_407;
          }
          goto LABEL_804;
        }
      }
    }
    inserted = InsertLong(v23, "NumNrptRules", *(unsigned int *)(v10 + 688));
    LUAPhonebookPath = inserted;
    if ( inserted )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return LUAPhonebookPath;
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v114 = 325;
        goto LABEL_407;
      }
      goto LABEL_804;
    }
    v80 = *(_QWORD *)(v10 + 696);
    if ( v80 )
    {
      if ( *(_DWORD *)(v10 + 688) )
      {
        inserted = InsertBinary(v23, "NrptRules", v80, *(unsigned int *)(v10 + 692));
        LUAPhonebookPath = inserted;
        if ( inserted )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            return LUAPhonebookPath;
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            v114 = 326;
            goto LABEL_407;
          }
          goto LABEL_804;
        }
      }
    }
    v81 = "1";
    if ( !*(_DWORD *)(v10 + 704) )
      v81 = "0";
    inserted = InsertStringA(v23, "AutoTiggerCapable", v81);
    LUAPhonebookPath = inserted;
    if ( inserted )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return LUAPhonebookPath;
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v114 = 327;
        goto LABEL_407;
      }
      goto LABEL_804;
    }
    LUAPhonebookPath = InsertLong(v23, "NumAppIds", *(unsigned int *)(v10 + 728));
    if ( LUAPhonebookPath )
      goto LABEL_803;
    v83 = *(_QWORD *)(v10 + 736);
    if ( v83 && *(_DWORD *)(v10 + 728) )
    {
      inserted = CreateDtlList(v82, v83, *(unsigned int *)(v10 + 732));
      LUAPhonebookPath = inserted;
      if ( inserted )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          return LUAPhonebookPath;
        if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          v114 = 328;
          goto LABEL_407;
        }
        goto LABEL_804;
      }
      v84 = InsertStringList(v23, "ApplicationIds", 0);
      LUAPhonebookPath = v84;
      if ( v84 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 329, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v84);
        }
        DtlDestroyList(0);
        goto LABEL_803;
      }
      DtlDestroyList(0);
    }
    LUAPhonebookPath = InsertLong(v23, "NumClassicAppIds", *(unsigned int *)(v10 + 708));
    if ( LUAPhonebookPath )
      goto LABEL_803;
    v86 = *(_QWORD *)(v10 + 720);
    if ( v86 && *(_DWORD *)(v10 + 708) )
    {
      inserted = CreateDtlList(v85, v86, *(unsigned int *)(v10 + 712));
      LUAPhonebookPath = inserted;
      if ( inserted )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          return LUAPhonebookPath;
        if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          v114 = 330;
          goto LABEL_407;
        }
        goto LABEL_804;
      }
      LUAPhonebookPath = InsertStringList(v23, "ClassicApplicationIds", 0);
      if ( LUAPhonebookPath )
      {
        DtlDestroyList(0);
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          return LUAPhonebookPath;
        if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          goto LABEL_804;
        v114 = 331;
        v115 = LUAPhonebookPath;
LABEL_408:
        WPP_SF_d(v4[1].Flink, v114, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v115);
        goto LABEL_803;
      }
      DtlDestroyList(0);
    }
    inserted = InsertString(v23, "SecurityDescriptor", *(_QWORD *)(v10 + 744));
    LUAPhonebookPath = inserted;
    if ( inserted )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return LUAPhonebookPath;
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v114 = 332;
        goto LABEL_407;
      }
      goto LABEL_804;
    }
    LUAPhonebookPath = InsertString(v23, "ApnInfoProviderId", *(_QWORD *)(v10 + 864));
    if ( LUAPhonebookPath )
      goto LABEL_803;
    LUAPhonebookPath = InsertString(v23, "ApnInfoUsername", *(_QWORD *)(v10 + 880));
    if ( LUAPhonebookPath )
      goto LABEL_803;
    LUAPhonebookPath = InsertString(v23, "ApnInfoPassword", *(_QWORD *)(v10 + 888));
    if ( LUAPhonebookPath )
      goto LABEL_803;
    LUAPhonebookPath = InsertString(v23, "ApnInfoAccessPoint", *(_QWORD *)(v10 + 872));
    if ( LUAPhonebookPath )
      goto LABEL_803;
    LUAPhonebookPath = InsertLong(v23, "ApnInfoAuthentication", *(unsigned int *)(v10 + 900));
    if ( LUAPhonebookPath )
      goto LABEL_803;
    v87 = "1";
    if ( !*(_DWORD *)(v10 + 896) )
      v87 = "0";
    LUAPhonebookPath = InsertStringA(v23, "ApnInfoCompression", v87);
    if ( LUAPhonebookPath )
      goto LABEL_803;
    v88 = "1";
    if ( !*(_DWORD *)(v10 + 904) )
      v88 = "0";
    LUAPhonebookPath = InsertStringA(v23, "DeviceComplianceEnabled", v88);
    if ( LUAPhonebookPath )
      goto LABEL_803;
    v89 = "1";
    if ( !*(_DWORD *)(v10 + 912) )
      v89 = "0";
    LUAPhonebookPath = InsertStringA(v23, "DeviceComplianceSsoEnabled", v89);
    if ( LUAPhonebookPath )
      goto LABEL_803;
    LUAPhonebookPath = InsertString(v23, "DeviceComplianceSsoEku", *(_QWORD *)(v10 + 920));
    if ( LUAPhonebookPath )
      goto LABEL_803;
    LUAPhonebookPath = InsertString(v23, "DeviceComplianceSsoIssuer", *(_QWORD *)(v10 + 928));
    if ( LUAPhonebookPath )
      goto LABEL_803;
    LUAPhonebookPath = InsertLong(v23, "FlagsSet", *(unsigned int *)(v10 + 952));
    if ( LUAPhonebookPath )
      goto LABEL_803;
    LUAPhonebookPath = InsertLong(v23, "Options", *(unsigned int *)(v10 + 956));
    if ( LUAPhonebookPath )
      goto LABEL_803;
    v90 = "1";
    if ( !*(_DWORD *)(v10 + 788) )
      v90 = "0";
    LUAPhonebookPath = InsertStringA(v23, "DisableDefaultDnsSuffixes", v90);
    if ( LUAPhonebookPath )
      goto LABEL_803;
    LUAPhonebookPath = InsertLong(v23, "NumTrustedNetworks", *(unsigned int *)(v10 + 792));
    if ( LUAPhonebookPath )
      goto LABEL_803;
    v91 = *(_QWORD *)(v10 + 800);
    if ( v91 )
    {
      if ( *(_DWORD *)(v10 + 792) )
      {
        LUAPhonebookPath = InsertBinary(v23, "TrustedNetworks", v91, *(unsigned int *)(v10 + 796));
        if ( LUAPhonebookPath )
          goto LABEL_803;
      }
    }
    v92 = *(_QWORD *)(v10 + 760);
    if ( v92 )
    {
      LUAPhonebookPath = InsertBinary(v23, "ThirdPartyProfileInfo", v92, *(unsigned int *)(v10 + 752));
      if ( LUAPhonebookPath )
        goto LABEL_803;
    }
    LUAPhonebookPath = InsertLong(v23, "NumDnsSearchSuffixes", *(unsigned int *)(v10 + 768));
    if ( LUAPhonebookPath )
      goto LABEL_803;
    v93 = *(_QWORD *)(v10 + 776);
    if ( v93 )
    {
      LUAPhonebookPath = InsertBinary(v23, "DnsSuffixSearchList", v93, *(unsigned int *)(v10 + 772));
      if ( LUAPhonebookPath )
        goto LABEL_803;
    }
    v94 = "1";
    if ( !*(_DWORD *)(v10 + 784) )
      v94 = "0";
    LUAPhonebookPath = InsertStringA(v23, "PowershellCreatedProfile", v94);
    if ( LUAPhonebookPath )
      goto LABEL_803;
    LUAPhonebookPath = InsertLong(v23, "ProxyFlags", *(unsigned int *)(v10 + 560));
    if ( LUAPhonebookPath )
      goto LABEL_803;
    v95 = "1";
    if ( !*(_DWORD *)(v10 + 820) )
      v95 = "0";
    LUAPhonebookPath = InsertStringA(v23, "ProxySettingsModified", v95);
    if ( LUAPhonebookPath )
      goto LABEL_803;
    if ( (*(_BYTE *)(v10 + 560) & 2) != 0 )
    {
      LUAPhonebookPath = InsertString(v23, "Proxy", *(_QWORD *)(v10 + 576));
      if ( LUAPhonebookPath )
        goto LABEL_803;
      LUAPhonebookPath = InsertString(v23, "ExcludeList", *(_QWORD *)(v10 + 584));
      if ( LUAPhonebookPath )
        goto LABEL_803;
      v96 = "1";
      if ( !*(_DWORD *)(v10 + 592) )
        v96 = "0";
      LUAPhonebookPath = InsertStringA(v23, "BypassProxyForLocal", v96);
      if ( LUAPhonebookPath )
        goto LABEL_803;
    }
    if ( (*(_BYTE *)(v10 + 560) & 4) != 0 )
    {
      LUAPhonebookPath = InsertString(v23, "AutoConfigScript", *(_QWORD *)(v10 + 568));
      if ( LUAPhonebookPath )
        goto LABEL_803;
    }
    LUAPhonebookPath = InsertString(v23, "ProvisioningAuthority", *(_QWORD *)(v10 + 808));
    if ( LUAPhonebookPath )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
      {
        v113 = 333;
        goto LABEL_808;
      }
      return LUAPhonebookPath;
    }
    v97 = "1";
    if ( !*(_DWORD *)(v10 + 816) )
      v97 = "0";
    LUAPhonebookPath = InsertStringA(v23, "AuthTypeOTP", v97);
    if ( LUAPhonebookPath )
      goto LABEL_803;
    v98 = "1";
    if ( !*(_DWORD *)(v10 + 824) )
      v98 = "0";
    LUAPhonebookPath = InsertStringA(v23, "GREKeyDefined", v98);
    if ( LUAPhonebookPath )
      goto LABEL_803;
    if ( *(_DWORD *)(v10 + 824) )
    {
      LUAPhonebookPath = InsertULong(v23, "GREKey", *(unsigned int *)(v10 + 828));
      if ( LUAPhonebookPath )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
        {
          v113 = 334;
          goto LABEL_808;
        }
        return LUAPhonebookPath;
      }
    }
    LUAPhonebookPath = InsertLong(v23, "NumPerAppTrafficFilters", *(unsigned int *)(v10 + 832));
    if ( LUAPhonebookPath )
      goto LABEL_803;
    v99 = *(_QWORD *)(v10 + 840);
    if ( v99 )
    {
      if ( *(_DWORD *)(v10 + 832) )
      {
        LUAPhonebookPath = InsertBinary(v23, "PerAppTrafficFilters", v99, *(unsigned int *)(v10 + 836));
        if ( LUAPhonebookPath )
          goto LABEL_803;
      }
    }
    v100 = "1";
    if ( !*(_DWORD *)(v10 + 848) )
      v100 = "0";
    LUAPhonebookPath = InsertStringA(v23, "AlwaysOnCapable", v100);
    if ( LUAPhonebookPath )
      goto LABEL_803;
    v101 = "1";
    if ( !*(_DWORD *)(v10 + 856) )
      v101 = "0";
    inserted = InsertStringA(v23, "DeviceTunnel", v101);
    LUAPhonebookPath = inserted;
    if ( inserted )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return LUAPhonebookPath;
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v114 = 335;
        goto LABEL_407;
      }
      goto LABEL_804;
    }
    v102 = "1";
    if ( !*(_DWORD *)(v10 + 852) )
      v102 = "0";
    LUAPhonebookPath = InsertStringA(v23, "PrivateNetwork", v102);
    if ( LUAPhonebookPath )
      goto LABEL_803;
    v103 = *(_QWORD *)(v10 + 944);
    if ( v103 )
    {
      v104 = *(unsigned int *)(v10 + 936);
      if ( (_DWORD)v104 )
      {
        LUAPhonebookPath = InsertBinary(v23, "PluginStorage", v103, v104);
        if ( LUAPhonebookPath )
          goto LABEL_803;
      }
    }
    LUAPhonebookPath = InsertString(v23, "ManagementApp", *(_QWORD *)(v10 + 960));
    if ( LUAPhonebookPath )
      goto LABEL_803;
    if ( *(_DWORD *)(v10 + 168) == 15 )
    {
      LUAPhonebookPath = InsertULong(v23, "ProtocolListLength", *(unsigned int *)(v10 + 968));
      if ( LUAPhonebookPath )
        goto LABEL_803;
      LUAPhonebookPath = InsertBinary(v23, "ProtocolList", v10 + 972, 16);
      if ( LUAPhonebookPath )
        goto LABEL_803;
      LUAPhonebookPath = InsertULong(v23, "ProtocolListRetryTimeInHours", *(unsigned int *)(v10 + 988));
      if ( LUAPhonebookPath )
        goto LABEL_803;
      LUAPhonebookPath = InsertULong(v23, "ProtocolListCurrentProtocol", *(unsigned int *)(v10 + 992));
      if ( LUAPhonebookPath )
        goto LABEL_803;
      LUAPhonebookPath = InsertULong(v23, "ProtocolListTimeOfLastProtocolSelectionLow", *(unsigned int *)(v10 + 1000));
      if ( LUAPhonebookPath )
        goto LABEL_803;
      LUAPhonebookPath = InsertULong(v23, "ProtocolListTimeOfLastProtocolSelectionHigh", *(unsigned int *)(v10 + 1004));
      if ( LUAPhonebookPath )
        goto LABEL_803;
    }
    InsertNetComponents(v23, *(_QWORD *)(v10 + 264));
    v105 = **(_QWORD **)(v10 + 32);
    if ( v105 )
    {
      do
      {
        v106 = *(_QWORD *)(v105 + 16);
        LUAPhonebookPath = InsertGroup(v23, "MEDIA", *(_QWORD *)(v106 + 24));
        if ( LUAPhonebookPath )
          break;
        LUAPhonebookPath = InsertString(v23, "Port", *(_QWORD *)v106);
        if ( LUAPhonebookPath )
          break;
        v109 = *(_QWORD *)(v106 + 16);
        if ( v109 )
        {
          LUAPhonebookPath = InsertString(v23, "Device", v109);
          if ( LUAPhonebookPath )
            break;
        }
        if ( *(_DWORD *)(v106 + 40) == 3 || (*(_BYTE *)(v106 + 48) & 4) != 0 )
        {
          LUAPhonebookPath = InsertLong(v23, "ConnectBPS", *(unsigned int *)(v106 + 104));
          if ( LUAPhonebookPath )
            break;
        }
        LOBYTE(v108) = 2;
        LOBYTE(v107) = 48;
        rasFindLine(v23, v107, 2, v108, 2);
        LUAPhonebookPath = InsertDeviceList(a1, v23, v10, v106);
        if ( LUAPhonebookPath )
          break;
        v105 = *(_QWORD *)(v105 + 8);
      }
      while ( v105 );
      v9 = v122;
    }
    v5 = 0;
    if ( *(_DWORD *)(v10 + 548) )
    {
      LUAPhonebookPath = InsertGroup(v23, "PROXYSETTINGS", 0);
      if ( LUAPhonebookPath )
        goto LABEL_803;
      LUAPhonebookPath = InsertString(v23, "AutoConfigScript", *(_QWORD *)(v10 + 568));
      if ( LUAPhonebookPath )
        goto LABEL_803;
      LUAPhonebookPath = InsertString(v23, "Proxy", *(_QWORD *)(v10 + 576));
      if ( LUAPhonebookPath )
        goto LABEL_803;
      LUAPhonebookPath = InsertLong(v23, "ProxyFlags", *(unsigned int *)(v10 + 560));
      if ( LUAPhonebookPath )
        goto LABEL_803;
      v110 = *(const WCHAR **)(v10 + 584);
      memset_0(MultiByteStr, 0, 0x101u);
      v111 = lstrlenW(v110);
      if ( v111 )
      {
        while ( 1 )
        {
          memset_0(MultiByteStr, 0, 0x101u);
          cbMultiByte = v111;
          if ( v111 >= 0x100 )
            cbMultiByte = 256;
          if ( !WideCharToMultiByte(0xFDE9u, 0, v110, -1, MultiByteStr, cbMultiByte, 0, 0) )
            GetLastError();
          LUAPhonebookPath = InsertStringA(v23, "ExcludeList", MultiByteStr);
          if ( LUAPhonebookPath )
            goto LABEL_803;
          v110 += cbMultiByte;
          v111 -= cbMultiByte;
          if ( !v111 )
          {
            v5 = 0;
            goto LABEL_388;
          }
        }
      }
      v5 = 0;
      LUAPhonebookPath = InsertStringA(v23, "ExcludeList", MultiByteStr);
      if ( LUAPhonebookPath )
        goto LABEL_803;
LABEL_388:
      LUAPhonebookPath = 0;
    }
    *(_DWORD *)(v10 + 532) = 0;
    v4 = WPP_GLOBAL_Control;
    goto LABEL_46;
  }
  v116 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 308, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 1);
      v116 = WPP_GLOBAL_Control;
    }
    if ( v116 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v116[1].Blink) < 0 && BYTE1(v116[1].Blink) >= 6u )
    {
      v117 = 309;
LABEL_518:
      WPP_SF_d(v116[1].Flink, v117, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 1);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18006d96c  mov     [rsp-8+arg_10], rbx
0x18006d971  push    rbp
0x18006d972  push    rsi
0x18006d973  push    rdi
0x18006d974  push    r12
0x18006d976  push    r13
0x18006d978  push    r14
0x18006d97a  push    r15
0x18006d97c  lea     rbp, [rsp-90h]
0x18006d984  sub     rsp, 190h
0x18006d98b  mov     rax, cs:__security_cookie
0x18006d992  xor     rax, rsp
0x18006d995  mov     [rbp+0C0h+var_40], rax
0x18006d99c  mov     rsi, rdx
0x18006d99f  mov     [rsp+1C0h+var_158], rdx
0x18006d9a4  mov     rbx, rcx
0x18006d9a7  mov     [rsp+1C0h+var_160], rcx
0x18006d9ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d9b3  lea     r14, WPP_GLOBAL_Control
0x18006d9ba  cmp     rcx, r14
0x18006d9bd  jz      short loc_18006D9E7
0x18006d9bf  test    byte ptr [rcx+1Ch], 80h
0x18006d9c3  jz      short loc_18006D9E7
0x18006d9c5  cmp     byte ptr [rcx+19h], 6
0x18006d9c9  jb      short loc_18006D9E7
0x18006d9cb  mov     rcx, [rcx+10h]
0x18006d9cf  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006d9d6  mov     edx, 0E6h
0x18006d9db  call    WPP_SF_
0x18006d9e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d9e7  mov     rax, [rbx+10h]
0x18006d9eb  xor     r15d, r15d
0x18006d9ee  mov     edx, r15d
0x18006d9f1  mov     edi, r15d
0x18006d9f4  mov     [rsp+1C0h+var_180], edx
0x18006d9f8  mov     r8, [rax]
0x18006d9fb  mov     [rsp+1C0h+var_170], r8
0x18006da00  test    r8, r8
0x18006da03  jz      loc_180070AF8
0x18006da09  mov     r13d, r15d
0x18006da0c  mov     [rsp+1C0h+var_168], r15
0x18006da11  mov     rsi, [r8+10h]
0x18006da15  mov     r9d, 100h
0x18006da1b  lea     r12, [rsi+21Ch]
0x18006da22  cmp     [rsi+214h], r15d
0x18006da29  jnz     short loc_18006DA35
0x18006da2b  cmp     [r12], r15d
0x18006da2f  jz      loc_18006DC36
0x18006da35  mov     eax, [rbx+20h]
0x18006da38  and     eax, r9d
0x18006da3b  jz      short loc_18006DA93
0x18006da3d  cmp     [rsi+224h], r15d
0x18006da44  jz      short loc_18006DA93
0x18006da46  cmp     rcx, r14
0x18006da49  jz      short loc_18006DA79
0x18006da4b  test    byte ptr [rcx+1Ch], 80h
0x18006da4f  jz      short loc_18006DA79
0x18006da51  cmp     byte ptr [rcx+19h], 5
0x18006da55  jb      short loc_18006DA79
0x18006da57  mov     r9, [rsi+8]
0x18006da5b  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006da62  mov     rcx, [rcx+10h]
0x18006da66  mov     edx, 0E7h
0x18006da6b  call    WPP_SF_S
0x18006da70  mov     edx, [rsp+1C0h+var_180]
0x18006da74  mov     r8, [rsp+1C0h+var_170]
0x18006da79  mov     [rsi+214h], r15d
0x18006da80  mov     [rsi+21Ch], r15d
0x18006da87  mov     rcx, cs:WPP_GLOBAL_Control
0x18006da8e  jmp     loc_18006DC36
0x18006da93  mov     edx, [rsi]
0x18006da95  cmp     edx, 0FFFFFFFFh
0x18006da98  jnz     loc_18006DC62
0x18006da9e  mov     [rsp+1C0h+hMem], r15
0x18006daa3  cmp     [rsi+224h], r15d
0x18006daaa  jz      short loc_18006DAEA
0x18006daac  cmp     dword ptr [rbx+8], 4
0x18006dab0  mov     r15d, 1
0x18006dab6  jz      short loc_18006DAEA
0x18006dab8  mov     rdx, [rsi+8]; STRSAFE_LPCWSTR
0x18006dabc  lea     r8, [rsp+1C0h+hMem]
0x18006dac1  mov     rcx, [rbx]; pszSrc
0x18006dac4  call    GetProvisionedProfilePath
0x18006dac9  mov     edi, eax
0x18006dacb  test    eax, eax
0x18006dacd  jnz     short loc_18006DB08
0x18006dacf  mov     r14, [rsp+1C0h+hMem]
0x18006dad4  mov     rbx, [rbx+30h]
0x18006dad8  xor     r13d, r13d
0x18006dadb  mov     [rsp+1C0h+var_168], r13
0x18006dae0  test    rbx, rbx
0x18006dae3  jz      short loc_18006DB5E
0x18006dae5  mov     rbx, [rbx]
0x18006dae8  jmp     short loc_18006DB54
0x18006daea  mov     rcx, [rbx]; pszSrc
0x18006daed  test    eax, eax
0x18006daef  jz      short loc_18006DB12
0x18006daf1  lea     rdx, [rsp+1C0h+hMem]
0x18006daf6  call    GetLUAPhonebookPath
0x18006dafb  mov     edi, eax
0x18006dafd  test    eax, eax
0x18006daff  jnz     short loc_18006DB08
0x18006db01  mov     r14, [rsp+1C0h+hMem]
0x18006db06  jmp     short loc_18006DB1C
0x18006db08  mov     r14, [rsp+1C0h+hMem]
0x18006db0d  jmp     loc_18006DBDA
0x18006db12  xor     edi, edi
0x18006db14  call    StrDup
0x18006db19  mov     r14, rax
0x18006db1c  test    r14, r14
0x18006db1f  jnz     short loc_18006DAD4
0x18006db21  lea     edi, [r14+8]
0x18006db25  jmp     loc_18006DBDA
0x18006db2a  mov     r13, [rbx+10h]
0x18006db2e  mov     [rsp+1C0h+var_168], r13
0x18006db33  test    r13, r13
0x18006db36  jz      short loc_18006DB5E
0x18006db38  mov     rcx, [r13+8]; lpString1
0x18006db3c  mov     rdx, r14; lpString2
0x18006db3f  call    CompareStringWrapW
0x18006db44  test    eax, eax
0x18006db46  jz      short loc_18006DB59
0x18006db48  mov     rbx, [rbx+8]
0x18006db4c  xor     r13d, r13d
0x18006db4f  mov     [rsp+1C0h+var_168], r13
0x18006db54  test    rbx, rbx
0x18006db57  jnz     short loc_18006DB2A
0x18006db59  test    r13, r13
0x18006db5c  jnz     short loc_18006DBDA
0x18006db5e  mov     rax, [rsp+1C0h+var_160]
0x18006db63  mov     r9d, r15d
0x18006db66  mov     r15, [rsp+1C0h+var_160]
0x18006db6b  mov     rdx, r14
0x18006db6e  mov     dword ptr [rsp+1C0h+hMem], 0FFFFFFFFh
0x18006db76  mov     dword ptr [rsp+1C0h+lpMultiByteStr], 1; int
0x18006db7e  mov     rax, [rax+30h]
0x18006db82  mov     r8d, [r15+8]
0x18006db86  mov     rcx, [r15+28h]; hToken
0x18006db8a  mov     ebx, [rax+10h]
0x18006db8d  call    CreateProfileDirAndSetAcls
0x18006db92  mov     edi, eax
0x18006db94  test    eax, eax
0x18006db96  jnz     short loc_18006DBDA
0x18006db98  mov     edx, [r15+20h]
0x18006db9c  lea     r8, [rsp+1C0h+hMem]
0x18006dba1  xor     r9d, r9d
0x18006dba4  mov     rcx, r14; lpFileName
0x18006dba7  call    LoadFile
0x18006dbac  mov     edi, eax
0x18006dbae  test    eax, eax
0x18006dbb0  jnz     short loc_18006DBDA
0x18006dbb2  mov     ecx, dword ptr [rsp+1C0h+hMem]
0x18006dbb6  inc     ebx
0x18006dbb8  mov     r8d, ebx
0x18006dbbb  mov     rdx, r14
0x18006dbbe  call    CreateHRasfileNode
0x18006dbc3  mov     [rsi], ebx
0x18006dbc5  mov     rdx, rax
0x18006dbc8  mov     rcx, [r15+30h]
0x18006dbcc  call    DtlAddNodeLast
0x18006dbd1  mov     r13, [rdx+10h]
0x18006dbd5  mov     [rsp+1C0h+var_168], r13
0x18006dbda  xor     r15d, r15d
0x18006dbdd  test    r14, r14
0x18006dbe0  jz      short loc_18006DBEB
0x18006dbe2  mov     rcx, r14; hMem
0x18006dbe5  call    cs:__imp_GlobalFree
0x18006dbeb  test    edi, edi
0x18006dbed  jz      short loc_18006DC52
0x18006dbef  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dbf6  lea     r14, WPP_GLOBAL_Control
0x18006dbfd  cmp     rcx, r14
0x18006dc00  jz      short loc_18006DC2D
0x18006dc02  test    byte ptr [rcx+1Ch], 80h
0x18006dc06  jz      short loc_18006DC2D
0x18006dc08  cmp     byte ptr [rcx+19h], 2
0x18006dc0c  jb      short loc_18006DC2D
0x18006dc0e  mov     edx, 0E8h
0x18006dc13  mov     rcx, [rcx+10h]
0x18006dc17  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006dc1e  mov     r9d, edi
0x18006dc21  call    WPP_SF_d
0x18006dc26  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dc2d  mov     edx, [rsp+1C0h+var_180]
0x18006dc31  mov     r8, [rsp+1C0h+var_170]
0x18006dc36  mov     r8, [r8+8]
0x18006dc3a  mov     [rsp+1C0h+var_170], r8
0x18006dc3f  test    r8, r8
0x18006dc42  jz      loc_180070AE6
0x18006dc48  mov     rbx, [rsp+1C0h+var_160]
0x18006dc4d  jmp     loc_18006DA11
0x18006dc52  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dc59  lea     r14, WPP_GLOBAL_Control
0x18006dc60  jmp     short loc_18006DC9D
0x18006dc62  mov     rax, [rbx+30h]
0x18006dc66  mov     r13, r15
0x18006dc69  mov     [rsp+1C0h+var_168], r15
0x18006dc6e  test    rax, rax
0x18006dc71  jz      short loc_18006DC9D
0x18006dc73  mov     rax, [rax]
0x18006dc76  jmp     short loc_18006DC98
0x18006dc78  mov     r13, [rax+10h]
0x18006dc7c  mov     [rsp+1C0h+var_168], r13
0x18006dc81  test    r13, r13
0x18006dc84  jz      short loc_18006DCA2
0x18006dc86  cmp     [r13+10h], edx
0x18006dc8a  jz      short loc_18006DC9D
0x18006dc8c  mov     rax, [rax+8]
0x18006dc90  mov     r13, r15
0x18006dc93  mov     [rsp+1C0h+var_168], r15
0x18006dc98  test    rax, rax
0x18006dc9b  jnz     short loc_18006DC78
0x18006dc9d  test    r13, r13
0x18006dca0  jnz     short loc_18006DCFF
0x18006dca2  cmp     rcx, r14
0x18006dca5  jz      short loc_18006DCD3
0x18006dca7  test    byte ptr [rcx+1Ch], 80h
0x18006dcab  jz      short loc_18006DCD3
0x18006dcad  cmp     byte ptr [rcx+19h], 5
0x18006dcb1  jb      short loc_18006DCD3
0x18006dcb3  mov     r9, [rsi+8]
0x18006dcb7  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006dcbe  mov     rcx, [rcx+10h]
0x18006dcc2  mov     edx, 0E9h
0x18006dcc7  call    WPP_SF_S
0x18006dccc  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dcd3  mov     edi, 26Eh
0x18006dcd8  cmp     rcx, r14
0x18006dcdb  jz      loc_18006DC2D
0x18006dce1  test    byte ptr [rcx+1Ch], 80h
0x18006dce5  jz      loc_18006DC2D
0x18006dceb  cmp     byte ptr [rcx+19h], 2
0x18006dcef  jb      loc_18006DC2D
0x18006dcf5  mov     edx, 0EAh
0x18006dcfa  jmp     loc_18006DC13
0x18006dcff  mov     ebx, [r13+0]
0x18006dd03  mov     rcx, rsi
0x18006dd06  call    UpdateEntryTimeStamp
0x18006dd0b  mov     rcx, [rsi+8]; lpWideCharStr
0x18006dd0f  call    StrDupAFromTInternal
0x18006dd14  mov     r14, rax
0x18006dd17  test    rax, rax
0x18006dd1a  jz      loc_180070B98
0x18006dd20  mov     rdx, rax
0x18006dd23  mov     ecx, ebx
0x18006dd25  call    RasfileFindSectionLine
0x18006dd2a  test    eax, eax
0x18006dd2c  jz      short loc_18006DD35
0x18006dd2e  mov     ecx, ebx
0x18006dd30  call    DeleteCurrentSection
0x18006dd35  mov     rcx, r14; hMem
0x18006dd38  call    cs:__imp_GlobalFree
0x18006dd3e  cmp     [r12], r15d
0x18006dd42  jnz     loc_18006F5ED
0x18006dd48  mov     r12d, 2
0x18006dd4e  xor     r8d, r8d
0x18006dd51  mov     r9b, r12b
0x18006dd54  mov     byte ptr [rsp+1C0h+lpMultiByteStr], r12b
0x18006dd59  mov     dl, 3Fh ; '?'
0x18006dd5b  mov     ecx, ebx
0x18006dd5d  call    rasFindLine
0x18006dd62  mov     rdx, [rsi+8]
0x18006dd66  mov     ecx, ebx
0x18006dd68  call    InsertSection
0x18006dd6d  mov     edi, eax
0x18006dd6f  test    eax, eax
0x18006dd71  jnz     loc_180070AB9
0x18006dd77  lea     r8d, [r12-1]
0x18006dd7c  mov     ecx, ebx
0x18006dd7e  lea     rdx, aEncoding; "Encoding"
0x18006dd85  call    InsertLong
0x18006dd8a  mov     edi, eax
0x18006dd8c  test    eax, eax
0x18006dd8e  jnz     loc_180070A84
0x18006dd94  lea     r8d, [r12+6]
0x18006dd99  mov     ecx, ebx
0x18006dd9b  lea     rdx, aPbversion; "PBVersion"
0x18006dda2  call    InsertLong
0x18006dda7  mov     edi, eax
0x18006dda9  test    eax, eax
0x18006ddab  jnz     loc_180070A4F
0x18006ddb1  mov     r8d, [rsi+18h]
0x18006ddb5  lea     rdx, aType; "Type"
0x18006ddbc  mov     ecx, ebx
0x18006ddbe  call    InsertLong
0x18006ddc3  mov     edi, eax
0x18006ddc5  test    eax, eax
0x18006ddc7  jnz     loc_180070A1A
0x18006ddcd  cmp     [rsi+0B0h], r15d
0x18006ddd4  lea     r8, a1; "1"
0x18006dddb  lea     r14, a0; "0"
0x18006dde2  mov     ecx, ebx
0x18006dde4  cmovz   r8, r14
0x18006dde8  lea     rdx, aAutologon; "AutoLogon"
0x18006ddef  call    InsertStringA
0x18006ddf4  mov     edi, eax
0x18006ddf6  test    eax, eax
0x18006ddf8  jnz     loc_1800709E5
0x18006ddfe  cmp     [rsi+0B4h], r15d
0x18006de05  lea     r8, a1; "1"
  ... truncated ...
```
