# OBTAIN_PREFERRED_MODES_ON_PATH::operator()(_D3DKMT_DISPLAYMODE * *,uint *)

- ea: `0x1401c0a28`
- end: `0x1401c188e`
- name: `??ROBTAIN_PREFERRED_MODES_ON_PATH@@QEBAJPEAPEAU_D3DKMT_DISPLAYMODE@@PEAI@Z`
- size: `3686`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path`

## callers

- `0x1401dd4a4`

## callees

- `0x1400091f0`
- `0x14001b9c0`
- `0x140046780`
- `0x140047b60`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a1000`
- `0x1401c0a28`
- `0x14022c3d0`
- `0x1402df5a8`
- `0x1403374e0`
- `0x140338ba8`
- `0x140338d34`
- `0x140339978`
- `0x140339ea0`
- `0x140368554`

## import_xrefs

- `watchdog!WdLogSingleEntry4` at `0x1401c0c9b`
- `watchdog!WdLogSingleEntry4` at `0x1401c0c9b`
- `watchdog!WdLogSingleEntry2` at `0x1401c0adc`
- `watchdog!WdLogSingleEntry2` at `0x1401c0b77`
- `watchdog!WdLogSingleEntry2` at `0x1401c0e37`
- `watchdog!WdLogSingleEntry2` at `0x1401c12a8`
- `watchdog!WdLogSingleEntry2` at `0x1401c14f7`
- `watchdog!WdLogSingleEntry2` at `0x1401c1540`
- `watchdog!WdLogSingleEntry2` at `0x1401c1696`
- `watchdog!WdLogSingleEntry2` at `0x1401c0adc`
- `watchdog!WdLogSingleEntry2` at `0x1401c0b77`
- `watchdog!WdLogSingleEntry2` at `0x1401c0e37`
- `watchdog!WdLogSingleEntry2` at `0x1401c12a8`
- `watchdog!WdLogSingleEntry2` at `0x1401c14f7`
- `watchdog!WdLogSingleEntry2` at `0x1401c1540`
- `watchdog!WdLogSingleEntry2` at `0x1401c1696`
- `watchdog!WdLogSingleEntry3` at `0x1401c0a9d`
- `watchdog!WdLogSingleEntry3` at `0x1401c0be8`
- `watchdog!WdLogSingleEntry3` at `0x1401c0da3`
- `watchdog!WdLogSingleEntry3` at `0x1401c0f49`
- `watchdog!WdLogSingleEntry3` at `0x1401c108a`
- `watchdog!WdLogSingleEntry3` at `0x1401c13ea`
- `watchdog!WdLogSingleEntry3` at `0x1401c1468`
- `watchdog!WdLogSingleEntry3` at `0x1401c1497`
- `watchdog!WdLogSingleEntry3` at `0x1401c14c9`
- `watchdog!WdLogSingleEntry3` at `0x1401c15f7`
- `watchdog!WdLogSingleEntry3` at `0x1401c0a9d`
- `watchdog!WdLogSingleEntry3` at `0x1401c0be8`
- `watchdog!WdLogSingleEntry3` at `0x1401c0da3`
- `watchdog!WdLogSingleEntry3` at `0x1401c0f49`
- `watchdog!WdLogSingleEntry3` at `0x1401c108a`
- `watchdog!WdLogSingleEntry3` at `0x1401c13ea`
- `watchdog!WdLogSingleEntry3` at `0x1401c1468`
- `watchdog!WdLogSingleEntry3` at `0x1401c1497`
- `watchdog!WdLogSingleEntry3` at `0x1401c14c9`
- `watchdog!WdLogSingleEntry3` at `0x1401c15f7`
- `watchdog!WdLogSingleEntry0` at `0x1401c1719`
- `watchdog!WdLogSingleEntry0` at `0x1401c1719`
- `watchdog!WdLogSingleEntry1` at `0x1401c0cfe`
- `watchdog!WdLogSingleEntry1` at `0x1401c17cf`
- `watchdog!WdLogSingleEntry1` at `0x1401c0cfe`
- `watchdog!WdLogSingleEntry1` at `0x1401c17cf`

## string_xrefs

- `0x1401c14a3`: `Failed to pin D3DKMDT_VPPS_IDENTITY on path from source 0x%I64x to target 0x%I64x (Status = 0x%I64x).`
- `0x1401c1474`: `Failed to acquire path info on path from source 0x%I64x to target 0x%I64x (Status = 0x%I64x).`
- `0x1401c14d5`: `Failed to acquire VidPn path info from source 0x%I64x to target 0x%I64x (Status = 0x%I64x).`
- `0x1401c13f6`: `Unable to unpin content scaling on path from source 0x%I64x to target 0x%I64x (Status = 0x%I64x).`
- `0x1401c0cac`: `Failed to Add VidPn path from source 0x%I64x to target 0x%I64x on VidPn 0x%I64x (Status=0x%I64x).`
- `0x1401c0b83`: `Failed call to create an empty VidPN on adapter 0x%I64x (status = 0x%I64x).`

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
0x1401c0a28  mov     [rsp-8+arg_18], rbx
0x1401c0a2d  push    rbp
0x1401c0a2e  push    rsi
0x1401c0a2f  push    rdi
0x1401c0a30  push    r12
0x1401c0a32  push    r13
0x1401c0a34  push    r14
0x1401c0a36  push    r15
0x1401c0a38  lea     rbp, [rsp-110h]
0x1401c0a40  sub     rsp, 210h
0x1401c0a47  mov     rax, cs:__security_cookie
0x1401c0a4e  xor     rax, rsp
0x1401c0a51  mov     [rbp+140h+var_40], rax
0x1401c0a58  mov     [rbp+140h+var_E0], rdx
0x1401c0a5c  mov     rdi, rcx
0x1401c0a5f  xor     edx, edx; Val
0x1401c0a61  mov     [rbp+140h+var_E8], r8
0x1401c0a65  lea     rcx, [rbp+140h+var_A0]; void *
0x1401c0a6c  lea     r8d, [rdx+60h]; Size
0x1401c0a70  call    memset
0x1401c0a75  mov     edx, [rdi+0Ch]; unsigned int
0x1401c0a78  lea     r8, [rbp+140h+var_A0]; struct _D3DKMDT_MONITOR_SOURCE_MODE *
0x1401c0a7f  mov     rcx, [rdi]; void *
0x1401c0a82  call    ?DmmGetPreferredMonitorSourceModeOnTarget@@YAJPEAXIPEAU_D3DKMDT_MONITOR_SOURCE_MODE@@@Z; DmmGetPreferredMonitorSourceModeOnTarget(void *,uint,_D3DKMDT_MONITOR_SOURCE_MODE *)
0x1401c0a87  xor     r12d, r12d
0x1401c0a8a  test    eax, eax
0x1401c0a8c  jns     short loc_1401C0AB8
0x1401c0a8e  mov     r8d, [rdi+0Ch]
0x1401c0a92  lea     ecx, [r12+3]
0x1401c0a97  mov     rdx, [rdi]
0x1401c0a9a  movsxd  r9, eax
0x1401c0a9d  call    cs:__imp_WdLogSingleEntry3
0x1401c0aa4  nop     dword ptr [rax+rax+00h]
0x1401c0aa9  mov     cs:WdLogGlobalForLineNumber, 54Ch
0x1401c0ab3  jmp     loc_1401C1861
0x1401c0ab8  mov     rcx, [rdi]; this
0x1401c0abb  lea     r8, [rsp+240h+var_1E0]
0x1401c0ac0  mov     [rsp+240h+var_1E0], r12
0x1401c0ac5  call    DxgkQueryDmmInterface
0x1401c0aca  movsxd  rsi, eax
0x1401c0acd  test    eax, eax
0x1401c0acf  jns     short loc_1401C0B2C
0x1401c0ad1  mov     rdx, [rdi]
0x1401c0ad4  mov     r8, rsi
0x1401c0ad7  mov     ecx, 2
0x1401c0adc  call    cs:__imp_WdLogSingleEntry2
0x1401c0ae3  nop     dword ptr [rax+rax+00h]
0x1401c0ae8  lea     r9, aFailedToQueryd; "Failed to QueryDxgDmmInterface on hAdap"...
0x1401c0aef  mov     cs:WdLogGlobalForLineNumber, 558h
0x1401c0af9  mov     rax, [rdi]
0x1401c0afc  or      r8d, 0FFFFFFFFh
0x1401c0b00  mov     [rsp+240h+var_200], r12
0x1401c0b05  mov     edx, 40000h
0x1401c0b0a  mov     [rsp+240h+var_208], r12
0x1401c0b0f  xor     ecx, ecx
0x1401c0b11  mov     [rsp+240h+var_210], r12
0x1401c0b16  mov     [rsp+240h+var_218], rsi
0x1401c0b1b  mov     [rsp+240h+var_220], rax
0x1401c0b20  call    DxgkLogInternalTriageEvent
0x1401c0b25  mov     eax, esi
0x1401c0b27  jmp     loc_1401C1863
0x1401c0b2c  mov     rbx, [rsp+240h+var_1E0]
0x1401c0b31  lea     r8, [rbp+140h+var_F8]
0x1401c0b35  mov     rcx, [rdi]
0x1401c0b38  lea     rdx, [rsp+240h+var_1E8]
0x1401c0b3d  mov     [rbp+140h+var_F8], r12
0x1401c0b41  mov     [rsp+240h+var_1E8], r12
0x1401c0b46  mov     rax, [rbx+28h]
0x1401c0b4a  mov     [rsp+240h+var_1C8], r12
0x1401c0b4f  mov     [rbp+140h+var_1C0], r12
0x1401c0b53  mov     [rbp+140h+var_1B8], r12
0x1401c0b57  mov     [rbp+140h+var_1B0], r12d
0x1401c0b5b  mov     [rsp+240h+var_1D0], r12b
0x1401c0b60  call    _guard_dispatch_icall
0x1401c0b65  movsxd  rsi, eax
0x1401c0b68  test    eax, eax
0x1401c0b6a  jns     short loc_1401C0B99
0x1401c0b6c  mov     rdx, [rdi]
0x1401c0b6f  mov     r8, rsi
0x1401c0b72  mov     ecx, 2
0x1401c0b77  call    cs:__imp_WdLogSingleEntry2
0x1401c0b7e  nop     dword ptr [rax+rax+00h]
0x1401c0b83  lea     r9, aFailedCallToCr; "Failed call to create an empty VidPN on"...
0x1401c0b8a  mov     cs:WdLogGlobalForLineNumber, 56Bh
0x1401c0b94  jmp     loc_1401C0AF9
0x1401c0b99  mov     r9, [rdi]
0x1401c0b9c  lea     rcx, [rsp+240h+var_1D0]
0x1401c0ba1  mov     r8, [rbx+40h]
0x1401c0ba5  mov     rdx, [rsp+240h+var_1E8]
0x1401c0baa  call    ?Own@?$AutoRelease@PEBU_D3DKMDT_VIDPN_PRESENT_PATH@@P6AJPEAUD3DKMDT_HVIDPNTOPOLOGY__@@PEBU1@@ZPEAU2@@DXGDMM@@QEAAXPEBU_D3DKMDT_VIDPN_PRESENT_PATH@@Q6AJPEAUD3DKMDT_HVIDPNTOPOLOGY__@@0@Z1@Z; DXGDMM::AutoRelease<_D3DKMDT_VIDPN_PRESENT_PATH const *,long (*)(D3DKMDT_HVIDPNTOPOLOGY__ *,_D3DKMDT_VIDPN_PRESENT_PATH const *),D3DKMDT_HVIDPNTOPOLOGY__ *>::Own(_D3DKMDT_VIDPN_PRESENT_PATH const *,long (*const)(D3DKMDT_HVIDPNTOPOLOGY__ *,_D3DKMDT_VIDPN_PRESENT_PATH const *),D3DKMDT_HVIDPNTOPOLOGY__ *)
0x1401c0baf  mov     rax, [rbp+140h+var_F8]
0x1401c0bb3  lea     r8, [rbp+140h+var_130]
0x1401c0bb7  mov     rsi, [rsp+240h+var_1C8]
0x1401c0bbc  lea     rdx, [rbp+140h+var_128]
0x1401c0bc0  mov     [rbp+140h+var_128], r12
0x1401c0bc4  mov     rcx, rsi
0x1401c0bc7  mov     [rbp+140h+var_130], r12
0x1401c0bcb  mov     rax, [rax]
0x1401c0bce  call    _guard_dispatch_icall
0x1401c0bd3  movsxd  r14, eax
0x1401c0bd6  test    eax, eax
0x1401c0bd8  jns     short loc_1401C0C50
0x1401c0bda  mov     r8, [rdi]
0x1401c0bdd  mov     r9, r14
0x1401c0be0  mov     rdx, rsi
0x1401c0be3  mov     ecx, 2
0x1401c0be8  call    cs:__imp_WdLogSingleEntry3
0x1401c0bef  nop     dword ptr [rax+rax+00h]
0x1401c0bf4  mov     [rsp+240h+var_200], r12
0x1401c0bf9  lea     r9, aFailedToGetVid; "Failed to get VidPn topology from hVidP"...
0x1401c0c00  mov     [rsp+240h+var_208], r12
0x1401c0c05  mov     cs:WdLogGlobalForLineNumber, 582h
0x1401c0c0f  mov     rax, [rdi]
0x1401c0c12  mov     [rsp+240h+var_210], r14
0x1401c0c17  mov     [rsp+240h+var_218], rax
0x1401c0c1c  mov     [rsp+240h+var_220], rsi
0x1401c0c21  or      r8d, 0FFFFFFFFh
0x1401c0c25  mov     edx, 40000h
0x1401c0c2a  xor     ecx, ecx
0x1401c0c2c  call    DxgkLogInternalTriageEvent
0x1401c0c31  cmp     [rsp+240h+var_1D0], r12b
0x1401c0c36  jz      short loc_1401C0C48
0x1401c0c38  mov     rcx, [rbp+140h+var_1B8]
0x1401c0c3c  mov     rdx, rsi
0x1401c0c3f  mov     rax, [rbp+140h+var_1C0]
0x1401c0c43  call    _guard_dispatch_icall
0x1401c0c48  mov     eax, r14d
0x1401c0c4b  jmp     loc_1401C1863
0x1401c0c50  mov     rax, [rbp+140h+var_130]
0x1401c0c54  mov     r13d, 2
0x1401c0c5a  mov     r8d, [rdi+0Ch]
0x1401c0c5e  mov     edx, [rdi+8]
0x1401c0c61  mov     rcx, [rbp+140h+var_128]
0x1401c0c65  mov     rax, [rax+28h]
0x1401c0c69  lea     r9d, [r13-1]
0x1401c0c6d  mov     dword ptr [rsp+240h+var_218], r13d
0x1401c0c72  mov     word ptr [rsp+240h+var_220], r12w
0x1401c0c78  call    _guard_dispatch_icall
0x1401c0c7d  mov     edx, [rdi+0Ch]; unsigned int
0x1401c0c80  movsxd  r14, eax
0x1401c0c83  test    eax, eax
0x1401c0c85  jns     short loc_1401C0CDC
0x1401c0c87  mov     r8d, edx
0x1401c0c8a  mov     rbx, r14
0x1401c0c8d  mov     edx, [rdi+8]
0x1401c0c90  mov     r9, rsi
0x1401c0c93  mov     ecx, r13d
0x1401c0c96  mov     [rsp+240h+var_220], rbx
0x1401c0c9b  call    cs:__imp_WdLogSingleEntry4
0x1401c0ca2  nop     dword ptr [rax+rax+00h]
0x1401c0ca7  mov     [rsp+240h+var_200], r12
0x1401c0cac  lea     r9, aFailedToAddVid; "Failed to Add VidPn path from source 0x"...
0x1401c0cb3  mov     [rsp+240h+var_208], rbx
0x1401c0cb8  mov     cs:WdLogGlobalForLineNumber, 595h
0x1401c0cc2  mov     ecx, [rdi+0Ch]
0x1401c0cc5  mov     eax, [rdi+8]
0x1401c0cc8  mov     [rsp+240h+var_210], rsi
0x1401c0ccd  mov     [rsp+240h+var_218], rcx
0x1401c0cd2  mov     [rsp+240h+var_220], rax
0x1401c0cd7  jmp     loc_1401C0C21
0x1401c0cdc  mov     rcx, [rdi]; void *
0x1401c0cdf  lea     r9, [rsp+240h+var_1D8]; enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *
0x1401c0ce4  xor     r8d, r8d; enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *
0x1401c0ce7  mov     [rsp+240h+var_1D8], r12d
0x1401c0cec  call    ?DmmGetVideoOutputTechnology@@YAJQEAXIPEAW4_D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY@@1@Z; DmmGetVideoOutputTechnology(void * const,uint,_D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *,_D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY *)
0x1401c0cf1  movsxd  r14, eax
0x1401c0cf4  test    eax, eax
0x1401c0cf6  jns     short loc_1401C0D39
0x1401c0cf8  mov     rdx, r14
0x1401c0cfb  mov     ecx, r13d
0x1401c0cfe  call    cs:__imp_WdLogSingleEntry1
0x1401c0d05  nop     dword ptr [rax+rax+00h]
0x1401c0d0a  mov     [rsp+240h+var_200], r12
0x1401c0d0f  lea     r9, aFailedCallToDm_0; "Failed call to DmmGetVideoOutputTechnol"...
0x1401c0d16  mov     [rsp+240h+var_208], r12
0x1401c0d1b  mov     [rsp+240h+var_210], r12
0x1401c0d20  mov     [rsp+240h+var_218], r12
0x1401c0d25  mov     [rsp+240h+var_220], r14
0x1401c0d2a  mov     cs:WdLogGlobalForLineNumber, 5A1h
0x1401c0d34  jmp     loc_1401C0C21
0x1401c0d39  mov     eax, [rsp+240h+var_1D8]
0x1401c0d3d  sub     eax, 0Fh
0x1401c0d40  jz      short loc_1401C0D51
0x1401c0d42  sub     eax, 1
0x1401c0d45  jz      short loc_1401C0D51
0x1401c0d47  mov     [rsp+240h+var_1F0], r12b
0x1401c0d4c  cmp     eax, 1
0x1401c0d4f  jnz     short loc_1401C0D56
0x1401c0d51  mov     [rsp+240h+var_1F0], 1
0x1401c0d56  mov     rax, [rbp+140h+var_F8]
0x1401c0d5a  lea     r9, [rbp+140h+var_F0]
0x1401c0d5e  mov     edx, [rdi+8]
0x1401c0d61  lea     r8, [rsp+240h+var_1E0]
0x1401c0d66  mov     [rbp+140h+var_F0], r12
0x1401c0d6a  mov     rcx, rsi
0x1401c0d6d  mov     [rsp+240h+var_1E0], r12
0x1401c0d72  mov     rax, [rax+8]
0x1401c0d76  mov     [rbp+140h+var_1A0], r12
0x1401c0d7a  mov     [rbp+140h+var_198], r12
0x1401c0d7e  mov     [rbp+140h+var_190], r12
0x1401c0d82  mov     [rbp+140h+var_188], r12d
0x1401c0d86  mov     [rbp+140h+var_1A8], r12b
0x1401c0d8a  call    _guard_dispatch_icall
0x1401c0d8f  movsxd  r14, eax
0x1401c0d92  test    eax, eax
0x1401c0d94  jns     short loc_1401C0DDC
0x1401c0d96  mov     r8d, [rdi+8]
0x1401c0d9a  mov     r9, r14
0x1401c0d9d  mov     rdx, rsi
0x1401c0da0  mov     ecx, r13d
0x1401c0da3  call    cs:__imp_WdLogSingleEntry3
0x1401c0daa  nop     dword ptr [rax+rax+00h]
0x1401c0daf  mov     [rsp+240h+var_200], r12
0x1401c0db4  lea     r9, aFailedToAcquir_38; "Failed to acquire VidPn source mode set"...
0x1401c0dbb  mov     [rsp+240h+var_208], r12
0x1401c0dc0  mov     cs:WdLogGlobalForLineNumber, 5B7h
0x1401c0dca  mov     ecx, [rdi+8]
0x1401c0dcd  mov     [rsp+240h+var_210], r14
0x1401c0dd2  mov     [rsp+240h+var_218], rcx
0x1401c0dd7  jmp     loc_1401C0C1C
0x1401c0ddc  mov     r8, [rbp+140h+var_F8]
0x1401c0de0  lea     rcx, [rbp+140h+var_1A8]
0x1401c0de4  mov     rdx, [rsp+240h+var_1E0]
0x1401c0de9  mov     r9, rsi
0x1401c0dec  mov     r8, [r8+10h]
0x1401c0df0  call    ?Own@?$AutoRelease@PEBU_D3DKMDT_VIDPN_PRESENT_PATH@@P6AJPEAUD3DKMDT_HVIDPNTOPOLOGY__@@PEBU1@@ZPEAU2@@DXGDMM@@QEAAXPEBU_D3DKMDT_VIDPN_PRESENT_PATH@@Q6AJPEAUD3DKMDT_HVIDPNTOPOLOGY__@@0@Z1@Z; DXGDMM::AutoRelease<_D3DKMDT_VIDPN_PRESENT_PATH const *,long (*)(D3DKMDT_HVIDPNTOPOLOGY__ *,_D3DKMDT_VIDPN_PRESENT_PATH const *),D3DKMDT_HVIDPNTOPOLOGY__ *>::Own(_D3DKMDT_VIDPN_PRESENT_PATH const *,long (*const)(D3DKMDT_HVIDPNTOPOLOGY__ *,_D3DKMDT_VIDPN_PRESENT_PATH const *),D3DKMDT_HVIDPNTOPOLOGY__ *)
0x1401c0df5  mov     rax, [rbp+140h+var_F0]
0x1401c0df9  lea     rdx, [rsp+240h+var_1E0]
0x1401c0dfe  mov     r15, [rbp+140h+var_1A0]
0x1401c0e02  mov     [rsp+240h+var_1E0], r12
0x1401c0e07  mov     rcx, r15
0x1401c0e0a  mov     [rbp+140h+var_178], r12
0x1401c0e0e  mov     rax, [rax+8]
0x1401c0e12  mov     [rbp+140h+var_170], r12
0x1401c0e16  mov     [rbp+140h+var_168], r12
0x1401c0e1a  mov     [rbp+140h+var_160], r12d
0x1401c0e1e  mov     [rbp+140h+var_180], r12b
0x1401c0e22  call    _guard_dispatch_icall
0x1401c0e27  movsxd  r14, eax
0x1401c0e2a  test    eax, eax
0x1401c0e2c  jns     short loc_1401C0E9C
0x1401c0e2e  mov     r8, r14
0x1401c0e31  mov     rdx, r15
0x1401c0e34  mov     ecx, r13d
0x1401c0e37  call    cs:__imp_WdLogSingleEntry2
0x1401c0e3e  nop     dword ptr [rax+rax+00h]
0x1401c0e43  mov     [rsp+240h+var_200], r12
0x1401c0e48  lea     r9, aFailedToAcquir_14; "Failed to acquire first mode info from "...
0x1401c0e4f  mov     [rsp+240h+var_208], r12
0x1401c0e54  or      r8d, 0FFFFFFFFh
0x1401c0e58  mov     [rsp+240h+var_210], r12
0x1401c0e5d  mov     edx, 40000h
0x1401c0e62  mov     [rsp+240h+var_218], r14
0x1401c0e67  xor     ecx, ecx
0x1401c0e69  mov     [rsp+240h+var_220], r15
0x1401c0e6e  mov     cs:WdLogGlobalForLineNumber, 5CCh
0x1401c0e78  call    DxgkLogInternalTriageEvent
0x1401c0e7d  cmp     [rbp+140h+var_1A8], r12b
0x1401c0e81  jz      loc_1401C0C31
0x1401c0e87  mov     rcx, [rbp+140h+var_190]
0x1401c0e8b  mov     rdx, r15
0x1401c0e8e  mov     rax, [rbp+140h+var_198]
0x1401c0e92  call    _guard_dispatch_icall
0x1401c0e97  jmp     loc_1401C0C31
0x1401c0e9c  mov     r8, [rbp+140h+var_F0]
0x1401c0ea0  lea     rcx, [rbp+140h+var_180]
0x1401c0ea4  mov     rdx, [rsp+240h+var_1E0]
0x1401c0ea9  mov     r9, r15
0x1401c0eac  mov     r8, [r8+20h]
0x1401c0eb0  call    ?Own@?$AutoRelease@PEBU_D3DKMDT_VIDPN_PRESENT_PATH@@P6AJPEAUD3DKMDT_HVIDPNTOPOLOGY__@@PEBU1@@ZPEAU2@@DXGDMM@@QEAAXPEBU_D3DKMDT_VIDPN_PRESENT_PATH@@Q6AJPEAUD3DKMDT_HVIDPNTOPOLOGY__@@0@Z1@Z; DXGDMM::AutoRelease<_D3DKMDT_VIDPN_PRESENT_PATH const *,long (*)(D3DKMDT_HVIDPNTOPOLOGY__ *,_D3DKMDT_VIDPN_PRESENT_PATH const *),D3DKMDT_HVIDPNTOPOLOGY__ *>::Own(_D3DKMDT_VIDPN_PRESENT_PATH const *,long (*const)(D3DKMDT_HVIDPNTOPOLOGY__ *,_D3DKMDT_VIDPN_PRESENT_PATH const *),D3DKMDT_HVIDPNTOPOLOGY__ *)
0x1401c0eb5  mov     r14, [rbp+140h+var_178]
0x1401c0eb9  test    r14, r14
0x1401c0ebc  jz      loc_1401C16D3
0x1401c0ec2  mov     ecx, [r14+4]
0x1401c0ec6  lea     eax, [rcx-1]
0x1401c0ec9  test    eax, 0FFFFFFFCh
0x1401c0ece  jnz     loc_1401C132E
0x1401c0ed4  cmp     ecx, r13d
0x1401c0ed7  jz      loc_1401C132E
0x1401c0edd  mov     ecx, [r14+8]
0x1401c0ee1  cmp     ecx, [r14+10h]
0x1401c0ee5  jnz     loc_1401C132E
0x1401c0eeb  mov     edx, [r14+0Ch]
0x1401c0eef  cmp     edx, [r14+14h]
0x1401c0ef3  jnz     loc_1401C132E
0x1401c0ef9  mov     eax, [r14+1Ch]
0x1401c0efd  sub     eax, 15h
0x1401c0f00  cmp     eax, 1
0x1401c0f03  ja      loc_1401C132E
0x1401c0f09  cmp     ecx, [rbp+140h+var_A0.VideoSignalInfo.ActiveSize.cx]
0x1401c0f0f  jnz     loc_1401C132E
0x1401c0f15  cmp     edx, [rbp+140h+var_A0.VideoSignalInfo.ActiveSize.cy]
0x1401c0f1b  jnz     loc_1401C132E
0x1401c0f21  mov     rax, [rbp+140h+var_F0]
0x1401c0f25  mov     r8b, 1
0x1401c0f28  mov     edx, [r14]
0x1401c0f2b  mov     rcx, r15
0x1401c0f2e  mov     rax, [rax+28h]
0x1401c0f32  call    _guard_dispatch_icall
0x1401c0f37  test    eax, eax
  ... truncated ...
```
