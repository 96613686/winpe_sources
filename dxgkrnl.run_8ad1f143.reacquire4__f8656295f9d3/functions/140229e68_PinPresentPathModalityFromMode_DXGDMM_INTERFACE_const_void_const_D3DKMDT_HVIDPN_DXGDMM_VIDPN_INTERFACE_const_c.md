# PinPresentPathModalityFromMode(_DXGDMM_INTERFACE const *,void * const,D3DKMDT_HVIDPN__ *,_DXGDMM_VIDPN_INTERFACE const * const,D3DKMDT_HVIDPNTOPOLOGY__ *,_DXGDMM_VIDPNTOPOLOGY_INTERFACE const * const,uint,unsigned __int64,_DXGK_DISPLAYMODE_INFO *,_D3DKMDT_VIDPN_PRESENT_PATH_SCALING,uchar,uchar,D3DKMDT_HVIDPN__ * *)

- ea: `0x140229e68`
- end: `0x14022a908`
- name: `?PinPresentPathModalityFromMode@@YAJPEBU_DXGDMM_INTERFACE@@QEAXPEAUD3DKMDT_HVIDPN__@@QEBU_DXGDMM_VIDPN_INTERFACE@@PEAUD3DKMDT_HVIDPNTOPOLOGY__@@QEBU_DXGDMM_VIDPNTOPOLOGY_INTERFACE@@I_KPEAU_DXGK_DISPLAYMODE_INFO@@W4_D3DKMDT_VIDPN_PRESENT_PATH_SCALING@@EEPEAPEAU2@@Z`
- size: `2720`
- prototype: `int(const struct _DXGDMM_INTERFACE *, void *const, struct D3DKMDT_HVIDPN__ *, const struct _DXGDMM_VIDPN_INTERFACE *const, struct D3DKMDT_HVIDPNTOPOLOGY__ *, const struct _DXGDMM_VIDPNTOPOLOGY_INTERFACE *const, unsigned int, unsigned __int64, struct _DXGK_DISPLAYMODE_INFO *, enum _D3DKMDT_VIDPN_PRESENT_PATH_SCALING, unsigned __int8, unsigned __int8, struct D3DKMDT_HVIDPN__ **)`
- caller_count: `1`
- callee_count: `22`
- tags: `reparse_path, installer_update`

## callers

- `0x1401b4f98`

## callees

- `0x140012380`
- `0x14001b890`
- `0x140044b74`
- `0x14004fd60`
- `0x1400a01e0`
- `0x1400a0540`
- `0x1401d2064`
- `0x140229a84`
- `0x140229e68`
- `0x14022b2b4`
- `0x14022b94c`
- `0x1402c46ec`
- `0x1402c4d60`
- `0x1402c5370`
- `0x140323854`
- `0x1403330ac`
- `0x140333154`
- `0x14036b520`
- `0x140386a9c`
- `0x140386f90`
- `0x1403872d0`
- `0x1403881a4`

## import_xrefs

- `watchdog!WdLogSingleEntry4` at `0x14022a571`
- `watchdog!WdLogSingleEntry4` at `0x14022a571`
- `watchdog!WdLogSingleEntry2` at `0x14022a5c7`
- `watchdog!WdLogSingleEntry2` at `0x14022a5c7`
- `watchdog!WdLogSingleEntry3` at `0x14022a167`
- `watchdog!WdLogSingleEntry3` at `0x14022a272`
- `watchdog!WdLogSingleEntry3` at `0x14022a167`
- `watchdog!WdLogSingleEntry3` at `0x14022a272`
- `watchdog!WdLogSingleEntry0` at `0x140229eb5`
- `watchdog!WdLogSingleEntry0` at `0x140229f01`
- `watchdog!WdLogSingleEntry0` at `0x140229f4d`
- `watchdog!WdLogSingleEntry0` at `0x140229fa0`
- `watchdog!WdLogSingleEntry0` at `0x140229ff5`
- `watchdog!WdLogSingleEntry0` at `0x14022a04a`
- `watchdog!WdLogSingleEntry0` at `0x14022a0a3`
- `watchdog!WdLogSingleEntry0` at `0x14022a0f7`
- `watchdog!WdLogSingleEntry0` at `0x14022a882`
- `watchdog!WdLogSingleEntry0` at `0x140229eb5`
- `watchdog!WdLogSingleEntry0` at `0x140229f01`
- `watchdog!WdLogSingleEntry0` at `0x140229f4d`
- `watchdog!WdLogSingleEntry0` at `0x140229fa0`
- `watchdog!WdLogSingleEntry0` at `0x140229ff5`
- `watchdog!WdLogSingleEntry0` at `0x14022a04a`
- `watchdog!WdLogSingleEntry0` at `0x14022a0a3`
- `watchdog!WdLogSingleEntry0` at `0x14022a0f7`
- `watchdog!WdLogSingleEntry0` at `0x14022a882`
- `watchdog!WdLogSingleEntry1` at `0x14022a1e3`
- `watchdog!WdLogSingleEntry1` at `0x14022a7ad`
- `watchdog!WdLogSingleEntry1` at `0x14022a1e3`
- `watchdog!WdLogSingleEntry1` at `0x14022a7ad`

## string_xrefs

- `0x14022a1f3`: `Failed to allocate PathModality for 0x%I64x paths`
- `0x14022a178`: `Failed to determine number of paths originating from source 0x%I64x in topology 0x%I64x (status = 0x%I64x)`
- `0x14022a287`: `Failed to find the most important paths originating from source 0x%I64x in topology 0x%I64x (status = 0x%I64x)`
- `0x14022a583`: `Failed to convert paths from source 0x%I64x to target 0x%I64x in VidPn topology 0x%I64x to PathsModality (status = 0x%I64x)`
- `0x14022a5e4`: `Failed to enumerate the all the paths topology 0x%I64x (status = 0x%I64x)`
- `0x14022a893`: `Failed to update refresh rate!`

## pseudocode

```c
__int64 __fastcall PinPresentPathModalityFromMode(
        void (__fastcall **a1)(char *, struct D3DKMDT_HVIDPN__ *),
        char *a2,
        struct D3DKMDT_HVIDPN__ *a3,
        struct _DXGDMM_VIDPN_INTERFACE *a4,
        struct D3DKMDT_HVIDPNTOPOLOGY__ *a5,
        const struct _DXGDMM_VIDPNTOPOLOGY_INTERFACE *a6,
        unsigned int a7,
        unsigned __int64 a8,
        struct _DXGK_DISPLAYMODE_INFO *a9,
        enum _D3DKMDT_VIDPN_PRESENT_PATH_SCALING a10,
        unsigned int a11,
        unsigned int a12,
        struct D3DKMDT_HVIDPN__ **a13)
{
  struct D3DKMDT_HVIDPNTOPOLOGY__ *v16; // r14
  const struct _DXGDMM_VIDPNTOPOLOGY_INTERFACE *v17; // rbx
  struct _DXGK_DISPLAYMODE_INFO *v18; // r12
  __int64 v19; // r15
  int v20; // r8d
  __int64 (__fastcall *v21)(struct D3DKMDT_HVIDPNTOPOLOGY__ *, unsigned __int64 *); // rax
  int v22; // eax
  __int64 v23; // rsi
  unsigned __int16 v24; // ax
  __int64 v25; // rbx
  int MostImportantVidPnPathTargetsFromSource; // eax
  __m128 si128; // xmm6
  unsigned int i; // eax
  unsigned int v29; // esi
  const struct D3DKMT_PATHMODALITY_DESCRIPTOR *PathDescriptor; // rdi
  int v31; // eax
  bool v32; // al
  int v33; // eax
  __int64 v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rcx
  enum _D3DKMDT_VIDPN_PRESENT_PATH_ROTATION v37; // eax
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // rcx
  unsigned int j; // edi
  unsigned __int16 v43; // ax
  const struct D3DKMT_PATHMODALITY_DESCRIPTOR *v44; // r14
  unsigned int k; // esi
  unsigned __int16 v46; // dx
  unsigned int v47; // ebx
  const struct D3DKMT_PATHMODALITY_DESCRIPTOR *v48; // rax
  const struct D3DKMT_PATHMODALITY_DESCRIPTOR *v49; // rax
  int v50; // ebx
  struct DXGPROCESS *Current; // rax
  struct D3DKMDT_HVIDPN__ **v52; // r14
  int v53; // edi
  __int64 v54; // r8
  int v55; // edi
  __int64 v56; // r8
  unsigned int m; // ebx
  const struct D3DKMT_PATHMODALITY_DESCRIPTOR *v58; // rax
  unsigned int PathModalityForAdapterWithCoreAccessHeld; // eax
  struct D3DKMDT_HVIDPN__ *v60; // rdx
  _BYTE v62[64]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v63; // [rsp+98h] [rbp-70h]
  _D3DKMDT_VIDPN_TARGET_MODE v64[2]; // [rsp+C8h] [rbp-40h] BYREF
  unsigned __int64 v66; // [rsp+180h] [rbp+78h] BYREF
  struct D3DKMDT_HVIDPN__ *v67; // [rsp+188h] [rbp+80h]
  struct _DXGDMM_VIDPN_INTERFACE *v68; // [rsp+190h] [rbp+88h]

  v68 = a4;
  v67 = a3;
  if ( !a2 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4108;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"i_hAdapter != NULL", 4108, 0, 0, 0, 0);
  }
  if ( !a3 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4109;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"i_hVidPn != NULL", 4109, 0, 0, 0, 0);
  }
  if ( !a4 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4110;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"i_pDmmVidPnInterface != NULL", 4110, 0, 0, 0, 0);
  }
  v16 = a5;
  if ( !a5 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4111;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"i_hVidPnTopology != NULL", 4111, 0, 0, 0, 0);
  }
  v17 = a6;
  if ( !a6 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4112;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"i_pDmmVidPnTopologyInterface != NULL", 4112, 0, 0, 0, 0);
  }
  v18 = a9;
  if ( !a9 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4113;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"io_pDisplayModeInfo != NULL", 4113, 0, 0, 0, 0);
  }
  v19 = a7;
  if ( a7 == -1 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4114;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      v19 | v20,
      (unsigned int)L"i_VidPnSourceId != D3DDDI_ID_UNINITIALIZED",
      4114,
      0,
      0,
      0,
      0);
  }
  if ( !a13 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4115;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"o_phFunctionalizedVidPn != NULL", 4115, 0, 0, 0, 0);
  }
  v21 = (__int64 (__fastcall *)(struct D3DKMDT_HVIDPNTOPOLOGY__ *, unsigned __int64 *))*((_QWORD *)v17 + 15);
  v66 = 0;
  v22 = v21(v16, &v66);
  v23 = v22;
  if ( v22 >= 0 )
  {
    CCD_TOPOLOGY::CCD_TOPOLOGY((CCD_TOPOLOGY *)v62, v66, v66);
    if ( v63 )
      v24 = *(_WORD *)(v63 + 22);
    else
      v24 = 0;
    if ( v24 >= (unsigned __int16)v66 )
    {
      v25 = *(_QWORD *)(a2 + 412);
      a10 = D3DKMDT_VPPS_UNINITIALIZED;
      MostImportantVidPnPathTargetsFromSource = DmmGetMostImportantVidPnPathTargetsFromSource(
                                                  (DXGADAPTER *)a2,
                                                  a3,
                                                  v19,
                                                  (unsigned int *const)&a10);
      v23 = MostImportantVidPnPathTargetsFromSource;
      if ( MostImportantVidPnPathTargetsFromSource >= 0 )
      {
        si128 = (__m128)_mm_load_si128((const __m128i *)&_xmm);
        for ( i = 0; ; i = a7 + 1 )
        {
          v29 = i;
          a7 = i;
          if ( i >= v66 )
            break;
          a12 = 0;
          a11 = 0;
          PathDescriptor = CCD_TOPOLOGY::GetPathDescriptor((CCD_TOPOLOGY *)v62, i);
          v31 = (*((__int64 (__fastcall **)(struct D3DKMDT_HVIDPNTOPOLOGY__ *, _QWORD, unsigned int *, unsigned int *))a6
                 + 16))(
                  v16,
                  v29,
                  &a12,
                  &a11);
          v23 = v31;
          if ( v31 < 0 )
          {
            WdLogSingleEntry2(2, v16);
            WdLogGlobalForLineNumber = 4166;
            DxgkLogInternalTriageEvent(
              0,
              0x40000,
              -1,
              (unsigned int)L"Failed to enumerate the all the paths topology 0x%I64x (status = 0x%I64x)",
              (__int64)v16,
              v23,
              0,
              0,
              0);
            goto LABEL_80;
          }
          *((_DWORD *)PathDescriptor + 6) = a12;
          *((_DWORD *)PathDescriptor + 7) = a11;
          *(_QWORD *)PathDescriptor |= 0x8700000000000uLL;
          *((_QWORD *)PathDescriptor + 2) = v25;
          v32 = a12 != (_DWORD)v19 || *((_BYTE *)DXGGLOBAL::GetGlobal() + 304953);
          v33 = ConvertVidPnPathToPathDescription(a2, v67, v68, a6, v16, a12, a11, v32, PathDescriptor);
          v23 = v33;
          if ( v33 < 0 )
          {
            WdLogSingleEntry4(2, a12, a11, v16, v33);
            WdLogGlobalForLineNumber = 4194;
            DxgkLogInternalTriageEvent(
              0,
              0x40000,
              -1,
              (unsigned int)L"Failed to convert paths from source 0x%I64x to target 0x%I64x in VidPn topology 0x%I64x to P"
                             "athsModality (status = 0x%I64x)",
              a12,
              a11,
              (__int64)v16,
              v23,
              0);
            goto LABEL_80;
          }
          if ( a12 == (_DWORD)v19 )
          {
            *((_DWORD *)PathDescriptor + 24) = *(_DWORD *)v18;
            *((_DWORD *)PathDescriptor + 25) = *((_DWORD *)v18 + 1);
            *((_QWORD *)PathDescriptor + 13) = *((_QWORD *)PathDescriptor + 12);
            *((_DWORD *)PathDescriptor + 29) = *((_DWORD *)v18 + 2);
            *((_BYTE *)PathDescriptor + 128) = (*((_DWORD *)v18 + 10) & 0x10) != 0;
            *(_QWORD *)PathDescriptor |= 0x100uLL;
            *((_QWORD *)PathDescriptor + 1) |= 0x100uLL;
            v34 = *((_QWORD *)v18 + 7);
            v35 = *((_QWORD *)PathDescriptor + 1);
            v36 = *(_QWORD *)PathDescriptor | 2LL;
            *(_QWORD *)PathDescriptor = v36;
            v35 |= 2uLL;
            *((_QWORD *)PathDescriptor + 1) = v35;
            *(_QWORD *)((char *)PathDescriptor + 52) = v34;
            *((_QWORD *)PathDescriptor + 28) = *((_QWORD *)v18 + 2);
            *((_DWORD *)PathDescriptor + 60) = *((_DWORD *)v18 + 18);
            *(_QWORD *)PathDescriptor = v36 | 0x1000000;
            *((_QWORD *)PathDescriptor + 1) = v35 | 0x1000000;
            if ( *((_BYTE *)DXGGLOBAL::GetGlobal() + 304896)
              && (int)DmmGetClientVidPnTargetModeInfo(
                        (DXGADAPTER *)a2,
                        a11,
                        0,
                        0,
                        0,
                        0,
                        (struct _D3DKMDT_2DREGION *)((char *)PathDescriptor + 44),
                        0) >= 0 )
            {
              *(__m128 *)PathDescriptor = _mm_or_ps(si128, (__m128)_mm_loadu_si128((const __m128i *)PathDescriptor));
            }
            if ( a11 == a10 )
            {
              v37 = ConvertD3DddiRotationToDmmRotation(*((enum _D3DDDI_ROTATION *)v18 + 7));
              *(_QWORD *)PathDescriptor |= 0x200uLL;
            }
            else
            {
              *(_QWORD *)PathDescriptor &= ~0x200uLL;
              v37 = D3DKMDT_VPPR_UNINITIALIZED;
            }
            v38 = *(_QWORD *)PathDescriptor;
            *((_DWORD *)PathDescriptor + 33) = v37;
            if ( a11 == a10 )
              *((_DWORD *)PathDescriptor + 20) = *((_DWORD *)v18 + 6)
                                               ^ (*((_DWORD *)PathDescriptor + 20)
                                                ^ *((_DWORD *)v18 + 6))
                                               & 0xFFFFFFF8;
            v39 = v38 | 4;
            *(_QWORD *)PathDescriptor = v39;
            v40 = *((unsigned int *)v18 + 8);
            if ( (unsigned int)(v40 - 1) <= 1 )
            {
              ConvertGdiScalingToDMMScaling(v40, (char *)PathDescriptor + 136);
            }
            else if ( (v39 & 0x40000000000LL) == 0 )
            {
              DmmGetDefaultScaling(a2, (enum _D3DKMDT_VIDPN_PRESENT_PATH_SCALING *)PathDescriptor + 34);
            }
            *(_QWORD *)PathDescriptor |= 0x40000000000uLL;
          }
          else
          {
            *((_QWORD *)PathDescriptor + 1) |= *(_QWORD *)PathDescriptor & 0x18001820B8FLL;
          }
        }
        v41 = v63;
        for ( j = 0; ; ++j )
        {
          v43 = v41 ? *(_WORD *)(v41 + 20) : 0;
          if ( j >= v43 )
            break;
          v44 = CCD_TOPOLOGY::GetPathDescriptor((CCD_TOPOLOGY *)v62, j);
          if ( (*(_QWORD *)v44 & 0x4000000000000LL) != 0 )
          {
            v41 = v63;
          }
          else
          {
            for ( k = j; ; ++k )
            {
              v41 = v63;
              v46 = v63 ? *(_WORD *)(v63 + 20) : 0;
              if ( k >= v46 )
                break;
              v47 = *((_DWORD *)v44 + 6);
              v48 = CCD_TOPOLOGY::GetPathDescriptor((CCD_TOPOLOGY *)v62, k);
              if ( CCD_TOPOLOGY::IsMatchingSource(v48, (const struct _LUID *)v44 + 2, v47) )
              {
                *((_DWORD *)CCD_TOPOLOGY::GetPathDescriptor((CCD_TOPOLOGY *)v62, k) + 46) = j | 0xFE540000;
                v49 = CCD_TOPOLOGY::GetPathDescriptor((CCD_TOPOLOGY *)v62, k);
                *(_QWORD *)v49 |= 0x4000000000000uLL;
              }
            }
          }
        }
        v50 = (unsigned __int8)DxgkGetGlobalRawmodeFlag() != 0 ? 0x20000 : 0;
        Current = DXGPROCESS::GetCurrent();
        v52 = a13;
        v53 = v50 | 0x8000000;
        LOBYTE(v54) = 1;
        if ( (*((_DWORD *)Current + 102) & 4) == 0 )
          v53 = v50;
        v55 = v53 | 0x40000;
        if ( (int)BmlGetPathModalityForAdapterWithCoreAccessHeld(v63, a2, v54, 2, v55, a13) >= 0 )
          goto LABEL_77;
        for ( m = 0; m < v66; ++m )
        {
          v58 = CCD_TOPOLOGY::GetPathDescriptor((CCD_TOPOLOGY *)v62, m);
          if ( *((_DWORD *)v58 + 6) == (_DWORD)v19 )
            *((_QWORD *)v58 + 1) &= 0xFFFFFFFFFEFFFFFDuLL;
        }
        LOBYTE(v56) = 1;
        PathModalityForAdapterWithCoreAccessHeld = BmlGetPathModalityForAdapterWithCoreAccessHeld(
                                                     v63,
                                                     a2,
                                                     v56,
                                                     2,
                                                     v55,
                                                     v52);
        v23 = (int)PathModalityForAdapterWithCoreAccessHeld;
        DxgkLogCodePointPacket(30, PathModalityForAdapterWithCoreAccessHeld, (unsigned int)a8 + (v19 & 0xFFFF0000));
        if ( (int)v23 >= 0 )
        {
LABEL_77:
          memset(v64, 0, 0x50u);
          v60 = *v52;
          a6 = 0;
          a7 = 0;
          LODWORD(v23) = RetrievePinnedModeForTarget(v68, v60, a10, v64, (struct _D3DDDI_RATIONAL *)&a6, &a7);
          if ( (int)v23 < 0 )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 4430;
            DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"Failed to update refresh rate!", 4430, 0, 0, 0, 0);
            a1[8](a2, *v52);
            *v52 = 0;
          }
          else
          {
            *((_QWORD *)v18 + 7) = v64[0].VideoSignalInfo.VSyncFreq;
            v64[0].VideoSignalInfo.VSyncFreq = (D3DDDI_RATIONAL)a6;
            DmmCalculatePresentationVSync(&v64[0].VideoSignalInfo, (struct _D3DDDI_RATIONAL *)v18 + 2);
            *((_DWORD *)v18 + 3) = DmmMapVSyncFromRationalToInteger(
                                     (const struct _D3DDDI_RATIONAL *)v18 + 2,
                                     (enum _D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING)((int)(*(_DWORD *)&v64[0].VideoSignalInfo.AdditionalSignalInfo << 29) >> 29),
                                     0);
          }
        }
        else
        {
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 4391;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"After relaxing the refresh rate matching functionalize still failed (status = 0x%I64x)",
            v23,
            0,
            0,
            0,
            0);
        }
      }
      else
      {
        WdLogSingleEntry3(2, v19, v16, MostImportantVidPnPathTargetsFromSource);
        WdLogGlobalForLineNumber = 4147;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Failed to find the most important paths originating from source 0x%I64x in topology 0x%I64x (status = 0x%I64x)",
          v19,
          (__int64)v16,
          v23,
          0,
          0);
      }
    }
    else
    {
      WdLogSingleEntry1(6);
      WdLogGlobalForLineNumber = 4132;
      DxgkLogInternalTriageEvent(
        0,
        262145,
        -1,
        (unsigned int)L"Failed to allocate PathModality for 0x%I64x paths",
        v66,
        0,
        0,
        0,
        0);
      LODWORD(v23) = -1073741801;
    }
LABEL_80:
    CCD_TOPOLOGY::~CCD_TOPOLOGY((CCD_TOPOLOGY *)v62);
  }
  else
  {
    WdLogSingleEntry3(2, v19, v16, v22);
    WdLogGlobalForLineNumber = 4124;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Failed to determine number of paths originating from source 0x%I64x in topology 0x%I64x (status = 0x%I64x)",
      v19,
      (__int64)v16,
      v23,
      0,
      0);
  }
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x140229e68  mov     rax, rsp
0x140229e6b  mov     [rax+20h], r9
0x140229e6f  mov     [rax+18h], r8
0x140229e73  mov     [rax+8], rcx
0x140229e77  push    rbp
0x140229e78  push    rbx
0x140229e79  push    rsi
0x140229e7a  push    rdi
0x140229e7b  push    r12
0x140229e7d  push    r13
0x140229e7f  push    r14
0x140229e81  push    r15
0x140229e83  lea     rbp, [rax-68h]
0x140229e87  sub     rsp, 128h
0x140229e8e  or      r12d, 0FFFFFFFFh
0x140229e92  movaps  xmmword ptr [rax-58h], xmm6
0x140229e96  xor     esi, esi
0x140229e98  mov     rbx, r9
0x140229e9b  mov     rdi, r8
0x140229e9e  mov     r13, rdx
0x140229ea1  mov     r15d, 1
0x140229ea7  mov     r14d, 40002h
0x140229ead  test    rdx, rdx
0x140229eb0  jnz     short loc_140229EF9
0x140229eb2  mov     ecx, r15d
0x140229eb5  call    cs:__imp_WdLogSingleEntry0
0x140229ebc  nop     dword ptr [rax+rax+00h]
0x140229ec1  mov     [rsp+40h], rsi
0x140229ec6  lea     r9, aIHadapterNull; "i_hAdapter != NULL"
0x140229ecd  mov     [rsp+160h+var_128], rsi
0x140229ed2  mov     eax, 100Ch
0x140229ed7  mov     [rsp+160h+var_130], rsi
0x140229edc  mov     r8d, r12d
0x140229edf  mov     qword ptr [rsp+160h+var_138.Numerator], rsi
0x140229ee4  mov     edx, r14d
0x140229ee7  xor     ecx, ecx
0x140229ee9  mov     [rsp+160h+var_140], rax
0x140229eee  mov     cs:WdLogGlobalForLineNumber, eax
0x140229ef4  call    DxgkLogInternalTriageEvent
0x140229ef9  test    rdi, rdi
0x140229efc  jnz     short loc_140229F45
0x140229efe  mov     ecx, r15d
0x140229f01  call    cs:__imp_WdLogSingleEntry0
0x140229f08  nop     dword ptr [rax+rax+00h]
0x140229f0d  mov     [rsp+40h], rsi
0x140229f12  lea     r9, aIHvidpnNull; "i_hVidPn != NULL"
0x140229f19  mov     [rsp+160h+var_128], rsi
0x140229f1e  mov     eax, 100Dh
0x140229f23  mov     [rsp+160h+var_130], rsi
0x140229f28  mov     r8d, r12d
0x140229f2b  mov     qword ptr [rsp+160h+var_138.Numerator], rsi
0x140229f30  mov     edx, r14d
0x140229f33  xor     ecx, ecx
0x140229f35  mov     [rsp+160h+var_140], rax
0x140229f3a  mov     cs:WdLogGlobalForLineNumber, eax
0x140229f40  call    DxgkLogInternalTriageEvent
0x140229f45  test    rbx, rbx
0x140229f48  jnz     short loc_140229F91
0x140229f4a  mov     ecx, r15d
0x140229f4d  call    cs:__imp_WdLogSingleEntry0
0x140229f54  nop     dword ptr [rax+rax+00h]
0x140229f59  mov     [rsp+40h], rsi
0x140229f5e  lea     r9, aIPdmmvidpninte; "i_pDmmVidPnInterface != NULL"
0x140229f65  mov     [rsp+160h+var_128], rsi
0x140229f6a  mov     eax, 100Eh
0x140229f6f  mov     [rsp+160h+var_130], rsi
0x140229f74  mov     r8d, r12d
0x140229f77  mov     qword ptr [rsp+160h+var_138.Numerator], rsi
0x140229f7c  mov     edx, r14d
0x140229f7f  xor     ecx, ecx
0x140229f81  mov     [rsp+160h+var_140], rax
0x140229f86  mov     cs:WdLogGlobalForLineNumber, eax
0x140229f8c  call    DxgkLogInternalTriageEvent
0x140229f91  mov     r14, [rbp+60h+arg_20]
0x140229f98  test    r14, r14
0x140229f9b  jnz     short loc_140229FE6
0x140229f9d  mov     ecx, r15d
0x140229fa0  call    cs:__imp_WdLogSingleEntry0
0x140229fa7  nop     dword ptr [rax+rax+00h]
0x140229fac  mov     [rsp+40h], rsi
0x140229fb1  lea     r9, aIHvidpntopolog; "i_hVidPnTopology != NULL"
0x140229fb8  mov     [rsp+160h+var_128], rsi
0x140229fbd  mov     eax, 100Fh
0x140229fc2  mov     [rsp+160h+var_130], rsi
0x140229fc7  mov     r8d, r12d
0x140229fca  mov     qword ptr [rsp+160h+var_138.Numerator], rsi
0x140229fcf  mov     edx, 40002h
0x140229fd4  xor     ecx, ecx
0x140229fd6  mov     [rsp+160h+var_140], rax
0x140229fdb  mov     cs:WdLogGlobalForLineNumber, eax
0x140229fe1  call    DxgkLogInternalTriageEvent
0x140229fe6  mov     rbx, qword ptr [rbp+60h+arg_28.Numerator]
0x140229fed  test    rbx, rbx
0x140229ff0  jnz     short loc_14022A03B
0x140229ff2  mov     ecx, r15d
0x140229ff5  call    cs:__imp_WdLogSingleEntry0
0x140229ffc  nop     dword ptr [rax+rax+00h]
0x14022a001  mov     [rsp+40h], rsi
0x14022a006  lea     r9, aIPdmmvidpntopo; "i_pDmmVidPnTopologyInterface != NULL"
0x14022a00d  mov     [rsp+160h+var_128], rsi
0x14022a012  mov     eax, 1010h
0x14022a017  mov     [rsp+160h+var_130], rsi
0x14022a01c  mov     r8d, r12d
0x14022a01f  mov     qword ptr [rsp+160h+var_138.Numerator], rsi
0x14022a024  mov     edx, 40002h
0x14022a029  xor     ecx, ecx
0x14022a02b  mov     [rsp+160h+var_140], rax
0x14022a030  mov     cs:WdLogGlobalForLineNumber, eax
0x14022a036  call    DxgkLogInternalTriageEvent
0x14022a03b  mov     r12, [rbp+60h+arg_40]
0x14022a042  test    r12, r12
0x14022a045  jnz     short loc_14022A091
0x14022a047  mov     ecx, r15d
0x14022a04a  call    cs:__imp_WdLogSingleEntry0
0x14022a051  nop     dword ptr [rax+rax+00h]
0x14022a056  mov     [rsp+40h], rsi
0x14022a05b  lea     r9, aIoPdisplaymode; "io_pDisplayModeInfo != NULL"
0x14022a062  mov     [rsp+160h+var_128], rsi
0x14022a067  mov     eax, 1011h
0x14022a06c  mov     [rsp+160h+var_130], rsi
0x14022a071  or      r8d, 0FFFFFFFFh
0x14022a075  mov     qword ptr [rsp+160h+var_138.Numerator], rsi
0x14022a07a  mov     edx, 40002h
0x14022a07f  xor     ecx, ecx
0x14022a081  mov     [rsp+160h+var_140], rax
0x14022a086  mov     cs:WdLogGlobalForLineNumber, eax
0x14022a08c  call    DxgkLogInternalTriageEvent
0x14022a091  mov     r15d, [rbp+60h+arg_30]
0x14022a098  cmp     r15d, 0FFFFFFFFh
0x14022a09c  jnz     short loc_14022A0E9
0x14022a09e  mov     ecx, 1
0x14022a0a3  call    cs:__imp_WdLogSingleEntry0
0x14022a0aa  nop     dword ptr [rax+rax+00h]
0x14022a0af  mov     [rsp+40h], rsi
0x14022a0b4  lea     r9, aIVidpnsourceid; "i_VidPnSourceId != D3DDDI_ID_UNINITIALI"...
0x14022a0bb  mov     [rsp+160h+var_128], rsi
0x14022a0c0  mov     eax, 1012h
0x14022a0c5  mov     [rsp+160h+var_130], rsi
0x14022a0ca  or      r8d, r15d
0x14022a0cd  mov     qword ptr [rsp+160h+var_138.Numerator], rsi
0x14022a0d2  mov     edx, 40002h
0x14022a0d7  xor     ecx, ecx
0x14022a0d9  mov     [rsp+160h+var_140], rax
0x14022a0de  mov     cs:WdLogGlobalForLineNumber, eax
0x14022a0e4  call    DxgkLogInternalTriageEvent
0x14022a0e9  cmp     [rbp+60h+arg_60], rsi
0x14022a0f0  jnz     short loc_14022A13E
0x14022a0f2  mov     ecx, 1
0x14022a0f7  call    cs:__imp_WdLogSingleEntry0
0x14022a0fe  nop     dword ptr [rax+rax+00h]
0x14022a103  mov     [rsp+40h], rsi
0x14022a108  lea     r9, aOPhfunctionali; "o_phFunctionalizedVidPn != NULL"
0x14022a10f  mov     [rsp+160h+var_128], rsi
0x14022a114  mov     eax, 1013h
0x14022a119  mov     [rsp+160h+var_130], rsi
0x14022a11e  or      r8d, 0FFFFFFFFh
0x14022a122  mov     qword ptr [rsp+160h+var_138.Numerator], rsi
0x14022a127  mov     edx, 40002h
0x14022a12c  xor     ecx, ecx
0x14022a12e  mov     [rsp+160h+var_140], rax
0x14022a133  mov     cs:WdLogGlobalForLineNumber, eax
0x14022a139  call    DxgkLogInternalTriageEvent
0x14022a13e  mov     rax, [rbx+78h]
0x14022a142  lea     rdx, [rbp+60h+arg_8]
0x14022a146  mov     rcx, r14
0x14022a149  mov     [rbp+60h+arg_8], rsi
0x14022a14d  call    _guard_dispatch_icall
0x14022a152  xor     ebx, ebx
0x14022a154  movsxd  rsi, eax
0x14022a157  test    eax, eax
0x14022a159  jns     short loc_14022A1B2
0x14022a15b  mov     r9, rsi
0x14022a15e  lea     ecx, [rbx+2]
0x14022a161  mov     r8, r14
0x14022a164  mov     rdx, r15
0x14022a167  call    cs:__imp_WdLogSingleEntry3
0x14022a16e  nop     dword ptr [rax+rax+00h]
0x14022a173  mov     [rsp+40h], rbx
0x14022a178  lea     r9, aFailedToDeterm_0; "Failed to determine number of paths ori"...
0x14022a17f  mov     [rsp+160h+var_128], rbx
0x14022a184  or      r8d, 0FFFFFFFFh
0x14022a188  mov     [rsp+160h+var_130], rsi
0x14022a18d  mov     edx, 40000h
0x14022a192  mov     qword ptr [rsp+160h+var_138.Numerator], r14
0x14022a197  xor     ecx, ecx
0x14022a199  mov     [rsp+160h+var_140], r15
0x14022a19e  mov     cs:WdLogGlobalForLineNumber, 101Ch
0x14022a1a8  call    DxgkLogInternalTriageEvent
0x14022a1ad  jmp     loc_14022A8E9
0x14022a1b2  mov     rdx, [rbp+60h+arg_8]; unsigned __int16
0x14022a1b6  lea     rcx, [rsp+160h+var_110]; this
0x14022a1bb  movzx   r8d, dx; unsigned __int16
0x14022a1bf  call    ??0CCD_TOPOLOGY@@QEAA@GG@Z; CCD_TOPOLOGY::CCD_TOPOLOGY(ushort,ushort)
0x14022a1c4  mov     rax, [rbp+60h+var_D0]
0x14022a1c8  test    rax, rax
0x14022a1cb  jz      short loc_14022A1D3
0x14022a1cd  movzx   eax, word ptr [rax+16h]
0x14022a1d1  jmp     short loc_14022A1D5
0x14022a1d3  mov     eax, ebx
0x14022a1d5  mov     rdx, [rbp+60h+arg_8]
0x14022a1d9  cmp     ax, dx
0x14022a1dc  jnb     short loc_14022A237
0x14022a1de  mov     ecx, 6
0x14022a1e3  call    cs:__imp_WdLogSingleEntry1
0x14022a1ea  nop     dword ptr [rax+rax+00h]
0x14022a1ef  mov     rax, [rbp+60h+arg_8]
0x14022a1f3  lea     r9, aFailedToAlloca_75; "Failed to allocate PathModality for 0x%"...
0x14022a1fa  mov     [rsp+40h], rbx
0x14022a1ff  or      r8d, 0FFFFFFFFh
0x14022a203  mov     [rsp+160h+var_128], rbx
0x14022a208  mov     edx, 40001h
0x14022a20d  mov     [rsp+160h+var_130], rbx
0x14022a212  xor     ecx, ecx
0x14022a214  mov     qword ptr [rsp+160h+var_138.Numerator], rbx
0x14022a219  mov     [rsp+160h+var_140], rax
0x14022a21e  mov     cs:WdLogGlobalForLineNumber, 1024h
0x14022a228  call    DxgkLogInternalTriageEvent
0x14022a22d  mov     esi, 0C0000017h
0x14022a232  jmp     loc_14022A8DF
0x14022a237  mov     rbx, [r13+19Ch]
0x14022a23e  lea     r9, [rbp+60h+arg_48]; unsigned int *
0x14022a245  mov     r8d, r15d; unsigned int
0x14022a248  mov     [rbp+60h+arg_48], 0
0x14022a252  mov     rdx, rdi; struct D3DKMDT_HVIDPN__ *
0x14022a255  mov     rcx, r13; this
0x14022a258  call    ?DmmGetMostImportantVidPnPathTargetsFromSource@@YAJQEAXPEAUD3DKMDT_HVIDPN__@@IQEAI@Z; DmmGetMostImportantVidPnPathTargetsFromSource(void * const,D3DKMDT_HVIDPN__ *,uint,uint * const)
0x14022a25d  movsxd  rsi, eax
0x14022a260  test    eax, eax
0x14022a262  jns     short loc_14022A2C5
0x14022a264  mov     r9, rsi
0x14022a267  mov     r8, r14
0x14022a26a  mov     rdx, r15
0x14022a26d  mov     ecx, 2
0x14022a272  call    cs:__imp_WdLogSingleEntry3
0x14022a279  nop     dword ptr [rax+rax+00h]
0x14022a27e  mov     qword ptr [rsp+40h], 0
0x14022a287  lea     r9, aFailedToFindTh; "Failed to find the most important paths"...
0x14022a28e  mov     [rsp+160h+var_128], 0
0x14022a297  mov     [rsp+160h+var_130], rsi
0x14022a29c  mov     qword ptr [rsp+160h+var_138.Numerator], r14
0x14022a2a1  mov     [rsp+160h+var_140], r15
0x14022a2a6  mov     cs:WdLogGlobalForLineNumber, 1033h
0x14022a2b0  or      r8d, 0FFFFFFFFh
0x14022a2b4  mov     edx, 40000h
0x14022a2b9  xor     ecx, ecx
0x14022a2bb  call    DxgkLogInternalTriageEvent
0x14022a2c0  jmp     loc_14022A8DF
0x14022a2c5  movdqa  xmm6, cs:__xmm@00000000000000010000000000000001
0x14022a2cd  xor     eax, eax
0x14022a2cf  mov     esi, eax
0x14022a2d1  mov     [rbp+60h+arg_30], eax
0x14022a2d7  cmp     rsi, [rbp+60h+arg_8]
0x14022a2db  jnb     loc_14022A604
0x14022a2e1  mov     edx, eax; unsigned int
0x14022a2e3  mov     [rbp+60h+arg_58], 0
0x14022a2ed  lea     rcx, [rsp+160h+var_110]; this
0x14022a2f2  mov     [rbp+60h+arg_50], 0
0x14022a2fc  call    ?GetPathDescriptor@CCD_TOPOLOGY@@QEBAPEBUD3DKMT_PATHMODALITY_DESCRIPTOR@@I@Z; CCD_TOPOLOGY::GetPathDescriptor(uint)
0x14022a301  mov     rdi, rax
0x14022a304  lea     r9, [rbp+60h+arg_50]
0x14022a30b  mov     rax, qword ptr [rbp+60h+arg_28.Numerator]
0x14022a312  lea     r8, [rbp+60h+arg_58]
0x14022a319  mov     edx, esi
0x14022a31b  mov     rcx, r14
0x14022a31e  mov     rax, [rax+80h]
0x14022a325  call    _guard_dispatch_icall
0x14022a32a  movsxd  rsi, eax
0x14022a32d  test    eax, eax
0x14022a32f  js      loc_14022A5BC
0x14022a335  mov     ecx, [rbp+60h+arg_58]
0x14022a33b  mov     [rdi+18h], ecx
0x14022a33e  mov     eax, [rbp+60h+arg_50]
0x14022a344  mov     [rdi+1Ch], eax
0x14022a347  mov     rax, 8700000000000h
0x14022a351  or      [rdi], rax
0x14022a354  mov     [rdi+10h], rbx
0x14022a358  cmp     [rbp+60h+arg_58], r15d
0x14022a35f  jnz     short loc_14022A373
0x14022a361  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x14022a366  cmp     byte ptr [rax+4A739h], 0
0x14022a36d  jnz     short loc_14022A373
0x14022a36f  xor     al, al
0x14022a371  jmp     short loc_14022A375
0x14022a373  mov     al, 1
0x14022a375  mov     r9, qword ptr [rbp+60h+arg_28.Numerator]; struct _DXGDMM_VIDPNTOPOLOGY_INTERFACE *
0x14022a37c  mov     rcx, r13; void *
0x14022a37f  mov     r8, [rbp+60h+arg_18]; struct _DXGDMM_VIDPN_INTERFACE *
0x14022a386  mov     rdx, [rbp+60h+arg_10]; struct D3DKMDT_HVIDPN__ *
0x14022a38d  mov     [rsp+40h], rdi; struct D3DKMT_PATHMODALITY_DESCRIPTOR *
0x14022a392  mov     byte ptr [rsp+160h+var_128], al; bool
0x14022a396  mov     eax, [rbp+60h+arg_50]
0x14022a39c  mov     dword ptr [rsp+160h+var_130], eax; unsigned int
0x14022a3a0  mov     eax, [rbp+60h+arg_58]
0x14022a3a6  mov     [rsp+160h+var_138.Numerator], eax; unsigned int
0x14022a3aa  mov     [rsp+160h+var_140], r14; struct D3DKMDT_HVIDPNTOPOLOGY__ *
0x14022a3af  call    ?ConvertVidPnPathToPathDescription@@YAJPEAXPEAUD3DKMDT_HVIDPN__@@QEBU_DXGDMM_VIDPN_INTERFACE@@QEBU_DXGDMM_VIDPNTOPOLOGY_INTERFACE@@PEAUD3DKMDT_HVIDPNTOPOLOGY__@@II_NPEAUD3DKMT_PATHMODALITY_DESCRIPTOR@@@Z; ConvertVidPnPathToPathDescription(void *,D3DKMDT_HVIDPN__ *,_DXGDMM_VIDPN_INTERFACE const * const,_DXGDMM_VIDPNTOPOLOGY_INTERFACE const * const,D3DKMDT_HVIDPNTOPOLOGY__ *,uint,uint,bool,D3DKMT_PATHMODALITY_DESCRIPTOR *)
0x14022a3b4  movsxd  rsi, eax
0x14022a3b7  test    eax, eax
0x14022a3b9  js      loc_14022A554
0x14022a3bf  cmp     [rbp+60h+arg_58], r15d
  ... truncated ...
```
