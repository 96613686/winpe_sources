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
  signed int v12; // eax
  signed int v13; // edi
  unsigned __int64 ClientCommittedVidPnRef; // r13
  __int64 v15; // rax
  __int64 v16; // rbx
  __int64 v17; // rdx
  unsigned __int8 IsLegacyDisplayStateSynchronization; // al
  __int64 v19; // rdx
  int v20; // r9d
  unsigned __int8 v21; // r11
  int v22; // ecx
  unsigned __int8 v23; // dl
  unsigned int v24; // r8d
  unsigned int v25; // r12d
  unsigned int v26; // r15d
  unsigned int v27; // r10d
  unsigned int v28; // edx
  unsigned int v29; // ecx
  int v30; // r9d
  int v31; // eax
  int v32; // eax
  unsigned int v33; // ecx
  int v34; // r9d
  int v35; // eax
  int v36; // eax
  ADAPTER_DISPLAY *v37; // r8
  int v38; // ebx
  unsigned int v39; // r15d
  int v40; // r12d
  __int64 v41; // rcx
  struct DXGDEVICE *VidPnSourceOwner; // r13
  unsigned __int8 v43; // r9
  VIDPN_MGR *v44; // r15
  unsigned int v45; // r15d
  __int64 v46; // rdi
  char *v47; // rbx
  _BYTE *v48; // r14
  __int64 v49; // r15
  char *v50; // r13
  bool v51; // zf
  char *v52; // rax
  __int128 v53; // xmm1
  __int128 v54; // xmm2
  __int64 v55; // xmm3_8
  bool v56; // dl
  int v57; // eax
  ADAPTER_DISPLAY *v58; // rcx
  int v59; // eax
  DMMVIDEOPRESENTTARGET *TargetById; // rax
  _OWORD *v61; // r8
  int v62; // edx
  unsigned __int8 v63; // r15
  _OWORD *v64; // rax
  __int128 v65; // xmm1
  __int128 v66; // xmm2
  __int64 v67; // xmm3_8
  ADAPTER_DISPLAY *v68; // rcx
  unsigned int v69; // eax
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
  __int64 v97; // rcx
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
  __int64 v127; // rdx
  __int64 v128; // rcx
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
  __int64 v140; // r8
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
  UINT v153; // [rsp+80h] [rbp-80h] BYREF
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
  const struct DMMVIDPN *v175; // [rsp+140h] [rbp+40h]
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
  v11 = ContainingAdapter;
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
  v12 = VIDPN_MGR::BuildSetTimingsPathInfoFromClientVidPn(
          a1,
          (__int64)&v169,
          (__int64)&v153,
          (__int64)&Src,
          (__int64)&v157,
          (__int64)&v167);
  v13 = v12;
  v158 = v12;
  if ( v12 < 0 )
  {
    WdLogSingleEntry2(2, a4, v12);
    WdLogGlobalForLineNumber = 2542;
    goto LABEL_291;
  }
  if ( !v153 )
  {
    WdLogSingleEntry2(3, *((int *)v11 + 104), *((unsigned int *)v11 + 103));
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
      DisplayScenarioJournalSetSetTimingPathInfo(*(_QWORD *)((char *)v11 + 412), 0, 56 * v153);
      v13 = 0;
      goto LABEL_291;
    }
  }
  v160 = 0;
  ClientCommittedVidPnRef = (unsigned __int64)VIDPN_MGR::AcquireLastClientCommittedVidPnRef(a1);
  v176 = ClientCommittedVidPnRef;
  if ( a4 )
    ClientCommittedVidPnRef = (unsigned __int64)a4;
  v15 = 56LL * v153;
  v171 = (const struct DMMVIDPN *)ClientCommittedVidPnRef;
  if ( !is_mul_ok(v153, 0x38u) )
    v15 = -1;
  v165 = (char *)operator new[](v15, 1313891414, 256);
  if ( !v165 )
  {
    WdLogSingleEntry1(6, v153);
    WdLogGlobalForLineNumber = 2622;
    wistd::unique_ptr<unsigned int [0],wistd::default_delete<unsigned int [0]>>::reset(&v165);
    auto_rc<DMMVIDPN const>::reset(&v176, 0);
    v13 = -1073741801;
    goto LABEL_291;
  }
  v166 = (DMMVIDPNTOPOLOGY *)(ClientCommittedVidPnRef + 96);
  memmove(v165, Src, 56LL * v153);
  _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)a1 + 15) + 72LL));
  v16 = *((_QWORD *)a1 + 15);
  v17 = *((_QWORD *)v11 + 407);
  v164 = v16;
  v174 = v17;
  v173 = 0;
  IsLegacyDisplayStateSynchronization = DXGADAPTER::IsLegacyDisplayStateSynchronization(v11);
  v20 = *((_DWORD *)v11 + 783);
  v149 = IsLegacyDisplayStateSynchronization;
  v21 = IsLegacyDisplayStateSynchronization;
  v155 = v20;
  if ( !v19 )
    goto LABEL_60;
  v22 = *(_DWORD *)(v19 + 756);
  v23 = a7;
  if ( a7 )
  {
    if ( !v22 )
      goto LABEL_26;
  }
  else if ( v22 )
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
    v21 = v149;
    v20 = v155;
    v23 = a7;
  }
  if ( v20 >= 2200 )
  {
    v24 = 0;
    v25 = 0;
    v26 = 0;
    v27 = *(_DWORD *)(*((_QWORD *)v11 + 406) + 96LL);
    if ( v23 )
    {
      v28 = 0;
      if ( v27 )
      {
        v29 = 0;
        v30 = *((_DWORD *)a5 + 2) | *((_DWORD *)a5 + 3) | *((_DWORD *)a5 + 6);
        if ( v21 )
        {
          do
          {
            v32 = 1 << v29;
            if ( (v30 & (1 << v29)) != 0 )
            {
              v28 |= v32;
            }
            else if ( (v32 & *(_DWORD *)a5) != 0 )
            {
              v24 |= v32;
            }
            ++v29;
          }
          while ( v29 < v27 );
        }
        else
        {
          do
          {
            v31 = 1 << v29;
            if ( ((1 << v29) & v30) != 0 )
            {
              v28 |= v31;
              v25 |= v31;
            }
            else if ( (v31 & *(_DWORD *)a5) != 0 )
            {
              v24 |= v31;
            }
            ++v29;
          }
          while ( v29 < v27 );
        }
      }
    }
    else
    {
      v28 = 0;
      if ( v27 )
      {
        v33 = 0;
        v34 = *((_DWORD *)a5 + 2) | *((_DWORD *)a5 + 3) | *((_DWORD *)a5 + 6);
        if ( v21 )
        {
          do
          {
            v36 = 1 << v33;
            if ( (v34 & (1 << v33)) != 0 )
            {
              v28 |= v36;
            }
            else if ( (v36 & *(_DWORD *)a5) != 0 )
            {
              v24 |= v36;
              v26 |= v36;
            }
            ++v33;
          }
          while ( v33 < v27 );
        }
        else
        {
          do
          {
            v35 = 1 << v33;
            if ( ((1 << v33) & v34) != 0 )
            {
              v28 |= v35;
              v25 |= v35;
            }
            else if ( (v35 & *(_DWORD *)a5) != 0 )
            {
              v24 |= v35;
              v26 |= v35;
            }
            ++v33;
          }
          while ( v33 < v27 );
        }
      }
    }
    ADAPTER_RENDER::FlushPresentReferencesAndDisableOverlays(*((ADAPTER_RENDER **)v11 + 407), v28, v24, v25, v26);
    *((_DWORD *)a5 + 16) |= v25;
    if ( v26 )
      CVidSchSuspendResume::SetSuspendSourceMask((CVidSchSuspendResume *)&v173, v26);
  }
  else
  {
    ADAPTER_RENDER::FlushScheduler(*((_QWORD *)v11 + 407), 8, 0xFFFFFFFFLL);
  }
  v20 = v155;
LABEL_60:
  v37 = (ADAPTER_DISPLAY *)*((_QWORD *)v11 + 406);
  if ( !*((_DWORD *)v37 + 24) )
    goto LABEL_85;
  v38 = v173;
  v39 = 0;
  do
  {
    v40 = 1 << v39;
    if ( ((*((_DWORD *)a5 + 2) | *((_DWORD *)a5 + 3)) & (1 << v39)) != 0 )
    {
      v41 = *((_QWORD *)v11 + 407);
      if ( v41 && v20 < 2200 )
      {
        ADAPTER_RENDER::FlushScheduler(v41, 8, v39);
        v37 = (ADAPTER_DISPLAY *)*((_QWORD *)v11 + 406);
      }
      if ( v162 && v170 )
      {
        VidPnSourceOwner = ADAPTER_DISPLAY::GetVidPnSourceOwner(v37, v39);
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
        v43 = v38 || a7;
        ADAPTER_DISPLAY::DisablePrimaryOnDevice(*((ADAPTER_DISPLAY **)v11 + 406), VidPnSourceOwner, v39, v43);
      }
    }
LABEL_78:
    if ( ((*((_DWORD *)a5 + 6) | *((_DWORD *)a5 + 2) | *((_DWORD *)a5 + 3)) & v40) != 0
      && *((_QWORD *)v11 + 407)
      && *((_BYTE *)v11 + 3177)
      && v149 )
    {
      ADAPTER_DISPLAY::DisableMPOPlanes(*((ADAPTER_DISPLAY **)v11 + 406), v39, 0);
      *((_DWORD *)a5 + 16) |= v40;
    }
    v37 = (ADAPTER_DISPLAY *)*((_QWORD *)v11 + 406);
    ++v39;
    v20 = v155;
  }
  while ( v39 < *((_DWORD *)v37 + 24) );
  v16 = v164;
  v13 = v158;
  ClientCommittedVidPnRef = (unsigned __int64)v171;
LABEL_85:
  v44 = v163;
  if ( *((_DWORD *)a5 + 5) )
    VIDPN_MGR::RequestPowerStateForTargets(v163, (const struct DMMVIDPN *)ClientCommittedVidPnRef);
  if ( DXGADAPTER::UsingSetTimingsFromVidPn(v11) )
  {
    v150 = 0;
    if ( !v151 )
      goto LABEL_91;
    v45 = v156;
    v177[0] = 0;
    memset(&v168, 0, 40);
    if ( v156 == 4 )
      DisplayLogSetMonitorPowerStage(0, 16, 0, v177);
    *(_QWORD *)&v168.Format = &v154;
    v168.MultisampleMethod.NumQualityLevels = v153;
    v168.hAllocation = (HANDLE)(ClientCommittedVidPnRef & -(__int64)(ClientCommittedVidPnRef != -88));
    v58 = (ADAPTER_DISPLAY *)*((_QWORD *)v11 + 406);
    *(_QWORD *)&v168.RefreshRate.Denominator = Src;
    v59 = ADAPTER_DISPLAY::DdiSetTimingsFromVidPn(v58, (struct _DXGKARG_SETTIMINGSFROMVIDPN *)&v168);
    v13 = v59;
    if ( v59 < 0 )
    {
      WdLogSingleEntry3(2, *((int *)v11 + 104), *((unsigned int *)v11 + 103), v59);
      WdLogGlobalForLineNumber = 2857;
    }
    if ( v153 == 1
      && ((v45 - 1) & 0xFFFFFFFD) == 0
      && (v13 < 0 || (*((_DWORD *)Src + 8) & 0xF000000) == 0xD000000)
      && (*((_DWORD *)Src + 3) & 4) != 0
      && ((v154 & 1) != 0 || (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v11 + 27) + 64LL) + 3652LL) & 3) != 0) )
    {
      TargetById = DMMVIDEOPRESENTTARGETSET::GetTargetById((DMMVIDEOPRESENTTARGETSET *)v16, *(_DWORD *)Src);
      if ( TargetById )
      {
        if ( !DMMVIDEOPRESENTTARGET::IsTargetForceable(TargetById) )
        {
          DisplayScenarioJournalSetSetTimingPathInfo(*(_QWORD *)((char *)v11 + 412), (unsigned int)v13, 56 * v153);
          v61 = v165;
          *((_DWORD *)v165 + 3) = *((_DWORD *)v165 + 3) & 0xFFFFFFF0 | 9;
          v62 = *((_DWORD *)a5 + 1);
          *((_DWORD *)a5 + 6) = v62 & (*((_DWORD *)a5 + 5) ^ *((_DWORD *)a5 + 6));
          *((_DWORD *)a5 + 5) = 0;
          *((_DWORD *)a5 + 20) = v62;
          if ( v13 < 0 )
            v63 = 0;
          else
            v63 = v154 & 1;
          v64 = Src;
          v154 = 0;
          v65 = v61[1];
          v66 = v61[2];
          v67 = *((_QWORD *)v61 + 6);
          *(_OWORD *)Src = *v61;
          v64[1] = v65;
          v64[2] = v66;
          *((_QWORD *)v64 + 6) = v67;
          *(_QWORD *)&v168.Width = 0;
          v168.hAllocation = (HANDLE)(ClientCommittedVidPnRef & -(__int64)(ClientCommittedVidPnRef != -88));
          *(_QWORD *)&v168.Format = &v154;
          v168.MultisampleMethod.NumQualityLevels = v153;
          v168.RefreshRate.Numerator = 0;
          v68 = (ADAPTER_DISPLAY *)*((_QWORD *)v11 + 406);
          *(_QWORD *)&v168.RefreshRate.Denominator = Src;
          v13 = ADAPTER_DISPLAY::DdiSetTimingsFromVidPn(v68, (struct _DXGKARG_SETTIMINGSFROMVIDPN *)&v168);
          if ( v13 < 0 )
          {
            WdLogSingleEntry4(2, *(unsigned int *)Src);
            WdLogGlobalForLineNumber = 2940;
          }
          DxgkLogCodePointPacket(
            104,
            *(unsigned int *)Src,
            (unsigned int)v13,
            *((_BYTE *)Src + 35) & 0xF,
            *(_QWORD *)((char *)v11 + 412));
          v154 = v154 & 0xFFFFFFFE | ((unsigned __int8)v154 | v63) & 1;
          v45 = v156;
        }
      }
    }
    if ( v45 == 4 )
      DisplayLogSetMonitorPowerStage(0, 2147483664LL, (unsigned int)v13, v177);
  }
  else
  {
    v150 = 1;
    if ( v151 || *((_DWORD *)a5 + 10) )
    {
      v151 = 1;
      v56 = a7 || v173;
      v57 = VIDPN_MGR::CommitVidPnOnAdapter(
              v44,
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
              v56);
      v13 = v57;
      if ( v57 < 0 )
      {
        WdLogSingleEntry3(2, *((int *)v11 + 104), *((unsigned int *)v11 + 103), v57);
        WdLogGlobalForLineNumber = 3002;
      }
    }
    else
    {
      v151 = 0;
    }
LABEL_91:
    v45 = v156;
  }
  *(_DWORD *)&v147[4] = HIDWORD(Src);
  DisplayScenarioJournalSetSetTimingPathInfo(*(_QWORD *)((char *)v11 + 412), (unsigned int)v13, 56 * v153);
  LogSetTimingSourceMask(v11, a5);
  if ( v151 )
  {
    if ( v13 < 0 )
    {
      *((_DWORD *)a5 + 21) = -1;
      FillFailedStatus(a5, v13);
      v71 = 0;
      if ( v153 )
      {
        v72 = v165;
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
        while ( v71 < v153 );
        v16 = v164;
      }
      v70 = (_BYTE *)v159;
      v69 = 1;
      v154 = 1;
      *(_BYTE *)v159 = (((v45 - 1) & 0xFFFFFFFD) != 0 ? 2 : 0) | *(_BYTE *)v159 & 0xFD;
    }
    else
    {
      v46 = 0;
      if ( v153 )
      {
        v47 = v165;
        v48 = (_BYTE *)v159;
        do
        {
          v49 = 56LL * (unsigned int)v46;
          v50 = &v47[v49];
          v51 = VIDPN_MGR::CheckDdiSetTimingsViolationOnPathInfo(
                  v163,
                  (struct _DXGK_SET_TIMING_PATH_INFO *)&v47[v49],
                  (struct _DXGK_SET_TIMING_PATH_INFO *)((char *)Src + v49)) == 0;
          v52 = (char *)Src;
          if ( v51 )
          {
            v53 = *((_OWORD *)v50 + 1);
            v54 = *((_OWORD *)v50 + 2);
            v55 = *((_QWORD *)v50 + 6);
            *(_OWORD *)((char *)Src + v49) = *(_OWORD *)v50;
            *(_OWORD *)&v52[v49 + 16] = v53;
            *(_OWORD *)&v52[v49 + 32] = v54;
            *(_QWORD *)&v52[v49 + 48] = v55;
            *(_DWORD *)((char *)Src + v49 + 32) = *(_DWORD *)((_BYTE *)Src + v49 + 32) & 0xF0FFFFFF | 0xD000000;
            *((_DWORD *)a5 + *(unsigned int *)(v157 + 4 * v46) + 22) = -1073741437;
            *((_DWORD *)a5 + 21) |= 1 << *(_DWORD *)(v157 + 4 * v46);
          }
          else if ( (*(_DWORD *)((_BYTE *)Src + v49 + 32) & 0xF000000) == 0xD000000 )
          {
            *((_DWORD *)a5 + *(unsigned int *)(v157 + 4 * v46) + 22) = -1073741506;
            *((_DWORD *)a5 + 21) |= 1 << *(_DWORD *)(v157 + 4 * v46);
            *v48 = (((v156 - 1) & 0xFFFFFFFD) != 0 ? 2 : 0) | *v48 & 0xFD;
          }
          v46 = (unsigned int)(v46 + 1);
        }
        while ( (unsigned int)v46 < v153 );
        v16 = v164;
        v11 = ContainingAdapter;
      }
      v69 = v154;
      v70 = (_BYTE *)v159;
    }
    if ( (v69 & 0xFFFFFFFE) != 0 )
    {
      WdLogSingleEntry1(1, (unsigned __int64)v69 >> 1);
      LOBYTE(v69) = v154;
      WdLogGlobalForLineNumber = 3124;
    }
    if ( (v69 & 1) != 0 )
      *v70 |= 1u;
  }
  ActivityId = 0;
  EtwActivityIdControl(3u, &ActivityId);
  for ( i = 0; (unsigned int)i < v153; i = (unsigned int)(i + 1) )
  {
    v80 = 56LL * (unsigned int)i;
    v81 = *(_DWORD *)(v157 + 4 * i);
    LODWORD(v159) = v81;
    v82 = DMMVIDEOPRESENTTARGETSET::GetTargetById((DMMVIDEOPRESENTTARGETSET *)v16, *(_DWORD *)((char *)Src + v80));
    v83 = v82;
    if ( v82 )
    {
      v84 = 1 << v81;
      if ( v151 )
      {
        LogMonitorHandleOnOffState(*((_QWORD *)v82 + 14), &ActivityId, (*(_DWORD *)((char *)Src + v80 + 12) >> 2) & 1);
        if ( !v150 )
        {
          DxgkLogCodePointPacket(
            88,
            *(unsigned int *)((char *)Src + v80),
            *((_BYTE *)Src + v80 + 35) & 0xF | 0x80000000,
            *(unsigned int *)((char *)Src + v80 + 24),
            *(_QWORD *)((char *)v11 + 412));
          if ( (unsigned int)dword_1401605E8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1401605E8, 0x4000) )
          {
            v161 = *((_BYTE *)Src + v80 + 35) & 0xF | 0x80000000;
            ContainingAdapter = *(DXGADAPTER **)((char *)Src + v80 + 24);
            v158 = *(_DWORD *)((char *)Src + v80);
            v171 = *(const struct DMMVIDPN **)((char *)v11 + 412);
            v155 = 1;
            *(_QWORD *)&v177[0] = 0x1000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
              (_DWORD)Src,
              (unsigned int)word_140145FFA,
              v85,
              v86,
              (__int64)v177,
              (__int64)&v155,
              (__int64)&v171,
              (__int64)&v158,
              (__int64)&ContainingAdapter,
              (__int64)&v161);
          }
          DxgkLogCodePointPacket(
            89,
            *(unsigned int *)((char *)Src + v80),
            *(unsigned int *)((char *)Src + v80 + 48),
            0,
            *(_QWORD *)((char *)v11 + 412));
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
        v90 = *((_DWORD *)a5 + 21) | v160;
        if ( !_bittest(&v90, v159) )
        {
          DMMVIDEOPRESENTTARGET::SetTargetActivated(v83, 1u, 1u);
          if ( ((*((_DWORD *)a5 + 2) | *((_DWORD *)a5 + 6) | *((_DWORD *)a5 + 8) | *((_DWORD *)a5 + 9)) & v84) != 0
            && (*(_DWORD *)((_BYTE *)Src + v80 + 32) & 0xF000000) == 0xE000000 )
          {
            PathFromTarget = DMMVIDPNTOPOLOGY::GetPathFromTarget(v166, *(_DWORD *)((char *)Src + v80));
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
  CVidSchSuspendResume::Resume((CVidSchSuspendResume *)&v173);
  v92 = (ADAPTER_DISPLAY *)*((_QWORD *)v11 + 406);
  if ( *((_DWORD *)v92 + 24) )
  {
    v93 = 0;
    while ( 1 )
    {
      memset(v178, 0, sizeof(v178));
      v94 = 1 << v93;
      if ( ((1 << v93) & *((_DWORD *)a5 + 3)) != 0 )
      {
        v155 = 2;
      }
      else if ( (v94 & *((_DWORD *)a5 + 10)) != 0 )
      {
        v155 = 4;
      }
      else
      {
        v95 = ~*((_DWORD *)a5 + 8);
        v155 = 0;
        if ( (*((_DWORD *)a5 + 2) & v95 & v94) != 0 )
          v155 = (*(_DWORD *)a5 & v94) != 0 ? 3 : 1;
      }
      DisplayModeInfo = ADAPTER_DISPLAY::GetDisplayModeInfo(v92, v93);
      v97 = *((_DWORD *)a5 + 13) | (unsigned int)(*((_DWORD *)a5 + 2) | *((_DWORD *)a5 + 10));
      v98 = v166;
      *(_OWORD *)v178 = *(_OWORD *)DisplayModeInfo;
      *(_OWORD *)&v178[4] = *((_OWORD *)DisplayModeInfo + 1);
      *(_OWORD *)&v178[8] = *((_OWORD *)DisplayModeInfo + 2);
      *(_OWORD *)&v178[12] = *((_OWORD *)DisplayModeInfo + 3);
      *(_OWORD *)&v178[16] = *((_OWORD *)DisplayModeInfo + 4);
      if ( ((unsigned int)v97 & v94) != 0 )
        DMMVIDPNTOPOLOGY::GetDisplayModeFromVidPnSource(
          v166,
          ((v156 - 1) & 0xFFFFFFFD) == 0,
          v93,
          (struct _DXGK_DISPLAYMODE_INFO *)v178);
      if ( (v94 & *((_DWORD *)a5 + 21)) != 0 )
        goto LABEL_228;
      if ( (v94 & v160) == 0 )
        break;
LABEL_230:
      v92 = (ADAPTER_DISPLAY *)*((_QWORD *)v11 + 406);
      v93 = (unsigned int)(v93 + 1);
      if ( (unsigned int)v93 >= *((_DWORD *)v92 + 24) )
      {
        v16 = v164;
        goto LABEL_232;
      }
    }
    if ( (v94 & *((_DWORD *)a5 + 10)) != 0 )
    {
      ADAPTER_DISPLAY::SetDisplayModeInfo(
        *((ADAPTER_DISPLAY **)v11 + 406),
        v93,
        (const struct _DXGK_DISPLAYMODE_INFO *const)v178);
      *(_DWORD *)v147 = 0;
      OUTPUTDUPL_MGR::MoveContextToPendingDestroyList(
        *(_QWORD *)(*((_QWORD *)v11 + 406) + 120LL),
        (unsigned int)v93,
        0,
        0,
        *(_QWORD *)v147,
        1);
      v177[0] = 0xBu;
      v177[1] = 0;
      if ( (int)DxgkStatusChangeNotify((int *)v177, v99, v100) < 0 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 3395;
        DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"NT_SUCCESS(NotificationStatus)", 3395, 0, 0, 0, 0);
      }
    }
    v97 = *((_DWORD *)a5 + 13)
        | *((_DWORD *)a5 + 2)
        | *((_DWORD *)a5 + 3)
        | *((_DWORD *)a5 + 6)
        | (unsigned int)(*((_DWORD *)a5 + 8) | *((_DWORD *)a5 + 9));
    if ( ((unsigned int)v97 & v94) != 0 )
    {
      v158 = 0;
      MostImportantVidPnPathTargetsFromSource = GetMostImportantVidPnPathTargetsFromSource(v98, v93, &v158);
      if ( (int)(MostImportantVidPnPathTargetsFromSource + 0x80000000) >= 0
        && MostImportantVidPnPathTargetsFromSource != -1071774919 )
      {
        WdLogSingleEntry0(1);
        v102 = 0;
        WdLogGlobalForLineNumber = 3430;
        goto LABEL_184;
      }
      v102 = 0;
      if ( MostImportantVidPnPathTargetsFromSource < 0 || (v103 = v158, v158 == -1) || (v109 = 0, !v153) )
      {
LABEL_184:
        v103 = -1;
      }
      else
      {
        while ( 1 )
        {
          v102 = 0;
          if ( (_DWORD)v93 == *(_DWORD *)(v157 + 4 * v109) )
          {
            v110 = 56LL * (unsigned int)v109;
            if ( v158 == *(_DWORD *)((char *)Src + v110)
              && (*(_DWORD *)((_BYTE *)Src + v110 + 32) & 0xF000000) == 0xE000000
              && (*(_DWORD *)((_BYTE *)Src + v110 + 12) & 4) != 0
              && (v94 & *((_DWORD *)a5 + 18)) == 0 )
            {
              break;
            }
          }
          v109 = (unsigned int)(v109 + 1);
          if ( (unsigned int)v109 >= v153 )
            goto LABEL_184;
        }
        *((_DWORD *)a5 + 19) |= v94;
        v102 = 1;
      }
      ADAPTER_DISPLAY::SetVidPnPrimaryTarget(*((ADAPTER_DISPLAY **)v11 + 406), v93, v103);
      if ( (v94 & *((_DWORD *)a5 + 2)) != 0 )
      {
        v51 = *((_QWORD *)v11 + 407) == 0;
        v178[11] = 1;
        *(_QWORD *)&v178[12] = 1;
        if ( !v51 )
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
              memset(&v168.Width, 0, 40);
              v168.hAllocation = v106;
              v108 = ADAPTER_RENDER::DdiDescribeAllocation(v107, &v168);
              if ( v108 < 0 )
              {
                WdLogSingleEntry3(3, v105, (unsigned int)v93, v108);
                WdLogGlobalForLineNumber = 3540;
              }
              else if ( v168.Width == v178[0]
                     && v168.Height == v178[1]
                     && v168.Format == v178[2]
                     && *(_QWORD *)&v168.RefreshRate == *(_QWORD *)&v178[14]
                     && (((unsigned __int8)~(v178[10] >> 4) ^ (unsigned __int8)~(*((_DWORD *)v105 + 1) >> 12)) & 1) == 0 )
              {
                *(D3DDDI_MULTISAMPLINGMETHOD *)&v178[11] = v168.MultisampleMethod;
                v178[13] = v168.PrivateDriverFormatAttribute;
              }
              else if ( v150 || (*((_DWORD *)v105 + 1) & 2) == 0 )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 3528;
              }
            }
          }
        }
      }
      v111 = v156;
      v112 = ADAPTER_DISPLAY::SetVidPnSourceActive(
               *((ADAPTER_DISPLAY **)v11 + 406),
               v93,
               v102,
               (const struct _DXGK_DISPLAYMODE_INFO *)v178,
               v156 == 4,
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
          v159 = 0;
          if ( DMMVIDPNTOPOLOGY::GetNumPathsFromSource(v166, v93, &v159) < 0 || !v159 )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 3587;
          }
          v97 = (unsigned int)(*((_DWORD *)a5 + 13) | *((_DWORD *)a5 + 2));
          if ( ((unsigned int)v97 & v94) != 0 )
          {
            if ( ((v111 - 1) & 0xFFFFFFFD) == 0 )
              ADAPTER_DISPLAY::SetPartOfDesktop(*((ADAPTER_DISPLAY **)v11 + 406), v93, 1u);
            ADAPTER_DISPLAY::SetDisplayModeInfo(
              *((ADAPTER_DISPLAY **)v11 + 406),
              v93,
              (const struct _DXGK_DISPLAYMODE_INFO *const)v178);
            ADAPTER_DISPLAY::SetLastCddIntegerVSync(*((ADAPTER_DISPLAY **)v11 + 406), v93, v178[3]);
            ADAPTER_DISPLAY::DetermineScalingCapabilities(*((ADAPTER_DISPLAY **)v11 + 406), v93);
            ADAPTER_DISPLAY::SetHdrEnabled(*((ADAPTER_DISPLAY **)v11 + 406), v93, (v94 & *((_DWORD *)a5 + 64)) != 0);
            if ( v162 && v170 )
              ADAPTER_DISPLAY::UpdateOneCddPrimaryPrivateDriverData(
                *((ADAPTER_DISPLAY **)v11 + 406),
                v93,
                *(struct DXGADAPTER **)(*((_QWORD *)v162 + 2) + 16LL));
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
    v114 = v155;
    if ( v155 )
    {
      CurrentProcess = PsGetCurrentProcess(v97);
      ProcessImageFileName = PsGetProcessImageFileName(CurrentProcess);
      *(_DWORD *)v147 = *((_DWORD *)a5 + v93 + 22);
      VIDPN_MGR::CacheDisplayModeChangeRequest(
        v163,
        (unsigned int)v93,
        v178,
        1,
        *(_QWORD *)v147,
        v114,
        *(_DWORD *)(*((_QWORD *)v11 + 406) + 424LL),
        ProcessImageFileName);
    }
    goto LABEL_230;
  }
LABEL_232:
  for ( j = 0; (unsigned int)j < v153; j = (unsigned int)(j + 1) )
  {
    v118 = 56LL * (unsigned int)j;
    v119 = DMMVIDEOPRESENTTARGETSET::GetTargetById((DMMVIDEOPRESENTTARGETSET *)v16, *(_DWORD *)((char *)Src + v118));
    v120 = v119;
    if ( v119 )
    {
      v121 = Src;
      if ( (*(_DWORD *)((_BYTE *)Src + v118 + 12) & 4) == 0
        || (v122 = v157, v123 = 1 << *(_DWORD *)(v157 + 4 * j), (v123 & *((_DWORD *)a5 + 18)) != 0)
        || (v123 & *((_DWORD *)a5 + 21)) != 0 )
      {
        DMMVIDEOPRESENTTARGET::SetTargetActivated(
          v119,
          0,
          (*(_DWORD *)((_BYTE *)Src + v118 + 32) & 0xF000000) == 201326592);
        v121 = Src;
        v122 = v157;
      }
      if ( !v150
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
          WdLogSingleEntry3(2, v11, *(unsigned int *)(v157 + 4 * j), v124);
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
              *(_DWORD *)(v157 + 4 * j));
          }
          else
          {
            v126 = *(_QWORD *)(*((_QWORD *)v11 + 406) + 464LL);
            if ( v126 )
              _InterlockedExchange(
                (volatile __int32 *)(3040LL * *(unsigned int *)(v157 + 4 * j) + *(_QWORD *)(v126 + 8) + 1080),
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
      *((_DWORD *)a5 + 16) |= 1 << *(_DWORD *)(v157 + 4 * j);
  }
  auto_rc<DMMVIDPN>::reset((char *)v163 + 320, 0);
  CVidSchSuspendResume::Resume((CVidSchSuspendResume *)&v173);
  v129 = (ADAPTER_DISPLAY *)*((_QWORD *)v11 + 406);
  if ( *((_DWORD *)v129 + 24) )
  {
    v130 = 0;
    v131 = v162;
    do
    {
      v128 = (unsigned int)v130;
      v132 = 1 << v130;
      if ( ((1 << v130) & *((_DWORD *)a5 + 15)) != 0 )
        ADAPTER_DISPLAY::InvalidateDisplayModeListCacheOnSource(v129, v130);
      if ( (v132 & *((_DWORD *)a5 + 16)) != 0 )
        DXGADAPTER::NotifyMultiPlaneOverlayDisable(v11, v130);
      if ( v131 && !v150 )
      {
        if ( ADAPTER_DISPLAY::GetCddPrimaryAllocation(*((ADAPTER_DISPLAY **)v11 + 406), v130, 0)
          && ADAPTER_DISPLAY::IsCddPrimaryStale(*((ADAPTER_DISPLAY **)v11 + 406), v130) )
        {
          ADAPTER_DISPLAY::DestroyCddAllocations(v133, v131, v130);
        }
        v134 = (ADAPTER_DISPLAY *)*((_QWORD *)v11 + 406);
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
            *(_QWORD *)((char *)v11 + 412));
        }
        v137 = v156;
        v138 = ADAPTER_DISPLAY::SetVidPnSourceActive(*((ADAPTER_DISPLAY **)v11 + 406), v130, 0, 0, v156 == 4, a7 != 0);
        if ( v138 < 0 )
        {
          WdLogSingleEntry3(2, v11, (unsigned int)v130, v138);
          WdLogGlobalForLineNumber = 3863;
        }
        if ( v175 )
        {
          v139 = (const struct DMMVIDPN *)((char *)v175 + 96);
          v140 = (__int64)v175 + 152;
          *(_QWORD *)v148 = *((_QWORD *)v175 + 17);
          LOBYTE(v140) = 2;
          ApplyPermissionWithinThisScope::ApplyPermissionWithinThisScope(
            v177,
            ((unsigned __int64)v175 + 152) & -(__int64)((const struct DMMVIDPN *)((char *)v175 + 96) != 0),
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
          ADAPTER_DISPLAY::DestroyCddAllocations(*((ADAPTER_DISPLAY **)v11 + 406), v162, v130);
        if ( ((v137 - 1) & 0xFFFFFFFD) == 0 )
        {
          ADAPTER_DISPLAY::SetPartOfDesktop(*((ADAPTER_DISPLAY **)v11 + 406), v130, 0);
          ADAPTER_DISPLAY::SetContentRect(*((ADAPTER_DISPLAY **)v11 + 406), v130, &stru_1401635A8);
          ADAPTER_DISPLAY::SetCddInterface(*((ADAPTER_DISPLAY **)v11 + 406), v130, 0);
        }
        ADAPTER_DISPLAY::SetVidPnPrimaryTarget(*((ADAPTER_DISPLAY **)v11 + 406), v130, 0xFFFFFFFF);
        ADAPTER_DISPLAY::MarkCommitVidPnOnModeChange(*((ADAPTER_DISPLAY **)v11 + 406), v130, 1u);
        ADAPTER_DISPLAY::SetHdrEnabled(*((ADAPTER_DISPLAY **)v11 + 406), v130, 0);
      }
      v129 = (ADAPTER_DISPLAY *)*((_QWORD *)v11 + 406);
      v130 = (unsigned int)(v130 + 1);
    }
    while ( (unsigned int)v130 < *((_DWORD *)v129 + 24) );
    v16 = v164;
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
    v142 = *((_QWORD *)v11 + 406);
    if ( *(_DWORD *)(v142 + 96) )
    {
      v143 = 0;
      do
      {
        v144 = (unsigned int)v143;
        v145 = *((_DWORD *)a5 + v143 + 40) & 7;
        v143 = (unsigned int)(v143 + 1);
        v127 = *((_DWORD *)a5 + 4 * v145 + 56) != 0 ? v145 : 0;
        v128 = 4024 * v144;
        *(_DWORD *)(4024 * v144 + *(_QWORD *)(v142 + 128) + 3804) = v127;
        v142 = *((_QWORD *)v11 + 406);
      }
      while ( (unsigned int)v143 < *(_DWORD *)(v142 + 96) );
    }
  }
  DxgkInvalidateQdcCache(v128, v127);
  CVidSchSuspendResume::Resume((CVidSchSuspendResume *)&v173);
  if ( v16 )
    ReferenceCounted::Release((ReferenceCounted *)(v16 + 64));
  wistd::unique_ptr<unsigned int [0],wistd::default_delete<unsigned int [0]>>::reset(&v165);
  auto_rc<DMMVIDPN const>::reset(&v176, 0);
  v13 = 0;
LABEL_291:
  wistd::unique_ptr<unsigned int [0],wistd::default_delete<unsigned int [0]>>::reset(&v167);
  wistd::unique_ptr<unsigned int [0],wistd::default_delete<unsigned int [0]>>::reset(&v157);
  wistd::unique_ptr<unsigned int [0],wistd::default_delete<unsigned int [0]>>::reset(&Src);
  return (unsigned int)v13;
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
