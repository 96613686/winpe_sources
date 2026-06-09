# OBTAIN_PREFERRED_MODES_ON_PATH::operator()(_D3DKMT_DISPLAYMODE * *,uint *)

- ea: `0x1401bde28`
- end: `0x1401bec8e`
- name: `??ROBTAIN_PREFERRED_MODES_ON_PATH@@QEBAJPEAPEAU_D3DKMT_DISPLAYMODE@@PEAI@Z`
- size: `3686`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path`

## callers

- `0x1401db134`

## callees

- `0x140009030`
- `0x14001b890`
- `0x140046520`
- `0x140047960`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1400a0540`
- `0x1401bde28`
- `0x140229d70`
- `0x1402d8af8`
- `0x140330ac0`
- `0x140332188`
- `0x140332314`
- `0x140332f58`
- `0x140333480`
- `0x140368514`

## import_xrefs

- `watchdog!WdLogSingleEntry4` at `0x1401be09b`
- `watchdog!WdLogSingleEntry4` at `0x1401be09b`
- `watchdog!WdLogSingleEntry2` at `0x1401bdedc`
- `watchdog!WdLogSingleEntry2` at `0x1401bdf77`
- `watchdog!WdLogSingleEntry2` at `0x1401be237`
- `watchdog!WdLogSingleEntry2` at `0x1401be6a8`
- `watchdog!WdLogSingleEntry2` at `0x1401be8f7`
- `watchdog!WdLogSingleEntry2` at `0x1401be940`
- `watchdog!WdLogSingleEntry2` at `0x1401bea96`
- `watchdog!WdLogSingleEntry2` at `0x1401bdedc`
- `watchdog!WdLogSingleEntry2` at `0x1401bdf77`
- `watchdog!WdLogSingleEntry2` at `0x1401be237`
- `watchdog!WdLogSingleEntry2` at `0x1401be6a8`
- `watchdog!WdLogSingleEntry2` at `0x1401be8f7`
- `watchdog!WdLogSingleEntry2` at `0x1401be940`
- `watchdog!WdLogSingleEntry2` at `0x1401bea96`
- `watchdog!WdLogSingleEntry3` at `0x1401bde9d`
- `watchdog!WdLogSingleEntry3` at `0x1401bdfe8`
- `watchdog!WdLogSingleEntry3` at `0x1401be1a3`
- `watchdog!WdLogSingleEntry3` at `0x1401be349`
- `watchdog!WdLogSingleEntry3` at `0x1401be48a`
- `watchdog!WdLogSingleEntry3` at `0x1401be7ea`
- `watchdog!WdLogSingleEntry3` at `0x1401be868`
- `watchdog!WdLogSingleEntry3` at `0x1401be897`
- `watchdog!WdLogSingleEntry3` at `0x1401be8c9`
- `watchdog!WdLogSingleEntry3` at `0x1401be9f7`
- `watchdog!WdLogSingleEntry3` at `0x1401bde9d`
- `watchdog!WdLogSingleEntry3` at `0x1401bdfe8`
- `watchdog!WdLogSingleEntry3` at `0x1401be1a3`
- `watchdog!WdLogSingleEntry3` at `0x1401be349`
- `watchdog!WdLogSingleEntry3` at `0x1401be48a`
- `watchdog!WdLogSingleEntry3` at `0x1401be7ea`
- `watchdog!WdLogSingleEntry3` at `0x1401be868`
- `watchdog!WdLogSingleEntry3` at `0x1401be897`
- `watchdog!WdLogSingleEntry3` at `0x1401be8c9`
- `watchdog!WdLogSingleEntry3` at `0x1401be9f7`
- `watchdog!WdLogSingleEntry0` at `0x1401beb19`
- `watchdog!WdLogSingleEntry0` at `0x1401beb19`
- `watchdog!WdLogSingleEntry1` at `0x1401be0fe`
- `watchdog!WdLogSingleEntry1` at `0x1401bebcf`
- `watchdog!WdLogSingleEntry1` at `0x1401be0fe`
- `watchdog!WdLogSingleEntry1` at `0x1401bebcf`

## string_xrefs

- `0x1401be8a3`: `Failed to pin D3DKMDT_VPPS_IDENTITY on path from source 0x%I64x to target 0x%I64x (Status = 0x%I64x).`
- `0x1401be874`: `Failed to acquire path info on path from source 0x%I64x to target 0x%I64x (Status = 0x%I64x).`
- `0x1401be8d5`: `Failed to acquire VidPn path info from source 0x%I64x to target 0x%I64x (Status = 0x%I64x).`
- `0x1401be7f6`: `Unable to unpin content scaling on path from source 0x%I64x to target 0x%I64x (Status = 0x%I64x).`
- `0x1401be0ac`: `Failed to Add VidPn path from source 0x%I64x to target 0x%I64x on VidPn 0x%I64x (Status=0x%I64x).`
- `0x1401bdf83`: `Failed call to create an empty VidPN on adapter 0x%I64x (status = 0x%I64x).`

## pseudocode

```c
__int64 __fastcall OBTAIN_PREFERRED_MODES_ON_PATH::operator()(
        _QWORD *a1,
        struct _D3DKMT_DISPLAYMODE **a2,
        unsigned int *a3)
{
  int PreferredMonitorSourceModeOnTarget; // eax
  DXGADAPTER *v5; // rcx
  int DmmInterface; // eax
  __int64 v7; // rsi
  const wchar_t *v8; // r9
  __int64 v10; // rbx
  void *v11; // rcx
  __int64 (__fastcall *v12)(void *, __int64 *, __int64 *); // rax
  int v13; // eax
  __int64 v14; // rsi
  int v15; // eax
  __int64 v16; // r14
  int v17; // eax
  unsigned int v18; // edx
  void *v19; // rcx
  int VideoOutputTechnology; // eax
  __int64 v21; // rdx
  __int64 (__fastcall *v22)(__int64, __int64, __int64 *, __int64 *); // rax
  int v23; // eax
  __int64 v24; // r15
  __int64 (__fastcall *v25)(__int64, __int64 *); // rax
  int v26; // eax
  __int64 v27; // r8
  unsigned int *v28; // r14
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // edx
  int v32; // eax
  __int64 v33; // rdx
  __int64 (__fastcall *v34)(__int64, __int64, __int64 *, __int64 *); // rax
  int v35; // eax
  __int64 v36; // r12
  __int64 v37; // r12
  __int64 (__fastcall *v38)(__int64, enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *); // rax
  int v39; // eax
  __int64 v40; // r8
  unsigned int *v41; // rbx
  __int64 v42; // r8
  int v43; // eax
  __int64 v44; // r8
  __int64 v45; // rdx
  int v46; // eax
  struct _D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT v47; // ebx
  int v48; // eax
  __int64 v49; // r8
  __int64 v50; // rdx
  int v51; // eax
  struct _D3DKMDT_VIDPN_PRESENT_PATH_ROTATION_SUPPORT v52; // ebx
  enum _D3DKMDT_VIDPN_PRESENT_PATH_ROTATION i; // eax
  int v54; // eax
  int v55; // eax
  __int64 v56; // rbx
  int v57; // eax
  int v58; // eax
  bool v59; // zf
  __int64 v60; // rbx
  const wchar_t *v61; // r9
  __int64 v62; // rbx
  __int64 v63; // rbx
  unsigned int v64; // eax
  __int64 v65; // rax
  unsigned __int64 v66; // kr00_8
  struct _D3DKMT_DISPLAYMODE *v67; // rax
  int UniqueModes; // eax
  __int64 v69; // rbx
  int v70; // [rsp+20h] [rbp-E0h]
  char v71; // [rsp+50h] [rbp-B0h]
  char v72; // [rsp+51h] [rbp-AFh] BYREF
  char v73[6]; // [rsp+52h] [rbp-AEh] BYREF
  __int64 v74; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v75; // [rsp+60h] [rbp-A0h] BYREF
  enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY v76[2]; // [rsp+68h] [rbp-98h] BYREF
  char v77[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v78; // [rsp+78h] [rbp-88h]
  void (__fastcall *v79)(__int64, __int64); // [rsp+80h] [rbp-80h]
  __int64 v80; // [rsp+88h] [rbp-78h]
  int v81; // [rsp+90h] [rbp-70h]
  char v82[8]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v83; // [rsp+A0h] [rbp-60h]
  void (__fastcall *v84)(__int64, __int64); // [rsp+A8h] [rbp-58h]
  __int64 v85; // [rsp+B0h] [rbp-50h]
  int v86; // [rsp+B8h] [rbp-48h]
  char v87[8]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int *v88; // [rsp+C8h] [rbp-38h]
  void (__fastcall *v89)(__int64, unsigned int *); // [rsp+D0h] [rbp-30h]
  __int64 v90; // [rsp+D8h] [rbp-28h]
  int v91; // [rsp+E0h] [rbp-20h]
  char v92[8]; // [rsp+E8h] [rbp-18h] BYREF
  unsigned int *v93; // [rsp+F0h] [rbp-10h]
  void (__fastcall *v94)(__int64, unsigned int *); // [rsp+F8h] [rbp-8h]
  __int64 v95; // [rsp+100h] [rbp+0h]
  int v96; // [rsp+108h] [rbp+8h]
  __int64 v97; // [rsp+110h] [rbp+10h] BYREF
  __int64 v98; // [rsp+118h] [rbp+18h] BYREF
  char v99[8]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v100; // [rsp+128h] [rbp+28h]
  void (__fastcall *v101)(__int64, __int64); // [rsp+130h] [rbp+30h]
  __int64 v102; // [rsp+138h] [rbp+38h]
  int v103; // [rsp+140h] [rbp+40h]
  __int64 v104; // [rsp+148h] [rbp+48h] BYREF
  __int64 v105; // [rsp+150h] [rbp+50h] BYREF
  unsigned int *v106; // [rsp+158h] [rbp+58h]
  struct _D3DKMT_DISPLAYMODE **v107; // [rsp+160h] [rbp+60h]
  struct _D3DKMT_DISPLAYMODE v108; // [rsp+168h] [rbp+68h] BYREF
  struct _D3DKMDT_MONITOR_SOURCE_MODE v109; // [rsp+1A0h] [rbp+A0h] BYREF

  v107 = a2;
  v106 = a3;
  memset(&v109, 0, sizeof(v109));
  PreferredMonitorSourceModeOnTarget = DmmGetPreferredMonitorSourceModeOnTarget((void *)*a1, *((_DWORD *)a1 + 3), &v109);
  if ( PreferredMonitorSourceModeOnTarget < 0 )
  {
    WdLogSingleEntry3(3, *a1, *((unsigned int *)a1 + 3), PreferredMonitorSourceModeOnTarget);
    WdLogGlobalForLineNumber = 1356;
    return 0;
  }
  v5 = (DXGADAPTER *)*a1;
  v75 = 0;
  DmmInterface = DxgkQueryDmmInterface(v5);
  v7 = DmmInterface;
  if ( DmmInterface < 0 )
  {
    WdLogSingleEntry2(2, *a1);
    v8 = L"Failed to QueryDxgDmmInterface on hAdapter 0x%I64x (status = 0x%I64x).";
    WdLogGlobalForLineNumber = 1368;
LABEL_5:
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v8, *a1, v7, 0, 0, 0);
    return (unsigned int)v7;
  }
  v10 = v75;
  v11 = (void *)*a1;
  v104 = 0;
  v74 = 0;
  v12 = *(__int64 (__fastcall **)(void *, __int64 *, __int64 *))(v75 + 40);
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v77[0] = 0;
  v13 = v12(v11, &v74, &v104);
  v7 = v13;
  if ( v13 < 0 )
  {
    WdLogSingleEntry2(2, *a1);
    v8 = L"Failed call to create an empty VidPN on adapter 0x%I64x (status = 0x%I64x).";
    WdLogGlobalForLineNumber = 1387;
    goto LABEL_5;
  }
  DXGDMM::AutoRelease<_D3DKMDT_VIDPN_PRESENT_PATH const *,long (*)(D3DKMDT_HVIDPNTOPOLOGY__ *,_D3DKMDT_VIDPN_PRESENT_PATH const *),D3DKMDT_HVIDPNTOPOLOGY__ *>::Own(
    v77,
    v74,
    *(_QWORD *)(v10 + 64),
    *a1);
  v14 = v78;
  v98 = 0;
  v97 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *))v104)(v78, &v98, &v97);
  v16 = v15;
  if ( v15 >= 0 )
  {
    v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, _WORD, int))(v97 + 40))(
            v98,
            *((unsigned int *)a1 + 2),
            *((unsigned int *)a1 + 3),
            1,
            0,
            2);
    v18 = *((_DWORD *)a1 + 3);
    v16 = v17;
    if ( v17 >= 0 )
    {
      v19 = (void *)*a1;
      v76[0] = D3DKMDT_VOT_HD15;
      VideoOutputTechnology = DmmGetVideoOutputTechnology(v19, v18, 0, v76);
      v16 = VideoOutputTechnology;
      if ( VideoOutputTechnology >= 0 )
      {
        if ( v76[0] == D3DKMDT_VOT_MIRACAST
          || v76[0] == D3DKMDT_VOT_INDIRECT_WIRED
          || (v71 = 0, v76[0] == (D3DKMDT_VOT_SVIDEO_7PIN|D3DKMDT_VOT_INDIRECT_WIRED)) )
        {
          v71 = 1;
        }
        v21 = *((unsigned int *)a1 + 2);
        v105 = 0;
        v75 = 0;
        v22 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *, __int64 *))(v104 + 8);
        v83 = 0;
        v84 = 0;
        v85 = 0;
        v86 = 0;
        v82[0] = 0;
        v23 = v22(v14, v21, &v75, &v105);
        v16 = v23;
        if ( v23 >= 0 )
        {
          DXGDMM::AutoRelease<_D3DKMDT_VIDPN_PRESENT_PATH const *,long (*)(D3DKMDT_HVIDPNTOPOLOGY__ *,_D3DKMDT_VIDPN_PRESENT_PATH const *),D3DKMDT_HVIDPNTOPOLOGY__ *>::Own(
            v82,
            v75,
            *(_QWORD *)(v104 + 16),
            v14);
          v24 = v83;
          v75 = 0;
          v88 = 0;
          v25 = *(__int64 (__fastcall **)(__int64, __int64 *))(v105 + 8);
          v89 = 0;
          v90 = 0;
          v91 = 0;
          v87[0] = 0;
          v26 = v25(v83, &v75);
          v16 = v26;
          if ( v26 >= 0 )
          {
            DXGDMM::AutoRelease<_D3DKMDT_VIDPN_PRESENT_PATH const *,long (*)(D3DKMDT_HVIDPNTOPOLOGY__ *,_D3DKMDT_VIDPN_PRESENT_PATH const *),D3DKMDT_HVIDPNTOPOLOGY__ *>::Own(
              v87,
              v75,
              *(_QWORD *)(v105 + 32),
              v24);
            while ( 1 )
            {
              v28 = v88;
              if ( !v88 )
                break;
              v29 = v88[1];
              if ( ((v29 - 1) & 0xFFFFFFFC) == 0 && v29 != 2 )
              {
                v30 = v88[2];
                if ( v30 == v88[4] )
                {
                  v31 = v88[3];
                  if ( v31 == v88[5]
                    && v88[7] - 21 <= 1
                    && v30 == v109.VideoSignalInfo.ActiveSize.cx
                    && v31 == v109.VideoSignalInfo.ActiveSize.cy )
                  {
                    LOBYTE(v27) = 1;
                    v32 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(v105 + 40))(v24, *v88, v27);
                    if ( v32 >= 0 )
                    {
                      v33 = *((unsigned int *)a1 + 3);
                      v75 = 0;
                      v74 = 0;
                      v34 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *, __int64 *))(v104 + 24);
                      v100 = 0;
                      v101 = 0;
                      v102 = 0;
                      v103 = 0;
                      v99[0] = 0;
                      v35 = v34(v14, v33, &v74, &v75);
                      v36 = v35;
                      if ( v35 < 0 )
                      {
                        WdLogSingleEntry3(2, v14, *((unsigned int *)a1 + 3), v35);
                        WdLogGlobalForLineNumber = 1561;
                        DxgkLogInternalTriageEvent(
                          0,
                          0x40000,
                          -1,
                          (unsigned int)L"Failed to acquire target mode set from VidPn 0x%I64x for Target 0x%I64x (Status = 0x%I64x).",
                          v14,
                          *((unsigned int *)a1 + 3),
                          v36,
                          0,
                          0);
LABEL_96:
                        if ( v87[0] )
                          v89(v90, v28);
                        if ( v82[0] )
                          v84(v85, v24);
                        if ( v77[0] )
                          v79(v80, v14);
                        return (unsigned int)v36;
                      }
                      DXGDMM::AutoRelease<D3DKMDT_HVIDPNTARGETMODESET__ *,long (*)(D3DKMDT_HVIDPN__ *,D3DKMDT_HVIDPNTARGETMODESET__ *),D3DKMDT_HVIDPN__ *>::Own(
                        v99,
                        v74,
                        *(_QWORD *)(v104 + 32),
                        v14);
                      v37 = v100;
                      *(_QWORD *)v76 = 0;
                      v93 = 0;
                      v38 = *(__int64 (__fastcall **)(__int64, enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *))(v75 + 8);
                      v94 = 0;
                      v95 = 0;
                      v96 = 0;
                      v92[0] = 0;
                      v39 = v38(v100, v76);
                      LODWORD(v74) = v39;
                      if ( v39 < 0 )
                      {
                        v63 = v39;
                        WdLogSingleEntry2(2, v37);
                        WdLogGlobalForLineNumber = 1582;
                        DxgkLogInternalTriageEvent(
                          0,
                          0x40000,
                          -1,
                          (unsigned int)L"Failed to acquire first target mode info from target mode set 0x%I64x (Status = 0x%I64x).",
                          v37,
                          v63,
                          0,
                          0,
                          0);
LABEL_85:
                        if ( v99[0] )
                          v101(v102, v37);
                        if ( v87[0] )
                          v89(v90, v28);
                        if ( v82[0] )
                          v84(v85, v24);
                        v59 = v77[0] == 0;
LABEL_92:
                        if ( !v59 )
                          v79(v80, v14);
                        return (unsigned int)v74;
                      }
                      while ( 1 )
                      {
                        DXGDMM::AutoRelease<_D3DKMDT_VIDPN_PRESENT_PATH const *,long (*)(D3DKMDT_HVIDPNTOPOLOGY__ *,_D3DKMDT_VIDPN_PRESENT_PATH const *),D3DKMDT_HVIDPNTOPOLOGY__ *>::Own(
                          v92,
                          *(_QWORD *)v76,
                          *(_QWORD *)(v75 + 32),
                          v37);
                        v41 = v93;
                        if ( !v93 )
                          break;
                        LOBYTE(v40) = v71;
                        v72 = 0;
                        if ( (*(int (__fastcall **)(unsigned int *, struct _D3DKMDT_MONITOR_SOURCE_MODE *, __int64, char *))(v75 + 80))(
                               v93,
                               &v109,
                               v40,
                               &v72) >= 0
                          && v72 )
                        {
                          LOBYTE(v42) = 1;
                          v43 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(v75 + 48))(v37, *v41, v42);
                          if ( v43 >= 0 )
                          {
                            v44 = *((unsigned int *)a1 + 3);
                            v45 = *((unsigned int *)a1 + 2);
                            *(_QWORD *)v76 = 0;
                            v46 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *))(v97 + 24))(
                                    v98,
                                    v45,
                                    v44,
                                    v76);
                            LODWORD(v74) = v46;
                            if ( v46 < 0 )
                            {
                              v60 = v46;
                              WdLogSingleEntry3(2, *((unsigned int *)a1 + 2), *((unsigned int *)a1 + 3), v46);
                              v61 = L"Failed to acquire VidPn path info from source 0x%I64x to target 0x%I64x (Status = 0x%I64x).";
                              WdLogGlobalForLineNumber = 1632;
                              goto LABEL_77;
                            }
                            v47 = *(struct _D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT *)(*(_QWORD *)v76 + 16LL);
                            (*(void (__fastcall **)(__int64))(v97 + 32))(v98);
                            if ( BmlIsSupportedPathScaling(D3DKMDT_VPPS_IDENTITY, v47) )
                            {
                              LOBYTE(v70) = 1;
                              v48 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, int))(v97 + 64))(
                                      v98,
                                      *((unsigned int *)a1 + 2),
                                      *((unsigned int *)a1 + 3),
                                      1,
                                      v70);
                              LODWORD(v74) = v48;
                              if ( v48 < 0 )
                              {
                                v60 = v48;
                                WdLogSingleEntry3(2, *((unsigned int *)a1 + 2), *((unsigned int *)a1 + 3), v48);
                                v61 = L"Failed to pin D3DKMDT_VPPS_IDENTITY on path from source 0x%I64x to target 0x%I64x "
                                       "(Status = 0x%I64x).";
                                WdLogGlobalForLineNumber = 1657;
                              }
                              else
                              {
                                v49 = *((unsigned int *)a1 + 3);
                                v50 = *((unsigned int *)a1 + 2);
                                *(_QWORD *)v76 = 0;
                                v51 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *))(v97 + 24))(
                                        v98,
                                        v50,
                                        v49,
                                        v76);
                                LODWORD(v74) = v51;
                                if ( v51 < 0 )
                                {
                                  v60 = v51;
                                  WdLogSingleEntry3(2, *((unsigned int *)a1 + 2), *((unsigned int *)a1 + 3), v51);
                                  v61 = L"Failed to acquire path info on path from source 0x%I64x to target 0x%I64x (Status = 0x%I64x).";
                                  WdLogGlobalForLineNumber = 1674;
                                }
                                else
                                {
                                  v52 = *(struct _D3DKMDT_VIDPN_PRESENT_PATH_ROTATION_SUPPORT *)(*(_QWORD *)v76 + 24LL);
                                  (*(void (__fastcall **)(__int64))(v97 + 32))(v98);
                                  for ( i = D3DKMDT_VPPR_IDENTITY; ; i = v76[0] + 1 )
                                  {
                                    v76[0] = i;
                                    if ( i > D3DKMDT_VPPR_ROTATE270 )
                                      break;
                                    if ( BmlIsSupportedPathRotation(i, v52) )
                                    {
                                      v73[0] = 0;
                                      memset(&v108, 0, sizeof(v108));
                                      PopulateDisplayModeFromPresentPath(
                                        (_DWORD)v28,
                                        (_DWORD)v93,
                                        1,
                                        v76[0],
                                        1,
                                        1,
                                        0,
                                        2,
                                        (__int64)&v108,
                                        (__int64)v73);
                                      LODWORD(v74) = MODE_UNION_LIST::AddUniqueMode((MODE_UNION_LIST *)(a1 + 3), &v108);
                                      if ( (int)v74 < 0
                                        || v73[0]
                                        && (++v108.IntegerRefreshRate,
                                            *(_DWORD *)&v108.Flags |= 2u,
                                            LODWORD(v74) = MODE_UNION_LIST::AddUniqueMode(
                                                             (MODE_UNION_LIST *)(a1 + 3),
                                                             &v108),
                                            (int)v74 < 0) )
                                      {
                                        if ( v92[0] )
                                          v94(v95, v93);
                                        if ( v99[0] )
                                          v101(v102, v37);
                                        if ( v87[0] )
                                          v89(v90, v28);
                                        if ( v82[0] )
                                          v84(v85, v24);
                                        v59 = v77[0] == 0;
                                        goto LABEL_92;
                                      }
                                    }
                                  }
                                  v54 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(v97 + 72))(
                                          v98,
                                          *((unsigned int *)a1 + 2),
                                          *((unsigned int *)a1 + 3),
                                          0);
                                  LODWORD(v74) = v54;
                                  if ( v54 >= 0 )
                                    goto LABEL_57;
                                  v60 = v54;
                                  WdLogSingleEntry3(2, *((unsigned int *)a1 + 2), *((unsigned int *)a1 + 3), v54);
                                  v61 = L"Unable to unpin content scaling on path from source 0x%I64x to target 0x%I64x (S"
                                         "tatus = 0x%I64x).";
                                  WdLogGlobalForLineNumber = 1773;
                                }
                              }
LABEL_77:
                              DxgkLogInternalTriageEvent(
                                0,
                                0x40000,
                                -1,
                                (_DWORD)v61,
                                *((unsigned int *)a1 + 2),
                                *((unsigned int *)a1 + 3),
                                v60,
                                0,
                                0);
LABEL_78:
                              if ( v92[0] )
                                v94(v95, v93);
                              goto LABEL_85;
                            }
LABEL_57:
                            v41 = v93;
                          }
                          else
                          {
                            WdLogSingleEntry3(3, *v41, v37, v43);
                            WdLogGlobalForLineNumber = 1615;
                          }
                        }
                        *(_QWORD *)v76 = 0;
                        v55 = (*(__int64 (__fastcall **)(__int64, unsigned int *, enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *))(v75 + 16))(
                                v37,
                                v41,
                                v76);
                        LODWORD(v74) = v55;
                        if ( v55 < 0 )
                        {
                          v56 = v55;
                          WdLogSingleEntry2(2, v37);
                          WdLogGlobalForLineNumber = 1788;
                          DxgkLogInternalTriageEvent(
                            0,
                            0x40000,
                            -1,
                            (unsigned int)L"Failed to acquire next target mode info on target mode set 0x%I64x (Status = 0x%I64x).",
                            v37,
                            v56,
                            0,
                            0,
                            0);
                          goto LABEL_78;
                        }
                      }
                      v57 = (*(__int64 (__fastcall **)(__int64, _QWORD))(v75 + 56))(v37, 0);
                      LODWORD(v74) = v57;
                      if ( v57 < 0 )
                      {
                        v62 = v57;
                        WdLogSingleEntry2(2, v37);
                        WdLogGlobalForLineNumber = 1805;
                        DxgkLogInternalTriageEvent(
                          0,
                          0x40000,
                          -1,
                          (unsigned int)L"Failed to Dunpin target mode set 0x%I64x (Status = 0x%I64x).",
                          v37,
                          v62,
                          0,
                          0,
                          0);
                        goto LABEL_78;
                      }
                      if ( v92[0] )
                        v94(v95, 0);
                      if ( v99[0] )
                        v101(v102, v37);
                    }
                    else
                    {
                      WdLogSingleEntry3(3, *v28, v24, v32);
                      WdLogGlobalForLineNumber = 1540;
                    }
                  }
                }
              }
              v75 = 0;
              v58 = (*(__int64 (__fastcall **)(__int64, unsigned int *, __int64 *))(v105 + 16))(v24, v28, &v75);
              v36 = v58;
              if ( v58 < 0 )
              {
                WdLogSingleEntry2(2, v24);
                WdLogGlobalForLineNumber = 1821;
                DxgkLogInternalTriageEvent(
                  0,
                  0x40000,
                  -1,
                  (unsigned int)L"Failed to acquire next source mode info from source mode set 0x%I64x (Status = 0x%I64x).",
                  v24,
                  v36,
                  0,
                  0,
                  0);
                goto LABEL_96;
              }
              DXGDMM::AutoRelease<_D3DKMDT_VIDPN_PRESENT_PATH const *,long (*)(D3DKMDT_HVIDPNTOPOLOGY__ *,_D3DKMDT_VIDPN_PRESENT_PATH const *),D3DKMDT_HVIDPNTOPOLOGY__ *>::Own(
                v87,
                v75,
                *(_QWORD *)(v105 + 32),
                v24);
            }
            v64 = *((_DWORD *)a1 + 10);
            if ( v64 )
            {
              v66 = v64;
              v65 = 44LL * v64;
              if ( !is_mul_ok(v66, 0x2Cu) )
                v65 = -1;
              v67 = (struct _D3DKMT_DISPLAYMODE *)operator new[](v65, 1265072196, 256);
              *v107 = v67;
              if ( !v67 )
              {
                WdLogSingleEntry0(6);
                WdLogGlobalForLineNumber = 1837;
                DxgkLogInternalTriageEvent(
                  0,
                  262145,
                  -1,
                  (unsigned int)L"Unable to allocate mode list memory.",
                  1837,
                  0,
                  0,
                  0,
                  0);
                if ( v87[0] )
                  v89(v90, 0);
                if ( v82[0] )
                  v84(v85, v24);
                if ( v77[0] )
                  v79(v80, v14);
                return 3221225495LL;
              }
              UniqueModes = MODE_UNION_LIST::GetUniqueModes(
                              (MODE_UNION_LIST *)(a1 + 3),
                              *((unsigned int *)a1 + 10),
                              v67,
                              v106);
              if ( UniqueModes < 0 )
              {
                v69 = UniqueModes;
                WdLogSingleEntry1(1);
                WdLogGlobalForLineNumber = 1847;
                DxgkLogInternalTriageEvent(
                  0,
                  262146,
                  -1,
                  (unsigned int)L"Failed to get unique modes (Status = 0x%I64x).",
                  v69,
                  0,
                  0,
                  0,
                  0);
              }
            }
            else
            {
              *v106 = 0;
            }
            if ( v87[0] )
              v89(v90, 0);
            if ( v82[0] )
              v84(v85, v24);
            if ( v77[0] )
              v79(v80, v14);
            return 0;
          }
          WdLogSingleEntry2(2, v24);
          WdLogGlobalForLineNumber = 1484;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Failed to acquire first mode info from source mode set 0x%I64x (Status = 0x%I64x).",
            v24,
            v16,
            0,
            0,
            0);
          if ( v82[0] )
            v84(v85, v24);
        }
        else
        {
          WdLogSingleEntry3(2, v14, *((unsigned int *)a1 + 2), v23);
          WdLogGlobalForLineNumber = 1463;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Failed to acquire VidPn source mode set from VidPn 0x%I64x for VidPn source ID 0x%I64x (Status = 0x%I64x).",
            v14,
            *((unsigned int *)a1 + 2),
            v16,
            0,
            0);
        }
      }
      else
      {
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 1441;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Failed call to DmmGetVideoOutputTechnology(Status = 0x%I64x)",
          v16,
          0,
          0,
          0,
          0);
      }
    }
    else
    {
      WdLogSingleEntry4(2, *((unsigned int *)a1 + 2), v18, v14, v17);
      WdLogGlobalForLineNumber = 1429;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Failed to Add VidPn path from source 0x%I64x to target 0x%I64x on VidPn 0x%I64x (Status=0x%I64x).",
        *((unsigned int *)a1 + 2),
        *((unsigned int *)a1 + 3),
        v14,
        v16,
        0);
    }
  }
  else
  {
    WdLogSingleEntry3(2, v14, *a1, v15);
    WdLogGlobalForLineNumber = 1410;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Failed to get VidPn topology from hVidPn 0x%I64x on Adapter 0x%I64x (Status=0x%I64x).",
      v14,
      *a1,
      v16,
      0,
      0);
  }
  if ( v77[0] )
    v79(v80, v14);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1401bde28  mov     [rsp-8+arg_18], rbx
0x1401bde2d  push    rbp
0x1401bde2e  push    rsi
0x1401bde2f  push    rdi
0x1401bde30  push    r12
0x1401bde32  push    r13
0x1401bde34  push    r14
0x1401bde36  push    r15
0x1401bde38  lea     rbp, [rsp-110h]
0x1401bde40  sub     rsp, 210h
0x1401bde47  mov     rax, cs:__security_cookie
0x1401bde4e  xor     rax, rsp
0x1401bde51  mov     [rbp+140h+var_40], rax
0x1401bde58  mov     [rbp+140h+var_E0], rdx
0x1401bde5c  mov     rdi, rcx
0x1401bde5f  xor     edx, edx; Val
0x1401bde61  mov     [rbp+140h+var_E8], r8
0x1401bde65  lea     rcx, [rbp+140h+var_A0]; void *
0x1401bde6c  lea     r8d, [rdx+60h]; Size
0x1401bde70  call    memset
0x1401bde75  mov     edx, [rdi+0Ch]; unsigned int
0x1401bde78  lea     r8, [rbp+140h+var_A0]; struct _D3DKMDT_MONITOR_SOURCE_MODE *
0x1401bde7f  mov     rcx, [rdi]; void *
0x1401bde82  call    ?DmmGetPreferredMonitorSourceModeOnTarget@@YAJPEAXIPEAU_D3DKMDT_MONITOR_SOURCE_MODE@@@Z; DmmGetPreferredMonitorSourceModeOnTarget(void *,uint,_D3DKMDT_MONITOR_SOURCE_MODE *)
0x1401bde87  xor     r12d, r12d
0x1401bde8a  test    eax, eax
0x1401bde8c  jns     short loc_1401BDEB8
0x1401bde8e  mov     r8d, [rdi+0Ch]
0x1401bde92  lea     ecx, [r12+3]
0x1401bde97  mov     rdx, [rdi]
0x1401bde9a  movsxd  r9, eax
0x1401bde9d  call    cs:__imp_WdLogSingleEntry3
0x1401bdea4  nop     dword ptr [rax+rax+00h]
0x1401bdea9  mov     cs:WdLogGlobalForLineNumber, 54Ch
0x1401bdeb3  jmp     loc_1401BEC61
0x1401bdeb8  mov     rcx, [rdi]; this
0x1401bdebb  lea     r8, [rsp+240h+var_1E0]
0x1401bdec0  mov     [rsp+240h+var_1E0], r12
0x1401bdec5  call    DxgkQueryDmmInterface
0x1401bdeca  movsxd  rsi, eax
0x1401bdecd  test    eax, eax
0x1401bdecf  jns     short loc_1401BDF2C
0x1401bded1  mov     rdx, [rdi]
0x1401bded4  mov     r8, rsi
0x1401bded7  mov     ecx, 2
0x1401bdedc  call    cs:__imp_WdLogSingleEntry2
0x1401bdee3  nop     dword ptr [rax+rax+00h]
0x1401bdee8  lea     r9, aFailedToQueryd; "Failed to QueryDxgDmmInterface on hAdap"...
0x1401bdeef  mov     cs:WdLogGlobalForLineNumber, 558h
0x1401bdef9  mov     rax, [rdi]
0x1401bdefc  or      r8d, 0FFFFFFFFh
0x1401bdf00  mov     [rsp+240h+var_200], r12
0x1401bdf05  mov     edx, 40000h
0x1401bdf0a  mov     [rsp+240h+var_208], r12
0x1401bdf0f  xor     ecx, ecx
0x1401bdf11  mov     [rsp+240h+var_210], r12
0x1401bdf16  mov     [rsp+240h+var_218], rsi
0x1401bdf1b  mov     [rsp+240h+var_220], rax
0x1401bdf20  call    DxgkLogInternalTriageEvent
0x1401bdf25  mov     eax, esi
0x1401bdf27  jmp     loc_1401BEC63
0x1401bdf2c  mov     rbx, [rsp+240h+var_1E0]
0x1401bdf31  lea     r8, [rbp+140h+var_F8]
0x1401bdf35  mov     rcx, [rdi]
0x1401bdf38  lea     rdx, [rsp+240h+var_1E8]
0x1401bdf3d  mov     [rbp+140h+var_F8], r12
0x1401bdf41  mov     [rsp+240h+var_1E8], r12
0x1401bdf46  mov     rax, [rbx+28h]
0x1401bdf4a  mov     [rsp+240h+var_1C8], r12
0x1401bdf4f  mov     [rbp+140h+var_1C0], r12
0x1401bdf53  mov     [rbp+140h+var_1B8], r12
0x1401bdf57  mov     [rbp+140h+var_1B0], r12d
0x1401bdf5b  mov     [rsp+240h+var_1D0], r12b
0x1401bdf60  call    _guard_dispatch_icall
0x1401bdf65  movsxd  rsi, eax
0x1401bdf68  test    eax, eax
0x1401bdf6a  jns     short loc_1401BDF99
0x1401bdf6c  mov     rdx, [rdi]
0x1401bdf6f  mov     r8, rsi
0x1401bdf72  mov     ecx, 2
0x1401bdf77  call    cs:__imp_WdLogSingleEntry2
0x1401bdf7e  nop     dword ptr [rax+rax+00h]
0x1401bdf83  lea     r9, aFailedCallToCr; "Failed call to create an empty VidPN on"...
0x1401bdf8a  mov     cs:WdLogGlobalForLineNumber, 56Bh
0x1401bdf94  jmp     loc_1401BDEF9
0x1401bdf99  mov     r9, [rdi]
0x1401bdf9c  lea     rcx, [rsp+240h+var_1D0]
0x1401bdfa1  mov     r8, [rbx+40h]
0x1401bdfa5  mov     rdx, [rsp+240h+var_1E8]
0x1401bdfaa  call    ?Own@?$AutoRelease@PEBU_D3DKMDT_VIDPN_PRESENT_PATH@@P6AJPEAUD3DKMDT_HVIDPNTOPOLOGY__@@PEBU1@@ZPEAU2@@DXGDMM@@QEAAXPEBU_D3DKMDT_VIDPN_PRESENT_PATH@@Q6AJPEAUD3DKMDT_HVIDPNTOPOLOGY__@@0@Z1@Z; DXGDMM::AutoRelease<_D3DKMDT_VIDPN_PRESENT_PATH const *,long (*)(D3DKMDT_HVIDPNTOPOLOGY__ *,_D3DKMDT_VIDPN_PRESENT_PATH const *),D3DKMDT_HVIDPNTOPOLOGY__ *>::Own(_D3DKMDT_VIDPN_PRESENT_PATH const *,long (*const)(D3DKMDT_HVIDPNTOPOLOGY__ *,_D3DKMDT_VIDPN_PRESENT_PATH const *),D3DKMDT_HVIDPNTOPOLOGY__ *)
0x1401bdfaf  mov     rax, [rbp+140h+var_F8]
0x1401bdfb3  lea     r8, [rbp+140h+var_130]
0x1401bdfb7  mov     rsi, [rsp+240h+var_1C8]
0x1401bdfbc  lea     rdx, [rbp+140h+var_128]
0x1401bdfc0  mov     [rbp+140h+var_128], r12
0x1401bdfc4  mov     rcx, rsi
0x1401bdfc7  mov     [rbp+140h+var_130], r12
0x1401bdfcb  mov     rax, [rax]
0x1401bdfce  call    _guard_dispatch_icall
0x1401bdfd3  movsxd  r14, eax
0x1401bdfd6  test    eax, eax
0x1401bdfd8  jns     short loc_1401BE050
0x1401bdfda  mov     r8, [rdi]
0x1401bdfdd  mov     r9, r14
0x1401bdfe0  mov     rdx, rsi
0x1401bdfe3  mov     ecx, 2
0x1401bdfe8  call    cs:__imp_WdLogSingleEntry3
0x1401bdfef  nop     dword ptr [rax+rax+00h]
0x1401bdff4  mov     [rsp+240h+var_200], r12
0x1401bdff9  lea     r9, aFailedToGetVid; "Failed to get VidPn topology from hVidP"...
0x1401be000  mov     [rsp+240h+var_208], r12
0x1401be005  mov     cs:WdLogGlobalForLineNumber, 582h
0x1401be00f  mov     rax, [rdi]
0x1401be012  mov     [rsp+240h+var_210], r14
0x1401be017  mov     [rsp+240h+var_218], rax
0x1401be01c  mov     [rsp+240h+var_220], rsi
0x1401be021  or      r8d, 0FFFFFFFFh
0x1401be025  mov     edx, 40000h
0x1401be02a  xor     ecx, ecx
0x1401be02c  call    DxgkLogInternalTriageEvent
0x1401be031  cmp     [rsp+240h+var_1D0], r12b
0x1401be036  jz      short loc_1401BE048
0x1401be038  mov     rcx, [rbp+140h+var_1B8]
0x1401be03c  mov     rdx, rsi
0x1401be03f  mov     rax, [rbp+140h+var_1C0]
0x1401be043  call    _guard_dispatch_icall
0x1401be048  mov     eax, r14d
0x1401be04b  jmp     loc_1401BEC63
0x1401be050  mov     rax, [rbp+140h+var_130]
0x1401be054  mov     r13d, 2
0x1401be05a  mov     r8d, [rdi+0Ch]
0x1401be05e  mov     edx, [rdi+8]
0x1401be061  mov     rcx, [rbp+140h+var_128]
0x1401be065  mov     rax, [rax+28h]
0x1401be069  lea     r9d, [r13-1]
0x1401be06d  mov     dword ptr [rsp+240h+var_218], r13d
0x1401be072  mov     word ptr [rsp+240h+var_220], r12w
0x1401be078  call    _guard_dispatch_icall
0x1401be07d  mov     edx, [rdi+0Ch]; unsigned int
0x1401be080  movsxd  r14, eax
0x1401be083  test    eax, eax
0x1401be085  jns     short loc_1401BE0DC
0x1401be087  mov     r8d, edx
0x1401be08a  mov     rbx, r14
0x1401be08d  mov     edx, [rdi+8]
0x1401be090  mov     r9, rsi
0x1401be093  mov     ecx, r13d
0x1401be096  mov     [rsp+240h+var_220], rbx
0x1401be09b  call    cs:__imp_WdLogSingleEntry4
0x1401be0a2  nop     dword ptr [rax+rax+00h]
0x1401be0a7  mov     [rsp+240h+var_200], r12
0x1401be0ac  lea     r9, aFailedToAddVid; "Failed to Add VidPn path from source 0x"...
0x1401be0b3  mov     [rsp+240h+var_208], rbx
0x1401be0b8  mov     cs:WdLogGlobalForLineNumber, 595h
0x1401be0c2  mov     ecx, [rdi+0Ch]
0x1401be0c5  mov     eax, [rdi+8]
0x1401be0c8  mov     [rsp+240h+var_210], rsi
0x1401be0cd  mov     [rsp+240h+var_218], rcx
0x1401be0d2  mov     [rsp+240h+var_220], rax
0x1401be0d7  jmp     loc_1401BE021
0x1401be0dc  mov     rcx, [rdi]; void *
0x1401be0df  lea     r9, [rsp+240h+var_1D8]; enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *
0x1401be0e4  xor     r8d, r8d; enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *
0x1401be0e7  mov     [rsp+240h+var_1D8], r12d
0x1401be0ec  call    ?DmmGetVideoOutputTechnology@@YAJQEAXIPEAW4_D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY@@1@Z; DmmGetVideoOutputTechnology(void * const,uint,_D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *,_D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *)
0x1401be0f1  movsxd  r14, eax
0x1401be0f4  test    eax, eax
0x1401be0f6  jns     short loc_1401BE139
0x1401be0f8  mov     rdx, r14
0x1401be0fb  mov     ecx, r13d
0x1401be0fe  call    cs:__imp_WdLogSingleEntry1
0x1401be105  nop     dword ptr [rax+rax+00h]
0x1401be10a  mov     [rsp+240h+var_200], r12
0x1401be10f  lea     r9, aFailedCallToDm_0; "Failed call to DmmGetVideoOutputTechnol"...
0x1401be116  mov     [rsp+240h+var_208], r12
0x1401be11b  mov     [rsp+240h+var_210], r12
0x1401be120  mov     [rsp+240h+var_218], r12
0x1401be125  mov     [rsp+240h+var_220], r14
0x1401be12a  mov     cs:WdLogGlobalForLineNumber, 5A1h
0x1401be134  jmp     loc_1401BE021
0x1401be139  mov     eax, [rsp+240h+var_1D8]
0x1401be13d  sub     eax, 0Fh
0x1401be140  jz      short loc_1401BE151
0x1401be142  sub     eax, 1
0x1401be145  jz      short loc_1401BE151
0x1401be147  mov     [rsp+240h+var_1F0], r12b
0x1401be14c  cmp     eax, 1
0x1401be14f  jnz     short loc_1401BE156
0x1401be151  mov     [rsp+240h+var_1F0], 1
0x1401be156  mov     rax, [rbp+140h+var_F8]
0x1401be15a  lea     r9, [rbp+140h+var_F0]
0x1401be15e  mov     edx, [rdi+8]
0x1401be161  lea     r8, [rsp+240h+var_1E0]
0x1401be166  mov     [rbp+140h+var_F0], r12
0x1401be16a  mov     rcx, rsi
0x1401be16d  mov     [rsp+240h+var_1E0], r12
0x1401be172  mov     rax, [rax+8]
0x1401be176  mov     [rbp+140h+var_1A0], r12
0x1401be17a  mov     [rbp+140h+var_198], r12
0x1401be17e  mov     [rbp+140h+var_190], r12
0x1401be182  mov     [rbp+140h+var_188], r12d
0x1401be186  mov     [rbp+140h+var_1A8], r12b
0x1401be18a  call    _guard_dispatch_icall
0x1401be18f  movsxd  r14, eax
0x1401be192  test    eax, eax
0x1401be194  jns     short loc_1401BE1DC
0x1401be196  mov     r8d, [rdi+8]
0x1401be19a  mov     r9, r14
0x1401be19d  mov     rdx, rsi
0x1401be1a0  mov     ecx, r13d
0x1401be1a3  call    cs:__imp_WdLogSingleEntry3
0x1401be1aa  nop     dword ptr [rax+rax+00h]
0x1401be1af  mov     [rsp+240h+var_200], r12
0x1401be1b4  lea     r9, aFailedToAcquir_38; "Failed to acquire VidPn source mode set"...
0x1401be1bb  mov     [rsp+240h+var_208], r12
0x1401be1c0  mov     cs:WdLogGlobalForLineNumber, 5B7h
0x1401be1ca  mov     ecx, [rdi+8]
0x1401be1cd  mov     [rsp+240h+var_210], r14
0x1401be1d2  mov     [rsp+240h+var_218], rcx
0x1401be1d7  jmp     loc_1401BE01C
0x1401be1dc  mov     r8, [rbp+140h+var_F8]
0x1401be1e0  lea     rcx, [rbp+140h+var_1A8]
0x1401be1e4  mov     rdx, [rsp+240h+var_1E0]
0x1401be1e9  mov     r9, rsi
0x1401be1ec  mov     r8, [r8+10h]
0x1401be1f0  call    ?Own@?$AutoRelease@PEBU_D3DKMDT_VIDPN_PRESENT_PATH@@P6AJPEAUD3DKMDT_HVIDPNTOPOLOGY__@@PEBU1@@ZPEAU2@@DXGDMM@@QEAAXPEBU_D3DKMDT_VIDPN_PRESENT_PATH@@Q6AJPEAUD3DKMDT_HVIDPNTOPOLOGY__@@0@Z1@Z; DXGDMM::AutoRelease<_D3DKMDT_VIDPN_PRESENT_PATH const *,long (*)(D3DKMDT_HVIDPNTOPOLOGY__ *,_D3DKMDT_VIDPN_PRESENT_PATH const *),D3DKMDT_HVIDPNTOPOLOGY__ *>::Own(_D3DKMDT_VIDPN_PRESENT_PATH const *,long (*const)(D3DKMDT_HVIDPNTOPOLOGY__ *,_D3DKMDT_VIDPN_PRESENT_PATH const *),D3DKMDT_HVIDPNTOPOLOGY__ *)
0x1401be1f5  mov     rax, [rbp+140h+var_F0]
0x1401be1f9  lea     rdx, [rsp+240h+var_1E0]
0x1401be1fe  mov     r15, [rbp+140h+var_1A0]
0x1401be202  mov     [rsp+240h+var_1E0], r12
0x1401be207  mov     rcx, r15
0x1401be20a  mov     [rbp+140h+var_178], r12
0x1401be20e  mov     rax, [rax+8]
0x1401be212  mov     [rbp+140h+var_170], r12
0x1401be216  mov     [rbp+140h+var_168], r12
0x1401be21a  mov     [rbp+140h+var_160], r12d
0x1401be21e  mov     [rbp+140h+var_180], r12b
0x1401be222  call    _guard_dispatch_icall
0x1401be227  movsxd  r14, eax
0x1401be22a  test    eax, eax
0x1401be22c  jns     short loc_1401BE29C
0x1401be22e  mov     r8, r14
0x1401be231  mov     rdx, r15
0x1401be234  mov     ecx, r13d
0x1401be237  call    cs:__imp_WdLogSingleEntry2
0x1401be23e  nop     dword ptr [rax+rax+00h]
0x1401be243  mov     [rsp+240h+var_200], r12
0x1401be248  lea     r9, aFailedToAcquir_14; "Failed to acquire first mode info from "...
0x1401be24f  mov     [rsp+240h+var_208], r12
0x1401be254  or      r8d, 0FFFFFFFFh
0x1401be258  mov     [rsp+240h+var_210], r12
0x1401be25d  mov     edx, 40000h
0x1401be262  mov     [rsp+240h+var_218], r14
0x1401be267  xor     ecx, ecx
0x1401be269  mov     [rsp+240h+var_220], r15
0x1401be26e  mov     cs:WdLogGlobalForLineNumber, 5CCh
0x1401be278  call    DxgkLogInternalTriageEvent
0x1401be27d  cmp     [rbp+140h+var_1A8], r12b
0x1401be281  jz      loc_1401BE031
0x1401be287  mov     rcx, [rbp+140h+var_190]
0x1401be28b  mov     rdx, r15
0x1401be28e  mov     rax, [rbp+140h+var_198]
0x1401be292  call    _guard_dispatch_icall
0x1401be297  jmp     loc_1401BE031
0x1401be29c  mov     r8, [rbp+140h+var_F0]
0x1401be2a0  lea     rcx, [rbp+140h+var_180]
0x1401be2a4  mov     rdx, [rsp+240h+var_1E0]
0x1401be2a9  mov     r9, r15
0x1401be2ac  mov     r8, [r8+20h]
0x1401be2b0  call    ?Own@?$AutoRelease@PEBU_D3DKMDT_VIDPN_PRESENT_PATH@@P6AJPEAUD3DKMDT_HVIDPNTOPOLOGY__@@PEBU1@@ZPEAU2@@DXGDMM@@QEAAXPEBU_D3DKMDT_VIDPN_PRESENT_PATH@@Q6AJPEAUD3DKMDT_HVIDPNTOPOLOGY__@@0@Z1@Z; DXGDMM::AutoRelease<_D3DKMDT_VIDPN_PRESENT_PATH const *,long (*)(D3DKMDT_HVIDPNTOPOLOGY__ *,_D3DKMDT_VIDPN_PRESENT_PATH const *),D3DKMDT_HVIDPNTOPOLOGY__ *>::Own(_D3DKMDT_VIDPN_PRESENT_PATH const *,long (*const)(D3DKMDT_HVIDPNTOPOLOGY__ *,_D3DKMDT_VIDPN_PRESENT_PATH const *),D3DKMDT_HVIDPNTOPOLOGY__ *)
0x1401be2b5  mov     r14, [rbp+140h+var_178]
0x1401be2b9  test    r14, r14
0x1401be2bc  jz      loc_1401BEAD3
0x1401be2c2  mov     ecx, [r14+4]
0x1401be2c6  lea     eax, [rcx-1]
0x1401be2c9  test    eax, 0FFFFFFFCh
0x1401be2ce  jnz     loc_1401BE72E
0x1401be2d4  cmp     ecx, r13d
0x1401be2d7  jz      loc_1401BE72E
0x1401be2dd  mov     ecx, [r14+8]
0x1401be2e1  cmp     ecx, [r14+10h]
0x1401be2e5  jnz     loc_1401BE72E
0x1401be2eb  mov     edx, [r14+0Ch]
0x1401be2ef  cmp     edx, [r14+14h]
0x1401be2f3  jnz     loc_1401BE72E
0x1401be2f9  mov     eax, [r14+1Ch]
0x1401be2fd  sub     eax, 15h
0x1401be300  cmp     eax, 1
0x1401be303  ja      loc_1401BE72E
0x1401be309  cmp     ecx, [rbp+140h+var_A0.VideoSignalInfo.ActiveSize.cx]
0x1401be30f  jnz     loc_1401BE72E
0x1401be315  cmp     edx, [rbp+140h+var_A0.VideoSignalInfo.ActiveSize.cy]
0x1401be31b  jnz     loc_1401BE72E
0x1401be321  mov     rax, [rbp+140h+var_F0]
0x1401be325  mov     r8b, 1
0x1401be328  mov     edx, [r14]
0x1401be32b  mov     rcx, r15
0x1401be32e  mov     rax, [rax+28h]
0x1401be332  call    _guard_dispatch_icall
0x1401be337  test    eax, eax
  ... truncated ...
```
