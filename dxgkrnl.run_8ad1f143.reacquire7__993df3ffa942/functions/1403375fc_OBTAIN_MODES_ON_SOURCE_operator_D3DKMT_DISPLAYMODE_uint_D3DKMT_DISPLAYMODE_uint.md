# OBTAIN_MODES_ON_SOURCE::operator()(_D3DKMT_DISPLAYMODE * *,uint *,_D3DKMT_DISPLAYMODE * *,uint *)

- ea: `0x1403375fc`
- end: `0x140338ba1`
- name: `??ROBTAIN_MODES_ON_SOURCE@@QEBAJPEAPEAU_D3DKMT_DISPLAYMODE@@PEAI01@Z`
- size: `5541`
- prototype: `__int64 __usercall@<rax>(OBTAIN_MODES_ON_SOURCE *this@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, reparse_path`

## callers

- `0x1401dd4a4`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x14001b9c0`
- `0x14003d198`
- `0x1400423f8`
- `0x1400452cc`
- `0x140046780`
- `0x140047b60`
- `0x140053634`
- `0x140071558`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a1000`
- `0x14022c3d0`
- `0x1403374e0`
- `0x1403375fc`
- `0x140338ba8`
- `0x140338c20`
- `0x140338d34`
- `0x140339978`
- `0x140339ca8`
- `0x140339ea0`
- `0x140368554`

## import_xrefs

- `watchdog!WdLogSingleEntry4` at `0x1403382cd`
- `watchdog!WdLogSingleEntry4` at `0x14033833c`
- `watchdog!WdLogSingleEntry4` at `0x140338536`
- `watchdog!WdLogSingleEntry4` at `0x140338645`
- `watchdog!WdLogSingleEntry4` at `0x1403382cd`
- `watchdog!WdLogSingleEntry4` at `0x14033833c`
- `watchdog!WdLogSingleEntry4` at `0x140338536`
- `watchdog!WdLogSingleEntry4` at `0x140338645`
- `watchdog!WdLogSingleEntry2` at `0x140337a45`
- `watchdog!WdLogSingleEntry2` at `0x140337b48`
- `watchdog!WdLogSingleEntry2` at `0x140337bee`
- `watchdog!WdLogSingleEntry2` at `0x140337a45`
- `watchdog!WdLogSingleEntry2` at `0x140337b48`
- `watchdog!WdLogSingleEntry2` at `0x140337bee`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140337bb2`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140337bb2`
- `watchdog!WdLogSingleEntry3` at `0x140337715`
- `watchdog!WdLogSingleEntry3` at `0x1403386d9`
- `watchdog!WdLogSingleEntry3` at `0x14033885e`
- `watchdog!WdLogSingleEntry3` at `0x140338b2f`
- `watchdog!WdLogSingleEntry3` at `0x140337715`
- `watchdog!WdLogSingleEntry3` at `0x1403386d9`
- `watchdog!WdLogSingleEntry3` at `0x14033885e`
- `watchdog!WdLogSingleEntry3` at `0x140338b2f`
- `watchdog!WdLogSingleEntry0` at `0x14033776a`
- `watchdog!WdLogSingleEntry0` at `0x1403388f6`
- `watchdog!WdLogSingleEntry0` at `0x140338a46`
- `watchdog!WdLogSingleEntry0` at `0x14033776a`
- `watchdog!WdLogSingleEntry0` at `0x1403388f6`
- `watchdog!WdLogSingleEntry0` at `0x140338a46`
- `watchdog!WdLogSingleEntry5` at `0x1403381ff`
- `watchdog!WdLogSingleEntry5` at `0x14033846b`
- `watchdog!WdLogSingleEntry5` at `0x1403381ff`
- `watchdog!WdLogSingleEntry5` at `0x14033846b`
- `watchdog!WdLogSingleEntry1` at `0x1403377dd`
- `watchdog!WdLogSingleEntry1` at `0x1403378dc`
- `watchdog!WdLogSingleEntry1` at `0x140337953`
- `watchdog!WdLogSingleEntry1` at `0x1403383c3`
- `watchdog!WdLogSingleEntry1` at `0x1403385f4`
- `watchdog!WdLogSingleEntry1` at `0x14033868f`
- `watchdog!WdLogSingleEntry1` at `0x140338722`
- `watchdog!WdLogSingleEntry1` at `0x14033878a`
- `watchdog!WdLogSingleEntry1` at `0x140338810`
- `watchdog!WdLogSingleEntry1` at `0x14033899b`
- `watchdog!WdLogSingleEntry1` at `0x140338aaa`
- `watchdog!WdLogSingleEntry1` at `0x1403377dd`
- `watchdog!WdLogSingleEntry1` at `0x1403378dc`
- `watchdog!WdLogSingleEntry1` at `0x140337953`
- `watchdog!WdLogSingleEntry1` at `0x1403383c3`
- `watchdog!WdLogSingleEntry1` at `0x1403385f4`
- `watchdog!WdLogSingleEntry1` at `0x14033868f`
- `watchdog!WdLogSingleEntry1` at `0x140338722`
- `watchdog!WdLogSingleEntry1` at `0x14033878a`
- `watchdog!WdLogSingleEntry1` at `0x140338810`
- `watchdog!WdLogSingleEntry1` at `0x14033899b`
- `watchdog!WdLogSingleEntry1` at `0x140338aaa`

## string_xrefs

- `0x1403383e0`: `Failed call to DXGDMM_VIDPNTOPOLOGY_INTERFACE::pfnAcquirePathInfo. (Status = 0x%I64x)`
- `0x1403386ad`: `Failed call to DXGDMM_VIDPNTOPOLOGY_INTERFACE::pfnAcquirePathInfo. (Status = 0x%I64x)`
- `0x1403382d9`: `Failed to pin the reported-as-supported rotation mode 0x%I64x on the path (0x%I64x, 0x%I64x) because of not supported by driver, returning 0x%I64x.`
- `0x140338210`: `Unable to set rotation on the path. (Status = 0x%I64x, m_VidPnSourceId = 0x%I64x, PrimVidPnTargetId = 0x%I64x, m_hVidPnTopology = 0x%I64x, PathRotation = 0x%I64x)`
- `0x14033847c`: `Unable to set scaling on the path. ( Status = 0x%I64x, m_VidPnSourceId = 0x%I64x, PrimVidPnTargetId = 0x%I64x, m_hVidPnTopology = 0x%I64x, PathScaling = 0x%I64x)`
- `0x140338542`: `Failed to pin the reported-as-supported scaling mode 0x%I64x on the path (0x%I64x, 0x%I64x) because of not supported by driver, returning 0x%I64x.`
- `0x140338b40`: `Failed call to DXGDMM_VIDPNTOPOLOGY_INTERFACE::pfnEnumPathTargetsFromSource. (Status = 0x%I64x, m_VidPnSourceId = 0x%I64x, PathIndex = 0x%I64x)`
- `0x140337726`: `Failed call to DXGDMM_VIDPNTOPOLOGY_INTERFACE::pfnGetPathImportance. (Status = 0x%I64x, PrimVidPnTargetId = 0x%I64x, m_VidPnSourceId = 0x%I64x)`

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
  unsigned int *v36; // r13
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
  __int64 v52; // rax
  bool v53; // zf
  __int64 v54; // rax
  __int64 v55; // rdx
  __int64 v56; // rcx
  int v57; // eax
  struct _D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT v58; // edi
  char v59; // al
  char v60; // al
  unsigned int j; // ecx
  int v62; // eax
  __int64 v63; // rax
  __int64 v64; // rdx
  __int64 v65; // rcx
  int v66; // eax
  struct _D3DKMDT_VIDPN_PRESENT_PATH_ROTATION_SUPPORT v67; // ebx
  enum _D3DKMDT_VIDPN_PRESENT_PATH_ROTATION k; // eax
  char v69; // cl
  char v70; // al
  __int64 v71; // r8
  int v72; // eax
  __int64 v73; // rcx
  bool v74; // zf
  struct _D3DDDI_RATIONAL v75; // r8
  _DWORD *v76; // rcx
  int v77; // r8d
  struct _D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT *m; // rax
  int v79; // r8d
  unsigned __int64 v80; // rdx
  unsigned __int64 v81; // rcx
  __int64 v82; // r8
  int v83; // eax
  int v84; // eax
  int v85; // eax
  int v86; // eax
  int v87; // eax
  __int64 v88; // rbx
  __int64 v89; // rdi
  __int64 v90; // rsi
  __int64 v91; // rdi
  const wchar_t *v92; // r9
  bool v93; // zf
  __int64 v94; // rdi
  __int64 v95; // rdx
  __int64 v96; // rbx
  __int64 v97; // rbx
  __int64 v98; // rdi
  __int64 v99; // rsi
  __int64 v100; // rdi
  const wchar_t *v101; // r9
  int v102; // eax
  __int64 v103; // rax
  struct _D3DKMT_DISPLAYMODE **v104; // rbx
  struct _D3DKMT_DISPLAYMODE *v105; // rax
  unsigned int v106; // eax
  __int64 v107; // rax
  unsigned __int64 v108; // kr00_8
  int UniqueModes; // eax
  __int64 v110; // rbx
  _QWORD *v111; // rdi
  __int64 v112; // rcx
  __int64 v113; // rax
  struct _D3DKMT_DISPLAYMODE *v114; // rax
  int v115; // eax
  __int64 v116; // rbx
  __int64 v117; // [rsp+20h] [rbp-E0h]
  char v118; // [rsp+50h] [rbp-B0h] BYREF
  char v119[3]; // [rsp+51h] [rbp-AFh] BYREF
  enum _D3DKMDT_VIDPN_PRESENT_PATH_ROTATION v120; // [rsp+54h] [rbp-ACh] BYREF
  enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY v121; // [rsp+58h] [rbp-A8h] BYREF
  char v122; // [rsp+5Ch] [rbp-A4h]
  char v123; // [rsp+5Dh] [rbp-A3h]
  char v124[2]; // [rsp+5Eh] [rbp-A2h] BYREF
  struct _D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT *v125; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v126; // [rsp+68h] [rbp-98h]
  void (__fastcall *v127)(__int64, __int64); // [rsp+70h] [rbp-90h]
  __int16 v128[2]; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v129; // [rsp+7Ch] [rbp-84h]
  char v130[8]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int *v131; // [rsp+88h] [rbp-78h]
  void (__fastcall *v132)(__int64, unsigned int *); // [rsp+90h] [rbp-70h]
  __int64 v133; // [rsp+98h] [rbp-68h]
  int v134; // [rsp+A0h] [rbp-60h]
  struct _D3DDDI_RATIONAL v135; // [rsp+A8h] [rbp-58h] BYREF
  char v136[8]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v137; // [rsp+B8h] [rbp-48h]
  void (__fastcall *v138)(__int64, __int64); // [rsp+C0h] [rbp-40h]
  __int64 v139; // [rsp+C8h] [rbp-38h]
  int v140; // [rsp+D0h] [rbp-30h]
  __int64 v141; // [rsp+D8h] [rbp-28h] BYREF
  char v142[8]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int *v143; // [rsp+E8h] [rbp-18h]
  void (__fastcall *v144)(__int64, unsigned int *); // [rsp+F0h] [rbp-10h]
  __int64 v145; // [rsp+F8h] [rbp-8h]
  int v146; // [rsp+100h] [rbp+0h]
  struct _D3DKMDT_VIDPN_PRESENT_PATH_ROTATION_SUPPORT *v147; // [rsp+108h] [rbp+8h] BYREF
  __int64 v148; // [rsp+110h] [rbp+10h] BYREF
  int v149; // [rsp+118h] [rbp+18h] BYREF
  unsigned int v150; // [rsp+11Ch] [rbp+1Ch]
  struct _D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT *v151; // [rsp+120h] [rbp+20h] BYREF
  __int64 v152; // [rsp+128h] [rbp+28h] BYREF
  void **v153; // [rsp+130h] [rbp+30h]
  struct _D3DKMT_DISPLAYMODE v154; // [rsp+138h] [rbp+38h] BYREF
  void *v155; // [rsp+168h] [rbp+68h]
  struct _D3DKMT_DISPLAYMODE **v156; // [rsp+170h] [rbp+70h]
  unsigned int *v157; // [rsp+178h] [rbp+78h]
  unsigned int *v158; // [rsp+180h] [rbp+80h]
  struct _D3DKMDT_MONITOR_SOURCE_MODE v159; // [rsp+190h] [rbp+90h] BYREF

  v158 = a5;
  v5 = D3DKMDT_VOT_OTHER;
  v129 = -1;
  v6 = 0;
  v153 = a4;
  v157 = a3;
  v156 = a2;
  v8 = 255;
  while ( 1 )
  {
    v9 = *((_QWORD *)this + 4);
    v10 = *((unsigned int *)this + 10);
    v11 = *((_QWORD *)this + 3);
    v121 = D3DKMDT_VOT_OTHER;
    v12 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *))(v9 + 8))(
            v11,
            v10,
            v6,
            &v121);
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
    v14 = (unsigned int)v121;
    if ( v121 == D3DKMDT_VOT_OTHER )
      break;
    ++*((_DWORD *)this + 13);
    v15 = *((unsigned int *)this + 10);
    v120 = D3DKMDT_VPPR_UNINITIALIZED;
    v128[0] = -1;
    v16 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, enum _D3DKMDT_VIDPN_PRESENT_PATH_ROTATION *, __int16 *))(*((_QWORD *)this + 4) + 112LL))(
            *((_QWORD *)this + 3),
            v15,
            v14,
            &v120,
            v128);
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
    if ( v5 == D3DKMDT_VOT_OTHER || v120 < v8 )
    {
      v5 = v121;
      v8 = v120;
      v129 = v121;
      *((_DWORD *)this + 12) = v6;
    }
    ++v6;
  }
  v17 = v129;
  if ( v129 == -1 && *((_DWORD *)this + 13) )
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
  v155 = *(void **)this;
  v121 = D3DKMDT_VOT_HD15;
  VideoOutputTechnology = DmmGetVideoOutputTechnology(v155, v17, 0, &v121);
  v20 = VideoOutputTechnology;
  if ( VideoOutputTechnology < 0 )
  {
    WdLogSingleEntry1(2, VideoOutputTechnology);
    v21 = L"Failed call to DmmGetVideoOutputTechnology(Status = 0x%I64x)";
    WdLogGlobalForLineNumber = 703;
LABEL_15:
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v21, v20, 0, 0, 0, 0);
    return (unsigned int)v20;
  }
  if ( v121 == D3DKMDT_VOT_MIRACAST
    || v121 == D3DKMDT_VOT_INDIRECT_WIRED
    || (v123 = 0, v121 == (D3DKMDT_VOT_SVIDEO_7PIN|D3DKMDT_VOT_INDIRECT_WIRED)) )
  {
    v123 = 1;
  }
  if ( *(_QWORD *)(v18 + 3256)
    || (DisplayOnlyDriverUseRawModes = ADAPTER_DISPLAY::GetDisplayOnlyDriverUseRawModes(*(ADAPTER_DISPLAY **)(v18 + 3248)),
        v122 = 1,
        !DisplayOnlyDriverUseRawModes) )
  {
    v122 = 0;
  }
  memset(&v159, 0, sizeof(v159));
  if ( DmmGetPreferredMonitorSourceModeOnTarget(*(void **)this, v17, &v159) < 0 )
    memset(&v159, 0, sizeof(v159));
  v24 = *((_QWORD *)this + 2);
  v25 = *((unsigned int *)this + 10);
  v26 = *((_QWORD *)this + 1);
  v148 = 0;
  v135 = 0;
  v27 = (*(__int64 (__fastcall **)(__int64, __int64, struct _D3DDDI_RATIONAL *, __int64 *))(v24 + 8))(
          v26,
          v25,
          &v135,
          &v148);
  v20 = v27;
  if ( v27 < 0 )
  {
    WdLogSingleEntry1(2, v27);
    v21 = L"Failed call to DXGDMM_VIDPN_INTERFACE::pfnAcquireSourceModeSet. (Status = 0x%I64x)";
    WdLogGlobalForLineNumber = 733;
    goto LABEL_15;
  }
  v28 = *((_QWORD *)this + 2);
  v29 = (__int64)v135;
  v30 = *((_QWORD *)this + 1);
  v31 = v135;
  v126 = v30;
  v32 = *(void (__fastcall **)(__int64, __int64))(v28 + 16);
  v135 = 0;
  v127 = v32;
  v131 = 0;
  v33 = *(__int64 (__fastcall **)(struct _D3DDDI_RATIONAL, struct _D3DDDI_RATIONAL *))(v148 + 8);
  v132 = 0;
  v133 = 0;
  v134 = 0;
  v130[0] = 0;
  v34 = ((__int64 (__fastcall *)(_QWORD, _QWORD))v33)(v31, &v135);
  v13 = v34;
  if ( v34 < 0 )
  {
    WdLogSingleEntry1(2, v34);
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
    v130,
    v135,
    *(_QWORD *)(v148 + 32),
    v29);
  *(_BYTE *)(ExposedViaHandle<DMMVIDPN,D3DKMDT_HVIDPN__ *>::GetFromHandle(*((_QWORD *)this + 1)) + 296) = 1;
  while ( 1 )
  {
    v36 = v131;
    if ( !v131 )
      break;
    v37 = v131[1];
    if ( (v37 == 3 || v37 == 4 || v37 == 1) && v131[2] == v131[4] && v131[3] == v131[5] )
    {
      LOBYTE(v35) = 1;
      v38 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(v148 + 40))(v29, *v131, v35);
      if ( v38 >= 0 )
      {
        v39 = *((_QWORD *)this + 2);
        v40 = *((_QWORD *)this + 1);
        v141 = 0;
        v125 = 0;
        v41 = *(__int64 (__fastcall **)(__int64, _QWORD, struct _D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT **, __int64 *))(v39 + 24);
        v137 = 0;
        v138 = 0;
        v139 = 0;
        v140 = 0;
        v136[0] = 0;
        v42 = v41(v40, (unsigned int)v17, &v125, &v141);
        v20 = v42;
        if ( v42 < 0 )
        {
          WdLogSingleEntry1(2, v42);
          v101 = L"Failed call to DXGDMM_VIDPNSOURCEMODESET_INTERFACE::pfnAcquireTargetModeSet. (Status = 0x%I64x)";
          WdLogGlobalForLineNumber = 818;
          goto LABEL_181;
        }
        DXGDMM::AutoRelease<D3DKMDT_HVIDPNTARGETMODESET__ *,long (*)(D3DKMDT_HVIDPN__ *,D3DKMDT_HVIDPNTARGETMODESET__ *),D3DKMDT_HVIDPN__ *>::Own(
          v136,
          v125,
          *(_QWORD *)(*((_QWORD *)this + 2) + 32LL),
          *((_QWORD *)this + 1));
        v43 = v137;
        v125 = 0;
        v143 = 0;
        v44 = *(__int64 (__fastcall **)(__int64, struct _D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT **))(v141 + 8);
        v144 = 0;
        v145 = 0;
        v146 = 0;
        v142[0] = 0;
        v45 = v44(v137, &v125);
        v20 = v45;
        if ( v45 < 0 )
        {
          WdLogSingleEntry1(2, v45);
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
          if ( v136[0] )
            v138(v139, v43);
          goto LABEL_182;
        }
        for ( i = v125; ; i = v151 )
        {
          DXGDMM::AutoRelease<_D3DKMDT_VIDPN_PRESENT_PATH const *,long (*)(D3DKMDT_HVIDPNTOPOLOGY__ *,_D3DKMDT_VIDPN_PRESENT_PATH const *),D3DKMDT_HVIDPNTOPOLOGY__ *>::Own(
            v142,
            i,
            *(_QWORD *)(v141 + 32),
            v43);
          v48 = v143;
          if ( !v143 )
            break;
          LOBYTE(v47) = 1;
          v49 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(v141 + 48))(v43, *v143, v47);
          if ( v49 >= 0 )
          {
            v119[0] = 0;
            v149 = 0;
            if ( v36[1] - 3 <= 1 || v122 )
            {
              v119[0] = 1;
            }
            else
            {
              v51 = (*(__int64 (__fastcall **)(__int64, _QWORD, char *, int *))(v141 + 64))(v43, *v48, v119, &v149);
              v20 = v51;
              if ( v51 == -1071774920 )
              {
                v52 = WdLogNewEntry5_WdTrace();
                *(_QWORD *)(v52 + 24) = (unsigned int)v17;
                *(_QWORD *)(v52 + 32) = *((unsigned int *)this + 10);
                WdLogGlobalForLineNumber = 883;
              }
              else if ( v51 < 0 )
              {
                WdLogSingleEntry2(2, v51, v48);
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
            v118 = 0;
            if ( v159.VideoSignalInfo.ActiveSize.cx == v36[2] && v159.VideoSignalInfo.ActiveSize.cy == v36[3] )
            {
              LOBYTE(v50) = v123;
              if ( (*(int (__fastcall **)(unsigned int *, struct _D3DKMDT_MONITOR_SOURCE_MODE *, __int64, char *))(v141 + 80))(
                     v48,
                     &v159,
                     v50,
                     &v118) < 0 )
                v118 = 0;
            }
            v54 = *((_QWORD *)this + 4);
            v55 = *((unsigned int *)this + 10);
            v56 = *((_QWORD *)this + 3);
            v125 = 0;
            v57 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, struct _D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT **))(v54 + 24))(
                    v56,
                    v55,
                    (unsigned int)v17,
                    &v125);
            v20 = v57;
            if ( v57 >= 0 )
            {
              v58 = v125[4];
              (*(void (__fastcall **)(_QWORD))(*((_QWORD *)this + 4) + 32LL))(*((_QWORD *)this + 3));
              if ( v36[2] == v48[5] && v36[3] == v48[6] )
                v59 = (char)v58;
              else
                v59 = -((*(_BYTE *)&v58 & 0x1E) != 0);
              v60 = v59 & 1;
              LOBYTE(v128[0]) = v60;
              for ( j = 0; ; j = v150 + 1 )
              {
                v150 = j;
                if ( j >= 5 || !v60 )
                {
                  v84 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(*((_QWORD *)this + 4) + 72LL))(
                          *((_QWORD *)this + 3),
                          *((unsigned int *)this + 10),
                          (unsigned int)v17,
                          0);
                  LODWORD(v125) = v84;
                  if ( v84 >= 0 )
                    goto LABEL_118;
                  v100 = v84;
                  WdLogSingleEntry4(2, v84, *((unsigned int *)this + 10), *((_QWORD *)this + 3), v17);
                  WdLogGlobalForLineNumber = 1208;
                  DxgkLogInternalTriageEvent(
                    0,
                    0x40000,
                    -1,
                    (unsigned int)L"Unable to unpin scaling. (Status = 0x%I64x, m_VidPnSourceId = 0x%I64x, m_hVidPnTopolog"
                                   "y = 0x%I64x, PrimVidPnTargetId = 0x%I64x)",
                    v100,
                    *((unsigned int *)this + 10),
                    *((_QWORD *)this + 3),
                    v17,
                    0);
LABEL_144:
                  if ( v142[0] )
                    v144(v145, v48);
                  if ( v136[0] )
                  {
                    v95 = v43;
                    goto LABEL_157;
                  }
LABEL_158:
                  v93 = v130[0] == 0;
LABEL_159:
                  if ( !v93 )
                    v132(v133, v36);
                  if ( v29 )
                    v127(v126, v29);
                  return (unsigned int)v125;
                }
                v121 = dword_1400ED8B8[j];
                if ( BmlIsSupportedPathScaling((enum _D3DKMDT_VIDPN_PRESENT_PATH_SCALING)v121, v58) )
                {
                  LOBYTE(v117) = 1;
                  v62 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, __int64))(*((_QWORD *)this + 4) + 64LL))(
                          *((_QWORD *)this + 3),
                          *((unsigned int *)this + 10),
                          (unsigned int)v17,
                          (unsigned int)v121,
                          v117);
                  LODWORD(v125) = v62;
                  if ( v62 == -1071774970 )
                  {
                    v91 = v121;
                    WdLogSingleEntry4(1, v121, *((unsigned int *)this + 10), v17, -1071774970);
                    v92 = L"Failed to pin the reported-as-supported scaling mode 0x%I64x on the path (0x%I64x, 0x%I64x) be"
                           "cause of not supported by driver, returning 0x%I64x.";
                    WdLogGlobalForLineNumber = 976;
LABEL_165:
                    DxgkLogInternalTriageEvent(
                      0,
                      262147,
                      -1,
                      (_DWORD)v92,
                      v91,
                      *((unsigned int *)this + 10),
                      v17,
                      -1071774970,
                      0);
                    if ( v142[0] )
                      v144(v145, v48);
                    if ( v136[0] )
                      v138(v139, v43);
                    if ( v130[0] )
                      v132(v133, v36);
                    if ( v29 )
                      v127(v126, v29);
                    return 3223192326LL;
                  }
                  if ( v62 < 0 )
                  {
                    v97 = v121;
                    v98 = v129;
                    v99 = v62;
                    WdLogSingleEntry5(2, v62, *((unsigned int *)this + 10));
                    WdLogGlobalForLineNumber = 982;
                    DxgkLogInternalTriageEvent(
                      0,
                      0x40000,
                      -1,
                      (unsigned int)L"Unable to set scaling on the path. ( Status = 0x%I64x, m_VidPnSourceId = 0x%I64x, Pr"
                                     "imVidPnTargetId = 0x%I64x, m_hVidPnTopology = 0x%I64x, PathScaling = 0x%I64x)",
                      v99,
                      *((unsigned int *)this + 10),
                      v98,
                      *((_QWORD *)this + 3),
                      v97);
                    if ( v142[0] )
                      v144(v145, v48);
                    if ( v136[0] )
                    {
                      v95 = v137;
LABEL_157:
                      v138(v139, v95);
                    }
                    goto LABEL_158;
                  }
                  v63 = *((_QWORD *)this + 4);
                  v64 = *((unsigned int *)this + 10);
                  v65 = *((_QWORD *)this + 3);
                  v147 = 0;
                  v66 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, struct _D3DKMDT_VIDPN_PRESENT_PATH_ROTATION_SUPPORT **))(v63 + 24))(
                          v65,
                          v64,
                          (unsigned int)v17,
                          &v147);
                  LODWORD(v125) = v66;
                  if ( v66 < 0 )
                  {
                    v96 = v66;
                    WdLogSingleEntry1(2, v66);
                    WdLogGlobalForLineNumber = 997;
                    DxgkLogInternalTriageEvent(
                      0,
                      0x40000,
                      -1,
                      (unsigned int)L"Failed call to DXGDMM_VIDPNTOPOLOGY_INTERFACE::pfnAcquirePathInfo. (Status = 0x%I64x)",
                      v96,
                      0,
                      0,
                      0,
                      0);
                    if ( v142[0] )
                      v144(v145, v48);
                    if ( v136[0] )
                      v138(v139, v43);
                    v93 = v130[0] == 0;
                    goto LABEL_159;
                  }
                  v67 = v147[6];
                  (*(void (__fastcall **)(_QWORD))(*((_QWORD *)this + 4) + 32LL))(*((_QWORD *)this + 3));
                  for ( k = D3DKMDT_VPPR_IDENTITY; ; k = v120 + 1 )
                  {
                    v120 = k;
                    if ( k > D3DKMDT_VPPR_ROTATE270 )
                      break;
                    if ( BmlIsSupportedPathRotation(k, v67) )
                    {
                      v124[0] = 0;
                      memset(&v154, 0, sizeof(v154));
                      v69 = *((_QWORD *)v155 + 407)
                         || !*(_BYTE *)(*((_QWORD *)v155 + 406) + 289LL)
                         || v120 == D3DKMDT_VPPR_IDENTITY;
                      v70 = v118 && v121 == D3DKMDT_VOT_SVIDEO;
                      PopulateDisplayModeFromPresentPath(
                        (_DWORD)v36,
                        (_DWORD)v48,
                        v121,
                        v120,
                        v119[0],
                        v70,
                        v69,
                        v149,
                        (__int64)&v154,
                        (__int64)v124);
                      if ( *((_DWORD *)this + 13) > 1u )
                      {
                        LOBYTE(v117) = 0;
                        v72 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))(*((_QWORD *)this + 4)
                                                                                                + 80LL))(
                                *((_QWORD *)this + 3),
                                *((unsigned int *)this + 10),
                                v129,
                                (unsigned int)v120,
                                v117);
                        LODWORD(v147) = v72;
                        if ( v72 == -1071774970 )
                        {
                          v17 = v129;
                          v91 = v120;
                          WdLogSingleEntry4(1, v120, *((unsigned int *)this + 10), v129, -1071774970);
                          v92 = L"Failed to pin the reported-as-supported rotation mode 0x%I64x on the path (0x%I64x, 0x%I"
                                 "64x) because of not supported by driver, returning 0x%I64x.";
                          WdLogGlobalForLineNumber = 1063;
                          goto LABEL_165;
                        }
                        if ( v72 < 0 )
                        {
                          v88 = v120;
                          v89 = v129;
                          v90 = v72;
                          WdLogSingleEntry5(2, v72, *((unsigned int *)this + 10));
                          WdLogGlobalForLineNumber = 1069;
                          DxgkLogInternalTriageEvent(
                            0,
                            0x40000,
                            -1,
                            (unsigned int)L"Unable to set rotation on the path. (Status = 0x%I64x, m_VidPnSourceId = 0x%I6"
                                           "4x, PrimVidPnTargetId = 0x%I64x, m_hVidPnTopology = 0x%I64x, PathRotation = 0x%I64x)",
                            v90,
                            *((unsigned int *)this + 10),
                            v89,
                            *((_QWORD *)this + 3),
                            v88);
                          if ( v142[0] )
                            v144(v145, v48);
                          if ( v136[0] )
                            v138(v139, v137);
                          v74 = v130[0] == 0;
                          goto LABEL_132;
                        }
                      }
                      if ( v154.Format != D3DDDIFMT_A8R8G8B8 && *((_BYTE *)this + 44)
                        || v154.Format <= (unsigned int)D3DDDIFMT_P8
                        && (v73 = 0x20003900000LL, _bittest64(&v73, (unsigned int)v154.Format)) )
                      {
                        if ( v153 )
                        {
                          LODWORD(v147) = MODE_UNION_LIST::AddUniqueMode(
                                            (OBTAIN_MODES_ON_SOURCE *)((char *)this + 104),
                                            &v154);
                          if ( (int)v147 < 0 )
                          {
                            if ( v142[0] )
                              v144(v145, v48);
                            if ( v136[0] )
                              v138(v139, v43);
                            v74 = v130[0] == 0;
LABEL_132:
                            if ( !v74 )
                              v132(v133, v36);
                            if ( v29 )
                              v127(v126, v29);
                            return (unsigned int)v147;
                          }
                        }
                      }
                      else
                      {
                        LODWORD(v125) = OBTAIN_MODES_ON_SOURCE::_AddMode(this, &v154, v71, v124[0] != 0);
                        if ( (int)v125 < 0 )
                        {
LABEL_138:
                          if ( v142[0] )
                            v144(v145, v48);
                          if ( v136[0] )
                            v138(v139, v43);
                          v93 = v130[0] == 0;
                          goto LABEL_159;
                        }
                        v135 = 0;
                        v75 = *(struct _D3DDDI_RATIONAL *)(v48 + 7);
                        v135 = v75;
                        if ( ((v48[14] >> 3) & 0x3F) != 0 )
                          v135.Denominator = ((v48[14] >> 3) & 0x3F) * v75.Denominator;
                        if ( !IsUnspecifiedFrequency((const struct _D3DDDI_RATIONAL *)(v48 + 17))
                          && (*v76 != v135.Numerator || v48[18] != v77) )
                        {
                          for ( m = 0;
                                ;
                                m = (struct _D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT *)(unsigned int)((_DWORD)v147 + 1) )
                          {
                            LODWORD(v147) = (_DWORD)m;
                            if ( (unsigned int)m >= 7 )
                              break;
                            v125 = m;
                            if ( !DMMVIDEOSIGNALMODE::IsFreqWithinToleranceRange(
                                    &v135,
                                    (const struct _D3DDDI_RATIONAL *)&byte_1400ED880[8 * (_QWORD)m],
                                    0)
                              && (*(int (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(v141 + 88))(
                                   v43,
                                   *v48,
                                   0x140000000LL + 8LL * (_QWORD)v125 + 972928,
                                   (unsigned int)(v79 + 1)) >= 0 )
                            {
                              v80 = (unsigned int)dword_1400ED884[2 * (_QWORD)v125];
                              v81 = (unsigned int)*(_QWORD *)(8LL * (_QWORD)v125 + 972928 + 0x140000000LL);
                              v154.RefreshRate = *(D3DDDI_RATIONAL *)(8LL * (_QWORD)v125 + 972928 + 0x140000000LL);
                              v154.IntegerRefreshRate = DivideAndRound(v81, v80);
                              if ( !MODE_UNION_LIST::FindMode((OBTAIN_MODES_ON_SOURCE *)((char *)this + 64), &v154) )
                              {
                                *((_DWORD *)&v154.Flags + 1) |= 0x100u;
                                LODWORD(v125) = OBTAIN_MODES_ON_SOURCE::_AddMode(this, &v154, v82, 0);
                                if ( (int)v125 < 0 )
                                  goto LABEL_138;
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                  v17 = v129;
                  if ( *((_DWORD *)this + 13) > 1u )
                  {
                    v83 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(*((_QWORD *)this + 4) + 88LL))(
                            *((_QWORD *)this + 3),
                            *((unsigned int *)this + 10),
                            v129,
                            0);
                    LODWORD(v125) = v83;
                    if ( v83 < 0 )
                    {
                      v94 = v83;
                      WdLogSingleEntry4(2, v83, *((_QWORD *)this + 3), *((unsigned int *)this + 10), v17);
                      WdLogGlobalForLineNumber = 1194;
                      DxgkLogInternalTriageEvent(
                        0,
                        0x40000,
                        -1,
                        (unsigned int)L"Unable to unpin rotation. (Status = 0x%I64x, m_hVidPnTopology = 0x%I64x, m_VidPnSo"
                                       "urceId = 0x%I64x, PrimVidPnTargetId = 0x%I64x)",
                        v94,
                        *((_QWORD *)this + 3),
                        *((unsigned int *)this + 10),
                        v17,
                        0);
                      goto LABEL_144;
                    }
                  }
                }
                v60 = v128[0];
              }
            }
            WdLogSingleEntry1(2, v57);
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
            if ( v142[0] )
              v144(v145, v48);
            if ( v136[0] )
              v138(v139, v43);
            v53 = v130[0] == 0;
LABEL_183:
            if ( !v53 )
              v132(v133, v36);
            if ( v29 )
              v127(v126, v29);
            return (unsigned int)v20;
          }
          WdLogSingleEntry2(3, v49, *v48);
          WdLogGlobalForLineNumber = 858;
LABEL_118:
          v151 = 0;
          v85 = (*(__int64 (__fastcall **)(__int64, unsigned int *, struct _D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT **))(v141 + 16))(
                  v43,
                  v48,
                  &v151);
          v20 = v85;
          if ( v85 < 0 )
          {
            WdLogSingleEntry1(2, v85);
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
        v86 = (*(__int64 (__fastcall **)(__int64, _QWORD))(v141 + 56))(v43, 0);
        v20 = v86;
        if ( v86 < 0 )
        {
          WdLogSingleEntry3(2, v86, v43, 0xFFFFFFFFLL);
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
        if ( v142[0] )
          v144(v145, 0);
        if ( v136[0] )
          v138(v139, v43);
      }
      else
      {
        WdLogSingleEntry2(3, v38, *v36);
        WdLogGlobalForLineNumber = 799;
      }
    }
    v152 = 0;
    v87 = (*(__int64 (__fastcall **)(__int64, unsigned int *, __int64 *))(v148 + 16))(v29, v36, &v152);
    v20 = v87;
    if ( v87 < 0 )
    {
      WdLogSingleEntry1(2, v87);
      v101 = L"Failed call to DXGDMM_VIDPNSOURCEMODESET_INTERFACE::pfnAcquireNextModeInfo. (Status = 0x%I64x)";
      WdLogGlobalForLineNumber = 1252;
LABEL_181:
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v101, v20, 0, 0, 0, 0);
LABEL_182:
      v53 = v130[0] == 0;
      goto LABEL_183;
    }
    DXGDMM::AutoRelease<_D3DKMDT_VIDPN_PRESENT_PATH const *,long (*)(D3DKMDT_HVIDPNTOPOLOGY__ *,_D3DKMDT_VIDPN_PRESENT_PATH const *),D3DKMDT_HVIDPNTOPOLOGY__ *>::Own(
      v130,
      v152,
      *(_QWORD *)(v148 + 32),
      v29);
  }
  v102 = (*(__int64 (__fastcall **)(__int64, _QWORD))(v148 + 48))(v29, 0);
  v20 = v102;
  if ( v102 < 0 )
  {
    WdLogSingleEntry3(2, v102, v29, 0xFFFFFFFFLL);
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
  v103 = ExposedViaHandle<DMMVIDPN,D3DKMDT_HVIDPN__ *>::GetFromHandle(*((_QWORD *)this + 1));
  v104 = v156;
  *(_BYTE *)(v103 + 296) = 0;
  v105 = *v104;
  if ( !*v104 )
  {
    v106 = *((_DWORD *)this + 20);
    if ( v106 )
    {
      v108 = v106;
      v107 = 44LL * v106;
      if ( !is_mul_ok(v108, 0x2Cu) )
        v107 = -1;
      v105 = (struct _D3DKMT_DISPLAYMODE *)operator new[](v107, 1265072196, 256);
      *v104 = v105;
      if ( !v105 )
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
        if ( v130[0] )
          v132(v133, 0);
        if ( v29 )
          v127(v126, v29);
        return 3221225495LL;
      }
    }
    else
    {
      v105 = 0;
    }
  }
  UniqueModes = MODE_UNION_LIST::GetUniqueModes(
                  (OBTAIN_MODES_ON_SOURCE *)((char *)this + 64),
                  *((unsigned int *)this + 20),
                  v105,
                  v157);
  if ( UniqueModes < 0 )
  {
    v110 = UniqueModes;
    WdLogSingleEntry1(1, UniqueModes);
    WdLogGlobalForLineNumber = 1294;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"GetUniqueModesFromUnionList failed. (Status = 0x%I64x)",
      v110,
      0,
      0,
      0,
      0);
  }
  v111 = v153;
  if ( v153 )
  {
    if ( *v153 )
    {
      DXGQUOTAALLOCATOR<256,1835156294>::operator delete(*v153);
      *v111 = 0;
    }
    v112 = *((unsigned int *)this + 30);
    if ( (_DWORD)v112 )
    {
      v113 = 44 * v112;
      if ( !is_mul_ok(*((unsigned int *)this + 30), 0x2Cu) )
        v113 = -1;
      v114 = (struct _D3DKMT_DISPLAYMODE *)operator new[](v113, 1265072196, 256);
      *v111 = v114;
      if ( v114 )
      {
        v115 = MODE_UNION_LIST::GetUniqueModes(
                 (OBTAIN_MODES_ON_SOURCE *)((char *)this + 104),
                 *((unsigned int *)this + 30),
                 v114,
                 v158);
        if ( v115 < 0 )
        {
          v116 = v115;
          WdLogSingleEntry1(1, v115);
          WdLogGlobalForLineNumber = 1321;
          DxgkLogInternalTriageEvent(
            0,
            262146,
            -1,
            (unsigned int)L"GetUniqueModesFromInvalidModesUnionList failed. (Status = 0x%I64x)",
            v116,
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
  if ( v130[0] )
    v132(v133, 0);
  if ( v29 )
    v127(v126, v29);
  return 0;
}

```

## disassembly

```asm
0x1403375fc  push    rbp
0x1403375fe  push    rbx
0x1403375ff  push    rsi
0x140337600  push    rdi
0x140337601  push    r12
0x140337603  push    r13
0x140337605  push    r14
0x140337607  push    r15
0x140337609  lea     rbp, [rsp-108h]
0x140337611  sub     rsp, 208h
0x140337618  mov     rax, cs:__security_cookie
0x14033761f  xor     rax, rsp
0x140337622  mov     [rbp+140h+var_50], rax
0x140337629  mov     rax, [rbp+140h+arg_20]
0x140337630  mov     edi, 0FFFFFFFFh
0x140337635  xor     r13d, r13d
0x140337638  mov     [rbp+140h+var_C0], rax
0x14033763f  mov     r12d, edi
0x140337642  mov     [rsp+240h+var_1C4], edi
0x140337646  mov     ebx, r13d
0x140337649  mov     [rbp+140h+var_110], r9
0x14033764d  mov     [rbp+140h+var_C8], r8
0x140337651  mov     r15, rcx
0x140337654  mov     [rbp+140h+var_D0], rdx
0x140337658  mov     r14d, 0FFh
0x14033765e  mov     rax, [r15+20h]
0x140337662  lea     r9, [rsp+240h+var_1E8]
0x140337667  mov     edx, [r15+28h]
0x14033766b  mov     rcx, [r15+18h]
0x14033766f  mov     [rsp+240h+var_1E8], edi
0x140337673  mov     rax, [rax+8]
0x140337677  mov     r8d, ebx
0x14033767a  mov     edi, ebx
0x14033767c  call    _guard_dispatch_icall
0x140337681  movsxd  rsi, eax
0x140337684  test    eax, eax
0x140337686  js      loc_140338B20
0x14033768c  mov     r8d, [rsp+240h+var_1E8]
0x140337691  mov     edi, 0FFFFFFFFh
0x140337696  cmp     r8d, edi
0x140337699  jz      loc_140337757
0x14033769f  inc     dword ptr [r15+34h]
0x1403376a3  lea     rcx, [rsp+240h+var_1C8]
0x1403376a8  mov     edx, [r15+28h]
0x1403376ac  lea     r9, [rsp+240h+var_1EC]
0x1403376b1  mov     eax, 0FFFFh
0x1403376b6  mov     [rsp+240h+var_1EC], r13d
0x1403376bb  mov     [rsp+240h+var_1C8], ax
0x1403376c0  mov     rax, [r15+20h]
0x1403376c4  mov     [rsp+240h+var_220], rcx
0x1403376c9  mov     rcx, [r15+18h]
0x1403376cd  mov     rax, [rax+70h]
0x1403376d1  call    _guard_dispatch_icall
0x1403376d6  movsxd  rsi, eax
0x1403376d9  test    eax, eax
0x1403376db  js      short loc_140337703
0x1403376dd  cmp     r12d, edi
0x1403376e0  jz      short loc_1403376E9
0x1403376e2  cmp     [rsp+240h+var_1EC], r14d
0x1403376e7  jge     short loc_1403376FC
0x1403376e9  mov     r12d, [rsp+240h+var_1E8]
0x1403376ee  mov     r14d, [rsp+240h+var_1EC]
0x1403376f3  mov     [rsp+240h+var_1C4], r12d
0x1403376f8  mov     [r15+30h], ebx
0x1403376fc  inc     ebx
0x1403376fe  jmp     loc_14033765E
0x140337703  mov     r9d, [r15+28h]
0x140337707  mov     rdx, rsi
0x14033770a  mov     r8d, r12d
0x14033770d  mov     ecx, 2
0x140337712  mov     ebx, r12d
0x140337715  call    cs:__imp_WdLogSingleEntry3
0x14033771c  nop     dword ptr [rax+rax+00h]
0x140337721  mov     [rsp+240h+var_200], r13
0x140337726  lea     r9, aFailedCallToDx_2; "Failed call to DXGDMM_VIDPNTOPOLOGY_INT"...
0x14033772d  mov     [rsp+240h+var_208], r13
0x140337732  mov     edx, 40000h
0x140337737  mov     cs:WdLogGlobalForLineNumber, 2A3h
0x140337741  mov     r8, rdi
0x140337744  mov     eax, [r15+28h]
0x140337748  mov     [rsp+240h+var_210], rax
0x14033774d  mov     [rsp+240h+var_218], rbx
0x140337752  jmp     loc_140338B6F
0x140337757  mov     ebx, [rsp+240h+var_1C4]
0x14033775b  cmp     ebx, edi
0x14033775d  jnz     short loc_1403377B0
0x14033775f  cmp     [r15+34h], r13d
0x140337763  jz      short loc_1403377B0
0x140337765  mov     ecx, 1
0x14033776a  call    cs:__imp_WdLogSingleEntry0
0x140337771  nop     dword ptr [rax+rax+00h]
0x140337776  mov     [rsp+240h+var_200], r13
0x14033777b  lea     r9, aPrimvidpntarge; "(PrimVidPnTargetId != D3DDDI_ID_UNINITI"...
0x140337782  mov     [rsp+240h+var_208], r13
0x140337787  mov     eax, 2B3h
0x14033778c  mov     [rsp+240h+var_210], r13
0x140337791  mov     r8d, edi
0x140337794  mov     [rsp+240h+var_218], r13
0x140337799  mov     edx, 40002h
0x14033779e  xor     ecx, ecx
0x1403377a0  mov     [rsp+240h+var_220], rax
0x1403377a5  mov     cs:WdLogGlobalForLineNumber, eax
0x1403377ab  call    DxgkLogInternalTriageEvent
0x1403377b0  mov     rsi, [r15]
0x1403377b3  lea     r9, [rsp+240h+var_1E8]; enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *
0x1403377b8  mov     rcx, rsi; void *
0x1403377bb  mov     [rbp+140h+var_D8], rsi
0x1403377bf  xor     r8d, r8d; enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *
0x1403377c2  mov     [rsp+240h+var_1E8], r13d
0x1403377c7  mov     edx, ebx; unsigned int
0x1403377c9  call    ?DmmGetVideoOutputTechnology@@YAJQEAXIPEAW4_D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY@@1@Z; DmmGetVideoOutputTechnology(void * const,uint,_D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *,_D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *)
0x1403377ce  movsxd  rdi, eax
0x1403377d1  test    eax, eax
0x1403377d3  jns     short loc_14033782C
0x1403377d5  mov     rdx, rdi
0x1403377d8  mov     ecx, 2
0x1403377dd  call    cs:__imp_WdLogSingleEntry1
0x1403377e4  nop     dword ptr [rax+rax+00h]
0x1403377e9  lea     r9, aFailedCallToDm_0; "Failed call to DmmGetVideoOutputTechnol"...
0x1403377f0  mov     cs:WdLogGlobalForLineNumber, 2BFh
0x1403377fa  mov     [rsp+240h+var_200], r13
0x1403377ff  mov     edx, 40000h
0x140337804  mov     [rsp+240h+var_208], r13
0x140337809  xor     ecx, ecx
0x14033780b  mov     [rsp+240h+var_210], r13
0x140337810  mov     r8d, 0FFFFFFFFh
0x140337816  mov     [rsp+240h+var_218], r13
0x14033781b  mov     [rsp+240h+var_220], rdi
0x140337820  call    DxgkLogInternalTriageEvent
0x140337825  mov     eax, edi
0x140337827  jmp     loc_140338B7D
0x14033782c  mov     eax, [rsp+240h+var_1E8]
0x140337830  sub     eax, 0Fh
0x140337833  jz      short loc_140337844
0x140337835  sub     eax, 1
0x140337838  jz      short loc_140337844
0x14033783a  mov     [rsp+240h+var_1E3], r13b
0x14033783f  cmp     eax, 1
0x140337842  jnz     short loc_140337849
0x140337844  mov     [rsp+240h+var_1E3], 1
0x140337849  cmp     [rsi+0CB8h], r13
0x140337850  jnz     short loc_140337867
0x140337852  mov     rcx, [rsi+0CB0h]; this
0x140337859  call    ?GetDisplayOnlyDriverUseRawModes@ADAPTER_DISPLAY@@QEBAHXZ; ADAPTER_DISPLAY::GetDisplayOnlyDriverUseRawModes(void)
0x14033785e  mov     [rsp+240h+var_1E4], 1
0x140337863  test    eax, eax
0x140337865  jnz     short loc_14033786C
0x140337867  mov     [rsp+240h+var_1E4], r13b
0x14033786c  mov     edi, 60h ; '`'
0x140337871  lea     rcx, [rbp+140h+var_B0]; void *
0x140337878  mov     r8d, edi; Size
0x14033787b  xor     edx, edx; Val
0x14033787d  call    memset
0x140337882  mov     rcx, [r15]; void *
0x140337885  lea     r8, [rbp+140h+var_B0]; struct _D3DKMDT_MONITOR_SOURCE_MODE *
0x14033788c  mov     edx, ebx; unsigned int
0x14033788e  call    ?DmmGetPreferredMonitorSourceModeOnTarget@@YAJPEAXIPEAU_D3DKMDT_MONITOR_SOURCE_MODE@@@Z; DmmGetPreferredMonitorSourceModeOnTarget(void *,uint,_D3DKMDT_MONITOR_SOURCE_MODE *)
0x140337893  test    eax, eax
0x140337895  jns     short loc_1403378A8
0x140337897  mov     r8d, edi; Size
0x14033789a  lea     rcx, [rbp+140h+var_B0]; void *
0x1403378a1  xor     edx, edx; Val
0x1403378a3  call    memset
0x1403378a8  mov     rax, [r15+10h]
0x1403378ac  lea     r9, [rbp+140h+var_130]
0x1403378b0  mov     edx, [r15+28h]
0x1403378b4  lea     r8, [rbp+140h+var_198]
0x1403378b8  mov     rcx, [r15+8]
0x1403378bc  mov     [rbp+140h+var_130], r13
0x1403378c0  mov     qword ptr [rbp+140h+var_198.Numerator], r13
0x1403378c4  mov     rax, [rax+8]
0x1403378c8  call    _guard_dispatch_icall
0x1403378cd  movsxd  rdi, eax
0x1403378d0  test    eax, eax
0x1403378d2  jns     short loc_1403378FE
0x1403378d4  mov     rdx, rdi
0x1403378d7  mov     ecx, 2
0x1403378dc  call    cs:__imp_WdLogSingleEntry1
0x1403378e3  nop     dword ptr [rax+rax+00h]
0x1403378e8  lea     r9, aFailedCallToDx_3; "Failed call to DXGDMM_VIDPN_INTERFACE::"...
0x1403378ef  mov     cs:WdLogGlobalForLineNumber, 2DDh
0x1403378f9  jmp     loc_1403377FA
0x1403378fe  mov     rax, [r15+10h]
0x140337902  lea     rdx, [rbp+140h+var_198]
0x140337906  mov     r14, qword ptr [rbp+140h+var_198.Numerator]
0x14033790a  mov     rdi, [r15+8]
0x14033790e  mov     rcx, r14
0x140337911  mov     [rsp+240h+var_1D8], rdi
0x140337916  mov     r12, [rax+10h]
0x14033791a  mov     rax, [rbp+140h+var_130]
0x14033791e  mov     qword ptr [rbp+140h+var_198.Numerator], r13
0x140337922  mov     [rsp+240h+var_1D0], r12
0x140337927  mov     [rbp+140h+var_1B8], r13
0x14033792b  mov     rax, [rax+8]
0x14033792f  mov     [rbp+140h+var_1B0], r13
0x140337933  mov     [rbp+140h+var_1A8], r13
0x140337937  mov     [rbp+140h+var_1A0], r13d
0x14033793b  mov     [rbp+140h+var_1C0], r13b
0x14033793f  call    _guard_dispatch_icall
0x140337944  movsxd  rsi, eax
0x140337947  test    eax, eax
0x140337949  jns     short loc_1403379B7
0x14033794b  mov     rdx, rsi
0x14033794e  mov     ecx, 2
0x140337953  call    cs:__imp_WdLogSingleEntry1
0x14033795a  nop     dword ptr [rax+rax+00h]
0x14033795f  mov     [rsp+240h+var_200], r13
0x140337964  lea     r9, aFailedCallToDx_4; "Failed call to DXGDMM_VIDPNSOURCEMODESE"...
0x14033796b  mov     [rsp+240h+var_208], r13
0x140337970  mov     edx, 40000h
0x140337975  mov     [rsp+240h+var_210], r13
0x14033797a  xor     ecx, ecx
0x14033797c  mov     [rsp+240h+var_218], r13
0x140337981  mov     r8d, 0FFFFFFFFh
0x140337987  mov     [rsp+240h+var_220], rsi
0x14033798c  mov     cs:WdLogGlobalForLineNumber, 2F1h
0x140337996  call    DxgkLogInternalTriageEvent
0x14033799b  test    r14, r14
0x14033799e  jz      loc_140338B7B
0x1403379a4  mov     rdx, r14
0x1403379a7  mov     rcx, rdi
0x1403379aa  mov     rax, r12
0x1403379ad  call    _guard_dispatch_icall
0x1403379b2  jmp     loc_140338B7B
0x1403379b7  mov     r8, [rbp+140h+var_130]
0x1403379bb  lea     rcx, [rbp+140h+var_1C0]
0x1403379bf  mov     rdx, qword ptr [rbp+140h+var_198.Numerator]
0x1403379c3  mov     r9, r14
0x1403379c6  mov     r8, [r8+20h]
0x1403379ca  call    ?Own@?$AutoRelease@PEBU_D3DKMDT_VIDPN_PRESENT_PATH@@P6AJPEAUD3DKMDT_HVIDPNTOPOLOGY__@@PEBU1@@ZPEAU2@@DXGDMM@@QEAAXPEBU_D3DKMDT_VIDPN_PRESENT_PATH@@Q6AJPEAUD3DKMDT_HVIDPNTOPOLOGY__@@0@Z1@Z; DXGDMM::AutoRelease<_D3DKMDT_VIDPN_PRESENT_PATH const *,long (*)(D3DKMDT_HVIDPNTOPOLOGY__ *,_D3DKMDT_VIDPN_PRESENT_PATH const *),D3DKMDT_HVIDPNTOPOLOGY__ *>::Own(_D3DKMDT_VIDPN_PRESENT_PATH const *,long (*const)(D3DKMDT_HVIDPNTOPOLOGY__ *,_D3DKMDT_VIDPN_PRESENT_PATH const *),D3DKMDT_HVIDPNTOPOLOGY__ *)
0x1403379cf  mov     rcx, [r15+8]
0x1403379d3  call    ?GetFromHandle@?$ExposedViaHandle@VDMMVIDPN@@PEAUD3DKMDT_HVIDPN__@@@@SAPEAVDMMVIDPN@@PEAUD3DKMDT_HVIDPN__@@@Z; ExposedViaHandle<DMMVIDPN,D3DKMDT_HVIDPN__ *>::GetFromHandle(D3DKMDT_HVIDPN__ *)
0x1403379d8  xor     r12d, r12d
0x1403379db  mov     byte ptr [rax+128h], 1
0x1403379e2  mov     r13, [rbp+140h+var_1B8]
0x1403379e6  test    r13, r13
0x1403379e9  jz      loc_140338832
0x1403379ef  mov     eax, [r13+4]
0x1403379f3  mov     rdi, r13
0x1403379f6  cmp     eax, 3
0x1403379f9  jz      short loc_140337A09
0x1403379fb  cmp     eax, 4
0x1403379fe  jz      short loc_140337A09
0x140337a00  cmp     eax, 1
0x140337a03  jnz     loc_140338193
0x140337a09  mov     eax, [rdi+10h]
0x140337a0c  cmp     [rdi+8], eax
0x140337a0f  jnz     loc_140338193
0x140337a15  mov     eax, [rdi+14h]
0x140337a18  cmp     [rdi+0Ch], eax
0x140337a1b  jnz     loc_140338193
0x140337a21  mov     rax, [rbp+140h+var_130]
0x140337a25  mov     r8b, 1
0x140337a28  mov     edx, [rdi]
0x140337a2a  mov     rcx, r14
0x140337a2d  mov     rax, [rax+28h]
0x140337a31  call    _guard_dispatch_icall
0x140337a36  test    eax, eax
0x140337a38  jns     short loc_140337A60
0x140337a3a  mov     r8d, [rdi]
0x140337a3d  mov     ecx, 3
0x140337a42  movsxd  rdx, eax
0x140337a45  call    cs:__imp_WdLogSingleEntry2
0x140337a4c  nop     dword ptr [rax+rax+00h]
0x140337a51  mov     cs:WdLogGlobalForLineNumber, 31Fh
0x140337a5b  jmp     loc_140338193
0x140337a60  mov     rax, [r15+10h]
0x140337a64  lea     r9, [rbp+140h+var_168]
0x140337a68  mov     rcx, [r15+8]
0x140337a6c  lea     r8, [rsp+240h+var_1E0]
0x140337a71  mov     [rbp+140h+var_168], r12
0x140337a75  mov     edx, ebx
0x140337a77  mov     [rsp+240h+var_1E0], r12
0x140337a7c  mov     rax, [rax+18h]
0x140337a80  mov     [rbp+140h+var_188], r12
0x140337a84  mov     [rbp+140h+var_180], r12
0x140337a88  mov     [rbp+140h+var_178], r12
0x140337a8c  mov     [rbp+140h+var_170], r12d
0x140337a90  mov     [rbp+140h+var_190], r12b
0x140337a94  call    _guard_dispatch_icall
0x140337a99  movsxd  rdi, eax
0x140337a9c  test    eax, eax
0x140337a9e  js      loc_140338782
0x140337aa4  mov     r8, [r15+10h]
0x140337aa8  lea     rcx, [rbp+140h+var_190]
0x140337aac  mov     r9, [r15+8]
0x140337ab0  mov     rdx, [rsp+240h+var_1E0]
0x140337ab5  mov     r8, [r8+20h]
0x140337ab9  call    ?Own@?$AutoRelease@PEAUD3DKMDT_HVIDPNTARGETMODESET__@@P6AJPEAUD3DKMDT_HVIDPN__@@PEAU1@@ZPEAU2@@DXGDMM@@QEAAXPEAUD3DKMDT_HVIDPNTARGETMODESET__@@Q6AJPEAUD3DKMDT_HVIDPN__@@0@Z1@Z; DXGDMM::AutoRelease<D3DKMDT_HVIDPNTARGETMODESET__ *,long (*)(D3DKMDT_HVIDPN__ *,D3DKMDT_HVIDPNTARGETMODESET__ *),D3DKMDT_HVIDPN__ *>::Own(D3DKMDT_HVIDPNTARGETMODESET__ *,long (*const)(D3DKMDT_HVIDPN__ *,D3DKMDT_HVIDPNTARGETMODESET__ *),D3DKMDT_HVIDPN__ *)
0x140337abe  mov     rax, [rbp+140h+var_168]
0x140337ac2  lea     rdx, [rsp+240h+var_1E0]
0x140337ac7  mov     rsi, [rbp+140h+var_188]
0x140337acb  mov     [rsp+240h+var_1E0], r12
0x140337ad0  mov     rcx, rsi
0x140337ad3  mov     [rbp+140h+var_158], r12
0x140337ad7  mov     rax, [rax+8]
0x140337adb  mov     [rbp+140h+var_150], r12
0x140337adf  mov     [rbp+140h+var_148], r12
0x140337ae3  mov     [rbp+140h+var_140], r12d
0x140337ae7  mov     [rbp+140h+var_160], r12b
  ... truncated ...
```
