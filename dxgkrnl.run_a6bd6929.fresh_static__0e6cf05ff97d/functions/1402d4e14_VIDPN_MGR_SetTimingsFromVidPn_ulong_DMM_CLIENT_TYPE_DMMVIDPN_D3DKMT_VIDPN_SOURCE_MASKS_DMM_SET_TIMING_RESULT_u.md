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
  int v69; // eax
  unsigned int v70; // eax
  _BYTE *v71; // rdi
  UINT v72; // r9d
  char *v73; // rbx
  __int64 v74; // rax
  __int64 v75; // rdx
  char *v76; // rax
  __int128 v77; // xmm1
  __int128 v78; // xmm2
  __int64 v79; // xmm3_8
  __int64 i; // r13
  __int64 v81; // rdi
  int v82; // r12d
  struct DMMVIDEOPRESENTTARGET *v83; // rax
  struct DMMVIDEOPRESENTTARGET *v84; // r15
  int v85; // r12d
  int v86; // r8d
  int v87; // r9d
  int TargetLinkTrainingStatus; // eax
  int v89; // r9d
  int v90; // eax
  int v91; // eax
  DMMVIDPNPRESENTPATH *PathFromTarget; // rax
  ADAPTER_DISPLAY *v93; // rdi
  __int64 v94; // r15
  int v95; // r13d
  int v96; // eax
  const struct _DXGK_DISPLAYMODE_INFO *DisplayModeInfo; // rax
  __int64 v98; // rdx
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
  __int64 v129; // rdx
  __int64 v130; // rcx
  ADAPTER_DISPLAY *v131; // r10
  __int64 v132; // r15
  struct DXGDEVICE *v133; // rdi
  int v134; // r12d
  ADAPTER_DISPLAY *v135; // rcx
  ADAPTER_DISPLAY *v136; // rdi
  const struct _D3DKMT_DISPLAYMODE *v137; // rax
  int v138; // eax
  unsigned int v139; // r13d
  int v140; // eax
  DMMVIDPNTOPOLOGY *v141; // rdi
  __int64 v142; // r8
  int v143; // eax
  __int64 v144; // r10
  __int64 v145; // r9
  __int64 v146; // r8
  unsigned int v147; // ecx
  bool v149[8]; // [rsp+20h] [rbp-E0h]
  bool v150[8]; // [rsp+28h] [rbp-D8h]
  unsigned __int8 v151; // [rsp+70h] [rbp-90h]
  char v152; // [rsp+70h] [rbp-90h]
  char v153; // [rsp+71h] [rbp-8Fh]
  void *Src; // [rsp+78h] [rbp-88h] BYREF
  UINT v155; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v156; // [rsp+84h] [rbp-7Ch] BYREF
  int v157; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v158; // [rsp+8Ch] [rbp-74h]
  __int64 v159; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v160; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v161; // [rsp+A0h] [rbp-60h] BYREF
  int v162; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v163; // [rsp+ACh] [rbp-54h] BYREF
  struct DXGDEVICE *v164; // [rsp+B0h] [rbp-50h]
  VIDPN_MGR *v165; // [rsp+B8h] [rbp-48h]
  __int64 v166; // [rsp+C0h] [rbp-40h]
  char *v167; // [rsp+C8h] [rbp-38h] BYREF
  DMMVIDPNTOPOLOGY *v168; // [rsp+D0h] [rbp-30h]
  __int64 v169; // [rsp+D8h] [rbp-28h] BYREF
  struct _DXGKARG_DESCRIBEALLOCATION v170; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v171; // [rsp+110h] [rbp+10h] BYREF
  __int64 v172; // [rsp+118h] [rbp+18h]
  const struct DMMVIDPN *v173; // [rsp+120h] [rbp+20h] BYREF
  DXGADAPTER *ContainingAdapter; // [rsp+128h] [rbp+28h] BYREF
  int v175; // [rsp+130h] [rbp+30h] BYREF
  __int64 v176; // [rsp+138h] [rbp+38h]
  const struct DMMVIDPN *v177; // [rsp+140h] [rbp+40h]
  unsigned __int64 v178; // [rsp+148h] [rbp+48h] BYREF
  _OWORD v179[2]; // [rsp+150h] [rbp+50h] BYREF
  unsigned int v180[20]; // [rsp+170h] [rbp+70h] BYREF
  GUID ActivityId; // [rsp+1C0h] [rbp+C0h] BYREF

  v164 = a8;
  v172 = a9;
  v177 = a4;
  v158 = a3;
  v163 = a2;
  v165 = a1;
  v161 = (unsigned __int64)a6;
  v156 = 0;
  ContainingAdapter = VIDPN_MGR::GetContainingAdapter(a1);
  v11 = ContainingAdapter;
  if ( !DXGADAPTER::IsCoreResourceExclusiveOwner(ContainingAdapter) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 2510;
  }
  LODWORD(v171) = 0;
  *a6 = 0;
  v155 = 0;
  Src = 0;
  v159 = 0;
  v169 = 0;
  v12 = VIDPN_MGR::BuildSetTimingsPathInfoFromClientVidPn(
          a1,
          (__int64)&v171,
          (__int64)&v155,
          (__int64)&Src,
          (__int64)&v159,
          (__int64)&v169);
  v13 = v12;
  v160 = v12;
  if ( v12 < 0 )
  {
    WdLogSingleEntry2(2, a4, v12);
    WdLogGlobalForLineNumber = 2542;
    goto LABEL_291;
  }
  if ( !v155 )
  {
    WdLogSingleEntry2(3, *((int *)v11 + 104), *((unsigned int *)v11 + 103));
    WdLogGlobalForLineNumber = 2560;
    goto LABEL_291;
  }
  if ( *((_DWORD *)a5 + 2) || *((_DWORD *)a5 + 3) || *((_DWORD *)a5 + 6) )
  {
    v153 = 1;
  }
  else
  {
    v153 = 0;
    if ( !*((_DWORD *)a5 + 10) && !*((_DWORD *)a5 + 8) && !*((_DWORD *)a5 + 13) )
    {
      DisplayScenarioJournalSetSetTimingPathInfo(*(_QWORD *)((char *)v11 + 412), 0, 56 * v155);
      v13 = 0;
      goto LABEL_291;
    }
  }
  v162 = 0;
  ClientCommittedVidPnRef = (unsigned __int64)VIDPN_MGR::AcquireLastClientCommittedVidPnRef(a1);
  v178 = ClientCommittedVidPnRef;
  if ( a4 )
    ClientCommittedVidPnRef = (unsigned __int64)a4;
  v15 = 56LL * v155;
  v173 = (const struct DMMVIDPN *)ClientCommittedVidPnRef;
  if ( !is_mul_ok(v155, 0x38u) )
    v15 = -1;
  v167 = (char *)operator new[](v15, 1313891414, 256);
  if ( !v167 )
  {
    WdLogSingleEntry1(6, v155);
    WdLogGlobalForLineNumber = 2622;
    wistd::unique_ptr<unsigned int [0],wistd::default_delete<unsigned int [0]>>::reset(&v167);
    auto_rc<DMMVIDPN const>::reset(&v178, 0);
    v13 = -1073741801;
    goto LABEL_291;
  }
  v168 = (DMMVIDPNTOPOLOGY *)(ClientCommittedVidPnRef + 96);
  memmove(v167, Src, 56LL * v155);
  _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)a1 + 15) + 72LL));
  v16 = *((_QWORD *)a1 + 15);
  v17 = *((_QWORD *)v11 + 407);
  v166 = v16;
  v176 = v17;
  v175 = 0;
  IsLegacyDisplayStateSynchronization = DXGADAPTER::IsLegacyDisplayStateSynchronization(v11);
  v20 = *((_DWORD *)v11 + 783);
  v151 = IsLegacyDisplayStateSynchronization;
  v21 = IsLegacyDisplayStateSynchronization;
  v157 = v20;
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
    v21 = v151;
    v20 = v157;
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
      CVidSchSuspendResume::SetSuspendSourceMask((CVidSchSuspendResume *)&v175, v26);
  }
  else
  {
    ADAPTER_RENDER::FlushScheduler(*((_QWORD *)v11 + 407), 8, 0xFFFFFFFFLL);
  }
  v20 = v157;
LABEL_60:
  v37 = (ADAPTER_DISPLAY *)*((_QWORD *)v11 + 406);
  if ( !*((_DWORD *)v37 + 24) )
    goto LABEL_85;
  v38 = v175;
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
      if ( v164 && v172 )
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
      && v151 )
    {
      ADAPTER_DISPLAY::DisableMPOPlanes(*((ADAPTER_DISPLAY **)v11 + 406), v39, 0);
      *((_DWORD *)a5 + 16) |= v40;
    }
    v37 = (ADAPTER_DISPLAY *)*((_QWORD *)v11 + 406);
    ++v39;
    v20 = v157;
  }
  while ( v39 < *((_DWORD *)v37 + 24) );
  v16 = v166;
  v13 = v160;
  ClientCommittedVidPnRef = (unsigned __int64)v173;
LABEL_85:
  v44 = v165;
  if ( *((_DWORD *)a5 + 5) )
    VIDPN_MGR::RequestPowerStateForTargets(v165, (const struct DMMVIDPN *)ClientCommittedVidPnRef);
  if ( DXGADAPTER::UsingSetTimingsFromVidPn(v11) )
  {
    v152 = 0;
    if ( !v153 )
      goto LABEL_91;
    v45 = v158;
    v179[0] = 0;
    memset(&v170, 0, 40);
    if ( v158 == 4 )
      DisplayLogSetMonitorPowerStage(0, 16, 0, v179);
    *(_QWORD *)&v170.Format = &v156;
    v170.MultisampleMethod.NumQualityLevels = v155;
    v170.hAllocation = (HANDLE)(ClientCommittedVidPnRef & -(__int64)(ClientCommittedVidPnRef != -88));
    v58 = (ADAPTER_DISPLAY *)*((_QWORD *)v11 + 406);
    *(_QWORD *)&v170.RefreshRate.Denominator = Src;
    v59 = ADAPTER_DISPLAY::DdiSetTimingsFromVidPn(v58, (struct _DXGKARG_SETTIMINGSFROMVIDPN *)&v170);
    v13 = v59;
    if ( v59 < 0 )
    {
      WdLogSingleEntry3(2, *((int *)v11 + 104), *((unsigned int *)v11 + 103), v59);
      WdLogGlobalForLineNumber = 2857;
    }
    if ( v155 == 1
      && ((v45 - 1) & 0xFFFFFFFD) == 0
      && (v13 < 0 || (*((_DWORD *)Src + 8) & 0xF000000) == 0xD000000)
      && (*((_DWORD *)Src + 3) & 4) != 0
      && ((v156 & 1) != 0 || (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v11 + 27) + 64LL) + 3652LL) & 3) != 0) )
    {
      TargetById = DMMVIDEOPRESENTTARGETSET::GetTargetById((DMMVIDEOPRESENTTARGETSET *)v16, *(_DWORD *)Src);
      if ( TargetById )
      {
        if ( !DMMVIDEOPRESENTTARGET::IsTargetForceable(TargetById) )
        {
          DisplayScenarioJournalSetSetTimingPathInfo(*(_QWORD *)((char *)v11 + 412), (unsigned int)v13, 56 * v155);
          v61 = v167;
          *((_DWORD *)v167 + 3) = *((_DWORD *)v167 + 3) & 0xFFFFFFF0 | 9;
          v62 = *((_DWORD *)a5 + 1);
          *((_DWORD *)a5 + 6) = v62 & (*((_DWORD *)a5 + 5) ^ *((_DWORD *)a5 + 6));
          *((_DWORD *)a5 + 5) = 0;
          *((_DWORD *)a5 + 20) = v62;
          if ( v13 < 0 )
            v63 = 0;
          else
            v63 = v156 & 1;
          v64 = Src;
          v156 = 0;
          v65 = v61[1];
          v66 = v61[2];
          v67 = *((_QWORD *)v61 + 6);
          *(_OWORD *)Src = *v61;
          v64[1] = v65;
          v64[2] = v66;
          *((_QWORD *)v64 + 6) = v67;
          *(_QWORD *)&v170.Width = 0;
          v170.hAllocation = (HANDLE)(ClientCommittedVidPnRef & -(__int64)(ClientCommittedVidPnRef != -88));
          *(_QWORD *)&v170.Format = &v156;
          v170.MultisampleMethod.NumQualityLevels = v155;
          v170.RefreshRate.Numerator = 0;
          v68 = (ADAPTER_DISPLAY *)*((_QWORD *)v11 + 406);
          *(_QWORD *)&v170.RefreshRate.Denominator = Src;
          v69 = ADAPTER_DISPLAY::DdiSetTimingsFromVidPn(v68, (struct _DXGKARG_SETTIMINGSFROMVIDPN *)&v170);
          v13 = v69;
          if ( v69 < 0 )
          {
            WdLogSingleEntry4(2, *(unsigned int *)Src, *((int *)v11 + 104), *((unsigned int *)v11 + 103), v69);
            WdLogGlobalForLineNumber = 2940;
          }
          DxgkLogCodePointPacket(
            104,
            *(unsigned int *)Src,
            (unsigned int)v13,
            *((_BYTE *)Src + 35) & 0xF,
            *(_QWORD *)((char *)v11 + 412));
          v156 = v156 & 0xFFFFFFFE | ((unsigned __int8)v156 | v63) & 1;
          v45 = v158;
        }
      }
    }
    if ( v45 == 4 )
      DisplayLogSetMonitorPowerStage(0, 2147483664LL, (unsigned int)v13, v179);
  }
  else
  {
    v152 = 1;
    if ( v153 || *((_DWORD *)a5 + 10) )
    {
      v153 = 1;
      v56 = a7 || v175;
      v57 = VIDPN_MGR::CommitVidPnOnAdapter(
              v44,
              v163,
              v158,
              ClientCommittedVidPnRef,
              v155,
              Src,
              v159,
              a5,
              &v162,
              v169,
              &v156,
              v164,
              v172,
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
      v153 = 0;
    }
LABEL_91:
    v45 = v158;
  }
  *(_DWORD *)&v149[4] = HIDWORD(Src);
  DisplayScenarioJournalSetSetTimingPathInfo(*(_QWORD *)((char *)v11 + 412), (unsigned int)v13, 56 * v155);
  LogSetTimingSourceMask(v11, a5);
  if ( v153 )
  {
    if ( v13 < 0 )
    {
      *((_DWORD *)a5 + 21) = -1;
      FillFailedStatus(a5, v13);
      v72 = 0;
      if ( v155 )
      {
        v73 = v167;
        do
        {
          v74 = v72++;
          v75 = 56 * v74;
          v76 = (char *)Src;
          v77 = *(_OWORD *)&v73[v75 + 16];
          v78 = *(_OWORD *)&v73[v75 + 32];
          v79 = *(_QWORD *)&v73[v75 + 48];
          *(_OWORD *)((char *)Src + v75) = *(_OWORD *)&v73[v75];
          *(_OWORD *)&v76[v75 + 16] = v77;
          *(_OWORD *)&v76[v75 + 32] = v78;
          *(_QWORD *)&v76[v75 + 48] = v79;
          *(_DWORD *)((char *)Src + v75 + 32) = *(_DWORD *)((_BYTE *)Src + v75 + 32) & 0xF0FFFFFF | 0xD000000;
          *(_DWORD *)((char *)Src + v75 + 16) |= 1u;
        }
        while ( v72 < v155 );
        v16 = v166;
      }
      v71 = (_BYTE *)v161;
      v70 = 1;
      v156 = 1;
      *(_BYTE *)v161 = (((v45 - 1) & 0xFFFFFFFD) != 0 ? 2 : 0) | *(_BYTE *)v161 & 0xFD;
    }
    else
    {
      v46 = 0;
      if ( v155 )
      {
        v47 = v167;
        v48 = (_BYTE *)v161;
        do
        {
          v49 = 56LL * (unsigned int)v46;
          v50 = &v47[v49];
          v51 = VIDPN_MGR::CheckDdiSetTimingsViolationOnPathInfo(
                  v165,
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
            *((_DWORD *)a5 + *(unsigned int *)(v159 + 4 * v46) + 22) = -1073741437;
            *((_DWORD *)a5 + 21) |= 1 << *(_DWORD *)(v159 + 4 * v46);
          }
          else if ( (*(_DWORD *)((_BYTE *)Src + v49 + 32) & 0xF000000) == 0xD000000 )
          {
            *((_DWORD *)a5 + *(unsigned int *)(v159 + 4 * v46) + 22) = -1073741506;
            *((_DWORD *)a5 + 21) |= 1 << *(_DWORD *)(v159 + 4 * v46);
            *v48 = (((v158 - 1) & 0xFFFFFFFD) != 0 ? 2 : 0) | *v48 & 0xFD;
          }
          v46 = (unsigned int)(v46 + 1);
        }
        while ( (unsigned int)v46 < v155 );
        v16 = v166;
        v11 = ContainingAdapter;
      }
      v70 = v156;
      v71 = (_BYTE *)v161;
    }
    if ( (v70 & 0xFFFFFFFE) != 0 )
    {
      WdLogSingleEntry1(1, (unsigned __int64)v70 >> 1);
      LOBYTE(v70) = v156;
      WdLogGlobalForLineNumber = 3124;
    }
    if ( (v70 & 1) != 0 )
      *v71 |= 1u;
  }
  ActivityId = 0;
  EtwActivityIdControl(3u, &ActivityId);
  for ( i = 0; (unsigned int)i < v155; i = (unsigned int)(i + 1) )
  {
    v81 = 56LL * (unsigned int)i;
    v82 = *(_DWORD *)(v159 + 4 * i);
    LODWORD(v161) = v82;
    v83 = DMMVIDEOPRESENTTARGETSET::GetTargetById((DMMVIDEOPRESENTTARGETSET *)v16, *(_DWORD *)((char *)Src + v81));
    v84 = v83;
    if ( v83 )
    {
      v85 = 1 << v82;
      if ( v153 )
      {
        LogMonitorHandleOnOffState(*((_QWORD *)v83 + 14), &ActivityId, (*(_DWORD *)((char *)Src + v81 + 12) >> 2) & 1);
        if ( !v152 )
        {
          DxgkLogCodePointPacket(
            88,
            *(unsigned int *)((char *)Src + v81),
            *((_BYTE *)Src + v81 + 35) & 0xF | 0x80000000,
            *(unsigned int *)((char *)Src + v81 + 24),
            *(_QWORD *)((char *)v11 + 412));
          if ( (unsigned int)dword_1401605E8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1401605E8, 0x4000) )
          {
            v163 = *((_BYTE *)Src + v81 + 35) & 0xF | 0x80000000;
            ContainingAdapter = *(DXGADAPTER **)((char *)Src + v81 + 24);
            v160 = *(_DWORD *)((char *)Src + v81);
            v173 = *(const struct DMMVIDPN **)((char *)v11 + 412);
            v157 = 1;
            *(_QWORD *)&v179[0] = 0x1000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
              (_DWORD)Src,
              (unsigned int)word_140145FFA,
              v86,
              v87,
              (__int64)v179,
              (__int64)&v157,
              (__int64)&v173,
              (__int64)&v160,
              (__int64)&ContainingAdapter,
              (__int64)&v163);
          }
          DxgkLogCodePointPacket(
            89,
            *(unsigned int *)((char *)Src + v81),
            *(unsigned int *)((char *)Src + v81 + 48),
            0,
            *(_QWORD *)((char *)v11 + 412));
        }
        TargetLinkTrainingStatus = DMMVIDEOPRESENTTARGET::GetTargetLinkTrainingStatus(v84, 0);
        if ( TargetLinkTrainingStatus != v89 )
          *((_DWORD *)a5 + 9) |= v85;
        DMMVIDEOPRESENTTARGET::UpdateTargetLinkTrainingStatus(
          v84,
          *(_QWORD *)((char *)Src + v81 + 24),
          *((_BYTE *)Src + v81 + 35) & 0xF);
        if ( (*(_DWORD *)((_BYTE *)Src + v81 + 32) & 0xF000000) == 0xC000000 )
          DMMVIDEOPRESENTTARGET::StartLinkTrainingTimer(v84, 1u);
        else
          DMMVIDEOPRESENTTARGET::CancelLinkTrainingTimer(v84);
        *((_BYTE *)v84 + 414) = 0;
      }
      else
      {
        v90 = DMMVIDEOPRESENTTARGET::GetTargetLinkTrainingStatus(v83, 0);
        *(_DWORD *)((char *)Src + v81 + 32) ^= (*(_DWORD *)((char *)Src + v81 + 32) ^ (v90 << 24)) & 0xF000000;
      }
      if ( (*(_DWORD *)((_BYTE *)Src + v81 + 12) & 4) != 0 && (v85 & *((_DWORD *)a5 + 18)) == 0 )
      {
        v91 = *((_DWORD *)a5 + 21) | v162;
        if ( !_bittest(&v91, v161) )
        {
          DMMVIDEOPRESENTTARGET::SetTargetActivated(v84, 1u, 1u);
          if ( ((*((_DWORD *)a5 + 2) | *((_DWORD *)a5 + 6) | *((_DWORD *)a5 + 8) | *((_DWORD *)a5 + 9)) & v85) != 0
            && (*(_DWORD *)((_BYTE *)Src + v81 + 32) & 0xF000000) == 0xE000000 )
          {
            PathFromTarget = DMMVIDPNTOPOLOGY::GetPathFromTarget(v168, *(_DWORD *)((char *)Src + v81));
            DMMVIDPNPRESENTPATH::SetDriverGammaRamp(PathFromTarget, 0);
          }
        }
      }
      if ( (*(_DWORD *)((_BYTE *)Src + v81 + 32) & 0xF000000) != 0xD000000
        && ((*((_DWORD *)a5 + 2) | *((_DWORD *)a5 + 4)) & v85) != 0 )
      {
        MonitorSetLastWireformatAndColorspace(
          *((struct HDXGMONITOR__ **)v84 + 14),
          *(union _D3DKMDT_WIRE_FORMAT_AND_PREFERENCE *)((char *)Src + v81 + 8),
          *(enum _D3DDDI_OUTPUT_WIRE_COLOR_SPACE_TYPE *)((char *)Src + v81 + 4));
      }
    }
  }
  CVidSchSuspendResume::Resume((CVidSchSuspendResume *)&v175);
  v93 = (ADAPTER_DISPLAY *)*((_QWORD *)v11 + 406);
  if ( *((_DWORD *)v93 + 24) )
  {
    v94 = 0;
    while ( 1 )
    {
      memset(v180, 0, sizeof(v180));
      v95 = 1 << v94;
      if ( ((1 << v94) & *((_DWORD *)a5 + 3)) != 0 )
      {
        v157 = 2;
      }
      else if ( (v95 & *((_DWORD *)a5 + 10)) != 0 )
      {
        v157 = 4;
      }
      else
      {
        v96 = ~*((_DWORD *)a5 + 8);
        v157 = 0;
        if ( (*((_DWORD *)a5 + 2) & v96 & v95) != 0 )
          v157 = (*(_DWORD *)a5 & v95) != 0 ? 3 : 1;
      }
      DisplayModeInfo = ADAPTER_DISPLAY::GetDisplayModeInfo(v93, v94);
      v99 = *((_DWORD *)a5 + 13) | (unsigned int)(*((_DWORD *)a5 + 2) | *((_DWORD *)a5 + 10));
      v100 = v168;
      *(_OWORD *)v180 = *(_OWORD *)DisplayModeInfo;
      *(_OWORD *)&v180[4] = *((_OWORD *)DisplayModeInfo + 1);
      *(_OWORD *)&v180[8] = *((_OWORD *)DisplayModeInfo + 2);
      *(_OWORD *)&v180[12] = *((_OWORD *)DisplayModeInfo + 3);
      *(_OWORD *)&v180[16] = *((_OWORD *)DisplayModeInfo + 4);
      if ( ((unsigned int)v99 & v95) != 0 )
        DMMVIDPNTOPOLOGY::GetDisplayModeFromVidPnSource(
          v168,
          ((v158 - 1) & 0xFFFFFFFD) == 0,
          v94,
          (struct _DXGK_DISPLAYMODE_INFO *)v180);
      if ( (v95 & *((_DWORD *)a5 + 21)) != 0 )
        goto LABEL_228;
      if ( (v95 & v162) == 0 )
        break;
LABEL_230:
      v93 = (ADAPTER_DISPLAY *)*((_QWORD *)v11 + 406);
      v94 = (unsigned int)(v94 + 1);
      if ( (unsigned int)v94 >= *((_DWORD *)v93 + 24) )
      {
        v16 = v166;
        goto LABEL_232;
      }
    }
    if ( (v95 & *((_DWORD *)a5 + 10)) != 0 )
    {
      ADAPTER_DISPLAY::SetDisplayModeInfo(
        *((ADAPTER_DISPLAY **)v11 + 406),
        v94,
        (const struct _DXGK_DISPLAYMODE_INFO *const)v180);
      *(_DWORD *)v149 = 0;
      OUTPUTDUPL_MGR::MoveContextToPendingDestroyList(
        *(_QWORD *)(*((_QWORD *)v11 + 406) + 120LL),
        (unsigned int)v94,
        0,
        0,
        *(_QWORD *)v149,
        1);
      v179[0] = 0xBu;
      v179[1] = 0;
      if ( (int)DxgkStatusChangeNotify((int *)v179, v101, v102) < 0 )
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
    if ( ((unsigned int)v99 & v95) != 0 )
    {
      v160 = 0;
      MostImportantVidPnPathTargetsFromSource = GetMostImportantVidPnPathTargetsFromSource(v100, v94, &v160);
      if ( (int)(MostImportantVidPnPathTargetsFromSource + 0x80000000) >= 0
        && MostImportantVidPnPathTargetsFromSource != -1071774919 )
      {
        WdLogSingleEntry0(1);
        v104 = 0;
        WdLogGlobalForLineNumber = 3430;
        goto LABEL_184;
      }
      v104 = 0;
      if ( MostImportantVidPnPathTargetsFromSource < 0 || (v105 = v160, v160 == -1) || (v111 = 0, !v155) )
      {
LABEL_184:
        v105 = -1;
      }
      else
      {
        while ( 1 )
        {
          v104 = 0;
          if ( (_DWORD)v94 == *(_DWORD *)(v159 + 4 * v111) )
          {
            v112 = 56LL * (unsigned int)v111;
            if ( v160 == *(_DWORD *)((char *)Src + v112)
              && (*(_DWORD *)((_BYTE *)Src + v112 + 32) & 0xF000000) == 0xE000000
              && (*(_DWORD *)((_BYTE *)Src + v112 + 12) & 4) != 0
              && (v95 & *((_DWORD *)a5 + 18)) == 0 )
            {
              break;
            }
          }
          v111 = (unsigned int)(v111 + 1);
          if ( (unsigned int)v111 >= v155 )
            goto LABEL_184;
        }
        *((_DWORD *)a5 + 19) |= v95;
        v104 = 1;
      }
      ADAPTER_DISPLAY::SetVidPnPrimaryTarget(*((ADAPTER_DISPLAY **)v11 + 406), v94, v105);
      if ( (v95 & *((_DWORD *)a5 + 2)) != 0 )
      {
        v51 = *((_QWORD *)v11 + 407) == 0;
        v180[11] = 1;
        *(_QWORD *)&v180[12] = 1;
        if ( !v51 )
        {
          DisplayedPrimaryAllocation = ADAPTER_DISPLAY::GetDisplayedPrimaryAllocation(
                                         *((ADAPTER_DISPLAY **)v11 + 406),
                                         v94);
          v107 = DisplayedPrimaryAllocation;
          if ( DisplayedPrimaryAllocation )
          {
            if ( (*((_BYTE *)DisplayedPrimaryAllocation + 4) & 0x10) != 0 )
              v107 = 0;
            if ( v107 )
            {
              v108 = (void *)*((_QWORD *)v107 + 2);
              v109 = (ADAPTER_RENDER *)*((_QWORD *)v11 + 407);
              memset(&v170.Width, 0, 40);
              v170.hAllocation = v108;
              v110 = ADAPTER_RENDER::DdiDescribeAllocation(v109, &v170);
              if ( v110 < 0 )
              {
                WdLogSingleEntry3(3, v107, (unsigned int)v94, v110);
                WdLogGlobalForLineNumber = 3540;
              }
              else if ( v170.Width == v180[0]
                     && v170.Height == v180[1]
                     && v170.Format == v180[2]
                     && *(_QWORD *)&v170.RefreshRate == *(_QWORD *)&v180[14]
                     && (((unsigned __int8)~(v180[10] >> 4) ^ (unsigned __int8)~(*((_DWORD *)v107 + 1) >> 12)) & 1) == 0 )
              {
                *(D3DDDI_MULTISAMPLINGMETHOD *)&v180[11] = v170.MultisampleMethod;
                v180[13] = v170.PrivateDriverFormatAttribute;
              }
              else if ( v152 || (*((_DWORD *)v107 + 1) & 2) == 0 )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 3528;
              }
            }
          }
        }
      }
      v113 = v158;
      v114 = ADAPTER_DISPLAY::SetVidPnSourceActive(
               *((ADAPTER_DISPLAY **)v11 + 406),
               v94,
               v104,
               (const struct _DXGK_DISPLAYMODE_INFO *)v180,
               v158 == 4,
               a7 != 0);
      v115 = v114;
      if ( v114 >= 0 )
      {
        ADAPTER_DISPLAY::MarkCommitVidPnOnModeChange(*((ADAPTER_DISPLAY **)v11 + 406), v94, 0);
        if ( (v95 & *((_DWORD *)a5 + 3)) != 0 )
        {
          if ( ((v113 - 1) & 0xFFFFFFFD) != 0 )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 3574;
          }
          ADAPTER_DISPLAY::SetPartOfDesktop(*((ADAPTER_DISPLAY **)v11 + 406), v94, 0);
          ADAPTER_DISPLAY::SetContentRect(*((ADAPTER_DISPLAY **)v11 + 406), v94, &stru_1401635A8);
          ADAPTER_DISPLAY::SetCddInterface(*((ADAPTER_DISPLAY **)v11 + 406), v94, 0);
          ADAPTER_DISPLAY::SetHdrEnabled(*((ADAPTER_DISPLAY **)v11 + 406), v94, 0);
        }
        else
        {
          v161 = 0;
          if ( DMMVIDPNTOPOLOGY::GetNumPathsFromSource(v168, v94, &v161) < 0 || !v161 )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 3587;
          }
          v99 = (unsigned int)(*((_DWORD *)a5 + 13) | *((_DWORD *)a5 + 2));
          if ( ((unsigned int)v99 & v95) != 0 )
          {
            if ( ((v113 - 1) & 0xFFFFFFFD) == 0 )
              ADAPTER_DISPLAY::SetPartOfDesktop(*((ADAPTER_DISPLAY **)v11 + 406), v94, 1u);
            ADAPTER_DISPLAY::SetDisplayModeInfo(
              *((ADAPTER_DISPLAY **)v11 + 406),
              v94,
              (const struct _DXGK_DISPLAYMODE_INFO *const)v180);
            ADAPTER_DISPLAY::SetLastCddIntegerVSync(*((ADAPTER_DISPLAY **)v11 + 406), v94, v180[3]);
            ADAPTER_DISPLAY::DetermineScalingCapabilities(*((ADAPTER_DISPLAY **)v11 + 406), v94);
            ADAPTER_DISPLAY::SetHdrEnabled(*((ADAPTER_DISPLAY **)v11 + 406), v94, (v95 & *((_DWORD *)a5 + 64)) != 0);
            if ( v164 && v172 )
              ADAPTER_DISPLAY::UpdateOneCddPrimaryPrivateDriverData(
                *((ADAPTER_DISPLAY **)v11 + 406),
                v94,
                *(struct DXGADAPTER **)(*((_QWORD *)v164 + 2) + 16LL));
          }
        }
      }
      else
      {
        WdLogSingleEntry3(2, v11, (unsigned int)v94, v114);
        WdLogGlobalForLineNumber = 3558;
        *((_DWORD *)a5 + v94 + 22) = v115;
        *((_DWORD *)a5 + 21) |= v95;
      }
    }
LABEL_228:
    v116 = v157;
    if ( v157 )
    {
      CurrentProcess = PsGetCurrentProcess(v99, v98);
      ProcessImageFileName = PsGetProcessImageFileName(CurrentProcess);
      *(_DWORD *)v149 = *((_DWORD *)a5 + v94 + 22);
      VIDPN_MGR::CacheDisplayModeChangeRequest(
        v165,
        (unsigned int)v94,
        v180,
        1,
        *(_QWORD *)v149,
        v116,
        *(_DWORD *)(*((_QWORD *)v11 + 406) + 424LL),
        ProcessImageFileName);
    }
    goto LABEL_230;
  }
LABEL_232:
  for ( j = 0; (unsigned int)j < v155; j = (unsigned int)(j + 1) )
  {
    v120 = 56LL * (unsigned int)j;
    v121 = DMMVIDEOPRESENTTARGETSET::GetTargetById((DMMVIDEOPRESENTTARGETSET *)v16, *(_DWORD *)((char *)Src + v120));
    v122 = v121;
    if ( v121 )
    {
      v123 = Src;
      if ( (*(_DWORD *)((_BYTE *)Src + v120 + 12) & 4) == 0
        || (v124 = v159, v125 = 1 << *(_DWORD *)(v159 + 4 * j), (v125 & *((_DWORD *)a5 + 18)) != 0)
        || (v125 & *((_DWORD *)a5 + 21)) != 0 )
      {
        DMMVIDEOPRESENTTARGET::SetTargetActivated(
          v121,
          0,
          (*(_DWORD *)((_BYTE *)Src + v120 + 32) & 0xF000000) == 201326592);
        v123 = Src;
        v124 = v159;
      }
      if ( !v152
        && *((_BYTE *)v122 + 416)
        && ((*(_DWORD *)&v123[v120 + 32] & 0xF000000) != 0xE000000 || v123[v120 + 48] != 0xFF) )
      {
        v126 = ADAPTER_DISPLAY::SetVidPnSourceVisibility(
                 *((ADAPTER_DISPLAY **)v11 + 406),
                 *(_DWORD *)(v124 + 4 * j),
                 0,
                 0x800u,
                 a7);
        if ( v126 < 0 )
        {
          WdLogSingleEntry3(2, v11, *(unsigned int *)(v159 + 4 * j), v126);
          WdLogGlobalForLineNumber = 3695;
        }
        if ( (*((_DWORD *)Src + 14 * (unsigned int)j + 8) & 0xF000000) == 0xE000000 )
        {
          v127 = *((_QWORD *)v11 + 407);
          if ( v127 )
          {
            VIDSCH_EXPORT::VidSchRequestDeferredVidPnSourceVisibility(
              *(VIDSCH_EXPORT **)(v127 + 736),
              *(struct _VIDSCH_GLOBAL **)(v127 + 744),
              *(_DWORD *)(v159 + 4 * j));
          }
          else
          {
            v128 = *(_QWORD *)(*((_QWORD *)v11 + 406) + 464LL);
            if ( v128 )
              _InterlockedExchange(
                (volatile __int32 *)(3040LL * *(unsigned int *)(v159 + 4 * j) + *(_QWORD *)(v128 + 8) + 1080),
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
      *((_DWORD *)a5 + 16) |= 1 << *(_DWORD *)(v159 + 4 * j);
  }
  auto_rc<DMMVIDPN>::reset((char *)v165 + 320, 0);
  CVidSchSuspendResume::Resume((CVidSchSuspendResume *)&v175);
  v131 = (ADAPTER_DISPLAY *)*((_QWORD *)v11 + 406);
  if ( *((_DWORD *)v131 + 24) )
  {
    v132 = 0;
    v133 = v164;
    do
    {
      v130 = (unsigned int)v132;
      v134 = 1 << v132;
      if ( ((1 << v132) & *((_DWORD *)a5 + 15)) != 0 )
        ADAPTER_DISPLAY::InvalidateDisplayModeListCacheOnSource(v131, v132);
      if ( (v134 & *((_DWORD *)a5 + 16)) != 0 )
        DXGADAPTER::NotifyMultiPlaneOverlayDisable(v11, v132);
      if ( v133 && !v152 )
      {
        if ( ADAPTER_DISPLAY::GetCddPrimaryAllocation(*((ADAPTER_DISPLAY **)v11 + 406), v132, 0)
          && ADAPTER_DISPLAY::IsCddPrimaryStale(*((ADAPTER_DISPLAY **)v11 + 406), v132) )
        {
          ADAPTER_DISPLAY::DestroyCddAllocations(v135, v133, v132);
        }
        v136 = (ADAPTER_DISPLAY *)*((_QWORD *)v11 + 406);
        v137 = (const struct _D3DKMT_DISPLAYMODE *)ADAPTER_DISPLAY::GetDisplayModeInfo(v136, v132);
        ADAPTER_DISPLAY::SetCddDisplayMode(v136, v132, v137);
        v133 = v164;
      }
      if ( (v134 & *((_DWORD *)a5 + 21)) != 0 )
      {
        v138 = *((_DWORD *)a5 + v132 + 40);
        if ( (v138 & 7) != 0 )
        {
          *((_DWORD *)a5 + 4 * (v138 & 7) + 56) = 0;
          DxgkLogCodePointPacket(
            101,
            (unsigned int)v132,
            *((_DWORD *)a5 + v132 + 40) & 7,
            2,
            *(_QWORD *)((char *)v11 + 412));
        }
        v139 = v158;
        v140 = ADAPTER_DISPLAY::SetVidPnSourceActive(*((ADAPTER_DISPLAY **)v11 + 406), v132, 0, 0, v158 == 4, a7 != 0);
        if ( v140 < 0 )
        {
          WdLogSingleEntry3(2, v11, (unsigned int)v132, v140);
          WdLogGlobalForLineNumber = 3863;
        }
        if ( v177 )
        {
          v141 = (const struct DMMVIDPN *)((char *)v177 + 96);
          v142 = (__int64)v177 + 152;
          *(_QWORD *)v150 = *((_QWORD *)v177 + 17);
          LOBYTE(v142) = 2;
          ApplyPermissionWithinThisScope::ApplyPermissionWithinThisScope(
            v179,
            ((unsigned __int64)v177 + 152) & -(__int64)((const struct DMMVIDPN *)((char *)v177 + 96) != 0),
            v142);
          v143 = DMMVIDPNTOPOLOGY::RemoveAllPathsFromSource(v141, v132);
          if ( (int)(v143 + 0x80000000) >= 0 && v143 != -1071774919 )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 3878;
          }
          ApplyPermissionWithinThisScope::~ApplyPermissionWithinThisScope((ApplyPermissionWithinThisScope *)v179);
        }
        v133 = v164;
        if ( v164 )
          ADAPTER_DISPLAY::DestroyCddAllocations(*((ADAPTER_DISPLAY **)v11 + 406), v164, v132);
        if ( ((v139 - 1) & 0xFFFFFFFD) == 0 )
        {
          ADAPTER_DISPLAY::SetPartOfDesktop(*((ADAPTER_DISPLAY **)v11 + 406), v132, 0);
          ADAPTER_DISPLAY::SetContentRect(*((ADAPTER_DISPLAY **)v11 + 406), v132, &stru_1401635A8);
          ADAPTER_DISPLAY::SetCddInterface(*((ADAPTER_DISPLAY **)v11 + 406), v132, 0);
        }
        ADAPTER_DISPLAY::SetVidPnPrimaryTarget(*((ADAPTER_DISPLAY **)v11 + 406), v132, 0xFFFFFFFF);
        ADAPTER_DISPLAY::MarkCommitVidPnOnModeChange(*((ADAPTER_DISPLAY **)v11 + 406), v132, 1u);
        ADAPTER_DISPLAY::SetHdrEnabled(*((ADAPTER_DISPLAY **)v11 + 406), v132, 0);
      }
      v131 = (ADAPTER_DISPLAY *)*((_QWORD *)v11 + 406);
      v132 = (unsigned int)(v132 + 1);
    }
    while ( (unsigned int)v132 < *((_DWORD *)v131 + 24) );
    v16 = v166;
  }
  if ( v177 )
  {
    *(_DWORD *)v150 = *((_DWORD *)a5 + 63);
    *(_DWORD *)v149 = *((_DWORD *)a5 + 62);
    ADAPTER_DISPLAY::SetSyncLockGroup(
      v131,
      1,
      *((unsigned int *)a5 + 60),
      *((unsigned int *)a5 + 61),
      *(_QWORD *)v149,
      *(_QWORD *)v150);
    v144 = *((_QWORD *)v11 + 406);
    if ( *(_DWORD *)(v144 + 96) )
    {
      v145 = 0;
      do
      {
        v146 = (unsigned int)v145;
        v147 = *((_DWORD *)a5 + v145 + 40) & 7;
        v145 = (unsigned int)(v145 + 1);
        v129 = *((_DWORD *)a5 + 4 * v147 + 56) != 0 ? v147 : 0;
        v130 = 4024 * v146;
        *(_DWORD *)(4024 * v146 + *(_QWORD *)(v144 + 128) + 3804) = v129;
        v144 = *((_QWORD *)v11 + 406);
      }
      while ( (unsigned int)v145 < *(_DWORD *)(v144 + 96) );
    }
  }
  DxgkInvalidateQdcCache(v130, v129);
  CVidSchSuspendResume::Resume((CVidSchSuspendResume *)&v175);
  if ( v16 )
    ReferenceCounted::Release((ReferenceCounted *)(v16 + 64));
  wistd::unique_ptr<unsigned int [0],wistd::default_delete<unsigned int [0]>>::reset(&v167);
  auto_rc<DMMVIDPN const>::reset(&v178, 0);
  v13 = 0;
LABEL_291:
  wistd::unique_ptr<unsigned int [0],wistd::default_delete<unsigned int [0]>>::reset(&v169);
  wistd::unique_ptr<unsigned int [0],wistd::default_delete<unsigned int [0]>>::reset(&v159);
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
