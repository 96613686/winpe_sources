# CscDclInternalFsControl

- ea: `0x14007ae70`
- end: `0x14007c5ad`
- name: `CscDclInternalFsControl`
- size: `5949`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `80`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14007a9d0`

## callees

- `0x1400111cc`
- `0x140012be8`
- `0x14001406c`
- `0x140014cc0`
- `0x140014d60`
- `0x140014d94`
- `0x140017090`
- `0x14001764c`
- `0x140018930`
- `0x140018f64`
- `0x140019848`
- `0x140019858`
- `0x1400198f8`
- `0x14001991c`
- `0x140019a08`
- `0x140019a68`
- `0x140019abc`
- `0x140019ae0`
- `0x140019b6c`
- `0x140019bbc`
- `0x140019f24`
- `0x14001d194`
- `0x14002f010`
- `0x14002f440`
- `0x140046228`
- `0x140048b74`
- `0x14004b218`
- `0x14004b2f8`
- `0x14004b364`
- `0x14004b3c8`
- `0x14004b570`
- `0x14004b610`
- `0x14004b9a4`
- `0x14004bab8`
- `0x14004bcdc`
- `0x14004bdc4`
- `0x14004be90`
- `0x14004bf18`
- `0x14004bfb4`
- `0x14004c04c`
- `0x14004c124`
- `0x14004c220`
- `0x14004c364`
- `0x14004c49c`
- `0x14004c5ac`
- `0x14004c6b8`
- `0x14004c7f0`
- `0x14004c8b0`
- `0x14004c994`
- `0x14004caa4`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14007aec5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14007b869`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14007aec5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14007b869`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007b82c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007c527`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007b82c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007c527`
- `ntoskrnl!RtlLengthSid` at `0x14007b54f`
- `ntoskrnl!RtlLengthSid` at `0x14007b5a1`
- `ntoskrnl!RtlLengthSid` at `0x14007b614`
- `ntoskrnl!RtlLengthSid` at `0x14007b92a`
- `ntoskrnl!RtlLengthSid` at `0x14007c161`
- `ntoskrnl!RtlLengthSid` at `0x14007c1a5`
- `ntoskrnl!RtlLengthSid` at `0x14007b54f`
- `ntoskrnl!RtlLengthSid` at `0x14007b5a1`
- `ntoskrnl!RtlLengthSid` at `0x14007b614`
- `ntoskrnl!RtlLengthSid` at `0x14007b92a`
- `ntoskrnl!RtlLengthSid` at `0x14007c161`
- `ntoskrnl!RtlLengthSid` at `0x14007c1a5`
- `ntoskrnl!ProbeForWrite` at `0x14007b81f`
- `ntoskrnl!ProbeForWrite` at `0x14007b81f`
- `ntoskrnl!RtlValidSid` at `0x14007b56a`
- `ntoskrnl!RtlValidSid` at `0x14007b5bb`
- `ntoskrnl!RtlValidSid` at `0x14007b62e`
- `ntoskrnl!RtlValidSid` at `0x14007b8e8`
- `ntoskrnl!RtlValidSid` at `0x14007b958`
- `ntoskrnl!RtlValidSid` at `0x14007c172`
- `ntoskrnl!RtlValidSid` at `0x14007c1b7`
- `ntoskrnl!RtlValidSid` at `0x14007b56a`
- `ntoskrnl!RtlValidSid` at `0x14007b5bb`
- `ntoskrnl!RtlValidSid` at `0x14007b62e`
- `ntoskrnl!RtlValidSid` at `0x14007b8e8`
- `ntoskrnl!RtlValidSid` at `0x14007b958`
- `ntoskrnl!RtlValidSid` at `0x14007c172`
- `ntoskrnl!RtlValidSid` at `0x14007c1b7`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x14007b31a`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x14007b31a`
- `ntoskrnl!IoIs32bitProcess` at `0x14007b163`
- `ntoskrnl!IoIs32bitProcess` at `0x14007bb8f`
- `ntoskrnl!IoIs32bitProcess` at `0x14007bc16`
- `ntoskrnl!IoIs32bitProcess` at `0x14007b163`
- `ntoskrnl!IoIs32bitProcess` at `0x14007bb8f`
- `ntoskrnl!IoIs32bitProcess` at `0x14007bc16`

## pseudocode

```c
__int64 __fastcall CscDclInternalFsControl(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  __int64 v6; // rdx
  int ItemInformationExtended; // ebx
  __int64 v8; // r8
  unsigned int i; // r9d
  __int64 v10; // rdi
  unsigned __int64 v11; // rbx
  _WORD *v12; // rsi
  unsigned int v13; // r15d
  __int64 FsctlOperationString; // rax
  __int64 v15; // r10
  int v16; // r12d
  int v17; // ecx
  int SecurityInformation; // eax
  int v19; // r15d
  int v20; // eax
  __int64 v21; // rcx
  int v22; // edx
  unsigned int v23; // r8d
  int HashData; // eax
  int v25; // r8d
  int v26; // r9d
  void *v27; // rdx
  char v28; // r10
  int ConnectionPerf; // eax
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  int PeerCachingSettings; // eax
  ULONG v35; // edx
  int v36; // eax
  int v37; // edx
  int v38; // r8d
  int v39; // r9d
  __int64 v40; // r10
  __int64 v41; // r11
  __int64 v42; // rcx
  int v43; // ecx
  int v44; // ecx
  __int64 v45; // rsi
  __int64 v46; // r15
  __int64 v47; // rcx
  int v48; // ecx
  __int16 v49; // ax
  int v50; // r15d
  int v51; // eax
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // r9
  union _LARGE_INTEGER *v55; // rax
  void *v56; // rdi
  int v57; // ecx
  __int16 v58; // dx
  __int16 v59; // ax
  __int16 v60; // ax
  __int64 v61; // r8
  __int64 v62; // rdx
  __int64 v63; // rdx
  __int64 v64; // r8
  __int64 v65; // r9
  __int128 *v66; // rax
  int v67; // ecx
  int HashCapabilities; // eax
  int v69; // ecx
  __int16 v70; // ax
  int v71; // r12d
  int v72; // edx
  __int64 v73; // rcx
  int v74; // ecx
  __int64 v75; // rcx
  __int128 *v76; // rdx
  __int64 v77; // rdx
  __int64 v78; // rcx
  unsigned __int16 v79; // r8
  int v80; // eax
  __int64 v81; // rdx
  int v82; // eax
  unsigned __int64 v83; // rax
  unsigned __int64 v84; // r8
  int v85; // ecx
  unsigned int v86; // r8d
  unsigned int v87; // r9d
  int v88; // eax
  __int64 v89; // rcx
  __int64 v90; // rcx
  int v91; // edx
  unsigned int v92; // r8d
  char *v93; // rdi
  ULONG v94; // esi
  ULONG v95; // esi
  char *v96; // r15
  ULONG v97; // r12d
  __int64 v98; // rcx
  int v99; // edx
  __int64 v100; // rcx
  __int128 *v101; // rdx
  int v102; // eax
  HANDLE Handle; // [rsp+30h] [rbp-138h]
  unsigned int v105; // [rsp+50h] [rbp-118h] BYREF
  __int128 v106; // [rsp+58h] [rbp-110h] BYREF
  _WORD v107[2]; // [rsp+68h] [rbp-100h] BYREF
  char v108; // [rsp+6Ch] [rbp-FCh]
  __int128 v109; // [rsp+70h] [rbp-F8h] BYREF
  _DWORD v110[4]; // [rsp+80h] [rbp-E8h] BYREF
  _QWORD v111[12]; // [rsp+90h] [rbp-D8h] BYREF
  __int128 v112; // [rsp+F0h] [rbp-78h] BYREF
  __int128 v113; // [rsp+100h] [rbp-68h]
  __int128 v114; // [rsp+110h] [rbp-58h]
  __int64 v115; // [rsp+120h] [rbp-48h]

  *(_QWORD *)&v109 = a1;
  memset(v111, 0, sizeof(v111));
  v105 = 0;
  v108 = 0;
  KeEnterCriticalRegion();
  ItemInformationExtended = CscDclpInitializeFsctlContext(v111, a4);
  if ( ItemInformationExtended < 0 )
    goto LABEL_349;
  v10 = v111[6];
  v11 = LODWORD(v111[7]);
  v12 = (_WORD *)v111[10];
  v13 = v111[11];
  v110[0] = v111[11];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    FsctlOperationString = CscDclpGetFsctlOperationString(LODWORD(v111[0]));
    WPP_SF_s(*(_QWORD *)(v15 + 24), 59, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids, FsctlOperationString);
  }
  v16 = 1;
  if ( (v111[0] & 0x100000000LL) != 0 )
  {
    LOBYTE(v6) = 1;
    CscDclpSynchronizeMRx(a1, v6);
    v108 = 1;
  }
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 56) + 156LL) & 0x1000080) != 0 )
  {
    ItemInformationExtended = -1073741628;
    goto LABEL_349;
  }
  if ( SLODWORD(v111[0]) > 38 )
  {
    if ( SLODWORD(v111[0]) > 57 )
    {
      if ( SLODWORD(v111[0]) > 67 )
      {
        switch ( LODWORD(v111[0]) )
        {
          case 'D':
            ItemInformationExtended = CscDclMRxQueryItemInformationExtended(a1, v12, v12 + 8);
            if ( ItemInformationExtended >= 0 )
              v105 = 40;
            goto LABEL_349;
          case 'E':
            v16 = 4;
            if ( v13 < 4 )
              goto LABEL_26;
            PeerCachingSettings = CscDclMRxGetPeerCachingSettings((unsigned int)(LODWORD(v111[0]) - 69), v12);
            goto LABEL_63;
          case 'F':
            HashData = CscDclMRxResetKernelPerformanceCounters();
            goto LABEL_38;
        }
        if ( LODWORD(v111[0]) != 71 )
        {
          switch ( LODWORD(v111[0]) )
          {
            case 'H':
              if ( (unsigned int)v11 < 0xC )
                goto LABEL_26;
              HashData = CscDclMRxSetCachingSettings((unsigned int)(LODWORD(v111[0]) - 72), *(unsigned int *)(v10 + 8));
              break;
            case 'I':
              if ( v13 > 0xFFFF )
                LOWORD(v13) = -1;
              *(_QWORD *)&v106 = 0;
              *(_DWORD *)((char *)&v106 + 2) = (unsigned __int16)(v13 - 4);
              *((_QWORD *)&v106 + 1) = v12 + 2;
              *v12 = 0;
              ItemInformationExtended = CscDclMRxQueryFailedTransitionPath(a1, &v106, v12);
              v102 = (unsigned __int16)v106;
              v12[1] = v106;
              v105 = v102 + 4;
              goto LABEL_349;
            case 'J':
              HashData = CscDclMrxPrugeOfflineLviewCache();
              break;
            default:
              goto LABEL_26;
          }
          goto LABEL_38;
        }
        if ( v13 < 8 )
          goto LABEL_26;
        HashCapabilities = CscDclMRxQueryHashCapabilities(a1, v12, v12 + 2);
        goto LABEL_224;
      }
      if ( LODWORD(v111[0]) == 67 )
      {
        v106 = 0;
        if ( v13 < 0x10 )
          goto LABEL_26;
        v100 = *(unsigned __int16 *)(v10 + 8);
        LOWORD(v106) = v100;
        WORD1(v106) = v100;
        *((_QWORD *)&v106 + 1) = v10 + 10;
        v101 = &v106;
        if ( !(_WORD)v100 )
          v101 = 0;
        ConnectionPerf = CscDclMRxGetConnectionPerf(v100, v101, v12, v12 + 4);
LABEL_48:
        ItemInformationExtended = ConnectionPerf;
        if ( ConnectionPerf >= 0 )
          v105 = 16;
        goto LABEL_349;
      }
      if ( LODWORD(v111[0]) == 58 )
      {
        ItemInformationExtended = CscDclMRxQueryHandleOplockState(a1, v12, (char *)v12 + 1);
        goto LABEL_30;
      }
      if ( LODWORD(v111[0]) != 59 )
      {
        if ( LODWORD(v111[0]) == 60 )
        {
          if ( (unsigned int)v11 < 0x10 )
            goto LABEL_26;
          HashData = CscDclMRxSetTransparentCacheSettings(
                       LODWORD(v111[0]),
                       *(unsigned int *)(v10 + 8),
                       *(unsigned int *)(v10 + 12));
          goto LABEL_38;
        }
        if ( LODWORD(v111[0]) == 61 )
        {
          if ( (unsigned int)v11 < 0xC )
            goto LABEL_26;
          HashData = CscDclMRxSetPeerCachingSettings(LODWORD(v111[0]), *(unsigned int *)(v10 + 8));
          goto LABEL_38;
        }
        if ( LODWORD(v111[0]) != 62 )
        {
          switch ( LODWORD(v111[0]) )
          {
            case '?':
              if ( (unsigned int)v11 < 0x18 )
                goto LABEL_26;
              v98 = *(unsigned int *)(v10 + 20);
              if ( (_DWORD)v98 + *(_DWORD *)(v10 + 16) != (_DWORD)v11 )
                goto LABEL_26;
              HashData = CscDclMRxWriteStoreData(a1, *(_QWORD *)(v10 + 8), v10 + v98);
              break;
            case '@':
              if ( (unsigned int)v11 < 0x20 )
                goto LABEL_26;
              HashData = CscDclMRxRetrieveHashData(
                           a1,
                           *(_DWORD *)(v10 + 8),
                           *(_DWORD *)(v10 + 12),
                           *(_QWORD *)(v10 + 16),
                           *(_DWORD *)(v10 + 24),
                           (__int64)v12,
                           v13,
                           (__int64)&v105);
              break;
            case 'A':
              if ( (unsigned int)v11 < 0xC || (*(_DWORD *)(v10 + 8) & 0xFFFFFFF8) != 0 )
                goto LABEL_26;
              HashData = CscDclMRxSetPrefetch(a1);
              break;
            default:
              HashData = CscDclMRxClearAllConnectionPerf();
              break;
          }
          goto LABEL_38;
        }
        if ( v13 < 0x40 )
          goto LABEL_26;
        ItemInformationExtended = CscDclMRxQueryKernelPerformanceCounters(LODWORD(v111[0]), v12);
        if ( ItemInformationExtended )
          goto LABEL_349;
        goto LABEL_94;
      }
    }
    else
    {
      if ( LODWORD(v111[0]) == 57 )
      {
        HashData = CscDclMRxConvertBackoutHandle(a1);
        goto LABEL_38;
      }
      if ( SLODWORD(v111[0]) <= 48 )
      {
        switch ( LODWORD(v111[0]) )
        {
          case '0':
            v106 = 0;
            v75 = *(unsigned __int16 *)(v10 + 20);
            LOWORD(v106) = v75;
            WORD1(v106) = v75;
            *((_QWORD *)&v106 + 1) = v10 + 22;
            v76 = &v106;
            if ( !(_WORD)v75 )
              v76 = 0;
            HashData = CscDclMRxSetConnectionPerf(v75, v76, *(_QWORD *)(v10 + 8), *(unsigned int *)(v10 + 16));
            goto LABEL_38;
          case '\'':
            HashData = CscDclMRxImportAssociateHandle(a1, v10 + 8);
            goto LABEL_38;
          case '(':
            HashData = CscDclMRxImportEnd(a1, 0);
            goto LABEL_38;
          case ')':
            v106 = 0;
            v74 = *(unsigned __int16 *)(v10 + 10);
            if ( (unsigned int)v11 < v74 + 12 )
              goto LABEL_26;
            LOWORD(v106) = *(_WORD *)(v10 + 10);
            WORD1(v106) = v74;
            *((_QWORD *)&v106 + 1) = v10 + 12;
            LOBYTE(v6) = *(_BYTE *)(v10 + 8);
            HashData = CscDclMRxImportItem(a1, v6, (unsigned int)&v106, (_DWORD)v12, v13, (__int64)&v105);
            goto LABEL_38;
          case '*':
            v106 = 0;
            v109 = 0;
            v72 = *(unsigned __int16 *)(v10 + 10);
            v73 = *(unsigned __int16 *)(v10 + 12);
            if ( (unsigned int)v11 < (int)v73 + v72 + 14 )
              goto LABEL_26;
            LOWORD(v106) = *(_WORD *)(v10 + 12);
            WORD1(v106) = v73;
            *((_QWORD *)&v106 + 1) = v10 + 14;
            LOWORD(v109) = v72;
            WORD1(v109) = v72;
            *((_QWORD *)&v109 + 1) = v10 + v73 + 14;
            HashData = CscDclMRxImportFile(
                         a1,
                         *(unsigned __int16 *)(v10 + 8),
                         (unsigned int)&v109,
                         (unsigned int)&v106,
                         (__int64)v12,
                         v13,
                         (__int64)&v105);
            goto LABEL_38;
          case '+':
            v106 = 0;
            v109 = 0;
            v69 = *(unsigned __int16 *)(v10 + 8);
            if ( (unsigned int)v11 < v69 + 10 )
              goto LABEL_26;
            LOWORD(v106) = *(_WORD *)(v10 + 8);
            WORD1(v106) = v69;
            *((_QWORD *)&v106 + 1) = v10 + 10;
            v70 = 0;
            if ( v13 > 6 )
            {
              *((_QWORD *)&v109 + 1) = v12 + 3;
              if ( v13 > 0xFFFF )
                LOWORD(v13) = -1;
              v70 = v13 - 6;
              WORD1(v109) = v13 - 6;
            }
            ItemInformationExtended = CscDclMRxImportQueryTempName(
                                        a1,
                                        (unsigned int)&v106,
                                        (unsigned __int64)&v109 & -(__int64)(v70 != 0),
                                        (int)v12 + 2,
                                        (__int64)v12);
            if ( ItemInformationExtended >= 0 )
            {
              v71 = (unsigned __int16)v109;
              v12[2] = v109;
              v16 = v71 + 6;
            }
            else
            {
              v16 = 4;
            }
LABEL_64:
            v105 = v16;
            goto LABEL_349;
        }
        if ( LODWORD(v111[0]) != 44 )
        {
          if ( LODWORD(v111[0]) != 45 )
          {
            if ( LODWORD(v111[0]) != 46 )
            {
              ItemInformationExtended = -1073741822;
              goto LABEL_349;
            }
            v112 = 0;
            v113 = 0;
            v114 = 0;
            v115 = 0;
            if ( IoIs32bitProcess(*(PIRP *)(a1 + 40)) )
            {
              if ( (_DWORD)v11 != 72 )
                goto LABEL_26;
              v65 = *(int *)(v10 + 12);
              v112 = *(_OWORD *)(v10 + 16);
              v113 = *(_OWORD *)(v10 + 32);
              v114 = *(_OWORD *)(v10 + 48);
              v115 = *(_QWORD *)(v10 + 64);
              v66 = &v112;
            }
            else
            {
              if ( (_DWORD)v11 != 80 )
                goto LABEL_26;
              v65 = *(_QWORD *)(v10 + 16);
              v66 = (__int128 *)(v10 + 24);
            }
            LOBYTE(v64) = *(_BYTE *)(v10 + 9);
            LOBYTE(v63) = *(_BYTE *)(v10 + 8);
            HashData = CscDclMrxUpdateSuspendedItem(a1, v63, v64, v65, v66);
            goto LABEL_38;
          }
          if ( IoIs32bitProcess(*(PIRP *)(a1 + 40)) )
            goto LABEL_26;
          ItemInformationExtended = CscDclMRxCreateReplaceDataHandleForSuspendedItem(
                                      a1,
                                      *(unsigned int *)(v10 + 8),
                                      v12);
          if ( ItemInformationExtended )
            goto LABEL_349;
LABEL_221:
          v105 = 8;
          goto LABEL_349;
        }
        v106 = 0;
        v67 = *(unsigned __int16 *)(v10 + 8);
        if ( (unsigned int)v11 < v67 + 10 )
          goto LABEL_26;
        LOWORD(v106) = *(_WORD *)(v10 + 8);
        WORD1(v106) = v67;
        *((_QWORD *)&v106 + 1) = v10 + 10;
        HashCapabilities = CscDclMRxImportQueryGatheredStoreVersion(a1, &v106, v12, v12 + 2);
LABEL_224:
        ItemInformationExtended = HashCapabilities;
        if ( HashCapabilities < 0 )
          goto LABEL_349;
        goto LABEL_221;
      }
      if ( LODWORD(v111[0]) != 49 )
      {
        if ( LODWORD(v111[0]) == 50 )
        {
          HashData = CscDclMRxFlushPriorityQueue(a1);
          goto LABEL_38;
        }
        if ( LODWORD(v111[0]) == 51 )
        {
          v93 = (char *)(v10 + 8);
          v94 = RtlLengthSid(v93);
          if ( !RtlValidSid(v93) )
            goto LABEL_36;
          if ( v94 + 8 > (unsigned int)v11 )
            goto LABEL_36;
          v95 = v94 + 3;
          v96 = &v93[v95 & 0xFFFFFFFC];
          v97 = RtlLengthSid(v96);
          if ( !RtlValidSid(v96) || v97 + (v95 & 0xFFFFFFFC) + 8 > (unsigned int)v11 )
            goto LABEL_36;
          HashData = CscDclMRxReplaceSid(a1, v93, v96);
          goto LABEL_38;
        }
        if ( LODWORD(v111[0]) != 52 )
        {
          if ( LODWORD(v111[0]) == 53 )
          {
            v106 = 0;
            v89 = *(unsigned __int16 *)(v10 + 8);
            if ( (unsigned int)v11 < (int)v89 + 10 || (v89 & 1) != 0 )
              goto LABEL_26;
            WORD1(v106) = *(_WORD *)(v10 + 8);
            LOWORD(v106) = v89;
            *((_QWORD *)&v106 + 1) = v10 + 10;
            HashData = CscDclMRxTest(v89, &v106);
          }
          else
          {
            if ( LODWORD(v111[0]) == 54 )
            {
              v106 = 0;
              LOBYTE(v107[0]) = 0;
              LOBYTE(v110[0]) = 0;
              v85 = *(unsigned __int16 *)(v10 + 12);
              if ( (unsigned int)v11 < v85 + 14
                || (unsigned __int16)v85 <= 4u
                || *(_WORD *)(v10 + 14) != 92
                || *(_WORD *)(v10 + 16) != 92 )
              {
                goto LABEL_26;
              }
              *((_QWORD *)&v106 + 1) = v10 + 16;
              LOWORD(v85) = v85 - 2;
              LOWORD(v106) = v85;
              WORD1(v106) = v85;
              ItemInformationExtended = 0;
              v105 = 4;
              v86 = *(_DWORD *)(v10 + 8);
              v87 = v86 >> 1;
              LOBYTE(v87) = (v86 & 2) != 0;
              LOBYTE(v86) = v86 & 1;
              CscDclMRxIsKnownOfflinePath(v85, (unsigned int)&v106, v86, v87, (__int64)v107, (__int64)v110);
              *(_DWORD *)v12 = 0;
              v88 = 0;
              if ( LOBYTE(v107[0]) )
              {
                *(_DWORD *)v12 = 2;
                v88 = 2;
              }
              if ( LOBYTE(v110[0]) )
                *(_DWORD *)v12 = v88 | 1;
              goto LABEL_349;
            }
            v77 = (unsigned int)(LODWORD(v111[0]) - 55);
            if ( LODWORD(v111[0]) == 55 )
            {
              v78 = *(unsigned int *)(v10 + 12);
              if ( v11 < 16 * (v78 + 1) )
                goto LABEL_26;
              if ( LOBYTE(v111[3]) )
              {
                for ( i = 0; ; ++i )
                {
                  LODWORD(v78) = *(_DWORD *)(v10 + 12);
                  if ( i >= (unsigned int)v78 )
                    break;
                  v79 = *(_WORD *)(v10 + 16LL * i + 16);
                  if ( v79 == 0xFFFF || (v80 = 0, (v79 & 1) != 0) )
                    v80 = -1073741811;
                  if ( v80 < 0 )
                    goto LABEL_36;
                  v81 = *(unsigned __int16 *)(v10 + 16LL * i + 18);
                  if ( v81 == 0xFFFF || (v82 = 0, (v81 & 1) != 0) )
                    v82 = -1073741811;
                  if ( v82 < 0 || (unsigned __int16)v81 < v79 )
                    goto LABEL_36;
                  v83 = *(_QWORD *)(v10 + 16LL * i + 24) - v111[4];
                  v84 = v83 + v81;
                  if ( v83 + v81 < v83 || v84 > 0xFFFFFFFF )
                  {
                    LODWORD(v8) = -1073741811;
                    v77 = v83 + v10;
                  }
                  else
                  {
                    if ( v84 > v11 )
                      goto LABEL_36;
                    v77 = v83 + v10;
                    if ( (((_BYTE)v83 + (_BYTE)v10) & 1) != 0 )
                      goto LABEL_36;
                    LODWORD(v8) = 0;
                  }
                  if ( (int)v8 < 0 )
                    goto LABEL_36;
                  *(_QWORD *)(v10 + 16LL * i + 24) = v77;
                }
              }
              LOBYTE(i) = *(_BYTE *)(v10 + 8) & 2;
              LOBYTE(v8) = *(_BYTE *)(v10 + 8) & 4;
              LOBYTE(v77) = *(_BYTE *)(v10 + 8) & 1;
              HashData = CscDclMRxOfflineDirectoryRenameSetEntries(a1, v77, v8, i, v10 + 16, v78);
            }
            else
            {
              LODWORD(v77) = *(_BYTE *)(v10 + 8) & 1;
              HashData = CscDclMRxOfflineDirectoryRenameRemoveEntries(a1, v77);
            }
          }
          goto LABEL_38;
        }
        v109 = 0;
        v106 = 0;
        v90 = *(unsigned __int16 *)(v10 + 8);
        v91 = *(unsigned __int16 *)(v10 + 10);
        v92 = v91 + v90 + 12;
        if ( v92 >= (int)v90 + 12 )
        {
          if ( v92 > (unsigned int)v11 )
            goto LABEL_36;
          WORD1(v109) = *(_WORD *)(v10 + 8);
          LOWORD(v109) = v90;
          *((_QWORD *)&v109 + 1) = v10 + 12;
          WORD1(v106) = v91;
          LOWORD(v106) = v91;
          *((_QWORD *)&v106 + 1) = v10 + 12 + v90;
          HashData = CscDclMRxRebootRenameAdd(*((_QWORD *)&v106 + 1), &v109, &v106);
          goto LABEL_38;
        }
LABEL_39:
        ItemInformationExtended = -1073741675;
        goto LABEL_349;
      }
    }
    v109 = 0;
    v99 = *(unsigned __int16 *)(v10 + 8);
    if ( (unsigned int)v11 < v99 + 10 )
      goto LABEL_26;
    LOWORD(v109) = *(_WORD *)(v10 + 8);
    WORD1(v109) = v99;
    *((_QWORD *)&v109 + 1) = v10 + 10;
    if ( LODWORD(v111[0]) == 49 )
      HashData = CscDclMRxSetSparseExclusionList(49, &v109);
    else
      HashData = CscDclMRxSetExcludedFileTypes(LODWORD(v111[0]), &v109);
    goto LABEL_38;
  }
  if ( LODWORD(v111[0]) == 38 )
  {
    v61 = *(unsigned int *)(v10 + 8);
    v62 = v10 + 12;
    if ( !(_DWORD)v61 )
      v62 = 0;
    ItemInformationExtended = CscDclMRxImportStart(a1, v62, v61, v12);
    if ( ItemInformationExtended < 0 )
      goto LABEL_349;
LABEL_66:
    v105 = 20;
    goto LABEL_349;
  }
  if ( SLODWORD(v111[0]) > 19 )
  {
    if ( SLODWORD(v111[0]) > 29 )
    {
      switch ( LODWORD(v111[0]) )
      {
        case 0x1E:
          HashData = CscDclpUpcallReply(
                       a1,
                       *(_QWORD *)(v10 + 16),
                       *(_DWORD *)(v10 + 8),
                       *(_QWORD *)(v10 + 24),
                       *(_DWORD *)(v10 + 32));
          goto LABEL_38;
        case 0x1F:
          HashData = CscDclMRxDeleteCredential(a1);
          goto LABEL_38;
        case 0x20:
          if ( v13 > 1 )
            goto LABEL_26;
          PeerCachingSettings = CscDclMRxIsCredError(a1, v12);
          goto LABEL_63;
        case 0x21:
          LOBYTE(v6) = *(_BYTE *)(v10 + 8);
          HashData = CscDclMRxEncryptDecryptItem(a1, v6);
          goto LABEL_38;
        case 0x22:
          v106 = 0;
          v60 = *(_WORD *)(v10 + 10);
          if ( (v60 & 1) != 0 )
            goto LABEL_26;
          WORD1(v106) = *(_WORD *)(v10 + 10);
          LOWORD(v106) = v60;
          *((_QWORD *)&v106 + 1) = v10 + 12;
          LOBYTE(v8) = *(_BYTE *)(v10 + 8);
          HashData = CscDclMRxExtractDir(a1, &v106, v8);
          goto LABEL_38;
      }
      if ( LODWORD(v111[0]) != 35 )
      {
        if ( LODWORD(v111[0]) == 36 )
        {
          if ( (unsigned int)v11 < 0x14 )
            goto LABEL_26;
          v56 = (void *)(v10 + 8);
          if ( (unsigned int)v11 < RtlLengthSid(v56) + 8 )
            goto LABEL_26;
          v19 = 2;
          if ( v110[0] > 2u || !RtlValidSid(v56) )
            goto LABEL_26;
          ItemInformationExtended = CscDclMRxGetSidIndex(a1, v56, v12);
          if ( ItemInformationExtended >= 0 )
            goto LABEL_31;
        }
        else
        {
          if ( !RtlValidSid((PSID)(v10 + 8)) )
            goto LABEL_26;
          ItemInformationExtended = CscDclMRxAddSid(a1, v10 + 8, v12);
          if ( ItemInformationExtended >= 0 )
            goto LABEL_30;
        }
        goto LABEL_349;
      }
      v106 = 0;
      v109 = 0;
      v57 = *(unsigned __int16 *)(v10 + 8);
      if ( (unsigned int)v11 < v57 + 10 )
        goto LABEL_26;
      v58 = 0;
      if ( v13 > 4 )
      {
        *((_QWORD *)&v109 + 1) = v12 + 2;
        if ( v13 > 0xFFFF )
          LOWORD(v13) = -1;
        v58 = v13 - 4;
        WORD1(v109) = v13 - 4;
      }
      v59 = 0;
      if ( (_WORD)v57 )
      {
        LOWORD(v106) = v57;
        WORD1(v106) = v57;
        *((_QWORD *)&v106 + 1) = v10 + 10;
        v59 = v57;
      }
      ItemInformationExtended = CscDclMRxExtractQueryItemLocation(
                                  a1,
                                  (unsigned __int64)&v106 & -(__int64)(v59 != 0),
                                  (unsigned __int64)&v109 & -(__int64)(v58 != 0),
                                  v12);
      if ( ItemInformationExtended < 0 )
        goto LABEL_30;
      v50 = (unsigned __int16)v109;
    }
    else
    {
      if ( LODWORD(v111[0]) == 29 )
      {
        if ( LOBYTE(v111[3]) )
          ProbeForWrite(*(volatile void **)(v10 + 24), *(unsigned int *)(v10 + 32), 1u);
        KeLeaveCriticalRegion();
        v55 = 0;
        if ( !*(_BYTE *)(v10 + 8) )
          v55 = (union _LARGE_INTEGER *)(v10 + 16);
        ItemInformationExtended = CscDclpUpcallReceive(
                                    a1,
                                    v111[1],
                                    *(_QWORD *)(v10 + 24),
                                    *(_DWORD *)(v10 + 32),
                                    v55,
                                    (__int64)v12);
        KeEnterCriticalRegion();
        if ( !ItemInformationExtended )
          v105 = 32;
        goto LABEL_349;
      }
      if ( LODWORD(v111[0]) == 20 )
      {
        v51 = *(_DWORD *)(v10 + 8);
        if ( (v51 & 0xFFFFFFF8) != 0 || !v51 )
          goto LABEL_26;
        v52 = 0;
        v53 = 0;
        v54 = 0;
        if ( (v51 & 1) != 0 )
          v52 = v10 + 12;
        if ( (v51 & 2) != 0 )
          v53 = v10 + 16;
        if ( (v51 & 4) != 0 )
          v54 = v10 + 20;
        HashData = CscDclMRxSetDatabaseEvictionPeriod((unsigned int)(LODWORD(v111[0]) - 20), v52, v53, v54);
        goto LABEL_38;
      }
      v47 = (unsigned int)(LODWORD(v111[0]) - 21);
      if ( LODWORD(v111[0]) != 21 )
      {
        switch ( LODWORD(v111[0]) )
        {
          case 0x16:
            v48 = *(unsigned __int16 *)(v10 + 32);
            if ( (unsigned int)v11 < v48 + 34 || (v48 & 1) != 0 )
              goto LABEL_26;
            PeerCachingSettings = CscDclMRxSetLocationDatabase();
            break;
          case 0x17:
            goto LABEL_108;
          case 0x18:
            HashData = CscDclpUpcallConnect(a1, v111[1], LODWORD(v111[2]));
            goto LABEL_38;
          case 0x19:
            HashData = CscDclpUpcallDisconnect(a1);
            goto LABEL_38;
          case 0x1A:
            HashData = CscDclMRxEnable();
            goto LABEL_38;
          case 0x1B:
            goto LABEL_108;
          default:
            PeerCachingSettings = CscDclMRxIsEnabled((unsigned int)(LODWORD(v111[0]) - 27), v12);
            break;
        }
LABEL_63:
        ItemInformationExtended = PeerCachingSettings;
        if ( PeerCachingSettings < 0 )
          goto LABEL_349;
        goto LABEL_64;
      }
      v106 = 0;
      *(_DWORD *)v12 = 0;
      v49 = 0;
      if ( v13 > 4 )
      {
        *((_QWORD *)&v106 + 1) = v12 + 2;
        if ( v13 > 0xFFFF )
          LOWORD(v13) = -1;
        v49 = v13 - 4;
        WORD1(v106) = v13 - 4;
      }
      ItemInformationExtended = CscDclMRxQueryLocationDatabase(v47, (unsigned __int64)&v106 & -(__int64)(v49 != 0), v12);
      if ( ItemInformationExtended < 0 )
        goto LABEL_30;
      v50 = (unsigned __int16)v106;
    }
    v12[1] = v50;
    v19 = v50 + 4;
    goto LABEL_31;
  }
  if ( LODWORD(v111[0]) == 19 )
  {
    ItemInformationExtended = CscDclMRxQueryDatabaseEvictionPeriod(19, v12, v12 + 2, v12 + 4);
    if ( ItemInformationExtended >= 0 )
      v105 = 12;
    goto LABEL_349;
  }
  if ( SLODWORD(v111[0]) > 9 )
  {
    switch ( LODWORD(v111[0]) )
    {
      case 0xA:
        v46 = 0;
        if ( *(_BYTE *)(v10 + 8) )
        {
          if ( (unsigned int)v11 < 0x18 )
            goto LABEL_26;
          v46 = v10 + 12;
          if ( (unsigned int)v11 < RtlLengthSid((PSID)(v10 + 12)) + 12 || !RtlValidSid((PSID)(v10 + 12)) )
            goto LABEL_26;
        }
        ItemInformationExtended = CscDclMRxQueryPinInformation(a1, v46, v12);
        if ( ItemInformationExtended >= 0 )
          v105 = 3;
        goto LABEL_349;
      case 0xB:
        HashData = CscDclMRxQueryPinAllInformation(a1, &v105, v13, v12);
        goto LABEL_38;
      case 0xC:
        v45 = 0;
        if ( *(_BYTE *)(v10 + 12) )
        {
          if ( (unsigned int)v11 < 0x1C )
            goto LABEL_26;
          v45 = v10 + 16;
          if ( (unsigned int)v11 < RtlLengthSid((PSID)(v10 + 16)) + 16 || !RtlValidSid((PSID)(v10 + 16)) )
            goto LABEL_26;
        }
        HashData = CscDclMRxSetPinInformation(a1, v45, v10 + 8);
        goto LABEL_38;
    }
    if ( LODWORD(v111[0]) != 13 )
    {
      switch ( LODWORD(v111[0]) )
      {
        case 0xE:
          v106 = 0;
          v44 = *(unsigned __int16 *)(v10 + 14);
          if ( (unsigned int)v11 < v44 + 16 || (v44 & 1) != 0 )
            goto LABEL_26;
          WORD1(v106) = *(_WORD *)(v10 + 14);
          LOWORD(v106) = v44;
          *((_QWORD *)&v106 + 1) = v10 + 16;
          HashData = CscDclMRxQueryDirectory(
                       a1,
                       (unsigned int)&v105,
                       (_DWORD)v12,
                       v13,
                       *(_DWORD *)(v10 + 8),
                       *(_BYTE *)(v10 + 12),
                       (__int64)&v106,
                       *(_BYTE *)(v10 + 13));
          goto LABEL_38;
        case 0xF:
          if ( (_DWORD)v11 != 16 || v13 < 0x18 )
            goto LABEL_26;
          HashData = CscDclMRxQueryDiffTransferOffsets(a1, *(_QWORD *)(v10 + 8), v13, (_DWORD)v12, (__int64)&v105);
          goto LABEL_38;
        case 0x10:
          v106 = 0;
          v43 = *(unsigned __int16 *)(v10 + 10);
          if ( (unsigned int)v11 < v43 + 12 || (v43 & 1) != 0 )
            goto LABEL_26;
          WORD1(v106) = *(_WORD *)(v10 + 10);
          LOWORD(v106) = v43;
          *((_QWORD *)&v106 + 1) = v10 + 12;
          HashData = CscDclMRxEnumerateQueue(
                       a1,
                       (unsigned int)&v105,
                       (_DWORD)v12,
                       v13,
                       *(_BYTE *)(v10 + 8),
                       *(_BYTE *)(v10 + 9),
                       (__int64)&v106);
          goto LABEL_38;
      }
      if ( LODWORD(v111[0]) != 17 )
      {
        v36 = *(_DWORD *)(v10 + 8);
        if ( (v36 & 0xFFFFFFE0) != 0 )
          goto LABEL_26;
        v37 = 0;
        v38 = 0;
        v39 = 0;
        v40 = 0;
        v41 = 0;
        v42 = 0;
        if ( (v36 & 1) != 0 )
          v37 = v10 + 12;
        if ( (v36 & 2) != 0 )
          v38 = v10 + 24;
        if ( (v36 & 4) != 0 )
          v39 = v10 + 32;
        if ( (v36 & 8) != 0 )
          v40 = v10 + 49;
        if ( (v36 & 0x10) != 0 )
          v41 = v10 + 50;
        if ( (v36 & 0x20) != 0 )
          v42 = v10 + 48;
        HashData = CscDclMRxSetDatabase(v42, v37, v38, v39, v40, v41, v42);
        goto LABEL_38;
      }
      ItemInformationExtended = CscDclMRxQueryDatabase(
                                  0,
                                  (_DWORD)v12,
                                  (int)v12 + 57,
                                  (int)v12 + 58,
                                  (__int64)(v12 + 28));
      if ( ItemInformationExtended < 0 )
        goto LABEL_349;
LABEL_94:
      v105 = 64;
      goto LABEL_349;
    }
    if ( *(_BYTE *)(v10 + 12)
      && ((unsigned int)v11 < 0x1C
       || (unsigned int)v11 < RtlLengthSid((PSID)(v10 + 16)) + 16
       || !RtlValidSid((PSID)(v10 + 16))) )
    {
      goto LABEL_26;
    }
LABEL_108:
    HashData = CscDclMRxSetLocationDatabase();
    goto LABEL_38;
  }
  switch ( LODWORD(v111[0]) )
  {
    case 9:
      v35 = *(_DWORD *)(v10 + 12);
      if ( v35 > 0x44
        || (unsigned int)v11 < v35 + 16
        || !RtlValidRelativeSecurityDescriptor((PSECURITY_DESCRIPTOR)(v10 + 16), v35, 0) )
      {
        goto LABEL_26;
      }
      HashData = CscDclMRxSetSecurityInformation(a1, *(unsigned int *)(v10 + 8), v10 + 16);
      goto LABEL_38;
    case 0:
      ItemInformationExtended = CscDclMRxQueryHandleInformation(a1, v12);
      goto LABEL_66;
    case 1:
      LOBYTE(i) = *(_BYTE *)(v10 + 16);
      PeerCachingSettings = CscDclMRxTransition(a1, *(_DWORD *)(v10 + 8), *(_DWORD *)(v10 + 12), i, (__int64)v12);
      goto LABEL_63;
    case 2:
      ItemInformationExtended = CscDclMRxQueryItemInformation(a1, v12, v12 + 28);
      if ( ItemInformationExtended >= 0 )
        v105 = 136;
      goto LABEL_349;
    case 3:
      v30 = *(_DWORD *)(v10 + 8);
      if ( (v30 & 0xFFFFFFF8) != 0 )
        goto LABEL_26;
      v31 = 0;
      v32 = 0;
      v33 = 0;
      if ( (v30 & 1) != 0 )
        v31 = v10 + 12;
      if ( (v30 & 2) != 0 )
        v32 = v10 + 20;
      if ( (v30 & 4) != 0 )
        v33 = v10 + 32;
      HashData = CscDclMRxSetItemInformation(a1, v31, v32, v33);
      goto LABEL_38;
    case 4:
      *(_DWORD *)v12 = CscDclMRxDeleteItem(a1, *(unsigned int *)(v10 + 8), v12 + 2, v12 + 4);
      v105 = 12;
      ItemInformationExtended = 0;
      goto LABEL_349;
    case 5:
      HashData = CscDclMRxEvictItem(a1);
      goto LABEL_38;
    case 6:
      if ( IoIs32bitProcess(*(PIRP *)(a1 + 40)) )
      {
        if ( (_DWORD)v11 != 24 )
          goto LABEL_26;
        v27 = (void *)*(int *)(v10 + 16);
      }
      else
      {
        if ( (_DWORD)v11 != 32 )
          goto LABEL_26;
        v27 = *(void **)(v10 + 24);
      }
      if ( v27 == (void *)-1LL )
        goto LABEL_26;
      LOBYTE(v26) = *(_BYTE *)(v10 + 8);
      if ( (v26 & 1) == ((v26 & 2) != 0) )
        goto LABEL_26;
      v28 = (v26 & 8) != 0;
      LOBYTE(v26) = (v26 & 4) != 0;
      LOBYTE(v25) = (*(_BYTE *)(v10 + 8) & 2) != 0;
      Handle = v27;
      LOBYTE(v27) = *(_BYTE *)(v10 + 8) & 1;
      ConnectionPerf = CscDclMRxEvict(a1, (int)v27, v25, v26, v28, v10 + 16, Handle, (__int64)v12, (__int64)(v12 + 4));
      goto LABEL_48;
    case 7:
      v106 = 0;
      v109 = 0;
      v21 = *(unsigned __int16 *)(v10 + 8);
      v22 = *(unsigned __int16 *)(v10 + 10);
      v23 = v22 + v21 + 12;
      if ( v23 >= (int)v21 + 12 )
      {
        if ( v23 > (unsigned int)v11 )
        {
LABEL_36:
          ItemInformationExtended = -1073741585;
          goto LABEL_349;
        }
        WORD1(v106) = *(_WORD *)(v10 + 8);
        LOWORD(v106) = v21;
        *((_QWORD *)&v106 + 1) = v10 + 12;
        WORD1(v109) = v22;
        LOWORD(v109) = v22;
        *((_QWORD *)&v109 + 1) = v10 + 12 + v21;
        HashData = CscDclMRxRenameItem(*((_QWORD *)&v109 + 1), &v106, &v109);
LABEL_38:
        ItemInformationExtended = HashData;
        goto LABEL_349;
      }
      goto LABEL_39;
  }
  if ( LODWORD(v111[0]) != 8 )
  {
LABEL_26:
    ItemInformationExtended = -1073741811;
    goto LABEL_349;
  }
  LOWORD(v110[0]) = (v13 - 4) >> 4;
  v107[0] = 0;
  v109 = 0;
  v17 = *(unsigned __int16 *)(v10 + 8);
  if ( (_WORD)v17 )
  {
    if ( (unsigned int)v11 < v17 + 10 )
      goto LABEL_26;
    *((_QWORD *)&v109 + 1) = v10 + 10;
    WORD1(v109) = v17;
    LOWORD(v109) = v17;
  }
  SecurityInformation = CscDclMRxQuerySecurityInformation(
                          a1,
                          (unsigned __int64)&v109 & -(__int64)((_WORD)v109 != 0),
                          (unsigned int)v110,
                          (unsigned int)v107,
                          (unsigned __int64)(v12 + 2) & -(__int64)(LOWORD(v110[0]) != 0));
  ItemInformationExtended = SecurityInformation;
  if ( SecurityInformation == -2147483643 )
  {
    *v12 = v110[0];
LABEL_30:
    v19 = 2;
LABEL_31:
    v105 = v19;
    goto LABEL_349;
  }
  if ( SecurityInformation >= 0 )
  {
    v20 = v107[0];
    *v12 = v107[0];
    v105 = 16 * v20 + 4;
  }
LABEL_349:
  if ( v108 )
    CscDclpSynchronizeMRx(a1, 0);
  KeLeaveCriticalRegion();
  CscDclpCleanupFsctlContext(v111, (unsigned __int64)&v105 & -(__int64)(v105 != 0));
  *(_QWORD *)(a1 + 184) = v105;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      60,
      WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids,
      (unsigned int)ItemInformationExtended);
  return (unsigned int)ItemInformationExtended;
}

```

## disassembly

```asm
0x14007ae70  push    rbx
0x14007ae72  push    rsi
0x14007ae73  push    rdi
0x14007ae74  push    r12
0x14007ae76  push    r13
0x14007ae78  push    r14
0x14007ae7a  push    r15
0x14007ae7c  sub     rsp, 130h
0x14007ae83  mov     rax, cs:__security_cookie
0x14007ae8a  xor     rax, rsp
0x14007ae8d  mov     [rsp+168h+var_40], rax
0x14007ae95  mov     sil, r9b
0x14007ae98  mov     dil, r8b
0x14007ae9b  mov     bl, dl
0x14007ae9d  mov     r13, rcx
0x14007aea0  mov     qword ptr [rsp+168h+var_F8], rcx
0x14007aea5  xor     edx, edx; Val
0x14007aea7  lea     r8d, [rdx+60h]; Size
0x14007aeab  lea     rcx, [rsp+168h+var_D8]; void *
0x14007aeb3  call    memset
0x14007aeb8  xor     r14d, r14d
0x14007aebb  mov     [rsp+168h+var_118], r14d
0x14007aec0  mov     [rsp+168h+var_FC], r14b
0x14007aec5  call    cs:__imp_KeEnterCriticalRegion
0x14007aecc  nop     dword ptr [rax+rax+00h]
0x14007aed1  mov     byte ptr [rsp+168h+var_148], sil; char
0x14007aed6  mov     r9b, dil
0x14007aed9  mov     r8b, bl
0x14007aedc  mov     rdx, r13
0x14007aedf  lea     rcx, [rsp+168h+var_D8]; void *
0x14007aee7  call    CscDclpInitializeFsctlContext
0x14007aeec  mov     ebx, eax
0x14007aeee  test    eax, eax
0x14007aef0  js      loc_14007C50F
0x14007aef6  mov     rdi, [rsp+168h+var_A8]
0x14007aefe  mov     ebx, [rsp+168h+var_A0]
0x14007af05  mov     rsi, [rsp+168h+var_88]
0x14007af0d  mov     r15d, [rsp+168h+var_80]
0x14007af15  mov     [rsp+168h+var_E8], r15d
0x14007af1d  lea     rax, WPP_GLOBAL_Control
0x14007af24  mov     r10, cs:WPP_GLOBAL_Control
0x14007af2b  cmp     r10, rax
0x14007af2e  jz      short loc_14007AF5B
0x14007af30  mov     eax, [r10+2Ch]
0x14007af34  test    al, 20h
0x14007af36  jz      short loc_14007AF5B
0x14007af38  mov     ecx, [rsp+168h+var_D8]
0x14007af3f  call    CscDclpGetFsctlOperationString
0x14007af44  mov     r9, rax
0x14007af47  lea     edx, [r14+3Bh]
0x14007af4b  lea     r8, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids
0x14007af52  mov     rcx, [r10+18h]
0x14007af56  call    WPP_SF_s
0x14007af5b  mov     r12d, 1
0x14007af61  test    [rsp+168h+var_D4], r12b
0x14007af69  jz      short loc_14007AF7B
0x14007af6b  mov     dl, r12b
0x14007af6e  mov     rcx, r13
0x14007af71  call    CscDclpSynchronizeMRx
0x14007af76  mov     [rsp+168h+var_FC], r12b
0x14007af7b  mov     rax, [r13+38h]
0x14007af7f  test    dword ptr [rax+9Ch], 1000080h
0x14007af89  jz      short loc_14007AF95
0x14007af8b  mov     ebx, 0C00000C4h
0x14007af90  jmp     loc_14007C50F
0x14007af95  mov     ecx, [rsp+168h+var_D8]
0x14007af9c  cmp     ecx, 26h ; '&'
0x14007af9f  jg      loc_14007BAF1
0x14007afa5  jz      loc_14007BAC7
0x14007afab  cmp     ecx, 13h
0x14007afae  jg      loc_14007B68E
0x14007afb4  jz      loc_14007B667
0x14007afba  cmp     ecx, 9
0x14007afbd  jg      loc_14007B342
0x14007afc3  jz      loc_14007B2FC
0x14007afc9  test    ecx, ecx
0x14007afcb  jz      loc_14007B2E2
0x14007afd1  sub     ecx, r12d
0x14007afd4  jz      loc_14007B2B6
0x14007afda  sub     ecx, r12d
0x14007afdd  jz      loc_14007B290
0x14007afe3  sub     ecx, r12d
0x14007afe6  jz      loc_14007B245
0x14007afec  sub     ecx, r12d
0x14007afef  jz      loc_14007B220
0x14007aff5  sub     ecx, r12d
0x14007aff8  jz      loc_14007B213
0x14007affe  sub     ecx, r12d
0x14007b001  jz      loc_14007B15F
0x14007b007  sub     ecx, r12d
0x14007b00a  jz      loc_14007B0DE
0x14007b010  cmp     ecx, r12d
0x14007b013  jnz     short loc_14007B04F
0x14007b015  lea     ecx, [r15-4]
0x14007b019  shr     ecx, 4
0x14007b01c  mov     word ptr [rsp+168h+var_E8], cx
0x14007b024  mov     [rsp+168h+var_100], r14w
0x14007b02a  xorps   xmm0, xmm0
0x14007b02d  movups  [rsp+168h+var_F8], xmm0
0x14007b032  lea     rax, [rsi+4]
0x14007b036  neg     cx
0x14007b039  sbb     r8, r8
0x14007b03c  and     r8, rax
0x14007b03f  movzx   ecx, word ptr [rdi+8]
0x14007b043  test    cx, cx
0x14007b046  jz      short loc_14007B06C
0x14007b048  lea     eax, [rcx+0Ah]
0x14007b04b  cmp     ebx, eax
0x14007b04d  jnb     short loc_14007B059
0x14007b04f  mov     ebx, 0C000000Dh
0x14007b054  jmp     loc_14007C50F
0x14007b059  lea     rax, [rdi+0Ah]
0x14007b05d  mov     qword ptr [rsp+168h+var_F8+8], rax
0x14007b062  mov     word ptr [rsp+168h+var_F8+2], cx
0x14007b067  mov     word ptr [rsp+168h+var_F8], cx
0x14007b06c  movzx   eax, word ptr [rsp+168h+var_F8]
0x14007b071  neg     ax
0x14007b074  sbb     rdx, rdx
0x14007b077  lea     rax, [rsp+168h+var_F8]
0x14007b07c  and     rdx, rax
0x14007b07f  mov     [rsp+168h+var_148], r8
0x14007b084  lea     r9, [rsp+168h+var_100]
0x14007b089  lea     r8, [rsp+168h+var_E8]
0x14007b091  mov     rcx, r13
0x14007b094  call    CscDclMRxQuerySecurityInformation
0x14007b099  mov     ebx, eax
0x14007b09b  cmp     eax, 80000005h
0x14007b0a0  jnz     short loc_14007B0BD
0x14007b0a2  movzx   eax, word ptr [rsp+168h+var_E8]
0x14007b0aa  mov     [rsi], ax
0x14007b0ad  mov     r15d, 2
0x14007b0b3  mov     [rsp+168h+var_118], r15d
0x14007b0b8  jmp     loc_14007C50F
0x14007b0bd  test    eax, eax
0x14007b0bf  js      loc_14007C50F
0x14007b0c5  movzx   eax, [rsp+168h+var_100]
0x14007b0ca  mov     [rsi], ax
0x14007b0cd  mov     ecx, eax
0x14007b0cf  shl     ecx, 4
0x14007b0d2  add     ecx, 4
0x14007b0d5  mov     [rsp+168h+var_118], ecx
0x14007b0d9  jmp     loc_14007C50F
0x14007b0de  xorps   xmm0, xmm0
0x14007b0e1  movups  [rsp+168h+var_110], xmm0
0x14007b0e6  xorps   xmm1, xmm1
0x14007b0e9  movups  [rsp+168h+var_F8], xmm1
0x14007b0ee  movzx   ecx, word ptr [rdi+8]
0x14007b0f2  lea     eax, [rcx+0Ch]
0x14007b0f5  cmp     eax, 0Ch
0x14007b0f8  jb      short loc_14007B155
0x14007b0fa  movzx   edx, word ptr [rdi+0Ah]
0x14007b0fe  lea     r8d, [rdx+rax]
0x14007b102  cmp     r8d, eax
0x14007b105  jb      short loc_14007B155
0x14007b107  cmp     r8d, ebx
0x14007b10a  jbe     short loc_14007B116
0x14007b10c  mov     ebx, 0C00000EFh
0x14007b111  jmp     loc_14007C50F
0x14007b116  mov     word ptr [rsp+168h+var_110+2], cx
0x14007b11b  mov     word ptr [rsp+168h+var_110], cx
0x14007b120  lea     rax, [rdi+0Ch]
0x14007b124  mov     qword ptr [rsp+168h+var_110+8], rax
0x14007b129  mov     word ptr [rsp+168h+var_F8+2], dx
0x14007b12e  mov     word ptr [rsp+168h+var_F8], dx
0x14007b133  add     rdi, 0Ch
0x14007b137  add     rcx, rdi
0x14007b13a  mov     qword ptr [rsp+168h+var_F8+8], rcx
0x14007b13f  lea     r8, [rsp+168h+var_F8]
0x14007b144  lea     rdx, [rsp+168h+var_110]
0x14007b149  call    CscDclMRxRenameItem
0x14007b14e  mov     ebx, eax
0x14007b150  jmp     loc_14007C50F
0x14007b155  mov     ebx, 0C0000095h
0x14007b15a  jmp     loc_14007C50F
0x14007b15f  mov     rcx, [r13+28h]; Irp
0x14007b163  call    cs:__imp_IoIs32bitProcess
0x14007b16a  nop     dword ptr [rax+rax+00h]
0x14007b16f  test    al, al
0x14007b171  jz      short loc_14007B182
0x14007b173  cmp     ebx, 18h
0x14007b176  jnz     loc_14007B04F
0x14007b17c  movsxd  rdx, dword ptr [rdi+10h]
0x14007b180  jmp     short loc_14007B18F
0x14007b182  cmp     ebx, 20h ; ' '
0x14007b185  jnz     loc_14007B04F
0x14007b18b  mov     rdx, [rdi+18h]
0x14007b18f  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x14007b193  jz      loc_14007B04F
0x14007b199  mov     r9b, [rdi+8]
0x14007b19d  mov     cl, r9b
0x14007b1a0  and     cl, r12b
0x14007b1a3  mov     r11b, cl
0x14007b1a6  mov     r8b, r9b
0x14007b1a9  and     r8b, 2
0x14007b1ad  setnz   al
0x14007b1b0  cmp     cl, al
0x14007b1b2  jz      loc_14007B04F
0x14007b1b8  lea     rax, [rsi+8]
0x14007b1bc  lea     rcx, [rdi+10h]
0x14007b1c0  mov     r10b, r9b
0x14007b1c3  shr     r10b, 3
0x14007b1c7  and     r10b, r12b
0x14007b1ca  shr     r9b, 2
0x14007b1ce  and     r9b, r12b; int
0x14007b1d1  test    r8b, r8b
0x14007b1d4  setnz   r8b; int
0x14007b1d8  mov     [rsp+168h+var_128], rax; __int64
0x14007b1dd  mov     [rsp+168h+var_130], rsi; __int64
0x14007b1e2  mov     [rsp+168h+Handle], rdx; Handle
0x14007b1e7  mov     [rsp+168h+var_140], rcx; __int64
0x14007b1ec  mov     byte ptr [rsp+168h+var_148], r10b; char
0x14007b1f1  mov     dl, r11b; int
0x14007b1f4  mov     rcx, r13; int
0x14007b1f7  call    CscDclMRxEvict
0x14007b1fc  mov     ebx, eax
0x14007b1fe  test    eax, eax
0x14007b200  js      loc_14007C50F
0x14007b206  mov     [rsp+168h+var_118], 10h
0x14007b20e  jmp     loc_14007C50F
0x14007b213  mov     rcx, r13
0x14007b216  call    CscDclMRxEvictItem
0x14007b21b  jmp     loc_14007B14E
0x14007b220  lea     r9, [rsi+8]
0x14007b224  lea     r8, [rsi+4]
0x14007b228  mov     edx, [rdi+8]
0x14007b22b  mov     rcx, r13
0x14007b22e  call    CscDclMRxDeleteItem
0x14007b233  mov     [rsi], eax
0x14007b235  mov     [rsp+168h+var_118], 0Ch
0x14007b23d  mov     ebx, r14d
0x14007b240  jmp     loc_14007C50F
0x14007b245  mov     eax, [rdi+8]
0x14007b248  test    eax, 0FFFFFFF8h
0x14007b24d  jnz     loc_14007B04F
0x14007b253  mov     rdx, r14
0x14007b256  mov     r8, r14
0x14007b259  mov     r9, r14
0x14007b25c  test    r12b, al
0x14007b25f  jz      short loc_14007B265
0x14007b261  lea     rdx, [rdi+0Ch]
0x14007b265  mov     r15d, 2
0x14007b26b  test    r15b, al
0x14007b26e  jz      short loc_14007B274
0x14007b270  lea     r8, [rdi+14h]
0x14007b274  mov     r12d, 4
0x14007b27a  test    r12b, al
0x14007b27d  jz      short loc_14007B283
0x14007b27f  lea     r9, [rdi+20h]
0x14007b283  mov     rcx, r13
0x14007b286  call    CscDclMRxSetItemInformation
0x14007b28b  jmp     loc_14007B14E
0x14007b290  lea     r8, [rsi+38h]
0x14007b294  mov     rdx, rsi
0x14007b297  mov     rcx, r13
0x14007b29a  call    CscDclMRxQueryItemInformation
0x14007b29f  mov     ebx, eax
0x14007b2a1  test    eax, eax
0x14007b2a3  js      loc_14007C50F
0x14007b2a9  mov     [rsp+168h+var_118], 88h
0x14007b2b1  jmp     loc_14007C50F
0x14007b2b6  mov     [rsp+168h+var_148], rsi
0x14007b2bb  mov     r9b, [rdi+10h]
0x14007b2bf  mov     r8d, [rdi+0Ch]
0x14007b2c3  mov     edx, [rdi+8]
0x14007b2c6  mov     rcx, r13
0x14007b2c9  call    CscDclMRxTransition
0x14007b2ce  mov     ebx, eax
0x14007b2d0  test    eax, eax
0x14007b2d2  js      loc_14007C50F
0x14007b2d8  mov     [rsp+168h+var_118], r12d
0x14007b2dd  jmp     loc_14007C50F
0x14007b2e2  mov     rdx, rsi
0x14007b2e5  mov     rcx, r13
0x14007b2e8  call    CscDclMRxQueryHandleInformation
0x14007b2ed  mov     ebx, eax
0x14007b2ef  mov     [rsp+168h+var_118], 14h
0x14007b2f7  jmp     loc_14007C50F
0x14007b2fc  mov     edx, [rdi+0Ch]; SecurityDescriptorLength
0x14007b2ff  cmp     edx, 44h ; 'D'
0x14007b302  ja      loc_14007B04F
0x14007b308  lea     eax, [rdx+10h]
0x14007b30b  cmp     ebx, eax
0x14007b30d  jb      loc_14007B04F
0x14007b313  xor     r8d, r8d; RequiredInformation
0x14007b316  lea     rcx, [rdi+10h]; SecurityDescriptorInput
0x14007b31a  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x14007b321  nop     dword ptr [rax+rax+00h]
0x14007b326  test    al, al
0x14007b328  jz      loc_14007B04F
0x14007b32e  lea     r8, [rdi+10h]
0x14007b332  mov     edx, [rdi+8]
0x14007b335  mov     rcx, r13
0x14007b338  call    CscDclMRxSetSecurityInformation
0x14007b33d  jmp     loc_14007B14E
0x14007b342  sub     ecx, 0Ah
0x14007b345  jz      loc_14007B5FB
0x14007b34b  sub     ecx, r12d
0x14007b34e  jz      loc_14007B5E3
0x14007b354  sub     ecx, r12d
0x14007b357  jz      loc_14007B588
  ... truncated ...
```
