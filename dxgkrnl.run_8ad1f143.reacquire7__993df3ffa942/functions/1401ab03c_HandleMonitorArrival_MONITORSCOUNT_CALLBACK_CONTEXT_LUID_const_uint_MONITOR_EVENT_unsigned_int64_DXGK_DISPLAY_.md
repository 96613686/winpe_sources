# HandleMonitorArrival(MONITORSCOUNT_CALLBACK_CONTEXT *,_LUID const &,uint,MONITOR_EVENT,unsigned __int64,_DXGK_DISPLAY_SCENARIO_CONTEXT *)

- ea: `0x1401ab03c`
- end: `0x1401ac237`
- name: `?HandleMonitorArrival@@YAJPEAUMONITORSCOUNT_CALLBACK_CONTEXT@@AEBU_LUID@@IW4MONITOR_EVENT@@_KPEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@@Z`
- size: `4603`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140226e1c`

## callees

- `0x140012540`
- `0x14001b9c0`
- `0x140044dd4`
- `0x1400456cc`
- `0x140188d6c`
- `0x1401892e8`
- `0x14018b56c`
- `0x140191d84`
- `0x140193a8c`
- `0x1401ab03c`
- `0x1401bcacc`
- `0x1401d8c74`
- `0x140225a70`
- `0x140227bc4`
- `0x140227cb0`
- `0x1402e7b40`
- `0x1402e8b88`
- `0x14034dfb8`
- `0x14034dffc`
- `0x14034e178`
- `0x14034e510`
- `0x14034e830`
- `0x14034e8b0`
- `0x14034f704`
- `0x1403e400c`
- `0x1403ef5b0`
- `0x1403fdf3c`

## import_xrefs

- `watchdog!WdLogSingleEntry2` at `0x1401ab71d`
- `watchdog!WdLogSingleEntry2` at `0x1401ab785`
- `watchdog!WdLogSingleEntry2` at `0x1401ab9cd`
- `watchdog!WdLogSingleEntry2` at `0x1401aba01`
- `watchdog!WdLogSingleEntry2` at `0x1401abb8e`
- `watchdog!WdLogSingleEntry2` at `0x1401abf40`
- `watchdog!WdLogSingleEntry2` at `0x1401abfa8`
- `watchdog!WdLogSingleEntry2` at `0x1401ac03d`
- `watchdog!WdLogSingleEntry2` at `0x1401ac0a5`
- `watchdog!WdLogSingleEntry2` at `0x1401ab71d`
- `watchdog!WdLogSingleEntry2` at `0x1401ab785`
- `watchdog!WdLogSingleEntry2` at `0x1401ab9cd`
- `watchdog!WdLogSingleEntry2` at `0x1401aba01`
- `watchdog!WdLogSingleEntry2` at `0x1401abb8e`
- `watchdog!WdLogSingleEntry2` at `0x1401abf40`
- `watchdog!WdLogSingleEntry2` at `0x1401abfa8`
- `watchdog!WdLogSingleEntry2` at `0x1401ac03d`
- `watchdog!WdLogSingleEntry2` at `0x1401ac0a5`
- `watchdog!WdLogSingleEntry0` at `0x1401ab210`
- `watchdog!WdLogSingleEntry0` at `0x1401ab3da`
- `watchdog!WdLogSingleEntry0` at `0x1401ab4cd`
- `watchdog!WdLogSingleEntry0` at `0x1401ab52d`
- `watchdog!WdLogSingleEntry0` at `0x1401ab8e3`
- `watchdog!WdLogSingleEntry0` at `0x1401aba6e`
- `watchdog!WdLogSingleEntry0` at `0x1401abc13`
- `watchdog!WdLogSingleEntry0` at `0x1401abc99`
- `watchdog!WdLogSingleEntry0` at `0x1401abe82`
- `watchdog!WdLogSingleEntry0` at `0x1401ab210`
- `watchdog!WdLogSingleEntry0` at `0x1401ab3da`
- `watchdog!WdLogSingleEntry0` at `0x1401ab4cd`
- `watchdog!WdLogSingleEntry0` at `0x1401ab52d`
- `watchdog!WdLogSingleEntry0` at `0x1401ab8e3`
- `watchdog!WdLogSingleEntry0` at `0x1401aba6e`
- `watchdog!WdLogSingleEntry0` at `0x1401abc13`
- `watchdog!WdLogSingleEntry0` at `0x1401abc99`
- `watchdog!WdLogSingleEntry0` at `0x1401abe82`
- `watchdog!WdLogSingleEntry5` at `0x1401ab0cb`
- `watchdog!WdLogSingleEntry5` at `0x1401ab17c`
- `watchdog!WdLogSingleEntry5` at `0x1401ab2ff`
- `watchdog!WdLogSingleEntry5` at `0x1401ab5c0`
- `watchdog!WdLogSingleEntry5` at `0x1401ab670`
- `watchdog!WdLogSingleEntry5` at `0x1401ab6bb`
- `watchdog!WdLogSingleEntry5` at `0x1401ac176`
- `watchdog!WdLogSingleEntry5` at `0x1401ac20a`
- `watchdog!WdLogSingleEntry5` at `0x1401ab0cb`
- `watchdog!WdLogSingleEntry5` at `0x1401ab17c`
- `watchdog!WdLogSingleEntry5` at `0x1401ab2ff`
- `watchdog!WdLogSingleEntry5` at `0x1401ab5c0`
- `watchdog!WdLogSingleEntry5` at `0x1401ab670`
- `watchdog!WdLogSingleEntry5` at `0x1401ab6bb`
- `watchdog!WdLogSingleEntry5` at `0x1401ac176`
- `watchdog!WdLogSingleEntry5` at `0x1401ac20a`
- `watchdog!WdLogSingleEntry1` at `0x1401abb2a`
- `watchdog!WdLogSingleEntry1` at `0x1401abb2a`

## string_xrefs

- `0x1401abe93`: `io_pNewTopologySet->GetPathsCount() == 2`
- `0x1401ab18d`: `Unable to get copy of most recent topology. (NtStatus = 0x%I64x, i_AdapterLuid = 0x%I64x%08I64x, i_IncomingTargetId = 0x%I64x, i_MonitorEvent = 0x%I64x)`
- `0x1401ab0dc`: `Unable to invalidate path-persistence invariance. (NtStatus = 0x%I64x, i_AdapterLuid = 0x%I64x%08I64x, i_IncomingTargetId = 0x%I64x, i_MonitorEvent = 0x%I64x)`
- `0x1401ab310`: `Unable to query monitor type - assumed DMM_VMT_UNINITIALIZED. (_NtStatus = 0x%I64x, i_AdapterLuid = 0x%I64x%08I64x, i_IncomingTargetId = 0x%I64x, i_MonitorEvent = 0x%I64x)`
- `0x1401ab737`: `Unable to create copy of io_pNewTopologySet - will keep current topology. (NtStatus = 0x%I64x, io_pNewTopologySet = 0x%I64x)`
- `0x1401ab5d1`: `Unable to persist most recent topology. (NtStatus = 0x%I64x, i_AdapterLuid = 0x%I64x%08I64x, i_IncomingTargetId = 0x%I64x, i_MonitorEvent = 0x%I64x)`
- `0x1401ab79f`: `Unable to persist current topology - default topology will be created later. (NtStatus = 0x%I64x, io_pNewTopologySet = 0x%I64x)`
- `0x1401aba7f`: `IncomingTargetSupportsVirtualTopologies`
- `0x1401aba1b`: `Unable to persist current topology - default topology will be created later. (NtStatus = 0x%I64x, &OriginalTopologySet = 0x%I64x)`
- `0x1401abba8`: `Unable to persist current topology - default topology will be created later. (NtStatus = 0x%I64x, &OriginalTopologySet = 0x%I64x)`
- `0x1401abfc2`: `Unable to persist current topology - default topology will be created later. (NtStatus = 0x%I64x, &OriginalTopologySet = 0x%I64x)`
- `0x1401ac0bf`: `Unable to persist current topology - default topology will be created later. (NtStatus = 0x%I64x, &OriginalTopologySet = 0x%I64x)`
- `0x1401abc24`: `NumPathsToReserve == 2`
- `0x1401abb3b`: `Unable to allocate 0x%I64x paths for newly added monitor topology - will keep current topology. (NumPathsToReserve = 0x%I64u)`
- `0x1401abcaa`: `io_pNewTopologySet->GetPathDescriptor(0)->pDevMode == NULL`
- `0x1401abf50`: `Unable to functionalize topology with newly added monitor - will keep current topology. (NtStatus = 0x%I64x, io_pNewTopologySet->GetPathsModality() = 0x%I64x)`
- `0x1401ac187`: `Unable to invalidate path-persistence/emergency-monitors invariance.(NtStatus = 0x%I64x, i_AdapterLuid = 0x%I64x%08I64x, i_IncomingTargetId = 0x%I64x, i_MonitorEvent = 0x%I64x)`
- `0x1401ac04d`: `Unable to persist the newly created topology for newly added monitor - will keep current topology. (NtStatus = 0x%I64x, io_pNewTopologySet->GetPathsModality() = 0x%I64x)`

## pseudocode

```c
__int64 __fastcall HandleMonitorArrival(
        __int64 a1,
        const struct _LUID *a2,
        unsigned int a3,
        int a4,
        __int64 a5,
        struct _DXGK_DISPLAY_SCENARIO_CONTEXT *a6)
{
  __int64 v7; // rbx
  __int64 v9; // rdi
  __int64 result; // rax
  int v11; // eax
  LONG *p_HighPart; // r12
  __int64 v13; // r15
  __int64 v14; // rbx
  struct CCD_BTL *v15; // rax
  int v16; // eax
  __int64 v17; // r15
  unsigned int v18; // ebx
  int v19; // eax
  __int64 v20; // r15
  __int64 v21; // rbx
  enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY v22; // ecx
  unsigned int v23; // ebx
  enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY v24; // r15d
  unsigned int v25; // edx
  int Persisted; // eax
  int v27; // ebx
  __int64 v28; // r15
  unsigned int i; // r12d
  unsigned __int16 v30; // cx
  const struct D3DKMT_PATHMODALITY_DESCRIPTOR *PathDescriptor; // rax
  int v32; // eax
  __int64 v33; // rdx
  int v34; // eax
  __int64 v35; // r12
  int v36; // eax
  __int64 v37; // r15
  __int64 v38; // r9
  __int64 v39; // r8
  __int64 v40; // rdx
  __int64 v41; // rdx
  unsigned int v42; // ebx
  unsigned int j; // ebx
  unsigned __int8 v44; // r15
  unsigned int v45; // ebx
  struct _LUID *v46; // rax
  bool v47; // r12
  unsigned __int16 v48; // bx
  const struct D3DKMT_PATHMODALITY_DESCRIPTOR *v49; // rax
  unsigned __int16 v50; // cx
  int v51; // eax
  __int64 v52; // r15
  unsigned int k; // ebx
  unsigned __int16 v54; // cx
  __int16 v55; // r15
  unsigned __int16 v56; // r15
  int v57; // eax
  __int64 v58; // r12
  unsigned int v59; // ebx
  char v60; // al
  bool v61; // zf
  enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY v62; // r12d
  const struct D3DKMT_PATHMODALITY_DESCRIPTOR *v63; // rax
  __int64 v64; // rdx
  _OWORD *v65; // rcx
  __int128 v66; // xmm1
  __int128 v67; // xmm0
  __int128 v68; // xmm1
  __int128 v69; // xmm0
  __int128 v70; // xmm1
  __int128 v71; // xmm0
  __int128 v72; // xmm1
  __int128 v73; // xmm0
  __int128 v74; // xmm1
  __int64 v75; // rax
  const struct D3DKMT_PATHMODALITY_DESCRIPTOR *v76; // rcx
  __int64 v77; // rdx
  _OWORD *v78; // rax
  __int128 v79; // xmm1
  __int128 v80; // xmm0
  __int128 v81; // xmm1
  __int128 v82; // xmm0
  __int128 v83; // xmm1
  __int128 v84; // xmm0
  __int128 v85; // xmm1
  __int128 v86; // xmm0
  __int128 v87; // xmm1
  __int64 v88; // rax
  const struct D3DKMT_PATHMODALITY_DESCRIPTOR *v89; // rax
  struct _LUID v90; // rcx
  const struct D3DKMT_PATHMODALITY_DESCRIPTOR *v91; // r15
  bool v92; // cf
  char v93; // dl
  const struct D3DKMT_PATHMODALITY_DESCRIPTOR *v94; // rax
  __int64 v95; // rcx
  int v96; // eax
  __int64 v97; // r15
  int v98; // eax
  __int64 v99; // r12
  int v100; // eax
  __int64 v101; // r15
  int v102; // eax
  __int64 v103; // r12
  struct CCD_BTL *v104; // rax
  int v105; // eax
  __int64 v106; // rbx
  __int64 v107; // rsi
  unsigned __int8 v108; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 v109; // [rsp+51h] [rbp-AFh] BYREF
  unsigned __int8 v110; // [rsp+52h] [rbp-AEh] BYREF
  unsigned __int8 v111; // [rsp+53h] [rbp-ADh] BYREF
  unsigned __int8 v112; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int8 v113; // [rsp+55h] [rbp-ABh]
  unsigned __int8 v114; // [rsp+56h] [rbp-AAh]
  unsigned int v115; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v116; // [rsp+60h] [rbp-A0h]
  enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY LaptopSpecialCaseFlags; // [rsp+68h] [rbp-98h] BYREF
  enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY v118; // [rsp+6Ch] [rbp-94h]
  __int64 v119; // [rsp+70h] [rbp-90h]
  enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY v120; // [rsp+78h] [rbp-88h] BYREF
  LONG *v121; // [rsp+80h] [rbp-80h]
  unsigned int UnusedVidpnSourceId; // [rsp+88h] [rbp-78h]
  _BYTE v123[64]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v124; // [rsp+D0h] [rbp-30h]
  int v125; // [rsp+DCh] [rbp-24h]
  int v126; // [rsp+E0h] [rbp-20h]
  _BYTE v127[64]; // [rsp+100h] [rbp+0h] BYREF
  struct D3DKMT_GETPATHSMODALITY *v128; // [rsp+140h] [rbp+40h]
  _BYTE v129[368]; // [rsp+170h] [rbp+70h] BYREF

  v7 = a4;
  v9 = a3;
  if ( a5 == 4 )
  {
    *(_BYTE *)(a1 + 26) = 0;
    return 0;
  }
  v11 = DisplayConfigHandleMonitorInvalidation(3u, (struct MONITORSCOUNT_CALLBACK_CONTEXT *)a1, a6);
  v119 = v9;
  v116 = v7;
  p_HighPart = &a2->HighPart;
  v13 = v7;
  v121 = &a2->HighPart;
  if ( v11 >= 0 )
  {
    v121 = &a2->HighPart;
  }
  else
  {
    v14 = v11;
    WdLogSingleEntry5(2, v11, *p_HighPart);
    WdLogGlobalForLineNumber = 3561;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Unable to invalidate path-persistence invariance. (NtStatus = 0x%I64x, i_AdapterLuid = 0x%I64x%08I64"
                     "x, i_IncomingTargetId = 0x%I64x, i_MonitorEvent = 0x%I64x)",
      v14,
      *p_HighPart,
      a2->LowPart,
      v9,
      v13);
  }
  if ( *(_BYTE *)(a1 + 24) )
  {
    CCD_TOPOLOGY::CCD_TOPOLOGY((CCD_TOPOLOGY *)v123, 8u, 0);
    v15 = CCD_BTL::Global();
    v16 = CCD_TOPOLOGY::CopyRenewScope((CCD_TOPOLOGY *)v123, (struct CCD_BTL *)((char *)v15 + 8));
    v17 = v16;
    if ( v16 < 0 )
    {
      WdLogSingleEntry5(2, v16, *p_HighPart);
      WdLogGlobalForLineNumber = 3586;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Unable to get copy of most recent topology. (NtStatus = 0x%I64x, i_AdapterLuid = 0x%I64x%08I64x, i"
                       "_IncomingTargetId = 0x%I64x, i_MonitorEvent = 0x%I64x)",
        v17,
        *p_HighPart,
        a2->LowPart,
        v119,
        v116);
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))DxgkLogCodePointPacket)(
        62,
        0,
        (unsigned int)v17,
        0,
        *a2);
LABEL_10:
      *(_BYTE *)(a1 + 31) = 1;
LABEL_11:
      *(_BYTE *)(a1 + 26) = 1;
      CCD_TOPOLOGY::~CCD_TOPOLOGY((CCD_TOPOLOGY *)v123);
      return 0;
    }
    v18 = *((_DWORD *)DXGGLOBAL::GetGlobal() + 474);
    if ( v18 > 1 )
    {
      WdLogSingleEntry0(3);
      WdLogGlobalForLineNumber = 3614;
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))DxgkLogCodePointPacket)(82, v18, 1, 0, *a2);
      goto LABEL_10;
    }
    if ( !v124 || !*(_WORD *)(v124 + 20) )
    {
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))DxgkLogCodePointPacket)(62, 1, 0, 0, *a2);
      goto LABEL_11;
    }
    v115 = 0;
    LaptopSpecialCaseFlags = D3DKMDT_VOT_HD15;
    v120 = D3DKMDT_VOT_HD15;
    v109 = 0;
    v108 = 1;
    v110 = 0;
    v111 = 0;
    v112 = 0;
    v19 = QueryMonitorType(
            a2,
            a3,
            (enum _DMM_VIDPN_MONITOR_TYPE *)&v115,
            &LaptopSpecialCaseFlags,
            &v120,
            &v109,
            &v108,
            &v110,
            &v111,
            &v112);
    if ( v19 >= 0 )
    {
      v23 = v115;
      v22 = LaptopSpecialCaseFlags;
      v114 = v109;
      v113 = v108;
      v108 = v111;
      v109 = v112;
    }
    else
    {
      v20 = v116;
      v21 = v19;
      WdLogSingleEntry5(2, v19, a2->HighPart);
      WdLogGlobalForLineNumber = 3663;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Unable to query monitor type - assumed DMM_VMT_UNINITIALIZED. (_NtStatus = 0x%I64x, i_AdapterLuid "
                       "= 0x%I64x%08I64x, i_IncomingTargetId = 0x%I64x, i_MonitorEvent = 0x%I64x)",
        v21,
        a2->HighPart,
        a2->LowPart,
        v119,
        v20);
      v22 = D3DKMDT_VOT_UNINITIALIZED;
      v114 = 0;
      v23 = 0;
      v113 = 0;
      v110 = 0;
      v108 = 0;
      v109 = 0;
    }
    v118 = v22;
    LaptopSpecialCaseFlags = GetLaptopSpecialCaseFlags(
                               (const struct CCD_TOPOLOGY *)v123,
                               a2,
                               a3,
                               v22,
                               (const struct MONITORSCOUNT_CALLBACK_CONTEXT *)a1);
    v24 = LaptopSpecialCaseFlags;
    if ( LaptopSpecialCaseFlags )
    {
      if ( LaptopSpecialCaseFlags == D3DKMDT_VOT_SVIDEO )
      {
        *(_BYTE *)(a1 + 27) = 1;
      }
      else if ( LaptopSpecialCaseFlags == D3DKMDT_VOT_D_JPN )
      {
        *(_BYTE *)(a1 + 28) = 1;
      }
      else
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 3695;
        DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"Invalid laptop special case flags!", 3695, 0, 0, 0, 0);
      }
    }
    CCD_TOPOLOGY::CCD_TOPOLOGY((CCD_TOPOLOGY *)v127, 8u, 0);
    if ( v24 && v23 == 1 )
      v25 = v24 | 0x86;
    else
      v25 = 143;
    Persisted = CCD_TOPOLOGY::RetrievePersisted((CCD_TOPOLOGY *)v127, v25, 0);
    v27 = Persisted;
    if ( Persisted < 0 )
    {
      LODWORD(v28) = Persisted;
    }
    else
    {
      LODWORD(v28) = -1073741823;
      if ( v120 == D3DKMDT_VOT_MIRACAST )
      {
        for ( i = 0; ; ++i )
        {
          v30 = v128 ? *((_WORD *)v128 + 10) : 0;
          if ( i >= v30 )
            break;
          PathDescriptor = CCD_TOPOLOGY::GetPathDescriptor((CCD_TOPOLOGY *)v127, i);
          if ( *((_DWORD *)PathDescriptor + 7) == a3
            && *((_DWORD *)PathDescriptor + 4) == a2->LowPart
            && *((_DWORD *)PathDescriptor + 5) == *v121 )
          {
            goto LABEL_41;
          }
        }
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 3745;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Miracast monitor was not active in CCD database so adding as new monitor",
          3745,
          0,
          0,
          0,
          0);
        v27 = -1073741823;
LABEL_41:
        p_HighPart = v121;
      }
      if ( IsValidCloneConfiguration(v128) )
      {
        LODWORD(v28) = v27;
        if ( v27 >= 0 )
        {
          v32 = CCD_TOPOLOGY::Persist((CCD_TOPOLOGY *)v127, 0);
          v28 = v32;
          if ( v32 < 0 )
          {
            WdLogSingleEntry5(2, v32, *p_HighPart);
            WdLogGlobalForLineNumber = 3773;
            DxgkLogInternalTriageEvent(
              0,
              0x40000,
              -1,
              (unsigned int)L"Unable to persist most recent topology. (NtStatus = 0x%I64x, i_AdapterLuid = 0x%I64x%08I64x,"
                             " i_IncomingTargetId = 0x%I64x, i_MonitorEvent = 0x%I64x)",
              v28,
              *p_HighPart,
              a2->LowPart,
              v119,
              v116);
            ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))DxgkLogCodePointPacket)(
              62,
              2,
              (unsigned int)v28,
              0,
              *a2);
          }
          *(_DWORD *)(a1 + 32) |= 0x40u;
        }
      }
      else
      {
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 3755;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"The persisted topology requires cross-adapter clone support however it does not support Virtual "
                         "Mode. Therefore the new monitor will be added in extend mode.",
          3755,
          0,
          0,
          0,
          0);
      }
    }
    CCD_TOPOLOGY::~CCD_TOPOLOGY((CCD_TOPOLOGY *)v127);
    if ( (int)v28 >= 0 )
    {
      v13 = v116;
      WdLogSingleEntry5(4, *p_HighPart, a2->LowPart);
      WdLogGlobalForLineNumber = 3794;
LABEL_144:
      CCD_TOPOLOGY::~CCD_TOPOLOGY((CCD_TOPOLOGY *)v123);
      p_HighPart = v121;
      goto LABEL_145;
    }
    if ( (_DWORD)v28 == -1073741266 )
    {
      v13 = v116;
      *(_BYTE *)(a1 + 26) = 1;
      *(_BYTE *)(a1 + 31) = 1;
      goto LABEL_144;
    }
    v33 = (int)v28;
    v13 = v116;
    WdLogSingleEntry5(4, v33, *p_HighPart);
    WdLogGlobalForLineNumber = 3803;
    if ( a6 )
      *((_BYTE *)a6 + 45) = 1;
    *(_BYTE *)(a1 + 26) = 1;
    *(_BYTE *)(a1 + 31) = 1;
    CCD_TOPOLOGY::CCD_TOPOLOGY((CCD_TOPOLOGY *)v127, 8u, 0);
    v34 = CCD_TOPOLOGY::CopyInheritScope((CCD_TOPOLOGY *)v127, (const struct CCD_TOPOLOGY *)v123);
    v35 = v34;
    if ( v34 < 0 )
    {
      WdLogSingleEntry2(2, v34, v123);
      WdLogGlobalForLineNumber = 3824;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Unable to create copy of io_pNewTopologySet - will keep current topology. (NtStatus = 0x%I64x, io_"
                       "pNewTopologySet = 0x%I64x)",
        v35,
        (__int64)v123,
        0,
        0,
        0);
      v36 = CCD_TOPOLOGY::Persist((CCD_TOPOLOGY *)v123, 0);
      v37 = v36;
      if ( v36 < 0 )
      {
        WdLogSingleEntry2(2, v36, v123);
        WdLogGlobalForLineNumber = 3834;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Unable to persist current topology - default topology will be created later. (NtStatus = 0x%I64x"
                         ", io_pNewTopologySet = 0x%I64x)",
          v37,
          (__int64)v123,
          0,
          0,
          0);
      }
      v38 = (unsigned int)v37;
      v39 = (unsigned int)v35;
      v40 = 3;
      goto LABEL_58;
    }
    v115 = 0;
    if ( (int)CCD_TOPOLOGY::FindPathDescriptorByTarget((CCD_TOPOLOGY *)v123, a2, a3, &v115) >= 0 )
    {
      v42 = v115;
      if ( v115 < *(unsigned __int16 *)(v124 + 20) )
      {
        CCD_TOPOLOGY::ClearModalitySetId((CCD_TOPOLOGY *)v123);
        for ( j = v42 + 1; j < *(unsigned __int16 *)(v124 + 20); ++j )
          CCD_TOPOLOGY::SwapPathsDescriptors((CCD_TOPOLOGY *)v123, j - 1, j);
        --*(_WORD *)(v124 + 20);
      }
    }
    if ( !v124 || !*(_WORD *)(v124 + 20) )
    {
      v104 = CCD_BTL::Global();
      CCD_TOPOLOGY::Clear((struct CCD_BTL *)((char *)v104 + 8));
      goto LABEL_142;
    }
    v44 = v108;
    v47 = 0;
    if ( !v108 && !v113 )
    {
      if ( v114
        || (v45 = *((_DWORD *)CCD_TOPOLOGY::GetPathDescriptor((CCD_TOPOLOGY *)v123, 0) + 7),
            v46 = (struct _LUID *)CCD_TOPOLOGY::GetPathDescriptor((CCD_TOPOLOGY *)v123, 0),
            DxgkIsPortraitFirstTarget(v46[2], v45)) )
      {
        v47 = 1;
      }
    }
    LOBYTE(v41) = v47;
    v48 = DetermineDefaultTopology((unsigned int)LaptopSpecialCaseFlags, v41);
    v115 = v48;
    if ( v48 == 3 )
    {
      if ( v44 && *((_BYTE *)CCD_TOPOLOGY::GetPathDescriptor((CCD_TOPOLOGY *)v123, 0) + 129)
        || a2->LowPart == *((_DWORD *)CCD_TOPOLOGY::GetPathDescriptor((CCD_TOPOLOGY *)v123, 0) + 4)
        && (v49 = CCD_TOPOLOGY::GetPathDescriptor((CCD_TOPOLOGY *)v123, 0), *v121 == *((_DWORD *)v49 + 5)) )
      {
        if ( !v44 )
        {
          UnusedVidpnSourceId = *((_DWORD *)CCD_TOPOLOGY::GetPathDescriptor((CCD_TOPOLOGY *)v123, 0) + 6);
LABEL_102:
          if ( v124 )
            v55 = *(_WORD *)(v124 + 20);
          else
            v55 = 0;
          v56 = v55 + 1;
          if ( CCD_TOPOLOGY::Reserve((CCD_TOPOLOGY *)v123, v56) >= v56 )
          {
            v59 = v56 - 1;
            if ( v108 || (v60 = LaptopSpecialCaseFlags, LaptopSpecialCaseFlags == D3DKMDT_VOT_HD15) )
            {
              v62 = v118;
            }
            else
            {
              if ( v56 != 2 )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 4043;
                DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"NumPathsToReserve == 2", 4043, 0, 0, 0, 0);
                v60 = LaptopSpecialCaseFlags;
              }
              v61 = !v47;
              v62 = v118;
              if ( v61 )
                v59 = ((unsigned __int8)~v60 >> 3) & 1;
              else
                v59 = IsInternalVideoOutput(v118) == 0;
              if ( *((_QWORD *)CCD_TOPOLOGY::GetPathDescriptor((CCD_TOPOLOGY *)v123, 0) + 31) )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 4075;
                DxgkLogInternalTriageEvent(
                  0,
                  262146,
                  -1,
                  (unsigned int)L"io_pNewTopologySet->GetPathDescriptor(0)->pDevMode == NULL",
                  4075,
                  0,
                  0,
                  0,
                  0);
              }
              v63 = CCD_TOPOLOGY::GetPathDescriptor((CCD_TOPOLOGY *)v123, 0);
              v64 = 2;
              v65 = v129;
              do
              {
                v66 = *((_OWORD *)v63 + 1);
                *v65 = *(_OWORD *)v63;
                v67 = *((_OWORD *)v63 + 2);
                v65[1] = v66;
                v68 = *((_OWORD *)v63 + 3);
                v65[2] = v67;
                v69 = *((_OWORD *)v63 + 4);
                v65[3] = v68;
                v70 = *((_OWORD *)v63 + 5);
                v65[4] = v69;
                v71 = *((_OWORD *)v63 + 6);
                v65[5] = v70;
                v72 = *((_OWORD *)v63 + 7);
                v63 = (const struct D3DKMT_PATHMODALITY_DESCRIPTOR *)((char *)v63 + 128);
                v65[6] = v71;
                v65[7] = v72;
                v65 += 8;
                --v64;
              }
              while ( v64 );
              v73 = *(_OWORD *)v63;
              v74 = *((_OWORD *)v63 + 1);
              v75 = *((_QWORD *)v63 + 4);
              *v65 = v73;
              v65[1] = v74;
              *((_QWORD *)v65 + 4) = v75;
              v76 = CCD_TOPOLOGY::GetPathDescriptor((CCD_TOPOLOGY *)v123, 1u);
              v77 = 2;
              v78 = v129;
              do
              {
                v79 = v78[1];
                *(_OWORD *)v76 = *v78;
                v80 = v78[2];
                *((_OWORD *)v76 + 1) = v79;
                v81 = v78[3];
                *((_OWORD *)v76 + 2) = v80;
                v82 = v78[4];
                *((_OWORD *)v76 + 3) = v81;
                v83 = v78[5];
                *((_OWORD *)v76 + 4) = v82;
                v84 = v78[6];
                *((_OWORD *)v76 + 5) = v83;
                v85 = v78[7];
                v78 += 8;
                *((_OWORD *)v76 + 6) = v84;
                *((_OWORD *)v76 + 7) = v85;
                v76 = (const struct D3DKMT_PATHMODALITY_DESCRIPTOR *)((char *)v76 + 128);
                --v77;
              }
              while ( v77 );
              v86 = *v78;
              v87 = v78[1];
              v88 = *((_QWORD *)v78 + 4);
              *(_OWORD *)v76 = v86;
              *((_OWORD *)v76 + 1) = v87;
              *((_QWORD *)v76 + 4) = v88;
              *(_QWORD *)CCD_TOPOLOGY::GetPathDescriptor((CCD_TOPOLOGY *)v123, 1 - v59) = 0xCF00000000000LL;
            }
            v89 = CCD_TOPOLOGY::GetPathDescriptor((CCD_TOPOLOGY *)v123, v59);
            v90 = *a2;
            v91 = v89;
            v92 = v109 != 0;
            v109 = -v109;
            *((struct _LUID *)v89 + 2) = v90;
            v93 = v92 ? 4 : 0;
            v92 = v108 != 0;
            v108 = -v108;
            *((_DWORD *)v89 + 6) = UnusedVidpnSourceId;
            *((_DWORD *)v89 + 7) = a3;
            *((_DWORD *)v89 + 23) = v120;
            *((_DWORD *)v89 + 22) = v62;
            *((_BYTE *)v89 + 129) = v93 | (v92 ? 2 : 0) | (v110 != 0);
            *(_QWORD *)v89 = 0x8F00000000000LL;
            ++*(_WORD *)(v124 + 20);
            if ( (_WORD)v115 == 3 )
            {
              if ( !v124 || *(_WORD *)(v124 + 20) != 2 )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 4117;
                DxgkLogInternalTriageEvent(
                  0,
                  262146,
                  -1,
                  (unsigned int)L"io_pNewTopologySet->GetPathsCount() == 2",
                  4117,
                  0,
                  0,
                  0,
                  0);
              }
              v94 = CCD_TOPOLOGY::GetPathDescriptor((CCD_TOPOLOGY *)v123, v59 == 0);
              v95 = *((_QWORD *)v94 + 19);
              *(_QWORD *)v91 |= 0x20000uLL;
              *((_QWORD *)v91 + 19) = v95;
              *((_DWORD *)v91 + 46) = *((_DWORD *)v94 + 46);
              *(_QWORD *)v91 |= 0x4000000000000uLL;
            }
            else
            {
              CCD_TOPOLOGY::RegulateCloneGroupIdForNewPath((CCD_TOPOLOGY *)v123, v59);
            }
            v125 = 1;
            v126 = 4;
            v96 = CCD_TOPOLOGY::Functionalize((CCD_TOPOLOGY *)v123, 0, 0);
            v97 = v96;
            if ( v96 >= 0 )
            {
              v100 = CCD_TOPOLOGY::Persist((CCD_TOPOLOGY *)v123, 1u);
              v101 = v100;
              if ( v100 == -1073741266 )
              {
                v38 = 0;
                v39 = 3221226030LL;
                v40 = 7;
              }
              else
              {
                if ( v100 >= 0 )
                {
                  *(_BYTE *)(a1 + 31) = 0;
                  goto LABEL_59;
                }
                WdLogSingleEntry2(2, v100, v124);
                WdLogGlobalForLineNumber = 4196;
                DxgkLogInternalTriageEvent(
                  0,
                  0x40000,
                  -1,
                  (unsigned int)L"Unable to persist the newly created topology for newly added monitor - will keep current"
                                 " topology. (NtStatus = 0x%I64x, io_pNewTopologySet->GetPathsModality() = 0x%I64x)",
                  v101,
                  v124,
                  0,
                  0,
                  0);
                v102 = CCD_TOPOLOGY::Persist((CCD_TOPOLOGY *)v127, 0);
                v103 = v102;
                if ( v102 < 0 )
                {
                  WdLogSingleEntry2(2, v102, v127);
                  WdLogGlobalForLineNumber = 4206;
                  DxgkLogInternalTriageEvent(
                    0,
                    0x40000,
                    -1,
                    (unsigned int)L"Unable to persist current topology - default topology will be created later. (NtStatus"
                                   " = 0x%I64x, &OriginalTopologySet = 0x%I64x)",
                    v103,
                    (__int64)v127,
                    0,
                    0,
                    0);
                }
                v38 = (unsigned int)v103;
                v39 = (unsigned int)v101;
                v40 = 8;
              }
            }
            else
            {
              WdLogSingleEntry2(2, v96, v124);
              WdLogGlobalForLineNumber = 4140;
              DxgkLogInternalTriageEvent(
                0,
                0x40000,
                -1,
                (unsigned int)L"Unable to functionalize topology with newly added monitor - will keep current topology. (N"
                               "tStatus = 0x%I64x, io_pNewTopologySet->GetPathsModality() = 0x%I64x)",
                v97,
                v124,
                0,
                0,
                0);
              v98 = CCD_TOPOLOGY::Persist((CCD_TOPOLOGY *)v127, 0);
              v99 = v98;
              if ( v98 < 0 )
              {
                WdLogSingleEntry2(2, v98, v127);
                WdLogGlobalForLineNumber = 4150;
                DxgkLogInternalTriageEvent(
                  0,
                  0x40000,
                  -1,
                  (unsigned int)L"Unable to persist current topology - default topology will be created later. (NtStatus ="
                                 " 0x%I64x, &OriginalTopologySet = 0x%I64x)",
                  v99,
                  (__int64)v127,
                  0,
                  0,
                  0);
              }
              v38 = (unsigned int)v99;
              v39 = (unsigned int)v97;
              v40 = 6;
            }
          }
          else
          {
            WdLogSingleEntry1(6, v56);
            WdLogGlobalForLineNumber = 4009;
            DxgkLogInternalTriageEvent(
              0,
              262145,
              -1,
              (unsigned int)L"Unable to allocate 0x%I64x paths for newly added monitor topology - will keep current topolo"
                             "gy. (NumPathsToReserve = 0x%I64u)",
              v56,
              0,
              0,
              0,
              0);
            v57 = CCD_TOPOLOGY::Persist((CCD_TOPOLOGY *)v127, 0);
            v58 = v57;
            if ( v57 < 0 )
            {
              WdLogSingleEntry2(2, v57, v127);
              WdLogGlobalForLineNumber = 4019;
              DxgkLogInternalTriageEvent(
                0,
                0x40000,
                -1,
                (unsigned int)L"Unable to persist current topology - default topology will be created later. (NtStatus = 0"
                               "x%I64x, &OriginalTopologySet = 0x%I64x)",
                v58,
                (__int64)v127,
                0,
                0,
                0);
            }
            v39 = v56;
            v38 = (unsigned int)v58;
            v40 = 5;
          }
LABEL_58:
          ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))DxgkLogCodePointPacket)(62, v40, v39, v38, *a2);
LABEL_59:
          v13 = v116;
LABEL_142:
          CCD_TOPOLOGY::~CCD_TOPOLOGY((CCD_TOPOLOGY *)v127);
          goto LABEL_144;
        }
      }
      else
      {
        v48 = 4;
        v115 = 4;
      }
    }
    else if ( (unsigned __int16)(v48 - 4) > 1u )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 3903;
      DxgkLogInternalTriageEvent(
        0,
        262146,
        -1,
        (unsigned int)L"(defaultTopology == MultiScreenDefaultShellTopology::Cloned) || (defaultTopology == MultiScreenDef"
                       "aultShellTopology::Conjoined) || (defaultTopology == MultiScreenDefaultShellTopology::Disjoint)",
        3903,
        0,
        0,
        0,
        0);
    }
    UnusedVidpnSourceId = GetUnusedVidpnSourceId((struct CCD_TOPOLOGY *)v123, a2);
    if ( UnusedVidpnSourceId == 16 )
    {
      if ( v124 )
        v50 = *(_WORD *)(v124 + 20);
      else
        v50 = 0;
      WdLogSingleEntry2(4, v50, 16);
      WdLogGlobalForLineNumber = 3953;
      v51 = CCD_TOPOLOGY::Persist((CCD_TOPOLOGY *)v127, 0);
      v52 = v51;
      if ( v51 < 0 )
      {
        WdLogSingleEntry2(2, v51, v127);
        WdLogGlobalForLineNumber = 3963;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Unable to persist current topology - default topology will be created later. (NtStatus = 0x%I64x"
                         ", &OriginalTopologySet = 0x%I64x)",
          v52,
          (__int64)v127,
          0,
          0,
          0);
      }
      v38 = 0;
      v39 = (unsigned int)v52;
      v40 = 4;
      goto LABEL_58;
    }
    if ( v48 == 3 )
    {
      if ( !v44 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 3980;
        DxgkLogInternalTriageEvent(
          0,
          262146,
          -1,
          (unsigned int)L"IncomingTargetSupportsVirtualTopologies",
          3980,
          0,
          0,
          0,
          0);
      }
      for ( k = 0; ; ++k )
      {
        v54 = v124 ? *(_WORD *)(v124 + 20) : 0;
        if ( k >= v54 )
          break;
        if ( !*((_BYTE *)CCD_TOPOLOGY::GetPathDescriptor((CCD_TOPOLOGY *)v123, k) + 129) )
        {
          LOWORD(v115) = 4;
          goto LABEL_102;
        }
      }
    }
    goto LABEL_102;
  }
LABEL_145:
  v105 = DisplayConfigHandleMonitorInvalidation(1u, (struct MONITORSCOUNT_CALLBACK_CONTEXT *)a1, a6);
  v106 = v105;
  if ( v105 < 0 )
  {
    v107 = v119;
    WdLogSingleEntry5(2, v105, *p_HighPart);
    WdLogGlobalForLineNumber = 4262;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Unable to invalidate path-persistence/emergency-monitors invariance.(NtStatus = 0x%I64x, i_AdapterLu"
                     "id = 0x%I64x%08I64x, i_IncomingTargetId = 0x%I64x, i_MonitorEvent = 0x%I64x)",
      v106,
      *p_HighPart,
      a2->LowPart,
      v107,
      v13);
    LODWORD(v106) = 0;
  }
  WdLogSingleEntry5(4, *p_HighPart, a2->LowPart);
  result = (unsigned int)v106;
  WdLogGlobalForLineNumber = 4272;
  return result;
}

```

## disassembly

```asm
0x1401ab03c  mov     [rsp-8+arg_10], r8d
0x1401ab041  push    rbp
0x1401ab042  push    rbx
0x1401ab043  push    rsi
0x1401ab044  push    rdi
0x1401ab045  push    r12
0x1401ab047  push    r13
0x1401ab049  push    r14
0x1401ab04b  push    r15
0x1401ab04d  lea     rbp, [rsp-1A8h]
0x1401ab055  sub     rsp, 2A8h
0x1401ab05c  cmp     [rbp+1E0h+arg_20], 4
0x1401ab064  mov     r14, rdx
0x1401ab067  movsxd  rbx, r9d
0x1401ab06a  mov     r13, rcx
0x1401ab06d  mov     edi, r8d
0x1401ab070  jnz     short loc_1401AB07F
0x1401ab072  xor     edi, edi
0x1401ab074  mov     [rcx+1Ah], dil
0x1401ab078  xor     eax, eax
0x1401ab07a  jmp     loc_1401AC222
0x1401ab07f  mov     r8, [rbp+1E0h+arg_28]; struct _DXGK_DISPLAY_SCENARIO_CONTEXT *
0x1401ab086  mov     rdx, r13; struct MONITORSCOUNT_CALLBACK_CONTEXT *
0x1401ab089  mov     ecx, 3; unsigned __int64
0x1401ab08e  call    ?DisplayConfigHandleMonitorInvalidation@@YAJ_KPEAUMONITORSCOUNT_CALLBACK_CONTEXT@@PEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@@Z; DisplayConfigHandleMonitorInvalidation(unsigned __int64,MONITORSCOUNT_CALLBACK_CONTEXT *,_DXGK_DISPLAY_SCENARIO_CONTEXT *)
0x1401ab093  mov     rsi, rdi
0x1401ab096  mov     [rsp+2E0h+var_270], rdi
0x1401ab09b  xor     edi, edi
0x1401ab09d  mov     [rsp+2E0h+var_280], rbx
0x1401ab0a2  lea     r12, [r14+4]
0x1401ab0a6  mov     r15, rbx
0x1401ab0a9  mov     [rbp+1E0h+var_260], r12
0x1401ab0ad  test    eax, eax
0x1401ab0af  jns     short loc_1401AB11A
0x1401ab0b1  mov     r9d, [r14]
0x1401ab0b4  lea     ecx, [rdi+2]
0x1401ab0b7  movsxd  r8, dword ptr [r12]
0x1401ab0bb  movsxd  rbx, eax
0x1401ab0be  mov     rdx, rbx
0x1401ab0c1  mov     [rsp+2E0h+var_2B8], r15
0x1401ab0c6  mov     [rsp+2E0h+var_2C0], rsi
0x1401ab0cb  call    cs:__imp_WdLogSingleEntry5
0x1401ab0d2  nop     dword ptr [rax+rax+00h]
0x1401ab0d7  mov     [rsp+2E0h+var_2A0], r15
0x1401ab0dc  lea     r9, aUnableToInvali; "Unable to invalidate path-persistence i"...
0x1401ab0e3  mov     cs:WdLogGlobalForLineNumber, 0DE9h
0x1401ab0ed  or      r8d, 0FFFFFFFFh
0x1401ab0f1  movsxd  rcx, dword ptr [r12]
0x1401ab0f5  mov     edx, 40000h
0x1401ab0fa  mov     eax, [r14]
0x1401ab0fd  mov     [rsp+2E0h+var_2A8], rsi
0x1401ab102  mov     [rsp+2E0h+var_2B0], rax
0x1401ab107  mov     [rsp+2E0h+var_2B8], rcx
0x1401ab10c  xor     ecx, ecx
0x1401ab10e  mov     [rsp+2E0h+var_2C0], rbx
0x1401ab113  call    DxgkLogInternalTriageEvent
0x1401ab118  jmp     short loc_1401AB11E
0x1401ab11a  mov     [rbp+1E0h+var_260], r12
0x1401ab11e  mov     esi, 1
0x1401ab123  cmp     [r13+18h], dil
0x1401ab127  jz      loc_1401AC13B
0x1401ab12d  xor     r8d, r8d; unsigned __int16
0x1401ab130  lea     edx, [rsi+7]; unsigned __int16
0x1401ab133  lea     rcx, [rbp+1E0h+var_250]; this
0x1401ab137  call    ??0CCD_TOPOLOGY@@QEAA@GG@Z; CCD_TOPOLOGY::CCD_TOPOLOGY(ushort,ushort)
0x1401ab13c  call    ?Global@CCD_BTL@@SAAEAV1@XZ; CCD_BTL::Global(void)
0x1401ab141  lea     rcx, [rbp+1E0h+var_250]; this
0x1401ab145  lea     rdx, [rax+8]; struct CCD_TOPOLOGY *
0x1401ab149  call    ?CopyRenewScope@CCD_TOPOLOGY@@QEAAJAEBV1@@Z; CCD_TOPOLOGY::CopyRenewScope(CCD_TOPOLOGY const &)
0x1401ab14e  movsxd  r15, eax
0x1401ab151  test    eax, eax
0x1401ab153  jns     loc_1401AB1FC
0x1401ab159  mov     rdi, [rsp+2E0h+var_280]
0x1401ab15e  mov     rdx, r15
0x1401ab161  mov     rsi, [rsp+2E0h+var_270]
0x1401ab166  mov     ecx, 2
0x1401ab16b  mov     r9d, [r14]
0x1401ab16e  movsxd  r8, dword ptr [r12]
0x1401ab172  mov     [rsp+2E0h+var_2B8], rdi
0x1401ab177  mov     [rsp+2E0h+var_2C0], rsi
0x1401ab17c  call    cs:__imp_WdLogSingleEntry5
0x1401ab183  nop     dword ptr [rax+rax+00h]
0x1401ab188  mov     [rsp+2E0h+var_2A0], rdi
0x1401ab18d  lea     r9, aUnableToGetCop; "Unable to get copy of most recent topol"...
0x1401ab194  mov     cs:WdLogGlobalForLineNumber, 0E02h
0x1401ab19e  or      r8d, 0FFFFFFFFh
0x1401ab1a2  mov     ecx, [r14]
0x1401ab1a5  mov     edx, 40000h
0x1401ab1aa  movsxd  rax, dword ptr [r12]
0x1401ab1ae  mov     [rsp+2E0h+var_2A8], rsi
0x1401ab1b3  mov     [rsp+2E0h+var_2B0], rcx
0x1401ab1b8  xor     ecx, ecx
0x1401ab1ba  mov     [rsp+2E0h+var_2B8], rax
0x1401ab1bf  mov     [rsp+2E0h+var_2C0], r15
0x1401ab1c4  call    DxgkLogInternalTriageEvent
0x1401ab1c9  mov     rax, [r14]
0x1401ab1cc  xor     edx, edx
0x1401ab1ce  xor     r9d, r9d
0x1401ab1d1  mov     [rsp+2E0h+var_2C0], rax
0x1401ab1d6  mov     r8d, r15d
0x1401ab1d9  lea     ecx, [rdx+3Eh]
0x1401ab1dc  call    ?DxgkLogCodePointPacket@@YAXW4_DXGK_DIAG_CODE_POINT_TYPE@@IIIU_LUID@@@Z; DxgkLogCodePointPacket(_DXGK_DIAG_CODE_POINT_TYPE,uint,uint,uint,_LUID)
0x1401ab1e1  mov     esi, 1
0x1401ab1e6  mov     [r13+1Fh], sil
0x1401ab1ea  lea     rcx, [rbp+1E0h+var_250]; this
0x1401ab1ee  mov     [r13+1Ah], sil
0x1401ab1f2  call    ??1CCD_TOPOLOGY@@QEAA@XZ; CCD_TOPOLOGY::~CCD_TOPOLOGY(void)
0x1401ab1f7  jmp     loc_1401AB078
0x1401ab1fc  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1401ab201  mov     ebx, [rax+768h]
0x1401ab207  cmp     ebx, esi
0x1401ab209  jbe     short loc_1401AB241
0x1401ab20b  mov     ecx, 3
0x1401ab210  call    cs:__imp_WdLogSingleEntry0
0x1401ab217  nop     dword ptr [rax+rax+00h]
0x1401ab21c  xor     r9d, r9d
0x1401ab21f  mov     cs:WdLogGlobalForLineNumber, 0E1Eh
0x1401ab229  mov     rax, [r14]
0x1401ab22c  mov     r8d, esi
0x1401ab22f  mov     edx, ebx
0x1401ab231  mov     [rsp+2E0h+var_2C0], rax
0x1401ab236  lea     ecx, [r9+52h]
0x1401ab23a  call    ?DxgkLogCodePointPacket@@YAXW4_DXGK_DIAG_CODE_POINT_TYPE@@IIIU_LUID@@@Z; DxgkLogCodePointPacket(_DXGK_DIAG_CODE_POINT_TYPE,uint,uint,uint,_LUID)
0x1401ab23f  jmp     short loc_1401AB1E6
0x1401ab241  mov     rax, [rbp+1E0h+var_210]
0x1401ab245  test    rax, rax
0x1401ab248  jz      loc_1401AC1C7
0x1401ab24e  cmp     [rax+14h], di
0x1401ab252  jz      loc_1401AC1C7
0x1401ab258  mov     edx, [rbp+1E0h+arg_10]; unsigned int
0x1401ab25e  lea     rax, [rsp+2E0h+var_28C]
0x1401ab263  mov     [rsp+2E0h+var_298], rax; unsigned __int8 *
0x1401ab268  lea     r9, [rsp+2E0h+var_278]; enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *
0x1401ab26d  lea     rax, [rsp+2E0h+var_28D]
0x1401ab272  mov     [rsp+2E0h+var_288], edi
0x1401ab276  mov     [rsp+2E0h+var_2A0], rax; unsigned __int8 *
0x1401ab27b  lea     r8, [rsp+2E0h+var_288]; enum _DMM_VIDPN_MONITOR_TYPE *
0x1401ab280  lea     rax, [rsp+2E0h+var_28E]
0x1401ab285  mov     [rsp+2E0h+var_278], edi
0x1401ab289  mov     [rsp+2E0h+var_2A8], rax; unsigned __int8 *
0x1401ab28e  mov     rcx, r14; struct _LUID *
0x1401ab291  lea     rax, [rsp+2E0h+var_290]
0x1401ab296  mov     [rsp+2E0h+var_268], edi
0x1401ab29a  mov     [rsp+2E0h+var_2B0], rax; unsigned __int8 *
0x1401ab29f  lea     rax, [rsp+2E0h+var_28F]
0x1401ab2a4  mov     [rsp+2E0h+var_2B8], rax; unsigned __int8 *
0x1401ab2a9  lea     rax, [rsp+2E0h+var_268]
0x1401ab2ae  mov     [rsp+2E0h+var_2C0], rax; enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *
0x1401ab2b3  mov     [rsp+2E0h+var_28F], dil
0x1401ab2b8  mov     [rsp+2E0h+var_290], sil
0x1401ab2bd  mov     [rsp+2E0h+var_28E], dil
0x1401ab2c2  mov     [rsp+2E0h+var_28D], dil
0x1401ab2c7  mov     [rsp+2E0h+var_28C], dil
0x1401ab2cc  call    ?QueryMonitorType@@YAJAEBU_LUID@@IPEAW4_DMM_VIDPN_MONITOR_TYPE@@PEAW4_D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY@@2PEAE3333@Z; QueryMonitorType(_LUID const &,uint,_DMM_VIDPN_MONITOR_TYPE *,_D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *,_D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *,uchar *,uchar *,uchar *,uchar *,uchar *)
0x1401ab2d1  test    eax, eax
0x1401ab2d3  jns     loc_1401AB373
0x1401ab2d9  mov     r15, [rsp+2E0h+var_280]
0x1401ab2de  mov     ecx, 2
0x1401ab2e3  mov     r9d, [r14]
0x1401ab2e6  movsxd  r8, dword ptr [r14+4]
0x1401ab2ea  movsxd  rbx, eax
0x1401ab2ed  mov     rax, [rsp+2E0h+var_270]
0x1401ab2f2  mov     rdx, rbx
0x1401ab2f5  mov     [rsp+2E0h+var_2B8], r15
0x1401ab2fa  mov     [rsp+2E0h+var_2C0], rax
0x1401ab2ff  call    cs:__imp_WdLogSingleEntry5
0x1401ab306  nop     dword ptr [rax+rax+00h]
0x1401ab30b  mov     rdx, [rsp+2E0h+var_270]
0x1401ab310  lea     r9, aUnableToQueryM; "Unable to query monitor type - assumed "...
0x1401ab317  mov     [rsp+2E0h+var_2A0], r15
0x1401ab31c  or      r8d, 0FFFFFFFFh
0x1401ab320  mov     [rsp+2E0h+var_2A8], rdx
0x1401ab325  mov     edx, 40000h
0x1401ab32a  mov     cs:WdLogGlobalForLineNumber, 0E4Fh
0x1401ab334  movsxd  rcx, dword ptr [r14+4]
0x1401ab338  mov     eax, [r14]
0x1401ab33b  mov     [rsp+2E0h+var_2B0], rax
0x1401ab340  mov     [rsp+2E0h+var_2B8], rcx
0x1401ab345  xor     ecx, ecx
0x1401ab347  mov     [rsp+2E0h+var_2C0], rbx
0x1401ab34c  call    DxgkLogInternalTriageEvent
0x1401ab351  mov     ecx, 0FFFFFFFEh
0x1401ab356  mov     [rsp+2E0h+var_28A], dil
0x1401ab35b  mov     ebx, edi
0x1401ab35d  mov     [rsp+2E0h+var_28B], dil
0x1401ab362  mov     [rsp+2E0h+var_28E], dil
0x1401ab367  mov     [rsp+2E0h+var_290], dil
0x1401ab36c  mov     [rsp+2E0h+var_28F], dil
0x1401ab371  jmp     short loc_1401AB3A3
0x1401ab373  mov     al, [rsp+2E0h+var_28F]
0x1401ab377  mov     dl, [rsp+2E0h+var_28C]
0x1401ab37b  mov     ebx, [rsp+2E0h+var_288]
0x1401ab37f  mov     ecx, [rsp+2E0h+var_278]
0x1401ab383  mov     [rsp+2E0h+var_28A], al
0x1401ab387  mov     al, [rsp+2E0h+var_290]
0x1401ab38b  mov     [rsp+2E0h+var_28B], al
0x1401ab38f  mov     al, [rsp+2E0h+var_28E]
0x1401ab393  mov     [rsp+2E0h+var_28E], al
0x1401ab397  mov     al, [rsp+2E0h+var_28D]
0x1401ab39b  mov     [rsp+2E0h+var_290], al
0x1401ab39f  mov     [rsp+2E0h+var_28F], dl
0x1401ab3a3  mov     r8d, [rbp+1E0h+arg_10]; unsigned int
0x1401ab3aa  mov     r9d, ecx; enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY
0x1401ab3ad  mov     [rsp+2E0h+var_274], ecx
0x1401ab3b1  mov     rdx, r14; struct _LUID *
0x1401ab3b4  lea     rcx, [rbp+1E0h+var_250]; struct CCD_TOPOLOGY *
0x1401ab3b8  mov     [rsp+2E0h+var_2C0], r13; struct MONITORSCOUNT_CALLBACK_CONTEXT *
0x1401ab3bd  call    ?GetLaptopSpecialCaseFlags@@YAIAEBVCCD_TOPOLOGY@@AEBU_LUID@@IW4_D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY@@AEBUMONITORSCOUNT_CALLBACK_CONTEXT@@@Z; GetLaptopSpecialCaseFlags(CCD_TOPOLOGY const &,_LUID const &,uint,_D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY,MONITORSCOUNT_CALLBACK_CONTEXT const &)
0x1401ab3c2  mov     [rsp+2E0h+var_278], eax
0x1401ab3c6  mov     r15d, eax
0x1401ab3c9  mov     ecx, eax
0x1401ab3cb  test    eax, eax
0x1401ab3cd  jz      short loc_1401AB42D
0x1401ab3cf  sub     ecx, esi
0x1401ab3d1  jz      short loc_1401AB429
0x1401ab3d3  cmp     ecx, 7
0x1401ab3d6  jz      short loc_1401AB423
0x1401ab3d8  mov     ecx, esi
0x1401ab3da  call    cs:__imp_WdLogSingleEntry0
0x1401ab3e1  nop     dword ptr [rax+rax+00h]
0x1401ab3e6  mov     [rsp+2E0h+var_2A0], rdi
0x1401ab3eb  lea     r9, aInvalidLaptopS; "Invalid laptop special case flags!"
0x1401ab3f2  mov     [rsp+2E0h+var_2A8], rdi
0x1401ab3f7  mov     eax, 0E6Fh
0x1401ab3fc  mov     [rsp+2E0h+var_2B0], rdi
0x1401ab401  or      r8d, 0FFFFFFFFh
0x1401ab405  mov     [rsp+2E0h+var_2B8], rdi
0x1401ab40a  mov     edx, 40002h
0x1401ab40f  xor     ecx, ecx
0x1401ab411  mov     [rsp+2E0h+var_2C0], rax
0x1401ab416  mov     cs:WdLogGlobalForLineNumber, eax
0x1401ab41c  call    DxgkLogInternalTriageEvent
0x1401ab421  jmp     short loc_1401AB42D
0x1401ab423  mov     [r13+1Ch], sil
0x1401ab427  jmp     short loc_1401AB42D
0x1401ab429  mov     [r13+1Bh], sil
0x1401ab42d  xor     r8d, r8d; unsigned __int16
0x1401ab430  lea     rcx, [rbp+1E0h+var_1E0]; this
0x1401ab434  lea     edx, [r8+8]; unsigned __int16
0x1401ab438  call    ??0CCD_TOPOLOGY@@QEAA@GG@Z; CCD_TOPOLOGY::CCD_TOPOLOGY(ushort,ushort)
0x1401ab43d  test    r15d, r15d
0x1401ab440  jz      short loc_1401AB451
0x1401ab442  cmp     ebx, esi
0x1401ab444  jnz     short loc_1401AB451
0x1401ab446  mov     edx, r15d
0x1401ab449  or      edx, 86h
0x1401ab44f  jmp     short loc_1401AB456
0x1401ab451  mov     edx, 8Fh; unsigned int
0x1401ab456  xor     r8d, r8d; unsigned __int16 *
0x1401ab459  lea     rcx, [rbp+1E0h+var_1E0]; this
0x1401ab45d  call    ?RetrievePersisted@CCD_TOPOLOGY@@QEAAJIPEAG@Z; CCD_TOPOLOGY::RetrievePersisted(uint,ushort *)
0x1401ab462  mov     ebx, eax
0x1401ab464  test    eax, eax
0x1401ab466  js      loc_1401AB638
0x1401ab46c  cmp     [rsp+2E0h+var_268], 0Fh
0x1401ab471  mov     r15d, 0C0000001h
0x1401ab477  jnz     loc_1401AB51B
0x1401ab47d  mov     r12d, edi
0x1401ab480  mov     rax, [rbp+1E0h+var_1A0]
0x1401ab484  test    rax, rax
0x1401ab487  jz      short loc_1401AB48F
0x1401ab489  movzx   ecx, word ptr [rax+14h]
0x1401ab48d  jmp     short loc_1401AB491
0x1401ab48f  mov     ecx, edi
0x1401ab491  movzx   eax, cx
0x1401ab494  cmp     r12d, eax
0x1401ab497  jnb     short loc_1401AB4C8
0x1401ab499  mov     edx, r12d; unsigned int
0x1401ab49c  lea     rcx, [rbp+1E0h+var_1E0]; this
0x1401ab4a0  call    ?GetPathDescriptor@CCD_TOPOLOGY@@QEBAPEBUD3DKMT_PATHMODALITY_DESCRIPTOR@@I@Z; CCD_TOPOLOGY::GetPathDescriptor(uint)
0x1401ab4a5  mov     ecx, [rbp+1E0h+arg_10]
0x1401ab4ab  cmp     [rax+1Ch], ecx
0x1401ab4ae  jnz     short loc_1401AB4C3
0x1401ab4b0  mov     ecx, [r14]
0x1401ab4b3  cmp     [rax+10h], ecx
0x1401ab4b6  jnz     short loc_1401AB4C3
0x1401ab4b8  mov     rcx, [rbp+1E0h+var_260]
0x1401ab4bc  mov     ecx, [rcx]
0x1401ab4be  cmp     [rax+14h], ecx
0x1401ab4c1  jz      short loc_1401AB517
0x1401ab4c3  add     r12d, esi
0x1401ab4c6  jmp     short loc_1401AB480
0x1401ab4c8  mov     ecx, 2
0x1401ab4cd  call    cs:__imp_WdLogSingleEntry0
0x1401ab4d4  nop     dword ptr [rax+rax+00h]
0x1401ab4d9  mov     [rsp+2E0h+var_2A0], rdi
0x1401ab4de  lea     r9, aMiracastMonito; "Miracast monitor was not active in CCD "...
0x1401ab4e5  mov     [rsp+2E0h+var_2A8], rdi
0x1401ab4ea  mov     eax, 0EA1h
0x1401ab4ef  mov     [rsp+2E0h+var_2B0], rdi
0x1401ab4f4  or      r8d, 0FFFFFFFFh
0x1401ab4f8  mov     [rsp+2E0h+var_2B8], rdi
0x1401ab4fd  mov     edx, 40000h
0x1401ab502  xor     ecx, ecx
0x1401ab504  mov     [rsp+2E0h+var_2C0], rax
0x1401ab509  mov     cs:WdLogGlobalForLineNumber, eax
0x1401ab50f  call    DxgkLogInternalTriageEvent
0x1401ab514  mov     ebx, r15d
0x1401ab517  mov     r12, [rbp+1E0h+var_260]
0x1401ab51b  mov     rcx, [rbp+1E0h+var_1A0]; struct D3DKMT_GETPATHSMODALITY *
  ... truncated ...
```
