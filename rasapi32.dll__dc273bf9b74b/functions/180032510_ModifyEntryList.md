# ModifyEntryList

- ea: `0x180032510`
- end: `0x18003533a`
- name: `ModifyEntryList`
- size: `11818`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180005af0`

## callees

- `0x180002418`
- `0x1800054c0`
- `0x180006514`
- `0x18000e964`
- `0x1800300ec`
- `0x180032510`
- `0x18003e654`
- `0x18003e88c`
- `0x18004e580`
- `0x18004e984`
- `0x18007e5f0`
- `0x1800ca68c`
- `0x1800ca820`
- `0x1800cc364`
- `0x1800cc568`
- `0x1800cda18`
- `0x1800cda3c`
- `0x1800cdb80`
- `0x1800cdbf4`
- `0x1800ce25c`
- `0x1800ce4c4`
- `0x1800ce628`
- `0x1800d0b08`
- `0x1800d0ca8`
- `0x1800d1174`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800327d0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800327d0`
- `rtutils!TracePrintfExA` at `0x180032606`
- `rtutils!TracePrintfExA` at `0x1800326b3`
- `rtutils!TracePrintfExA` at `0x18003273f`
- `rtutils!TracePrintfExA` at `0x1800352dc`
- `rtutils!TracePrintfExA` at `0x180032606`
- `rtutils!TracePrintfExA` at `0x1800326b3`
- `rtutils!TracePrintfExA` at `0x18003273f`
- `rtutils!TracePrintfExA` at `0x1800352dc`

## string_xrefs

- `0x18003375a`: `ApnInfoCompression`
- `0x180032ade`: `CustomDialDll`
- `0x180033798`: `DeviceComplianceSsoEnabled`
- `0x180032d95`: `ShowMonitorIconInTaskBar`
- `0x180032a43`: `RedialAttempts`
- `0x18003296a`: `LcpExtensions`
- `0x180032cd1`: `PreferredCompression`
- `0x1800337b7`: `DeviceComplianceSsoEku`
- `0x180032aa0`: `RedialOnLinkFailure`
- `0x18003371c`: `ApnInfoAccessPoint`
- `0x180033779`: `DeviceComplianceEnabled`
- `0x180032d09`: `PreferredMdmProtocol`
- `0x1800329a8`: `SwCompression`
- `0x1800337d6`: `DeviceComplianceSsoIssuer`
- `0x180032cb5`: `PreferredProtocol`
- `0x180032b1c`: `CustomRasDialDll`
- `0x18003294b`: `ExcludedProtocols`
- `0x1800329c7`: `NegotiateMultilinkAlways`
- `0x180032e5b`: `IpHeaderCompression`
- `0x1800336a0`: `SecurityDescriptor`
- `0x180033919`: `PowershellCreatedProfile`
- `0x180033b48`: `PluginStorage`
- `0x180033252`: `ImsConfig`
- `0x1800332ed`: `CacheCredentials`
- `0x180033b93`: `ProtocolListLength`
- `0x180032b3d`: `ForceSecureCompartment`
- `0x1800339e5`: `AutoConfigScript`
- `0x180033bf4`: `ProtocolListCurrentProtocol`
- `0x180033bd5`: `ProtocolListRetryTimeInHours`
- `0x180033bb8`: `ProtocolList`
- `0x180033c32`: `ProtocolListTimeOfLastProtocolSelectionHigh`
- `0x180033c13`: `ProtocolListTimeOfLastProtocolSelectionLow`

## pseudocode

```c
__int64 __fastcall ModifyEntryList(__int64 a1, unsigned int *a2)
{
  char *v3; // rcx
  __int64 *v4; // rax
  unsigned int v5; // ebx
  int v6; // r12d
  __int64 i; // r13
  unsigned int *v8; // rdi
  unsigned int HRasfileForEntry; // eax
  unsigned int *HRasfileFromIndex; // r14
  unsigned int v11; // esi
  __int64 v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  void *v15; // rbp
  int v16; // edx
  int v17; // r9d
  unsigned int inserted; // eax
  __int64 v19; // r8
  unsigned int v20; // eax
  __int64 v21; // r8
  const WCHAR *v22; // r8
  const WCHAR *v23; // r8
  const WCHAR *v24; // r8
  const WCHAR *v25; // r8
  const WCHAR *v26; // r8
  const WCHAR *v27; // r8
  const WCHAR *v28; // r8
  const WCHAR *v29; // r8
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  __int64 v33; // r8
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 v38; // rdx
  unsigned int v39; // r8d
  __int64 v40; // r8
  __int64 v41; // r8
  __int64 v42; // rcx
  char *v43; // rdx
  unsigned int v44; // r9d
  unsigned int v45; // r8d
  HGLOBAL v46; // rbp
  unsigned int v47; // eax
  __int64 v48; // rcx
  char *v49; // rdx
  unsigned int v50; // r9d
  unsigned int v51; // r8d
  HGLOBAL v52; // rbp
  __int64 v53; // r8
  __int64 v54; // r8
  __int64 v55; // r8
  __int64 v56; // r8
  __int64 v57; // r8
  __int64 v58; // r9
  __int64 j; // rbp
  __int64 v60; // r14
  int v61; // edx
  int v62; // r9d
  __int64 v63; // r8
  __int64 v64; // rdx
  __int64 v65; // rdx
  __int64 v66; // r9
  char *v67; // rcx
  __int64 v68; // rdx
  unsigned int v70; // edi
  unsigned int *v71; // [rsp+70h] [rbp+8h] BYREF
  unsigned int *v72; // [rsp+78h] [rbp+10h]
  HGLOBAL hMem; // [rsp+80h] [rbp+18h] BYREF

  v72 = a2;
  v3 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 230, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
    v3 = (char *)WPP_GLOBAL_Control;
  }
  v4 = *(__int64 **)(a1 + 16);
  v5 = 0;
  v6 = 0;
  v71 = 0;
  for ( i = *v4; ; i = *(_QWORD *)(i + 8) )
  {
    if ( !i )
    {
      if ( !v5 )
      {
        v70 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 16LL) - v6;
        if ( v3 != (char *)&WPP_GLOBAL_Control && v3[28] < 0 && (unsigned __int8)v3[25] >= 5u )
        {
          WPP_SF_d(*((_QWORD *)v3 + 2), 336, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v70);
          v3 = (char *)WPP_GLOBAL_Control;
        }
        if ( g_dwTraceId != -1 )
        {
          TracePrintfExA(g_dwTraceId, 0xCu, "ModifyEntryList: Number of connections written %d", v70);
          v3 = (char *)WPP_GLOBAL_Control;
        }
        *v72 = v70;
      }
      goto LABEL_683;
    }
    v8 = *(unsigned int **)(i + 16);
    if ( !v8[133] && !v8[135] )
      continue;
    if ( (*(_DWORD *)(a1 + 32) & 0x100) != 0 && v8[137] )
    {
      if ( v3 != (char *)&WPP_GLOBAL_Control && v3[28] < 0 && (unsigned __int8)v3[25] >= 5u )
        WPP_SF_S(*((_QWORD *)v3 + 2), 231, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, *((_QWORD *)v8 + 1));
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "Entry %S not written to hidden pbk", *((const wchar_t **)v8 + 1));
      v8[133] = 0;
      v8[135] = 0;
      goto LABEL_18;
    }
    if ( *v8 == -1 )
    {
      HRasfileForEntry = GetHRasfileForEntry(a1, *(_QWORD *)(i + 16), &v71);
      v5 = HRasfileForEntry;
      if ( HRasfileForEntry )
      {
        v3 = (char *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            232,
            &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids,
            HRasfileForEntry);
          v3 = (char *)WPP_GLOBAL_Control;
        }
        if ( g_dwTraceId != -1 )
        {
          TracePrintfExA(
            g_dwTraceId,
            0xCu,
            "ModifyEntryList: GetHRasfileForEntry for entry %S failed with err %d",
            *((const wchar_t **)v8 + 1),
            v5);
LABEL_18:
          v3 = (char *)WPP_GLOBAL_Control;
          continue;
        }
        continue;
      }
      HRasfileFromIndex = v71;
    }
    else
    {
      HRasfileFromIndex = (unsigned int *)GetHRasfileFromIndex(*(_QWORD *)(a1 + 48), *v8, 0);
      v71 = HRasfileFromIndex;
    }
    if ( HRasfileFromIndex )
      break;
    v3 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        233,
        &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids,
        *((_QWORD *)v8 + 1));
      v3 = (char *)WPP_GLOBAL_Control;
    }
    if ( g_dwTraceId != -1 )
    {
      TracePrintfExA(
        g_dwTraceId,
        0xCu,
        "ModifyEntryList: Could not get matching HRASFILEDATA. Ignoring entry %S",
        *((const wchar_t **)v8 + 1));
      v3 = (char *)WPP_GLOBAL_Control;
    }
    v5 = 622;
    if ( v3 != (char *)&WPP_GLOBAL_Control && v3[28] < 0 && (unsigned __int8)v3[25] >= 2u )
    {
      WPP_SF_d(*((_QWORD *)v3 + 2), 234, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 622);
      goto LABEL_18;
    }
LABEL_19:
    ;
  }
  v11 = *HRasfileFromIndex;
  UpdateEntryTimeStamp(v8);
  v12 = StrDupAFromTInternal(*((LPCWCH *)v8 + 1));
  v15 = (void *)v12;
  if ( !v12 )
  {
    inserted = 8;
    v5 = 8;
    v3 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v5;
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_683;
    v65 = 235;
LABEL_672:
    v66 = inserted;
LABEL_673:
    WPP_SF_d(*((_QWORD *)v3 + 2), v65, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v66);
LABEL_674:
    v3 = (char *)WPP_GLOBAL_Control;
    goto LABEL_683;
  }
  if ( (unsigned int)RasfileFindSectionLine(v11, v12, v13, v14) )
    DeleteCurrentSection(v11);
  GlobalFree(v15);
  if ( v8[135] )
  {
    HRasfileFromIndex[5] |= 1u;
    ++v6;
LABEL_262:
    v3 = (char *)WPP_GLOBAL_Control;
    goto LABEL_19;
  }
  LOBYTE(v17) = 2;
  LOBYTE(v16) = 63;
  rasFindLine(v11, v16, 0, v17, 2);
  inserted = InsertSection(v11, *((_QWORD *)v8 + 1));
  v5 = inserted;
  if ( inserted )
  {
    v3 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v5;
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_683;
    v65 = 236;
    goto LABEL_672;
  }
  inserted = InsertLong(v11, "Encoding", 1);
  v5 = inserted;
  if ( inserted )
  {
    v3 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v5;
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_683;
    v65 = 237;
    goto LABEL_672;
  }
  inserted = InsertLong(v11, "PBVersion", 8);
  v5 = inserted;
  if ( inserted )
  {
    v3 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v5;
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_683;
    v65 = 238;
    goto LABEL_672;
  }
  inserted = InsertLong(v11, "Type", v8[6]);
  v5 = inserted;
  if ( inserted )
  {
    v3 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v5;
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_683;
    v65 = 239;
    goto LABEL_672;
  }
  inserted = InsertFlag(v11, "AutoLogon", v8[44]);
  v5 = inserted;
  if ( inserted )
  {
    v3 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v5;
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_683;
    v65 = 240;
    goto LABEL_672;
  }
  inserted = InsertFlag(v11, "UseRasCredentials", v8[45]);
  v5 = inserted;
  if ( inserted )
  {
    v3 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v5;
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_683;
    v65 = 241;
    goto LABEL_672;
  }
  inserted = InsertLong(v11, "LowDateTime", v8[4]);
  v5 = inserted;
  if ( inserted )
  {
    v3 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v5;
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_683;
    v65 = 242;
    goto LABEL_672;
  }
  inserted = InsertLong(v11, "HighDateTime", v8[5]);
  v5 = inserted;
  if ( inserted )
  {
    v3 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v5;
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_683;
    v65 = 243;
    goto LABEL_672;
  }
  inserted = InsertLong(v11, "DialParamsUID", v8[114]);
  v5 = inserted;
  if ( inserted )
  {
    v3 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v5;
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_683;
    v65 = 244;
    goto LABEL_672;
  }
  v19 = *((_QWORD *)v8 + 58);
  if ( v19 )
  {
    v20 = InsertBinary(v11, "Guid", v19, 16);
    v5 = v20;
    if ( v20 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 245, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v20);
          v3 = (char *)WPP_GLOBAL_Control;
        }
        if ( v3 != (char *)&WPP_GLOBAL_Control && v3[28] < 0 && (unsigned __int8)v3[25] >= 6u )
        {
          v64 = 246;
          goto LABEL_687;
        }
      }
      return v5;
    }
  }
  inserted = InsertLong(v11, "VpnStrategy", v8[42]);
  v5 = inserted;
  if ( inserted )
  {
    v3 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v5;
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_683;
    v65 = 247;
    goto LABEL_672;
  }
  inserted = InsertLong(v11, "ExcludedProtocols", v8[59]);
  v5 = inserted;
  if ( inserted )
  {
    v3 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v5;
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_683;
    v65 = 248;
    goto LABEL_672;
  }
  inserted = InsertFlag(v11, "LcpExtensions", v8[60]);
  v5 = inserted;
  if ( inserted )
  {
    v3 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v5;
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_683;
    v65 = 249;
    goto LABEL_672;
  }
  inserted = InsertLong(v11, "DataEncryption", v8[43]);
  v5 = inserted;
  if ( inserted )
  {
    v3 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v5;
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_683;
    v65 = 250;
    goto LABEL_672;
  }
  v5 = InsertFlag(v11, "SwCompression", v8[61]);
  if ( v5 )
    goto LABEL_615;
  v5 = InsertFlag(v11, "NegotiateMultilinkAlways", v8[62]);
  if ( v5 )
    goto LABEL_615;
  v5 = InsertFlag(v11, "SkipDoubleDialDialog", v8[63]);
  if ( v5 )
    goto LABEL_615;
  v5 = InsertLong(v11, "DialMode", v8[33]);
  if ( v5 )
    goto LABEL_615;
  v5 = InsertLong(v11, "OverridePref", v8[36]);
  if ( v5 )
    goto LABEL_615;
  v5 = InsertLong(v11, "RedialAttempts", v8[37]);
  if ( v5 )
    goto LABEL_615;
  v5 = InsertLong(v11, "RedialSeconds", v8[38]);
  if ( v5 )
    goto LABEL_615;
  v5 = InsertLong(v11, "IdleDisconnectSeconds", v8[39]);
  if ( v5 )
    goto LABEL_615;
  v5 = InsertFlag(v11, "RedialOnLinkFailure", v8[40]);
  if ( v5 )
    goto LABEL_615;
  v5 = InsertLong(v11, "CallbackMode", v8[105]);
  if ( v5 )
    goto LABEL_615;
  v5 = InsertString(v11, "CustomDialDll", *((_QWORD *)v8 + 54));
  if ( !v5 )
  {
    v5 = InsertString(v11, "CustomDialFunc", *((_QWORD *)v8 + 55));
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 252;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertString(v11, "CustomRasDialDll", *((_QWORD *)v8 + 56));
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 253;
        goto LABEL_687;
      }
      return v5;
    }
    v8[46] = 0;
    v5 = InsertFlag(v11, "ForceSecureCompartment", 0);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 254;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertFlag(v11, "DisableIKENameEkuCheck", v8[47]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 255;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertFlag(v11, "AuthenticateServer", v8[106]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 256;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertFlag(v11, "ShareMsFilePrint", v8[64]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 257;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertFlag(v11, "BindMsNetClient", v8[65]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 258;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertFlag(v11, "SharedPhoneNumbers", v8[10]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 259;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertFlag(v11, "GlobalDeviceSettings", v8[11]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 260;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertString(v11, "PrerequisiteEntry", *((_QWORD *)v8 + 7));
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 261;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertString(v11, "PrerequisitePbk", *((_QWORD *)v8 + 8));
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 262;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertString(v11, "PreferredPort", *((_QWORD *)v8 + 9));
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 263;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertString(v11, "PreferredDevice", *((_QWORD *)v8 + 10));
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 264;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertLong(v11, "PreferredBps", v8[22]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 265;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertFlag(v11, "PreferredHwFlow", v8[23]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 266;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertFlag(v11, "PreferredProtocol", v8[24]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 267;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertFlag(v11, "PreferredCompression", v8[25]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 268;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertLong(v11, "PreferredSpeaker", v8[26]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 269;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertLong(v11, "PreferredMdmProtocol", v8[27]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 270;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertFlag(v11, "PreviewUserPw", v8[29]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 271;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertFlag(v11, "PreviewDomain", v8[30]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 272;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertFlag(v11, "PreviewPhoneNumber", v8[31]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 273;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertFlag(v11, "ShowDialingProgress", v8[28]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 274;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertFlag(v11, "ShowMonitorIconInTaskBar", v8[12]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 275;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertLong(v11, "CustomAuthKey", v8[48]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 276;
        goto LABEL_687;
      }
      return v5;
    }
    v21 = *((_QWORD *)v8 + 25);
    if ( v21 )
    {
      v5 = InsertBinary(v11, "CustomAuthData", v21, v8[52]);
      if ( v5 )
      {
        v3 = (char *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
        {
          v64 = 277;
          goto LABEL_687;
        }
        return v5;
      }
    }
    v5 = InsertLong(v11, "AuthRestrictions", v8[41]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 278;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertFlag(v11, "IpPrioritizeRemote", v8[68]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 279;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertLong(v11, "IpInterfaceMetric", v8[88]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 280;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertFlag(v11, "IpHeaderCompression", v8[69]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 281;
        goto LABEL_687;
      }
      return v5;
    }
    v22 = L"0.0.0.0";
    if ( *((_QWORD *)v8 + 35) )
      v22 = (const WCHAR *)*((_QWORD *)v8 + 35);
    v5 = InsertString(v11, "IpAddress", v22);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 282;
        goto LABEL_687;
      }
      return v5;
    }
    v23 = L"0.0.0.0";
    if ( *((_QWORD *)v8 + 36) )
      v23 = (const WCHAR *)*((_QWORD *)v8 + 36);
    v5 = InsertString(v11, "IpDnsAddress", v23);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 283;
        goto LABEL_687;
      }
      return v5;
    }
    v24 = L"0.0.0.0";
    if ( *((_QWORD *)v8 + 37) )
      v24 = (const WCHAR *)*((_QWORD *)v8 + 37);
    v5 = InsertString(v11, "IpDns2Address", v24);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 284;
        goto LABEL_687;
      }
      return v5;
    }
    v25 = L"0.0.0.0";
    if ( *((_QWORD *)v8 + 38) )
      v25 = (const WCHAR *)*((_QWORD *)v8 + 38);
    v5 = InsertString(v11, "IpWinsAddress", v25);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 285;
        goto LABEL_687;
      }
      return v5;
    }
    v26 = L"0.0.0.0";
    if ( *((_QWORD *)v8 + 39) )
      v26 = (const WCHAR *)*((_QWORD *)v8 + 39);
    v5 = InsertString(v11, "IpWins2Address", v26);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 286;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertLong(v11, "IpAssign", v8[80]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 287;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertLong(v11, "IpNameAssign", v8[81]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 288;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertLong(v11, "IpDnsFlags", v8[82]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 289;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertLong(v11, "IpNBTFlags", v8[83]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 290;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertLong(v11, "TcpWindowSize", v8[84]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 291;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertLong(v11, "UseFlags", v8[34]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 292;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertLong(v11, "IpSecFlags", v8[35]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 293;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertString(v11, "IpDnsSuffix", *((_QWORD *)v8 + 43));
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 294;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertLong(v11, "Ipv6Assign", v8[89]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 295;
        goto LABEL_687;
      }
      return v5;
    }
    v27 = L"::";
    if ( *((_QWORD *)v8 + 45) )
      v27 = (const WCHAR *)*((_QWORD *)v8 + 45);
    v5 = InsertString(v11, "Ipv6Address", v27);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 296;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertLong(v11, "Ipv6PrefixLength", v8[92]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 297;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertFlag(v11, "Ipv6PrioritizeRemote", v8[93]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 298;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertLong(v11, "Ipv6InterfaceMetric", v8[104]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 299;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertLong(v11, "Ipv6NameAssign", v8[94]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 300;
        goto LABEL_687;
      }
      return v5;
    }
    v28 = L"::";
    if ( *((_QWORD *)v8 + 48) )
      v28 = (const WCHAR *)*((_QWORD *)v8 + 48);
    v5 = InsertString(v11, "Ipv6DnsAddress", v28);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 301;
        goto LABEL_687;
      }
      return v5;
    }
    v29 = L"::";
    if ( *((_QWORD *)v8 + 49) )
      v29 = (const WCHAR *)*((_QWORD *)v8 + 49);
    v5 = InsertString(v11, "Ipv6Dns2Address", v29);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 302;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertBinary(v11, "Ipv6Prefix", v8 + 102, 8);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 303;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertBinary(v11, "Ipv6InterfaceId", v8 + 100, 8);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 304;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertFlag(v11, "DisableClassBasedDefaultRoute", v8[136]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 305;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertFlag(v11, "DisableMobility", v8[122]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 306;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertLong(v11, "NetworkOutageTime", v8[123]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 307;
        goto LABEL_687;
      }
      return v5;
    }
    if ( (unsigned int)InsertString(v11, "IDI", *((_QWORD *)v8 + 62)) )
    {
      v67 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 308, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 1);
          v67 = (char *)WPP_GLOBAL_Control;
        }
        if ( v67 != (char *)&WPP_GLOBAL_Control && v67[28] < 0 && (unsigned __int8)v67[25] >= 6u )
        {
          v68 = 309;
LABEL_389:
          WPP_SF_d(*((_QWORD *)v67 + 2), v68, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 1);
        }
      }
      return 1;
    }
    if ( (unsigned int)InsertString(v11, "IDR", *((_QWORD *)v8 + 63)) )
    {
      v67 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 310, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 1);
          v67 = (char *)WPP_GLOBAL_Control;
        }
        if ( v67 != (char *)&WPP_GLOBAL_Control && v67[28] < 0 && (unsigned __int8)v67[25] >= 6u )
        {
          v68 = 311;
          goto LABEL_389;
        }
      }
      return 1;
    }
    v30 = InsertFlag(v11, "ImsConfig", v8[128]);
    v5 = v30;
    if ( v30 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 312, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v30);
          v3 = (char *)WPP_GLOBAL_Control;
        }
        if ( v3 != (char *)&WPP_GLOBAL_Control && v3[28] < 0 && (unsigned __int8)v3[25] >= 6u )
        {
          v64 = 313;
          goto LABEL_687;
        }
      }
      return v5;
    }
    v31 = InsertLong(v11, "IdiType", v8[129]);
    v5 = v31;
    if ( v31 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 314, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v31);
          v3 = (char *)WPP_GLOBAL_Control;
        }
        if ( v3 != (char *)&WPP_GLOBAL_Control && v3[28] < 0 && (unsigned __int8)v3[25] >= 6u )
        {
          v64 = 315;
          goto LABEL_687;
        }
      }
      return v5;
    }
    v32 = InsertLong(v11, "IdrType", v8[130]);
    v5 = v32;
    if ( v32 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 316, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v32);
          v3 = (char *)WPP_GLOBAL_Control;
        }
        if ( v3 != (char *)&WPP_GLOBAL_Control && v3[28] < 0 && (unsigned __int8)v3[25] >= 6u )
        {
          v64 = 317;
          goto LABEL_687;
        }
      }
      return v5;
    }
    v5 = InsertLong(v11, "ProvisionType", v8[137]);
    if ( v5 )
      goto LABEL_615;
    v5 = InsertString(v11, "PreSharedKey", *((_QWORD *)v8 + 69));
    if ( v5 )
      goto LABEL_615;
    v5 = InsertFlag(v11, "CacheCredentials", v8[32]);
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 318;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertLong(v11, "NumCustomPolicy", v8[149]);
    if ( v5 )
      goto LABEL_615;
    v33 = *((_QWORD *)v8 + 76);
    if ( v33 )
    {
      if ( v8[149] )
      {
        v5 = InsertBinary(v11, "CustomIPSecPolicies", v33, v8[150]);
        if ( v5 )
          goto LABEL_615;
      }
    }
    v5 = InsertLong(v11, "NumEku", v8[154]);
    if ( v5 )
      goto LABEL_615;
    v34 = *((_QWORD *)v8 + 78);
    if ( v34 )
    {
      if ( v8[154] )
      {
        v35 = v8[155];
        if ( (_DWORD)v35 )
        {
          v5 = InsertBinary(v11, "CertificateEKU", v34, v35);
          if ( v5 )
            goto LABEL_615;
        }
      }
    }
    v5 = InsertFlag(v11, "UseMachineRootCert", v8[158]);
    if ( v5 )
      goto LABEL_615;
    if ( v8[158] == 1 )
    {
      v36 = *((_QWORD *)v8 + 81);
      if ( v36 )
      {
        v37 = v8[160];
        if ( (_DWORD)v37 )
        {
          v5 = InsertBinary(v11, "RootCertificate", v36, v37);
          if ( v5 )
            goto LABEL_615;
        }
      }
    }
    inserted = InsertFlag(v11, "Disable_IKEv2_Fragmentation", v8[131]);
    v5 = inserted;
    if ( inserted )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v65 = 319;
          goto LABEL_672;
        }
LABEL_683:
        if ( v3 != (char *)&WPP_GLOBAL_Control && v3[28] < 0 && (unsigned __int8)v3[25] >= 6u )
        {
          v64 = 337;
LABEL_687:
          WPP_SF_d(*((_QWORD *)v3 + 2), v64, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v5);
        }
      }
      return v5;
    }
    inserted = InsertFlag(v11, "PlumbIKEv2TSAsRoutes", v8[132]);
    v5 = inserted;
    if ( inserted )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v65 = 320;
          goto LABEL_672;
        }
        goto LABEL_683;
      }
      return v5;
    }
    v5 = InsertLong(v11, "NumServers", v8[164]);
    if ( v5 )
      goto LABEL_615;
    v38 = *((_QWORD *)v8 + 83);
    if ( v38 )
    {
      v39 = v8[164];
      if ( v39 )
      {
        inserted = CreateServerLists(v11, v38, v39);
        v5 = inserted;
        if ( inserted )
        {
          v3 = (char *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v65 = 321;
              goto LABEL_672;
            }
            goto LABEL_683;
          }
          return v5;
        }
      }
    }
    inserted = InsertLong(v11, "RouteVersion", 1);
    v5 = inserted;
    if ( inserted )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v65 = 322;
          goto LABEL_672;
        }
        goto LABEL_683;
      }
      return v5;
    }
    inserted = InsertLong(v11, "NumRoutes", v8[168]);
    v5 = inserted;
    if ( inserted )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v65 = 323;
          goto LABEL_672;
        }
        goto LABEL_683;
      }
      return v5;
    }
    v40 = *((_QWORD *)v8 + 85);
    if ( v40 )
    {
      if ( v8[168] )
      {
        inserted = InsertBinary(v11, "Routes", v40, v8[169]);
        v5 = inserted;
        if ( inserted )
        {
          v3 = (char *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v65 = 324;
              goto LABEL_672;
            }
            goto LABEL_683;
          }
          return v5;
        }
      }
    }
    inserted = InsertLong(v11, "NumNrptRules", v8[172]);
    v5 = inserted;
    if ( inserted )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v65 = 325;
          goto LABEL_672;
        }
        goto LABEL_683;
      }
      return v5;
    }
    v41 = *((_QWORD *)v8 + 87);
    if ( v41 )
    {
      if ( v8[172] )
      {
        inserted = InsertBinary(v11, "NrptRules", v41, v8[173]);
        v5 = inserted;
        if ( inserted )
        {
          v3 = (char *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v65 = 326;
              goto LABEL_672;
            }
            goto LABEL_683;
          }
          return v5;
        }
      }
    }
    inserted = InsertFlag(v11, "AutoTiggerCapable", v8[176]);
    v5 = inserted;
    if ( inserted )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v65 = 327;
          goto LABEL_672;
        }
        goto LABEL_683;
      }
      return v5;
    }
    v5 = InsertLong(v11, "NumAppIds", v8[182]);
    if ( v5 )
      goto LABEL_615;
    v43 = (char *)*((_QWORD *)v8 + 92);
    if ( v43 )
    {
      v44 = v8[182];
      if ( v44 )
      {
        v45 = v8[183];
        hMem = 0;
        inserted = CreateDtlList(v42, v43, v45, v44, &hMem);
        v5 = inserted;
        if ( inserted )
        {
          v3 = (char *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v65 = 328;
              goto LABEL_672;
            }
            goto LABEL_683;
          }
          return v5;
        }
        v46 = hMem;
        v47 = InsertStringList(v11, "ApplicationIds", hMem);
        v5 = v47;
        if ( v47 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((char *)WPP_GLOBAL_Control + 28) < 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 329, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v47);
          }
          DtlDestroyList(v46);
          goto LABEL_674;
        }
        DtlDestroyList(v46);
      }
    }
    v5 = InsertLong(v11, "NumClassicAppIds", v8[177]);
    if ( v5 )
      goto LABEL_615;
    v49 = (char *)*((_QWORD *)v8 + 90);
    if ( v49 )
    {
      v50 = v8[177];
      if ( v50 )
      {
        v51 = v8[178];
        hMem = 0;
        inserted = CreateDtlList(v48, v49, v51, v50, &hMem);
        v5 = inserted;
        if ( inserted )
        {
          v3 = (char *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v65 = 330;
              goto LABEL_672;
            }
            goto LABEL_683;
          }
          return v5;
        }
        v52 = hMem;
        v5 = InsertStringList(v11, "ClassicApplicationIds", hMem);
        if ( v5 )
        {
          DtlDestroyList(v52);
          v3 = (char *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return v5;
          if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_683;
          v65 = 331;
          v66 = v5;
          goto LABEL_673;
        }
        DtlDestroyList(v52);
      }
    }
    inserted = InsertString(v11, "SecurityDescriptor", *((_QWORD *)v8 + 93));
    v5 = inserted;
    if ( inserted )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v65 = 332;
          goto LABEL_672;
        }
        goto LABEL_683;
      }
      return v5;
    }
    v5 = InsertString(v11, "ApnInfoProviderId", *((_QWORD *)v8 + 108));
    if ( v5 )
      goto LABEL_615;
    v5 = InsertString(v11, "ApnInfoUsername", *((_QWORD *)v8 + 110));
    if ( v5 )
      goto LABEL_615;
    v5 = InsertString(v11, "ApnInfoPassword", *((_QWORD *)v8 + 111));
    if ( v5 )
      goto LABEL_615;
    v5 = InsertString(v11, "ApnInfoAccessPoint", *((_QWORD *)v8 + 109));
    if ( v5 )
      goto LABEL_615;
    v5 = InsertLong(v11, "ApnInfoAuthentication", v8[225]);
    if ( v5 )
      goto LABEL_615;
    v5 = InsertFlag(v11, "ApnInfoCompression", v8[224]);
    if ( v5 )
      goto LABEL_615;
    v5 = InsertFlag(v11, "DeviceComplianceEnabled", v8[226]);
    if ( v5 )
      goto LABEL_615;
    v5 = InsertFlag(v11, "DeviceComplianceSsoEnabled", v8[228]);
    if ( v5 )
      goto LABEL_615;
    v5 = InsertString(v11, "DeviceComplianceSsoEku", *((_QWORD *)v8 + 115));
    if ( v5 )
      goto LABEL_615;
    v5 = InsertString(v11, "DeviceComplianceSsoIssuer", *((_QWORD *)v8 + 116));
    if ( v5 )
      goto LABEL_615;
    v5 = InsertLong(v11, "FlagsSet", v8[238]);
    if ( v5 )
      goto LABEL_615;
    v5 = InsertLong(v11, "Options", v8[239]);
    if ( v5 )
      goto LABEL_615;
    v5 = InsertFlag(v11, "DisableDefaultDnsSuffixes", v8[197]);
    if ( v5 )
      goto LABEL_615;
    v5 = InsertLong(v11, "NumTrustedNetworks", v8[198]);
    if ( v5 )
      goto LABEL_615;
    v53 = *((_QWORD *)v8 + 100);
    if ( v53 )
    {
      if ( v8[198] )
      {
        v5 = InsertBinary(v11, "TrustedNetworks", v53, v8[199]);
        if ( v5 )
          goto LABEL_615;
      }
    }
    v54 = *((_QWORD *)v8 + 95);
    if ( v54 )
    {
      v5 = InsertBinary(v11, "ThirdPartyProfileInfo", v54, v8[188]);
      if ( v5 )
        goto LABEL_615;
    }
    v5 = InsertLong(v11, "NumDnsSearchSuffixes", v8[192]);
    if ( v5 )
      goto LABEL_615;
    v55 = *((_QWORD *)v8 + 97);
    if ( v55 )
    {
      v5 = InsertBinary(v11, "DnsSuffixSearchList", v55, v8[193]);
      if ( v5 )
        goto LABEL_615;
    }
    v5 = InsertFlag(v11, "PowershellCreatedProfile", v8[196]);
    if ( v5 )
      goto LABEL_615;
    v5 = InsertLong(v11, "ProxyFlags", v8[140]);
    if ( v5 )
      goto LABEL_615;
    v5 = InsertFlag(v11, "ProxySettingsModified", v8[205]);
    if ( v5 )
      goto LABEL_615;
    if ( (v8[140] & 2) != 0 )
    {
      v5 = InsertString(v11, "Proxy", *((_QWORD *)v8 + 72));
      if ( v5 )
        goto LABEL_615;
      v5 = InsertString(v11, "ExcludeList", *((_QWORD *)v8 + 73));
      if ( v5 )
        goto LABEL_615;
      v5 = InsertFlag(v11, "BypassProxyForLocal", v8[148]);
      if ( v5 )
        goto LABEL_615;
    }
    if ( (v8[140] & 4) != 0 )
    {
      v5 = InsertString(v11, "AutoConfigScript", *((_QWORD *)v8 + 71));
      if ( v5 )
        goto LABEL_615;
    }
    v5 = InsertString(v11, "ProvisioningAuthority", *((_QWORD *)v8 + 101));
    if ( v5 )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        v64 = 333;
        goto LABEL_687;
      }
      return v5;
    }
    v5 = InsertFlag(v11, "AuthTypeOTP", v8[204]);
    if ( v5 )
      goto LABEL_615;
    v5 = InsertFlag(v11, "GREKeyDefined", v8[206]);
    if ( v5 )
      goto LABEL_615;
    if ( v8[206] )
    {
      v5 = InsertULong(v11, "GREKey", v8[207]);
      if ( v5 )
      {
        v3 = (char *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
        {
          v64 = 334;
          goto LABEL_687;
        }
        return v5;
      }
    }
    v5 = InsertLong(v11, "NumPerAppTrafficFilters", v8[208]);
    if ( v5 )
      goto LABEL_615;
    v56 = *((_QWORD *)v8 + 105);
    if ( v56 )
    {
      if ( v8[208] )
      {
        v5 = InsertBinary(v11, "PerAppTrafficFilters", v56, v8[209]);
        if ( v5 )
          goto LABEL_615;
      }
    }
    v5 = InsertFlag(v11, "AlwaysOnCapable", v8[212]);
    if ( v5 )
      goto LABEL_615;
    inserted = InsertFlag(v11, "DeviceTunnel", v8[214]);
    v5 = inserted;
    if ( inserted )
    {
      v3 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v65 = 335;
          goto LABEL_672;
        }
        goto LABEL_683;
      }
      return v5;
    }
    v5 = InsertFlag(v11, "PrivateNetwork", v8[213]);
    if ( v5 )
      goto LABEL_615;
    v57 = *((_QWORD *)v8 + 118);
    if ( v57 )
    {
      v58 = v8[234];
      if ( (_DWORD)v58 )
      {
        v5 = InsertBinary(v11, "PluginStorage", v57, v58);
        if ( v5 )
          goto LABEL_615;
      }
    }
    v5 = InsertString(v11, "ManagementApp", *((_QWORD *)v8 + 120));
    if ( v5 )
      goto LABEL_615;
    if ( v8[42] == 15 )
    {
      v5 = InsertULong(v11, "ProtocolListLength", v8[242]);
      if ( v5 )
        goto LABEL_615;
      v5 = InsertBinary(v11, "ProtocolList", v8 + 243, 16);
      if ( v5 )
        goto LABEL_615;
      v5 = InsertULong(v11, "ProtocolListRetryTimeInHours", v8[247]);
      if ( v5 )
        goto LABEL_615;
      v5 = InsertULong(v11, "ProtocolListCurrentProtocol", v8[248]);
      if ( v5 )
        goto LABEL_615;
      v5 = InsertULong(v11, "ProtocolListTimeOfLastProtocolSelectionLow", v8[250]);
      if ( v5 )
        goto LABEL_615;
      v5 = InsertULong(v11, "ProtocolListTimeOfLastProtocolSelectionHigh", v8[251]);
      if ( v5 )
        goto LABEL_615;
    }
    InsertNetComponents(v11, *((_QWORD *)v8 + 33));
    for ( j = **((_QWORD **)v8 + 4); j; j = *(_QWORD *)(j + 8) )
    {
      v60 = *(_QWORD *)(j + 16);
      v5 = InsertGroup(v11, "MEDIA", *(_QWORD *)(v60 + 24));
      if ( v5 )
        break;
      v5 = InsertString(v11, "Port", *(_QWORD *)v60);
      if ( v5 )
        break;
      v63 = *(_QWORD *)(v60 + 16);
      if ( v63 )
      {
        v5 = InsertString(v11, "Device", v63);
        if ( v5 )
          break;
      }
      if ( *(_DWORD *)(v60 + 40) == 3 || (*(_BYTE *)(v60 + 48) & 4) != 0 )
      {
        v5 = InsertLong(v11, "ConnectBPS", *(unsigned int *)(v60 + 104));
        if ( v5 )
          break;
      }
      LOBYTE(v62) = 2;
      LOBYTE(v61) = 48;
      rasFindLine(v11, v61, 2, v62, 2);
      v5 = InsertDeviceList(a1, v11, v8, v60);
      if ( v5 )
        break;
    }
    if ( v8[137] )
    {
      v5 = InsertProxySettings(v11, v8);
      if ( v5 )
      {
LABEL_615:
        v3 = (char *)WPP_GLOBAL_Control;
        goto LABEL_683;
      }
    }
    v8[133] = 0;
    goto LABEL_262;
  }
  v3 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v64 = 251;
    goto LABEL_687;
  }
  return v5;
}

```

## disassembly

```asm
0x180032510  mov     [rsp+arg_18], rbx
0x180032515  mov     [rsp+arg_8], rdx
0x18003251a  push    rbp
0x18003251b  push    rsi
0x18003251c  push    rdi
0x18003251d  push    r12
0x18003251f  push    r13
0x180032521  push    r14
0x180032523  push    r15
0x180032525  sub     rsp, 30h
0x180032529  mov     r15, rcx
0x18003252c  mov     rcx, cs:WPP_GLOBAL_Control
0x180032533  lea     rdx, WPP_GLOBAL_Control
0x18003253a  cmp     rcx, rdx
0x18003253d  jz      short loc_18003256E
0x18003253f  test    byte ptr [rcx+1Ch], 80h
0x180032543  jz      short loc_18003256E
0x180032545  cmp     byte ptr [rcx+19h], 6
0x180032549  jb      short loc_18003256E
0x18003254b  mov     rcx, [rcx+10h]
0x18003254f  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180032556  mov     edx, 0E6h
0x18003255b  call    WPP_SF_
0x180032560  mov     rcx, cs:WPP_GLOBAL_Control
0x180032567  lea     rdx, WPP_GLOBAL_Control
0x18003256e  mov     rax, [r15+10h]
0x180032572  xor     ebx, ebx
0x180032574  xor     r12d, r12d
0x180032577  mov     [rsp+68h+arg_0], rbx
0x18003257c  or      ebp, 0FFFFFFFFh
0x18003257f  mov     r13, [rax]
0x180032582  lea     r14d, [rbx+2]
0x180032586  test    r13, r13
0x180032589  jz      loc_180035283
0x18003258f  mov     rdi, [r13+10h]
0x180032593  cmp     dword ptr [rdi+214h], 0
0x18003259a  jnz     short loc_1800325A9
0x18003259c  cmp     dword ptr [rdi+21Ch], 0
0x1800325a3  jz      loc_18003262E
0x1800325a9  test    dword ptr [r15+20h], 100h
0x1800325b1  jz      loc_180032637
0x1800325b7  cmp     dword ptr [rdi+224h], 0
0x1800325be  jz      short loc_180032637
0x1800325c0  cmp     rcx, rdx
0x1800325c3  jz      short loc_1800325EA
0x1800325c5  test    byte ptr [rcx+1Ch], 80h
0x1800325c9  jz      short loc_1800325EA
0x1800325cb  cmp     byte ptr [rcx+19h], 5
0x1800325cf  jb      short loc_1800325EA
0x1800325d1  mov     r9, [rdi+8]
0x1800325d5  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x1800325dc  mov     rcx, [rcx+10h]
0x1800325e0  mov     edx, 0E7h
0x1800325e5  call    WPP_SF_S
0x1800325ea  mov     eax, cs:g_dwTraceId
0x1800325f0  cmp     eax, ebp
0x1800325f2  jz      short loc_18003260C
0x1800325f4  mov     r9, [rdi+8]
0x1800325f8  lea     r8, aEntrySNotWritt; "Entry %S not written to hidden pbk"
0x1800325ff  mov     edx, 0Ch; dwFlags
0x180032604  mov     ecx, eax; dwTraceID
0x180032606  call    cs:__imp_TracePrintfExA
0x18003260c  mov     dword ptr [rdi+214h], 0
0x180032616  mov     dword ptr [rdi+21Ch], 0
0x180032620  mov     rcx, cs:WPP_GLOBAL_Control
0x180032627  lea     rdx, WPP_GLOBAL_Control
0x18003262e  mov     r13, [r13+8]
0x180032632  jmp     loc_180032586
0x180032637  cmp     [rdi], ebp
0x180032639  jnz     loc_1800326C5
0x18003263f  lea     r8, [rsp+68h+arg_0]
0x180032644  mov     rdx, rdi
0x180032647  mov     rcx, r15
0x18003264a  call    GetHRasfileForEntry
0x18003264f  mov     ebx, eax
0x180032651  test    eax, eax
0x180032653  jz      short loc_1800326BE
0x180032655  mov     rcx, cs:WPP_GLOBAL_Control
0x18003265c  lea     rsi, WPP_GLOBAL_Control
0x180032663  cmp     rcx, rsi
0x180032666  jz      short loc_180032693
0x180032668  test    byte ptr [rcx+1Ch], 80h
0x18003266c  jz      short loc_180032693
0x18003266e  cmp     [rcx+19h], r14b
0x180032672  jb      short loc_180032693
0x180032674  mov     rcx, [rcx+10h]
0x180032678  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18003267f  mov     edx, 0E8h
0x180032684  mov     r9d, eax
0x180032687  call    WPP_SF_d
0x18003268c  mov     rcx, cs:WPP_GLOBAL_Control
0x180032693  mov     eax, cs:g_dwTraceId
0x180032699  cmp     eax, ebp
0x18003269b  jz      short loc_180032627
0x18003269d  mov     r9, [rdi+8]
0x1800326a1  lea     r8, aModifyentrylis_1; "ModifyEntryList: GetHRasfileForEntry fo"...
0x1800326a8  mov     edx, 0Ch; dwFlags
0x1800326ad  mov     dword ptr [rsp+68h+var_48], ebx
0x1800326b1  mov     ecx, eax; dwTraceID
0x1800326b3  call    cs:__imp_TracePrintfExA
0x1800326b9  jmp     loc_180032620
0x1800326be  mov     r14, [rsp+68h+arg_0]
0x1800326c3  jmp     short loc_1800326DB
0x1800326c5  mov     rcx, [r15+30h]
0x1800326c9  xor     r8d, r8d
0x1800326cc  mov     edx, [rdi]
0x1800326ce  call    GetHRasfileFromIndex
0x1800326d3  mov     r14, rax
0x1800326d6  mov     [rsp+68h+arg_0], rax
0x1800326db  test    r14, r14
0x1800326de  jnz     loc_180032798
0x1800326e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800326eb  lea     rsi, WPP_GLOBAL_Control
0x1800326f2  cmp     rcx, rsi
0x1800326f5  jz      short loc_180032723
0x1800326f7  test    byte ptr [rcx+1Ch], 80h
0x1800326fb  jz      short loc_180032723
0x1800326fd  cmp     byte ptr [rcx+19h], 5
0x180032701  jb      short loc_180032723
0x180032703  mov     r9, [rdi+8]
0x180032707  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18003270e  mov     rcx, [rcx+10h]
0x180032712  mov     edx, 0E9h
0x180032717  call    WPP_SF_S
0x18003271c  mov     rcx, cs:WPP_GLOBAL_Control
0x180032723  mov     eax, cs:g_dwTraceId
0x180032729  cmp     eax, ebp
0x18003272b  jz      short loc_18003274C
0x18003272d  mov     r9, [rdi+8]
0x180032731  lea     r8, aModifyentrylis_0; "ModifyEntryList: Could not get matching"...
0x180032738  mov     edx, 0Ch; dwFlags
0x18003273d  mov     ecx, eax; dwTraceID
0x18003273f  call    cs:__imp_TracePrintfExA
0x180032745  mov     rcx, cs:WPP_GLOBAL_Control
0x18003274c  mov     ebx, 26Eh
0x180032751  lea     rdx, WPP_GLOBAL_Control
0x180032758  mov     r14d, 2
0x18003275e  cmp     rcx, rdx
0x180032761  jz      loc_18003262E
0x180032767  test    byte ptr [rcx+1Ch], 80h
0x18003276b  jz      loc_18003262E
0x180032771  cmp     [rcx+19h], r14b
0x180032775  jb      loc_18003262E
0x18003277b  mov     rcx, [rcx+10h]
0x18003277f  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180032786  mov     edx, 0EAh
0x18003278b  mov     r9d, ebx
0x18003278e  call    WPP_SF_d
0x180032793  jmp     loc_180032620
0x180032798  mov     esi, [r14]
0x18003279b  mov     rcx, rdi
0x18003279e  call    UpdateEntryTimeStamp
0x1800327a3  mov     rcx, [rdi+8]; lpWideCharStr
0x1800327a7  call    StrDupAFromTInternal
0x1800327ac  mov     rbp, rax
0x1800327af  test    rax, rax
0x1800327b2  jz      loc_180035230
0x1800327b8  mov     rdx, rax
0x1800327bb  mov     ecx, esi
0x1800327bd  call    RasfileFindSectionLine
0x1800327c2  test    eax, eax
0x1800327c4  jz      short loc_1800327CD
0x1800327c6  mov     ecx, esi
0x1800327c8  call    DeleteCurrentSection
0x1800327cd  mov     rcx, rbp; hMem
0x1800327d0  call    cs:__imp_GlobalFree
0x1800327d6  cmp     dword ptr [rdi+21Ch], 0
0x1800327dd  jnz     loc_180033D58
0x1800327e3  mov     r14d, 2
0x1800327e9  xor     r8d, r8d
0x1800327ec  mov     r9b, r14b
0x1800327ef  mov     byte ptr [rsp+68h+var_48], r14b
0x1800327f4  mov     dl, 3Fh ; '?'
0x1800327f6  mov     ecx, esi
0x1800327f8  call    rasFindLine
0x1800327fd  mov     rdx, [rdi+8]
0x180032801  mov     ecx, esi
0x180032803  call    InsertSection
0x180032808  mov     ebx, eax
0x18003280a  test    eax, eax
0x18003280c  jnz     loc_1800351FE
0x180032812  lea     ebp, [rax+1]
0x180032815  mov     ecx, esi
0x180032817  mov     r8d, ebp
0x18003281a  lea     rdx, aEncoding; "Encoding"
0x180032821  call    InsertLong
0x180032826  mov     ebx, eax
0x180032828  test    eax, eax
0x18003282a  jnz     loc_1800351CC
0x180032830  lea     r8d, [r14+6]
0x180032834  mov     ecx, esi
0x180032836  lea     rdx, aPbversion; "PBVersion"
0x18003283d  call    InsertLong
0x180032842  mov     ebx, eax
0x180032844  test    eax, eax
0x180032846  jnz     loc_180035197
0x18003284c  mov     r8d, [rdi+18h]
0x180032850  lea     rdx, aType; "Type"
0x180032857  mov     ecx, esi
0x180032859  call    InsertLong
0x18003285e  mov     ebx, eax
0x180032860  test    eax, eax
0x180032862  jnz     loc_180035162
0x180032868  mov     r8d, [rdi+0B0h]
0x18003286f  lea     rdx, aAutologon; "AutoLogon"
0x180032876  mov     ecx, esi
0x180032878  call    InsertFlag
0x18003287d  mov     ebx, eax
0x18003287f  test    eax, eax
0x180032881  jnz     loc_18003512D
0x180032887  mov     r8d, [rdi+0B4h]
0x18003288e  lea     rdx, aUserascredenti_0; "UseRasCredentials"
0x180032895  mov     ecx, esi
0x180032897  call    InsertFlag
0x18003289c  mov     ebx, eax
0x18003289e  test    eax, eax
0x1800328a0  jnz     loc_1800350F8
0x1800328a6  mov     r8d, [rdi+10h]
0x1800328aa  lea     rdx, aLowdatetime; "LowDateTime"
0x1800328b1  mov     ecx, esi
0x1800328b3  call    InsertLong
0x1800328b8  mov     ebx, eax
0x1800328ba  test    eax, eax
0x1800328bc  jnz     loc_1800350C3
0x1800328c2  mov     r8d, [rdi+14h]
0x1800328c6  lea     rdx, aHighdatetime; "HighDateTime"
0x1800328cd  mov     ecx, esi
0x1800328cf  call    InsertLong
0x1800328d4  mov     ebx, eax
0x1800328d6  test    eax, eax
0x1800328d8  jnz     loc_18003508E
0x1800328de  mov     r8d, [rdi+1C8h]
0x1800328e5  lea     rdx, aDialparamsuid; "DialParamsUID"
0x1800328ec  mov     ecx, esi
0x1800328ee  call    InsertLong
0x1800328f3  mov     ebx, eax
0x1800328f5  test    eax, eax
0x1800328f7  jnz     loc_180035059
0x1800328fd  mov     r8, [rdi+1D0h]
0x180032904  test    r8, r8
0x180032907  jz      short loc_180032925
0x180032909  lea     r9d, [r14+0Eh]
0x18003290d  mov     ecx, esi
0x18003290f  lea     rdx, aGuid; "Guid"
0x180032916  call    InsertBinary
0x18003291b  mov     ebx, eax
0x18003291d  test    eax, eax
0x18003291f  jnz     loc_180033D68
0x180032925  mov     r8d, [rdi+0A8h]
0x18003292c  lea     rdx, aVpnstrategy; "VpnStrategy"
0x180032933  mov     ecx, esi
0x180032935  call    InsertLong
0x18003293a  mov     ebx, eax
0x18003293c  test    eax, eax
0x18003293e  jnz     loc_180035024
0x180032944  mov     r8d, [rdi+0ECh]
0x18003294b  lea     rdx, aExcludedprotoc; "ExcludedProtocols"
0x180032952  mov     ecx, esi
0x180032954  call    InsertLong
0x180032959  mov     ebx, eax
0x18003295b  test    eax, eax
0x18003295d  jnz     loc_180034FEF
0x180032963  mov     r8d, [rdi+0F0h]
0x18003296a  lea     rdx, aLcpextensions; "LcpExtensions"
0x180032971  mov     ecx, esi
0x180032973  call    InsertFlag
0x180032978  mov     ebx, eax
0x18003297a  test    eax, eax
0x18003297c  jnz     loc_180034FBA
0x180032982  mov     r8d, [rdi+0ACh]
0x180032989  lea     rdx, aDataencryption; "DataEncryption"
0x180032990  mov     ecx, esi
0x180032992  call    InsertLong
0x180032997  mov     ebx, eax
0x180032999  test    eax, eax
0x18003299b  jnz     loc_180034F85
0x1800329a1  mov     r8d, [rdi+0F4h]
0x1800329a8  lea     rdx, aSwcompression; "SwCompression"
0x1800329af  mov     ecx, esi
0x1800329b1  call    InsertFlag
0x1800329b6  mov     ebx, eax
0x1800329b8  test    eax, eax
0x1800329ba  jnz     loc_180034F79
0x1800329c0  mov     r8d, [rdi+0F8h]
0x1800329c7  lea     rdx, aNegotiatemulti; "NegotiateMultilinkAlways"
0x1800329ce  mov     ecx, esi
0x1800329d0  call    InsertFlag
0x1800329d5  mov     ebx, eax
0x1800329d7  test    eax, eax
0x1800329d9  jnz     loc_180034F79
0x1800329df  mov     r8d, [rdi+0FCh]
0x1800329e6  lea     rdx, aSkipdoubledial; "SkipDoubleDialDialog"
0x1800329ed  mov     ecx, esi
0x1800329ef  call    InsertFlag
0x1800329f4  mov     ebx, eax
0x1800329f6  test    eax, eax
0x1800329f8  jnz     loc_180034F79
0x1800329fe  mov     r8d, [rdi+84h]
0x180032a05  lea     rdx, aDialmode; "DialMode"
0x180032a0c  mov     ecx, esi
  ... truncated ...
```
