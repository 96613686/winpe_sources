# ModifyEntryList

- ea: `0x1800714c0`
- end: `0x18007473f`
- name: `ModifyEntryList`
- size: `12927`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18007f488`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18000ebe8`
- `0x18005fbf4`
- `0x18005fc8c`
- `0x180060298`
- `0x1800606cc`
- `0x180060830`
- `0x18006aa50`
- `0x18006ae48`
- `0x18006b640`
- `0x18006e908`
- `0x18006eae0`
- `0x18007006c`
- `0x1800701b0`
- `0x18007022c`
- `0x1800708a4`
- `0x180070b18`
- `0x180070c34`
- `0x180070d64`
- `0x180070ed0`
- `0x18007127c`
- `0x1800714c0`
- `0x18007fc60`
- `0x18007ff30`
- `0x180080430`
- `0x180081228`
- `0x180085100`
- `0x180093498`
- `0x180094810`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073109`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073109`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180071739`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180071892`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180071739`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180071892`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800730f9`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800730f9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180073071`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180073071`

## string_xrefs

- `0x180071b52`: `RedialAttempts`
- `0x180071bb6`: `RedialOnLinkFailure`
- `0x180071bf8`: `CustomDialDll`
- `0x180071a2e`: `ExcludedProtocols`
- `0x180071a54`: `LcpExtensions`
- `0x180071a9d`: `SwCompression`
- `0x180071ac7`: `NegotiateMultilinkAlways`
- `0x180071e24`: `PreferredProtocol`
- `0x180071e4b`: `PreferredCompression`
- `0x180071c36`: `CustomRasDialDll`
- `0x180071c58`: `ForceSecureCompartment`
- `0x180072022`: `IpHeaderCompression`
- `0x180071e87`: `PreferredMdmProtocol`
- `0x180071f46`: `ShowMonitorIconInTaskBar`
- `0x180072445`: `ImsConfig`
- `0x1800724eb`: `CacheCredentials`
- `0x18007298a`: `ApnInfoCompression`
- `0x1800729ae`: `DeviceComplianceEnabled`
- `0x1800729d8`: `DeviceComplianceSsoEnabled`
- `0x1800729fb`: `DeviceComplianceSsoEku`
- `0x180072a1a`: `DeviceComplianceSsoIssuer`
- `0x1800728bc`: `SecurityDescriptor`
- `0x180072938`: `ApnInfoAccessPoint`
- `0x180072c56`: `AutoConfigScript`
- `0x180072fff`: `AutoConfigScript`
- `0x180072b70`: `PowershellCreatedProfile`
- `0x180072e62`: `ProtocolList`
- `0x180072e7f`: `ProtocolListRetryTimeInHours`
- `0x180072e9e`: `ProtocolListCurrentProtocol`
- `0x180072ebd`: `ProtocolListTimeOfLastProtocolSelectionLow`
- `0x180072edc`: `ProtocolListTimeOfLastProtocolSelectionHigh`
- `0x180072df2`: `PluginStorage`
- `0x180072e3d`: `ProtocolListLength`

## pseudocode

```c
__int64 __fastcall ModifyEntryList(__int64 a1, unsigned int *a2)
{
  unsigned int *v2; // rsi
  __int64 v3; // rbx
  struct _LIST_ENTRY *v4; // rcx
  int v5; // edx
  unsigned int LUAPhonebookPath; // edi
  __int64 v7; // r8
  PCNZWCH *v8; // r13
  __int64 v9; // rsi
  _DWORD *v10; // r12
  WCHAR *v11; // r14
  __int64 *v12; // rbx
  __int64 v13; // rbx
  const WCHAR *v14; // rcx
  int v15; // ebx
  unsigned int v16; // ebx
  __int64 HRasfileNode; // rax
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 *v20; // rax
  __int64 v21; // rax
  unsigned int v22; // ebx
  __int64 v23; // rax
  __int64 v24; // r8
  __int64 v25; // r9
  void *v26; // r14
  int v27; // edx
  int v28; // r9d
  unsigned int inserted; // eax
  const char *v30; // r8
  const char *v31; // r8
  __int64 v32; // r8
  unsigned int v33; // eax
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
  const char *v52; // r8
  __int64 v53; // r8
  const char *v54; // r8
  const char *v55; // r8
  const WCHAR *v56; // r8
  const WCHAR *v57; // r8
  const WCHAR *v58; // r8
  const WCHAR *v59; // r8
  const WCHAR *v60; // r8
  const WCHAR *v61; // r8
  const char *v62; // r8
  const WCHAR *v63; // r8
  const WCHAR *v64; // r8
  const char *v65; // r8
  const char *v66; // r8
  const char *v67; // r8
  unsigned int v68; // eax
  unsigned int v69; // eax
  unsigned int v70; // eax
  const char *v71; // r8
  __int64 v72; // r8
  __int64 v73; // r8
  __int64 v74; // r9
  const char *v75; // r8
  __int64 v76; // r8
  __int64 v77; // r9
  const char *v78; // r8
  const char *v79; // r8
  __int64 v80; // r8
  __int64 v81; // r8
  const char *v82; // r8
  __int64 v83; // rcx
  __int64 v84; // rdx
  unsigned int v85; // eax
  __int64 v86; // rcx
  __int64 v87; // rdx
  const char *v88; // r8
  const char *v89; // r8
  const char *v90; // r8
  const char *v91; // r8
  __int64 v92; // r8
  __int64 v93; // r8
  __int64 v94; // r8
  const char *v95; // r8
  const char *v96; // r8
  const char *v97; // r8
  const char *v98; // r8
  const char *v99; // r8
  __int64 v100; // r8
  const char *v101; // r8
  const char *v102; // r8
  const char *v103; // r8
  __int64 v104; // r8
  __int64 v105; // r9
  __int64 v106; // r15
  __int64 v107; // r14
  int v108; // edx
  int v109; // r9d
  __int64 v110; // r8
  const WCHAR *v111; // r15
  unsigned int v112; // r14d
  __int64 cbMultiByte; // r12
  __int64 v114; // rdx
  __int64 v115; // rdx
  __int64 v116; // r9
  struct _LIST_ENTRY *v117; // rcx
  __int64 v118; // rdx
  unsigned int v120; // ebx
  int v121; // [rsp+40h] [rbp-C0h]
  __int64 v122; // [rsp+50h] [rbp-B0h]
  PCNZWCH *v123; // [rsp+58h] [rbp-A8h]
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
  LUAPhonebookPath = 0;
  v121 = 0;
  v7 = **(_QWORD **)(v3 + 16);
  v122 = v7;
  if ( !v7 )
  {
LABEL_797:
    v120 = *(_DWORD *)(*(_QWORD *)(v3 + 16) + 16LL) - v5;
    if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 5u )
      WPP_SF_d(v4[1].Flink, 336, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v120);
    *v2 = v120;
LABEL_802:
    v4 = WPP_GLOBAL_Control;
    goto LABEL_803;
  }
  v8 = 0;
  v123 = 0;
  while ( 1 )
  {
    v9 = *(_QWORD *)(v7 + 16);
    v10 = (_DWORD *)(v9 + 540);
    if ( !*(_DWORD *)(v9 + 532) && !*v10 )
      goto LABEL_48;
    if ( (*(_DWORD *)(v3 + 32) & 0x100) == 0 || !*(_DWORD *)(v9 + 548) )
      break;
    if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 5u )
    {
      WPP_SF_S(v4[1].Flink, 231, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, *(_QWORD *)(v9 + 8));
      v5 = v121;
      v7 = v122;
    }
    *(_DWORD *)(v9 + 532) = 0;
    *(_DWORD *)(v9 + 540) = 0;
    v4 = WPP_GLOBAL_Control;
LABEL_48:
    v7 = *(_QWORD *)(v7 + 8);
    v122 = v7;
    if ( !v7 )
    {
      if ( LUAPhonebookPath )
        goto LABEL_803;
      v3 = a1;
      v2 = a2;
      goto LABEL_797;
    }
    v3 = a1;
  }
  if ( *(_DWORD *)v9 == -1 )
  {
    if ( !*(_DWORD *)(v9 + 548) || *(_DWORD *)(v3 + 8) == 4 )
    {
      v14 = *(const WCHAR **)v3;
      if ( (*(_DWORD *)(v3 + 32) & 0x100) != 0 )
      {
        LUAPhonebookPath = GetLUAPhonebookPath(v14);
        if ( LUAPhonebookPath )
          goto LABEL_26;
        v11 = 0;
      }
      else
      {
        LUAPhonebookPath = 0;
        v11 = (WCHAR *)StrDup(v14);
      }
      if ( v11 )
      {
LABEL_21:
        v12 = *(__int64 **)(v3 + 48);
        v8 = 0;
        v123 = 0;
        if ( !v12 )
          goto LABEL_35;
        v13 = *v12;
        while ( v13 )
        {
          v8 = *(PCNZWCH **)(v13 + 16);
          v123 = v8;
          if ( !v8 )
            goto LABEL_35;
          if ( !(unsigned int)CompareStringWrapW(v8[1], v11) )
            break;
          v13 = *(_QWORD *)(v13 + 8);
          v8 = 0;
          v123 = 0;
        }
        if ( !v8 )
        {
LABEL_35:
          v15 = *(_DWORD *)(*(_QWORD *)(a1 + 48) + 16LL);
          LUAPhonebookPath = CreateProfileDirAndSetAcls(*(HANDLE *)(a1 + 40), 1);
          if ( !LUAPhonebookPath )
          {
            LUAPhonebookPath = LoadFile(v11);
            if ( !LUAPhonebookPath )
            {
              v16 = v15 + 1;
              HRasfileNode = CreateHRasfileNode(0xFFFFFFFFLL, v11, v16);
              *(_DWORD *)v9 = v16;
              DtlAddNodeLast(*(_QWORD *)(a1 + 48), HRasfileNode);
              v8 = *(PCNZWCH **)(v18 + 16);
              v123 = v8;
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
      LUAPhonebookPath = GetProvisionedProfilePath(*(STRSAFE_LPCWSTR *)v3, *(STRSAFE_LPCWSTR *)(v9 + 8));
      if ( !LUAPhonebookPath )
      {
        v11 = 0;
        goto LABEL_21;
      }
LABEL_26:
      v11 = 0;
    }
    if ( v11 )
      GlobalFree(v11);
    if ( LUAPhonebookPath )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v19 = 232;
        goto LABEL_45;
      }
      goto LABEL_46;
    }
    v4 = WPP_GLOBAL_Control;
  }
  else
  {
    v20 = *(__int64 **)(v3 + 48);
    v8 = 0;
    v123 = 0;
    if ( v20 )
    {
      v21 = *v20;
      while ( v21 )
      {
        v8 = *(PCNZWCH **)(v21 + 16);
        v123 = v8;
        if ( !v8 )
          goto LABEL_58;
        if ( *((_DWORD *)v8 + 4) == *(_DWORD *)v9 )
          break;
        v21 = *(_QWORD *)(v21 + 8);
        v8 = 0;
        v123 = 0;
      }
    }
  }
  if ( !v8 )
  {
LABEL_58:
    if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 5u )
    {
      WPP_SF_S(v4[1].Flink, 233, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, *(_QWORD *)(v9 + 8));
      v4 = WPP_GLOBAL_Control;
    }
    LUAPhonebookPath = 622;
    if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 2u )
    {
      v19 = 234;
LABEL_45:
      WPP_SF_d(v4[1].Flink, v19, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, LUAPhonebookPath);
      v4 = WPP_GLOBAL_Control;
    }
LABEL_46:
    v5 = v121;
LABEL_47:
    v7 = v122;
    goto LABEL_48;
  }
  v22 = *(_DWORD *)v8;
  UpdateEntryTimeStamp(v9);
  v23 = StrDupAFromTInternal(*(LPCWCH *)(v9 + 8));
  v26 = (void *)v23;
  if ( !v23 )
  {
    inserted = 8;
    LUAPhonebookPath = 8;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_803;
    v115 = 235;
    goto LABEL_406;
  }
  if ( (unsigned int)RasfileFindSectionLine(v22, v23, v24, v25) )
    DeleteCurrentSection(v22);
  GlobalFree(v26);
  if ( *v10 )
  {
    *((_DWORD *)v8 + 5) |= 1u;
    v4 = WPP_GLOBAL_Control;
    v5 = ++v121;
    goto LABEL_47;
  }
  LOBYTE(v28) = 2;
  LOBYTE(v27) = 63;
  rasFindLine(v22, v27, 0, v28, 2);
  inserted = InsertSection(v22, *(_QWORD *)(v9 + 8));
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_803;
    v115 = 236;
    goto LABEL_406;
  }
  inserted = InsertLong(v22, "Encoding", 1);
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_803;
    v115 = 237;
    goto LABEL_406;
  }
  inserted = InsertLong(v22, "PBVersion", 8);
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_803;
    v115 = 238;
    goto LABEL_406;
  }
  inserted = InsertLong(v22, "Type", *(unsigned int *)(v9 + 24));
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_803;
    v115 = 239;
    goto LABEL_406;
  }
  v30 = "1";
  if ( !*(_DWORD *)(v9 + 176) )
    v30 = "0";
  inserted = InsertStringA(v22, "AutoLogon", v30);
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_803;
    v115 = 240;
    goto LABEL_406;
  }
  v31 = "1";
  if ( !*(_DWORD *)(v9 + 180) )
    v31 = "0";
  inserted = InsertStringA(v22, "UseRasCredentials", v31);
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_803;
    v115 = 241;
    goto LABEL_406;
  }
  inserted = InsertLong(v22, "LowDateTime", *(unsigned int *)(v9 + 16));
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_803;
    v115 = 242;
    goto LABEL_406;
  }
  inserted = InsertLong(v22, "HighDateTime", *(unsigned int *)(v9 + 20));
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_803;
    v115 = 243;
    goto LABEL_406;
  }
  inserted = InsertLong(v22, "DialParamsUID", *(unsigned int *)(v9 + 456));
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_803;
    v115 = 244;
LABEL_406:
    v116 = inserted;
    goto LABEL_407;
  }
  v32 = *(_QWORD *)(v9 + 464);
  if ( v32 )
  {
    v33 = InsertBinary(v22, "Guid", v32, 16);
    LUAPhonebookPath = v33;
    if ( v33 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      {
        if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 245, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v33);
          v4 = WPP_GLOBAL_Control;
        }
        if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 6u )
        {
          v114 = 246;
          goto LABEL_807;
        }
      }
      return LUAPhonebookPath;
    }
  }
  inserted = InsertLong(v22, "VpnStrategy", *(unsigned int *)(v9 + 168));
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v115 = 247;
      goto LABEL_406;
    }
    goto LABEL_803;
  }
  inserted = InsertLong(v22, "ExcludedProtocols", *(unsigned int *)(v9 + 236));
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v115 = 248;
      goto LABEL_406;
    }
    goto LABEL_803;
  }
  v34 = "1";
  if ( !*(_DWORD *)(v9 + 240) )
    v34 = "0";
  inserted = InsertStringA(v22, "LcpExtensions", v34);
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v115 = 249;
      goto LABEL_406;
    }
    goto LABEL_803;
  }
  inserted = InsertLong(v22, "DataEncryption", *(unsigned int *)(v9 + 172));
  LUAPhonebookPath = inserted;
  if ( inserted )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LUAPhonebookPath;
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v115 = 250;
      goto LABEL_406;
    }
LABEL_803:
    if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 6u )
    {
      v114 = 337;
LABEL_807:
      WPP_SF_d(v4[1].Flink, v114, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, LUAPhonebookPath);
    }
    return LUAPhonebookPath;
  }
  v35 = "1";
  if ( !*(_DWORD *)(v9 + 244) )
    v35 = "0";
  LUAPhonebookPath = InsertStringA(v22, "SwCompression", v35);
  if ( LUAPhonebookPath )
    goto LABEL_802;
  v36 = "1";
  if ( !*(_DWORD *)(v9 + 248) )
    v36 = "0";
  LUAPhonebookPath = InsertStringA(v22, "NegotiateMultilinkAlways", v36);
  if ( LUAPhonebookPath )
    goto LABEL_802;
  v37 = "1";
  if ( !*(_DWORD *)(v9 + 252) )
    v37 = "0";
  LUAPhonebookPath = InsertStringA(v22, "SkipDoubleDialDialog", v37);
  if ( LUAPhonebookPath )
    goto LABEL_802;
  LUAPhonebookPath = InsertLong(v22, "DialMode", *(unsigned int *)(v9 + 132));
  if ( LUAPhonebookPath )
    goto LABEL_802;
  LUAPhonebookPath = InsertLong(v22, "OverridePref", *(unsigned int *)(v9 + 144));
  if ( LUAPhonebookPath )
    goto LABEL_802;
  LUAPhonebookPath = InsertLong(v22, "RedialAttempts", *(unsigned int *)(v9 + 148));
  if ( LUAPhonebookPath )
    goto LABEL_802;
  LUAPhonebookPath = InsertLong(v22, "RedialSeconds", *(unsigned int *)(v9 + 152));
  if ( LUAPhonebookPath )
    goto LABEL_802;
  LUAPhonebookPath = InsertLong(v22, "IdleDisconnectSeconds", *(unsigned int *)(v9 + 156));
  if ( LUAPhonebookPath )
    goto LABEL_802;
  v38 = "1";
  if ( !*(_DWORD *)(v9 + 160) )
    v38 = "0";
  LUAPhonebookPath = InsertStringA(v22, "RedialOnLinkFailure", v38);
  if ( LUAPhonebookPath )
    goto LABEL_802;
  LUAPhonebookPath = InsertLong(v22, "CallbackMode", *(unsigned int *)(v9 + 420));
  if ( LUAPhonebookPath )
    goto LABEL_802;
  LUAPhonebookPath = InsertString(v22, "CustomDialDll", *(_QWORD *)(v9 + 432));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 251;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertString(v22, "CustomDialFunc", *(_QWORD *)(v9 + 440));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 252;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertString(v22, "CustomRasDialDll", *(_QWORD *)(v9 + 448));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 253;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  *(_DWORD *)(v9 + 184) = 0;
  LUAPhonebookPath = InsertStringA(v22, "ForceSecureCompartment", "0");
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 254;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v39 = "1";
  if ( !*(_DWORD *)(v9 + 188) )
    v39 = "0";
  LUAPhonebookPath = InsertStringA(v22, "DisableIKENameEkuCheck", v39);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 255;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v40 = "1";
  if ( !*(_DWORD *)(v9 + 424) )
    v40 = "0";
  LUAPhonebookPath = InsertStringA(v22, "AuthenticateServer", v40);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 256;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v41 = "1";
  if ( !*(_DWORD *)(v9 + 256) )
    v41 = "0";
  LUAPhonebookPath = InsertStringA(v22, "ShareMsFilePrint", v41);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 257;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v42 = "1";
  if ( !*(_DWORD *)(v9 + 260) )
    v42 = "0";
  LUAPhonebookPath = InsertStringA(v22, "BindMsNetClient", v42);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 258;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v43 = "1";
  if ( !*(_DWORD *)(v9 + 40) )
    v43 = "0";
  LUAPhonebookPath = InsertStringA(v22, "SharedPhoneNumbers", v43);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 259;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v44 = "1";
  if ( !*(_DWORD *)(v9 + 44) )
    v44 = "0";
  LUAPhonebookPath = InsertStringA(v22, "GlobalDeviceSettings", v44);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 260;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertString(v22, "PrerequisiteEntry", *(_QWORD *)(v9 + 56));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 261;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertString(v22, "PrerequisitePbk", *(_QWORD *)(v9 + 64));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 262;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertString(v22, "PreferredPort", *(_QWORD *)(v9 + 72));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 263;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertString(v22, "PreferredDevice", *(_QWORD *)(v9 + 80));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 264;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "PreferredBps", *(unsigned int *)(v9 + 88));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 265;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v45 = "1";
  if ( !*(_DWORD *)(v9 + 92) )
    v45 = "0";
  LUAPhonebookPath = InsertStringA(v22, "PreferredHwFlow", v45);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 266;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v46 = "1";
  if ( !*(_DWORD *)(v9 + 96) )
    v46 = "0";
  LUAPhonebookPath = InsertStringA(v22, "PreferredProtocol", v46);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 267;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v47 = "1";
  if ( !*(_DWORD *)(v9 + 100) )
    v47 = "0";
  LUAPhonebookPath = InsertStringA(v22, "PreferredCompression", v47);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 268;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "PreferredSpeaker", *(unsigned int *)(v9 + 104));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 269;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "PreferredMdmProtocol", *(unsigned int *)(v9 + 108));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 270;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v48 = "1";
  if ( !*(_DWORD *)(v9 + 116) )
    v48 = "0";
  LUAPhonebookPath = InsertStringA(v22, "PreviewUserPw", v48);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 271;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v49 = "1";
  if ( !*(_DWORD *)(v9 + 120) )
    v49 = "0";
  LUAPhonebookPath = InsertStringA(v22, "PreviewDomain", v49);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 272;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v50 = "1";
  if ( !*(_DWORD *)(v9 + 124) )
    v50 = "0";
  LUAPhonebookPath = InsertStringA(v22, "PreviewPhoneNumber", v50);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 273;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v51 = "1";
  if ( !*(_DWORD *)(v9 + 112) )
    v51 = "0";
  LUAPhonebookPath = InsertStringA(v22, "ShowDialingProgress", v51);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 274;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v52 = "1";
  if ( !*(_DWORD *)(v9 + 48) )
    v52 = "0";
  LUAPhonebookPath = InsertStringA(v22, "ShowMonitorIconInTaskBar", v52);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 275;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "CustomAuthKey", *(unsigned int *)(v9 + 192));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 276;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v53 = *(_QWORD *)(v9 + 200);
  if ( v53 )
  {
    LUAPhonebookPath = InsertBinary(v22, "CustomAuthData", v53, *(unsigned int *)(v9 + 208));
    if ( LUAPhonebookPath )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
      {
        v114 = 277;
        goto LABEL_807;
      }
      return LUAPhonebookPath;
    }
  }
  LUAPhonebookPath = InsertLong(v22, "AuthRestrictions", *(unsigned int *)(v9 + 164));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 278;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v54 = "1";
  if ( !*(_DWORD *)(v9 + 272) )
    v54 = "0";
  LUAPhonebookPath = InsertStringA(v22, "IpPrioritizeRemote", v54);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 279;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "IpInterfaceMetric", *(unsigned int *)(v9 + 352));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 280;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v55 = "1";
  if ( !*(_DWORD *)(v9 + 276) )
    v55 = "0";
  LUAPhonebookPath = InsertStringA(v22, "IpHeaderCompression", v55);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 281;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v56 = L"0.0.0.0";
  if ( *(_QWORD *)(v9 + 280) )
    v56 = *(const WCHAR **)(v9 + 280);
  LUAPhonebookPath = InsertString(v22, "IpAddress", v56);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 282;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v57 = L"0.0.0.0";
  if ( *(_QWORD *)(v9 + 288) )
    v57 = *(const WCHAR **)(v9 + 288);
  LUAPhonebookPath = InsertString(v22, "IpDnsAddress", v57);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 283;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v58 = L"0.0.0.0";
  if ( *(_QWORD *)(v9 + 296) )
    v58 = *(const WCHAR **)(v9 + 296);
  LUAPhonebookPath = InsertString(v22, "IpDns2Address", v58);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 284;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v59 = L"0.0.0.0";
  if ( *(_QWORD *)(v9 + 304) )
    v59 = *(const WCHAR **)(v9 + 304);
  LUAPhonebookPath = InsertString(v22, "IpWinsAddress", v59);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 285;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v60 = L"0.0.0.0";
  if ( *(_QWORD *)(v9 + 312) )
    v60 = *(const WCHAR **)(v9 + 312);
  LUAPhonebookPath = InsertString(v22, "IpWins2Address", v60);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 286;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "IpAssign", *(unsigned int *)(v9 + 320));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 287;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "IpNameAssign", *(unsigned int *)(v9 + 324));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 288;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "IpDnsFlags", *(unsigned int *)(v9 + 328));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 289;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "IpNBTFlags", *(unsigned int *)(v9 + 332));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 290;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "TcpWindowSize", *(unsigned int *)(v9 + 336));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 291;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "UseFlags", *(unsigned int *)(v9 + 136));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 292;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "IpSecFlags", *(unsigned int *)(v9 + 140));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 293;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertString(v22, "IpDnsSuffix", *(_QWORD *)(v9 + 344));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 294;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "Ipv6Assign", *(unsigned int *)(v9 + 356));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 295;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v61 = L"::";
  if ( *(_QWORD *)(v9 + 360) )
    v61 = *(const WCHAR **)(v9 + 360);
  LUAPhonebookPath = InsertString(v22, "Ipv6Address", v61);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 296;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "Ipv6PrefixLength", *(unsigned int *)(v9 + 368));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 297;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v62 = "1";
  if ( !*(_DWORD *)(v9 + 372) )
    v62 = "0";
  LUAPhonebookPath = InsertStringA(v22, "Ipv6PrioritizeRemote", v62);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 298;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "Ipv6InterfaceMetric", *(unsigned int *)(v9 + 416));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 299;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "Ipv6NameAssign", *(unsigned int *)(v9 + 376));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 300;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v63 = L"::";
  if ( *(_QWORD *)(v9 + 384) )
    v63 = *(const WCHAR **)(v9 + 384);
  LUAPhonebookPath = InsertString(v22, "Ipv6DnsAddress", v63);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 301;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v64 = L"::";
  if ( *(_QWORD *)(v9 + 392) )
    v64 = *(const WCHAR **)(v9 + 392);
  LUAPhonebookPath = InsertString(v22, "Ipv6Dns2Address", v64);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 302;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertBinary(v22, "Ipv6Prefix", v9 + 408, 8);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 303;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertBinary(v22, "Ipv6InterfaceId", v9 + 400, 8);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 304;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v65 = "1";
  if ( !*(_DWORD *)(v9 + 544) )
    v65 = "0";
  LUAPhonebookPath = InsertStringA(v22, "DisableClassBasedDefaultRoute", v65);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 305;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  v66 = "1";
  if ( !*(_DWORD *)(v9 + 488) )
    v66 = "0";
  LUAPhonebookPath = InsertStringA(v22, "DisableMobility", v66);
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 306;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  LUAPhonebookPath = InsertLong(v22, "NetworkOutageTime", *(unsigned int *)(v9 + 492));
  if ( LUAPhonebookPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v114 = 307;
      goto LABEL_807;
    }
    return LUAPhonebookPath;
  }
  if ( !(unsigned int)InsertString(v22, "IDI", *(_QWORD *)(v9 + 496)) )
  {
    if ( (unsigned int)InsertString(v22, "IDR", *(_QWORD *)(v9 + 504)) )
    {
      v117 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      {
        if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 310, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 1);
          v117 = WPP_GLOBAL_Control;
        }
        if ( v117 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && SBYTE4(v117[1].Blink) < 0
          && BYTE1(v117[1].Blink) >= 6u )
        {
          v118 = 311;
          goto LABEL_517;
        }
      }
      return 1;
    }
    v67 = "1";
    if ( !*(_DWORD *)(v9 + 512) )
      v67 = "0";
    v68 = InsertStringA(v22, "ImsConfig", v67);
    LUAPhonebookPath = v68;
    if ( v68 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      {
        if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 312, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v68);
          v4 = WPP_GLOBAL_Control;
        }
        if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 6u )
        {
          v114 = 313;
          goto LABEL_807;
        }
      }
      return LUAPhonebookPath;
    }
    v69 = InsertLong(v22, "IdiType", *(unsigned int *)(v9 + 516));
    LUAPhonebookPath = v69;
    if ( v69 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      {
        if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 314, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v69);
          v4 = WPP_GLOBAL_Control;
        }
        if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 6u )
        {
          v114 = 315;
          goto LABEL_807;
        }
      }
      return LUAPhonebookPath;
    }
    v70 = InsertLong(v22, "IdrType", *(unsigned int *)(v9 + 520));
    LUAPhonebookPath = v70;
    if ( v70 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      {
        if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 316, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v70);
          v4 = WPP_GLOBAL_Control;
        }
        if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 6u )
        {
          v114 = 317;
          goto LABEL_807;
        }
      }
      return LUAPhonebookPath;
    }
    LUAPhonebookPath = InsertLong(v22, "ProvisionType", *(unsigned int *)(v9 + 548));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    LUAPhonebookPath = InsertString(v22, "PreSharedKey", *(_QWORD *)(v9 + 552));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v71 = "1";
    if ( !*(_DWORD *)(v9 + 128) )
      v71 = "0";
    LUAPhonebookPath = InsertStringA(v22, "CacheCredentials", v71);
    if ( LUAPhonebookPath )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
      {
        v114 = 318;
        goto LABEL_807;
      }
      return LUAPhonebookPath;
    }
    LUAPhonebookPath = InsertLong(v22, "NumCustomPolicy", *(unsigned int *)(v9 + 596));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v72 = *(_QWORD *)(v9 + 608);
    if ( v72 )
    {
      if ( *(_DWORD *)(v9 + 596) )
      {
        LUAPhonebookPath = InsertBinary(v22, "CustomIPSecPolicies", v72, *(unsigned int *)(v9 + 600));
        if ( LUAPhonebookPath )
          goto LABEL_802;
      }
    }
    LUAPhonebookPath = InsertLong(v22, "NumEku", *(unsigned int *)(v9 + 616));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v73 = *(_QWORD *)(v9 + 624);
    if ( v73 )
    {
      if ( *(_DWORD *)(v9 + 616) )
      {
        v74 = *(unsigned int *)(v9 + 620);
        if ( (_DWORD)v74 )
        {
          LUAPhonebookPath = InsertBinary(v22, "CertificateEKU", v73, v74);
          if ( LUAPhonebookPath )
            goto LABEL_802;
        }
      }
    }
    v75 = "1";
    if ( !*(_DWORD *)(v9 + 632) )
      v75 = "0";
    LUAPhonebookPath = InsertStringA(v22, "UseMachineRootCert", v75);
    if ( LUAPhonebookPath )
      goto LABEL_802;
    if ( *(_DWORD *)(v9 + 632) == 1 )
    {
      v76 = *(_QWORD *)(v9 + 648);
      if ( v76 )
      {
        v77 = *(unsigned int *)(v9 + 640);
        if ( (_DWORD)v77 )
        {
          LUAPhonebookPath = InsertBinary(v22, "RootCertificate", v76, v77);
          if ( LUAPhonebookPath )
            goto LABEL_802;
        }
      }
    }
    v78 = "1";
    if ( !*(_DWORD *)(v9 + 524) )
      v78 = "0";
    inserted = InsertStringA(v22, "Disable_IKEv2_Fragmentation", v78);
    LUAPhonebookPath = inserted;
    if ( inserted )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return LUAPhonebookPath;
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v115 = 319;
        goto LABEL_406;
      }
      goto LABEL_803;
    }
    v79 = "1";
    if ( !*(_DWORD *)(v9 + 528) )
      v79 = "0";
    inserted = InsertStringA(v22, "PlumbIKEv2TSAsRoutes", v79);
    LUAPhonebookPath = inserted;
    if ( inserted )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return LUAPhonebookPath;
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v115 = 320;
        goto LABEL_406;
      }
      goto LABEL_803;
    }
    LUAPhonebookPath = InsertLong(v22, "NumServers", *(unsigned int *)(v9 + 656));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    if ( *(_QWORD *)(v9 + 664) )
    {
      if ( *(_DWORD *)(v9 + 656) )
      {
        inserted = CreateServerLists(v22);
        LUAPhonebookPath = inserted;
        if ( inserted )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            return LUAPhonebookPath;
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            v115 = 321;
            goto LABEL_406;
          }
          goto LABEL_803;
        }
      }
    }
    inserted = InsertLong(v22, "RouteVersion", 1);
    LUAPhonebookPath = inserted;
    if ( inserted )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return LUAPhonebookPath;
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v115 = 322;
        goto LABEL_406;
      }
      goto LABEL_803;
    }
    inserted = InsertLong(v22, "NumRoutes", *(unsigned int *)(v9 + 672));
    LUAPhonebookPath = inserted;
    if ( inserted )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return LUAPhonebookPath;
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v115 = 323;
        goto LABEL_406;
      }
      goto LABEL_803;
    }
    v80 = *(_QWORD *)(v9 + 680);
    if ( v80 )
    {
      if ( *(_DWORD *)(v9 + 672) )
      {
        inserted = InsertBinary(v22, "Routes", v80, *(unsigned int *)(v9 + 676));
        LUAPhonebookPath = inserted;
        if ( inserted )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            return LUAPhonebookPath;
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            v115 = 324;
            goto LABEL_406;
          }
          goto LABEL_803;
        }
      }
    }
    inserted = InsertLong(v22, "NumNrptRules", *(unsigned int *)(v9 + 688));
    LUAPhonebookPath = inserted;
    if ( inserted )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return LUAPhonebookPath;
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v115 = 325;
        goto LABEL_406;
      }
      goto LABEL_803;
    }
    v81 = *(_QWORD *)(v9 + 696);
    if ( v81 )
    {
      if ( *(_DWORD *)(v9 + 688) )
      {
        inserted = InsertBinary(v22, "NrptRules", v81, *(unsigned int *)(v9 + 692));
        LUAPhonebookPath = inserted;
        if ( inserted )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            return LUAPhonebookPath;
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            v115 = 326;
            goto LABEL_406;
          }
          goto LABEL_803;
        }
      }
    }
    v82 = "1";
    if ( !*(_DWORD *)(v9 + 704) )
      v82 = "0";
    inserted = InsertStringA(v22, "AutoTiggerCapable", v82);
    LUAPhonebookPath = inserted;
    if ( inserted )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return LUAPhonebookPath;
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v115 = 327;
        goto LABEL_406;
      }
      goto LABEL_803;
    }
    LUAPhonebookPath = InsertLong(v22, "NumAppIds", *(unsigned int *)(v9 + 728));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v84 = *(_QWORD *)(v9 + 736);
    if ( v84 && *(_DWORD *)(v9 + 728) )
    {
      inserted = CreateDtlList(v83, v84, *(unsigned int *)(v9 + 732));
      LUAPhonebookPath = inserted;
      if ( inserted )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          return LUAPhonebookPath;
        if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          v115 = 328;
          goto LABEL_406;
        }
        goto LABEL_803;
      }
      v85 = InsertStringList(v22, "ApplicationIds", 0);
      LUAPhonebookPath = v85;
      if ( v85 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 329, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v85);
        }
        DtlDestroyList(0);
        goto LABEL_802;
      }
      DtlDestroyList(0);
    }
    LUAPhonebookPath = InsertLong(v22, "NumClassicAppIds", *(unsigned int *)(v9 + 708));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v87 = *(_QWORD *)(v9 + 720);
    if ( v87 && *(_DWORD *)(v9 + 708) )
    {
      inserted = CreateDtlList(v86, v87, *(unsigned int *)(v9 + 712));
      LUAPhonebookPath = inserted;
      if ( inserted )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          return LUAPhonebookPath;
        if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          v115 = 330;
          goto LABEL_406;
        }
        goto LABEL_803;
      }
      LUAPhonebookPath = InsertStringList(v22, "ClassicApplicationIds", 0);
      if ( LUAPhonebookPath )
      {
        DtlDestroyList(0);
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          return LUAPhonebookPath;
        if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          goto LABEL_803;
        v115 = 331;
        v116 = LUAPhonebookPath;
LABEL_407:
        WPP_SF_d(v4[1].Flink, v115, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v116);
        goto LABEL_802;
      }
      DtlDestroyList(0);
    }
    inserted = InsertString(v22, "SecurityDescriptor", *(_QWORD *)(v9 + 744));
    LUAPhonebookPath = inserted;
    if ( inserted )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return LUAPhonebookPath;
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v115 = 332;
        goto LABEL_406;
      }
      goto LABEL_803;
    }
    LUAPhonebookPath = InsertString(v22, "ApnInfoProviderId", *(_QWORD *)(v9 + 864));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    LUAPhonebookPath = InsertString(v22, "ApnInfoUsername", *(_QWORD *)(v9 + 880));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    LUAPhonebookPath = InsertString(v22, "ApnInfoPassword", *(_QWORD *)(v9 + 888));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    LUAPhonebookPath = InsertString(v22, "ApnInfoAccessPoint", *(_QWORD *)(v9 + 872));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    LUAPhonebookPath = InsertLong(v22, "ApnInfoAuthentication", *(unsigned int *)(v9 + 900));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v88 = "1";
    if ( !*(_DWORD *)(v9 + 896) )
      v88 = "0";
    LUAPhonebookPath = InsertStringA(v22, "ApnInfoCompression", v88);
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v89 = "1";
    if ( !*(_DWORD *)(v9 + 904) )
      v89 = "0";
    LUAPhonebookPath = InsertStringA(v22, "DeviceComplianceEnabled", v89);
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v90 = "1";
    if ( !*(_DWORD *)(v9 + 912) )
      v90 = "0";
    LUAPhonebookPath = InsertStringA(v22, "DeviceComplianceSsoEnabled", v90);
    if ( LUAPhonebookPath )
      goto LABEL_802;
    LUAPhonebookPath = InsertString(v22, "DeviceComplianceSsoEku", *(_QWORD *)(v9 + 920));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    LUAPhonebookPath = InsertString(v22, "DeviceComplianceSsoIssuer", *(_QWORD *)(v9 + 928));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    LUAPhonebookPath = InsertLong(v22, "FlagsSet", *(unsigned int *)(v9 + 952));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    LUAPhonebookPath = InsertLong(v22, "Options", *(unsigned int *)(v9 + 956));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v91 = "1";
    if ( !*(_DWORD *)(v9 + 788) )
      v91 = "0";
    LUAPhonebookPath = InsertStringA(v22, "DisableDefaultDnsSuffixes", v91);
    if ( LUAPhonebookPath )
      goto LABEL_802;
    LUAPhonebookPath = InsertLong(v22, "NumTrustedNetworks", *(unsigned int *)(v9 + 792));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v92 = *(_QWORD *)(v9 + 800);
    if ( v92 )
    {
      if ( *(_DWORD *)(v9 + 792) )
      {
        LUAPhonebookPath = InsertBinary(v22, "TrustedNetworks", v92, *(unsigned int *)(v9 + 796));
        if ( LUAPhonebookPath )
          goto LABEL_802;
      }
    }
    v93 = *(_QWORD *)(v9 + 760);
    if ( v93 )
    {
      LUAPhonebookPath = InsertBinary(v22, "ThirdPartyProfileInfo", v93, *(unsigned int *)(v9 + 752));
      if ( LUAPhonebookPath )
        goto LABEL_802;
    }
    LUAPhonebookPath = InsertLong(v22, "NumDnsSearchSuffixes", *(unsigned int *)(v9 + 768));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v94 = *(_QWORD *)(v9 + 776);
    if ( v94 )
    {
      LUAPhonebookPath = InsertBinary(v22, "DnsSuffixSearchList", v94, *(unsigned int *)(v9 + 772));
      if ( LUAPhonebookPath )
        goto LABEL_802;
    }
    v95 = "1";
    if ( !*(_DWORD *)(v9 + 784) )
      v95 = "0";
    LUAPhonebookPath = InsertStringA(v22, "PowershellCreatedProfile", v95);
    if ( LUAPhonebookPath )
      goto LABEL_802;
    LUAPhonebookPath = InsertLong(v22, "ProxyFlags", *(unsigned int *)(v9 + 560));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v96 = "1";
    if ( !*(_DWORD *)(v9 + 820) )
      v96 = "0";
    LUAPhonebookPath = InsertStringA(v22, "ProxySettingsModified", v96);
    if ( LUAPhonebookPath )
      goto LABEL_802;
    if ( (*(_BYTE *)(v9 + 560) & 2) != 0 )
    {
      LUAPhonebookPath = InsertString(v22, "Proxy", *(_QWORD *)(v9 + 576));
      if ( LUAPhonebookPath )
        goto LABEL_802;
      LUAPhonebookPath = InsertString(v22, "ExcludeList", *(_QWORD *)(v9 + 584));
      if ( LUAPhonebookPath )
        goto LABEL_802;
      v97 = "1";
      if ( !*(_DWORD *)(v9 + 592) )
        v97 = "0";
      LUAPhonebookPath = InsertStringA(v22, "BypassProxyForLocal", v97);
      if ( LUAPhonebookPath )
        goto LABEL_802;
    }
    if ( (*(_BYTE *)(v9 + 560) & 4) != 0 )
    {
      LUAPhonebookPath = InsertString(v22, "AutoConfigScript", *(_QWORD *)(v9 + 568));
      if ( LUAPhonebookPath )
        goto LABEL_802;
    }
    LUAPhonebookPath = InsertString(v22, "ProvisioningAuthority", *(_QWORD *)(v9 + 808));
    if ( LUAPhonebookPath )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
      {
        v114 = 333;
        goto LABEL_807;
      }
      return LUAPhonebookPath;
    }
    v98 = "1";
    if ( !*(_DWORD *)(v9 + 816) )
      v98 = "0";
    LUAPhonebookPath = InsertStringA(v22, "AuthTypeOTP", v98);
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v99 = "1";
    if ( !*(_DWORD *)(v9 + 824) )
      v99 = "0";
    LUAPhonebookPath = InsertStringA(v22, "GREKeyDefined", v99);
    if ( LUAPhonebookPath )
      goto LABEL_802;
    if ( *(_DWORD *)(v9 + 824) )
    {
      LUAPhonebookPath = InsertULong(v22, "GREKey", *(unsigned int *)(v9 + 828));
      if ( LUAPhonebookPath )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
        {
          v114 = 334;
          goto LABEL_807;
        }
        return LUAPhonebookPath;
      }
    }
    LUAPhonebookPath = InsertLong(v22, "NumPerAppTrafficFilters", *(unsigned int *)(v9 + 832));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v100 = *(_QWORD *)(v9 + 840);
    if ( v100 )
    {
      if ( *(_DWORD *)(v9 + 832) )
      {
        LUAPhonebookPath = InsertBinary(v22, "PerAppTrafficFilters", v100, *(unsigned int *)(v9 + 836));
        if ( LUAPhonebookPath )
          goto LABEL_802;
      }
    }
    v101 = "1";
    if ( !*(_DWORD *)(v9 + 848) )
      v101 = "0";
    LUAPhonebookPath = InsertStringA(v22, "AlwaysOnCapable", v101);
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v102 = "1";
    if ( !*(_DWORD *)(v9 + 856) )
      v102 = "0";
    inserted = InsertStringA(v22, "DeviceTunnel", v102);
    LUAPhonebookPath = inserted;
    if ( inserted )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return LUAPhonebookPath;
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v115 = 335;
        goto LABEL_406;
      }
      goto LABEL_803;
    }
    v103 = "1";
    if ( !*(_DWORD *)(v9 + 852) )
      v103 = "0";
    LUAPhonebookPath = InsertStringA(v22, "PrivateNetwork", v103);
    if ( LUAPhonebookPath )
      goto LABEL_802;
    v104 = *(_QWORD *)(v9 + 944);
    if ( v104 )
    {
      v105 = *(unsigned int *)(v9 + 936);
      if ( (_DWORD)v105 )
      {
        LUAPhonebookPath = InsertBinary(v22, "PluginStorage", v104, v105);
        if ( LUAPhonebookPath )
          goto LABEL_802;
      }
    }
    LUAPhonebookPath = InsertString(v22, "ManagementApp", *(_QWORD *)(v9 + 960));
    if ( LUAPhonebookPath )
      goto LABEL_802;
    if ( *(_DWORD *)(v9 + 168) == 15 )
    {
      LUAPhonebookPath = InsertULong(v22, "ProtocolListLength", *(unsigned int *)(v9 + 968));
      if ( LUAPhonebookPath )
        goto LABEL_802;
      LUAPhonebookPath = InsertBinary(v22, "ProtocolList", v9 + 972, 16);
      if ( LUAPhonebookPath )
        goto LABEL_802;
      LUAPhonebookPath = InsertULong(v22, "ProtocolListRetryTimeInHours", *(unsigned int *)(v9 + 988));
      if ( LUAPhonebookPath )
        goto LABEL_802;
      LUAPhonebookPath = InsertULong(v22, "ProtocolListCurrentProtocol", *(unsigned int *)(v9 + 992));
      if ( LUAPhonebookPath )
        goto LABEL_802;
      LUAPhonebookPath = InsertULong(v22, "ProtocolListTimeOfLastProtocolSelectionLow", *(unsigned int *)(v9 + 1000));
      if ( LUAPhonebookPath )
        goto LABEL_802;
      LUAPhonebookPath = InsertULong(v22, "ProtocolListTimeOfLastProtocolSelectionHigh", *(unsigned int *)(v9 + 1004));
      if ( LUAPhonebookPath )
        goto LABEL_802;
    }
    InsertNetComponents(v22, *(_QWORD *)(v9 + 264));
    v106 = **(_QWORD **)(v9 + 32);
    if ( v106 )
    {
      do
      {
        v107 = *(_QWORD *)(v106 + 16);
        LUAPhonebookPath = InsertGroup(v22, "MEDIA", *(_QWORD *)(v107 + 24));
        if ( LUAPhonebookPath )
          break;
        LUAPhonebookPath = InsertString(v22, "Port", *(_QWORD *)v107);
        if ( LUAPhonebookPath )
          break;
        v110 = *(_QWORD *)(v107 + 16);
        if ( v110 )
        {
          LUAPhonebookPath = InsertString(v22, "Device", v110);
          if ( LUAPhonebookPath )
            break;
        }
        if ( *(_DWORD *)(v107 + 40) == 3 || (*(_BYTE *)(v107 + 48) & 4) != 0 )
        {
          LUAPhonebookPath = InsertLong(v22, "ConnectBPS", *(unsigned int *)(v107 + 104));
          if ( LUAPhonebookPath )
            break;
        }
        LOBYTE(v109) = 2;
        LOBYTE(v108) = 48;
        rasFindLine(v22, v108, 2, v109, 2);
        LUAPhonebookPath = InsertDeviceList(a1, v22, v9, v107);
        if ( LUAPhonebookPath )
          break;
        v106 = *(_QWORD *)(v106 + 8);
      }
      while ( v106 );
      v8 = v123;
    }
    if ( *(_DWORD *)(v9 + 548) )
    {
      LUAPhonebookPath = InsertGroup(v22, "PROXYSETTINGS", 0);
      if ( LUAPhonebookPath )
        goto LABEL_802;
      LUAPhonebookPath = InsertString(v22, "AutoConfigScript", *(_QWORD *)(v9 + 568));
      if ( LUAPhonebookPath )
        goto LABEL_802;
      LUAPhonebookPath = InsertString(v22, "Proxy", *(_QWORD *)(v9 + 576));
      if ( LUAPhonebookPath )
        goto LABEL_802;
      LUAPhonebookPath = InsertLong(v22, "ProxyFlags", *(unsigned int *)(v9 + 560));
      if ( LUAPhonebookPath )
        goto LABEL_802;
      v111 = *(const WCHAR **)(v9 + 584);
      memset_0(MultiByteStr, 0, 0x101u);
      v112 = lstrlenW(v111);
      if ( v112 )
      {
        while ( 1 )
        {
          memset_0(MultiByteStr, 0, 0x101u);
          cbMultiByte = v112;
          if ( v112 >= 0x100 )
            cbMultiByte = 256;
          if ( !WideCharToMultiByte(0xFDE9u, 0, v111, -1, MultiByteStr, cbMultiByte, 0, 0) )
            GetLastError();
          LUAPhonebookPath = InsertStringA(v22, "ExcludeList", MultiByteStr);
          if ( LUAPhonebookPath )
            goto LABEL_802;
          v111 += cbMultiByte;
          v112 -= cbMultiByte;
          if ( !v112 )
            goto LABEL_387;
        }
      }
      LUAPhonebookPath = InsertStringA(v22, "ExcludeList", MultiByteStr);
      if ( LUAPhonebookPath )
        goto LABEL_802;
LABEL_387:
      LUAPhonebookPath = 0;
    }
    *(_DWORD *)(v9 + 532) = 0;
    v4 = WPP_GLOBAL_Control;
    goto LABEL_46;
  }
  v117 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 308, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 1);
      v117 = WPP_GLOBAL_Control;
    }
    if ( v117 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v117[1].Blink) < 0 && BYTE1(v117[1].Blink) >= 6u )
    {
      v118 = 309;
LABEL_517:
      WPP_SF_d(v117[1].Flink, v118, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 1);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800714c0  mov     [rsp-8+arg_10], rbx
0x1800714c5  push    rbp
0x1800714c6  push    rsi
0x1800714c7  push    rdi
0x1800714c8  push    r12
0x1800714ca  push    r13
0x1800714cc  push    r14
0x1800714ce  push    r15
0x1800714d0  lea     rbp, [rsp-90h]
0x1800714d8  sub     rsp, 190h
0x1800714df  mov     rax, cs:__security_cookie
0x1800714e6  xor     rax, rsp
0x1800714e9  mov     [rbp+0C0h+var_40], rax
0x1800714f0  mov     rsi, rdx
0x1800714f3  mov     [rsp+1C0h+var_158], rdx
0x1800714f8  mov     rbx, rcx
0x1800714fb  mov     [rsp+1C0h+var_160], rcx
0x180071500  mov     rcx, cs:WPP_GLOBAL_Control
0x180071507  lea     r14, WPP_GLOBAL_Control
0x18007150e  cmp     rcx, r14
0x180071511  jz      short loc_18007153B
0x180071513  test    byte ptr [rcx+1Ch], 80h
0x180071517  jz      short loc_18007153B
0x180071519  cmp     byte ptr [rcx+19h], 6
0x18007151d  jb      short loc_18007153B
0x18007151f  mov     rcx, [rcx+10h]
0x180071523  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007152a  mov     edx, 0E6h
0x18007152f  call    WPP_SF_
0x180071534  mov     rcx, cs:WPP_GLOBAL_Control
0x18007153b  mov     rax, [rbx+10h]
0x18007153f  xor     r15d, r15d
0x180071542  mov     edx, r15d
0x180071545  mov     edi, r15d
0x180071548  mov     [rsp+1C0h+var_180], edx
0x18007154c  mov     r8, [rax]
0x18007154f  mov     [rsp+1C0h+var_170], r8
0x180071554  test    r8, r8
0x180071557  jz      loc_18007466A
0x18007155d  mov     r13d, r15d
0x180071560  mov     [rsp+1C0h+var_168], r15
0x180071565  mov     rsi, [r8+10h]
0x180071569  mov     r9d, 100h
0x18007156f  lea     r12, [rsi+21Ch]
0x180071576  cmp     [rsi+214h], r15d
0x18007157d  jnz     short loc_180071589
0x18007157f  cmp     [r12], r15d
0x180071583  jz      loc_180071790
0x180071589  mov     eax, [rbx+20h]
0x18007158c  and     eax, r9d
0x18007158f  jz      short loc_1800715E7
0x180071591  cmp     [rsi+224h], r15d
0x180071598  jz      short loc_1800715E7
0x18007159a  cmp     rcx, r14
0x18007159d  jz      short loc_1800715CD
0x18007159f  test    byte ptr [rcx+1Ch], 80h
0x1800715a3  jz      short loc_1800715CD
0x1800715a5  cmp     byte ptr [rcx+19h], 5
0x1800715a9  jb      short loc_1800715CD
0x1800715ab  mov     r9, [rsi+8]
0x1800715af  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x1800715b6  mov     rcx, [rcx+10h]
0x1800715ba  mov     edx, 0E7h
0x1800715bf  call    WPP_SF_S
0x1800715c4  mov     edx, [rsp+1C0h+var_180]
0x1800715c8  mov     r8, [rsp+1C0h+var_170]
0x1800715cd  mov     [rsi+214h], r15d
0x1800715d4  mov     [rsi+21Ch], r15d
0x1800715db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800715e2  jmp     loc_180071790
0x1800715e7  mov     edx, [rsi]
0x1800715e9  cmp     edx, 0FFFFFFFFh
0x1800715ec  jnz     loc_1800717BC
0x1800715f2  mov     [rsp+1C0h+hMem], r15
0x1800715f7  cmp     [rsi+224h], r15d
0x1800715fe  jz      short loc_18007163E
0x180071600  cmp     dword ptr [rbx+8], 4
0x180071604  mov     r15d, 1
0x18007160a  jz      short loc_18007163E
0x18007160c  mov     rdx, [rsi+8]; STRSAFE_LPCWSTR
0x180071610  lea     r8, [rsp+1C0h+hMem]
0x180071615  mov     rcx, [rbx]; pszSrc
0x180071618  call    GetProvisionedProfilePath
0x18007161d  mov     edi, eax
0x18007161f  test    eax, eax
0x180071621  jnz     short loc_18007165C
0x180071623  mov     r14, [rsp+1C0h+hMem]
0x180071628  mov     rbx, [rbx+30h]
0x18007162c  xor     r13d, r13d
0x18007162f  mov     [rsp+1C0h+var_168], r13
0x180071634  test    rbx, rbx
0x180071637  jz      short loc_1800716B2
0x180071639  mov     rbx, [rbx]
0x18007163c  jmp     short loc_1800716A8
0x18007163e  mov     rcx, [rbx]; pszSrc
0x180071641  test    eax, eax
0x180071643  jz      short loc_180071666
0x180071645  lea     rdx, [rsp+1C0h+hMem]
0x18007164a  call    GetLUAPhonebookPath
0x18007164f  mov     edi, eax
0x180071651  test    eax, eax
0x180071653  jnz     short loc_18007165C
0x180071655  mov     r14, [rsp+1C0h+hMem]
0x18007165a  jmp     short loc_180071670
0x18007165c  mov     r14, [rsp+1C0h+hMem]
0x180071661  jmp     loc_18007172E
0x180071666  xor     edi, edi
0x180071668  call    StrDup
0x18007166d  mov     r14, rax
0x180071670  test    r14, r14
0x180071673  jnz     short loc_180071628
0x180071675  lea     edi, [r14+8]
0x180071679  jmp     loc_18007172E
0x18007167e  mov     r13, [rbx+10h]
0x180071682  mov     [rsp+1C0h+var_168], r13
0x180071687  test    r13, r13
0x18007168a  jz      short loc_1800716B2
0x18007168c  mov     rcx, [r13+8]; lpString1
0x180071690  mov     rdx, r14; lpString2
0x180071693  call    CompareStringWrapW
0x180071698  test    eax, eax
0x18007169a  jz      short loc_1800716AD
0x18007169c  mov     rbx, [rbx+8]
0x1800716a0  xor     r13d, r13d
0x1800716a3  mov     [rsp+1C0h+var_168], r13
0x1800716a8  test    rbx, rbx
0x1800716ab  jnz     short loc_18007167E
0x1800716ad  test    r13, r13
0x1800716b0  jnz     short loc_18007172E
0x1800716b2  mov     rax, [rsp+1C0h+var_160]
0x1800716b7  mov     r9d, r15d
0x1800716ba  mov     r15, [rsp+1C0h+var_160]
0x1800716bf  mov     rdx, r14
0x1800716c2  mov     dword ptr [rsp+1C0h+hMem], 0FFFFFFFFh
0x1800716ca  mov     dword ptr [rsp+1C0h+lpMultiByteStr], 1; int
0x1800716d2  mov     rax, [rax+30h]
0x1800716d6  mov     r8d, [r15+8]
0x1800716da  mov     rcx, [r15+28h]; hToken
0x1800716de  mov     ebx, [rax+10h]
0x1800716e1  call    CreateProfileDirAndSetAcls
0x1800716e6  mov     edi, eax
0x1800716e8  test    eax, eax
0x1800716ea  jnz     short loc_18007172E
0x1800716ec  mov     edx, [r15+20h]
0x1800716f0  lea     r8, [rsp+1C0h+hMem]
0x1800716f5  xor     r9d, r9d
0x1800716f8  mov     rcx, r14; lpFileName
0x1800716fb  call    LoadFile
0x180071700  mov     edi, eax
0x180071702  test    eax, eax
0x180071704  jnz     short loc_18007172E
0x180071706  mov     ecx, dword ptr [rsp+1C0h+hMem]
0x18007170a  inc     ebx
0x18007170c  mov     r8d, ebx
0x18007170f  mov     rdx, r14
0x180071712  call    CreateHRasfileNode
0x180071717  mov     [rsi], ebx
0x180071719  mov     rdx, rax
0x18007171c  mov     rcx, [r15+30h]
0x180071720  call    DtlAddNodeLast
0x180071725  mov     r13, [rdx+10h]
0x180071729  mov     [rsp+1C0h+var_168], r13
0x18007172e  xor     r15d, r15d
0x180071731  test    r14, r14
0x180071734  jz      short loc_180071745
0x180071736  mov     rcx, r14; hMem
0x180071739  call    cs:__imp_GlobalFree
0x180071740  nop     dword ptr [rax+rax+00h]
0x180071745  test    edi, edi
0x180071747  jz      short loc_1800717AC
0x180071749  mov     rcx, cs:WPP_GLOBAL_Control
0x180071750  lea     r14, WPP_GLOBAL_Control
0x180071757  cmp     rcx, r14
0x18007175a  jz      short loc_180071787
0x18007175c  test    byte ptr [rcx+1Ch], 80h
0x180071760  jz      short loc_180071787
0x180071762  cmp     byte ptr [rcx+19h], 2
0x180071766  jb      short loc_180071787
0x180071768  mov     edx, 0E8h
0x18007176d  mov     rcx, [rcx+10h]
0x180071771  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180071778  mov     r9d, edi
0x18007177b  call    WPP_SF_d
0x180071780  mov     rcx, cs:WPP_GLOBAL_Control
0x180071787  mov     edx, [rsp+1C0h+var_180]
0x18007178b  mov     r8, [rsp+1C0h+var_170]
0x180071790  mov     r8, [r8+8]
0x180071794  mov     [rsp+1C0h+var_170], r8
0x180071799  test    r8, r8
0x18007179c  jz      loc_180074658
0x1800717a2  mov     rbx, [rsp+1C0h+var_160]
0x1800717a7  jmp     loc_180071565
0x1800717ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800717b3  lea     r14, WPP_GLOBAL_Control
0x1800717ba  jmp     short loc_1800717F7
0x1800717bc  mov     rax, [rbx+30h]
0x1800717c0  mov     r13, r15
0x1800717c3  mov     [rsp+1C0h+var_168], r15
0x1800717c8  test    rax, rax
0x1800717cb  jz      short loc_1800717F7
0x1800717cd  mov     rax, [rax]
0x1800717d0  jmp     short loc_1800717F2
0x1800717d2  mov     r13, [rax+10h]
0x1800717d6  mov     [rsp+1C0h+var_168], r13
0x1800717db  test    r13, r13
0x1800717de  jz      short loc_1800717FC
0x1800717e0  cmp     [r13+10h], edx
0x1800717e4  jz      short loc_1800717F7
0x1800717e6  mov     rax, [rax+8]
0x1800717ea  mov     r13, r15
0x1800717ed  mov     [rsp+1C0h+var_168], r15
0x1800717f2  test    rax, rax
0x1800717f5  jnz     short loc_1800717D2
0x1800717f7  test    r13, r13
0x1800717fa  jnz     short loc_180071859
0x1800717fc  cmp     rcx, r14
0x1800717ff  jz      short loc_18007182D
0x180071801  test    byte ptr [rcx+1Ch], 80h
0x180071805  jz      short loc_18007182D
0x180071807  cmp     byte ptr [rcx+19h], 5
0x18007180b  jb      short loc_18007182D
0x18007180d  mov     r9, [rsi+8]
0x180071811  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180071818  mov     rcx, [rcx+10h]
0x18007181c  mov     edx, 0E9h
0x180071821  call    WPP_SF_S
0x180071826  mov     rcx, cs:WPP_GLOBAL_Control
0x18007182d  mov     edi, 26Eh
0x180071832  cmp     rcx, r14
0x180071835  jz      loc_180071787
0x18007183b  test    byte ptr [rcx+1Ch], 80h
0x18007183f  jz      loc_180071787
0x180071845  cmp     byte ptr [rcx+19h], 2
0x180071849  jb      loc_180071787
0x18007184f  mov     edx, 0EAh
0x180071854  jmp     loc_18007176D
0x180071859  mov     ebx, [r13+0]
0x18007185d  mov     rcx, rsi
0x180071860  call    UpdateEntryTimeStamp
0x180071865  mov     rcx, [rsi+8]; lpWideCharStr
0x180071869  call    StrDupAFromTInternal
0x18007186e  mov     r14, rax
0x180071871  test    rax, rax
0x180071874  jz      loc_18007470B
0x18007187a  mov     rdx, rax
0x18007187d  mov     ecx, ebx
0x18007187f  call    RasfileFindSectionLine
0x180071884  test    eax, eax
0x180071886  jz      short loc_18007188F
0x180071888  mov     ecx, ebx
0x18007188a  call    DeleteCurrentSection
0x18007188f  mov     rcx, r14; hMem
0x180071892  call    cs:__imp_GlobalFree
0x180071899  nop     dword ptr [rax+rax+00h]
0x18007189e  cmp     [r12], r15d
0x1800718a2  jnz     loc_18007315F
0x1800718a8  mov     r12d, 2
0x1800718ae  xor     r8d, r8d
0x1800718b1  mov     r9b, r12b
0x1800718b4  mov     byte ptr [rsp+1C0h+lpMultiByteStr], r12b
0x1800718b9  mov     dl, 3Fh ; '?'
0x1800718bb  mov     ecx, ebx
0x1800718bd  call    rasFindLine
0x1800718c2  mov     rdx, [rsi+8]
0x1800718c6  mov     ecx, ebx
0x1800718c8  call    InsertSection
0x1800718cd  mov     edi, eax
0x1800718cf  test    eax, eax
0x1800718d1  jnz     loc_18007462B
0x1800718d7  lea     r8d, [r12-1]
0x1800718dc  mov     ecx, ebx
0x1800718de  lea     rdx, aEncoding; "Encoding"
0x1800718e5  call    InsertLong
0x1800718ea  mov     edi, eax
0x1800718ec  test    eax, eax
0x1800718ee  jnz     loc_1800745F6
0x1800718f4  lea     r8d, [r12+6]
0x1800718f9  mov     ecx, ebx
0x1800718fb  lea     rdx, aPbversion; "PBVersion"
0x180071902  call    InsertLong
0x180071907  mov     edi, eax
0x180071909  test    eax, eax
0x18007190b  jnz     loc_1800745C1
0x180071911  mov     r8d, [rsi+18h]
0x180071915  lea     rdx, aType; "Type"
0x18007191c  mov     ecx, ebx
0x18007191e  call    InsertLong
0x180071923  mov     edi, eax
0x180071925  test    eax, eax
0x180071927  jnz     loc_18007458C
0x18007192d  cmp     [rsi+0B0h], r15d
0x180071934  lea     r8, a1; "1"
0x18007193b  lea     r14, a0; "0"
0x180071942  mov     ecx, ebx
0x180071944  cmovz   r8, r14
0x180071948  lea     rdx, aAutologon; "AutoLogon"
0x18007194f  call    InsertStringA
0x180071954  mov     edi, eax
0x180071956  test    eax, eax
0x180071958  jnz     loc_180074557
  ... truncated ...
```
