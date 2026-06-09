# OBTAIN_MODES_ON_SOURCE::operator()(_D3DKMT_DISPLAYMODE * *,uint *,_D3DKMT_DISPLAYMODE * *,uint *)

- ea: `0x140330bdc`
- end: `0x140332181`
- name: `??ROBTAIN_MODES_ON_SOURCE@@QEBAJPEAPEAU_D3DKMT_DISPLAYMODE@@PEAI01@Z`
- size: `5541`
- prototype: `__int64 __usercall@<rax>(OBTAIN_MODES_ON_SOURCE *this@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, reparse_path`

## callers

- `0x1401db134`

## callees

- `0x140009030`
- `0x14000d7d0`
- `0x14001b890`
- `0x14003cf38`
- `0x140042198`
- `0x14004506c`
- `0x140046520`
- `0x140047960`
- `0x140053454`
- `0x140070fa8`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1400a0540`
- `0x140229d70`
- `0x140330ac0`
- `0x140330bdc`
- `0x140332188`
- `0x140332200`
- `0x140332314`
- `0x140332f58`
- `0x140333288`
- `0x140333480`
- `0x140368514`

## import_xrefs

- `watchdog!WdLogSingleEntry4` at `0x1403318ad`
- `watchdog!WdLogSingleEntry4` at `0x14033191c`
- `watchdog!WdLogSingleEntry4` at `0x140331b16`
- `watchdog!WdLogSingleEntry4` at `0x140331c25`
- `watchdog!WdLogSingleEntry4` at `0x1403318ad`
- `watchdog!WdLogSingleEntry4` at `0x14033191c`
- `watchdog!WdLogSingleEntry4` at `0x140331b16`
- `watchdog!WdLogSingleEntry4` at `0x140331c25`
- `watchdog!WdLogSingleEntry2` at `0x140331025`
- `watchdog!WdLogSingleEntry2` at `0x140331128`
- `watchdog!WdLogSingleEntry2` at `0x1403311ce`
- `watchdog!WdLogSingleEntry2` at `0x140331025`
- `watchdog!WdLogSingleEntry2` at `0x140331128`
- `watchdog!WdLogSingleEntry2` at `0x1403311ce`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140331192`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140331192`
- `watchdog!WdLogSingleEntry3` at `0x140330cf5`
- `watchdog!WdLogSingleEntry3` at `0x140331cb9`
- `watchdog!WdLogSingleEntry3` at `0x140331e3e`
- `watchdog!WdLogSingleEntry3` at `0x14033210f`
- `watchdog!WdLogSingleEntry3` at `0x140330cf5`
- `watchdog!WdLogSingleEntry3` at `0x140331cb9`
- `watchdog!WdLogSingleEntry3` at `0x140331e3e`
- `watchdog!WdLogSingleEntry3` at `0x14033210f`
- `watchdog!WdLogSingleEntry0` at `0x140330d4a`
- `watchdog!WdLogSingleEntry0` at `0x140331ed6`
- `watchdog!WdLogSingleEntry0` at `0x140332026`
- `watchdog!WdLogSingleEntry0` at `0x140330d4a`
- `watchdog!WdLogSingleEntry0` at `0x140331ed6`
- `watchdog!WdLogSingleEntry0` at `0x140332026`
- `watchdog!WdLogSingleEntry5` at `0x1403317df`
- `watchdog!WdLogSingleEntry5` at `0x140331a4b`
- `watchdog!WdLogSingleEntry5` at `0x1403317df`
- `watchdog!WdLogSingleEntry5` at `0x140331a4b`
- `watchdog!WdLogSingleEntry1` at `0x140330dbd`
- `watchdog!WdLogSingleEntry1` at `0x140330ebc`
- `watchdog!WdLogSingleEntry1` at `0x140330f33`
- `watchdog!WdLogSingleEntry1` at `0x1403319a3`
- `watchdog!WdLogSingleEntry1` at `0x140331bd4`
- `watchdog!WdLogSingleEntry1` at `0x140331c6f`
- `watchdog!WdLogSingleEntry1` at `0x140331d02`
- `watchdog!WdLogSingleEntry1` at `0x140331d6a`
- `watchdog!WdLogSingleEntry1` at `0x140331df0`
- `watchdog!WdLogSingleEntry1` at `0x140331f7b`
- `watchdog!WdLogSingleEntry1` at `0x14033208a`
- `watchdog!WdLogSingleEntry1` at `0x140330dbd`
- `watchdog!WdLogSingleEntry1` at `0x140330ebc`
- `watchdog!WdLogSingleEntry1` at `0x140330f33`
- `watchdog!WdLogSingleEntry1` at `0x1403319a3`
- `watchdog!WdLogSingleEntry1` at `0x140331bd4`
- `watchdog!WdLogSingleEntry1` at `0x140331c6f`
- `watchdog!WdLogSingleEntry1` at `0x140331d02`
- `watchdog!WdLogSingleEntry1` at `0x140331d6a`
- `watchdog!WdLogSingleEntry1` at `0x140331df0`
- `watchdog!WdLogSingleEntry1` at `0x140331f7b`
- `watchdog!WdLogSingleEntry1` at `0x14033208a`

## string_xrefs

- `0x1403319c0`: `Failed call to DXGDMM_VIDPNTOPOLOGY_INTERFACE::pfnAcquirePathInfo. (Status = 0x%I64x)`
- `0x140331c8d`: `Failed call to DXGDMM_VIDPNTOPOLOGY_INTERFACE::pfnAcquirePathInfo. (Status = 0x%I64x)`
- `0x1403318b9`: `Failed to pin the reported-as-supported rotation mode 0x%I64x on the path (0x%I64x, 0x%I64x) because of not supported by driver, returning 0x%I64x.`
- `0x1403317f0`: `Unable to set rotation on the path. (Status = 0x%I64x, m_VidPnSourceId = 0x%I64x, PrimVidPnTargetId = 0x%I64x, m_hVidPnTopology = 0x%I64x, PathRotation = 0x%I64x)`
- `0x140331a5c`: `Unable to set scaling on the path. ( Status = 0x%I64x, m_VidPnSourceId = 0x%I64x, PrimVidPnTargetId = 0x%I64x, m_hVidPnTopology = 0x%I64x, PathScaling = 0x%I64x)`
- `0x140331b22`: `Failed to pin the reported-as-supported scaling mode 0x%I64x on the path (0x%I64x, 0x%I64x) because of not supported by driver, returning 0x%I64x.`
- `0x140332120`: `Failed call to DXGDMM_VIDPNTOPOLOGY_INTERFACE::pfnEnumPathTargetsFromSource. (Status = 0x%I64x, m_VidPnSourceId = 0x%I64x, PathIndex = 0x%I64x)`
- `0x140330d06`: `Failed call to DXGDMM_VIDPNTOPOLOGY_INTERFACE::pfnGetPathImportance. (Status = 0x%I64x, PrimVidPnTargetId = 0x%I64x, m_VidPnSourceId = 0x%I64x)`

## pseudocode

```c
__int64 __fastcall OBTAIN_MODES_ON_SOURCE::operator()(
        OBTAIN_MODES_ON_SOURCE *this,
        struct _D3DKMT_DISPLAYMODE **a2,
        unsigned int *a3,
        void **a4,
        unsigned int *a5)
{
  enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY v5; // r12d
  unsigned int v6; // ebx
  int v8; // r14d
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rsi
  __int64 v14; // r8
  __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // rbx
  __int64 v18; // rsi
  int VideoOutputTechnology; // eax
  __int64 v20; // rdi
  const wchar_t *v21; // r9
  int DisplayOnlyDriverUseRawModes; // eax
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rax
  __int64 v29; // r14
  __int64 v30; // rdi
  struct _D3DDDI_RATIONAL v31; // rcx
  void (__fastcall *v32)(__int64, __int64); // r12
  __int64 (__fastcall *v33)(struct _D3DDDI_RATIONAL, struct _D3DDDI_RATIONAL *); // rax
  int v34; // eax
  __int64 v35; // r8
  _DWORD *v36; // r13
  unsigned int v37; // eax
  int v38; // eax
  __int64 v39; // rax
  __int64 v40; // rcx
  __int64 (__fastcall *v41)(__int64, _QWORD, struct _D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT **, __int64 *); // rax
  int v42; // eax
  __int64 v43; // rsi
  __int64 (__fastcall *v44)(__int64, struct _D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT **); // rax
  int v45; // eax
  struct _D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT *i; // rdx
  __int64 v47; // r8
  unsigned int *v48; // r12
  int v49; // eax
  __int64 v50; // r8
  int v51; // eax
  __int64 v52; // rcx
  __int64 v53; // rax
  bool v54; // zf
  __int64 v55; // rax
  __int64 v56; // rdx
  __int64 v57; // rcx
  int v58; // eax
  struct _D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT v59; // edi
  char v60; // al
  char v61; // al
  unsigned int j; // ecx
  int v63; // eax
  __int64 v64; // rax
  __int64 v65; // rdx
  __int64 v66; // rcx
  int v67; // eax
  struct _D3DKMDT_VIDPN_PRESENT_PATH_ROTATION_SUPPORT v68; // ebx
  enum _D3DKMDT_VIDPN_PRESENT_PATH_ROTATION k; // eax
  char v70; // cl
  char v71; // al
  bool v72; // r8
  int v73; // eax
  __int64 v74; // rcx
  bool v75; // zf
  struct _D3DDDI_RATIONAL v76; // r8
  _DWORD *v77; // rcx
  int v78; // r8d
  struct _D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT *m; // rax
  int v80; // r8d
  unsigned __int64 v81; // rdx
  unsigned __int64 v82; // rcx
  bool v83; // r8
  int v84; // eax
  int v85; // eax
  int v86; // eax
  int v87; // eax
  int v88; // eax
  __int64 v89; // rbx
  __int64 v90; // rdi
  __int64 v91; // rsi
  __int64 v92; // rdi
  const wchar_t *v93; // r9
  bool v94; // zf
  __int64 v95; // rdi
  __int64 v96; // rdx
  __int64 v97; // rbx
  __int64 v98; // rbx
  __int64 v99; // rdi
  __int64 v100; // rsi
  __int64 v101; // rdi
  const wchar_t *v102; // r9
  int v103; // eax
  __int64 v104; // rax
  struct _D3DKMT_DISPLAYMODE **v105; // rbx
  struct _D3DKMT_DISPLAYMODE *v106; // rax
  unsigned int v107; // eax
  __int64 v108; // rax
  unsigned __int64 v109; // kr00_8
  int UniqueModes; // eax
  __int64 v111; // rbx
  _QWORD *v112; // rdi
  __int64 v113; // rcx
  __int64 v114; // rax
  struct _D3DKMT_DISPLAYMODE *v115; // rax
  int v116; // eax
  __int64 v117; // rbx
  __int64 v118; // [rsp+20h] [rbp-E0h]
  char v119; // [rsp+50h] [rbp-B0h] BYREF
  char v120[3]; // [rsp+51h] [rbp-AFh] BYREF
  enum _D3DKMDT_VIDPN_PRESENT_PATH_ROTATION v121; // [rsp+54h] [rbp-ACh] BYREF
  enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY v122; // [rsp+58h] [rbp-A8h] BYREF
  char v123; // [rsp+5Ch] [rbp-A4h]
  char v124; // [rsp+5Dh] [rbp-A3h]
  char v125[2]; // [rsp+5Eh] [rbp-A2h] BYREF
  struct _D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT *v126; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v127; // [rsp+68h] [rbp-98h]
  void (__fastcall *v128)(__int64, __int64); // [rsp+70h] [rbp-90h]
  __int16 v129[2]; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v130; // [rsp+7Ch] [rbp-84h]
  char v131[8]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int *v132; // [rsp+88h] [rbp-78h]
  void (__fastcall *v133)(__int64, _DWORD *); // [rsp+90h] [rbp-70h]
  __int64 v134; // [rsp+98h] [rbp-68h]
  int v135; // [rsp+A0h] [rbp-60h]
  struct _D3DDDI_RATIONAL v136; // [rsp+A8h] [rbp-58h] BYREF
  char v137[8]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v138; // [rsp+B8h] [rbp-48h]
  void (__fastcall *v139)(__int64, __int64); // [rsp+C0h] [rbp-40h]
  __int64 v140; // [rsp+C8h] [rbp-38h]
  int v141; // [rsp+D0h] [rbp-30h]
  __int64 v142; // [rsp+D8h] [rbp-28h] BYREF
  char v143[8]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int *v144; // [rsp+E8h] [rbp-18h]
  void (__fastcall *v145)(__int64, unsigned int *); // [rsp+F0h] [rbp-10h]
  __int64 v146; // [rsp+F8h] [rbp-8h]
  int v147; // [rsp+100h] [rbp+0h]
  struct _D3DKMDT_VIDPN_PRESENT_PATH_ROTATION_SUPPORT *v148; // [rsp+108h] [rbp+8h] BYREF
  __int64 v149; // [rsp+110h] [rbp+10h] BYREF
  int v150; // [rsp+118h] [rbp+18h] BYREF
  unsigned int v151; // [rsp+11Ch] [rbp+1Ch]
  struct _D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT *v152; // [rsp+120h] [rbp+20h] BYREF
  __int64 v153; // [rsp+128h] [rbp+28h] BYREF
  void **v154; // [rsp+130h] [rbp+30h]
  struct _D3DKMT_DISPLAYMODE v155; // [rsp+138h] [rbp+38h] BYREF
  void *v156; // [rsp+168h] [rbp+68h]
  struct _D3DKMT_DISPLAYMODE **v157; // [rsp+170h] [rbp+70h]
  unsigned int *v158; // [rsp+178h] [rbp+78h]
  unsigned int *v159; // [rsp+180h] [rbp+80h]
  struct _D3DKMDT_MONITOR_SOURCE_MODE v160; // [rsp+190h] [rbp+90h] BYREF

  v159 = a5;
  v5 = D3DKMDT_VOT_OTHER;
  v130 = -1;
  v6 = 0;
  v154 = a4;
  v158 = a3;
  v157 = a2;
  v8 = 255;
  while ( 1 )
  {
    v9 = *((_QWORD *)this + 4);
    v10 = *((unsigned int *)this + 10);
    v11 = *((_QWORD *)this + 3);
    v122 = D3DKMDT_VOT_OTHER;
    v12 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *))(v9 + 8))(
            v11,
            v10,
            v6,
            &v122);
    v13 = v12;
    if ( v12 < 0 )
    {
      WdLogSingleEntry3(1, v12, *((unsigned int *)this + 10), v6);
      WdLogGlobalForLineNumber = 652;
      DxgkLogInternalTriageEvent(
        0,
        262146,
        -1,
        (unsigned int)L"Failed call to DXGDMM_VIDPNTOPOLOGY_INTERFACE::pfnEnumPathTargetsFromSource. (Status = 0x%I64x, m_"
                       "VidPnSourceId = 0x%I64x, PathIndex = 0x%I64x)",
        v13,
        *((unsigned int *)this + 10),
        v6,
        0,
        0);
      return (unsigned int)v13;
    }
    v14 = (unsigned int)v122;
    if ( v122 == D3DKMDT_VOT_OTHER )
      break;
    ++*((_DWORD *)this + 13);
    v15 = *((unsigned int *)this + 10);
    v121 = D3DKMDT_VPPR_UNINITIALIZED;
    v129[0] = -1;
    v16 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, enum _D3DKMDT_VIDPN_PRESENT_PATH_ROTATION *, __int16 *))(*((_QWORD *)this + 4) + 112LL))(
            *((_QWORD *)this + 3),
            v15,
            v14,
            &v121,
            v129);
    v13 = v16;
    if ( v16 < 0 )
    {
      WdLogSingleEntry3(2, v16, (unsigned int)v5, *((unsigned int *)this + 10));
      WdLogGlobalForLineNumber = 675;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Failed call to DXGDMM_VIDPNTOPOLOGY_INTERFACE::pfnGetPathImportance. (Status = 0x%I64x, PrimVidPnT"
                       "argetId = 0x%I64x, m_VidPnSourceId = 0x%I64x)",
        v13,
        (unsigned int)v5,
        *((unsigned int *)this + 10),
        0,
        0);
      return (unsigned int)v13;
    }
    if ( v5 == D3DKMDT_VOT_OTHER || v121 < v8 )
    {
      v5 = v122;
      v8 = v121;
      v130 = v122;
      *((_DWORD *)this + 12) = v6;
    }
    ++v6;
  }
  v17 = v130;
  if ( v130 == -1 && *((_DWORD *)this + 13) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 691;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"(PrimVidPnTargetId != D3DDDI_ID_UNINITIALIZED) || (m_CloneGroupSize == 0)",
      691,
      0,
      0,
      0,
      0);
  }
  v18 = *(_QWORD *)this;
  v156 = *(void **)this;
  v122 = D3DKMDT_VOT_HD15;
  VideoOutputTechnology = DmmGetVideoOutputTechnology(v156, v17, 0, &v122);
  v20 = VideoOutputTechnology;
  if ( VideoOutputTechnology < 0 )
  {
    WdLogSingleEntry1(2);
    v21 = L"Failed call to DmmGetVideoOutputTechnology(Status = 0x%I64x)";
    WdLogGlobalForLineNumber = 703;
LABEL_15:
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v21, v20, 0, 0, 0, 0);
    return (unsigned int)v20;
  }
  if ( v122 == D3DKMDT_VOT_MIRACAST
    || v122 == D3DKMDT_VOT_INDIRECT_WIRED
    || (v124 = 0, v122 == (D3DKMDT_VOT_SVIDEO_7PIN|D3DKMDT_VOT_INDIRECT_WIRED)) )
  {
    v124 = 1;
  }
  if ( *(_QWORD *)(v18 + 3240)
    || (DisplayOnlyDriverUseRawModes = ADAPTER_DISPLAY::GetDisplayOnlyDriverUseRawModes(*(ADAPTER_DISPLAY **)(v18 + 3232)),
        v123 = 1,
        !DisplayOnlyDriverUseRawModes) )
  {
    v123 = 0;
  }
  memset(&v160, 0, sizeof(v160));
  if ( DmmGetPreferredMonitorSourceModeOnTarget(*(void **)this, v17, &v160) < 0 )
    memset(&v160, 0, sizeof(v160));
  v24 = *((_QWORD *)this + 2);
  v25 = *((unsigned int *)this + 10);
  v26 = *((_QWORD *)this + 1);
  v149 = 0;
  v136 = 0;
  v27 = (*(__int64 (__fastcall **)(__int64, __int64, struct _D3DDDI_RATIONAL *, __int64 *))(v24 + 8))(
          v26,
          v25,
          &v136,
          &v149);
  v20 = v27;
  if ( v27 < 0 )
  {
    WdLogSingleEntry1(2);
    v21 = L"Failed call to DXGDMM_VIDPN_INTERFACE::pfnAcquireSourceModeSet. (Status = 0x%I64x)";
    WdLogGlobalForLineNumber = 733;
    goto LABEL_15;
  }
  v28 = *((_QWORD *)this + 2);
  v29 = (__int64)v136;
  v30 = *((_QWORD *)this + 1);
  v31 = v136;
  v127 = v30;
  v32 = *(void (__fastcall **)(__int64, __int64))(v28 + 16);
  v136 = 0;
  v128 = v32;
  v132 = 0;
  v33 = *(__int64 (__fastcall **)(struct _D3DDDI_RATIONAL, struct _D3DDDI_RATIONAL *))(v149 + 8);
  v133 = 0;
  v134 = 0;
  v135 = 0;
  v131[0] = 0;
  v34 = ((__int64 (__fastcall *)(_QWORD, _QWORD))v33)(v31, &v136);
  v13 = v34;
  if ( v34 < 0 )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 753;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Failed call to DXGDMM_VIDPNSOURCEMODESET_INTERFACE::pfnAcquireFirstModeInfo. (Status = 0x%I64x)",
      v13,
      0,
      0,
      0,
      0);
    if ( v29 )
      v32(v30, v29);
    return (unsigned int)v13;
  }
  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))DXGDMM::AutoRelease<_D3DKMDT_VIDPN_PRESENT_PATH const *,long (*)(D3DKMDT_HVIDPNTOPOLOGY__ *,_D3DKMDT_VIDPN_PRESENT_PATH const *),D3DKMDT_HVIDPNTOPOLOGY__ *>::Own)(
    v131,
    v136,
    *(_QWORD *)(v149 + 32),
    v29);
  *(_BYTE *)(ExposedViaHandle<DMMVIDPN,D3DKMDT_HVIDPN__ *>::GetFromHandle(*((_QWORD *)this + 1)) + 296) = 1;
  while ( 1 )
  {
    v36 = v132;
    if ( !v132 )
      break;
    v37 = v132[1];
    if ( (v37 == 3 || v37 == 4 || v37 == 1) && v132[2] == v132[4] && v132[3] == v132[5] )
    {
      LOBYTE(v35) = 1;
      v38 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(v149 + 40))(v29, *v132, v35);
      if ( v38 >= 0 )
      {
        v39 = *((_QWORD *)this + 2);
        v40 = *((_QWORD *)this + 1);
        v142 = 0;
        v126 = 0;
        v41 = *(__int64 (__fastcall **)(__int64, _QWORD, struct _D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT **, __int64 *))(v39 + 24);
        v138 = 0;
        v139 = 0;
        v140 = 0;
        v141 = 0;
        v137[0] = 0;
        v42 = v41(v40, (unsigned int)v17, &v126, &v142);
        v20 = v42;
        if ( v42 < 0 )
        {
          WdLogSingleEntry1(2);
          v102 = L"Failed call to DXGDMM_VIDPNSOURCEMODESET_INTERFACE::pfnAcquireTargetModeSet. (Status = 0x%I64x)";
          WdLogGlobalForLineNumber = 818;
          goto LABEL_181;
        }
        DXGDMM::AutoRelease<D3DKMDT_HVIDPNTARGETMODESET__ *,long (*)(D3DKMDT_HVIDPN__ *,D3DKMDT_HVIDPNTARGETMODESET__ *),D3DKMDT_HVIDPN__ *>::Own(
          v137,
          v126,
          *(_QWORD *)(*((_QWORD *)this + 2) + 32LL),
          *((_QWORD *)this + 1));
        v43 = v138;
        v126 = 0;
        v144 = 0;
        v44 = *(__int64 (__fastcall **)(__int64, struct _D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT **))(v142 + 8);
        v145 = 0;
        v146 = 0;
        v147 = 0;
        v143[0] = 0;
        v45 = v44(v138, &v126);
        v20 = v45;
        if ( v45 < 0 )
        {
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 838;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Failed call to DXGDMM_VIDPNSOURCEMODESET_INTERFACE::pfnAcquireFirstModeInfo. (Status = 0x%I64x)",
            v20,
            0,
            0,
            0,
            0);
          if ( v137[0] )
            v139(v140, v43);
          goto LABEL_182;
        }
        for ( i = v126; ; i = v152 )
        {
          DXGDMM::AutoRelease<_D3DKMDT_VIDPN_PRESENT_PATH const *,long (*)(D3DKMDT_HVIDPNTOPOLOGY__ *,_D3DKMDT_VIDPN_PRESENT_PATH const *),D3DKMDT_HVIDPNTOPOLOGY__ *>::Own(
            v143,
            i,
            *(_QWORD *)(v142 + 32),
            v43);
          v48 = v144;
          if ( !v144 )
            break;
          LOBYTE(v47) = 1;
          v49 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(v142 + 48))(v43, *v144, v47);
          if ( v49 >= 0 )
          {
            v120[0] = 0;
            v150 = 0;
            if ( (unsigned int)(v36[1] - 3) <= 1 || v123 )
            {
              v120[0] = 1;
            }
            else
            {
              v51 = (*(__int64 (__fastcall **)(__int64, _QWORD, char *, int *))(v142 + 64))(v43, *v48, v120, &v150);
              v20 = v51;
              if ( v51 == -1071774920 )
              {
                v53 = WdLogNewEntry5_WdTrace(v52);
                *(_QWORD *)(v53 + 24) = (unsigned int)v17;
                *(_QWORD *)(v53 + 32) = *((unsigned int *)this + 10);
                WdLogGlobalForLineNumber = 883;
              }
              else if ( v51 < 0 )
              {
                WdLogSingleEntry2(2, v51);
                WdLogGlobalForLineNumber = 888;
                DxgkLogInternalTriageEvent(
                  0,
                  0x40000,
                  -1,
                  (unsigned int)L"Failed to determine whether mode is supported by monitor. (Status = 0x%I64x, spVidPnTarg"
                                 "etModeInfo.GetResource() = 0x%I64x)",
                  v20,
                  (__int64)v48,
                  0,
                  0,
                  0);
                goto LABEL_52;
              }
            }
            v119 = 0;
            if ( v160.VideoSignalInfo.ActiveSize.cx == v36[2] && v160.VideoSignalInfo.ActiveSize.cy == v36[3] )
            {
              LOBYTE(v50) = v124;
              if ( (*(int (__fastcall **)(unsigned int *, struct _D3DKMDT_MONITOR_SOURCE_MODE *, __int64, char *))(v142 + 80))(
                     v48,
                     &v160,
                     v50,
                     &v119) < 0 )
                v119 = 0;
            }
            v55 = *((_QWORD *)this + 4);
            v56 = *((unsigned int *)this + 10);
            v57 = *((_QWORD *)this + 3);
            v126 = 0;
            v58 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, struct _D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT **))(v55 + 24))(
                    v57,
                    v56,
                    (unsigned int)v17,
                    &v126);
            v20 = v58;
            if ( v58 >= 0 )
            {
              v59 = v126[4];
              (*(void (__fastcall **)(_QWORD))(*((_QWORD *)this + 4) + 32LL))(*((_QWORD *)this + 3));
              if ( v36[2] == v48[5] && v36[3] == v48[6] )
                v60 = (char)v59;
              else
                v60 = -((*(_BYTE *)&v59 & 0x1E) != 0);
              v61 = v60 & 1;
              LOBYTE(v129[0]) = v61;
              for ( j = 0; ; j = v151 + 1 )
              {
                v151 = j;
                if ( j >= 5 || !v61 )
                {
                  v85 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(*((_QWORD *)this + 4) + 72LL))(
                          *((_QWORD *)this + 3),
                          *((unsigned int *)this + 10),
                          (unsigned int)v17,
                          0);
                  LODWORD(v126) = v85;
                  if ( v85 >= 0 )
                    goto LABEL_118;
                  v101 = v85;
                  WdLogSingleEntry4(2, v85, *((unsigned int *)this + 10), *((_QWORD *)this + 3), v17);
                  WdLogGlobalForLineNumber = 1208;
                  DxgkLogInternalTriageEvent(
                    0,
                    0x40000,
                    -1,
                    (unsigned int)L"Unable to unpin scaling. (Status = 0x%I64x, m_VidPnSourceId = 0x%I64x, m_hVidPnTopolog"
                                   "y = 0x%I64x, PrimVidPnTargetId = 0x%I64x)",
                    v101,
                    *((unsigned int *)this + 10),
                    *((_QWORD *)this + 3),
                    v17,
                    0);
LABEL_144:
                  if ( v143[0] )
                    v145(v146, v48);
                  if ( v137[0] )
                  {
                    v96 = v43;
                    goto LABEL_157;
                  }
LABEL_158:
                  v94 = v131[0] == 0;
LABEL_159:
                  if ( !v94 )
                    v133(v134, v36);
                  if ( v29 )
                    v128(v127, v29);
                  return (unsigned int)v126;
                }
                v122 = dword_1400ED508[j];
                if ( BmlIsSupportedPathScaling((enum _D3DKMDT_VIDPN_PRESENT_PATH_SCALING)v122, v59) )
                {
                  LOBYTE(v118) = 1;
                  v63 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, __int64))(*((_QWORD *)this + 4) + 64LL))(
                          *((_QWORD *)this + 3),
                          *((unsigned int *)this + 10),
                          (unsigned int)v17,
                          (unsigned int)v122,
                          v118);
                  LODWORD(v126) = v63;
                  if ( v63 == -1071774970 )
                  {
                    v92 = v122;
                    WdLogSingleEntry4(1, v122, *((unsigned int *)this + 10), v17, -1071774970);
                    v93 = L"Failed to pin the reported-as-supported scaling mode 0x%I64x on the path (0x%I64x, 0x%I64x) be"
                           "cause of not supported by driver, returning 0x%I64x.";
                    WdLogGlobalForLineNumber = 976;
LABEL_165:
                    DxgkLogInternalTriageEvent(
                      0,
                      262147,
                      -1,
                      (_DWORD)v93,
                      v92,
                      *((unsigned int *)this + 10),
                      v17,
                      -1071774970,
                      0);
                    if ( v143[0] )
                      v145(v146, v48);
                    if ( v137[0] )
                      v139(v140, v43);
                    if ( v131[0] )
                      v133(v134, v36);
                    if ( v29 )
                      v128(v127, v29);
                    return 3223192326LL;
                  }
                  if ( v63 < 0 )
                  {
                    v98 = v122;
                    v99 = v130;
                    v100 = v63;
                    WdLogSingleEntry5(2, v63, *((unsigned int *)this + 10), v130, *((_QWORD *)this + 3), v122);
                    WdLogGlobalForLineNumber = 982;
                    DxgkLogInternalTriageEvent(
                      0,
                      0x40000,
                      -1,
                      (unsigned int)L"Unable to set scaling on the path. ( Status = 0x%I64x, m_VidPnSourceId = 0x%I64x, Pr"
                                     "imVidPnTargetId = 0x%I64x, m_hVidPnTopology = 0x%I64x, PathScaling = 0x%I64x)",
                      v100,
                      *((unsigned int *)this + 10),
                      v99,
                      *((_QWORD *)this + 3),
                      v98);
                    if ( v143[0] )
                      v145(v146, v48);
                    if ( v137[0] )
                    {
                      v96 = v138;
LABEL_157:
                      v139(v140, v96);
                    }
                    goto LABEL_158;
                  }
                  v64 = *((_QWORD *)this + 4);
                  v65 = *((unsigned int *)this + 10);
                  v66 = *((_QWORD *)this + 3);
                  v148 = 0;
                  v67 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, struct _D3DKMDT_VIDPN_PRESENT_PATH_ROTATION_SUPPORT **))(v64 + 24))(
                          v66,
                          v65,
                          (unsigned int)v17,
                          &v148);
                  LODWORD(v126) = v67;
                  if ( v67 < 0 )
                  {
                    v97 = v67;
                    WdLogSingleEntry1(2);
                    WdLogGlobalForLineNumber = 997;
                    DxgkLogInternalTriageEvent(
                      0,
                      0x40000,
                      -1,
                      (unsigned int)L"Failed call to DXGDMM_VIDPNTOPOLOGY_INTERFACE::pfnAcquirePathInfo. (Status = 0x%I64x)",
                      v97,
                      0,
                      0,
                      0,
                      0);
                    if ( v143[0] )
                      v145(v146, v48);
                    if ( v137[0] )
                      v139(v140, v43);
                    v94 = v131[0] == 0;
                    goto LABEL_159;
                  }
                  v68 = v148[6];
                  (*(void (__fastcall **)(_QWORD))(*((_QWORD *)this + 4) + 32LL))(*((_QWORD *)this + 3));
                  for ( k = D3DKMDT_VPPR_IDENTITY; ; k = v121 + 1 )
                  {
                    v121 = k;
                    if ( k > D3DKMDT_VPPR_ROTATE270 )
                      break;
                    if ( BmlIsSupportedPathRotation(k, v68) )
                    {
                      v125[0] = 0;
                      memset(&v155, 0, sizeof(v155));
                      v70 = *((_QWORD *)v156 + 405)
                         || !*(_BYTE *)(*((_QWORD *)v156 + 404) + 289LL)
                         || v121 == D3DKMDT_VPPR_IDENTITY;
                      v71 = v119 && v122 == D3DKMDT_VOT_SVIDEO;
                      PopulateDisplayModeFromPresentPath(
                        (_DWORD)v36,
                        (_DWORD)v48,
                        v122,
                        v121,
                        v120[0],
                        v71,
                        v70,
                        v150,
                        (__int64)&v155,
                        (__int64)v125);
                      if ( *((_DWORD *)this + 13) > 1u )
                      {
                        LOBYTE(v118) = 0;
                        v73 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))(*((_QWORD *)this + 4)
                                                                                                + 80LL))(
                                *((_QWORD *)this + 3),
                                *((unsigned int *)this + 10),
                                v130,
                                (unsigned int)v121,
                                v118);
                        LODWORD(v148) = v73;
                        if ( v73 == -1071774970 )
                        {
                          v17 = v130;
                          v92 = v121;
                          WdLogSingleEntry4(1, v121, *((unsigned int *)this + 10), v130, -1071774970);
                          v93 = L"Failed to pin the reported-as-supported rotation mode 0x%I64x on the path (0x%I64x, 0x%I"
                                 "64x) because of not supported by driver, returning 0x%I64x.";
                          WdLogGlobalForLineNumber = 1063;
                          goto LABEL_165;
                        }
                        if ( v73 < 0 )
                        {
                          v89 = v121;
                          v90 = v130;
                          v91 = v73;
                          WdLogSingleEntry5(2, v73, *((unsigned int *)this + 10), v130, *((_QWORD *)this + 3), v121);
                          WdLogGlobalForLineNumber = 1069;
                          DxgkLogInternalTriageEvent(
                            0,
                            0x40000,
                            -1,
                            (unsigned int)L"Unable to set rotation on the path. (Status = 0x%I64x, m_VidPnSourceId = 0x%I6"
                                           "4x, PrimVidPnTargetId = 0x%I64x, m_hVidPnTopology = 0x%I64x, PathRotation = 0x%I64x)",
                            v91,
                            *((unsigned int *)this + 10),
                            v90,
                            *((_QWORD *)this + 3),
                            v89);
                          if ( v143[0] )
                            v145(v146, v48);
                          if ( v137[0] )
                            v139(v140, v138);
                          v75 = v131[0] == 0;
                          goto LABEL_132;
                        }
                      }
                      if ( v155.Format != D3DDDIFMT_A8R8G8B8 && *((_BYTE *)this + 44)
                        || v155.Format <= (unsigned int)D3DDDIFMT_P8
                        && (v74 = 0x20003900000LL, _bittest64(&v74, (unsigned int)v155.Format)) )
                      {
                        if ( v154 )
                        {
                          LODWORD(v148) = MODE_UNION_LIST::AddUniqueMode(
                                            (OBTAIN_MODES_ON_SOURCE *)((char *)this + 104),
                                            &v155);
                          if ( (int)v148 < 0 )
                          {
                            if ( v143[0] )
                              v145(v146, v48);
                            if ( v137[0] )
                              v139(v140, v43);
                            v75 = v131[0] == 0;
LABEL_132:
                            if ( !v75 )
                              v133(v134, v36);
                            if ( v29 )
                              v128(v127, v29);
                            return (unsigned int)v148;
                          }
                        }
                      }
                      else
                      {
                        LODWORD(v126) = OBTAIN_MODES_ON_SOURCE::_AddMode(this, &v155, v72, v125[0] != 0);
                        if ( (int)v126 < 0 )
                        {
LABEL_138:
                          if ( v143[0] )
                            v145(v146, v48);
                          if ( v137[0] )
                            v139(v140, v43);
                          v94 = v131[0] == 0;
                          goto LABEL_159;
                        }
                        v136 = 0;
                        v76 = *(struct _D3DDDI_RATIONAL *)(v48 + 7);
                        v136 = v76;
                        if ( ((v48[14] >> 3) & 0x3F) != 0 )
                          v136.Denominator = ((v48[14] >> 3) & 0x3F) * v76.Denominator;
                        if ( !IsUnspecifiedFrequency((const struct _D3DDDI_RATIONAL *)(v48 + 17))
                          && (*v77 != v136.Numerator || v48[18] != v78) )
                        {
                          for ( m = 0;
                                ;
                                m = (struct _D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT *)(unsigned int)((_DWORD)v148 + 1) )
                          {
                            LODWORD(v148) = (_DWORD)m;
                            if ( (unsigned int)m >= 7 )
                              break;
                            v126 = m;
                            if ( !DMMVIDEOSIGNALMODE::IsFreqWithinToleranceRange(
                                    &v136,
                                    (const struct _D3DDDI_RATIONAL *)&byte_1400ED4D0[8 * (_QWORD)m],
                                    0)
                              && (*(int (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(v142 + 88))(
                                   v43,
                                   *v48,
                                   0x140000000LL + 8LL * (_QWORD)v126 + 971984,
                                   (unsigned int)(v80 + 1)) >= 0 )
                            {
                              v81 = (unsigned int)dword_1400ED4D4[2 * (_QWORD)v126];
                              v82 = (unsigned int)*(_QWORD *)(8LL * (_QWORD)v126 + 971984 + 0x140000000LL);
                              v155.RefreshRate = *(D3DDDI_RATIONAL *)(8LL * (_QWORD)v126 + 971984 + 0x140000000LL);
                              v155.IntegerRefreshRate = DivideAndRound(v82, v81);
                              if ( !MODE_UNION_LIST::FindMode((OBTAIN_MODES_ON_SOURCE *)((char *)this + 64), &v155) )
                              {
                                *((_DWORD *)&v155.Flags + 1) |= 0x100u;
                                LODWORD(v126) = OBTAIN_MODES_ON_SOURCE::_AddMode(this, &v155, v83, 0);
                                if ( (int)v126 < 0 )
                                  goto LABEL_138;
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                  v17 = v130;
                  if ( *((_DWORD *)this + 13) > 1u )
                  {
                    v84 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(*((_QWORD *)this + 4) + 88LL))(
                            *((_QWORD *)this + 3),
                            *((unsigned int *)this + 10),
                            v130,
                            0);
                    LODWORD(v126) = v84;
                    if ( v84 < 0 )
                    {
                      v95 = v84;
                      WdLogSingleEntry4(2, v84, *((_QWORD *)this + 3), *((unsigned int *)this + 10), v17);
                      WdLogGlobalForLineNumber = 1194;
                      DxgkLogInternalTriageEvent(
                        0,
                        0x40000,
                        -1,
                        (unsigned int)L"Unable to unpin rotation. (Status = 0x%I64x, m_hVidPnTopology = 0x%I64x, m_VidPnSo"
                                       "urceId = 0x%I64x, PrimVidPnTargetId = 0x%I64x)",
                        v95,
                        *((_QWORD *)this + 3),
                        *((unsigned int *)this + 10),
                        v17,
                        0);
                      goto LABEL_144;
                    }
                  }
                }
                v61 = v129[0];
              }
            }
            WdLogSingleEntry1(2);
            WdLogGlobalForLineNumber = 925;
            DxgkLogInternalTriageEvent(
              0,
              0x40000,
              -1,
              (unsigned int)L"Failed call to DXGDMM_VIDPNTOPOLOGY_INTERFACE::pfnAcquirePathInfo. (Status = 0x%I64x)",
              v20,
              0,
              0,
              0,
              0);
LABEL_52:
            if ( v143[0] )
              v145(v146, v48);
            if ( v137[0] )
              v139(v140, v43);
            v54 = v131[0] == 0;
LABEL_183:
            if ( !v54 )
              v133(v134, v36);
            if ( v29 )
              v128(v127, v29);
            return (unsigned int)v20;
          }
          WdLogSingleEntry2(3, v49);
          WdLogGlobalForLineNumber = 858;
LABEL_118:
          v152 = 0;
          v86 = (*(__int64 (__fastcall **)(__int64, unsigned int *, struct _D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT **))(v142 + 16))(
                  v43,
                  v48,
                  &v152);
          v20 = v86;
          if ( v86 < 0 )
          {
            WdLogSingleEntry1(2);
            WdLogGlobalForLineNumber = 1221;
            DxgkLogInternalTriageEvent(
              0,
              0x40000,
              -1,
              (unsigned int)L"Failed call to DXGDMM_VIDPNSOURCEMODESET_INTERFACE::pfnAcquireNextModeInfo. (Status = 0x%I64x)",
              v20,
              0,
              0,
              0,
              0);
            goto LABEL_52;
          }
        }
        v87 = (*(__int64 (__fastcall **)(__int64, _QWORD))(v142 + 56))(v43, 0);
        v20 = v87;
        if ( v87 < 0 )
        {
          WdLogSingleEntry3(2, v87, v43, 0xFFFFFFFFLL);
          WdLogGlobalForLineNumber = 1238;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Failed call to DXGDMM_VIDPNTARGETMODESET_INTERFACE::pfnUnpinMode. (Status = 0x%I64x, shVidPnTa"
                           "rgetModeSet.GetResource() = 0x%I64x, spVidPnTargetModeInfo.GetResource()->Id = 0x%I64x)",
            v20,
            v43,
            0xFFFFFFFFLL,
            0,
            0);
          goto LABEL_52;
        }
        if ( v143[0] )
          v145(v146, 0);
        if ( v137[0] )
          v139(v140, v43);
      }
      else
      {
        WdLogSingleEntry2(3, v38);
        WdLogGlobalForLineNumber = 799;
      }
    }
    v153 = 0;
    v88 = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64 *))(v149 + 16))(v29, v36, &v153);
    v20 = v88;
    if ( v88 < 0 )
    {
      WdLogSingleEntry1(2);
      v102 = L"Failed call to DXGDMM_VIDPNSOURCEMODESET_INTERFACE::pfnAcquireNextModeInfo. (Status = 0x%I64x)";
      WdLogGlobalForLineNumber = 1252;
LABEL_181:
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v102, v20, 0, 0, 0, 0);
LABEL_182:
      v54 = v131[0] == 0;
      goto LABEL_183;
    }
    DXGDMM::AutoRelease<_D3DKMDT_VIDPN_PRESENT_PATH const *,long (*)(D3DKMDT_HVIDPNTOPOLOGY__ *,_D3DKMDT_VIDPN_PRESENT_PATH const *),D3DKMDT_HVIDPNTOPOLOGY__ *>::Own(
      v131,
      v153,
      *(_QWORD *)(v149 + 32),
      v29);
  }
  v103 = (*(__int64 (__fastcall **)(__int64, _QWORD))(v149 + 48))(v29, 0);
  v20 = v103;
  if ( v103 < 0 )
  {
    WdLogSingleEntry3(2, v103, v29, 0xFFFFFFFFLL);
    WdLogGlobalForLineNumber = 1269;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Failed call to DXGDMM_VIDPNSOURCEMODESET_INTERFACE::pfnUnpinMode. (Status = 0x%I64x, spVidPnSourceMo"
                     "deInfo.GetResource() = 0x%I64x, spVidPnSourceModeInfo.GetResource()->Id = 0x%I64x)",
      v20,
      v29,
      0xFFFFFFFFLL,
      0,
      0);
    goto LABEL_182;
  }
  v104 = ExposedViaHandle<DMMVIDPN,D3DKMDT_HVIDPN__ *>::GetFromHandle(*((_QWORD *)this + 1));
  v105 = v157;
  *(_BYTE *)(v104 + 296) = 0;
  v106 = *v105;
  if ( !*v105 )
  {
    v107 = *((_DWORD *)this + 20);
    if ( v107 )
    {
      v109 = v107;
      v108 = 44LL * v107;
      if ( !is_mul_ok(v109, 0x2Cu) )
        v108 = -1;
      v106 = (struct _D3DKMT_DISPLAYMODE *)operator new[](v108, 1265072196, 256);
      *v105 = v106;
      if ( !v106 )
      {
        WdLogSingleEntry0(6);
        WdLogGlobalForLineNumber = 1283;
        DxgkLogInternalTriageEvent(
          0,
          262145,
          -1,
          (unsigned int)L"Unable to allocate mode list memory.",
          1283,
          0,
          0,
          0,
          0);
        if ( v131[0] )
          v133(v134, 0);
        if ( v29 )
          v128(v127, v29);
        return 3221225495LL;
      }
    }
    else
    {
      v106 = 0;
    }
  }
  UniqueModes = MODE_UNION_LIST::GetUniqueModes(
                  (OBTAIN_MODES_ON_SOURCE *)((char *)this + 64),
                  *((unsigned int *)this + 20),
                  v106,
                  v158);
  if ( UniqueModes < 0 )
  {
    v111 = UniqueModes;
    WdLogSingleEntry1(1);
    WdLogGlobalForLineNumber = 1294;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"GetUniqueModesFromUnionList failed. (Status = 0x%I64x)",
      v111,
      0,
      0,
      0,
      0);
  }
  v112 = v154;
  if ( v154 )
  {
    if ( *v154 )
    {
      DXGQUOTAALLOCATOR<256,1835156294>::operator delete(*v154);
      *v112 = 0;
    }
    v113 = *((unsigned int *)this + 30);
    if ( (_DWORD)v113 )
    {
      v114 = 44 * v113;
      if ( !is_mul_ok(*((unsigned int *)this + 30), 0x2Cu) )
        v114 = -1;
      v115 = (struct _D3DKMT_DISPLAYMODE *)operator new[](v114, 1265072196, 256);
      *v112 = v115;
      if ( v115 )
      {
        v116 = MODE_UNION_LIST::GetUniqueModes(
                 (OBTAIN_MODES_ON_SOURCE *)((char *)this + 104),
                 *((unsigned int *)this + 30),
                 v115,
                 v159);
        if ( v116 < 0 )
        {
          v117 = v116;
          WdLogSingleEntry1(1);
          WdLogGlobalForLineNumber = 1321;
          DxgkLogInternalTriageEvent(
            0,
            262146,
            -1,
            (unsigned int)L"GetUniqueModesFromInvalidModesUnionList failed. (Status = 0x%I64x)",
            v117,
            0,
            0,
            0,
            0);
        }
      }
      else
      {
        WdLogSingleEntry0(6);
        WdLogGlobalForLineNumber = 1311;
        DxgkLogInternalTriageEvent(
          0,
          262145,
          -1,
          (unsigned int)L"Unable to allocate mode list memory for invalid modes.",
          1311,
          0,
          0,
          0,
          0);
      }
    }
  }
  if ( v131[0] )
    v133(v134, 0);
  if ( v29 )
    v128(v127, v29);
  return 0;
}

```

## disassembly

```asm
0x140330bdc  push    rbp
0x140330bde  push    rbx
0x140330bdf  push    rsi
0x140330be0  push    rdi
0x140330be1  push    r12
0x140330be3  push    r13
0x140330be5  push    r14
0x140330be7  push    r15
0x140330be9  lea     rbp, [rsp-108h]
0x140330bf1  sub     rsp, 208h
0x140330bf8  mov     rax, cs:__security_cookie
0x140330bff  xor     rax, rsp
0x140330c02  mov     [rbp+140h+var_50], rax
0x140330c09  mov     rax, [rbp+140h+arg_20]
0x140330c10  mov     edi, 0FFFFFFFFh
0x140330c15  xor     r13d, r13d
0x140330c18  mov     [rbp+140h+var_C0], rax
0x140330c1f  mov     r12d, edi
0x140330c22  mov     [rsp+240h+var_1C4], edi
0x140330c26  mov     ebx, r13d
0x140330c29  mov     [rbp+140h+var_110], r9
0x140330c2d  mov     [rbp+140h+var_C8], r8
0x140330c31  mov     r15, rcx
0x140330c34  mov     [rbp+140h+var_D0], rdx
0x140330c38  mov     r14d, 0FFh
0x140330c3e  mov     rax, [r15+20h]
0x140330c42  lea     r9, [rsp+240h+var_1E8]
0x140330c47  mov     edx, [r15+28h]
0x140330c4b  mov     rcx, [r15+18h]
0x140330c4f  mov     [rsp+240h+var_1E8], edi
0x140330c53  mov     rax, [rax+8]
0x140330c57  mov     r8d, ebx
0x140330c5a  mov     edi, ebx
0x140330c5c  call    _guard_dispatch_icall
0x140330c61  movsxd  rsi, eax
0x140330c64  test    eax, eax
0x140330c66  js      loc_140332100
0x140330c6c  mov     r8d, [rsp+240h+var_1E8]
0x140330c71  mov     edi, 0FFFFFFFFh
0x140330c76  cmp     r8d, edi
0x140330c79  jz      loc_140330D37
0x140330c7f  inc     dword ptr [r15+34h]
0x140330c83  lea     rcx, [rsp+240h+var_1C8]
0x140330c88  mov     edx, [r15+28h]
0x140330c8c  lea     r9, [rsp+240h+var_1EC]
0x140330c91  mov     eax, 0FFFFh
0x140330c96  mov     [rsp+240h+var_1EC], r13d
0x140330c9b  mov     [rsp+240h+var_1C8], ax
0x140330ca0  mov     rax, [r15+20h]
0x140330ca4  mov     [rsp+240h+var_220], rcx
0x140330ca9  mov     rcx, [r15+18h]
0x140330cad  mov     rax, [rax+70h]
0x140330cb1  call    _guard_dispatch_icall
0x140330cb6  movsxd  rsi, eax
0x140330cb9  test    eax, eax
0x140330cbb  js      short loc_140330CE3
0x140330cbd  cmp     r12d, edi
0x140330cc0  jz      short loc_140330CC9
0x140330cc2  cmp     [rsp+240h+var_1EC], r14d
0x140330cc7  jge     short loc_140330CDC
0x140330cc9  mov     r12d, [rsp+240h+var_1E8]
0x140330cce  mov     r14d, [rsp+240h+var_1EC]
0x140330cd3  mov     [rsp+240h+var_1C4], r12d
0x140330cd8  mov     [r15+30h], ebx
0x140330cdc  inc     ebx
0x140330cde  jmp     loc_140330C3E
0x140330ce3  mov     r9d, [r15+28h]
0x140330ce7  mov     rdx, rsi
0x140330cea  mov     r8d, r12d
0x140330ced  mov     ecx, 2
0x140330cf2  mov     ebx, r12d
0x140330cf5  call    cs:__imp_WdLogSingleEntry3
0x140330cfc  nop     dword ptr [rax+rax+00h]
0x140330d01  mov     [rsp+240h+var_200], r13
0x140330d06  lea     r9, aFailedCallToDx_2; "Failed call to DXGDMM_VIDPNTOPOLOGY_INT"...
0x140330d0d  mov     [rsp+240h+var_208], r13
0x140330d12  mov     edx, 40000h
0x140330d17  mov     cs:WdLogGlobalForLineNumber, 2A3h
0x140330d21  mov     r8, rdi
0x140330d24  mov     eax, [r15+28h]
0x140330d28  mov     [rsp+240h+var_210], rax
0x140330d2d  mov     [rsp+240h+var_218], rbx
0x140330d32  jmp     loc_14033214F
0x140330d37  mov     ebx, [rsp+240h+var_1C4]
0x140330d3b  cmp     ebx, edi
0x140330d3d  jnz     short loc_140330D90
0x140330d3f  cmp     [r15+34h], r13d
0x140330d43  jz      short loc_140330D90
0x140330d45  mov     ecx, 1
0x140330d4a  call    cs:__imp_WdLogSingleEntry0
0x140330d51  nop     dword ptr [rax+rax+00h]
0x140330d56  mov     [rsp+240h+var_200], r13
0x140330d5b  lea     r9, aPrimvidpntarge; "(PrimVidPnTargetId != D3DDDI_ID_UNINITI"...
0x140330d62  mov     [rsp+240h+var_208], r13
0x140330d67  mov     eax, 2B3h
0x140330d6c  mov     [rsp+240h+var_210], r13
0x140330d71  mov     r8d, edi
0x140330d74  mov     [rsp+240h+var_218], r13
0x140330d79  mov     edx, 40002h
0x140330d7e  xor     ecx, ecx
0x140330d80  mov     [rsp+240h+var_220], rax
0x140330d85  mov     cs:WdLogGlobalForLineNumber, eax
0x140330d8b  call    DxgkLogInternalTriageEvent
0x140330d90  mov     rsi, [r15]
0x140330d93  lea     r9, [rsp+240h+var_1E8]; enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *
0x140330d98  mov     rcx, rsi; void *
0x140330d9b  mov     [rbp+140h+var_D8], rsi
0x140330d9f  xor     r8d, r8d; enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *
0x140330da2  mov     [rsp+240h+var_1E8], r13d
0x140330da7  mov     edx, ebx; unsigned int
0x140330da9  call    ?DmmGetVideoOutputTechnology@@YAJQEAXIPEAW4_D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY@@1@Z; DmmGetVideoOutputTechnology(void * const,uint,_D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *,_D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *)
0x140330dae  movsxd  rdi, eax
0x140330db1  test    eax, eax
0x140330db3  jns     short loc_140330E0C
0x140330db5  mov     rdx, rdi
0x140330db8  mov     ecx, 2
0x140330dbd  call    cs:__imp_WdLogSingleEntry1
0x140330dc4  nop     dword ptr [rax+rax+00h]
0x140330dc9  lea     r9, aFailedCallToDm_0; "Failed call to DmmGetVideoOutputTechnol"...
0x140330dd0  mov     cs:WdLogGlobalForLineNumber, 2BFh
0x140330dda  mov     [rsp+240h+var_200], r13
0x140330ddf  mov     edx, 40000h
0x140330de4  mov     [rsp+240h+var_208], r13
0x140330de9  xor     ecx, ecx
0x140330deb  mov     [rsp+240h+var_210], r13
0x140330df0  mov     r8d, 0FFFFFFFFh
0x140330df6  mov     [rsp+240h+var_218], r13
0x140330dfb  mov     [rsp+240h+var_220], rdi
0x140330e00  call    DxgkLogInternalTriageEvent
0x140330e05  mov     eax, edi
0x140330e07  jmp     loc_14033215D
0x140330e0c  mov     eax, [rsp+240h+var_1E8]
0x140330e10  sub     eax, 0Fh
0x140330e13  jz      short loc_140330E24
0x140330e15  sub     eax, 1
0x140330e18  jz      short loc_140330E24
0x140330e1a  mov     [rsp+240h+var_1E3], r13b
0x140330e1f  cmp     eax, 1
0x140330e22  jnz     short loc_140330E29
0x140330e24  mov     [rsp+240h+var_1E3], 1
0x140330e29  cmp     [rsi+0CA8h], r13
0x140330e30  jnz     short loc_140330E47
0x140330e32  mov     rcx, [rsi+0CA0h]; this
0x140330e39  call    ?GetDisplayOnlyDriverUseRawModes@ADAPTER_DISPLAY@@QEBAHXZ; ADAPTER_DISPLAY::GetDisplayOnlyDriverUseRawModes(void)
0x140330e3e  mov     [rsp+240h+var_1E4], 1
0x140330e43  test    eax, eax
0x140330e45  jnz     short loc_140330E4C
0x140330e47  mov     [rsp+240h+var_1E4], r13b
0x140330e4c  mov     edi, 60h ; '`'
0x140330e51  lea     rcx, [rbp+140h+var_B0]; void *
0x140330e58  mov     r8d, edi; Size
0x140330e5b  xor     edx, edx; Val
0x140330e5d  call    memset
0x140330e62  mov     rcx, [r15]; void *
0x140330e65  lea     r8, [rbp+140h+var_B0]; struct _D3DKMDT_MONITOR_SOURCE_MODE *
0x140330e6c  mov     edx, ebx; unsigned int
0x140330e6e  call    ?DmmGetPreferredMonitorSourceModeOnTarget@@YAJPEAXIPEAU_D3DKMDT_MONITOR_SOURCE_MODE@@@Z; DmmGetPreferredMonitorSourceModeOnTarget(void *,uint,_D3DKMDT_MONITOR_SOURCE_MODE *)
0x140330e73  test    eax, eax
0x140330e75  jns     short loc_140330E88
0x140330e77  mov     r8d, edi; Size
0x140330e7a  lea     rcx, [rbp+140h+var_B0]; void *
0x140330e81  xor     edx, edx; Val
0x140330e83  call    memset
0x140330e88  mov     rax, [r15+10h]
0x140330e8c  lea     r9, [rbp+140h+var_130]
0x140330e90  mov     edx, [r15+28h]
0x140330e94  lea     r8, [rbp+140h+var_198]
0x140330e98  mov     rcx, [r15+8]
0x140330e9c  mov     [rbp+140h+var_130], r13
0x140330ea0  mov     qword ptr [rbp+140h+var_198.Numerator], r13
0x140330ea4  mov     rax, [rax+8]
0x140330ea8  call    _guard_dispatch_icall
0x140330ead  movsxd  rdi, eax
0x140330eb0  test    eax, eax
0x140330eb2  jns     short loc_140330EDE
0x140330eb4  mov     rdx, rdi
0x140330eb7  mov     ecx, 2
0x140330ebc  call    cs:__imp_WdLogSingleEntry1
0x140330ec3  nop     dword ptr [rax+rax+00h]
0x140330ec8  lea     r9, aFailedCallToDx_3; "Failed call to DXGDMM_VIDPN_INTERFACE::"...
0x140330ecf  mov     cs:WdLogGlobalForLineNumber, 2DDh
0x140330ed9  jmp     loc_140330DDA
0x140330ede  mov     rax, [r15+10h]
0x140330ee2  lea     rdx, [rbp+140h+var_198]
0x140330ee6  mov     r14, qword ptr [rbp+140h+var_198.Numerator]
0x140330eea  mov     rdi, [r15+8]
0x140330eee  mov     rcx, r14
0x140330ef1  mov     [rsp+240h+var_1D8], rdi
0x140330ef6  mov     r12, [rax+10h]
0x140330efa  mov     rax, [rbp+140h+var_130]
0x140330efe  mov     qword ptr [rbp+140h+var_198.Numerator], r13
0x140330f02  mov     [rsp+240h+var_1D0], r12
0x140330f07  mov     [rbp+140h+var_1B8], r13
0x140330f0b  mov     rax, [rax+8]
0x140330f0f  mov     [rbp+140h+var_1B0], r13
0x140330f13  mov     [rbp+140h+var_1A8], r13
0x140330f17  mov     [rbp+140h+var_1A0], r13d
0x140330f1b  mov     [rbp+140h+var_1C0], r13b
0x140330f1f  call    _guard_dispatch_icall
0x140330f24  movsxd  rsi, eax
0x140330f27  test    eax, eax
0x140330f29  jns     short loc_140330F97
0x140330f2b  mov     rdx, rsi
0x140330f2e  mov     ecx, 2
0x140330f33  call    cs:__imp_WdLogSingleEntry1
0x140330f3a  nop     dword ptr [rax+rax+00h]
0x140330f3f  mov     [rsp+240h+var_200], r13
0x140330f44  lea     r9, aFailedCallToDx_4; "Failed call to DXGDMM_VIDPNSOURCEMODESE"...
0x140330f4b  mov     [rsp+240h+var_208], r13
0x140330f50  mov     edx, 40000h
0x140330f55  mov     [rsp+240h+var_210], r13
0x140330f5a  xor     ecx, ecx
0x140330f5c  mov     [rsp+240h+var_218], r13
0x140330f61  mov     r8d, 0FFFFFFFFh
0x140330f67  mov     [rsp+240h+var_220], rsi
0x140330f6c  mov     cs:WdLogGlobalForLineNumber, 2F1h
0x140330f76  call    DxgkLogInternalTriageEvent
0x140330f7b  test    r14, r14
0x140330f7e  jz      loc_14033215B
0x140330f84  mov     rdx, r14
0x140330f87  mov     rcx, rdi
0x140330f8a  mov     rax, r12
0x140330f8d  call    _guard_dispatch_icall
0x140330f92  jmp     loc_14033215B
0x140330f97  mov     r8, [rbp+140h+var_130]
0x140330f9b  lea     rcx, [rbp+140h+var_1C0]
0x140330f9f  mov     rdx, qword ptr [rbp+140h+var_198.Numerator]
0x140330fa3  mov     r9, r14
0x140330fa6  mov     r8, [r8+20h]
0x140330faa  call    ?Own@?$AutoRelease@PEBU_D3DKMDT_VIDPN_PRESENT_PATH@@P6AJPEAUD3DKMDT_HVIDPNTOPOLOGY__@@PEBU1@@ZPEAU2@@DXGDMM@@QEAAXPEBU_D3DKMDT_VIDPN_PRESENT_PATH@@Q6AJPEAUD3DKMDT_HVIDPNTOPOLOGY__@@0@Z1@Z; DXGDMM::AutoRelease<_D3DKMDT_VIDPN_PRESENT_PATH const *,long (*)(D3DKMDT_HVIDPNTOPOLOGY__ *,_D3DKMDT_VIDPN_PRESENT_PATH const *),D3DKMDT_HVIDPNTOPOLOGY__ *>::Own(_D3DKMDT_VIDPN_PRESENT_PATH const *,long (*const)(D3DKMDT_HVIDPNTOPOLOGY__ *,_D3DKMDT_VIDPN_PRESENT_PATH const *),D3DKMDT_HVIDPNTOPOLOGY__ *)
0x140330faf  mov     rcx, [r15+8]
0x140330fb3  call    ?GetFromHandle@?$ExposedViaHandle@VDMMVIDPN@@PEAUD3DKMDT_HVIDPN__@@@@SAPEAVDMMVIDPN@@PEAUD3DKMDT_HVIDPN__@@@Z; ExposedViaHandle<DMMVIDPN,D3DKMDT_HVIDPN__ *>::GetFromHandle(D3DKMDT_HVIDPN__ *)
0x140330fb8  xor     r12d, r12d
0x140330fbb  mov     byte ptr [rax+128h], 1
0x140330fc2  mov     r13, [rbp+140h+var_1B8]
0x140330fc6  test    r13, r13
0x140330fc9  jz      loc_140331E12
0x140330fcf  mov     eax, [r13+4]
0x140330fd3  mov     rdi, r13
0x140330fd6  cmp     eax, 3
0x140330fd9  jz      short loc_140330FE9
0x140330fdb  cmp     eax, 4
0x140330fde  jz      short loc_140330FE9
0x140330fe0  cmp     eax, 1
0x140330fe3  jnz     loc_140331773
0x140330fe9  mov     eax, [rdi+10h]
0x140330fec  cmp     [rdi+8], eax
0x140330fef  jnz     loc_140331773
0x140330ff5  mov     eax, [rdi+14h]
0x140330ff8  cmp     [rdi+0Ch], eax
0x140330ffb  jnz     loc_140331773
0x140331001  mov     rax, [rbp+140h+var_130]
0x140331005  mov     r8b, 1
0x140331008  mov     edx, [rdi]
0x14033100a  mov     rcx, r14
0x14033100d  mov     rax, [rax+28h]
0x140331011  call    _guard_dispatch_icall
0x140331016  test    eax, eax
0x140331018  jns     short loc_140331040
0x14033101a  mov     r8d, [rdi]
0x14033101d  mov     ecx, 3
0x140331022  movsxd  rdx, eax
0x140331025  call    cs:__imp_WdLogSingleEntry2
0x14033102c  nop     dword ptr [rax+rax+00h]
0x140331031  mov     cs:WdLogGlobalForLineNumber, 31Fh
0x14033103b  jmp     loc_140331773
0x140331040  mov     rax, [r15+10h]
0x140331044  lea     r9, [rbp+140h+var_168]
0x140331048  mov     rcx, [r15+8]
0x14033104c  lea     r8, [rsp+240h+var_1E0]
0x140331051  mov     [rbp+140h+var_168], r12
0x140331055  mov     edx, ebx
0x140331057  mov     [rsp+240h+var_1E0], r12
0x14033105c  mov     rax, [rax+18h]
0x140331060  mov     [rbp+140h+var_188], r12
0x140331064  mov     [rbp+140h+var_180], r12
0x140331068  mov     [rbp+140h+var_178], r12
0x14033106c  mov     [rbp+140h+var_170], r12d
0x140331070  mov     [rbp+140h+var_190], r12b
0x140331074  call    _guard_dispatch_icall
0x140331079  movsxd  rdi, eax
0x14033107c  test    eax, eax
0x14033107e  js      loc_140331D62
0x140331084  mov     r8, [r15+10h]
0x140331088  lea     rcx, [rbp+140h+var_190]
0x14033108c  mov     r9, [r15+8]
0x140331090  mov     rdx, [rsp+240h+var_1E0]
0x140331095  mov     r8, [r8+20h]
0x140331099  call    ?Own@?$AutoRelease@PEAUD3DKMDT_HVIDPNTARGETMODESET__@@P6AJPEAUD3DKMDT_HVIDPN__@@PEAU1@@ZPEAU2@@DXGDMM@@QEAAXPEAUD3DKMDT_HVIDPNTARGETMODESET__@@Q6AJPEAUD3DKMDT_HVIDPN__@@0@Z1@Z; DXGDMM::AutoRelease<D3DKMDT_HVIDPNTARGETMODESET__ *,long (*)(D3DKMDT_HVIDPN__ *,D3DKMDT_HVIDPNTARGETMODESET__ *),D3DKMDT_HVIDPN__ *>::Own(D3DKMDT_HVIDPNTARGETMODESET__ *,long (*const)(D3DKMDT_HVIDPN__ *,D3DKMDT_HVIDPNTARGETMODESET__ *),D3DKMDT_HVIDPN__ *)
0x14033109e  mov     rax, [rbp+140h+var_168]
0x1403310a2  lea     rdx, [rsp+240h+var_1E0]
0x1403310a7  mov     rsi, [rbp+140h+var_188]
0x1403310ab  mov     [rsp+240h+var_1E0], r12
0x1403310b0  mov     rcx, rsi
0x1403310b3  mov     [rbp+140h+var_158], r12
0x1403310b7  mov     rax, [rax+8]
0x1403310bb  mov     [rbp+140h+var_150], r12
0x1403310bf  mov     [rbp+140h+var_148], r12
0x1403310c3  mov     [rbp+140h+var_140], r12d
0x1403310c7  mov     [rbp+140h+var_160], r12b
  ... truncated ...
```
