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
        int a2,
        unsigned int a3,
        unsigned __int64 a4,
        struct D3DKMT_VIDPN_SOURCE_MASKS *a5,
        _BYTE *a6,
        unsigned __int8 a7,
        struct DXGDEVICE *a8,
        __int64 a9)
{
  DXGADAPTER *v12; // r14
  signed int v13; // eax
  signed int v14; // edi
  unsigned __int64 ClientCommittedVidPnRef; // r13
  unsigned __int64 v16; // rax
  __int64 v17; // rbx
  __int64 v18; // rdx
  unsigned __int8 IsLegacyDisplayStateSynchronization; // al
  __int64 v20; // rdx
  int v21; // r9d
  unsigned __int8 v22; // r11
  int v23; // ecx
  unsigned __int8 v24; // dl
  unsigned int v25; // r8d
  unsigned int v26; // r12d
  unsigned int v27; // r15d
  unsigned int v28; // r10d
  unsigned int v29; // edx
  unsigned int v30; // ecx
  int v31; // r9d
  int v32; // eax
  int v33; // eax
  unsigned int v34; // ecx
  int v35; // r9d
  int v36; // eax
  int v37; // eax
  ADAPTER_DISPLAY *v38; // r8
  int v39; // ebx
  unsigned int v40; // r15d
  int v41; // r12d
  __int64 v42; // rcx
  struct DXGDEVICE *VidPnSourceOwner; // r13
  unsigned __int8 v44; // r9
  VIDPN_MGR *v45; // r15
  unsigned int v46; // r15d
  __int64 v47; // rdi
  char *v48; // rbx
  _BYTE *v49; // r14
  __int64 v50; // r15
  char *v51; // r13
  bool v52; // zf
  char *v53; // rax
  __int128 v54; // xmm1
  __int128 v55; // xmm2
  __int64 v56; // xmm3_8
  bool v57; // dl
  int v58; // eax
  ADAPTER_DISPLAY *v59; // rcx
  int v60; // eax
  DMMVIDEOPRESENTTARGET *TargetById; // rax
  _OWORD *v62; // r8
  int v63; // edx
  unsigned __int8 v64; // r15
  _OWORD *v65; // rax
  __int128 v66; // xmm1
  __int128 v67; // xmm2
  __int64 v68; // xmm3_8
  ADAPTER_DISPLAY *v69; // rcx
  int v70; // eax
  unsigned int v71; // eax
  _BYTE *v72; // rdi
  unsigned int v73; // r9d
  char *v74; // rbx
  __int64 v75; // rax
  __int64 v76; // rdx
  char *v77; // rax
  __int128 v78; // xmm1
  __int128 v79; // xmm2
  __int64 v80; // xmm3_8
  __int64 i; // r13
  __int64 v82; // rdi
  int v83; // r12d
  struct DMMVIDEOPRESENTTARGET *v84; // rax
  struct DMMVIDEOPRESENTTARGET *v85; // r15
  int v86; // r12d
  int v87; // r8d
  int v88; // r9d
  int TargetLinkTrainingStatus; // eax
  int v90; // r9d
  int v91; // eax
  int v92; // eax
  DMMVIDPNPRESENTPATH *PathFromTarget; // rax
  ADAPTER_DISPLAY *v94; // rdi
  __int64 v95; // r15
  int v96; // r13d
  int v97; // eax
  const struct _DXGK_DISPLAYMODE_INFO *DisplayModeInfo; // rax
  __int64 v99; // rcx
  DMMVIDPNTOPOLOGY *v100; // rdi
  __int64 v101; // rdx
  __int64 v102; // r8
  int MostImportantVidPnPathTargetsFromSource; // eax
  bool v104; // r12
  unsigned int v105; // r10d
  struct DXGADAPTERALLOCATION *DisplayedPrimaryAllocation; // rax
  struct DXGADAPTERALLOCATION *v107; // rdi
  void *v108; // rax
  ADAPTER_RENDER *v109; // rcx
  int v110; // eax
  __int64 v111; // r9
  __int64 v112; // r8
  unsigned int v113; // edi
  int v114; // eax
  int v115; // r12d
  int v116; // edi
  __int64 CurrentProcess; // rax
  __int64 ProcessImageFileName; // rax
  __int64 j; // r12
  __int64 v120; // r15
  DMMVIDEOPRESENTTARGET *v121; // rax
  DMMVIDEOPRESENTTARGET *v122; // r13
  _BYTE *v123; // rdx
  __int64 v124; // r10
  int v125; // r8d
  int v126; // eax
  __int64 v127; // rcx
  __int64 v128; // r8
  ADAPTER_DISPLAY *v129; // r10
  __int64 v130; // r15
  struct DXGDEVICE *v131; // rdi
  int v132; // r12d
  ADAPTER_DISPLAY *v133; // rcx
  ADAPTER_DISPLAY *v134; // rdi
  const struct _D3DKMT_DISPLAYMODE *v135; // rax
  int v136; // eax
  unsigned int v137; // r13d
  int v138; // eax
  DMMVIDPNTOPOLOGY *v139; // rdi
  unsigned __int64 v140; // r8
  int v141; // eax
  __int64 v142; // r10
  __int64 v143; // r9
  __int64 v144; // r8
  unsigned int v145; // ecx
  bool v147[8]; // [rsp+20h] [rbp-E0h]
  bool v148[8]; // [rsp+28h] [rbp-D8h]
  unsigned __int8 v149; // [rsp+70h] [rbp-90h]
  char v150; // [rsp+70h] [rbp-90h]
  char v151; // [rsp+71h] [rbp-8Fh]
  void *Src; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v153; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v154; // [rsp+84h] [rbp-7Ch] BYREF
  int v155; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v156; // [rsp+8Ch] [rbp-74h]
  __int64 v157; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v158; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v159; // [rsp+A0h] [rbp-60h] BYREF
  int v160; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v161; // [rsp+ACh] [rbp-54h] BYREF
  struct DXGDEVICE *v162; // [rsp+B0h] [rbp-50h]
  VIDPN_MGR *v163; // [rsp+B8h] [rbp-48h]
  __int64 v164; // [rsp+C0h] [rbp-40h]
  char *v165; // [rsp+C8h] [rbp-38h] BYREF
  DMMVIDPNTOPOLOGY *v166; // [rsp+D0h] [rbp-30h]
  __int64 v167; // [rsp+D8h] [rbp-28h] BYREF
  struct _DXGKARG_DESCRIBEALLOCATION v168; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v169; // [rsp+110h] [rbp+10h] BYREF
  __int64 v170; // [rsp+118h] [rbp+18h]
  const struct DMMVIDPN *v171; // [rsp+120h] [rbp+20h] BYREF
  DXGADAPTER *ContainingAdapter; // [rsp+128h] [rbp+28h] BYREF
  int v173; // [rsp+130h] [rbp+30h] BYREF
  __int64 v174; // [rsp+138h] [rbp+38h]
  unsigned __int64 v175; // [rsp+140h] [rbp+40h]
  unsigned __int64 v176; // [rsp+148h] [rbp+48h] BYREF
  _OWORD v177[2]; // [rsp+150h] [rbp+50h] BYREF
  unsigned int v178[20]; // [rsp+170h] [rbp+70h] BYREF
  GUID ActivityId; // [rsp+1C0h] [rbp+C0h] BYREF

  v162 = a8;
  v170 = a9;
  v175 = a4;
  v156 = a3;
  v161 = a2;
  v163 = a1;
  v159 = (unsigned __int64)a6;
  v154 = 0;
  ContainingAdapter = VIDPN_MGR::GetContainingAdapter(a1);
  v12 = ContainingAdapter;
  if ( !DXGADAPTER::IsCoreResourceExclusiveOwner(ContainingAdapter) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 2510;
  }
  LODWORD(v169) = 0;
  *a6 = 0;
  v153 = 0;
  Src = 0;
  v157 = 0;
  v167 = 0;
  v13 = VIDPN_MGR::BuildSetTimingsPathInfoFromClientVidPn(
          a1,
          a2,
          a4,
          (__int64)a5,
          (unsigned int *)&v169,
          &v153,
          &Src,
          (__int64)&v157,
          (__int64)&v167);
  v14 = v13;
  v158 = v13;
  if ( v13 < 0 )
  {
    WdLogSingleEntry2(2, a4, v13);
    WdLogGlobalForLineNumber = 2542;
    goto LABEL_291;
  }
  if ( !v153 )
  {
    WdLogSingleEntry2(3, *((int *)v12 + 104), *((unsigned int *)v12 + 103));
    WdLogGlobalForLineNumber = 2560;
    goto LABEL_291;
  }
  if ( *((_DWORD *)a5 + 2) || *((_DWORD *)a5 + 3) || *((_DWORD *)a5 + 6) )
  {
    v151 = 1;
  }
  else
  {
    v151 = 0;
    if ( !*((_DWORD *)a5 + 10) && !*((_DWORD *)a5 + 8) && !*((_DWORD *)a5 + 13) )
    {
      DisplayScenarioJournalSetSetTimingPathInfo(*(_QWORD *)((char *)v12 + 412), 0, 56 * v153);
      v14 = 0;
      goto LABEL_291;
    }
  }
  v160 = 0;
  ClientCommittedVidPnRef = (unsigned __int64)VIDPN_MGR::AcquireLastClientCommittedVidPnRef(a1);
  v176 = ClientCommittedVidPnRef;
  if ( a4 )
    ClientCommittedVidPnRef = a4;
  v16 = 56LL * v153;
  v171 = (const struct DMMVIDPN *)ClientCommittedVidPnRef;
  if ( !is_mul_ok(v153, 0x38u) )
    v16 = -1;
  v165 = (char *)operator new[](v16, 0x4E506456u, 256);
  if ( !v165 )
  {
    WdLogSingleEntry1(6, v153);
    WdLogGlobalForLineNumber = 2622;
    wistd::unique_ptr<unsigned int [0],wistd::default_delete<unsigned int [0]>>::reset(&v165);
    auto_rc<DMMVIDPN const>::reset(&v176, 0);
    v14 = -1073741801;
    goto LABEL_291;
  }
  v166 = (DMMVIDPNTOPOLOGY *)(ClientCommittedVidPnRef + 96);
  memmove(v165, Src, 56LL * v153);
  _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)a1 + 15) + 72LL));
  v17 = *((_QWORD *)a1 + 15);
  v18 = *((_QWORD *)v12 + 407);
  v164 = v17;
  v174 = v18;
  v173 = 0;
  IsLegacyDisplayStateSynchronization = DXGADAPTER::IsLegacyDisplayStateSynchronization(v12);
  v21 = *((_DWORD *)v12 + 783);
  v149 = IsLegacyDisplayStateSynchronization;
  v22 = IsLegacyDisplayStateSynchronization;
  v155 = v21;
  if ( !v20 )
    goto LABEL_60;
  v23 = *(_DWORD *)(v20 + 756);
  v24 = a7;
  if ( a7 )
  {
    if ( !v23 )
      goto LABEL_26;
  }
  else if ( v23 )
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
    v22 = v149;
    v21 = v155;
    v24 = a7;
  }
  if ( v21 >= 2200 )
  {
    v25 = 0;
    v26 = 0;
    v27 = 0;
    v28 = *(_DWORD *)(*((_QWORD *)v12 + 406) + 96LL);
    if ( v24 )
    {
      v29 = 0;
      if ( v28 )
      {
        v30 = 0;
        v31 = *((_DWORD *)a5 + 2) | *((_DWORD *)a5 + 3) | *((_DWORD *)a5 + 6);
        if ( v22 )
        {
          do
          {
            v33 = 1 << v30;
            if ( (v31 & (1 << v30)) != 0 )
            {
              v29 |= v33;
            }
            else if ( (v33 & *(_DWORD *)a5) != 0 )
            {
              v25 |= v33;
            }
            ++v30;
          }
          while ( v30 < v28 );
        }
        else
        {
          do
          {
            v32 = 1 << v30;
            if ( ((1 << v30) & v31) != 0 )
            {
              v29 |= v32;
              v26 |= v32;
            }
            else if ( (v32 & *(_DWORD *)a5) != 0 )
            {
              v25 |= v32;
            }
            ++v30;
          }
          while ( v30 < v28 );
        }
      }
    }
    else
    {
      v29 = 0;
      if ( v28 )
      {
        v34 = 0;
        v35 = *((_DWORD *)a5 + 2) | *((_DWORD *)a5 + 3) | *((_DWORD *)a5 + 6);
        if ( v22 )
        {
          do
          {
            v37 = 1 << v34;
            if ( (v35 & (1 << v34)) != 0 )
            {
              v29 |= v37;
            }
            else if ( (v37 & *(_DWORD *)a5) != 0 )
            {
              v25 |= v37;
              v27 |= v37;
            }
            ++v34;
          }
          while ( v34 < v28 );
        }
        else
        {
          do
          {
            v36 = 1 << v34;
            if ( ((1 << v34) & v35) != 0 )
            {
              v29 |= v36;
              v26 |= v36;
            }
            else if ( (v36 & *(_DWORD *)a5) != 0 )
            {
              v25 |= v36;
              v27 |= v36;
            }
            ++v34;
          }
          while ( v34 < v28 );
        }
      }
    }
    ADAPTER_RENDER::FlushPresentReferencesAndDisableOverlays(*((ADAPTER_RENDER **)v12 + 407), v29, v25, v26, v27);
    *((_DWORD *)a5 + 16) |= v26;
    if ( v27 )
      CVidSchSuspendResume::SetSuspendSourceMask((CVidSchSuspendResume *)&v173, v27);
  }
  else
  {
    ADAPTER_RENDER::FlushScheduler(*((_QWORD *)v12 + 407), 8, 0xFFFFFFFFLL);
  }
  v21 = v155;
LABEL_60:
  v38 = (ADAPTER_DISPLAY *)*((_QWORD *)v12 + 406);
  if ( !*((_DWORD *)v38 + 24) )
    goto LABEL_85;
  v39 = v173;
  v40 = 0;
  do
  {
    v41 = 1 << v40;
    if ( ((*((_DWORD *)a5 + 2) | *((_DWORD *)a5 + 3)) & (1 << v40)) != 0 )
    {
      v42 = *((_QWORD *)v12 + 407);
      if ( v42 && v21 < 2200 )
      {
        ADAPTER_RENDER::FlushScheduler(v42, 8, v40);
        v38 = (ADAPTER_DISPLAY *)*((_QWORD *)v12 + 406);
      }
      if ( v162 && v170 )
      {
        VidPnSourceOwner = ADAPTER_DISPLAY::GetVidPnSourceOwner(v38, v40);
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
        v44 = v39 || a7;
        ADAPTER_DISPLAY::DisablePrimaryOnDevice(*((ADAPTER_DISPLAY **)v12 + 406), VidPnSourceOwner, v40, v44);
      }
    }
LABEL_78:
    if ( ((*((_DWORD *)a5 + 6) | *((_DWORD *)a5 + 2) | *((_DWORD *)a5 + 3)) & v41) != 0
      && *((_QWORD *)v12 + 407)
      && *((_BYTE *)v12 + 3177)
      && v149 )
    {
      ADAPTER_DISPLAY::DisableMPOPlanes(*((ADAPTER_DISPLAY **)v12 + 406), v40, 0);
      *((_DWORD *)a5 + 16) |= v41;
    }
    v38 = (ADAPTER_DISPLAY *)*((_QWORD *)v12 + 406);
    ++v40;
    v21 = v155;
  }
  while ( v40 < *((_DWORD *)v38 + 24) );
  v17 = v164;
  v14 = v158;
  ClientCommittedVidPnRef = (unsigned __int64)v171;
LABEL_85:
  v45 = v163;
  if ( *((_DWORD *)a5 + 5) )
    VIDPN_MGR::RequestPowerStateForTargets(v163, (const struct DMMVIDPN *)ClientCommittedVidPnRef);
  if ( DXGADAPTER::UsingSetTimingsFromVidPn(v12) )
  {
    v150 = 0;
    if ( !v151 )
      goto LABEL_91;
    v46 = v156;
    v177[0] = 0;
    memset(&v168, 0, 40);
    if ( v156 == 4 )
      DisplayLogSetMonitorPowerStage(0, 16, 0, v177);
    *(_QWORD *)&v168.Format = &v154;
    v168.MultisampleMethod.NumQualityLevels = v153;
    v168.hAllocation = (HANDLE)(ClientCommittedVidPnRef & -(__int64)(ClientCommittedVidPnRef != -88));
    v59 = (ADAPTER_DISPLAY *)*((_QWORD *)v12 + 406);
    *(_QWORD *)&v168.RefreshRate.Denominator = Src;
    v60 = ADAPTER_DISPLAY::DdiSetTimingsFromVidPn(v59, (struct _DXGKARG_SETTIMINGSFROMVIDPN *)&v168);
    v14 = v60;
    if ( v60 < 0 )
    {
      WdLogSingleEntry3(2, *((int *)v12 + 104), *((unsigned int *)v12 + 103), v60);
      WdLogGlobalForLineNumber = 2857;
    }
    if ( v153 == 1
      && ((v46 - 1) & 0xFFFFFFFD) == 0
      && (v14 < 0 || (*((_DWORD *)Src + 8) & 0xF000000) == 0xD000000)
      && (*((_DWORD *)Src + 3) & 4) != 0
      && ((v154 & 1) != 0 || (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v12 + 27) + 64LL) + 3652LL) & 3) != 0) )
    {
      TargetById = DMMVIDEOPRESENTTARGETSET::GetTargetById((DMMVIDEOPRESENTTARGETSET *)v17, *(_DWORD *)Src);
      if ( TargetById )
      {
        if ( !DMMVIDEOPRESENTTARGET::IsTargetForceable(TargetById) )
        {
          DisplayScenarioJournalSetSetTimingPathInfo(*(_QWORD *)((char *)v12 + 412), (unsigned int)v14, 56 * v153);
          v62 = v165;
          *((_DWORD *)v165 + 3) = *((_DWORD *)v165 + 3) & 0xFFFFFFF0 | 9;
          v63 = *((_DWORD *)a5 + 1);
          *((_DWORD *)a5 + 6) = v63 & (*((_DWORD *)a5 + 5) ^ *((_DWORD *)a5 + 6));
          *((_DWORD *)a5 + 5) = 0;
          *((_DWORD *)a5 + 20) = v63;
          if ( v14 < 0 )
            v64 = 0;
          else
            v64 = v154 & 1;
          v65 = Src;
          v154 = 0;
          v66 = v62[1];
          v67 = v62[2];
          v68 = *((_QWORD *)v62 + 6);
          *(_OWORD *)Src = *v62;
          v65[1] = v66;
          v65[2] = v67;
          *((_QWORD *)v65 + 6) = v68;
          *(_QWORD *)&v168.Width = 0;
          v168.hAllocation = (HANDLE)(ClientCommittedVidPnRef & -(__int64)(ClientCommittedVidPnRef != -88));
          *(_QWORD *)&v168.Format = &v154;
          v168.MultisampleMethod.NumQualityLevels = v153;
          v168.RefreshRate.Numerator = 0;
          v69 = (ADAPTER_DISPLAY *)*((_QWORD *)v12 + 406);
          *(_QWORD *)&v168.RefreshRate.Denominator = Src;
          v70 = ADAPTER_DISPLAY::DdiSetTimingsFromVidPn(v69, (struct _DXGKARG_SETTIMINGSFROMVIDPN *)&v168);
          v14 = v70;
          if ( v70 < 0 )
          {
            WdLogSingleEntry4(2, *(unsigned int *)Src, *((int *)v12 + 104), *((unsigned int *)v12 + 103), v70);
            WdLogGlobalForLineNumber = 2940;
          }
          DxgkLogCodePointPacket(
            104,
            *(unsigned int *)Src,
            (unsigned int)v14,
            *((_BYTE *)Src + 35) & 0xF,
            *(_QWORD *)((char *)v12 + 412));
          v154 = v154 & 0xFFFFFFFE | ((unsigned __int8)v154 | v64) & 1;
          v46 = v156;
        }
      }
    }
    if ( v46 == 4 )
      DisplayLogSetMonitorPowerStage(0, 2147483664LL, (unsigned int)v14, v177);
  }
  else
  {
    v150 = 1;
    if ( v151 || *((_DWORD *)a5 + 10) )
    {
      v151 = 1;
      v57 = a7 || v173;
      v58 = VIDPN_MGR::CommitVidPnOnAdapter(
              v45,
              v161,
              v156,
              ClientCommittedVidPnRef,
              v153,
              Src,
              v157,
              a5,
              &v160,
              v167,
              &v154,
              v162,
              v170,
              v57);
      v14 = v58;
      if ( v58 < 0 )
      {
        WdLogSingleEntry3(2, *((int *)v12 + 104), *((unsigned int *)v12 + 103), v58);
        WdLogGlobalForLineNumber = 3002;
      }
    }
    else
    {
      v151 = 0;
    }
LABEL_91:
    v46 = v156;
  }
  *(_DWORD *)&v147[4] = HIDWORD(Src);
  DisplayScenarioJournalSetSetTimingPathInfo(*(_QWORD *)((char *)v12 + 412), (unsigned int)v14, 56 * v153);
  LogSetTimingSourceMask(v12, a5);
  if ( v151 )
  {
    if ( v14 < 0 )
    {
      *((_DWORD *)a5 + 21) = -1;
      FillFailedStatus(a5, v14);
      v73 = 0;
      if ( v153 )
      {
        v74 = v165;
        do
        {
          v75 = v73++;
          v76 = 56 * v75;
          v77 = (char *)Src;
          v78 = *(_OWORD *)&v74[v76 + 16];
          v79 = *(_OWORD *)&v74[v76 + 32];
          v80 = *(_QWORD *)&v74[v76 + 48];
          *(_OWORD *)((char *)Src + v76) = *(_OWORD *)&v74[v76];
          *(_OWORD *)&v77[v76 + 16] = v78;
          *(_OWORD *)&v77[v76 + 32] = v79;
          *(_QWORD *)&v77[v76 + 48] = v80;
          *(_DWORD *)((char *)Src + v76 + 32) = *(_DWORD *)((_BYTE *)Src + v76 + 32) & 0xF0FFFFFF | 0xD000000;
          *(_DWORD *)((char *)Src + v76 + 16) |= 1u;
        }
        while ( v73 < v153 );
        v17 = v164;
      }
      v72 = (_BYTE *)v159;
      v71 = 1;
      v154 = 1;
      *(_BYTE *)v159 = (((v46 - 1) & 0xFFFFFFFD) != 0 ? 2 : 0) | *(_BYTE *)v159 & 0xFD;
    }
    else
    {
      v47 = 0;
      if ( v153 )
      {
        v48 = v165;
        v49 = (_BYTE *)v159;
        do
        {
          v50 = 56LL * (unsigned int)v47;
          v51 = &v48[v50];
          v52 = VIDPN_MGR::CheckDdiSetTimingsViolationOnPathInfo(
                  v163,
                  (struct _DXGK_SET_TIMING_PATH_INFO *)&v48[v50],
                  (struct _DXGK_SET_TIMING_PATH_INFO *)((char *)Src + v50)) == 0;
          v53 = (char *)Src;
          if ( v52 )
          {
            v54 = *((_OWORD *)v51 + 1);
            v55 = *((_OWORD *)v51 + 2);
            v56 = *((_QWORD *)v51 + 6);
            *(_OWORD *)((char *)Src + v50) = *(_OWORD *)v51;
            *(_OWORD *)&v53[v50 + 16] = v54;
            *(_OWORD *)&v53[v50 + 32] = v55;
            *(_QWORD *)&v53[v50 + 48] = v56;
            *(_DWORD *)((char *)Src + v50 + 32) = *(_DWORD *)((_BYTE *)Src + v50 + 32) & 0xF0FFFFFF | 0xD000000;
            *((_DWORD *)a5 + *(unsigned int *)(v157 + 4 * v47) + 22) = -1073741437;
            *((_DWORD *)a5 + 21) |= 1 << *(_DWORD *)(v157 + 4 * v47);
          }
          else if ( (*(_DWORD *)((_BYTE *)Src + v50 + 32) & 0xF000000) == 0xD000000 )
          {
            *((_DWORD *)a5 + *(unsigned int *)(v157 + 4 * v47) + 22) = -1073741506;
            *((_DWORD *)a5 + 21) |= 1 << *(_DWORD *)(v157 + 4 * v47);
            *v49 = (((v156 - 1) & 0xFFFFFFFD) != 0 ? 2 : 0) | *v49 & 0xFD;
          }
          v47 = (unsigned int)(v47 + 1);
        }
        while ( (unsigned int)v47 < v153 );
        v17 = v164;
        v12 = ContainingAdapter;
      }
      v71 = v154;
      v72 = (_BYTE *)v159;
    }
    if ( (v71 & 0xFFFFFFFE) != 0 )
    {
      WdLogSingleEntry1(1, (unsigned __int64)v71 >> 1);
      LOBYTE(v71) = v154;
      WdLogGlobalForLineNumber = 3124;
    }
    if ( (v71 & 1) != 0 )
      *v72 |= 1u;
  }
  ActivityId = 0;
  EtwActivityIdControl(3u, &ActivityId);
  for ( i = 0; (unsigned int)i < v153; i = (unsigned int)(i + 1) )
  {
    v82 = 56LL * (unsigned int)i;
    v83 = *(_DWORD *)(v157 + 4 * i);
    LODWORD(v159) = v83;
    v84 = DMMVIDEOPRESENTTARGETSET::GetTargetById((DMMVIDEOPRESENTTARGETSET *)v17, *(_DWORD *)((char *)Src + v82));
    v85 = v84;
    if ( v84 )
    {
      v86 = 1 << v83;
      if ( v151 )
      {
        LogMonitorHandleOnOffState(*((_QWORD *)v84 + 14), &ActivityId, (*(_DWORD *)((char *)Src + v82 + 12) >> 2) & 1);
        if ( !v150 )
        {
          DxgkLogCodePointPacket(
            88,
            *(unsigned int *)((char *)Src + v82),
            *((_BYTE *)Src + v82 + 35) & 0xF | 0x80000000,
            *(unsigned int *)((char *)Src + v82 + 24),
            *(_QWORD *)((char *)v12 + 412));
          if ( (unsigned int)dword_1401605E8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1401605E8, 0x4000) )
          {
            v161 = *((_BYTE *)Src + v82 + 35) & 0xF | 0x80000000;
            ContainingAdapter = *(DXGADAPTER **)((char *)Src + v82 + 24);
            v158 = *(_DWORD *)((char *)Src + v82);
            v171 = *(const struct DMMVIDPN **)((char *)v12 + 412);
            v155 = 1;
            *(_QWORD *)&v177[0] = 0x1000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
              (_DWORD)Src,
              (unsigned int)word_140145FFA,
              v87,
              v88,
              (__int64)v177,
              (__int64)&v155,
              (__int64)&v171,
              (__int64)&v158,
              (__int64)&ContainingAdapter,
              (__int64)&v161);
          }
          DxgkLogCodePointPacket(
            89,
            *(unsigned int *)((char *)Src + v82),
            *(unsigned int *)((char *)Src + v82 + 48),
            0,
            *(_QWORD *)((char *)v12 + 412));
        }
        TargetLinkTrainingStatus = DMMVIDEOPRESENTTARGET::GetTargetLinkTrainingStatus(v85, 0);
        if ( TargetLinkTrainingStatus != v90 )
          *((_DWORD *)a5 + 9) |= v86;
        DMMVIDEOPRESENTTARGET::UpdateTargetLinkTrainingStatus(
          v85,
          *(_QWORD *)((char *)Src + v82 + 24),
          *((_BYTE *)Src + v82 + 35) & 0xF);
        if ( (*(_DWORD *)((_BYTE *)Src + v82 + 32) & 0xF000000) == 0xC000000 )
          DMMVIDEOPRESENTTARGET::StartLinkTrainingTimer(v85, 1u);
        else
          DMMVIDEOPRESENTTARGET::CancelLinkTrainingTimer(v85);
        *((_BYTE *)v85 + 414) = 0;
      }
      else
      {
        v91 = DMMVIDEOPRESENTTARGET::GetTargetLinkTrainingStatus(v84, 0);
        *(_DWORD *)((char *)Src + v82 + 32) ^= (*(_DWORD *)((char *)Src + v82 + 32) ^ (v91 << 24)) & 0xF000000;
      }
      if ( (*(_DWORD *)((_BYTE *)Src + v82 + 12) & 4) != 0 && (v86 & *((_DWORD *)a5 + 18)) == 0 )
      {
        v92 = *((_DWORD *)a5 + 21) | v160;
        if ( !_bittest(&v92, v159) )
        {
          DMMVIDEOPRESENTTARGET::SetTargetActivated(v85, 1u, 1u);
          if ( ((*((_DWORD *)a5 + 2) | *((_DWORD *)a5 + 6) | *((_DWORD *)a5 + 8) | *((_DWORD *)a5 + 9)) & v86) != 0
            && (*(_DWORD *)((_BYTE *)Src + v82 + 32) & 0xF000000) == 0xE000000 )
          {
            PathFromTarget = DMMVIDPNTOPOLOGY::GetPathFromTarget(v166, *(_DWORD *)((char *)Src + v82));
            DMMVIDPNPRESENTPATH::SetDriverGammaRamp(PathFromTarget, 0);
          }
        }
      }
      if ( (*(_DWORD *)((_BYTE *)Src + v82 + 32) & 0xF000000) != 0xD000000
        && ((*((_DWORD *)a5 + 2) | *((_DWORD *)a5 + 4)) & v86) != 0 )
      {
        MonitorSetLastWireformatAndColorspace(
          *((struct HDXGMONITOR__ **)v85 + 14),
          *(union _D3DKMDT_WIRE_FORMAT_AND_PREFERENCE *)((char *)Src + v82 + 8),
          *(enum _D3DDDI_OUTPUT_WIRE_COLOR_SPACE_TYPE *)((char *)Src + v82 + 4));
      }
    }
  }
  CVidSchSuspendResume::Resume((CVidSchSuspendResume *)&v173);
  v94 = (ADAPTER_DISPLAY *)*((_QWORD *)v12 + 406);
  if ( *((_DWORD *)v94 + 24) )
  {
    v95 = 0;
    while ( 1 )
    {
      memset(v178, 0, sizeof(v178));
      v96 = 1 << v95;
      if ( ((1 << v95) & *((_DWORD *)a5 + 3)) != 0 )
      {
        v155 = 2;
      }
      else if ( (v96 & *((_DWORD *)a5 + 10)) != 0 )
      {
        v155 = 4;
      }
      else
      {
        v97 = ~*((_DWORD *)a5 + 8);
        v155 = 0;
        if ( (*((_DWORD *)a5 + 2) & v97 & v96) != 0 )
          v155 = (*(_DWORD *)a5 & v96) != 0 ? 3 : 1;
      }
      DisplayModeInfo = ADAPTER_DISPLAY::GetDisplayModeInfo(v94, v95);
      v99 = *((_DWORD *)a5 + 13) | (unsigned int)(*((_DWORD *)a5 + 2) | *((_DWORD *)a5 + 10));
      v100 = v166;
      *(_OWORD *)v178 = *(_OWORD *)DisplayModeInfo;
      *(_OWORD *)&v178[4] = *((_OWORD *)DisplayModeInfo + 1);
      *(_OWORD *)&v178[8] = *((_OWORD *)DisplayModeInfo + 2);
      *(_OWORD *)&v178[12] = *((_OWORD *)DisplayModeInfo + 3);
      *(_OWORD *)&v178[16] = *((_OWORD *)DisplayModeInfo + 4);
      if ( ((unsigned int)v99 & v96) != 0 )
        DMMVIDPNTOPOLOGY::GetDisplayModeFromVidPnSource(
          v166,
          ((v156 - 1) & 0xFFFFFFFD) == 0,
          v95,
          (struct _DXGK_DISPLAYMODE_INFO *)v178);
      if ( (v96 & *((_DWORD *)a5 + 21)) != 0 )
        goto LABEL_228;
      if ( (v96 & v160) == 0 )
        break;
LABEL_230:
      v94 = (ADAPTER_DISPLAY *)*((_QWORD *)v12 + 406);
      v95 = (unsigned int)(v95 + 1);
      if ( (unsigned int)v95 >= *((_DWORD *)v94 + 24) )
      {
        v17 = v164;
        goto LABEL_232;
      }
    }
    if ( (v96 & *((_DWORD *)a5 + 10)) != 0 )
    {
      ADAPTER_DISPLAY::SetDisplayModeInfo(
        *((ADAPTER_DISPLAY **)v12 + 406),
        v95,
        (const struct _DXGK_DISPLAYMODE_INFO *const)v178);
      OUTPUTDUPL_MGR::MoveContextToPendingDestroyList(
        *(_QWORD *)(*((_QWORD *)v12 + 406) + 120LL),
        (unsigned int)v95,
        0,
        0,
        0,
        1);
      v177[0] = 0xBu;
      v177[1] = 0;
      if ( (int)DxgkStatusChangeNotify((int *)v177, v101, v102) < 0 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 3395;
        DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"NT_SUCCESS(NotificationStatus)", 3395, 0, 0, 0, 0);
      }
    }
    v99 = *((_DWORD *)a5 + 13)
        | *((_DWORD *)a5 + 2)
        | *((_DWORD *)a5 + 3)
        | *((_DWORD *)a5 + 6)
        | (unsigned int)(*((_DWORD *)a5 + 8) | *((_DWORD *)a5 + 9));
    if ( ((unsigned int)v99 & v96) != 0 )
    {
      v158 = 0;
      MostImportantVidPnPathTargetsFromSource = GetMostImportantVidPnPathTargetsFromSource(v100, v95, &v158);
      if ( (int)(MostImportantVidPnPathTargetsFromSource + 0x80000000) >= 0
        && MostImportantVidPnPathTargetsFromSource != -1071774919 )
      {
        WdLogSingleEntry0(1);
        v104 = 0;
        WdLogGlobalForLineNumber = 3430;
        goto LABEL_184;
      }
      v104 = 0;
      if ( MostImportantVidPnPathTargetsFromSource < 0 || (v105 = v158, v158 == -1) || (v111 = 0, !v153) )
      {
LABEL_184:
        v105 = -1;
      }
      else
      {
        while ( 1 )
        {
          v104 = 0;
          if ( (_DWORD)v95 == *(_DWORD *)(v157 + 4 * v111) )
          {
            v112 = 56LL * (unsigned int)v111;
            if ( v158 == *(_DWORD *)((char *)Src + v112)
              && (*(_DWORD *)((_BYTE *)Src + v112 + 32) & 0xF000000) == 0xE000000
              && (*(_DWORD *)((_BYTE *)Src + v112 + 12) & 4) != 0
              && (v96 & *((_DWORD *)a5 + 18)) == 0 )
            {
              break;
            }
          }
          v111 = (unsigned int)(v111 + 1);
          if ( (unsigned int)v111 >= v153 )
            goto LABEL_184;
        }
        *((_DWORD *)a5 + 19) |= v96;
        v104 = 1;
      }
      ADAPTER_DISPLAY::SetVidPnPrimaryTarget(*((ADAPTER_DISPLAY **)v12 + 406), v95, v105);
      if ( (v96 & *((_DWORD *)a5 + 2)) != 0 )
      {
        v52 = *((_QWORD *)v12 + 407) == 0;
        v178[11] = 1;
        *(_QWORD *)&v178[12] = 1;
        if ( !v52 )
        {
          DisplayedPrimaryAllocation = ADAPTER_DISPLAY::GetDisplayedPrimaryAllocation(
                                         *((ADAPTER_DISPLAY **)v12 + 406),
                                         v95);
          v107 = DisplayedPrimaryAllocation;
          if ( DisplayedPrimaryAllocation )
          {
            if ( (*((_BYTE *)DisplayedPrimaryAllocation + 4) & 0x10) != 0 )
              v107 = 0;
            if ( v107 )
            {
              v108 = (void *)*((_QWORD *)v107 + 2);
              v109 = (ADAPTER_RENDER *)*((_QWORD *)v12 + 407);
              memset(&v168.Width, 0, 40);
              v168.hAllocation = v108;
              v110 = ADAPTER_RENDER::DdiDescribeAllocation(v109, &v168);
              if ( v110 < 0 )
              {
                WdLogSingleEntry3(3, v107, (unsigned int)v95, v110);
                WdLogGlobalForLineNumber = 3540;
              }
              else if ( v168.Width == v178[0]
                     && v168.Height == v178[1]
                     && v168.Format == v178[2]
                     && *(_QWORD *)&v168.RefreshRate == *(_QWORD *)&v178[14]
                     && (((unsigned __int8)~(v178[10] >> 4) ^ (unsigned __int8)~(*((_DWORD *)v107 + 1) >> 12)) & 1) == 0 )
              {
                *(D3DDDI_MULTISAMPLINGMETHOD *)&v178[11] = v168.MultisampleMethod;
                v178[13] = v168.PrivateDriverFormatAttribute;
              }
              else if ( v150 || (*((_DWORD *)v107 + 1) & 2) == 0 )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 3528;
              }
            }
          }
        }
      }
      v113 = v156;
      v114 = ADAPTER_DISPLAY::SetVidPnSourceActive(
               *((ADAPTER_DISPLAY **)v12 + 406),
               v95,
               v104,
               (const struct _DXGK_DISPLAYMODE_INFO *)v178,
               v156 == 4,
               a7 != 0);
      v115 = v114;
      if ( v114 >= 0 )
      {
        ADAPTER_DISPLAY::MarkCommitVidPnOnModeChange(*((ADAPTER_DISPLAY **)v12 + 406), v95, 0);
        if ( (v96 & *((_DWORD *)a5 + 3)) != 0 )
        {
          if ( ((v113 - 1) & 0xFFFFFFFD) != 0 )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 3574;
          }
          ADAPTER_DISPLAY::SetPartOfDesktop(*((ADAPTER_DISPLAY **)v12 + 406), v95, 0);
          ADAPTER_DISPLAY::SetContentRect(*((ADAPTER_DISPLAY **)v12 + 406), v95, &stru_1401635A8);
          ADAPTER_DISPLAY::SetCddInterface(*((ADAPTER_DISPLAY **)v12 + 406), v95, 0);
          ADAPTER_DISPLAY::SetHdrEnabled(*((ADAPTER_DISPLAY **)v12 + 406), v95, 0);
        }
        else
        {
          v159 = 0;
          if ( DMMVIDPNTOPOLOGY::GetNumPathsFromSource(v166, v95, &v159) < 0 || !v159 )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 3587;
          }
          v99 = (unsigned int)(*((_DWORD *)a5 + 13) | *((_DWORD *)a5 + 2));
          if ( ((unsigned int)v99 & v96) != 0 )
          {
            if ( ((v113 - 1) & 0xFFFFFFFD) == 0 )
              ADAPTER_DISPLAY::SetPartOfDesktop(*((ADAPTER_DISPLAY **)v12 + 406), v95, 1u);
            ADAPTER_DISPLAY::SetDisplayModeInfo(
              *((ADAPTER_DISPLAY **)v12 + 406),
              v95,
              (const struct _DXGK_DISPLAYMODE_INFO *const)v178);
            ADAPTER_DISPLAY::SetLastCddIntegerVSync(*((ADAPTER_DISPLAY **)v12 + 406), v95, v178[3]);
            ADAPTER_DISPLAY::DetermineScalingCapabilities(*((ADAPTER_DISPLAY **)v12 + 406), v95);
            ADAPTER_DISPLAY::SetHdrEnabled(*((ADAPTER_DISPLAY **)v12 + 406), v95, (v96 & *((_DWORD *)a5 + 64)) != 0);
            if ( v162 && v170 )
              ADAPTER_DISPLAY::UpdateOneCddPrimaryPrivateDriverData(
                *((ADAPTER_DISPLAY **)v12 + 406),
                v95,
                *(struct DXGADAPTER **)(*((_QWORD *)v162 + 2) + 16LL));
          }
        }
      }
      else
      {
        WdLogSingleEntry3(2, v12, (unsigned int)v95, v114);
        WdLogGlobalForLineNumber = 3558;
        *((_DWORD *)a5 + v95 + 22) = v115;
        *((_DWORD *)a5 + 21) |= v96;
      }
    }
LABEL_228:
    v116 = v155;
    if ( v155 )
    {
      CurrentProcess = PsGetCurrentProcess(v99);
      ProcessImageFileName = PsGetProcessImageFileName(CurrentProcess);
      *(_DWORD *)v147 = *((_DWORD *)a5 + v95 + 22);
      VIDPN_MGR::CacheDisplayModeChangeRequest(
        v163,
        (unsigned int)v95,
        v178,
        1,
        *(_QWORD *)v147,
        v116,
        *(_DWORD *)(*((_QWORD *)v12 + 406) + 424LL),
        ProcessImageFileName);
    }
    goto LABEL_230;
  }
LABEL_232:
  for ( j = 0; (unsigned int)j < v153; j = (unsigned int)(j + 1) )
  {
    v120 = 56LL * (unsigned int)j;
    v121 = DMMVIDEOPRESENTTARGETSET::GetTargetById((DMMVIDEOPRESENTTARGETSET *)v17, *(_DWORD *)((char *)Src + v120));
    v122 = v121;
    if ( v121 )
    {
      v123 = Src;
      if ( (*(_DWORD *)((_BYTE *)Src + v120 + 12) & 4) == 0
        || (v124 = v157, v125 = 1 << *(_DWORD *)(v157 + 4 * j), (v125 & *((_DWORD *)a5 + 18)) != 0)
        || (v125 & *((_DWORD *)a5 + 21)) != 0 )
      {
        DMMVIDEOPRESENTTARGET::SetTargetActivated(
          v121,
          0,
          (*(_DWORD *)((_BYTE *)Src + v120 + 32) & 0xF000000) == 201326592);
        v123 = Src;
        v124 = v157;
      }
      if ( !v150
        && *((_BYTE *)v122 + 416)
        && ((*(_DWORD *)&v123[v120 + 32] & 0xF000000) != 0xE000000 || v123[v120 + 48] != 0xFF) )
      {
        v126 = ADAPTER_DISPLAY::SetVidPnSourceVisibility(
                 *((ADAPTER_DISPLAY **)v12 + 406),
                 *(_DWORD *)(v124 + 4 * j),
                 0,
                 0x800u,
                 a7);
        if ( v126 < 0 )
        {
          WdLogSingleEntry3(2, v12, *(unsigned int *)(v157 + 4 * j), v126);
          WdLogGlobalForLineNumber = 3695;
        }
        if ( (*((_DWORD *)Src + 14 * (unsigned int)j + 8) & 0xF000000) == 0xE000000 )
        {
          v127 = *((_QWORD *)v12 + 407);
          if ( v127 )
          {
            VIDSCH_EXPORT::VidSchRequestDeferredVidPnSourceVisibility(
              *(VIDSCH_EXPORT **)(v127 + 736),
              *(struct _VIDSCH_GLOBAL **)(v127 + 744),
              *(_DWORD *)(v157 + 4 * j));
          }
          else
          {
            v128 = *(_QWORD *)(*((_QWORD *)v12 + 406) + 464LL);
            if ( v128 )
              _InterlockedExchange(
                (volatile __int32 *)(3040LL * *(unsigned int *)(v157 + 4 * j) + *(_QWORD *)(v128 + 8) + 1080),
                1);
          }
        }
      }
      *((_BYTE *)v122 + 416) = 0;
    }
    else if ( (*(_DWORD *)((_BYTE *)Src + v120 + 12) & 4) != 0 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 3739;
    }
    if ( (*((_DWORD *)Src + 14 * (unsigned int)j + 4) & 1) != 0 )
      *((_DWORD *)a5 + 16) |= 1 << *(_DWORD *)(v157 + 4 * j);
  }
  auto_rc<DMMVIDPN>::reset((char *)v163 + 320, 0);
  CVidSchSuspendResume::Resume((CVidSchSuspendResume *)&v173);
  v129 = (ADAPTER_DISPLAY *)*((_QWORD *)v12 + 406);
  if ( *((_DWORD *)v129 + 24) )
  {
    v130 = 0;
    v131 = v162;
    do
    {
      v132 = 1 << v130;
      if ( ((1 << v130) & *((_DWORD *)a5 + 15)) != 0 )
        ADAPTER_DISPLAY::InvalidateDisplayModeListCacheOnSource(v129, v130);
      if ( (v132 & *((_DWORD *)a5 + 16)) != 0 )
        DXGADAPTER::NotifyMultiPlaneOverlayDisable(v12, v130);
      if ( v131 && !v150 )
      {
        if ( ADAPTER_DISPLAY::GetCddPrimaryAllocation(*((ADAPTER_DISPLAY **)v12 + 406), v130, 0)
          && ADAPTER_DISPLAY::IsCddPrimaryStale(*((ADAPTER_DISPLAY **)v12 + 406), v130) )
        {
          ADAPTER_DISPLAY::DestroyCddAllocations(v133, v131, v130);
        }
        v134 = (ADAPTER_DISPLAY *)*((_QWORD *)v12 + 406);
        v135 = (const struct _D3DKMT_DISPLAYMODE *)ADAPTER_DISPLAY::GetDisplayModeInfo(v134, v130);
        ADAPTER_DISPLAY::SetCddDisplayMode(v134, v130, v135);
        v131 = v162;
      }
      if ( (v132 & *((_DWORD *)a5 + 21)) != 0 )
      {
        v136 = *((_DWORD *)a5 + v130 + 40);
        if ( (v136 & 7) != 0 )
        {
          *((_DWORD *)a5 + 4 * (v136 & 7) + 56) = 0;
          DxgkLogCodePointPacket(
            101,
            (unsigned int)v130,
            *((_DWORD *)a5 + v130 + 40) & 7,
            2,
            *(_QWORD *)((char *)v12 + 412));
        }
        v137 = v156;
        v138 = ADAPTER_DISPLAY::SetVidPnSourceActive(*((ADAPTER_DISPLAY **)v12 + 406), v130, 0, 0, v156 == 4, a7 != 0);
        if ( v138 < 0 )
        {
          WdLogSingleEntry3(2, v12, (unsigned int)v130, v138);
          WdLogGlobalForLineNumber = 3863;
        }
        if ( v175 )
        {
          v139 = (DMMVIDPNTOPOLOGY *)(v175 + 96);
          v140 = v175 + 152;
          *(_QWORD *)v148 = *(_QWORD *)(v175 + 136);
          LOBYTE(v140) = 2;
          ApplyPermissionWithinThisScope::ApplyPermissionWithinThisScope(
            v177,
            (v175 + 152) & -(__int64)(v175 != -96),
            v140);
          v141 = DMMVIDPNTOPOLOGY::RemoveAllPathsFromSource(v139, v130);
          if ( (int)(v141 + 0x80000000) >= 0 && v141 != -1071774919 )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 3878;
          }
          ApplyPermissionWithinThisScope::~ApplyPermissionWithinThisScope((ApplyPermissionWithinThisScope *)v177);
        }
        v131 = v162;
        if ( v162 )
          ADAPTER_DISPLAY::DestroyCddAllocations(*((ADAPTER_DISPLAY **)v12 + 406), v162, v130);
        if ( ((v137 - 1) & 0xFFFFFFFD) == 0 )
        {
          ADAPTER_DISPLAY::SetPartOfDesktop(*((ADAPTER_DISPLAY **)v12 + 406), v130, 0);
          ADAPTER_DISPLAY::SetContentRect(*((ADAPTER_DISPLAY **)v12 + 406), v130, &stru_1401635A8);
          ADAPTER_DISPLAY::SetCddInterface(*((ADAPTER_DISPLAY **)v12 + 406), v130, 0);
        }
        ADAPTER_DISPLAY::SetVidPnPrimaryTarget(*((ADAPTER_DISPLAY **)v12 + 406), v130, 0xFFFFFFFF);
        ADAPTER_DISPLAY::MarkCommitVidPnOnModeChange(*((ADAPTER_DISPLAY **)v12 + 406), v130, 1u);
        ADAPTER_DISPLAY::SetHdrEnabled(*((ADAPTER_DISPLAY **)v12 + 406), v130, 0);
      }
      v129 = (ADAPTER_DISPLAY *)*((_QWORD *)v12 + 406);
      v130 = (unsigned int)(v130 + 1);
    }
    while ( (unsigned int)v130 < *((_DWORD *)v129 + 24) );
    v17 = v164;
  }
  if ( v175 )
  {
    *(_DWORD *)v148 = *((_DWORD *)a5 + 63);
    *(_DWORD *)v147 = *((_DWORD *)a5 + 62);
    ADAPTER_DISPLAY::SetSyncLockGroup(
      v129,
      1,
      *((unsigned int *)a5 + 60),
      *((unsigned int *)a5 + 61),
      *(_QWORD *)v147,
      *(_QWORD *)v148);
    v142 = *((_QWORD *)v12 + 406);
    if ( *(_DWORD *)(v142 + 96) )
    {
      v143 = 0;
      do
      {
        v144 = (unsigned int)v143;
        v145 = *((_DWORD *)a5 + v143 + 40) & 7;
        v143 = (unsigned int)(v143 + 1);
        *(_DWORD *)(4024 * v144 + *(_QWORD *)(v142 + 128) + 3804) = *((_DWORD *)a5 + 4 * v145 + 56) != 0 ? v145 : 0;
        v142 = *((_QWORD *)v12 + 406);
      }
      while ( (unsigned int)v143 < *(_DWORD *)(v142 + 96) );
    }
  }
  DxgkInvalidateQdcCache();
  CVidSchSuspendResume::Resume((CVidSchSuspendResume *)&v173);
  if ( v17 )
    ReferenceCounted::Release((ReferenceCounted *)(v17 + 64));
  wistd::unique_ptr<unsigned int [0],wistd::default_delete<unsigned int [0]>>::reset(&v165);
  auto_rc<DMMVIDPN const>::reset(&v176, 0);
  v14 = 0;
LABEL_291:
  wistd::unique_ptr<unsigned int [0],wistd::default_delete<unsigned int [0]>>::reset(&v167);
  wistd::unique_ptr<unsigned int [0],wistd::default_delete<unsigned int [0]>>::reset(&v157);
  wistd::unique_ptr<unsigned int [0],wistd::default_delete<unsigned int [0]>>::reset(&Src);
  return (unsigned int)v14;
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
