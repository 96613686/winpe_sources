# VIDPN_MGR::SetTimingsFromVidPn(ulong,_DMM_CLIENT_TYPE,DMMVIDPN *,D3DKMT_VIDPN_SOURCE_MASKS *,_DMM_SET_TIMING_RESULT *,uchar,DXGDEVICE *,COREDEVICEACCESS *)

- ea: `0x1402d4e14`
- end: `0x1402d684e`
- name: `?SetTimingsFromVidPn@VIDPN_MGR@@QEAAJKW4_DMM_CLIENT_TYPE@@PEAVDMMVIDPN@@PEAUD3DKMT_VIDPN_SOURCE_MASKS@@PEAU_DMM_SET_TIMING_RESULT@@EPEAVDXGDEVICE@@PEAVCOREDEVICEACCESS@@@Z`
- size: `6714`
- prototype: ``
- caller_count: `6`
- callee_count: `77`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x1402cabc4`
- `0x1402ce1c8`
- `0x1402ce36c`
- `0x1402cffac`
- `0x1402d3c70`
- `0x1402d4364`

## callees

- `0x1400061bc`
- `0x1400091f0`
- `0x14001b9c0`
- `0x140021e50`
- `0x14002f780`
- `0x1400327f8`
- `0x140032a40`
- `0x140036ee8`
- `0x140039258`
- `0x140039568`
- `0x14003f8c4`
- `0x1400420f8`
- `0x140044dd4`
- `0x14004b034`
- `0x14004b574`
- `0x14004c238`
- `0x14004d4a4`
- `0x14004e0d0`
- `0x140052074`
- `0x1400559a0`
- `0x1400583ac`
- `0x140058ca4`
- `0x140059738`
- `0x14005db60`
- `0x140061d78`
- `0x14006973c`
- `0x140069874`
- `0x1400699a0`
- `0x140069a34`
- `0x14006e484`
- `0x14006e58c`
- `0x14008f9e8`
- `0x140090660`
- `0x140090770`
- `0x1400a0bd0`
- `0x1400a0d00`
- `0x1400a1000`
- `0x14018ee4c`
- `0x140194cd0`
- `0x1401a5580`
- `0x1401bccb4`
- `0x1401d16a0`
- `0x1401d1828`
- `0x1401d56d8`
- `0x1401f4e54`
- `0x1401f6154`
- `0x1401f77ec`
- `0x1401f985c`
- `0x1401fc6f0`
- `0x1402093a4`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1402d6261`
- `ntoskrnl!PsGetCurrentProcess` at `0x1402d6261`
- `ntoskrnl!EtwActivityIdControl` at `0x1402d5991`
- `ntoskrnl!EtwActivityIdControl` at `0x1402d5991`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1402d6270`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1402d6270`
- `watchdog!WdLogSingleEntry4` at `0x1402d57bd`
- `watchdog!WdLogSingleEntry4` at `0x1402d57bd`
- `watchdog!WdLogSingleEntry2` at `0x1402d4f25`
- `watchdog!WdLogSingleEntry2` at `0x1402d4f5b`
- `watchdog!WdLogSingleEntry2` at `0x1402d4f25`
- `watchdog!WdLogSingleEntry2` at `0x1402d4f5b`
- `watchdog!WdLogSingleEntry3` at `0x1402d556e`
- `watchdog!WdLogSingleEntry3` at `0x1402d562b`
- `watchdog!WdLogSingleEntry3` at `0x1402d606d`
- `watchdog!WdLogSingleEntry3` at `0x1402d60c9`
- `watchdog!WdLogSingleEntry3` at `0x1402d63c0`
- `watchdog!WdLogSingleEntry3` at `0x1402d6611`
- `watchdog!WdLogSingleEntry3` at `0x1402d556e`
- `watchdog!WdLogSingleEntry3` at `0x1402d562b`
- `watchdog!WdLogSingleEntry3` at `0x1402d606d`
- `watchdog!WdLogSingleEntry3` at `0x1402d60c9`
- `watchdog!WdLogSingleEntry3` at `0x1402d63c0`
- `watchdog!WdLogSingleEntry3` at `0x1402d6611`
- `watchdog!WdLogSingleEntry0` at `0x1402d4ea3`
- `watchdog!WdLogSingleEntry0` at `0x1402d50dd`
- `watchdog!WdLogSingleEntry0` at `0x1402d5dd3`
- `watchdog!WdLogSingleEntry0` at `0x1402d5e7e`
- `watchdog!WdLogSingleEntry0` at `0x1402d6047`
- `watchdog!WdLogSingleEntry0` at `0x1402d6114`
- `watchdog!WdLogSingleEntry0` at `0x1402d61a3`
- `watchdog!WdLogSingleEntry0` at `0x1402d646a`
- `watchdog!WdLogSingleEntry0` at `0x1402d667c`
- `watchdog!WdLogSingleEntry0` at `0x1402d4ea3`
- `watchdog!WdLogSingleEntry0` at `0x1402d50dd`
- `watchdog!WdLogSingleEntry0` at `0x1402d5dd3`
- `watchdog!WdLogSingleEntry0` at `0x1402d5e7e`
- `watchdog!WdLogSingleEntry0` at `0x1402d6047`
- `watchdog!WdLogSingleEntry0` at `0x1402d6114`
- `watchdog!WdLogSingleEntry0` at `0x1402d61a3`
- `watchdog!WdLogSingleEntry0` at `0x1402d646a`
- `watchdog!WdLogSingleEntry0` at `0x1402d667c`
- `watchdog!DisplayLogSetMonitorPowerStage` at `0x1402d55c7`
- `watchdog!DisplayLogSetMonitorPowerStage` at `0x1402d582c`
- `watchdog!DisplayLogSetMonitorPowerStage` at `0x1402d55c7`
- `watchdog!DisplayLogSetMonitorPowerStage` at `0x1402d582c`
- `watchdog!DisplayScenarioJournalSetSetTimingPathInfo` at `0x1402d4fb6`
- `watchdog!DisplayScenarioJournalSetSetTimingPathInfo` at `0x1402d53fc`
- `watchdog!DisplayScenarioJournalSetSetTimingPathInfo` at `0x1402d56eb`
- `watchdog!DisplayScenarioJournalSetSetTimingPathInfo` at `0x1402d4fb6`
- `watchdog!DisplayScenarioJournalSetSetTimingPathInfo` at `0x1402d53fc`
- `watchdog!DisplayScenarioJournalSetSetTimingPathInfo` at `0x1402d56eb`
- `watchdog!WdLogSingleEntry1` at `0x1402d5028`
- `watchdog!WdLogSingleEntry1` at `0x1402d595b`
- `watchdog!WdLogSingleEntry1` at `0x1402d5028`
- `watchdog!WdLogSingleEntry1` at `0x1402d595b`

## pseudocode

```c
__int64 __fastcall VIDPN_MGR::SetTimingsFromVidPn(
        VIDPN_MGR *a1,
        unsigned int a2,
        unsigned int a3,
        const struct DMMVIDPN *a4,
        struct D3DKMT_VIDPN_SOURCE_MASKS *a5,
        _BYTE *a6,
        unsigned __int8 a7,
        struct DXGDEVICE *a8,
        __int64 a9)
{
  DXGADAPTER *v11; // r14
  int v12; // edi
  unsigned __int64 ClientCommittedVidPnRef; // r13
  __int64 v14; // rax
  __int64 v15; // rbx
  __int64 v16; // rdx
  unsigned __int8 IsLegacyDisplayStateSynchronization; // al
  __int64 v18; // rdx
  int v19; // r9d
  unsigned __int8 v20; // r11
  int v21; // ecx
  unsigned __int8 v22; // dl
  unsigned int v23; // r8d
  unsigned int v24; // r12d
  unsigned int v25; // r15d
  unsigned int v26; // r10d
  unsigned int v27; // edx
  unsigned int v28; // ecx
  int v29; // r9d
  int v30; // eax
  int v31; // eax
  unsigned int v32; // ecx
  int v33; // r9d
  int v34; // eax
  int v35; // eax
  ADAPTER_DISPLAY *v36; // r8
  int v37; // ebx
  unsigned int v38; // r15d
  int v39; // r12d
  __int64 v40; // rcx
  struct DXGDEVICE *VidPnSourceOwner; // r13
  unsigned __int8 v42; // r9
  VIDPN_MGR *v43; // r15
  unsigned int v44; // r15d
  __int64 v45; // rdi
  char *v46; // rbx
  _BYTE *v47; // r14
  __int64 v48; // r15
  char *v49; // r13
  bool v50; // zf
  char *v51; // rax
  __int128 v52; // xmm1
  __int128 v53; // xmm2
  __int64 v54; // xmm3_8
  bool v55; // dl
  int v56; // eax
  ADAPTER_DISPLAY *v57; // rcx
  int v58; // eax
  DMMVIDEOPRESENTTARGET *TargetById; // rax
  _OWORD *v60; // r8
  int v61; // edx
  unsigned __int8 v62; // r15
  _OWORD *v63; // rax
  __int128 v64; // xmm1
  __int128 v65; // xmm2
  __int64 v66; // xmm3_8
  ADAPTER_DISPLAY *v67; // rcx
  int v68; // eax
  int v69; // eax
  _BYTE *v70; // rdi
  UINT v71; // r9d
  char *v72; // rbx
  __int64 v73; // rax
  __int64 v74; // rdx
  char *v75; // rax
  __int128 v76; // xmm1
  __int128 v77; // xmm2
  __int64 v78; // xmm3_8
  __int64 i; // r13
  __int64 v80; // rdi
  int v81; // r12d
  struct DMMVIDEOPRESENTTARGET *v82; // rax
  struct DMMVIDEOPRESENTTARGET *v83; // r15
  int v84; // r12d
  int v85; // r8d
  int v86; // r9d
  int TargetLinkTrainingStatus; // eax
  int v88; // r9d
  int v89; // eax
  int v90; // eax
  DMMVIDPNPRESENTPATH *PathFromTarget; // rax
  ADAPTER_DISPLAY *v92; // rdi
  __int64 v93; // r15
  int v94; // r13d
  int v95; // eax
  const struct _DXGK_DISPLAYMODE_INFO *DisplayModeInfo; // rax
  int v97; // ecx
  DMMVIDPNTOPOLOGY *v98; // rdi
  __int64 v99; // rdx
  __int64 v100; // r8
  int MostImportantVidPnPathTargetsFromSource; // eax
  bool v102; // r12
  unsigned int v103; // r10d
  struct DXGADAPTERALLOCATION *DisplayedPrimaryAllocation; // rax
  struct DXGADAPTERALLOCATION *v105; // rdi
  void *v106; // rax
  ADAPTER_RENDER *v107; // rcx
  int v108; // eax
  __int64 v109; // r9
  __int64 v110; // r8
  unsigned int v111; // edi
  int v112; // eax
  int v113; // r12d
  int v114; // edi
  __int64 CurrentProcess; // rax
  __int64 ProcessImageFileName; // rax
  __int64 j; // r12
  __int64 v118; // r15
  DMMVIDEOPRESENTTARGET *v119; // rax
  DMMVIDEOPRESENTTARGET *v120; // r13
  _BYTE *v121; // rdx
  __int64 v122; // r10
  int v123; // r8d
  int v124; // eax
  __int64 v125; // rcx
  __int64 v126; // r8
  ADAPTER_DISPLAY *v127; // r10
  __int64 v128; // r15
  struct DXGDEVICE *v129; // rdi
  int v130; // r12d
  ADAPTER_DISPLAY *v131; // rcx
  ADAPTER_DISPLAY *v132; // rdi
  const struct _D3DKMT_DISPLAYMODE *v133; // rax
  int v134; // eax
  unsigned int v135; // r13d
  int v136; // eax
  DMMVIDPNTOPOLOGY *v137; // rdi
  __int64 v138; // r8
  int v139; // eax
  __int64 v140; // r10
  __int64 v141; // r9
  __int64 v142; // r8
  unsigned int v143; // ecx
  bool v145[8]; // [rsp+20h] [rbp-E0h]
  bool v146[8]; // [rsp+28h] [rbp-D8h]
  unsigned __int8 v147; // [rsp+70h] [rbp-90h]
  char v148; // [rsp+70h] [rbp-90h]
  char v149; // [rsp+71h] [rbp-8Fh]
  void *Src; // [rsp+78h] [rbp-88h] BYREF
  UINT v151; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v152; // [rsp+84h] [rbp-7Ch] BYREF
  int v153; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v154; // [rsp+8Ch] [rbp-74h]
  __int64 v155; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v156; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v157; // [rsp+A0h] [rbp-60h] BYREF
  int v158; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v159; // [rsp+ACh] [rbp-54h] BYREF
  struct DXGDEVICE *v160; // [rsp+B0h] [rbp-50h]
  VIDPN_MGR *v161; // [rsp+B8h] [rbp-48h]
  __int64 v162; // [rsp+C0h] [rbp-40h]
  char *v163; // [rsp+C8h] [rbp-38h] BYREF
  DMMVIDPNTOPOLOGY *v164; // [rsp+D0h] [rbp-30h]
  __int64 v165; // [rsp+D8h] [rbp-28h] BYREF
  struct _DXGKARG_DESCRIBEALLOCATION v166; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v167; // [rsp+110h] [rbp+10h] BYREF
  __int64 v168; // [rsp+118h] [rbp+18h]
  const struct DMMVIDPN *v169; // [rsp+120h] [rbp+20h] BYREF
  DXGADAPTER *ContainingAdapter; // [rsp+128h] [rbp+28h] BYREF
  int v171; // [rsp+130h] [rbp+30h] BYREF
  __int64 v172; // [rsp+138h] [rbp+38h]
  const struct DMMVIDPN *v173; // [rsp+140h] [rbp+40h]
  unsigned __int64 v174; // [rsp+148h] [rbp+48h] BYREF
  _OWORD v175[2]; // [rsp+150h] [rbp+50h] BYREF
  unsigned int v176[20]; // [rsp+170h] [rbp+70h] BYREF
  GUID ActivityId; // [rsp+1C0h] [rbp+C0h] BYREF

  v160 = a8;
  v168 = a9;
  v173 = a4;
  v154 = a3;
  v159 = a2;
  v161 = a1;
  v157 = (unsigned __int64)a6;
  v152 = 0;
  ContainingAdapter = VIDPN_MGR::GetContainingAdapter(a1);
  v11 = ContainingAdapter;
  if ( !DXGADAPTER::IsCoreResourceExclusiveOwner(ContainingAdapter) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 2510;
  }
  LODWORD(v167) = 0;
  *a6 = 0;
  v151 = 0;
  Src = 0;
  v155 = 0;
  v165 = 0;
  v12 = VIDPN_MGR::BuildSetTimingsPathInfoFromClientVidPn(
          a1,
          (__int64)&v167,
          (__int64)&v151,
          (__int64)&Src,
          (__int64)&v155,
          (__int64)&v165);
  v156 = v12;
  if ( v12 < 0 )
  {
    WdLogSingleEntry2(2, a4);
    WdLogGlobalForLineNumber = 2542;
    goto LABEL_291;
  }
  if ( !v151 )
  {
    WdLogSingleEntry2(3, *((int *)v11 + 104));
    WdLogGlobalForLineNumber = 2560;
    goto LABEL_291;
  }
  if ( *((_DWORD *)a5 + 2) || *((_DWORD *)a5 + 3) || *((_DWORD *)a5 + 6) )
  {
    v149 = 1;
  }
  else
  {
    v149 = 0;
    if ( !*((_DWORD *)a5 + 10) && !*((_DWORD *)a5 + 8) && !*((_DWORD *)a5 + 13) )
    {
      DisplayScenarioJournalSetSetTimingPathInfo(*(_QWORD *)((char *)v11 + 412), 0, 56 * v151);
      v12 = 0;
      goto LABEL_291;
    }
  }
  v158 = 0;
  ClientCommittedVidPnRef = (unsigned __int64)VIDPN_MGR::AcquireLastClientCommittedVidPnRef(a1);
  v174 = ClientCommittedVidPnRef;
  if ( a4 )
    ClientCommittedVidPnRef = (unsigned __int64)a4;
  v14 = 56LL * v151;
  v169 = (const struct DMMVIDPN *)ClientCommittedVidPnRef;
  if ( !is_mul_ok(v151, 0x38u) )
    v14 = -1;
  v163 = (char *)operator new[](v14, 1313891414, 256);
  if ( !v163 )
  {
    WdLogSingleEntry1(6);
    WdLogGlobalForLineNumber = 2622;
    wistd::unique_ptr<unsigned int [0],wistd::default_delete<unsigned int [0]>>::reset(&v163);
    auto_rc<DMMVIDPN const>::reset(&v174, 0);
    v12 = -1073741801;
    goto LABEL_291;
  }
  v164 = (DMMVIDPNTOPOLOGY *)(ClientCommittedVidPnRef + 96);
  memmove(v163, Src, 56LL * v151);
  _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)a1 + 15) + 72LL));
  v15 = *((_QWORD *)a1 + 15);
  v16 = *((_QWORD *)v11 + 407);
  v162 = v15;
  v172 = v16;
  v171 = 0;
  IsLegacyDisplayStateSynchronization = DXGADAPTER::IsLegacyDisplayStateSynchronization(v11);
  v19 = *((_DWORD *)v11 + 783);
  v147 = IsLegacyDisplayStateSynchronization;
  v20 = IsLegacyDisplayStateSynchronization;
  v153 = v19;
  if ( !v18 )
    goto LABEL_60;
  v21 = *(_DWORD *)(v18 + 756);
  v22 = a7;
  if ( a7 )
  {
    if ( !v21 )
      goto LABEL_26;
  }
  else if ( v21 )
  {
LABEL_26:
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 2677;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"(i_DoNotSuspend && pDisplayAdapter->GetRenderCore()->GetSchedulerSuspendSourceMask()) || (!i_DoNotSu"
                     "spend && !pDisplayAdapter->GetRenderCore()->GetSchedulerSuspendSourceMask())",
      2677,
      0,
      0,
      0,
      0);
    v20 = v147;
    v19 = v153;
    v22 = a7;
  }
  if ( v19 >= 2200 )
  {
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v26 = *(_DWORD *)(*((_QWORD *)v11 + 406) + 96LL);
    if ( v22 )
    {
      v27 = 0;
      if ( v26 )
      {
        v28 = 0;
        v29 = *((_DWORD *)a5 + 2) | *((_DWORD *)a5 + 3) | *((_DWORD *)a5 + 6);
        if ( v20 )
        {
          do
          {
            v31 = 1 << v28;
            if ( (v29 & (1 << v28)) != 0 )
            {
              v27 |= v31;
            }
            else if ( (v31 & *(_DWORD *)a5) != 0 )
            {
              v23 |= v31;
            }
            ++v28;
          }
          while ( v28 < v26 );
        }
        else
        {
          do
          {
            v30 = 1 << v28;
            if ( ((1 << v28) & v29) != 0 )
            {
              v27 |= v30;
              v24 |= v30;
            }
            else if ( (v30 & *(_DWORD *)a5) != 0 )
            {
              v23 |= v30;
            }
            ++v28;
          }
          while ( v28 < v26 );
        }
      }
    }
    else
    {
      v27 = 0;
      if ( v26 )
      {
        v32 = 0;
        v33 = *((_DWORD *)a5 + 2) | *((_DWORD *)a5 + 3) | *((_DWORD *)a5 + 6);
        if ( v20 )
        {
          do
          {
            v35 = 1 << v32;
            if ( (v33 & (1 << v32)) != 0 )
            {
              v27 |= v35;
            }
            else if ( (v35 & *(_DWORD *)a5) != 0 )
            {
              v23 |= v35;
              v25 |= v35;
            }
            ++v32;
          }
          while ( v32 < v26 );
        }
        else
        {
          do
          {
            v34 = 1 << v32;
            if ( ((1 << v32) & v33) != 0 )
            {
              v27 |= v34;
              v24 |= v34;
            }
            else if ( (v34 & *(_DWORD *)a5) != 0 )
            {
              v23 |= v34;
              v25 |= v34;
            }
            ++v32;
          }
          while ( v32 < v26 );
        }
      }
    }
    ADAPTER_RENDER::FlushPresentReferencesAndDisableOverlays(*((ADAPTER_RENDER **)v11 + 407), v27, v23, v24, v25);
    *((_DWORD *)a5 + 16) |= v24;
    if ( v25 )
      CVidSchSuspendResume::SetSuspendSourceMask((CVidSchSuspendResume *)&v171, v25);
  }
  else
  {
    ADAPTER_RENDER::FlushScheduler(*((_QWORD *)v11 + 407), 8, 0xFFFFFFFFLL);
  }
  v19 = v153;
LABEL_60:
  v36 = (ADAPTER_DISPLAY *)*((_QWORD *)v11 + 406);
  if ( !*((_DWORD *)v36 + 24) )
    goto LABEL_85;
  v37 = v171;
  v38 = 0;
  do
  {
    v39 = 1 << v38;
    if ( ((*((_DWORD *)a5 + 2) | *((_DWORD *)a5 + 3)) & (1 << v38)) != 0 )
    {
      v40 = *((_QWORD *)v11 + 407);
      if ( v40 && v19 < 2200 )
      {
        ADAPTER_RENDER::FlushScheduler(v40, 8, v38);
        v36 = (ADAPTER_DISPLAY *)*((_QWORD *)v11 + 406);
      }
      if ( v160 && v168 )
      {
        VidPnSourceOwner = ADAPTER_DISPLAY::GetVidPnSourceOwner(v36, v38);
        if ( (unsigned int)Feature_CleanUpDisplayedPrimaryInSetTimings__private_IsEnabledDeviceUsageNoInline() )
        {
          if ( !VidPnSourceOwner )
            goto LABEL_78;
        }
        else if ( !VidPnSourceOwner
               || *((_QWORD *)VidPnSourceOwner + 237) != *(_QWORD *)(*((_QWORD *)VidPnSourceOwner + 2) + 16LL) )
        {
          goto LABEL_78;
        }
        v42 = v37 || a7;
        ADAPTER_DISPLAY::DisablePrimaryOnDevice(*((ADAPTER_DISPLAY **)v11 + 406), VidPnSourceOwner, v38, v42);
      }
    }
LABEL_78:
    if ( ((*((_DWORD *)a5 + 6) | *((_DWORD *)a5 + 2) | *((_DWORD *)a5 + 3)) & v39) != 0
      && *((_QWORD *)v11 + 407)
      && *((_BYTE *)v11 + 3177)
      && v147 )
    {
      ADAPTER_DISPLAY::DisableMPOPlanes(*((ADAPTER_DISPLAY **)v11 + 406), v38, 0);
      *((_DWORD *)a5 + 16) |= v39;
    }
    v36 = (ADAPTER_DISPLAY *)*((_QWORD *)v11 + 406);
    ++v38;
    v19 = v153;
  }
  while ( v38 < *((_DWORD *)v36 + 24) );
  v15 = v162;
  v12 = v156;
  ClientCommittedVidPnRef = (unsigned __int64)v169;
LABEL_85:
  v43 = v161;
  if ( *((_DWORD *)a5 + 5) )
    VIDPN_MGR::RequestPowerStateForTargets(v161, (const struct DMMVIDPN *)ClientCommittedVidPnRef);
  if ( DXGADAPTER::UsingSetTimingsFromVidPn(v11) )
  {
    v148 = 0;
    if ( !v149 )
      goto LABEL_91;
    v44 = v154;
    v175[0] = 0;
    memset(&v166, 0, 40);
    if ( v154 == 4 )
      DisplayLogSetMonitorPowerStage(0, 16, 0, v175);
    *(_QWORD *)&v166.Format = &v152;
    v166.MultisampleMethod.NumQualityLevels = v151;
    v166.hAllocation = (HANDLE)(ClientCommittedVidPnRef & -(__int64)(ClientCommittedVidPnRef != -88));
    v57 = (ADAPTER_DISPLAY *)*((_QWORD *)v11 + 406);
    *(_QWORD *)&v166.RefreshRate.Denominator = Src;
    v58 = ADAPTER_DISPLAY::DdiSetTimingsFromVidPn(v57, (struct _DXGKARG_SETTIMINGSFROMVIDPN *)&v166);
    v12 = v58;
    if ( v58 < 0 )
    {
      WdLogSingleEntry3(2, *((int *)v11 + 104), *((unsigned int *)v11 + 103), v58);
      WdLogGlobalForLineNumber = 2857;
    }
    if ( v151 == 1
      && ((v44 - 1) & 0xFFFFFFFD) == 0
      && (v12 < 0 || (*((_DWORD *)Src + 8) & 0xF000000) == 0xD000000)
      && (*((_DWORD *)Src + 3) & 4) != 0
      && ((v152 & 1) != 0 || (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v11 + 27) + 64LL) + 3652LL) & 3) != 0) )
    {
      TargetById = DMMVIDEOPRESENTTARGETSET::GetTargetById((DMMVIDEOPRESENTTARGETSET *)v15, *(_DWORD *)Src);
      if ( TargetById )
      {
        if ( !DMMVIDEOPRESENTTARGET::IsTargetForceable(TargetById) )
        {
          DisplayScenarioJournalSetSetTimingPathInfo(*(_QWORD *)((char *)v11 + 412), (unsigned int)v12, 56 * v151);
          v60 = v163;
          *((_DWORD *)v163 + 3) = *((_DWORD *)v163 + 3) & 0xFFFFFFF0 | 9;
          v61 = *((_DWORD *)a5 + 1);
          *((_DWORD *)a5 + 6) = v61 & (*((_DWORD *)a5 + 5) ^ *((_DWORD *)a5 + 6));
          *((_DWORD *)a5 + 5) = 0;
          *((_DWORD *)a5 + 20) = v61;
          if ( v12 < 0 )
            v62 = 0;
          else
            v62 = v152 & 1;
          v63 = Src;
          v152 = 0;
          v64 = v60[1];
          v65 = v60[2];
          v66 = *((_QWORD *)v60 + 6);
          *(_OWORD *)Src = *v60;
          v63[1] = v64;
          v63[2] = v65;
          *((_QWORD *)v63 + 6) = v66;
          *(_QWORD *)&v166.Width = 0;
          v166.hAllocation = (HANDLE)(ClientCommittedVidPnRef & -(__int64)(ClientCommittedVidPnRef != -88));
          *(_QWORD *)&v166.Format = &v152;
          v166.MultisampleMethod.NumQualityLevels = v151;
          v166.RefreshRate.Numerator = 0;
          v67 = (ADAPTER_DISPLAY *)*((_QWORD *)v11 + 406);
          *(_QWORD *)&v166.RefreshRate.Denominator = Src;
          v68 = ADAPTER_DISPLAY::DdiSetTimingsFromVidPn(v67, (struct _DXGKARG_SETTIMINGSFROMVIDPN *)&v166);
          v12 = v68;
          if ( v68 < 0 )
          {
            WdLogSingleEntry4(2, *(unsigned int *)Src, *((int *)v11 + 104), *((unsigned int *)v11 + 103), v68);
            WdLogGlobalForLineNumber = 2940;
          }
          DxgkLogCodePointPacket(104, *(unsigned int *)Src, (unsigned int)v12);
          v152 = v152 & 0xFFFFFFFE | ((unsigned __int8)v152 | v62) & 1;
          v44 = v154;
        }
      }
    }
    if ( v44 == 4 )
      DisplayLogSetMonitorPowerStage(0, 2147483664LL, (unsigned int)v12, v175);
  }
  else
  {
    v148 = 1;
    if ( v149 || *((_DWORD *)a5 + 10) )
    {
      v149 = 1;
      v55 = a7 || v171;
      v56 = VIDPN_MGR::CommitVidPnOnAdapter(
              v43,
              v159,
              v154,
              ClientCommittedVidPnRef,
              v151,
              Src,
              v155,
              a5,
              &v158,
              v165,
              &v152,
              v160,
              v168,
              v55);
      v12 = v56;
      if ( v56 < 0 )
      {
        WdLogSingleEntry3(2, *((int *)v11 + 104), *((unsigned int *)v11 + 103), v56);
        WdLogGlobalForLineNumber = 3002;
      }
    }
    else
    {
      v149 = 0;
    }
LABEL_91:
    v44 = v154;
  }
  *(_DWORD *)&v145[4] = HIDWORD(Src);
  DisplayScenarioJournalSetSetTimingPathInfo(*(_QWORD *)((char *)v11 + 412), (unsigned int)v12, 56 * v151);
  LogSetTimingSourceMask(v11, a5);
  if ( v149 )
  {
    if ( v12 < 0 )
    {
      *((_DWORD *)a5 + 21) = -1;
      FillFailedStatus(a5, v12);
      v71 = 0;
      if ( v151 )
      {
        v72 = v163;
        do
        {
          v73 = v71++;
          v74 = 56 * v73;
          v75 = (char *)Src;
          v76 = *(_OWORD *)&v72[v74 + 16];
          v77 = *(_OWORD *)&v72[v74 + 32];
          v78 = *(_QWORD *)&v72[v74 + 48];
          *(_OWORD *)((char *)Src + v74) = *(_OWORD *)&v72[v74];
          *(_OWORD *)&v75[v74 + 16] = v76;
          *(_OWORD *)&v75[v74 + 32] = v77;
          *(_QWORD *)&v75[v74 + 48] = v78;
          *(_DWORD *)((char *)Src + v74 + 32) = *(_DWORD *)((_BYTE *)Src + v74 + 32) & 0xF0FFFFFF | 0xD000000;
          *(_DWORD *)((char *)Src + v74 + 16) |= 1u;
        }
        while ( v71 < v151 );
        v15 = v162;
      }
      v70 = (_BYTE *)v157;
      v69 = 1;
      v152 = 1;
      *(_BYTE *)v157 = (((v44 - 1) & 0xFFFFFFFD) != 0 ? 2 : 0) | *(_BYTE *)v157 & 0xFD;
    }
    else
    {
      v45 = 0;
      if ( v151 )
      {
        v46 = v163;
        v47 = (_BYTE *)v157;
        do
        {
          v48 = 56LL * (unsigned int)v45;
          v49 = &v46[v48];
          v50 = VIDPN_MGR::CheckDdiSetTimingsViolationOnPathInfo(
                  v161,
                  (struct _DXGK_SET_TIMING_PATH_INFO *)&v46[v48],
                  (struct _DXGK_SET_TIMING_PATH_INFO *)((char *)Src + v48)) == 0;
          v51 = (char *)Src;
          if ( v50 )
          {
            v52 = *((_OWORD *)v49 + 1);
            v53 = *((_OWORD *)v49 + 2);
            v54 = *((_QWORD *)v49 + 6);
            *(_OWORD *)((char *)Src + v48) = *(_OWORD *)v49;
            *(_OWORD *)&v51[v48 + 16] = v52;
            *(_OWORD *)&v51[v48 + 32] = v53;
            *(_QWORD *)&v51[v48 + 48] = v54;
            *(_DWORD *)((char *)Src + v48 + 32) = *(_DWORD *)((_BYTE *)Src + v48 + 32) & 0xF0FFFFFF | 0xD000000;
            *((_DWORD *)a5 + *(unsigned int *)(v155 + 4 * v45) + 22) = -1073741437;
            *((_DWORD *)a5 + 21) |= 1 << *(_DWORD *)(v155 + 4 * v45);
          }
          else if ( (*(_DWORD *)((_BYTE *)Src + v48 + 32) & 0xF000000) == 0xD000000 )
          {
            *((_DWORD *)a5 + *(unsigned int *)(v155 + 4 * v45) + 22) = -1073741506;
            *((_DWORD *)a5 + 21) |= 1 << *(_DWORD *)(v155 + 4 * v45);
            *v47 = (((v154 - 1) & 0xFFFFFFFD) != 0 ? 2 : 0) | *v47 & 0xFD;
          }
          v45 = (unsigned int)(v45 + 1);
        }
        while ( (unsigned int)v45 < v151 );
        v15 = v162;
        v11 = ContainingAdapter;
      }
      v69 = v152;
      v70 = (_BYTE *)v157;
    }
    if ( (v69 & 0xFFFFFFFE) != 0 )
    {
      WdLogSingleEntry1(1);
      LOBYTE(v69) = v152;
      WdLogGlobalForLineNumber = 3124;
    }
    if ( (v69 & 1) != 0 )
      *v70 |= 1u;
  }
  ActivityId = 0;
  EtwActivityIdControl(3u, &ActivityId);
  for ( i = 0; (unsigned int)i < v151; i = (unsigned int)(i + 1) )
  {
    v80 = 56LL * (unsigned int)i;
    v81 = *(_DWORD *)(v155 + 4 * i);
    LODWORD(v157) = v81;
    v82 = DMMVIDEOPRESENTTARGETSET::GetTargetById((DMMVIDEOPRESENTTARGETSET *)v15, *(_DWORD *)((char *)Src + v80));
    v83 = v82;
    if ( v82 )
    {
      v84 = 1 << v81;
      if ( v149 )
      {
        LogMonitorHandleOnOffState(*((_QWORD *)v82 + 14), &ActivityId, (*(_DWORD *)((char *)Src + v80 + 12) >> 2) & 1);
        if ( !v148 )
        {
          DxgkLogCodePointPacket(
            88,
            *(unsigned int *)((char *)Src + v80),
            *((_BYTE *)Src + v80 + 35) & 0xF | 0x80000000);
          if ( (unsigned int)dword_1401605E8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1401605E8, 0x4000) )
          {
            v159 = *((_BYTE *)Src + v80 + 35) & 0xF | 0x80000000;
            ContainingAdapter = *(DXGADAPTER **)((char *)Src + v80 + 24);
            v156 = *(_DWORD *)((char *)Src + v80);
            v169 = *(const struct DMMVIDPN **)((char *)v11 + 412);
            v153 = 1;
            *(_QWORD *)&v175[0] = 0x1000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
              (_DWORD)Src,
              (unsigned int)word_140145FFA,
              v85,
              v86,
              (__int64)v175,
              (__int64)&v153,
              (__int64)&v169,
              (__int64)&v156,
              (__int64)&ContainingAdapter,
              (__int64)&v159);
          }
          *(_QWORD *)v145 = *(_QWORD *)((char *)v11 + 412);
          DxgkLogCodePointPacket(89, *(unsigned int *)((char *)Src + v80), *(unsigned int *)((char *)Src + v80 + 48));
        }
        TargetLinkTrainingStatus = DMMVIDEOPRESENTTARGET::GetTargetLinkTrainingStatus(v83, 0);
        if ( TargetLinkTrainingStatus != v88 )
          *((_DWORD *)a5 + 9) |= v84;
        DMMVIDEOPRESENTTARGET::UpdateTargetLinkTrainingStatus(
          v83,
          *(_QWORD *)((char *)Src + v80 + 24),
          *((_BYTE *)Src + v80 + 35) & 0xF);
        if ( (*(_DWORD *)((_BYTE *)Src + v80 + 32) & 0xF000000) == 0xC000000 )
          DMMVIDEOPRESENTTARGET::StartLinkTrainingTimer(v83, 1u);
        else
          DMMVIDEOPRESENTTARGET::CancelLinkTrainingTimer(v83);
        *((_BYTE *)v83 + 414) = 0;
      }
      else
      {
        v89 = DMMVIDEOPRESENTTARGET::GetTargetLinkTrainingStatus(v82, 0);
        *(_DWORD *)((char *)Src + v80 + 32) ^= (*(_DWORD *)((char *)Src + v80 + 32) ^ (v89 << 24)) & 0xF000000;
      }
      if ( (*(_DWORD *)((_BYTE *)Src + v80 + 12) & 4) != 0 && (v84 & *((_DWORD *)a5 + 18)) == 0 )
      {
        v90 = *((_DWORD *)a5 + 21) | v158;
        if ( !_bittest(&v90, v157) )
        {
          DMMVIDEOPRESENTTARGET::SetTargetActivated(v83, 1u, 1u);
          if ( ((*((_DWORD *)a5 + 2) | *((_DWORD *)a5 + 6) | *((_DWORD *)a5 + 8) | *((_DWORD *)a5 + 9)) & v84) != 0
            && (*(_DWORD *)((_BYTE *)Src + v80 + 32) & 0xF000000) == 0xE000000 )
          {
            PathFromTarget = DMMVIDPNTOPOLOGY::GetPathFromTarget(v164, *(_DWORD *)((char *)Src + v80));
            DMMVIDPNPRESENTPATH::SetDriverGammaRamp(PathFromTarget, 0);
          }
        }
      }
      if ( (*(_DWORD *)((_BYTE *)Src + v80 + 32) & 0xF000000) != 0xD000000
        && ((*((_DWORD *)a5 + 2) | *((_DWORD *)a5 + 4)) & v84) != 0 )
      {
        MonitorSetLastWireformatAndColorspace(
          *((struct HDXGMONITOR__ **)v83 + 14),
          *(union _D3DKMDT_WIRE_FORMAT_AND_PREFERENCE *)((char *)Src + v80 + 8),
          *(enum _D3DDDI_OUTPUT_WIRE_COLOR_SPACE_TYPE *)((char *)Src + v80 + 4));
      }
    }
  }
  CVidSchSuspendResume::Resume((CVidSchSuspendResume *)&v171);
  v92 = (ADAPTER_DISPLAY *)*((_QWORD *)v11 + 406);
  if ( *((_DWORD *)v92 + 24) )
  {
    v93 = 0;
    while ( 1 )
    {
      memset(v176, 0, sizeof(v176));
      v94 = 1 << v93;
      if ( ((1 << v93) & *((_DWORD *)a5 + 3)) != 0 )
      {
        v153 = 2;
      }
      else if ( (v94 & *((_DWORD *)a5 + 10)) != 0 )
      {
        v153 = 4;
      }
      else
      {
        v95 = ~*((_DWORD *)a5 + 8);
        v153 = 0;
        if ( (*((_DWORD *)a5 + 2) & v95 & v94) != 0 )
          v153 = (*(_DWORD *)a5 & v94) != 0 ? 3 : 1;
      }
      DisplayModeInfo = ADAPTER_DISPLAY::GetDisplayModeInfo(v92, v93);
      v97 = *((_DWORD *)a5 + 13) | *((_DWORD *)a5 + 2) | *((_DWORD *)a5 + 10);
      v98 = v164;
      *(_OWORD *)v176 = *(_OWORD *)DisplayModeInfo;
      *(_OWORD *)&v176[4] = *((_OWORD *)DisplayModeInfo + 1);
      *(_OWORD *)&v176[8] = *((_OWORD *)DisplayModeInfo + 2);
      *(_OWORD *)&v176[12] = *((_OWORD *)DisplayModeInfo + 3);
      *(_OWORD *)&v176[16] = *((_OWORD *)DisplayModeInfo + 4);
      if ( (v97 & v94) != 0 )
        DMMVIDPNTOPOLOGY::GetDisplayModeFromVidPnSource(
          v164,
          ((v154 - 1) & 0xFFFFFFFD) == 0,
          v93,
          (struct _DXGK_DISPLAYMODE_INFO *)v176);
      if ( (v94 & *((_DWORD *)a5 + 21)) != 0 )
        goto LABEL_228;
      if ( (v94 & v158) == 0 )
        break;
LABEL_230:
      v92 = (ADAPTER_DISPLAY *)*((_QWORD *)v11 + 406);
      v93 = (unsigned int)(v93 + 1);
      if ( (unsigned int)v93 >= *((_DWORD *)v92 + 24) )
      {
        v15 = v162;
        goto LABEL_232;
      }
    }
    if ( (v94 & *((_DWORD *)a5 + 10)) != 0 )
    {
      ADAPTER_DISPLAY::SetDisplayModeInfo(
        *((ADAPTER_DISPLAY **)v11 + 406),
        v93,
        (const struct _DXGK_DISPLAYMODE_INFO *const)v176);
      *(_DWORD *)v145 = 0;
      OUTPUTDUPL_MGR::MoveContextToPendingDestroyList(
        *(_QWORD *)(*((_QWORD *)v11 + 406) + 120LL),
        (unsigned int)v93,
        0,
        0,
        *(_QWORD *)v145,
        1);
      v175[0] = 0xBu;
      v175[1] = 0;
      if ( (int)DxgkStatusChangeNotify((int *)v175, v99, v100) < 0 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 3395;
        DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"NT_SUCCESS(NotificationStatus)", 3395, 0, 0, 0, 0);
      }
    }
    if ( ((*((_DWORD *)a5 + 13)
         | *((_DWORD *)a5 + 2)
         | *((_DWORD *)a5 + 3)
         | *((_DWORD *)a5 + 6)
         | *((_DWORD *)a5 + 8)
         | *((_DWORD *)a5 + 9))
        & v94) != 0 )
    {
      v156 = 0;
      MostImportantVidPnPathTargetsFromSource = GetMostImportantVidPnPathTargetsFromSource(v98, v93, &v156);
      if ( (int)(MostImportantVidPnPathTargetsFromSource + 0x80000000) >= 0
        && MostImportantVidPnPathTargetsFromSource != -1071774919 )
      {
        WdLogSingleEntry0(1);
        v102 = 0;
        WdLogGlobalForLineNumber = 3430;
        goto LABEL_184;
      }
      v102 = 0;
      if ( MostImportantVidPnPathTargetsFromSource < 0 || (v103 = v156, v156 == -1) || (v109 = 0, !v151) )
      {
LABEL_184:
        v103 = -1;
      }
      else
      {
        while ( 1 )
        {
          v102 = 0;
          if ( (_DWORD)v93 == *(_DWORD *)(v155 + 4 * v109) )
          {
            v110 = 56LL * (unsigned int)v109;
            if ( v156 == *(_DWORD *)((char *)Src + v110)
              && (*(_DWORD *)((_BYTE *)Src + v110 + 32) & 0xF000000) == 0xE000000
              && (*(_DWORD *)((_BYTE *)Src + v110 + 12) & 4) != 0
              && (v94 & *((_DWORD *)a5 + 18)) == 0 )
            {
              break;
            }
          }
          v109 = (unsigned int)(v109 + 1);
          if ( (unsigned int)v109 >= v151 )
            goto LABEL_184;
        }
        *((_DWORD *)a5 + 19) |= v94;
        v102 = 1;
      }
      ADAPTER_DISPLAY::SetVidPnPrimaryTarget(*((ADAPTER_DISPLAY **)v11 + 406), v93, v103);
      if ( (v94 & *((_DWORD *)a5 + 2)) != 0 )
      {
        v50 = *((_QWORD *)v11 + 407) == 0;
        v176[11] = 1;
        *(_QWORD *)&v176[12] = 1;
        if ( !v50 )
        {
          DisplayedPrimaryAllocation = ADAPTER_DISPLAY::GetDisplayedPrimaryAllocation(
                                         *((ADAPTER_DISPLAY **)v11 + 406),
                                         v93);
          v105 = DisplayedPrimaryAllocation;
          if ( DisplayedPrimaryAllocation )
          {
            if ( (*((_BYTE *)DisplayedPrimaryAllocation + 4) & 0x10) != 0 )
              v105 = 0;
            if ( v105 )
            {
              v106 = (void *)*((_QWORD *)v105 + 2);
              v107 = (ADAPTER_RENDER *)*((_QWORD *)v11 + 407);
              memset(&v166.Width, 0, 40);
              v166.hAllocation = v106;
              v108 = ADAPTER_RENDER::DdiDescribeAllocation(v107, &v166);
              if ( v108 < 0 )
              {
                WdLogSingleEntry3(3, v105, (unsigned int)v93, v108);
                WdLogGlobalForLineNumber = 3540;
              }
              else if ( v166.Width == v176[0]
                     && v166.Height == v176[1]
                     && v166.Format == v176[2]
                     && *(_QWORD *)&v166.RefreshRate == *(_QWORD *)&v176[14]
                     && (((unsigned __int8)~(v176[10] >> 4) ^ (unsigned __int8)~(*((_DWORD *)v105 + 1) >> 12)) & 1) == 0 )
              {
                *(D3DDDI_MULTISAMPLINGMETHOD *)&v176[11] = v166.MultisampleMethod;
                v176[13] = v166.PrivateDriverFormatAttribute;
              }
              else if ( v148 || (*((_DWORD *)v105 + 1) & 2) == 0 )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 3528;
              }
            }
          }
        }
      }
      v111 = v154;
      v112 = ADAPTER_DISPLAY::SetVidPnSourceActive(
               *((ADAPTER_DISPLAY **)v11 + 406),
               v93,
               v102,
               (const struct _DXGK_DISPLAYMODE_INFO *)v176,
               v154 == 4,
               a7 != 0);
      v113 = v112;
      if ( v112 >= 0 )
      {
        ADAPTER_DISPLAY::MarkCommitVidPnOnModeChange(*((ADAPTER_DISPLAY **)v11 + 406), v93, 0);
        if ( (v94 & *((_DWORD *)a5 + 3)) != 0 )
        {
          if ( ((v111 - 1) & 0xFFFFFFFD) != 0 )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 3574;
          }
          ADAPTER_DISPLAY::SetPartOfDesktop(*((ADAPTER_DISPLAY **)v11 + 406), v93, 0);
          ADAPTER_DISPLAY::SetContentRect(*((ADAPTER_DISPLAY **)v11 + 406), v93, &stru_1401635A8);
          ADAPTER_DISPLAY::SetCddInterface(*((ADAPTER_DISPLAY **)v11 + 406), v93, 0);
          ADAPTER_DISPLAY::SetHdrEnabled(*((ADAPTER_DISPLAY **)v11 + 406), v93, 0);
        }
        else
        {
          v157 = 0;
          if ( DMMVIDPNTOPOLOGY::GetNumPathsFromSource(v164, v93, &v157) < 0 || !v157 )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 3587;
          }
          if ( ((*((_DWORD *)a5 + 13) | *((_DWORD *)a5 + 2)) & v94) != 0 )
          {
            if ( ((v111 - 1) & 0xFFFFFFFD) == 0 )
              ADAPTER_DISPLAY::SetPartOfDesktop(*((ADAPTER_DISPLAY **)v11 + 406), v93, 1u);
            ADAPTER_DISPLAY::SetDisplayModeInfo(
              *((ADAPTER_DISPLAY **)v11 + 406),
              v93,
              (const struct _DXGK_DISPLAYMODE_INFO *const)v176);
            ADAPTER_DISPLAY::SetLastCddIntegerVSync(*((ADAPTER_DISPLAY **)v11 + 406), v93, v176[3]);
            ADAPTER_DISPLAY::DetermineScalingCapabilities(*((ADAPTER_DISPLAY **)v11 + 406), v93);
            ADAPTER_DISPLAY::SetHdrEnabled(*((ADAPTER_DISPLAY **)v11 + 406), v93, (v94 & *((_DWORD *)a5 + 64)) != 0);
            if ( v160 && v168 )
              ADAPTER_DISPLAY::UpdateOneCddPrimaryPrivateDriverData(
                *((ADAPTER_DISPLAY **)v11 + 406),
                v93,
                *(struct DXGADAPTER **)(*((_QWORD *)v160 + 2) + 16LL));
          }
        }
      }
      else
      {
        WdLogSingleEntry3(2, v11, (unsigned int)v93, v112);
        WdLogGlobalForLineNumber = 3558;
        *((_DWORD *)a5 + v93 + 22) = v113;
        *((_DWORD *)a5 + 21) |= v94;
      }
    }
LABEL_228:
    v114 = v153;
    if ( v153 )
    {
      CurrentProcess = PsGetCurrentProcess();
      ProcessImageFileName = PsGetProcessImageFileName(CurrentProcess);
      *(_DWORD *)v145 = *((_DWORD *)a5 + v93 + 22);
      VIDPN_MGR::CacheDisplayModeChangeRequest(
        v161,
        (unsigned int)v93,
        v176,
        1,
        *(_QWORD *)v145,
        v114,
        *(_DWORD *)(*((_QWORD *)v11 + 406) + 424LL),
        ProcessImageFileName);
    }
    goto LABEL_230;
  }
LABEL_232:
  for ( j = 0; (unsigned int)j < v151; j = (unsigned int)(j + 1) )
  {
    v118 = 56LL * (unsigned int)j;
    v119 = DMMVIDEOPRESENTTARGETSET::GetTargetById((DMMVIDEOPRESENTTARGETSET *)v15, *(_DWORD *)((char *)Src + v118));
    v120 = v119;
    if ( v119 )
    {
      v121 = Src;
      if ( (*(_DWORD *)((_BYTE *)Src + v118 + 12) & 4) == 0
        || (v122 = v155, v123 = 1 << *(_DWORD *)(v155 + 4 * j), (v123 & *((_DWORD *)a5 + 18)) != 0)
        || (v123 & *((_DWORD *)a5 + 21)) != 0 )
      {
        DMMVIDEOPRESENTTARGET::SetTargetActivated(
          v119,
          0,
          (*(_DWORD *)((_BYTE *)Src + v118 + 32) & 0xF000000) == 201326592);
        v121 = Src;
        v122 = v155;
      }
      if ( !v148
        && *((_BYTE *)v120 + 416)
        && ((*(_DWORD *)&v121[v118 + 32] & 0xF000000) != 0xE000000 || v121[v118 + 48] != 0xFF) )
      {
        v124 = ADAPTER_DISPLAY::SetVidPnSourceVisibility(
                 *((ADAPTER_DISPLAY **)v11 + 406),
                 *(_DWORD *)(v122 + 4 * j),
                 0,
                 0x800u,
                 a7);
        if ( v124 < 0 )
        {
          WdLogSingleEntry3(2, v11, *(unsigned int *)(v155 + 4 * j), v124);
          WdLogGlobalForLineNumber = 3695;
        }
        if ( (*((_DWORD *)Src + 14 * (unsigned int)j + 8) & 0xF000000) == 0xE000000 )
        {
          v125 = *((_QWORD *)v11 + 407);
          if ( v125 )
          {
            VIDSCH_EXPORT::VidSchRequestDeferredVidPnSourceVisibility(
              *(VIDSCH_EXPORT **)(v125 + 736),
              *(struct _VIDSCH_GLOBAL **)(v125 + 744),
              *(_DWORD *)(v155 + 4 * j));
          }
          else
          {
            v126 = *(_QWORD *)(*((_QWORD *)v11 + 406) + 464LL);
            if ( v126 )
              _InterlockedExchange(
                (volatile __int32 *)(3040LL * *(unsigned int *)(v155 + 4 * j) + *(_QWORD *)(v126 + 8) + 1080),
                1);
          }
        }
      }
      *((_BYTE *)v120 + 416) = 0;
    }
    else if ( (*(_DWORD *)((_BYTE *)Src + v118 + 12) & 4) != 0 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 3739;
    }
    if ( (*((_DWORD *)Src + 14 * (unsigned int)j + 4) & 1) != 0 )
      *((_DWORD *)a5 + 16) |= 1 << *(_DWORD *)(v155 + 4 * j);
  }
  auto_rc<DMMVIDPN>::reset((char *)v161 + 320, 0);
  CVidSchSuspendResume::Resume((CVidSchSuspendResume *)&v171);
  v127 = (ADAPTER_DISPLAY *)*((_QWORD *)v11 + 406);
  if ( *((_DWORD *)v127 + 24) )
  {
    v128 = 0;
    v129 = v160;
    do
    {
      v130 = 1 << v128;
      if ( ((1 << v128) & *((_DWORD *)a5 + 15)) != 0 )
        ADAPTER_DISPLAY::InvalidateDisplayModeListCacheOnSource(v127, v128);
      if ( (v130 & *((_DWORD *)a5 + 16)) != 0 )
        DXGADAPTER::NotifyMultiPlaneOverlayDisable(v11, v128);
      if ( v129 && !v148 )
      {
        if ( ADAPTER_DISPLAY::GetCddPrimaryAllocation(*((ADAPTER_DISPLAY **)v11 + 406), v128, 0)
          && ADAPTER_DISPLAY::IsCddPrimaryStale(*((ADAPTER_DISPLAY **)v11 + 406), v128) )
        {
          ADAPTER_DISPLAY::DestroyCddAllocations(v131, v129, v128);
        }
        v132 = (ADAPTER_DISPLAY *)*((_QWORD *)v11 + 406);
        v133 = (const struct _D3DKMT_DISPLAYMODE *)ADAPTER_DISPLAY::GetDisplayModeInfo(v132, v128);
        ADAPTER_DISPLAY::SetCddDisplayMode(v132, v128, v133);
        v129 = v160;
      }
      if ( (v130 & *((_DWORD *)a5 + 21)) != 0 )
      {
        v134 = *((_DWORD *)a5 + v128 + 40);
        if ( (v134 & 7) != 0 )
        {
          *((_DWORD *)a5 + 4 * (v134 & 7) + 56) = 0;
          DxgkLogCodePointPacket(101, (unsigned int)v128, *((_DWORD *)a5 + v128 + 40) & 7);
        }
        v135 = v154;
        v136 = ADAPTER_DISPLAY::SetVidPnSourceActive(*((ADAPTER_DISPLAY **)v11 + 406), v128, 0, 0, v154 == 4, a7 != 0);
        if ( v136 < 0 )
        {
          WdLogSingleEntry3(2, v11, (unsigned int)v128, v136);
          WdLogGlobalForLineNumber = 3863;
        }
        if ( v173 )
        {
          v137 = (const struct DMMVIDPN *)((char *)v173 + 96);
          v138 = (__int64)v173 + 152;
          *(_QWORD *)v146 = *((_QWORD *)v173 + 17);
          LOBYTE(v138) = 2;
          ApplyPermissionWithinThisScope::ApplyPermissionWithinThisScope(
            v175,
            ((unsigned __int64)v173 + 152) & -(__int64)((const struct DMMVIDPN *)((char *)v173 + 96) != 0),
            v138);
          v139 = DMMVIDPNTOPOLOGY::RemoveAllPathsFromSource(v137, v128);
          if ( (int)(v139 + 0x80000000) >= 0 && v139 != -1071774919 )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 3878;
          }
          ApplyPermissionWithinThisScope::~ApplyPermissionWithinThisScope((ApplyPermissionWithinThisScope *)v175);
        }
        v129 = v160;
        if ( v160 )
          ADAPTER_DISPLAY::DestroyCddAllocations(*((ADAPTER_DISPLAY **)v11 + 406), v160, v128);
        if ( ((v135 - 1) & 0xFFFFFFFD) == 0 )
        {
          ADAPTER_DISPLAY::SetPartOfDesktop(*((ADAPTER_DISPLAY **)v11 + 406), v128, 0);
          ADAPTER_DISPLAY::SetContentRect(*((ADAPTER_DISPLAY **)v11 + 406), v128, &stru_1401635A8);
          ADAPTER_DISPLAY::SetCddInterface(*((ADAPTER_DISPLAY **)v11 + 406), v128, 0);
        }
        ADAPTER_DISPLAY::SetVidPnPrimaryTarget(*((ADAPTER_DISPLAY **)v11 + 406), v128, 0xFFFFFFFF);
        ADAPTER_DISPLAY::MarkCommitVidPnOnModeChange(*((ADAPTER_DISPLAY **)v11 + 406), v128, 1u);
        ADAPTER_DISPLAY::SetHdrEnabled(*((ADAPTER_DISPLAY **)v11 + 406), v128, 0);
      }
      v127 = (ADAPTER_DISPLAY *)*((_QWORD *)v11 + 406);
      v128 = (unsigned int)(v128 + 1);
    }
    while ( (unsigned int)v128 < *((_DWORD *)v127 + 24) );
    v15 = v162;
  }
  if ( v173 )
  {
    *(_DWORD *)v146 = *((_DWORD *)a5 + 63);
    *(_DWORD *)v145 = *((_DWORD *)a5 + 62);
    ADAPTER_DISPLAY::SetSyncLockGroup(
      v127,
      1,
      *((unsigned int *)a5 + 60),
      *((unsigned int *)a5 + 61),
      *(_QWORD *)v145,
      *(_QWORD *)v146);
    v140 = *((_QWORD *)v11 + 406);
    if ( *(_DWORD *)(v140 + 96) )
    {
      v141 = 0;
      do
      {
        v142 = (unsigned int)v141;
        v143 = *((_DWORD *)a5 + v141 + 40) & 7;
        v141 = (unsigned int)(v141 + 1);
        *(_DWORD *)(4024 * v142 + *(_QWORD *)(v140 + 128) + 3804) = *((_DWORD *)a5 + 4 * v143 + 56) != 0 ? v143 : 0;
        v140 = *((_QWORD *)v11 + 406);
      }
      while ( (unsigned int)v141 < *(_DWORD *)(v140 + 96) );
    }
  }
  DxgkInvalidateQdcCache();
  CVidSchSuspendResume::Resume((CVidSchSuspendResume *)&v171);
  if ( v15 )
    ReferenceCounted::Release((ReferenceCounted *)(v15 + 64));
  wistd::unique_ptr<unsigned int [0],wistd::default_delete<unsigned int [0]>>::reset(&v163);
  auto_rc<DMMVIDPN const>::reset(&v174, 0);
  v12 = 0;
LABEL_291:
  wistd::unique_ptr<unsigned int [0],wistd::default_delete<unsigned int [0]>>::reset(&v165);
  wistd::unique_ptr<unsigned int [0],wistd::default_delete<unsigned int [0]>>::reset(&v155);
  wistd::unique_ptr<unsigned int [0],wistd::default_delete<unsigned int [0]>>::reset(&Src);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1402d4e14  push    rbp
0x1402d4e16  push    rbx
0x1402d4e17  push    rsi
0x1402d4e18  push    rdi
0x1402d4e19  push    r12
0x1402d4e1b  push    r13
0x1402d4e1d  push    r14
0x1402d4e1f  push    r15
0x1402d4e21  lea     rbp, [rsp-0E8h]
0x1402d4e29  sub     rsp, 1E8h
0x1402d4e30  mov     rax, cs:__security_cookie
0x1402d4e37  xor     rax, rsp
0x1402d4e3a  mov     [rbp+120h+var_50], rax
0x1402d4e41  mov     rax, [rbp+120h+arg_38]
0x1402d4e48  xor     r13d, r13d
0x1402d4e4b  mov     rdi, [rbp+120h+arg_28]
0x1402d4e52  mov     r12, r9
0x1402d4e55  mov     rsi, [rbp+120h+arg_20]
0x1402d4e5c  mov     ebx, edx
0x1402d4e5e  mov     [rbp+120h+var_170], rax
0x1402d4e62  mov     r15, rcx
0x1402d4e65  mov     rax, [rbp+120h+arg_40]
0x1402d4e6c  mov     [rbp+120h+var_108], rax
0x1402d4e70  mov     [rbp+120h+var_E0], r9
0x1402d4e74  mov     [rbp+120h+var_194], r8d
0x1402d4e78  mov     [rbp+120h+var_174], edx
0x1402d4e7b  mov     [rbp+120h+var_168], rcx
0x1402d4e7f  mov     [rbp+120h+var_180], rdi
0x1402d4e83  mov     dword ptr [rbp+120h+var_1A0+4], r13d
0x1402d4e87  call    ?GetContainingAdapter@VIDPN_MGR@@QEBAPEAVDXGADAPTER@@XZ; VIDPN_MGR::GetContainingAdapter(void)
0x1402d4e8c  mov     rcx, rax; this
0x1402d4e8f  mov     [rbp+120h+var_F8], rax
0x1402d4e93  mov     r14, rax
0x1402d4e96  call    ?IsCoreResourceExclusiveOwner@DXGADAPTER@@QEBAEXZ; DXGADAPTER::IsCoreResourceExclusiveOwner(void)
0x1402d4e9b  test    al, al
0x1402d4e9d  jnz     short loc_1402D4EB9
0x1402d4e9f  lea     ecx, [r13+1]
0x1402d4ea3  call    cs:__imp_WdLogSingleEntry0
0x1402d4eaa  nop     dword ptr [rax+rax+00h]
0x1402d4eaf  mov     cs:WdLogGlobalForLineNumber, 9CEh
0x1402d4eb9  xor     eax, eax
0x1402d4ebb  mov     dword ptr [rbp+120h+var_110], r13d
0x1402d4ebf  mov     [rdi], al
0x1402d4ec1  mov     r9, rsi
0x1402d4ec4  lea     rax, [rbp+120h+var_148]
0x1402d4ec8  mov     dword ptr [rbp+120h+var_1A0], r13d
0x1402d4ecc  mov     [rsp+220h+var_1E0], rax; __int64
0x1402d4ed1  mov     r8, r12
0x1402d4ed4  lea     rax, [rbp+120h+var_190]
0x1402d4ed8  mov     [rsp+220h+Src], r13
0x1402d4edd  mov     [rsp+220h+var_1E8], rax; __int64
0x1402d4ee2  mov     edx, ebx
0x1402d4ee4  lea     rax, [rsp+220h+Src]
0x1402d4ee9  mov     [rbp+120h+var_190], r13
0x1402d4eed  mov     [rsp+220h+var_1F0], rax; __int64
0x1402d4ef2  mov     rcx, r15; this
0x1402d4ef5  lea     rax, [rbp+120h+var_1A0]
0x1402d4ef9  mov     [rbp+120h+var_148], r13
0x1402d4efd  mov     qword ptr [rsp+220h+var_1F8], rax; __int64
0x1402d4f02  lea     rax, [rbp+120h+var_110]
0x1402d4f06  mov     qword ptr [rsp+220h+var_200], rax; __int64
0x1402d4f0b  call    ?BuildSetTimingsPathInfoFromClientVidPn@VIDPN_MGR@@AEBAJKQEAVDMMVIDPN@@PEAUD3DKMT_VIDPN_SOURCE_MASKS@@PEAK2AEAV?$unique_ptr@$$BY0A@U_DXGK_SET_TIMING_PATH_INFO@@U?$default_delete@$$BY0A@U_DXGK_SET_TIMING_PATH_INFO@@@wistd@@@wistd@@AEAV?$unique_ptr@$$BY0A@IU?$default_delete@$$BY0A@I@wistd@@@5@4@Z; VIDPN_MGR::BuildSetTimingsPathInfoFromClientVidPn(ulong,DMMVIDPN * const,D3DKMT_VIDPN_SOURCE_MASKS *,ulong *,ulong *,wistd::unique_ptr<_DXGK_SET_TIMING_PATH_INFO [0],wistd::default_delete<_DXGK_SET_TIMING_PATH_INFO [0]>> &,wistd::unique_ptr<uint [0],wistd::default_delete<uint [0]>> &,wistd::unique_ptr<uint [0],wistd::default_delete<uint [0]>> &)
0x1402d4f10  movsxd  rdi, eax
0x1402d4f13  mov     [rbp+120h+var_188], edi
0x1402d4f16  test    eax, eax
0x1402d4f18  jns     short loc_1402D4F40
0x1402d4f1a  mov     r8, rdi
0x1402d4f1d  mov     rdx, r12
0x1402d4f20  mov     ecx, 2
0x1402d4f25  call    cs:__imp_WdLogSingleEntry2
0x1402d4f2c  nop     dword ptr [rax+rax+00h]
0x1402d4f31  mov     cs:WdLogGlobalForLineNumber, 9EEh
0x1402d4f3b  jmp     loc_1402D680C
0x1402d4f40  mov     r9d, dword ptr [rbp+120h+var_1A0]
0x1402d4f44  test    r9d, r9d
0x1402d4f47  jnz     short loc_1402D4F76
0x1402d4f49  mov     r8d, [r14+19Ch]
0x1402d4f50  lea     ecx, [r9+3]
0x1402d4f54  movsxd  rdx, dword ptr [r14+1A0h]
0x1402d4f5b  call    cs:__imp_WdLogSingleEntry2
0x1402d4f62  nop     dword ptr [rax+rax+00h]
0x1402d4f67  mov     cs:WdLogGlobalForLineNumber, 0A00h
0x1402d4f71  jmp     loc_1402D680C
0x1402d4f76  cmp     [rsi+8], r13d
0x1402d4f7a  jnz     short loc_1402D4FCA
0x1402d4f7c  cmp     [rsi+0Ch], r13d
0x1402d4f80  jnz     short loc_1402D4FCA
0x1402d4f82  cmp     [rsi+18h], r13d
0x1402d4f86  jnz     short loc_1402D4FCA
0x1402d4f88  mov     [rsp+220h+var_1AF], r13b
0x1402d4f8d  cmp     [rsi+28h], r13d
0x1402d4f91  jnz     short loc_1402D4FCF
0x1402d4f93  cmp     [rsi+20h], r13d
0x1402d4f97  jnz     short loc_1402D4FCF
0x1402d4f99  cmp     [rsi+34h], r13d
0x1402d4f9d  jnz     short loc_1402D4FCF
0x1402d4f9f  mov     rax, [rsp+220h+Src]
0x1402d4fa4  xor     edx, edx
0x1402d4fa6  mov     rcx, [r14+19Ch]
0x1402d4fad  imul    r8d, r9d, 38h ; '8'
0x1402d4fb1  mov     qword ptr [rsp+220h+var_200], rax
0x1402d4fb6  call    cs:__imp_DisplayScenarioJournalSetSetTimingPathInfo
0x1402d4fbd  nop     dword ptr [rax+rax+00h]
0x1402d4fc2  mov     edi, r13d
0x1402d4fc5  jmp     loc_1402D680C
0x1402d4fca  mov     [rsp+220h+var_1AF], 1
0x1402d4fcf  mov     rcx, r15; this
0x1402d4fd2  mov     [rbp+120h+var_178], r13d
0x1402d4fd6  call    ?AcquireLastClientCommittedVidPnRef@VIDPN_MGR@@QEBAPEBVDMMVIDPN@@XZ; VIDPN_MGR::AcquireLastClientCommittedVidPnRef(void)
0x1402d4fdb  mov     ecx, dword ptr [rbp+120h+var_1A0]
0x1402d4fde  mov     r13, rax
0x1402d4fe1  mov     [rbp+120h+var_D8], rax
0x1402d4fe5  test    r12, r12
0x1402d4fe8  mov     eax, 38h ; '8'
0x1402d4fed  mov     r8d, 100h
0x1402d4ff3  cmovnz  r13, r12
0x1402d4ff7  mul     rcx
0x1402d4ffa  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1402d5001  mov     [rbp+120h+var_100], r13
0x1402d5005  mov     edx, 4E506456h
0x1402d500a  cmovb   rax, rcx
0x1402d500e  mov     rcx, rax
0x1402d5011  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1402d5016  mov     [rbp+120h+var_158], rax
0x1402d501a  mov     rcx, rax; void *
0x1402d501d  test    rax, rax
0x1402d5020  jnz     short loc_1402D505C
0x1402d5022  mov     edx, dword ptr [rbp+120h+var_1A0]
0x1402d5025  lea     ecx, [rax+6]
0x1402d5028  call    cs:__imp_WdLogSingleEntry1
0x1402d502f  nop     dword ptr [rax+rax+00h]
0x1402d5034  lea     rcx, [rbp+120h+var_158]
0x1402d5038  mov     cs:WdLogGlobalForLineNumber, 0A3Eh
0x1402d5042  call    ?reset@?$unique_ptr@$$BY0A@IU?$default_delete@$$BY0A@I@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uint [0],wistd::default_delete<uint [0]>>::reset(std::nullptr_t)
0x1402d5047  xor     edx, edx
0x1402d5049  lea     rcx, [rbp+120h+var_D8]
0x1402d504d  call    ?reset@?$auto_rc@$$CBVDMMVIDPN@@@@QEAAXPEBVDMMVIDPN@@@Z; auto_rc<DMMVIDPN const>::reset(DMMVIDPN const *)
0x1402d5052  mov     edi, 0C0000017h
0x1402d5057  jmp     loc_1402D680C
0x1402d505c  mov     rdx, [rsp+220h+Src]; Src
0x1402d5061  lea     rax, [r13+60h]
0x1402d5065  mov     [rbp+120h+var_150], rax
0x1402d5069  mov     eax, dword ptr [rbp+120h+var_1A0]
0x1402d506c  imul    r8, rax, 38h ; '8'; Size
0x1402d5070  call    memmove
0x1402d5075  mov     rax, [r15+78h]
0x1402d5079  lock inc dword ptr [rax+48h]
0x1402d507d  mov     rbx, [r15+78h]
0x1402d5081  mov     rcx, r14; this
0x1402d5084  mov     rdx, [r14+0CB8h]
0x1402d508b  mov     [rbp+120h+var_160], rbx
0x1402d508f  mov     [rbp+120h+var_E8], rdx
0x1402d5093  mov     [rbp+120h+var_F0], 0
0x1402d509a  call    ?IsLegacyDisplayStateSynchronization@DXGADAPTER@@QEBAEXZ; DXGADAPTER::IsLegacyDisplayStateSynchronization(void)
0x1402d509f  mov     r9d, [r14+0C3Ch]
0x1402d50a6  or      r15d, 0FFFFFFFFh
0x1402d50aa  mov     [rsp+220h+var_1B0], al
0x1402d50ae  mov     r11b, al
0x1402d50b1  mov     [rbp+120h+var_198], r9d
0x1402d50b5  test    rdx, rdx
0x1402d50b8  jz      loc_1402D5270
0x1402d50be  mov     ecx, [rdx+2F4h]
0x1402d50c4  mov     dl, [rbp+120h+arg_30]
0x1402d50ca  test    dl, dl
0x1402d50cc  jz      short loc_1402D50D4
0x1402d50ce  test    ecx, ecx
0x1402d50d0  jnz     short loc_1402D5142
0x1402d50d2  jmp     short loc_1402D50D8
0x1402d50d4  test    ecx, ecx
0x1402d50d6  jz      short loc_1402D5142
0x1402d50d8  mov     ecx, 1
0x1402d50dd  call    cs:__imp_WdLogSingleEntry0
0x1402d50e4  nop     dword ptr [rax+rax+00h]
0x1402d50e9  mov     [rsp+220h+var_1E0], 0
0x1402d50f2  lea     r9, aIDonotsuspendP; "(i_DoNotSuspend && pDisplayAdapter->Get"...
0x1402d50f9  mov     [rsp+220h+var_1E8], 0
0x1402d5102  mov     eax, 0A75h
0x1402d5107  mov     [rsp+220h+var_1F0], 0
0x1402d5110  mov     r8d, r15d
0x1402d5113  mov     qword ptr [rsp+220h+var_1F8], 0
0x1402d511c  mov     edx, 40002h
0x1402d5121  xor     ecx, ecx
0x1402d5123  mov     qword ptr [rsp+220h+var_200], rax
0x1402d5128  mov     cs:WdLogGlobalForLineNumber, eax
0x1402d512e  call    DxgkLogInternalTriageEvent
0x1402d5133  mov     r11b, [rsp+220h+var_1B0]
0x1402d5138  mov     r9d, [rbp+120h+var_198]
0x1402d513c  mov     dl, [rbp+120h+arg_30]
0x1402d5142  cmp     r9d, 898h
0x1402d5149  jge     short loc_1402D5166
0x1402d514b  mov     rcx, [r14+0CB8h]
0x1402d5152  xor     r9d, r9d
0x1402d5155  mov     r8d, r15d
0x1402d5158  lea     edx, [r9+8]
0x1402d515c  call    ?FlushScheduler@ADAPTER_RENDER@@QEAAJW4DXGADAPTER_FLUSHSCHEDULER_REASON@@IH@Z; ADAPTER_RENDER::FlushScheduler(DXGADAPTER_FLUSHSCHEDULER_REASON,uint,int)
0x1402d5161  jmp     loc_1402D526C
0x1402d5166  mov     rax, [r14+0CB0h]
0x1402d516d  xor     r8d, r8d
0x1402d5170  xor     r12d, r12d
0x1402d5173  xor     r15d, r15d
0x1402d5176  mov     r10d, [rax+60h]
0x1402d517a  test    dl, dl
0x1402d517c  jz      short loc_1402D51E2
0x1402d517e  xor     edx, edx
0x1402d5180  test    r10d, r10d
0x1402d5183  jz      loc_1402D5243
0x1402d5189  mov     r9d, [rsi+18h]
0x1402d518d  xor     ecx, ecx
0x1402d518f  or      r9d, [rsi+0Ch]
0x1402d5193  or      r9d, [rsi+8]
0x1402d5197  test    r11b, r11b
0x1402d519a  jnz     short loc_1402D51C2
0x1402d519c  mov     eax, 1
0x1402d51a1  shl     eax, cl
0x1402d51a3  test    r9d, eax
0x1402d51a6  jz      short loc_1402D51AF
0x1402d51a8  or      edx, eax
0x1402d51aa  or      r12d, eax
0x1402d51ad  jmp     short loc_1402D51B6
0x1402d51af  test    [rsi], eax
0x1402d51b1  jz      short loc_1402D51B6
0x1402d51b3  or      r8d, eax
0x1402d51b6  inc     ecx
0x1402d51b8  cmp     ecx, r10d
0x1402d51bb  jb      short loc_1402D519C
0x1402d51bd  jmp     loc_1402D5243
0x1402d51c2  mov     eax, 1
0x1402d51c7  shl     eax, cl
0x1402d51c9  test    eax, r9d
0x1402d51cc  jz      short loc_1402D51D2
0x1402d51ce  or      edx, eax
0x1402d51d0  jmp     short loc_1402D51D9
0x1402d51d2  test    [rsi], eax
0x1402d51d4  jz      short loc_1402D51D9
0x1402d51d6  or      r8d, eax
0x1402d51d9  inc     ecx
0x1402d51db  cmp     ecx, r10d
0x1402d51de  jb      short loc_1402D51C2
0x1402d51e0  jmp     short loc_1402D5243
0x1402d51e2  xor     edx, edx; unsigned int
0x1402d51e4  test    r10d, r10d
0x1402d51e7  jz      short loc_1402D5243
0x1402d51e9  mov     r9d, [rsi+18h]
0x1402d51ed  xor     ecx, ecx
0x1402d51ef  or      r9d, [rsi+0Ch]
0x1402d51f3  or      r9d, [rsi+8]
0x1402d51f7  test    r11b, r11b
0x1402d51fa  jnz     short loc_1402D5222
0x1402d51fc  mov     eax, 1
0x1402d5201  shl     eax, cl
0x1402d5203  test    r9d, eax
0x1402d5206  jz      short loc_1402D520F
0x1402d5208  or      edx, eax
0x1402d520a  or      r12d, eax
0x1402d520d  jmp     short loc_1402D5219
0x1402d520f  test    [rsi], eax
0x1402d5211  jz      short loc_1402D5219
0x1402d5213  or      r8d, eax
0x1402d5216  or      r15d, eax
0x1402d5219  inc     ecx
0x1402d521b  cmp     ecx, r10d
0x1402d521e  jb      short loc_1402D51FC
0x1402d5220  jmp     short loc_1402D5243
0x1402d5222  mov     eax, 1
0x1402d5227  shl     eax, cl
0x1402d5229  test    eax, r9d
0x1402d522c  jz      short loc_1402D5232
0x1402d522e  or      edx, eax
0x1402d5230  jmp     short loc_1402D523C
0x1402d5232  test    [rsi], eax
0x1402d5234  jz      short loc_1402D523C
0x1402d5236  or      r8d, eax; unsigned int
0x1402d5239  or      r15d, eax
0x1402d523c  inc     ecx
0x1402d523e  cmp     ecx, r10d
0x1402d5241  jb      short loc_1402D5222
0x1402d5243  mov     rcx, [r14+0CB8h]; this
0x1402d524a  mov     r9d, r12d; unsigned int
0x1402d524d  mov     dword ptr [rsp+220h+var_200], r15d; unsigned int
0x1402d5252  call    ?FlushPresentReferencesAndDisableOverlays@ADAPTER_RENDER@@QEAAJIIII@Z; ADAPTER_RENDER::FlushPresentReferencesAndDisableOverlays(uint,uint,uint,uint)
0x1402d5257  or      [rsi+40h], r12d
0x1402d525b  test    r15d, r15d
0x1402d525e  jz      short loc_1402D526C
0x1402d5260  mov     edx, r15d; unsigned int
0x1402d5263  lea     rcx, [rbp+120h+var_F0]; this
0x1402d5267  call    ?SetSuspendSourceMask@CVidSchSuspendResume@@QEAAXI@Z; CVidSchSuspendResume::SetSuspendSourceMask(uint)
0x1402d526c  mov     r9d, [rbp+120h+var_198]
0x1402d5270  mov     r8, [r14+0CB0h]
0x1402d5277  cmp     dword ptr [r8+60h], 0
0x1402d527c  jbe     loc_1402D539B
0x1402d5282  mov     ebx, [rbp+120h+var_F0]
0x1402d5285  xor     r15d, r15d
0x1402d5288  mov     dil, [rsp+220h+var_1B0]
0x1402d528d  mov     ecx, r15d
0x1402d5290  mov     r12d, 1
0x1402d5296  shl     r12d, cl
0x1402d5299  mov     ecx, [rsi+0Ch]
0x1402d529c  or      ecx, [rsi+8]
0x1402d529f  test    r12d, ecx
0x1402d52a2  jz      loc_1402D533B
  ... truncated ...
```
