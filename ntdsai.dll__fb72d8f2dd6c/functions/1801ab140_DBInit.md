# DBInit

- ea: `0x1801ab140`
- end: `0x1801ac5cd`
- name: `DBInit`
- size: `5261`
- prototype: ``
- caller_count: `1`
- callee_count: `41`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a504c`

## callees

- `0x180006360`
- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ff94`
- `0x180010510`
- `0x180017d1c`
- `0x18001e090`
- `0x18001ea60`
- `0x180030af8`
- `0x180030b60`
- `0x18003ce4c`
- `0x1800b68c0`
- `0x1801703f0`
- `0x180177f88`
- `0x18017a694`
- `0x180180c50`
- `0x180181460`
- `0x180181ae0`
- `0x180181bf0`
- `0x180181db0`
- `0x1801ab140`
- `0x1801b20a8`
- `0x1801b2b68`
- `0x1801b2c18`
- `0x1801b36e8`
- `0x1801b38e8`
- `0x1801b5ebc`
- `0x1801b6838`
- `0x1801b6b54`
- `0x1801b6e4c`
- `0x1801b854c`
- `0x1801b8750`
- `0x1801b98f4`
- `0x1801b9fbc`
- `0x1801bb8cc`
- `0x1801d9114`
- `0x18021d944`
- `0x18021da44`
- `0x18022b808`
- `0x18022c608`
- `0x18047b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x1801ac55b`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x1801ac55b`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1801ab268`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1801ab268`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1801ac541`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1801ac541`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ac3d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ac3d6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1801ac457`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1801ac457`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801ac464`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801ac464`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1801ab2de`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1801ab2de`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryA` at `0x1801ab3ca`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryA` at `0x1801ab3ca`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1801ab2ad`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1801ab2ad`
- `KERNEL32!CompareStringA` at `0x1801ac2a5`
- `KERNEL32!CompareStringA` at `0x1801ac2a5`
- `KERNEL32!GetVolumePathNameA` at `0x1801ac261`
- `KERNEL32!GetVolumePathNameA` at `0x1801ac261`

## string_xrefs

- `0x1801abca4`: `link_table`
- `0x1801ab224`: `Cache database records`

## pseudocode

```c
__int64 DBInit()
{
  __int64 result; // rax
  bool v1; // zf
  int v2; // eax
  int v3; // ebx
  __int64 v4; // rax
  void *v5; // rdi
  char *v6; // r14
  int v7; // r12d
  unsigned __int64 v8; // rsi
  __int64 v9; // rdx
  const char *v10; // rcx
  unsigned __int64 v11; // rax
  const char *v12; // rsi
  DWORD CurrentDirectoryA; // eax
  CHAR *v14; // rdi
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // r8
  __int64 v20; // r9
  BOOL v21; // r14d
  int v22; // eax
  DWORD HiddenAttIDs; // edi
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // r8
  __int64 v29; // r9
  BOOL v30; // esi
  int v31; // r12d
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 v38; // r8
  __int64 v39; // r9
  BOOL v40; // edi
  int v41; // eax
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // r8
  __int64 v45; // r9
  __int64 v46; // r8
  __int64 v47; // r9
  BOOL v48; // edi
  BOOL v49; // ecx
  int v50; // eax
  unsigned __int16 v51; // ax
  int v52; // r9d
  DWORD v53; // r12d
  __int64 v54; // rcx
  __int64 v55; // r8
  int v56; // r9d
  int v57; // eax
  int v58; // eax
  int v59; // r9d
  int v60; // eax
  int v61; // r9d
  int v62; // r9d
  unsigned int inited; // r12d
  __int64 v64; // rdx
  __int64 v65; // rcx
  __int64 v66; // r8
  __int64 v67; // r9
  __int64 v68; // r8
  __int64 v69; // r9
  BOOL v70; // edi
  int v71; // eax
  __int64 v72; // rdx
  __int64 v73; // rcx
  __int64 v74; // r8
  __int64 v75; // r9
  __int64 v76; // r8
  __int64 v77; // r9
  BOOL v78; // edi
  int v79; // eax
  unsigned __int64 i; // r15
  __int64 v81; // r8
  LPOVERLAPPED v82; // rdi
  int v83; // edi
  unsigned int v84; // eax
  int SubAuthority2; // [rsp+20h] [rbp-818h]
  int SubAuthority2a; // [rsp+20h] [rbp-818h]
  int SubAuthority2b; // [rsp+20h] [rbp-818h]
  int SubAuthority2c; // [rsp+20h] [rbp-818h]
  int SubAuthority2d; // [rsp+20h] [rbp-818h]
  int v90; // [rsp+60h] [rbp-7D8h] BYREF
  int v91[2]; // [rsp+68h] [rbp-7D0h] BYREF
  unsigned int v92; // [rsp+70h] [rbp-7C8h]
  unsigned int v93; // [rsp+74h] [rbp-7C4h]
  int v94; // [rsp+78h] [rbp-7C0h]
  __int64 v95; // [rsp+80h] [rbp-7B8h] BYREF
  __int64 v96; // [rsp+88h] [rbp-7B0h] BYREF
  int v97; // [rsp+90h] [rbp-7A8h] BYREF
  __int64 v98; // [rsp+98h] [rbp-7A0h] BYREF
  __int64 v99; // [rsp+A0h] [rbp-798h] BYREF
  __int64 v100; // [rsp+A8h] [rbp-790h] BYREF
  __int64 v101; // [rsp+B0h] [rbp-788h] BYREF
  _BYTE *v102; // [rsp+B8h] [rbp-780h]
  int v103; // [rsp+C0h] [rbp-778h]
  int v104; // [rsp+C4h] [rbp-774h]
  __int64 v105; // [rsp+D0h] [rbp-768h] BYREF
  int v106; // [rsp+D8h] [rbp-760h]
  int Internal; // [rsp+DCh] [rbp-75Ch]
  __int64 v108; // [rsp+E0h] [rbp-758h]
  int v109; // [rsp+E8h] [rbp-750h]
  int v110; // [rsp+ECh] [rbp-74Ch]
  __int64 v111; // [rsp+F0h] [rbp-748h]
  __int64 v112; // [rsp+F8h] [rbp-740h]
  __int64 v113; // [rsp+100h] [rbp-738h]
  __int64 v114; // [rsp+108h] [rbp-730h]
  __int64 v115; // [rsp+110h] [rbp-728h]
  int v116; // [rsp+118h] [rbp-720h]
  __int64 v117; // [rsp+11Ch] [rbp-71Ch]
  int v118; // [rsp+124h] [rbp-714h]
  char *v119; // [rsp+128h] [rbp-710h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+130h] [rbp-708h] BYREF
  _OWORD v121[2]; // [rsp+138h] [rbp-700h] BYREF
  char v122; // [rsp+160h] [rbp-6D8h] BYREF
  _BYTE v123[24]; // [rsp+380h] [rbp-4B8h] BYREF
  CHAR v124[24]; // [rsp+398h] [rbp-4A0h] BYREF
  CHAR szFileName; // [rsp+3B0h] [rbp-488h] BYREF
  _BYTE v126[271]; // [rsp+3B1h] [rbp-487h] BYREF
  CHAR szVolumePathName; // [rsp+4C0h] [rbp-378h] BYREF
  _BYTE v128[271]; // [rsp+4C1h] [rbp-377h] BYREF
  CHAR String1; // [rsp+5D0h] [rbp-268h] BYREF
  _BYTE v130[271]; // [rsp+5D1h] [rbp-267h] BYREF
  CHAR Buffer[272]; // [rsp+6E0h] [rbp-158h] BYREF

  v90 = -1;
  v99 = -1;
  v95 = -1;
  v96 = -1;
  v98 = -1;
  v100 = -1;
  memset(v121, 0, 28);
  *(_QWORD *)v91 = -1;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v97 = 0;
  memset_0(Buffer, 0, 0x105u);
  if ( !gFirstTimeThrough )
    return 0;
  gFirstTimeThrough = 0;
  dbAttributeLockingThreadsInitialize();
  memset_0(rgbMaxUpperKey, 255, 0xFFu);
  v92 = 0;
  v1 = (unsigned int)GetConfigParamLocalEx((__int64)"Cache database records", &gfEnableReadOnlyCopy) == 0;
  v2 = 0;
  if ( v1 )
    LOBYTE(v2) = *(_DWORD *)&gfEnableReadOnlyCopy != 0;
  *(_DWORD *)&gfEnableReadOnlyCopy = v2;
  DSDBLayerInitializeDynamicSettings();
  DSDBLayerLoadDynamicSettings();
  qsort(&IndicesToKeep, 0x25u, 0x14u, Compare_ATTRSIMPLE);
  v3 = 1;
  if ( RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x20u, 0, 0, 0, 0, 0, 0, 0, &pgdbBuiltinDomain) )
    RaiseDsaExcept(0xE0010003, 1);
  qword_18052B218 = CreateSemaphoreW(0, gcMaxJetSessions, gcMaxJetSessions, 0);
  if ( !qword_18052B218 )
    RaiseDsaExcept(0xE0010003, 1);
  qword_1805284D0 = (void *)DSAllocAux((unsigned __int64)(unsigned int)gcMaxJetSessions << 6, 33696220);
  v4 = DSAllocAux(8LL * (unsigned int)gcMaxJetSessions, 33696221);
  v5 = (void *)v4;
  UncUsn = v4;
  v6 = (char *)qword_1805284D0;
  if ( qword_1805284D0 && v4 )
  {
    v7 = 1;
    v8 = (unsigned int)gcMaxJetSessions;
    memset_0(qword_1805284D0, 0, (unsigned __int64)(unsigned int)gcMaxJetSessions << 6);
    v10 = 0;
    if ( (_DWORD)v8 )
    {
      do
      {
        v11 = (unsigned __int64)(unsigned int)v10 << 6;
        *(_QWORD *)&v6[v11] = -1;
        *(_DWORD *)&v6[v11 + 8] = -1;
        LODWORD(v10) = (_DWORD)v10 + 1;
      }
      while ( (unsigned int)v10 < (unsigned int)v8 );
      memset64(v5, 0x7FFFFFFFFFFFFFFFuLL, v8);
      v10 = 0;
    }
    if ( gfRunningAsMkdit )
    {
      v12 = "ntds.dit";
      CurrentDirectoryA = GetCurrentDirectoryA(0x105u, Buffer);
      v10 = ".";
      v14 = Buffer;
      if ( !CurrentDirectoryA )
        v14 = (CHAR *)".";
    }
    else if ( gfRunningAsExe )
    {
      v12 = gszDbPath;
      v14 = (CHAR *)gszLogPath;
      if ( gfDitIsReadOnly )
        v7 = 3;
    }
    else
    {
      v12 = 0;
      v14 = 0;
    }
    if ( (unsigned int)THStateCheckForTraceOverride(v10, v9)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 6)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v16, v15, v17, v18)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 6)) )
    {
      v21 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v16, v15, v19, v20)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 6));
      if ( (unsigned int)THStateCheckForTraceOverride(v16, v15)
        || (v1 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 6) == 0, v22 = 0, !v1) )
      {
        v22 = 1;
      }
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v22,
        v21,
        49,
        &WPP_ba68a6237e4938374ef2840e94810607_Traceguids,
        (__int64)v12,
        (__int64)v14);
    }
    HiddenAttIDs = DBInitializeJetDatabase((int)&jetInstance, (int)v91, (int)&v90, (int)v12, (__int64)v14, v14, v7);
    if ( HiddenAttIDs )
    {
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
        || (unsigned int)THStateCheckForTraceOverride(v25, v24)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 6)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v25, v24)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v25, v24, v26, v27)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 6)) )
      {
        v30 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v25, v24)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier(v25, v24, v28, v29)
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 6));
        if ( !(unsigned int)THStateCheckForTraceOverride(v25, v24)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 6) )
        {
          v3 = 0;
        }
        WPP_SF__ATTRTYP_LOG_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          33696280,
          2,
          6,
          v3,
          v30,
          50,
          (__int64)&WPP_ba68a6237e4938374ef2840e94810607_Traceguids);
      }
      return HiddenAttIDs;
    }
    v93 = 0;
    v31 = 0;
    v92 = 0;
    if ( (unsigned int)((__int64 (__fastcall *)(_QWORD, int *))pFnJetGetVersion)(*(_QWORD *)v91, &g_dwEseVersion) )
    {
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
        || (unsigned int)THStateCheckForTraceOverride(v35, v34)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 6)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v35, v34)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v35, v34, v36, v37)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 6)) )
      {
        v40 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v35, v34)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier(v35, v34, v38, v39)
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 6));
        if ( (unsigned int)THStateCheckForTraceOverride(v35, v34)
          || (v41 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 6)) != 0 )
        {
          v41 = 1;
        }
        WPP_SF__ATTRTYP_LOG_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          33696288,
          2,
          6,
          v41,
          v40,
          51,
          (__int64)&WPP_ba68a6237e4938374ef2840e94810607_Traceguids);
      }
      g_dwEseVersion = -1;
    }
    else if ( (unsigned int)THStateCheckForTraceOverride(v33, v32)
           || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 6)
           || gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v43, v42)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier(v43, v42, v44, v45)
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 6)) )
    {
      v48 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v43, v42)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v43, v42, v46, v47)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 6));
      v49 = (unsigned int)THStateCheckForTraceOverride(v43, v42)
         || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 6);
      WPP_SF__ATTRTYP_LOG_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33696292,
        4,
        6,
        v49,
        v48,
        52,
        (__int64)&WPP_ba68a6237e4938374ef2840e94810607_Traceguids);
    }
    result = dbCreateHiddenDBPOS();
    v94 = result;
    if ( !(_DWORD)result )
    {
      if ( (unsigned int)dbHiddenFlagsInitialize() )
      {
        if ( (_BYTE)gdbfDataBaseFlags != 49 )
        {
          if ( gfDitIsReadOnly == ((_BYTE)gdbfDataBaseFlags == 49) )
            v31 = 1;
          v92 = v31;
          v103 = v31;
        }
        if ( BYTE5(gdbfDataBaseFlags) != 49 )
        {
          v50 = v93;
          if ( !gfDitIsReadOnly )
            v50 = 1;
          v93 = v50;
          v104 = v50;
        }
        HiddenAttIDs = dbGetHiddenAttIDs();
        v94 = HiddenAttIDs;
        if ( !HiddenAttIDs )
        {
          dword_18052B3FC = DBGetOptionalFeatureEnabled(asc_1804B5F28);
          if ( dword_18052B3FC )
            qword_18052B450 = *(_QWORD *)((char *)&gdbfDataBaseFlags + 7);
        }
      }
      else
      {
        HiddenAttIDs = 87;
        v94 = 87;
      }
      if ( HiddenAttIDs )
        DoLogUnhandledError2(33696346, &word_18049B11A, HiddenAttIDs, 1);
      v51 = dbCloseHiddenDBPOS();
      v53 = v51;
      if ( v51 )
        DoLogUnhandledError2(33696351, &word_18049B11A, v51, 1);
      if ( !HiddenAttIDs )
        HiddenAttIDs = v53;
      if ( HiddenAttIDs )
        return HiddenAttIDs;
      if ( !gfDitIsReadOnly )
      {
        HiddenAttIDs = dbRecreateRequiredIndices(*(_QWORD *)v91, (unsigned int)v90, v92, v93);
        if ( HiddenAttIDs )
        {
          v54 = 33696367;
          goto LABEL_118;
        }
      }
      HiddenAttIDs = JetOpenTableException(
                       v91[0],
                       v90,
                       (unsigned int)"datatable",
                       v52,
                       SubAuthority2,
                       0,
                       (__int64)&v95,
                       2,
                       33696382);
      if ( HiddenAttIDs )
      {
        v54 = 33696384;
        goto LABEL_118;
      }
      if ( !gfDitIsReadOnly )
        goto LABEL_262;
      HiddenAttIDs = dbCreateNewColumns(v91[0], v90, v95, 2, (__int64)&off_18050F020);
      if ( HiddenAttIDs )
      {
        v54 = 33696400;
        goto LABEL_118;
      }
      if ( !gfDitIsReadOnly )
      {
LABEL_262:
        HiddenAttIDs = dbCheckLocalizedIndices(*(_QWORD *)v91, v95);
        if ( HiddenAttIDs )
        {
          v54 = 33696410;
          goto LABEL_118;
        }
      }
      HiddenAttIDs = dbGetExistingColumnIDs(*(_QWORD *)v91, v95, 26, &off_18050DF10);
      if ( HiddenAttIDs )
      {
        v54 = 33696421;
        goto LABEL_118;
      }
      HiddenAttIDs = dbGetExistingIndexIDs(*(_QWORD *)v91, v95, 10, &off_18050DD90);
      if ( HiddenAttIDs )
      {
        v54 = 33696431;
        goto LABEL_118;
      }
      LODWORD(dbAddSDPropTimeReadTemplate) = dscorepropinfoid;
      LODWORD(xmmword_18051A540) = dscorepropinfoid;
      LODWORD(xmmword_18051A570) = dscorepropinfoid;
      LODWORD(dbAddSDPropTimeWriteTemplate) = dscorepropinfoid;
      dword_18051A5C8 = dscorepropinfoid;
      LODWORD(xmmword_18051A5F0) = dscorepropinfoid;
      if ( *(_DWORD *)gfADAM )
      {
        abcntid = -1;
      }
      else
      {
        SubAuthority2a = 28;
        HiddenAttIDs = ((__int64 (__fastcall *)(_QWORD, __int64, const char *, _OWORD *))pFnJetGetTableColumnInfoA)(
                         *(_QWORD *)v91,
                         v95,
                         "ab_cnt_col",
                         v121);
        if ( !HiddenAttIDs )
        {
          abcntid = DWORD1(v121[0]);
          v57 = WORD4(v121[1]) & 0x800;
LABEL_138:
          gfDoingABRef = v57;
          v58 = JetOpenTableException(
                  v91[0],
                  v90,
                  (unsigned int)"metadatatable",
                  v56,
                  SubAuthority2a,
                  2,
                  (__int64)&v99,
                  2,
                  33696482);
          if ( v58 != -1305 )
          {
            if ( v58 )
            {
              v54 = 33696516;
              goto LABEL_118;
            }
            HiddenAttIDs = dbGetExistingColumnIDs(*(_QWORD *)v91, v99, 9, &off_18050DCB0);
            if ( HiddenAttIDs )
            {
              v54 = 33696499;
              goto LABEL_118;
            }
            HiddenAttIDs = dbGetExistingIndexIDs(*(_QWORD *)v91, v99, 1, &off_18050E180);
            if ( HiddenAttIDs )
            {
              v54 = 33696509;
              goto LABEL_118;
            }
          }
          v60 = JetOpenTableException(
                  v91[0],
                  v90,
                  (unsigned int)"dirsyncsettable",
                  v59,
                  SubAuthority2b,
                  2,
                  (__int64)&v100,
                  2,
                  33696530);
          if ( v60 != -1305 )
          {
            if ( v60 )
            {
              v54 = 33696564;
              goto LABEL_118;
            }
            HiddenAttIDs = dbGetExistingColumnIDs(*(_QWORD *)v91, v100, 2, &off_18050F200);
            if ( HiddenAttIDs )
            {
              v54 = 33696547;
              goto LABEL_118;
            }
            HiddenAttIDs = dbGetExistingIndexIDs(*(_QWORD *)v91, v100, 1, &off_18050E6D0);
            if ( HiddenAttIDs )
            {
              v54 = 33696557;
              goto LABEL_118;
            }
          }
          HiddenAttIDs = JetOpenTableException(
                           v91[0],
                           v90,
                           (unsigned int)"link_table",
                           v61,
                           SubAuthority2c,
                           2,
                           (__int64)&v96,
                           2,
                           33696578);
          if ( HiddenAttIDs )
          {
            v54 = 33696581;
            goto LABEL_118;
          }
          HiddenAttIDs = dbGetExistingColumnIDs(*(_QWORD *)v91, v96, 13, &off_18050F2E0);
          if ( HiddenAttIDs )
          {
            v54 = 33696591;
            goto LABEL_118;
          }
          HiddenAttIDs = dbCreateNewColumns(v91[0], v90, v96, 5, (__int64)&off_18050EEA0);
          if ( HiddenAttIDs )
          {
            v54 = 33696602;
            goto LABEL_118;
          }
          if ( !gfRunningAsMkdit )
          {
            HiddenAttIDs = dbCreateNewColumns(v91[0], v90, v96, 1, (__int64)&off_18050ED70);
            if ( HiddenAttIDs )
            {
              v54 = 33696622;
              goto LABEL_118;
            }
          }
          HiddenAttIDs = dbGetExistingIndexIDs(*(_QWORD *)v91, v96, 3, &off_18050F080);
          if ( HiddenAttIDs )
          {
            v54 = 33696634;
            goto LABEL_118;
          }
          HiddenAttIDs = dbCreateOrCheckNewIndicesBatch(v91[0], v96, 0, 8, (__int64)off_18050E1A0, 0, 0);
          if ( HiddenAttIDs )
          {
            v54 = 33696647;
            goto LABEL_118;
          }
          HiddenAttIDs = JetOpenTableException(
                           v91[0],
                           v90,
                           (unsigned int)"sdproptable",
                           v62,
                           SubAuthority2d,
                           0,
                           (__int64)&v98,
                           2,
                           33696661);
          if ( HiddenAttIDs )
          {
            v54 = 33696663;
            goto LABEL_118;
          }
          HiddenAttIDs = dbGetExistingColumnIDs(*(_QWORD *)v91, v98, 4, &off_18050EF90);
          if ( HiddenAttIDs )
          {
            v54 = 33696673;
            goto LABEL_118;
          }
          HiddenAttIDs = dbCreateNewColumns(v91[0], v90, v98, 3, (__int64)&off_18050DBE0);
          if ( HiddenAttIDs )
          {
            v54 = 33696684;
            goto LABEL_118;
          }
          HiddenAttIDs = dbCreateOrCheckNewIndicesBatch(v91[0], v98, 0, 1, (__int64)off_18050DC70, 0, 0);
          if ( HiddenAttIDs )
          {
            v54 = 33696697;
            goto LABEL_118;
          }
          HiddenAttIDs = dbInitSDTable(*(_QWORD *)v91, (unsigned int)v90, &v97);
          if ( HiddenAttIDs )
          {
            v54 = 33696706;
            goto LABEL_118;
          }
          HiddenAttIDs = dbInitLinkHistoryTable(*(_QWORD *)v91, (unsigned int)v90);
          if ( HiddenAttIDs )
          {
            v54 = 33696715;
            goto LABEL_118;
          }
          HiddenAttIDs = dbCreateHiddenDBPOS();
          if ( HiddenAttIDs )
          {
            v54 = 33696722;
            goto LABEL_118;
          }
          if ( dsaInitPhase == 1 || DataSource == 1 )
          {
            inited = dbInitQuotaTables(*(_QWORD *)v91, (unsigned int)v90);
            if ( inited )
            {
              if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
                || (unsigned int)THStateCheckForTraceOverride(v65, v64)
                || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 6)
                || gfTraceToSecondProvider
                && ((unsigned int)THStateCheckForTraceOverride(v65, v64)
                 || (unsigned int)ThStateCheckIfTraceToSecondProvier(v65, v64, v66, v67)
                 && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 6)) )
              {
                v70 = gfTraceToSecondProvider
                   && ((unsigned int)THStateCheckForTraceOverride(v65, v64)
                    || (unsigned int)ThStateCheckIfTraceToSecondProvier(v65, v64, v68, v69)
                    && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 6));
                if ( (unsigned int)THStateCheckForTraceOverride(v65, v64)
                  || (v71 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 6)) != 0 )
                {
                  v71 = 1;
                }
                WPP_SF__ATTRTYP_LOG_(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  33696736,
                  2,
                  6,
                  v71,
                  v70,
                  53,
                  (__int64)&WPP_ba68a6237e4938374ef2840e94810607_Traceguids);
              }
              if ( !gfDitIsReadOnly )
                return inited;
              if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
                || (unsigned int)THStateCheckForTraceOverride(v73, v72)
                || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 6)
                || gfTraceToSecondProvider
                && ((unsigned int)THStateCheckForTraceOverride(v73, v72)
                 || (unsigned int)ThStateCheckIfTraceToSecondProvier(v73, v72, v74, v75)
                 && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 6)) )
              {
                v78 = gfTraceToSecondProvider
                   && ((unsigned int)THStateCheckForTraceOverride(v73, v72)
                    || (unsigned int)ThStateCheckIfTraceToSecondProvier(v73, v72, v76, v77)
                    && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 6));
                if ( (unsigned int)THStateCheckForTraceOverride(v73, v72)
                  || (v79 = CheckWPPLevelFlagsEnabledForProvider(0, 3, 6)) != 0 )
                {
                  v79 = 1;
                }
                WPP_SF__ATTRTYP_LOG_(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  33696742,
                  3,
                  6,
                  v79,
                  v78,
                  54,
                  (__int64)&WPP_ba68a6237e4938374ef2840e94810607_Traceguids);
              }
            }
          }
          if ( !gfIsServerSKU )
          {
            v101 = 0x100000000LL;
            v102 = (_BYTE *)0xFFFFFFFF00000002LL;
            szFileName = 0;
            memset_0(v126, 0, 0x103u);
            szVolumePathName = 0;
            memset_0(v128, 0, 0x103u);
            String1 = 0;
            memset_0(v130, 0, 0x103u);
            for ( i = 0; ; ++i )
            {
              if ( i >= 4 )
                goto LABEL_239;
              v81 = *((unsigned int *)&v101 + i);
              if ( (_DWORD)v81 == -1 )
              {
                HiddenAttIDs = ((__int64 (__fastcall *)(_QWORD, _QWORD, CHAR *, __int64, _DWORD))pFnJetGetDatabaseInfoA)(
                                 *(_QWORD *)v91,
                                 (unsigned int)v90,
                                 &szFileName,
                                 260,
                                 0);
                if ( HiddenAttIDs )
                {
                  v54 = 33696783;
                  goto LABEL_118;
                }
              }
              else
              {
                HiddenAttIDs = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, CHAR *, int))pFnJetGetSystemParameterA)(
                                 *(_QWORD *)&jetInstance,
                                 *(_QWORD *)v91,
                                 v81,
                                 0,
                                 &szFileName,
                                 260);
                if ( HiddenAttIDs )
                {
                  v54 = 33696771;
                  goto LABEL_118;
                }
              }
              if ( !GetVolumePathNameA(&szFileName, &szVolumePathName, 0x104u) )
              {
                HiddenAttIDs = GetLastError();
                v55 = HiddenAttIDs;
                v54 = 33696789;
                goto LABEL_119;
              }
              if ( String1 && CompareStringA(0x7Fu, 1u, &String1, -1, &szVolumePathName, -1) != 2 )
                break;
LABEL_236:
              StringCchCopyA(&String1, 0x104u, &szVolumePathName);
            }
            v82 = gpDsEventConfig;
            if ( gpDsEventConfig )
            {
              if ( (gpDsEventConfig[6].Internal & 0x8000000000000000uLL) == 0LL
                || HIDWORD(gpDsEventConfig->Internal) && (unsigned int)DoLogOverride(514, 0) )
              {
                goto LABEL_234;
              }
              if ( (unsigned int)DoLogMsgOverride(3221227998LL) )
              {
                v82 = gpDsEventConfig;
LABEL_234:
                v108 = 0;
                v114 = 0;
                v117 = 0;
                v118 = 0;
                v105 = 0;
                Internal = v82[6].Internal;
                v106 = -1073739298;
                v109 = 0;
                v110 = 1;
                v119 = &v122;
                v113 = 0;
                v112 = 514;
                v111 = 1;
                v115 = 0;
                v116 = 0;
                DoLogEventAndTrace(&v105);
              }
            }
            RaiseDsaExcept(0xE0010004, 1);
            goto LABEL_236;
          }
LABEL_239:
          v83 = 0;
          v84 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))pFnJetCloseDatabase)(
                  *(_QWORD *)v91,
                  (unsigned int)v90,
                  0);
          if ( v84 )
            DoLogUnhandledError2(33696813, &word_18049B11A, v84, 1);
          _InterlockedDecrement(&gcOpenDatabases);
          ((void (__fastcall *)(_QWORD, __int64))pFnJetEndSession)(*(_QWORD *)v91, 1);
          dbEndSess(*(_QWORD *)v91);
          if ( hevIndexRebuildUI )
          {
            SetEvent(hevIndexRebuildUI);
            CloseHandle(hevIndexRebuildUI);
            hevIndexRebuildUI = 0;
          }
          if ( v97 )
          {
            BYTE1(gdbfDataBaseFlags) = 49;
            v83 = 1;
          }
          if ( v92 )
          {
            BYTE4(gdbfDataBaseFlags) = 49;
            v83 = 1;
          }
          if ( v93 )
          {
            BYTE5(gdbfDataBaseFlags) = 49;
            v83 = 1;
          }
          if ( *(_DWORD *)gfADAM )
            goto LABEL_252;
          if ( BYTE3(gdbfDataBaseFlags) == 49 )
          {
LABEL_253:
            HiddenAttIDs = 8409;
            v54 = 33696866;
LABEL_118:
            v55 = HiddenAttIDs;
LABEL_119:
            DoLogUnhandledError2(v54, &word_18049B11A, v55, 1);
            return HiddenAttIDs;
          }
          if ( *(_DWORD *)gfADAM )
          {
LABEL_252:
            if ( BYTE3(gdbfDataBaseFlags) != 49 )
              goto LABEL_253;
          }
          if ( !v83 )
            return 0;
          HiddenAttIDs = dbSetHiddenFlags();
          if ( !HiddenAttIDs )
            return 0;
          v54 = 33696873;
          goto LABEL_118;
        }
        abcntid = 0;
      }
      v57 = 0;
      goto LABEL_138;
    }
  }
  else
  {
    if ( gpDsEventConfig )
    {
      v101 = (__int64)v124;
      v102 = v123;
      _o__itow_s((unsigned int)(72 * gcMaxJetSessions), v124, 12);
      _o__ultow_s(33696223, v123, 9, 16);
      DoLogEventW(514, gpDsEventConfig[4].Offset, 0, -1073740655, 1, 2u, (__int64)&v101, 0, 0);
    }
    return 12;
  }
  return result;
}

```

## disassembly

```asm
0x1801ab140  mov     r11, rsp
0x1801ab143  push    rbx
0x1801ab144  push    rsi
0x1801ab145  push    rdi
0x1801ab146  push    r12
0x1801ab148  push    r13
0x1801ab14a  push    r14
0x1801ab14c  push    r15
0x1801ab14e  sub     rsp, 800h
0x1801ab155  mov     rax, cs:__security_cookie
0x1801ab15c  xor     rax, rsp
0x1801ab15f  mov     [rsp+838h+var_48], rax
0x1801ab167  mov     [rsp+838h+var_7D8], 0FFFFFFFFh
0x1801ab16f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1801ab173  mov     [r11-798h], rcx
0x1801ab17a  mov     [r11-7B8h], rcx
0x1801ab181  mov     [r11-7B0h], rcx
0x1801ab188  mov     [r11-7A0h], rcx
0x1801ab18f  mov     [r11-790h], rcx
0x1801ab196  xorps   xmm0, xmm0
0x1801ab199  movups  [rsp+838h+var_700], xmm0
0x1801ab1a1  movups  [rsp+838h+var_700+0Ch], xmm0
0x1801ab1a9  mov     qword ptr [rsp+838h+var_7D0], rcx
0x1801ab1ae  xor     r13d, r13d
0x1801ab1b1  mov     [r11-708h], r13d
0x1801ab1b8  mov     word ptr [rsp+838h+IdentifierAuthority.Value+4], 500h
0x1801ab1c2  mov     [r11-7A8h], r13d
0x1801ab1c9  xor     edx, edx; Val
0x1801ab1cb  mov     r8d, 105h; Size
0x1801ab1d1  lea     rcx, [r11-158h]; void *
0x1801ab1d8  call    memset_0
0x1801ab1dd  cmp     cs:gFirstTimeThrough, r13d
0x1801ab1e4  jnz     short loc_1801AB1ED
0x1801ab1e6  xor     eax, eax
0x1801ab1e8  jmp     loc_1801AC5AA
0x1801ab1ed  mov     cs:gFirstTimeThrough, r13d
0x1801ab1f4  call    dbAttributeLockingThreadsInitialize
0x1801ab1f9  mov     edx, 0FFh; Val
0x1801ab1fe  mov     r8d, edx; Size
0x1801ab201  lea     rcx, rgbMaxUpperKey; void *
0x1801ab208  call    memset_0
0x1801ab20d  mov     [rsp+838h+var_7C8], r13d
0x1801ab212  lea     r9, [rsp+838h+var_7C8]
0x1801ab217  mov     r8d, 4
0x1801ab21d  lea     rdx, gfEnableReadOnlyCopy; lpData
0x1801ab224  lea     rcx, aCacheDatabaseR; "Cache database records"
0x1801ab22b  call    GetConfigParamLocalEx
0x1801ab230  test    eax, eax
0x1801ab232  mov     eax, r13d
0x1801ab235  jnz     short loc_1801AB241
0x1801ab237  cmp     cs:gfEnableReadOnlyCopy, r13d
0x1801ab23e  setnz   al
0x1801ab241  mov     cs:gfEnableReadOnlyCopy, eax
0x1801ab247  call    DSDBLayerInitializeDynamicSettings
0x1801ab24c  call    DSDBLayerLoadDynamicSettings
0x1801ab251  lea     r9, Compare_ATTRSIMPLE; CompareFunction
0x1801ab258  mov     edx, 25h ; '%'; NumOfElements
0x1801ab25d  lea     r8d, [rdx-11h]; SizeOfElements
0x1801ab261  lea     rcx, IndicesToKeep; Base
0x1801ab268  call    cs:__imp_qsort
0x1801ab26e  lea     rax, pgdbBuiltinDomain
0x1801ab275  mov     [rsp+838h+Sid], rax; Sid
0x1801ab27a  mov     [rsp+838h+SubAuthority7], r13d; SubAuthority7
0x1801ab27f  mov     [rsp+838h+SubAuthority6], r13d; SubAuthority6
0x1801ab284  mov     [rsp+838h+SubAuthority5], r13d; SubAuthority5
0x1801ab289  mov     [rsp+838h+SubAuthority4], r13d; SubAuthority4
0x1801ab28e  mov     [rsp+838h+SubAuthority3], r13d; SubAuthority3
0x1801ab293  mov     [rsp+838h+SubAuthority2], r13d; SubAuthority2
0x1801ab298  xor     r9d, r9d; SubAuthority1
0x1801ab29b  lea     ebx, [r9+1]
0x1801ab29f  lea     r8d, [r9+20h]; SubAuthority0
0x1801ab2a3  mov     dl, bl; SubAuthorityCount
0x1801ab2a5  lea     rcx, [rsp+838h+IdentifierAuthority]; IdentifierAuthority
0x1801ab2ad  call    cs:__imp_RtlAllocateAndInitializeSid
0x1801ab2b3  test    eax, eax
0x1801ab2b5  jz      short loc_1801AB2D0
0x1801ab2b7  mov     [rsp+838h+SubAuthority2], ebx; int
0x1801ab2bb  mov     r9d, 20229CEh
0x1801ab2c1  xor     r8d, r8d
0x1801ab2c4  mov     edx, eax
0x1801ab2c6  mov     ecx, 0E0010003h; dwExceptionCode
0x1801ab2cb  call    RaiseDsaExcept
0x1801ab2d0  xor     r9d, r9d; lpName
0x1801ab2d3  mov     edx, cs:gcMaxJetSessions; lInitialCount
0x1801ab2d9  mov     r8d, edx; lMaximumCount
0x1801ab2dc  xor     ecx, ecx; lpSemaphoreAttributes
0x1801ab2de  call    cs:__imp_CreateSemaphoreW
0x1801ab2e4  mov     cs:qword_18052B218, rax
0x1801ab2eb  test    rax, rax
0x1801ab2ee  jnz     short loc_1801AB309
0x1801ab2f0  mov     [rsp+838h+SubAuthority2], ebx; int
0x1801ab2f4  mov     r9d, 20229D8h
0x1801ab2fa  xor     r8d, r8d
0x1801ab2fd  xor     edx, edx
0x1801ab2ff  mov     ecx, 0E0010003h; dwExceptionCode
0x1801ab304  call    RaiseDsaExcept
0x1801ab309  mov     ecx, cs:gcMaxJetSessions
0x1801ab30f  shl     rcx, 6
0x1801ab313  mov     edx, 20229DCh
0x1801ab318  call    DSAllocAux
0x1801ab31d  mov     cs:qword_1805284D0, rax
0x1801ab324  mov     ecx, cs:gcMaxJetSessions
0x1801ab32a  shl     rcx, 3
0x1801ab32e  mov     edx, 20229DDh
0x1801ab333  call    DSAllocAux
0x1801ab338  mov     rdi, rax
0x1801ab33b  mov     cs:UncUsn, rax
0x1801ab342  mov     r14, cs:qword_1805284D0
0x1801ab349  test    r14, r14
0x1801ab34c  jz      loc_1801AC4F4
0x1801ab352  test    rax, rax
0x1801ab355  jz      loc_1801AC4F4
0x1801ab35b  mov     r12d, ebx
0x1801ab35e  mov     esi, cs:gcMaxJetSessions
0x1801ab364  mov     r8d, esi
0x1801ab367  shl     r8, 6; Size
0x1801ab36b  xor     edx, edx; Val
0x1801ab36d  mov     rcx, r14; void *
0x1801ab370  call    memset_0
0x1801ab375  mov     ecx, r13d
0x1801ab378  test    esi, esi
0x1801ab37a  jz      short loc_1801AB3AD
0x1801ab37c  mov     eax, ecx
0x1801ab37e  shl     rax, 6
0x1801ab382  mov     qword ptr [rax+r14], 0FFFFFFFFFFFFFFFFh
0x1801ab38a  mov     dword ptr [rax+r14+8], 0FFFFFFFFh
0x1801ab393  add     ecx, ebx
0x1801ab395  cmp     ecx, esi
0x1801ab397  jb      short loc_1801AB37C
0x1801ab399  test    esi, esi
0x1801ab39b  jz      short loc_1801AB3AD
0x1801ab39d  mov     rax, 7FFFFFFFFFFFFFFFh
0x1801ab3a7  mov     rcx, rsi
0x1801ab3aa  rep stosq
0x1801ab3ad  cmp     cs:gfRunningAsMkdit, r13d
0x1801ab3b4  jz      short loc_1801AB3E7
0x1801ab3b6  lea     rsi, aNtdsDit; "ntds.dit"
0x1801ab3bd  lea     rdx, [rsp+838h+Buffer]; lpBuffer
0x1801ab3c5  mov     ecx, 105h; nBufferLength
0x1801ab3ca  call    cs:__imp_GetCurrentDirectoryA
0x1801ab3d0  lea     rcx, asc_1804B5F64; "."
0x1801ab3d7  lea     rdi, [rsp+838h+Buffer]
0x1801ab3df  test    eax, eax
0x1801ab3e1  cmovz   rdi, rcx
0x1801ab3e5  jmp     short loc_1801AB415
0x1801ab3e7  cmp     cs:gfRunningAsExe, r13d
0x1801ab3ee  jz      short loc_1801AB40F
0x1801ab3f0  mov     rsi, cs:gszDbPath
0x1801ab3f7  mov     rdi, cs:gszLogPath
0x1801ab3fe  cmp     cs:gfDitIsReadOnly, r13d
0x1801ab405  jz      short loc_1801AB415
0x1801ab407  mov     r12d, 3
0x1801ab40d  jmp     short loc_1801AB415
0x1801ab40f  mov     rsi, r13
0x1801ab412  mov     rdi, r13
0x1801ab415  call    THStateCheckForTraceOverride
0x1801ab41a  mov     r15d, 6
0x1801ab420  test    eax, eax
0x1801ab422  jnz     short loc_1801AB46E
0x1801ab424  mov     r8d, r15d
0x1801ab427  lea     edx, [rax+4]
0x1801ab42a  xor     ecx, ecx
0x1801ab42c  call    CheckWPPLevelFlagsEnabledForProvider
0x1801ab431  test    eax, eax
0x1801ab433  jnz     short loc_1801AB46E
0x1801ab435  mov     eax, cs:gfTraceToSecondProvider
0x1801ab43b  test    eax, eax
0x1801ab43d  jz      short loc_1801AB463
0x1801ab43f  call    THStateCheckForTraceOverride
0x1801ab444  test    eax, eax
0x1801ab446  jnz     short loc_1801AB46E
0x1801ab448  call    ThStateCheckIfTraceToSecondProvier
0x1801ab44d  test    eax, eax
0x1801ab44f  jz      short loc_1801AB463
0x1801ab451  mov     r8d, r15d
0x1801ab454  lea     edx, [r15-2]
0x1801ab458  mov     ecx, ebx
0x1801ab45a  call    CheckWPPLevelFlagsEnabledForProvider
0x1801ab45f  test    eax, eax
0x1801ab461  jnz     short loc_1801AB46E
0x1801ab463  mov     r13d, 31h ; '1'
0x1801ab469  jmp     loc_1801AB50B
0x1801ab46e  mov     eax, cs:gfTraceToSecondProvider
0x1801ab474  test    eax, eax
0x1801ab476  jz      short loc_1801AB4A2
0x1801ab478  call    THStateCheckForTraceOverride
0x1801ab47d  test    eax, eax
0x1801ab47f  jnz     short loc_1801AB49D
0x1801ab481  call    ThStateCheckIfTraceToSecondProvier
0x1801ab486  test    eax, eax
0x1801ab488  jz      short loc_1801AB4A2
0x1801ab48a  mov     r8d, r15d
0x1801ab48d  mov     edx, 4
0x1801ab492  mov     ecx, ebx
0x1801ab494  call    CheckWPPLevelFlagsEnabledForProvider
0x1801ab499  test    eax, eax
0x1801ab49b  jz      short loc_1801AB4A2
0x1801ab49d  mov     r14d, ebx
0x1801ab4a0  jmp     short loc_1801AB4A5
0x1801ab4a2  mov     r14d, r13d
0x1801ab4a5  call    THStateCheckForTraceOverride
0x1801ab4aa  test    eax, eax
0x1801ab4ac  jnz     short loc_1801AB4C2
0x1801ab4ae  mov     r8d, r15d
0x1801ab4b1  lea     edx, [rax+4]
0x1801ab4b4  xor     ecx, ecx
0x1801ab4b6  call    CheckWPPLevelFlagsEnabledForProvider
0x1801ab4bb  test    eax, eax
0x1801ab4bd  mov     eax, r13d
0x1801ab4c0  jz      short loc_1801AB4C4
0x1801ab4c2  mov     eax, ebx
0x1801ab4c4  mov     r13d, 31h ; '1'
0x1801ab4ca  mov     qword ptr [rsp+838h+SubAuthority7], rdi; __int64
0x1801ab4cf  mov     qword ptr [rsp+838h+SubAuthority6], rsi; __int64
0x1801ab4d4  lea     rcx, WPP_ba68a6237e4938374ef2840e94810607_Traceguids
0x1801ab4db  mov     qword ptr [rsp+838h+SubAuthority5], rcx; LPCGUID
0x1801ab4e0  mov     word ptr [rsp+838h+SubAuthority4], r13w; __int16
0x1801ab4e6  mov     [rsp+838h+SubAuthority3], r14d; int
0x1801ab4eb  mov     [rsp+838h+SubAuthority2], eax; int
0x1801ab4ef  mov     r9d, r15d
0x1801ab4f2  mov     edx, 2022A0Eh
0x1801ab4f7  lea     r8d, [r13-2Dh]
0x1801ab4fb  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ab502  mov     rcx, [rcx+10h]; int
0x1801ab506  call    WPP_SF_ss
0x1801ab50b  lea     r14, WPP_ba68a6237e4938374ef2840e94810607_Traceguids
0x1801ab512  mov     [rsp+838h+SubAuthority4], r12d; int
0x1801ab517  mov     qword ptr [rsp+838h+SubAuthority3], rdi; pszSrc
0x1801ab51c  mov     qword ptr [rsp+838h+SubAuthority2], rdi; __int64
0x1801ab521  mov     r9, rsi; int
0x1801ab524  lea     r8, [rsp+838h+var_7D8]; int
0x1801ab529  lea     rdx, [rsp+838h+var_7D0]; int
0x1801ab52e  lea     rcx, jetInstance; int
0x1801ab535  call    DBInitializeJetDatabase
0x1801ab53a  mov     edi, eax
0x1801ab53c  test    eax, eax
0x1801ab53e  jz      loc_1801AB63D
0x1801ab544  mov     r14d, 2
0x1801ab54a  mov     ecx, r14d
0x1801ab54d  call    IncrementWPPPerfCountersForLevel
0x1801ab552  test    eax, eax
0x1801ab554  jnz     short loc_1801AB5A9
0x1801ab556  call    THStateCheckForTraceOverride
0x1801ab55b  test    eax, eax
0x1801ab55d  jnz     short loc_1801AB5A9
0x1801ab55f  mov     r8d, r15d
0x1801ab562  mov     edx, r14d
0x1801ab565  xor     ecx, ecx
0x1801ab567  call    CheckWPPLevelFlagsEnabledForProvider
0x1801ab56c  test    eax, eax
0x1801ab56e  jnz     short loc_1801AB5A9
0x1801ab570  mov     eax, cs:gfTraceToSecondProvider
0x1801ab576  test    eax, eax
0x1801ab578  jz      loc_1801AB636
0x1801ab57e  call    THStateCheckForTraceOverride
0x1801ab583  test    eax, eax
0x1801ab585  jnz     short loc_1801AB5A9
0x1801ab587  call    ThStateCheckIfTraceToSecondProvier
0x1801ab58c  test    eax, eax
0x1801ab58e  jz      loc_1801AB636
0x1801ab594  mov     r8d, r15d
0x1801ab597  mov     edx, r14d
0x1801ab59a  mov     ecx, ebx
0x1801ab59c  call    CheckWPPLevelFlagsEnabledForProvider
0x1801ab5a1  test    eax, eax
0x1801ab5a3  jz      loc_1801AB636
0x1801ab5a9  mov     eax, cs:gfTraceToSecondProvider
0x1801ab5af  test    eax, eax
0x1801ab5b1  jz      short loc_1801AB5DA
0x1801ab5b3  call    THStateCheckForTraceOverride
0x1801ab5b8  test    eax, eax
0x1801ab5ba  jnz     short loc_1801AB5D6
0x1801ab5bc  call    ThStateCheckIfTraceToSecondProvier
0x1801ab5c1  test    eax, eax
0x1801ab5c3  jz      short loc_1801AB5DA
0x1801ab5c5  mov     r8d, r15d
0x1801ab5c8  mov     edx, r14d
0x1801ab5cb  mov     ecx, ebx
0x1801ab5cd  call    CheckWPPLevelFlagsEnabledForProvider
0x1801ab5d2  test    eax, eax
0x1801ab5d4  jz      short loc_1801AB5DA
0x1801ab5d6  mov     esi, ebx
0x1801ab5d8  jmp     short loc_1801AB5DC
0x1801ab5da  xor     esi, esi
0x1801ab5dc  call    THStateCheckForTraceOverride
0x1801ab5e1  test    eax, eax
0x1801ab5e3  jnz     short loc_1801AB5F8
0x1801ab5e5  mov     r8d, r15d
0x1801ab5e8  mov     edx, r14d
0x1801ab5eb  xor     ecx, ecx
0x1801ab5ed  call    CheckWPPLevelFlagsEnabledForProvider
0x1801ab5f2  test    eax, eax
0x1801ab5f4  jnz     short loc_1801AB5F8
0x1801ab5f6  xor     ebx, ebx
0x1801ab5f8  mov     [rsp+838h+SubAuthority7], edi
0x1801ab5fc  mov     [rsp+838h+SubAuthority6], edi
0x1801ab600  lea     rax, WPP_ba68a6237e4938374ef2840e94810607_Traceguids
0x1801ab607  mov     qword ptr [rsp+838h+SubAuthority5], rax
0x1801ab60c  mov     word ptr [rsp+838h+SubAuthority4], 32h ; '2'
0x1801ab613  mov     [rsp+838h+SubAuthority3], esi
  ... truncated ...
```
