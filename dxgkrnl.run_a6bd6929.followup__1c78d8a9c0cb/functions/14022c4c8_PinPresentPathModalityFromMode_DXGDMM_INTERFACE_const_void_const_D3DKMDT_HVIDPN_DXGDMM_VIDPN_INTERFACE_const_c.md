# PinPresentPathModalityFromMode(_DXGDMM_INTERFACE const *,void * const,D3DKMDT_HVIDPN__ *,_DXGDMM_VIDPN_INTERFACE const * const,D3DKMDT_HVIDPNTOPOLOGY__ *,_DXGDMM_VIDPNTOPOLOGY_INTERFACE const * const,uint,unsigned __int64,_DXGK_DISPLAYMODE_INFO *,_D3DKMDT_VIDPN_PRESENT_PATH_SCALING,uchar,uchar,D3DKMDT_HVIDPN__ * *)

- ea: `0x14022c4c8`
- end: `0x14022cf68`
- name: `?PinPresentPathModalityFromMode@@YAJPEBU_DXGDMM_INTERFACE@@QEAXPEAUD3DKMDT_HVIDPN__@@QEBU_DXGDMM_VIDPN_INTERFACE@@PEAUD3DKMDT_HVIDPNTOPOLOGY__@@QEBU_DXGDMM_VIDPNTOPOLOGY_INTERFACE@@I_KPEAU_DXGK_DISPLAYMODE_INFO@@W4_D3DKMDT_VIDPN_PRESENT_PATH_SCALING@@EEPEAPEAU2@@Z`
- size: `2720`
- prototype: `int(const struct _DXGDMM_INTERFACE *, void *const, struct D3DKMDT_HVIDPN__ *, const struct _DXGDMM_VIDPN_INTERFACE *const, struct D3DKMDT_HVIDPNTOPOLOGY__ *, const struct _DXGDMM_VIDPNTOPOLOGY_INTERFACE *const, unsigned int, unsigned __int64, struct _DXGK_DISPLAYMODE_INFO *, enum _D3DKMDT_VIDPN_PRESENT_PATH_SCALING, unsigned __int8, unsigned __int8, struct D3DKMDT_HVIDPN__ **)`
- caller_count: `1`
- callee_count: `22`
- tags: `reparse_path, installer_update`

## callers

- `0x1401b7b98`

## callees

- `0x140012540`
- `0x14001b9c0`
- `0x140044dd4`
- `0x14004ff60`
- `0x1400a0cb0`
- `0x1400a1000`
- `0x1401d4c64`
- `0x14022c0e4`
- `0x14022c4c8`
- `0x14022d914`
- `0x14022dfac`
- `0x1402cb13c`
- `0x1402cb7b0`
- `0x1402cbdc0`
- `0x14032a5c4`
- `0x140339acc`
- `0x140339b74`
- `0x14034dffc`
- `0x14034e4f0`
- `0x14034e830`
- `0x14034f704`
- `0x14036b560`

## import_xrefs

- `watchdog!WdLogSingleEntry4` at `0x14022cbd1`
- `watchdog!WdLogSingleEntry4` at `0x14022cbd1`
- `watchdog!WdLogSingleEntry2` at `0x14022cc27`
- `watchdog!WdLogSingleEntry2` at `0x14022cc27`
- `watchdog!WdLogSingleEntry3` at `0x14022c7c7`
- `watchdog!WdLogSingleEntry3` at `0x14022c8d2`
- `watchdog!WdLogSingleEntry3` at `0x14022c7c7`
- `watchdog!WdLogSingleEntry3` at `0x14022c8d2`
- `watchdog!WdLogSingleEntry0` at `0x14022c515`
- `watchdog!WdLogSingleEntry0` at `0x14022c561`
- `watchdog!WdLogSingleEntry0` at `0x14022c5ad`
- `watchdog!WdLogSingleEntry0` at `0x14022c600`
- `watchdog!WdLogSingleEntry0` at `0x14022c655`
- `watchdog!WdLogSingleEntry0` at `0x14022c6aa`
- `watchdog!WdLogSingleEntry0` at `0x14022c703`
- `watchdog!WdLogSingleEntry0` at `0x14022c757`
- `watchdog!WdLogSingleEntry0` at `0x14022cee2`
- `watchdog!WdLogSingleEntry0` at `0x14022c515`
- `watchdog!WdLogSingleEntry0` at `0x14022c561`
- `watchdog!WdLogSingleEntry0` at `0x14022c5ad`
- `watchdog!WdLogSingleEntry0` at `0x14022c600`
- `watchdog!WdLogSingleEntry0` at `0x14022c655`
- `watchdog!WdLogSingleEntry0` at `0x14022c6aa`
- `watchdog!WdLogSingleEntry0` at `0x14022c703`
- `watchdog!WdLogSingleEntry0` at `0x14022c757`
- `watchdog!WdLogSingleEntry0` at `0x14022cee2`
- `watchdog!WdLogSingleEntry1` at `0x14022c843`
- `watchdog!WdLogSingleEntry1` at `0x14022ce0d`
- `watchdog!WdLogSingleEntry1` at `0x14022c843`
- `watchdog!WdLogSingleEntry1` at `0x14022ce0d`

## string_xrefs

- `0x14022c853`: `Failed to allocate PathModality for 0x%I64x paths`
- `0x14022c7d8`: `Failed to determine number of paths originating from source 0x%I64x in topology 0x%I64x (status = 0x%I64x)`
- `0x14022c8e7`: `Failed to find the most important paths originating from source 0x%I64x in topology 0x%I64x (status = 0x%I64x)`
- `0x14022cbe3`: `Failed to convert paths from source 0x%I64x to target 0x%I64x in VidPn topology 0x%I64x to PathsModality (status = 0x%I64x)`
- `0x14022cc44`: `Failed to enumerate the all the paths topology 0x%I64x (status = 0x%I64x)`
- `0x14022cef3`: `Failed to update refresh rate!`

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
0x14022c4c8  mov     rax, rsp
0x14022c4cb  mov     [rax+20h], r9
0x14022c4cf  mov     [rax+18h], r8
0x14022c4d3  mov     [rax+8], rcx
0x14022c4d7  push    rbp
0x14022c4d8  push    rbx
0x14022c4d9  push    rsi
0x14022c4da  push    rdi
0x14022c4db  push    r12
0x14022c4dd  push    r13
0x14022c4df  push    r14
0x14022c4e1  push    r15
0x14022c4e3  lea     rbp, [rax-68h]
0x14022c4e7  sub     rsp, 128h
0x14022c4ee  or      r12d, 0FFFFFFFFh
0x14022c4f2  movaps  xmmword ptr [rax-58h], xmm6
0x14022c4f6  xor     esi, esi
0x14022c4f8  mov     rbx, r9
0x14022c4fb  mov     rdi, r8
0x14022c4fe  mov     r13, rdx
0x14022c501  mov     r15d, 1
0x14022c507  mov     r14d, 40002h
0x14022c50d  test    rdx, rdx
0x14022c510  jnz     short loc_14022C559
0x14022c512  mov     ecx, r15d
0x14022c515  call    cs:__imp_WdLogSingleEntry0
0x14022c51c  nop     dword ptr [rax+rax+00h]
0x14022c521  mov     [rsp+40h], rsi
0x14022c526  lea     r9, aIHadapterNull; "i_hAdapter != NULL"
0x14022c52d  mov     [rsp+160h+var_128], rsi
0x14022c532  mov     eax, 100Ch
0x14022c537  mov     [rsp+160h+var_130], rsi
0x14022c53c  mov     r8d, r12d
0x14022c53f  mov     qword ptr [rsp+160h+var_138.Numerator], rsi
0x14022c544  mov     edx, r14d
0x14022c547  xor     ecx, ecx
0x14022c549  mov     [rsp+160h+var_140], rax
0x14022c54e  mov     cs:WdLogGlobalForLineNumber, eax
0x14022c554  call    DxgkLogInternalTriageEvent
0x14022c559  test    rdi, rdi
0x14022c55c  jnz     short loc_14022C5A5
0x14022c55e  mov     ecx, r15d
0x14022c561  call    cs:__imp_WdLogSingleEntry0
0x14022c568  nop     dword ptr [rax+rax+00h]
0x14022c56d  mov     [rsp+40h], rsi
0x14022c572  lea     r9, aIHvidpnNull; "i_hVidPn != NULL"
0x14022c579  mov     [rsp+160h+var_128], rsi
0x14022c57e  mov     eax, 100Dh
0x14022c583  mov     [rsp+160h+var_130], rsi
0x14022c588  mov     r8d, r12d
0x14022c58b  mov     qword ptr [rsp+160h+var_138.Numerator], rsi
0x14022c590  mov     edx, r14d
0x14022c593  xor     ecx, ecx
0x14022c595  mov     [rsp+160h+var_140], rax
0x14022c59a  mov     cs:WdLogGlobalForLineNumber, eax
0x14022c5a0  call    DxgkLogInternalTriageEvent
0x14022c5a5  test    rbx, rbx
0x14022c5a8  jnz     short loc_14022C5F1
0x14022c5aa  mov     ecx, r15d
0x14022c5ad  call    cs:__imp_WdLogSingleEntry0
0x14022c5b4  nop     dword ptr [rax+rax+00h]
0x14022c5b9  mov     [rsp+40h], rsi
0x14022c5be  lea     r9, aIPdmmvidpninte; "i_pDmmVidPnInterface != NULL"
0x14022c5c5  mov     [rsp+160h+var_128], rsi
0x14022c5ca  mov     eax, 100Eh
0x14022c5cf  mov     [rsp+160h+var_130], rsi
0x14022c5d4  mov     r8d, r12d
0x14022c5d7  mov     qword ptr [rsp+160h+var_138.Numerator], rsi
0x14022c5dc  mov     edx, r14d
0x14022c5df  xor     ecx, ecx
0x14022c5e1  mov     [rsp+160h+var_140], rax
0x14022c5e6  mov     cs:WdLogGlobalForLineNumber, eax
0x14022c5ec  call    DxgkLogInternalTriageEvent
0x14022c5f1  mov     r14, [rbp+60h+arg_20]
0x14022c5f8  test    r14, r14
0x14022c5fb  jnz     short loc_14022C646
0x14022c5fd  mov     ecx, r15d
0x14022c600  call    cs:__imp_WdLogSingleEntry0
0x14022c607  nop     dword ptr [rax+rax+00h]
0x14022c60c  mov     [rsp+40h], rsi
0x14022c611  lea     r9, aIHvidpntopolog; "i_hVidPnTopology != NULL"
0x14022c618  mov     [rsp+160h+var_128], rsi
0x14022c61d  mov     eax, 100Fh
0x14022c622  mov     [rsp+160h+var_130], rsi
0x14022c627  mov     r8d, r12d
0x14022c62a  mov     qword ptr [rsp+160h+var_138.Numerator], rsi
0x14022c62f  mov     edx, 40002h
0x14022c634  xor     ecx, ecx
0x14022c636  mov     [rsp+160h+var_140], rax
0x14022c63b  mov     cs:WdLogGlobalForLineNumber, eax
0x14022c641  call    DxgkLogInternalTriageEvent
0x14022c646  mov     rbx, qword ptr [rbp+60h+arg_28.Numerator]
0x14022c64d  test    rbx, rbx
0x14022c650  jnz     short loc_14022C69B
0x14022c652  mov     ecx, r15d
0x14022c655  call    cs:__imp_WdLogSingleEntry0
0x14022c65c  nop     dword ptr [rax+rax+00h]
0x14022c661  mov     [rsp+40h], rsi
0x14022c666  lea     r9, aIPdmmvidpntopo; "i_pDmmVidPnTopologyInterface != NULL"
0x14022c66d  mov     [rsp+160h+var_128], rsi
0x14022c672  mov     eax, 1010h
0x14022c677  mov     [rsp+160h+var_130], rsi
0x14022c67c  mov     r8d, r12d
0x14022c67f  mov     qword ptr [rsp+160h+var_138.Numerator], rsi
0x14022c684  mov     edx, 40002h
0x14022c689  xor     ecx, ecx
0x14022c68b  mov     [rsp+160h+var_140], rax
0x14022c690  mov     cs:WdLogGlobalForLineNumber, eax
0x14022c696  call    DxgkLogInternalTriageEvent
0x14022c69b  mov     r12, [rbp+60h+arg_40]
0x14022c6a2  test    r12, r12
0x14022c6a5  jnz     short loc_14022C6F1
0x14022c6a7  mov     ecx, r15d
0x14022c6aa  call    cs:__imp_WdLogSingleEntry0
0x14022c6b1  nop     dword ptr [rax+rax+00h]
0x14022c6b6  mov     [rsp+40h], rsi
0x14022c6bb  lea     r9, aIoPdisplaymode; "io_pDisplayModeInfo != NULL"
0x14022c6c2  mov     [rsp+160h+var_128], rsi
0x14022c6c7  mov     eax, 1011h
0x14022c6cc  mov     [rsp+160h+var_130], rsi
0x14022c6d1  or      r8d, 0FFFFFFFFh
0x14022c6d5  mov     qword ptr [rsp+160h+var_138.Numerator], rsi
0x14022c6da  mov     edx, 40002h
0x14022c6df  xor     ecx, ecx
0x14022c6e1  mov     [rsp+160h+var_140], rax
0x14022c6e6  mov     cs:WdLogGlobalForLineNumber, eax
0x14022c6ec  call    DxgkLogInternalTriageEvent
0x14022c6f1  mov     r15d, [rbp+60h+arg_30]
0x14022c6f8  cmp     r15d, 0FFFFFFFFh
0x14022c6fc  jnz     short loc_14022C749
0x14022c6fe  mov     ecx, 1
0x14022c703  call    cs:__imp_WdLogSingleEntry0
0x14022c70a  nop     dword ptr [rax+rax+00h]
0x14022c70f  mov     [rsp+40h], rsi
0x14022c714  lea     r9, aIVidpnsourceid; "i_VidPnSourceId != D3DDDI_ID_UNINITIALI"...
0x14022c71b  mov     [rsp+160h+var_128], rsi
0x14022c720  mov     eax, 1012h
0x14022c725  mov     [rsp+160h+var_130], rsi
0x14022c72a  or      r8d, r15d
0x14022c72d  mov     qword ptr [rsp+160h+var_138.Numerator], rsi
0x14022c732  mov     edx, 40002h
0x14022c737  xor     ecx, ecx
0x14022c739  mov     [rsp+160h+var_140], rax
0x14022c73e  mov     cs:WdLogGlobalForLineNumber, eax
0x14022c744  call    DxgkLogInternalTriageEvent
0x14022c749  cmp     [rbp+60h+arg_60], rsi
0x14022c750  jnz     short loc_14022C79E
0x14022c752  mov     ecx, 1
0x14022c757  call    cs:__imp_WdLogSingleEntry0
0x14022c75e  nop     dword ptr [rax+rax+00h]
0x14022c763  mov     [rsp+40h], rsi
0x14022c768  lea     r9, aOPhfunctionali; "o_phFunctionalizedVidPn != NULL"
0x14022c76f  mov     [rsp+160h+var_128], rsi
0x14022c774  mov     eax, 1013h
0x14022c779  mov     [rsp+160h+var_130], rsi
0x14022c77e  or      r8d, 0FFFFFFFFh
0x14022c782  mov     qword ptr [rsp+160h+var_138.Numerator], rsi
0x14022c787  mov     edx, 40002h
0x14022c78c  xor     ecx, ecx
0x14022c78e  mov     [rsp+160h+var_140], rax
0x14022c793  mov     cs:WdLogGlobalForLineNumber, eax
0x14022c799  call    DxgkLogInternalTriageEvent
0x14022c79e  mov     rax, [rbx+78h]
0x14022c7a2  lea     rdx, [rbp+60h+arg_8]
0x14022c7a6  mov     rcx, r14
0x14022c7a9  mov     [rbp+60h+arg_8], rsi
0x14022c7ad  call    _guard_dispatch_icall
0x14022c7b2  xor     ebx, ebx
0x14022c7b4  movsxd  rsi, eax
0x14022c7b7  test    eax, eax
0x14022c7b9  jns     short loc_14022C812
0x14022c7bb  mov     r9, rsi
0x14022c7be  lea     ecx, [rbx+2]
0x14022c7c1  mov     r8, r14
0x14022c7c4  mov     rdx, r15
0x14022c7c7  call    cs:__imp_WdLogSingleEntry3
0x14022c7ce  nop     dword ptr [rax+rax+00h]
0x14022c7d3  mov     [rsp+40h], rbx
0x14022c7d8  lea     r9, aFailedToDeterm_0; "Failed to determine number of paths ori"...
0x14022c7df  mov     [rsp+160h+var_128], rbx
0x14022c7e4  or      r8d, 0FFFFFFFFh
0x14022c7e8  mov     [rsp+160h+var_130], rsi
0x14022c7ed  mov     edx, 40000h
0x14022c7f2  mov     qword ptr [rsp+160h+var_138.Numerator], r14
0x14022c7f7  xor     ecx, ecx
0x14022c7f9  mov     [rsp+160h+var_140], r15
0x14022c7fe  mov     cs:WdLogGlobalForLineNumber, 101Ch
0x14022c808  call    DxgkLogInternalTriageEvent
0x14022c80d  jmp     loc_14022CF49
0x14022c812  mov     rdx, [rbp+60h+arg_8]; unsigned __int16
0x14022c816  lea     rcx, [rsp+160h+var_110]; this
0x14022c81b  movzx   r8d, dx; unsigned __int16
0x14022c81f  call    ??0CCD_TOPOLOGY@@QEAA@GG@Z; CCD_TOPOLOGY::CCD_TOPOLOGY(ushort,ushort)
0x14022c824  mov     rax, [rbp+60h+var_D0]
0x14022c828  test    rax, rax
0x14022c82b  jz      short loc_14022C833
0x14022c82d  movzx   eax, word ptr [rax+16h]
0x14022c831  jmp     short loc_14022C835
0x14022c833  mov     eax, ebx
0x14022c835  mov     rdx, [rbp+60h+arg_8]
0x14022c839  cmp     ax, dx
0x14022c83c  jnb     short loc_14022C897
0x14022c83e  mov     ecx, 6
0x14022c843  call    cs:__imp_WdLogSingleEntry1
0x14022c84a  nop     dword ptr [rax+rax+00h]
0x14022c84f  mov     rax, [rbp+60h+arg_8]
0x14022c853  lea     r9, aFailedToAlloca_75; "Failed to allocate PathModality for 0x%"...
0x14022c85a  mov     [rsp+40h], rbx
0x14022c85f  or      r8d, 0FFFFFFFFh
0x14022c863  mov     [rsp+160h+var_128], rbx
0x14022c868  mov     edx, 40001h
0x14022c86d  mov     [rsp+160h+var_130], rbx
0x14022c872  xor     ecx, ecx
0x14022c874  mov     qword ptr [rsp+160h+var_138.Numerator], rbx
0x14022c879  mov     [rsp+160h+var_140], rax
0x14022c87e  mov     cs:WdLogGlobalForLineNumber, 1024h
0x14022c888  call    DxgkLogInternalTriageEvent
0x14022c88d  mov     esi, 0C0000017h
0x14022c892  jmp     loc_14022CF3F
0x14022c897  mov     rbx, [r13+19Ch]
0x14022c89e  lea     r9, [rbp+60h+arg_48]; unsigned int *
0x14022c8a5  mov     r8d, r15d; unsigned int
0x14022c8a8  mov     [rbp+60h+arg_48], 0
0x14022c8b2  mov     rdx, rdi; struct D3DKMDT_HVIDPN__ *
0x14022c8b5  mov     rcx, r13; this
0x14022c8b8  call    ?DmmGetMostImportantVidPnPathTargetsFromSource@@YAJQEAXPEAUD3DKMDT_HVIDPN__@@IQEAI@Z; DmmGetMostImportantVidPnPathTargetsFromSource(void * const,D3DKMDT_HVIDPN__ *,uint,uint * const)
0x14022c8bd  movsxd  rsi, eax
0x14022c8c0  test    eax, eax
0x14022c8c2  jns     short loc_14022C925
0x14022c8c4  mov     r9, rsi
0x14022c8c7  mov     r8, r14
0x14022c8ca  mov     rdx, r15
0x14022c8cd  mov     ecx, 2
0x14022c8d2  call    cs:__imp_WdLogSingleEntry3
0x14022c8d9  nop     dword ptr [rax+rax+00h]
0x14022c8de  mov     qword ptr [rsp+40h], 0
0x14022c8e7  lea     r9, aFailedToFindTh; "Failed to find the most important paths"...
0x14022c8ee  mov     [rsp+160h+var_128], 0
0x14022c8f7  mov     [rsp+160h+var_130], rsi
0x14022c8fc  mov     qword ptr [rsp+160h+var_138.Numerator], r14
0x14022c901  mov     [rsp+160h+var_140], r15
0x14022c906  mov     cs:WdLogGlobalForLineNumber, 1033h
0x14022c910  or      r8d, 0FFFFFFFFh
0x14022c914  mov     edx, 40000h
0x14022c919  xor     ecx, ecx
0x14022c91b  call    DxgkLogInternalTriageEvent
0x14022c920  jmp     loc_14022CF3F
0x14022c925  movdqa  xmm6, cs:__xmm@00000000000000010000000000000001
0x14022c92d  xor     eax, eax
0x14022c92f  mov     esi, eax
0x14022c931  mov     [rbp+60h+arg_30], eax
0x14022c937  cmp     rsi, [rbp+60h+arg_8]
0x14022c93b  jnb     loc_14022CC64
0x14022c941  mov     edx, eax; unsigned int
0x14022c943  mov     [rbp+60h+arg_58], 0
0x14022c94d  lea     rcx, [rsp+160h+var_110]; this
0x14022c952  mov     [rbp+60h+arg_50], 0
0x14022c95c  call    ?GetPathDescriptor@CCD_TOPOLOGY@@QEBAPEBUD3DKMT_PATHMODALITY_DESCRIPTOR@@I@Z; CCD_TOPOLOGY::GetPathDescriptor(uint)
0x14022c961  mov     rdi, rax
0x14022c964  lea     r9, [rbp+60h+arg_50]
0x14022c96b  mov     rax, qword ptr [rbp+60h+arg_28.Numerator]
0x14022c972  lea     r8, [rbp+60h+arg_58]
0x14022c979  mov     edx, esi
0x14022c97b  mov     rcx, r14
0x14022c97e  mov     rax, [rax+80h]
0x14022c985  call    _guard_dispatch_icall
0x14022c98a  movsxd  rsi, eax
0x14022c98d  test    eax, eax
0x14022c98f  js      loc_14022CC1C
0x14022c995  mov     ecx, [rbp+60h+arg_58]
0x14022c99b  mov     [rdi+18h], ecx
0x14022c99e  mov     eax, [rbp+60h+arg_50]
0x14022c9a4  mov     [rdi+1Ch], eax
0x14022c9a7  mov     rax, 8700000000000h
0x14022c9b1  or      [rdi], rax
0x14022c9b4  mov     [rdi+10h], rbx
0x14022c9b8  cmp     [rbp+60h+arg_58], r15d
0x14022c9bf  jnz     short loc_14022C9D3
0x14022c9c1  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x14022c9c6  cmp     byte ptr [rax+4A739h], 0
0x14022c9cd  jnz     short loc_14022C9D3
0x14022c9cf  xor     al, al
0x14022c9d1  jmp     short loc_14022C9D5
0x14022c9d3  mov     al, 1
0x14022c9d5  mov     r9, qword ptr [rbp+60h+arg_28.Numerator]; struct _DXGDMM_VIDPNTOPOLOGY_INTERFACE *
0x14022c9dc  mov     rcx, r13; void *
0x14022c9df  mov     r8, [rbp+60h+arg_18]; struct _DXGDMM_VIDPN_INTERFACE *
0x14022c9e6  mov     rdx, [rbp+60h+arg_10]; struct D3DKMDT_HVIDPN__ *
0x14022c9ed  mov     [rsp+40h], rdi; struct D3DKMT_PATHMODALITY_DESCRIPTOR *
0x14022c9f2  mov     byte ptr [rsp+160h+var_128], al; bool
0x14022c9f6  mov     eax, [rbp+60h+arg_50]
0x14022c9fc  mov     dword ptr [rsp+160h+var_130], eax; unsigned int
0x14022ca00  mov     eax, [rbp+60h+arg_58]
0x14022ca06  mov     [rsp+160h+var_138.Numerator], eax; unsigned int
0x14022ca0a  mov     [rsp+160h+var_140], r14; struct D3DKMDT_HVIDPNTOPOLOGY__ *
0x14022ca0f  call    ?ConvertVidPnPathToPathDescription@@YAJPEAXPEAUD3DKMDT_HVIDPN__@@QEBU_DXGDMM_VIDPN_INTERFACE@@QEBU_DXGDMM_VIDPNTOPOLOGY_INTERFACE@@PEAUD3DKMDT_HVIDPNTOPOLOGY__@@II_NPEAUD3DKMT_PATHMODALITY_DESCRIPTOR@@@Z; ConvertVidPnPathToPathDescription(void *,D3DKMDT_HVIDPN__ *,_DXGDMM_VIDPN_INTERFACE const * const,_DXGDMM_VIDPNTOPOLOGY_INTERFACE const * const,D3DKMDT_HVIDPNTOPOLOGY__ *,uint,uint,bool,D3DKMT_PATHMODALITY_DESCRIPTOR *)
0x14022ca14  movsxd  rsi, eax
0x14022ca17  test    eax, eax
0x14022ca19  js      loc_14022CBB4
0x14022ca1f  cmp     [rbp+60h+arg_58], r15d
  ... truncated ...
```
