# CxCodeVideoProcMFTDataHandler::OnBeginStreaming2(int,int)

- ea: `0x1800244c4`
- end: `0x180025a12`
- name: `?OnBeginStreaming2@CxCodeVideoProcMFTDataHandler@@AEAAJHH@Z`
- size: `5454`
- prototype: `__int64 __fastcall(CxCodeVideoProcMFTDataHandler *this, int, unsigned int)`
- caller_count: `2`
- callee_count: `49`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180024400`
- `0x18002bf40`

## callees

- `0x180004f88`
- `0x180005d44`
- `0x180007148`
- `0x180008c0c`
- `0x180008db8`
- `0x180009470`
- `0x1800094d4`
- `0x180009b2c`
- `0x18000a09c`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x180014b78`
- `0x180014be0`
- `0x18001ca44`
- `0x18001cb34`
- `0x18001f174`
- `0x18002106c`
- `0x18002336c`
- `0x18002427c`
- `0x180024370`
- `0x1800244c4`
- `0x180025a18`
- `0x180025c68`
- `0x180029350`
- `0x1800300ac`
- `0x1800359a8`
- `0x1800364d0`
- `0x180037030`
- `0x1800371c4`
- `0x1800371e8`
- `0x18003728c`
- `0x180041984`
- `0x18004a1c4`
- `0x180054140`
- `0x180054ee4`
- `0x1800599b8`
- `0x1800599dc`
- `0x180059cfc`
- `0x18005d29c`
- `0x18005f10c`
- `0x180066ad8`
- `0x180066c4c`
- `0x180066e70`
- `0x180066ee0`
- `0x180066f48`
- `0x180066fc4`
- `0x1800b1790`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180024873`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180024873`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x180024bb8`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x180024bb8`

## string_xrefs

- `0x180025672`: `Internal mis-configuration`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcMFTDataHandler::OnBeginStreaming2(
        CxCodeVideoProcMFTDataHandler *this,
        int a2,
        unsigned int a3)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v7; // ebx
  __int128 v8; // xmm0
  __int64 v9; // rcx
  int v10; // eax
  struct IMFAttributes *v11; // rcx
  unsigned int VideoProcessingAlgorithm; // eax
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // rcx
  int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // r9
  int RendererEffect; // ebx
  int v34; // edx
  int v35; // r14d
  int v36; // r9d
  int v37; // ecx
  int v38; // eax
  unsigned int v39; // edi
  __int64 v40; // rdx
  CxCodeVideoProcMFTDataHandler *v41; // rcx
  const struct MFMEDIATYPEUtils::VideoColorSpaceAttributes *v42; // r8
  unsigned int v43; // r13d
  int v44; // eax
  unsigned int v45; // ebx
  int v46; // r15d
  int v47; // edi
  int v48; // r11d
  unsigned int v49; // r10d
  int v50; // ebx
  __m128i v51; // xmm1
  int v52; // xmm2_4
  __int64 v53; // xmm3_8
  _QWORD *v54; // rdi
  unsigned int v55; // edx
  __int64 v56; // rdx
  __int64 v57; // rdx
  CxCodeVideoProcMFTDataHandler *v58; // rax
  const wchar_t *v59; // rdx
  int v60; // r10d
  __int64 v61; // rdx
  __int128 v62; // xmm0
  _MFVideoTransferFunction v63; // r10d
  _MFVideoTransferFunction *v64; // rcx
  unsigned int v65; // eax
  _MFVideoTransferFunction v66; // r8d
  __int64 v67; // xmm1_8
  __int64 v68; // r8
  _MFVideoTransferFunction v69; // r10d
  _MFVideoTransferFunction *v70; // rcx
  int v71; // r9d
  int v72; // edx
  int v73; // ecx
  int v74; // ecx
  int v75; // ecx
  int v76; // ecx
  int v77; // ecx
  int v78; // ecx
  int v79; // ecx
  CxCodeVideoProcMFTDataHandler *v80; // rcx
  CxCodeVideoProcMFTDataHandler *v81; // rcx
  CxCodeVideoProcMFTDataHandler *v82; // rcx
  CxCodeVideoProcMFTDataHandler *v83; // rcx
  CxCodeVideoProcMFTDataHandler *v84; // rcx
  CxCodeVideoProcMFTDataHandler *v85; // rcx
  CxCodeVideoProcMFTDataHandler *v86; // rcx
  DWORD v87; // r8d
  DWORD v88; // edx
  CxCodeVideoProcMFTDataHandler *v89; // rcx
  CxCodeVideoProcMFTDataHandler *v90; // rcx
  unsigned int v91; // r8d
  CxCodeVideoProcD3DDataHandler *v92; // rcx
  int D3DVideoProcessor; // eax
  CxCodeVideoProcMFTDataHandler *v94; // rcx
  __int128 v95; // xmm0
  struct tagRECT *v96; // rdi
  bool v97; // zf
  char *v98; // rax
  __int128 v99; // xmm0
  char *v100; // rax
  CxCodeVideoProcMFTDataHandler *v101; // rcx
  int v102; // eax
  __int64 v103; // rcx
  char *v104; // rax
  int v105; // eax
  bool v106; // zf
  char *v107; // rax
  __int128 v108; // xmm0
  _BYTE v110[4]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v111; // [rsp+74h] [rbp-8Ch] BYREF
  int v112; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v113[4]; // [rsp+80h] [rbp-80h] BYREF
  int v114; // [rsp+84h] [rbp-7Ch]
  int v115; // [rsp+88h] [rbp-78h]
  __m128i v116; // [rsp+90h] [rbp-70h]
  int v117; // [rsp+A0h] [rbp-60h]
  int v118; // [rsp+A8h] [rbp-58h]
  __int128 v119; // [rsp+B0h] [rbp-50h]
  CxCodeVideoProcMFTDataHandler *v120; // [rsp+C0h] [rbp-40h]
  _BYTE v121[4]; // [rsp+D0h] [rbp-30h] BYREF
  int v122; // [rsp+D4h] [rbp-2Ch]
  int v123; // [rsp+D8h] [rbp-28h]
  __m128i v124; // [rsp+E0h] [rbp-20h]
  int v125; // [rsp+F0h] [rbp-10h]
  int v126; // [rsp+F8h] [rbp-8h]
  __int128 v127; // [rsp+100h] [rbp+0h]
  CxCodeVideoProcMFTDataHandler *v128; // [rsp+110h] [rbp+10h]
  _BYTE v129[20]; // [rsp+120h] [rbp+20h] BYREF
  unsigned int v130; // [rsp+134h] [rbp+34h]
  unsigned int v131; // [rsp+138h] [rbp+38h]
  int v132; // [rsp+13Ch] [rbp+3Ch]
  int v133; // [rsp+140h] [rbp+40h]
  __int64 v134; // [rsp+150h] [rbp+50h]
  __int64 v135; // [rsp+158h] [rbp+58h]
  _MFVideoTransferFunction v136[4]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int64 v137; // [rsp+180h] [rbp+80h]

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v110,
    "CxCodeVideoProcMFTDataHandler::OnBeginStreaming2",
    2751);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 388) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 388) + 296LL))(*((_QWORD *)this + 388));
    v8 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _MFVideoTransferFunction *))(**((_QWORD **)this + 388) + 280LL))(
                      *((_QWORD *)this + 388),
                      v136);
    *((_DWORD *)ThreadRelativeContext + 504) = v7;
    *((_OWORD *)ThreadRelativeContext + 125) = v8;
  }
  v9 = *((_QWORD *)this + 28);
  *((_DWORD *)this + 784) = 0;
  v10 = MFGetAttributeUINT32(v9, &MF_XVP_DISABLE_FRC, 0);
  v11 = (struct IMFAttributes *)*((_QWORD *)this + 28);
  *((_DWORD *)this + 286) = v10;
  VideoProcessingAlgorithm = GetVideoProcessingAlgorithm(v11);
  v13 = *((_QWORD *)this + 28);
  *((_DWORD *)this + 38) = VideoProcessingAlgorithm;
  v14 = MFGetAttributeUINT32(v13, MF_XVP_CALLER_ALLOCATES_OUTPUT, 0);
  v15 = *((_QWORD *)this + 28);
  *((_DWORD *)this + 283) = v14;
  v16 = MFGetAttributeUINT32(v15, MF_LOW_LATENCY, 0);
  v17 = *((_QWORD *)this + 28);
  *((_DWORD *)this + 282) = v16;
  v18 = MFGetAttributeUINT32(v17, qword_1800DF0D8, 0);
  v19 = *((_QWORD *)this + 28);
  *((_DWORD *)this + 370) = v18;
  v20 = MFGetAttributeUINT32(v19, qword_1800DF098, 2);
  v21 = *((_QWORD *)this + 28);
  *((_DWORD *)this + 391) = v20;
  v22 = MFGetAttributeUINT32(v21, qword_1800DF088, 1);
  v23 = *((_QWORD *)this + 28);
  *((_DWORD *)this + 392) = v22;
  v24 = MFGetAttributeUINT32(v23, MF_XVP_SAMPLE_LOCK_TIMEOUT, 0xFFFFFFFFLL);
  v25 = *((_QWORD *)this + 28);
  *((_DWORD *)this + 378) = v24;
  v26 = MFGetAttributeUINT32(v25, MF_XVP_DEFERRED_VP_DESTRUCTION, 0);
  v27 = *((_QWORD *)this + 28);
  *((_DWORD *)this + 381) = v26;
  v28 = MFGetAttributeUINT32(v27, qword_1800DF0C8, 0);
  v29 = *((_QWORD *)this + 28);
  *((_DWORD *)this + 382) = v28;
  v30 = MFGetAttributeUINT32(v29, qword_1800DF078, 1);
  v31 = *((_QWORD *)this + 28);
  *((_BYTE *)this + 1516) = v30 != 0;
  *((_BYTE *)this + 1517) = (unsigned int)MFGetAttributeUINT32(v31, qword_1800DF068, 0) != 0;
  *((_DWORD *)this + 377) = *((_DWORD *)this + 791);
  if ( !*((_QWORD *)this + 384) )
  {
    if ( !*((_DWORD *)this + 281) )
    {
LABEL_13:
      *((_DWORD *)this + 250) = 0;
      goto LABEL_14;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 3072);
    XVPCreateVideoSettingsChangeWatcher((struct RegistryKeyWatcher **)this + 384);
  }
  if ( !*((_DWORD *)this + 281) || !a3 )
    goto LABEL_13;
  if ( *((_DWORD *)this + 250) == 1
    && (int)MFLightSensorReader::Initialize(
              (CxCodeVideoProcMFTDataHandler *)((char *)this + 1016),
              *((struct IMFTelemetrySession **)this + 388)) < 0 )
  {
    if ( byte_180153DE0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 42), 174, &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids, this);
    goto LABEL_13;
  }
  if ( (!*((_BYTE *)this + 1097) || !*((_BYTE *)this + 1096)) && (unsigned __int8)byte_180153DE0 >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 42), 175, &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids, this);
LABEL_14:
  CxCodeVideoProcMFTDataHandler::GetDebugMode(this);
  if ( (unsigned int)MFGetAttributeUINT32(*((_QWORD *)this + 28), qword_1800DF0B8, 0) )
    *((_DWORD *)this + 371) = 1;
  if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
  {
    WPP_SF_qdddd(
      *((_QWORD *)WPP_GLOBAL_Control + 42),
      176,
      &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
      this,
      *((_DWORD *)this + 286),
      *((_DWORD *)this + 282),
      *((_DWORD *)this + 38),
      *((_DWORD *)this + 281));
    if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
      WPP_SF_qdddd(
        *((_QWORD *)WPP_GLOBAL_Control + 42),
        177,
        &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
        this,
        *((_DWORD *)this + 75),
        *((_DWORD *)this + 74),
        *((_DWORD *)this + 163),
        *((_DWORD *)this + 162));
  }
  if ( *((_DWORD *)this + 281) && *((_DWORD *)this + 38) == 1 )
  {
    RendererEffect = -2147467259;
    RoOriginateErrorW(
      2147500037LL,
      98,
      L"XVP playback mode and MF_VIDEO_PROCESSOR_ALGORITHM_MRF_CRF_444 can not be enabled at the same time",
      v32);
    goto LABEL_283;
  }
  CxCodeVideoProcSampleInfo::Reset((CxCodeVideoProcMFTDataHandler *)((char *)this + 384), 0);
  CxCodeVideoProcSampleInfo::Reset((CxCodeVideoProcMFTDataHandler *)((char *)this + 832), v34);
  *(_QWORD *)((char *)this + 1148) = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 2376);
  if ( !CxCodeVideoProcMFTDataHandler::IsWarpMode(this) )
  {
    if ( a3 )
    {
      RendererEffect = CxCodeVideoProcMFTDataHandler::CheckD3DVideoDevice(this);
      if ( RendererEffect )
        goto LABEL_96;
    }
    if ( !*((_QWORD *)this + 389) )
    {
      if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 42), 178, &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids, this);
      a3 = 0;
    }
  }
  RendererEffect = CxCodeVideoProcMFTDataHandler::LoadRendererEffect(this);
  if ( RendererEffect
    || *((_QWORD *)this + 217) && (RendererEffect = CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect(this)) != 0
    || (RendererEffect = CxCodeVideoProcMFTDataHandler::ConfigureConversions(this, a2, a3)) != 0 )
  {
LABEL_96:
    if ( RendererEffect < 0 )
      goto LABEL_97;
LABEL_282:
    *((_DWORD *)this + 279) = 1;
    goto LABEL_283;
  }
  v35 = 1448433985;
  if ( a3
    || (v36 = *((_DWORD *)this + 761)) == 0
    || !*((_BYTE *)this + 1516)
    || (v37 = *((_DWORD *)this + 603)) == 0
    || (v38 = *((_DWORD *)this + 63), v38 != 21) && v38 != 1448433985 )
  {
    memset_0(v113, 0, 0x50u);
    memset_0(v121, 0, 0x50u);
    v39 = *((_DWORD *)this + 63);
    if ( (unsigned int)CtypeSurfaces::Find(v39, (struct TypeSurface *)v113)
      || (unsigned int)CtypeSurfaces::Find(*((_DWORD *)this + 154), (struct TypeSurface *)v121) )
    {
      goto LABEL_282;
    }
    if ( a3 )
    {
      if ( !v118 || !v126 )
      {
        if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 42), 190, &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids, this);
        MF::OriginateError<57>(2147500033LL, L"Conversion unavailable: Format not supported in D3D/WARP");
        goto LABEL_117;
      }
      goto LABEL_225;
    }
    v43 = 0;
    v111 = 0;
    if ( *((_DWORD *)this + 38) )
    {
      if ( v39 == 1448433985 )
      {
        *((_DWORD *)this + 760) = 0;
      }
      else
      {
        *((_DWORD *)this + 760) = 2;
        RendererEffect = CtypeConversions::Find(
                           v39,
                           0x56555941u,
                           (int (**)(const struct tagRECT *, const struct ParameterBase *))this + 317,
                           1,
                           0);
        if ( RendererEffect )
          goto LABEL_96;
      }
      v55 = *((_DWORD *)this + 154);
      if ( v55 != 1448433985 )
      {
        RendererEffect = CtypeConversions::Find(
                           0x56555941u,
                           v55,
                           (int (**)(const struct tagRECT *, const struct ParameterBase *))this + 318,
                           1,
                           0);
        if ( RendererEffect )
          goto LABEL_96;
      }
      memset_0(v129, 0, 0x50u);
      RendererEffect = CtypeSurfaces::Find(1448433985, (struct TypeSurface *)v129);
      if ( RendererEffect )
        goto LABEL_96;
      v54 = (_QWORD *)((char *)this + 2440);
      *((_DWORD *)this + 606) = v130;
      *((_DWORD *)this + 607) = v131;
      *((_DWORD *)this + 608) = v132;
      *((_DWORD *)this + 609) = v133;
      *((_QWORD *)this + 305) = v134;
      if ( *((_QWORD *)this + 343) )
        *((_QWORD *)this + 343) = v135;
      if ( *((_DWORD *)this + 758) )
      {
        v56 = *((unsigned int *)this + 388);
        *((_DWORD *)this + 758) = 3;
        RendererEffect = CTypeRotation::Find(v41, v56, (char *)this + 2752);
        if ( RendererEffect )
          goto LABEL_96;
      }
      if ( *((_DWORD *)this + 390) )
      {
        v57 = *((unsigned int *)this + 307);
        *((_DWORD *)this + 390) = 3;
        RendererEffect = CTypeMirror::Find(1448433985, v57, (char *)this + 2880);
        if ( RendererEffect )
          goto LABEL_96;
      }
LABEL_108:
      if ( *((_DWORD *)this + 759) )
      {
        *((_DWORD *)this + 759) = 3;
        v40 = 3;
        v58 = v128;
        if ( !v128 )
        {
          v40 = 2;
          *((_DWORD *)this + 759) = 2;
        }
        v41 = v120;
        if ( v120 || v58 )
        {
          if ( (_DWORD)v40 == 2 )
            v58 = v120;
          *((_QWORD *)this + 319) = v58;
        }
        else
        {
          if ( *((_BYTE *)this + 1517) )
          {
            if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
              WPP_SF_q(
                *((_QWORD *)WPP_GLOBAL_Control + 42),
                183,
                &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
                this);
            MF::OriginateError<60>(v41, L"Conversion unavailable: No suitable range conversion found.");
            goto LABEL_117;
          }
          *((_DWORD *)this + 759) = 0;
          v54 = (_QWORD *)((char *)this + 2440);
        }
      }
      *((_QWORD *)this + 342) = CopySurface;
      if ( *((_DWORD *)this + 761) && !*v54 )
      {
        if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
          WPP_SF_qDD(
            *((_QWORD *)WPP_GLOBAL_Control + 42),
            184,
            v42,
            this,
            *((_DWORD *)this + 63),
            *((_DWORD *)this + 154));
        v59 = L"Conversion unavailable: No suitable scaler found.";
LABEL_127:
        MF::OriginateError<50>(v41, v59);
LABEL_117:
        RendererEffect = -1072861841;
        goto LABEL_97;
      }
      if ( (!v118 || !v126) && !*((_BYTE *)this + 1517) )
        goto LABEL_225;
      if ( *((_DWORD *)this + 758) && !*((_QWORD *)this + 344) )
      {
        if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
          WPP_SF_qDD(
            *((_QWORD *)WPP_GLOBAL_Control + 42),
            185,
            v42,
            this,
            *((_DWORD *)this + 63),
            *((_DWORD *)this + 154));
        MF::OriginateError<51>(2147500033LL, L"Conversion unavailable: No suitable rotater found.");
        goto LABEL_117;
      }
      if ( *((_DWORD *)this + 390) && !*((_QWORD *)this + 360) )
      {
        if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
          WPP_SF_qDD(
            *((_QWORD *)WPP_GLOBAL_Control + 42),
            186,
            v42,
            this,
            *((_DWORD *)this + 63),
            *((_DWORD *)this + 154));
        v59 = L"Conversion unavailable: No suitable mirror found.";
        goto LABEL_127;
      }
      if ( !(unsigned int)MFMEDIATYPEUtils::MFMEDIATYPEUtilsHelper::IsColorSpaceConversionRequired(
                            (CxCodeVideoProcMFTDataHandler *)((char *)this + 536),
                            (CxCodeVideoProcMFTDataHandler *)((char *)this + 780),
                            v42)
        && *((_DWORD *)this + 94) == *((_DWORD *)this + 186)
        || *((_DWORD *)this + 38) )
      {
        goto LABEL_225;
      }
      v42 = (const struct MFMEDIATYPEUtils::VideoColorSpaceAttributes *)*((unsigned int *)this + 760);
      if ( !(_DWORD)v42 )
      {
        if ( *((_DWORD *)this + 759) )
        {
LABEL_156:
          if ( !(_DWORD)v42 )
          {
            v62 = *(_OWORD *)((char *)this + 780);
            v137 = (unsigned int)*(_QWORD *)((char *)this + 796);
            *(_OWORD *)v136 = v62;
            if ( !*((_BYTE *)this + 1517) )
            {
              if ( (unsigned int)IsLegacyTransferFunction(&v136[2])
                && (unsigned int)IsLegacyTransferFunction((const enum _MFVideoTransferFunction *)this + 136) )
              {
                v136[2] = *v64;
              }
              if ( *((_DWORD *)this + 135) < v63 && v136[1] < v63 )
              {
                v136[1] = *((_MFVideoTransferFunction *)this + 135);
                v136[3] = *((_MFVideoTransferFunction *)this + 137);
              }
            }
            if ( (unsigned int)MFMEDIATYPEUtils::MFMEDIATYPEUtilsHelper::IsColorSpaceConversionRequired(
                                 (CxCodeVideoProcMFTDataHandler *)((char *)this + 536),
                                 (const struct MFMEDIATYPEUtils::VideoColorSpaceAttributes *)v136,
                                 v42) )
            {
              if ( (unsigned __int8)byte_180153DE0 < 0x20u )
                goto LABEL_154;
              v61 = 188;
              goto LABEL_153;
            }
          }
LABEL_167:
          if ( !*((_DWORD *)this + 760) || *((_DWORD *)this + 759) )
            goto LABEL_225;
          v65 = *((_DWORD *)this + 139);
          v66 = *((_DWORD *)this + 134);
          v67 = *(_QWORD *)((char *)this + 796);
          *(_OWORD *)v136 = *(_OWORD *)((char *)this + 780);
          v136[0] = v66;
          v137 = __PAIR64__(v65, v67);
          if ( (unsigned int)IsLegacyTransferFunction(&v136[2])
            && (unsigned int)IsLegacyTransferFunction((const enum _MFVideoTransferFunction *)this + 136) )
          {
            v136[2] = *v70;
          }
          if ( (_DWORD)v68 == *((_DWORD *)this + 195) && *((_DWORD *)this + 135) < v69 && v136[1] < v69 )
          {
            v136[1] = *((_MFVideoTransferFunction *)this + 135);
            goto LABEL_219;
          }
          v71 = *((_DWORD *)this + 135);
          v72 = 6;
          if ( v71 > 6 )
          {
            switch ( v71 )
            {
              case 7:
                v68 = 16;
                break;
              case 8:
                v68 = 32;
                break;
              case 9:
                v68 = 64;
                break;
              case 10:
                v68 = 128;
                break;
              default:
LABEL_187:
                v68 = 0;
                break;
            }
          }
          else
          {
            if ( v71 != 6 )
            {
              if ( v71 )
              {
                switch ( v71 )
                {
                  case 2:
                    v68 = 1;
                    goto LABEL_197;
                  case 3:
                    v68 = 2;
                    goto LABEL_197;
                  case 4:
                    v68 = 4;
                    goto LABEL_197;
                  case 5:
                    v68 = 6;
                    goto LABEL_197;
                }
              }
              goto LABEL_187;
            }
            v68 = 8;
          }
LABEL_197:
          v73 = *((_DWORD *)this + 196);
          if ( v73 > 6 )
          {
            v77 = v73 - 7;
            if ( !v77 )
            {
              v72 = 16;
              goto LABEL_217;
            }
            v78 = v77 - 1;
            if ( !v78 )
            {
              v72 = 32;
              goto LABEL_217;
            }
            v79 = v78 - 1;
            if ( !v79 )
            {
              v72 = 64;
              goto LABEL_217;
            }
            if ( v79 == 1 )
            {
              v72 = 128;
              goto LABEL_217;
            }
          }
          else
          {
            if ( v73 == 6 )
            {
              v72 = 8;
              goto LABEL_217;
            }
            if ( v73 )
            {
              v74 = v73 - 2;
              if ( !v74 )
              {
                v72 = 1;
                goto LABEL_217;
              }
              v75 = v74 - 1;
              if ( !v75 )
              {
                v72 = 2;
                goto LABEL_217;
              }
              v76 = v75 - 1;
              if ( !v76 )
              {
                v72 = 4;
                goto LABEL_217;
              }
              if ( v76 == 1 )
              {
LABEL_217:
                if ( (v72 & v43) == 0 || ((unsigned int)v68 & v43) == 0 )
                  goto LABEL_220;
                v136[1] = *((_MFVideoTransferFunction *)this + 135);
LABEL_219:
                v136[3] = *((_MFVideoTransferFunction *)this + 137);
LABEL_220:
                if ( (unsigned int)MFMEDIATYPEUtils::MFMEDIATYPEUtilsHelper::IsColorSpaceConversionRequired(
                                     (CxCodeVideoProcMFTDataHandler *)((char *)this + 536),
                                     (const struct MFMEDIATYPEUtils::VideoColorSpaceAttributes *)v136,
                                     (const struct MFMEDIATYPEUtils::VideoColorSpaceAttributes *)v68) )
                {
                  if ( (unsigned __int8)byte_180153DE0 < 0x20u )
                    goto LABEL_154;
                  v61 = 189;
                  goto LABEL_153;
                }
LABEL_225:
                if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
                {
                  WPP_SF_qDDddddddd(
                    *((_QWORD *)WPP_GLOBAL_Control + 42),
                    v40,
                    v42,
                    this,
                    *((_DWORD *)this + 63),
                    *((_DWORD *)this + 154),
                    *((_DWORD *)this + 761),
                    *((_DWORD *)this + 758),
                    *((_DWORD *)this + 388),
                    *((_DWORD *)this + 390),
                    *((_DWORD *)this + 307),
                    *((_DWORD *)this + 67),
                    *((_DWORD *)this + 68));
                  if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
                    WPP_SF_qdddddd(
                      *((_QWORD *)WPP_GLOBAL_Control + 42),
                      192,
                      &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
                      this,
                      *((_DWORD *)this + 760),
                      *((_DWORD *)this + 759),
                      *((_DWORD *)this + 139),
                      *((_DWORD *)this + 200),
                      *((_DWORD *)this + 764),
                      *((_DWORD *)this + 763));
                }
                CxCodeVideoProcMFTDataHandler::CleanupIntermediateBuffer(
                  v41,
                  (CxCodeVideoProcMFTDataHandler *)((char *)this + 2456));
                CxCodeVideoProcMFTDataHandler::CleanupIntermediateBuffer(
                  v80,
                  (CxCodeVideoProcMFTDataHandler *)((char *)this + 2560));
                CxCodeVideoProcMFTDataHandler::CleanupIntermediateBuffer(
                  v81,
                  (CxCodeVideoProcMFTDataHandler *)((char *)this + 2760));
                CxCodeVideoProcMFTDataHandler::CleanupIntermediateBuffer(
                  v82,
                  (CxCodeVideoProcMFTDataHandler *)((char *)this + 2824));
                CxCodeVideoProcMFTDataHandler::CleanupIntermediateBuffer(
                  v83,
                  (CxCodeVideoProcMFTDataHandler *)((char *)this + 2680));
                CxCodeVideoProcMFTDataHandler::CleanupIntermediateBuffer(
                  v84,
                  (CxCodeVideoProcMFTDataHandler *)((char *)this + 2896));
                CxCodeVideoProcMFTDataHandler::CleanupIntermediateBuffer(
                  v85,
                  (CxCodeVideoProcMFTDataHandler *)((char *)this + 2616));
                CxCodeVideoProcMFTDataHandler::CleanupIntermediateBuffer(
                  v86,
                  (CxCodeVideoProcMFTDataHandler *)((char *)this + 2976));
                v87 = *((_DWORD *)this + 163);
                v88 = *((_DWORD *)this + 154);
                v112 = 0;
                RendererEffect = CxCodeVideoProcMFTDataHandler::GetDefaultStrideForType(
                                   v89,
                                   v88,
                                   v87,
                                   (unsigned int *)&v112);
                if ( RendererEffect )
                  goto LABEL_96;
                if ( (unsigned int)CxCodeVideoProcMFTDataHandler::CalcMinSampleSize(
                                     v90,
                                     *((_DWORD *)this + 154),
                                     *((_DWORD *)this + 162),
                                     v112,
                                     (unsigned int *)this + 246) )
                  goto LABEL_282;
                *(_DWORD *)(*((_QWORD *)this + 1) + 268LL) = *((_DWORD *)this + 246);
                if ( a3 )
                {
                  v92 = (CxCodeVideoProcD3DDataHandler *)*((_QWORD *)this + 21);
                  if ( !v92 )
                  {
                    if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
                      WPP_SF_q(
                        *((_QWORD *)WPP_GLOBAL_Control + 42),
                        193,
                        &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
                        this);
                    RendererEffect = -2147467261;
                    MF::OriginateError<27>(2147500035LL, L"Internal mis-configuration");
                    goto LABEL_97;
                  }
                  D3DVideoProcessor = CxCodeVideoProcD3DDataHandler::CreateD3DVideoProcessor(v92);
LABEL_278:
                  RendererEffect = D3DVideoProcessor;
                  goto LABEL_96;
                }
                if ( !*((_DWORD *)this + 49) )
                {
                  *(GUID *)v136 = GUID_00000000_0000_0000_0000_000000000000;
                  RendererEffect = CxCodeVideoProcThreadPool::Init(
                                     (CxCodeVideoProcMFTDataHandler *)((char *)this + 176),
                                     (struct _GUID *)v136,
                                     v91);
                  if ( RendererEffect )
                    goto LABEL_96;
                }
                RendererEffect = CxCodeVideoProcMFTDataHandler::SetupScaling(this);
                if ( RendererEffect )
                  goto LABEL_96;
                if ( *((_DWORD *)this + 763) )
                {
                  if ( *((_DWORD *)this + 38) == 1
                    || *((_DWORD *)this + 758) == 3
                    || *((_DWORD *)this + 390) == 3
                    || *((_DWORD *)this + 760) == 3 )
                  {
                    v97 = *((_DWORD *)this + 758) == 2;
                    *((_DWORD *)this + 732) = *((_DWORD *)this + 622);
                    v98 = (char *)this + 656;
                    if ( !v97 )
                      v98 = (char *)this + 712;
                    v99 = *(_OWORD *)v98;
                    v100 = (char *)this + 672;
                    *((_OWORD *)this + 182) = v99;
                    if ( !v97 )
                      v100 = (char *)this + 696;
                    v96 = (struct tagRECT *)((char *)this + 2952);
                    *(_OWORD *)((char *)this + 2952) = *(_OWORD *)v100;
                    RendererEffect = CxCodeVideoProcMFTDataHandler::CreateIntermediateBuffer(
                                       v94,
                                       (CxCodeVideoProcMFTDataHandler *)((char *)this + 2896));
                    if ( RendererEffect )
                      goto LABEL_96;
                  }
                  else
                  {
                    v95 = *((_OWORD *)this + 42);
                    v96 = (struct tagRECT *)((char *)this + 2952);
                    *((_DWORD *)this + 733) = 1;
                    *(_OWORD *)((char *)this + 2952) = v95;
                  }
                  memset_0(v129, 0, 0x50u);
                  RendererEffect = CtypeSurfaces::Find(*((_DWORD *)this + 622), (struct TypeSurface *)v129);
                  if ( RendererEffect )
                    goto LABEL_96;
                  RendererEffect = CxCodeVideoProcMFTDataHandler::GetValidArea(
                                     v101,
                                     *((_DWORD *)this + 740),
                                     *((_DWORD *)this + 741),
                                     v130,
                                     v131,
                                     v96,
                                     0,
                                     1);
                  if ( RendererEffect )
                    goto LABEL_96;
                }
                v102 = *((_DWORD *)this + 758);
                if ( v102 == 2 )
                  goto LABEL_257;
                if ( !v102 )
                {
LABEL_265:
                  v105 = *((_DWORD *)this + 390);
                  if ( v105 == 2 )
                  {
                    v106 = *((_DWORD *)this + 38) == 1;
                    if ( *((_DWORD *)this + 38) != 1 )
                      v35 = *((_DWORD *)this + 63);
                  }
                  else
                  {
                    if ( !v105 )
                    {
LABEL_276:
                      if ( *((_DWORD *)this + 759) != 2 )
                        goto LABEL_96;
                      v108 = *((_OWORD *)this + 20);
                      *((_DWORD *)this + 752) = *((_DWORD *)this + 63);
                      *((_OWORD *)this + 187) = v108;
                      *((_DWORD *)this + 750) -= *((_DWORD *)this + 748);
                      *((_DWORD *)this + 751) -= *((_DWORD *)this + 749);
                      *((_QWORD *)this + 374) = 0;
                      D3DVideoProcessor = CxCodeVideoProcMFTDataHandler::CreateIntermediateBuffer(
                                            v94,
                                            (CxCodeVideoProcMFTDataHandler *)((char *)this + 2976));
                      goto LABEL_278;
                    }
                    v106 = *((_DWORD *)this + 38) == 1;
                    if ( *((_DWORD *)this + 38) != 1 )
                    {
                      *((_DWORD *)this + 715) = 1;
                      goto LABEL_276;
                    }
                  }
                  *((_DWORD *)this + 714) = v35;
                  if ( v106 )
                  {
                    v107 = (char *)this + 656;
                  }
                  else
                  {
                    v107 = (char *)this + 336;
                    if ( *((_DWORD *)this + 758) != 2 )
                      v107 = (char *)this + 320;
                  }
                  *(_OWORD *)((char *)this + 2840) = *(_OWORD *)v107;
                  *((_DWORD *)this + 712) -= *((_DWORD *)this + 710);
                  *((_DWORD *)this + 713) -= *((_DWORD *)this + 711);
                  *((_QWORD *)this + 355) = 0;
                  RendererEffect = CxCodeVideoProcMFTDataHandler::CreateIntermediateBuffer(
                                     v94,
                                     (CxCodeVideoProcMFTDataHandler *)((char *)this + 2824));
                  if ( !RendererEffect )
                    goto LABEL_276;
                  goto LABEL_96;
                }
                if ( *((_DWORD *)this + 390) == 3 )
                {
LABEL_257:
                  if ( *((_DWORD *)this + 38) != 1 )
                  {
                    if ( v102 == 2 )
                      v103 = *((unsigned int *)this + 63);
                    else
                      v103 = *((unsigned int *)this + 154);
LABEL_262:
                    v97 = v102 == 2;
                    *((_DWORD *)this + 698) = v103;
                    v104 = (char *)this + 336;
                    if ( !v97 )
                      v104 = (char *)this + 656;
                    *(_OWORD *)((char *)this + 2776) = *(_OWORD *)v104;
                    *((_DWORD *)this + 696) -= *((_DWORD *)this + 694);
                    *((_DWORD *)this + 697) -= *((_DWORD *)this + 695);
                    *((_QWORD *)this + 347) = 0;
                    RendererEffect = CxCodeVideoProcMFTDataHandler::CreateIntermediateBuffer(
                                       (CxCodeVideoProcMFTDataHandler *)v103,
                                       (CxCodeVideoProcMFTDataHandler *)((char *)this + 2760));
                    if ( RendererEffect )
                      goto LABEL_96;
                    goto LABEL_265;
                  }
                }
                else if ( *((_DWORD *)this + 38) != 1 )
                {
                  *((_DWORD *)this + 699) = 1;
                  goto LABEL_265;
                }
                v103 = 1448433985;
                goto LABEL_262;
              }
            }
          }
          v72 = 0;
          goto LABEL_217;
        }
        if ( *((_BYTE *)this + 1517)
          || !(unsigned int)IsLegacyTransferFunction((const enum _MFVideoTransferFunction *)(v40 + 8))
          || !(unsigned int)IsLegacyTransferFunction((const enum _MFVideoTransferFunction *)this + 136)
          || *((_DWORD *)this + 135) >= v60
          || *((_DWORD *)this + 196) >= v60 )
        {
          if ( (unsigned __int8)byte_180153DE0 < 0x20u )
          {
LABEL_154:
            MF::OriginateError<70>(
              2147500033LL,
              L"Conversion unavailable: No suitable color space conversion available.");
            goto LABEL_117;
          }
          v61 = 187;
LABEL_153:
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 42), v61, &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids, this);
          goto LABEL_154;
        }
      }
      if ( !*((_DWORD *)this + 759) )
        goto LABEL_167;
      goto LABEL_156;
    }
    if ( *((_DWORD *)this + 760) )
    {
      v44 = CtypeConversions::Find(
              v39,
              (unsigned int)v41,
              (int (**)(const struct tagRECT *, const struct ParameterBase *))this + 317,
              0,
              &v111);
      RendererEffect = v44;
      if ( v44 < 0 )
      {
        XvpOriginateError<31>(
          "CxCodeVideoProcMFTDataHandler::OnBeginStreaming2",
          (unsigned int)v44,
          L"No conversion found for format");
LABEL_97:
        *((_DWORD *)this + 292) = 0;
        *((_QWORD *)this + 379) = 0;
        *((_DWORD *)this + 390) = 0;
        *((_QWORD *)this + 380) = 0;
        *((_QWORD *)this + 381) = 0;
        *((_DWORD *)this + 764) = 0;
        *((_DWORD *)this + 388) = 0;
        *((_QWORD *)this + 305) = 0;
        *((_QWORD *)this + 317) = 0;
        *((_QWORD *)this + 343) = 0;
        *((_QWORD *)this + 342) = 0;
        *((_QWORD *)this + 344) = 0;
        *((_QWORD *)this + 360) = 0;
        goto LABEL_283;
      }
      v43 = v111;
    }
    v45 = *((_DWORD *)this + 63);
    v46 = IsPolyPhaseResizerSupported(v45);
    v47 = IsPolyPhaseResizerSupported(*((_DWORD *)this + 154));
    CxCodeVideoProcMFTDataHandler::EstimateScaleTargetRect(this, v136, 2);
    v49 = *((_DWORD *)this + 79);
    v40 = v49 % v124.m128i_i32[1];
    if ( v49 % v124.m128i_i32[1]
      || (v42 = (const struct MFMEDIATYPEUtils::VideoColorSpaceAttributes *)*((unsigned int *)this + 78),
          v40 = (unsigned int)(*((_DWORD *)this + 78) % v124.m128i_i32[2]),
          (_DWORD)v40) )
    {
      if ( *((_DWORD *)this + 760) )
        *((_DWORD *)this + 760) = 3;
      if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
        WPP_SF_qddD(*((_QWORD *)WPP_GLOBAL_Control + 42), 180, v42, this, v49, *((_DWORD *)this + 78), v48);
      if ( v46 || (_QWORD)v119 || !*((_DWORD *)this + 760) )
        goto LABEL_90;
      *((_DWORD *)this + 764) = 2;
    }
    else
    {
      v40 = (unsigned int)(v136[2] - v136[0]) % v116.m128i_i32[1];
      if ( (_DWORD)v40 || (v40 = (unsigned int)(v136[3] - v136[1]) % v116.m128i_i32[2], (_DWORD)v40) )
      {
        if ( *((_DWORD *)this + 760) )
          *((_DWORD *)this + 760) = 2;
        if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
          WPP_SF_qddD(
            *((_QWORD *)WPP_GLOBAL_Control + 42),
            181,
            v42,
            this,
            *((_DWORD *)this + 173),
            *((_DWORD *)this + 172),
            v45);
        goto LABEL_90;
      }
      if ( !*((_DWORD *)this + 761) && *((_DWORD *)this + 68) != 7 || !*((_DWORD *)this + 760) )
      {
LABEL_90:
        if ( *((_DWORD *)this + 760) == 2 )
        {
          v51 = v124;
          v52 = v125;
          v53 = v127;
        }
        else
        {
          v51 = v116;
          v52 = v117;
          v53 = v119;
        }
        *((_DWORD *)this + 609) = v52;
        v54 = (_QWORD *)((char *)this + 2440);
        *((_DWORD *)this + 606) = v51.m128i_i32[1];
        *((_QWORD *)this + 305) = v53;
        *(_QWORD *)((char *)this + 2428) = _mm_srli_si128(v51, 8).m128i_u64[0];
        goto LABEL_108;
      }
      v50 = 3
          - (((unsigned int)(v115 * (_DWORD)v42) >> 3) * ((v114 * v49) >> 3) < ((unsigned int)(*((_DWORD *)this + 173)
                                                                                             * v122) >> 3)
                                                                             * ((unsigned int)(*((_DWORD *)this + 172)
                                                                                             * v123) >> 3));
      *((_DWORD *)this + 760) = v50;
      if ( !IsRectEmpty((const RECT *)((char *)this + 632)) )
      {
        *((_DWORD *)this + 760) = 2;
        if ( !v47 )
        {
          if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
            WPP_SF_qDD(
              *((_QWORD *)WPP_GLOBAL_Control + 42),
              182,
              v42,
              this,
              *((_DWORD *)this + 63),
              *((_DWORD *)this + 154));
          MF::OriginateError<50>(v41, L"Conversion unavailable: No suitable scaler found.");
          goto LABEL_66;
        }
        goto LABEL_90;
      }
      if ( v46 )
      {
        if ( !v47 )
          goto LABEL_76;
LABEL_73:
        *((_DWORD *)this + 760) = v50;
        goto LABEL_90;
      }
      if ( !v47 )
      {
        if ( (_QWORD)v119 )
        {
          if ( !(_QWORD)v127 )
          {
LABEL_76:
            *((_DWORD *)this + 760) = 3;
            goto LABEL_90;
          }
          goto LABEL_73;
        }
        if ( !(_QWORD)v127 )
        {
LABEL_66:
          RendererEffect = -2147467263;
          goto LABEL_97;
        }
      }
    }
    *((_DWORD *)this + 760) = 2;
    goto LABEL_90;
  }
  if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
    WPP_SF_qddd(
      *((_QWORD *)WPP_GLOBAL_Control + 42),
      179,
      &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
      this,
      v37,
      v38,
      v36);
  RendererEffect = -1072875846;
LABEL_283:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v110);
  return (unsigned int)RendererEffect;
}

```

## disassembly

```asm
0x1800244c4  mov     [rsp-8+arg_18], rbx
0x1800244c9  push    rbp
0x1800244ca  push    rsi
0x1800244cb  push    rdi
0x1800244cc  push    r12
0x1800244ce  push    r13
0x1800244d0  push    r14
0x1800244d2  push    r15
0x1800244d4  lea     rbp, [rsp-0A0h]
0x1800244dc  sub     rsp, 1A0h
0x1800244e3  mov     rax, cs:__security_cookie
0x1800244ea  xor     rax, rsp
0x1800244ed  mov     [rbp+0D0h+var_40], rax
0x1800244f4  mov     r12d, r8d
0x1800244f7  mov     r14d, edx
0x1800244fa  mov     rsi, rcx
0x1800244fd  lea     rdx, aCxcodevideopro_108; "CxCodeVideoProcMFTDataHandler::OnBeginS"...
0x180024504  mov     r8d, 0ABFh; int
0x18002450a  lea     rcx, [rsp+1D0h+var_160]; this
0x18002450f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180024514  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002451b  xor     r15d, r15d
0x18002451e  cmp     [rcx+8], r15b
0x180024522  jz      short loc_18002457E
0x180024524  cmp     [rsi+0C20h], r15
0x18002452b  jz      short loc_18002457E
0x18002452d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180024532  mov     rdx, [rsi+0C20h]
0x180024539  mov     rdi, rax
0x18002453c  mov     rcx, [rdx]
0x18002453f  mov     rax, [rcx+128h]
0x180024546  mov     rcx, rdx
0x180024549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002454e  mov     r8, [rsi+0C20h]
0x180024555  lea     rdx, [rbp+0D0h+var_60]
0x180024559  mov     ebx, eax
0x18002455b  mov     rcx, [r8]
0x18002455e  mov     rax, [rcx+118h]
0x180024565  mov     rcx, r8
0x180024568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002456d  movups  xmm0, xmmword ptr [rax]
0x180024570  mov     [rdi+7E0h], ebx
0x180024576  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18002457e  mov     rcx, [rsi+0E0h]
0x180024585  lea     rdx, MF_XVP_DISABLE_FRC
0x18002458c  xor     r8d, r8d
0x18002458f  mov     [rsi+0C40h], r15d
0x180024596  call    MFGetAttributeUINT32
0x18002459b  mov     rcx, [rsi+0E0h]; struct IMFAttributes *
0x1800245a2  mov     [rsi+478h], eax
0x1800245a8  call    ?GetVideoProcessingAlgorithm@@YAIPEAUIMFAttributes@@@Z; GetVideoProcessingAlgorithm(IMFAttributes *)
0x1800245ad  mov     rcx, [rsi+0E0h]
0x1800245b4  lea     rdx, MF_XVP_CALLER_ALLOCATES_OUTPUT
0x1800245bb  xor     r8d, r8d
0x1800245be  mov     [rsi+98h], eax
0x1800245c4  call    MFGetAttributeUINT32
0x1800245c9  mov     rcx, [rsi+0E0h]
0x1800245d0  lea     rdx, MF_LOW_LATENCY
0x1800245d7  xor     r8d, r8d
0x1800245da  mov     [rsi+46Ch], eax
0x1800245e0  call    MFGetAttributeUINT32
0x1800245e5  mov     rcx, [rsi+0E0h]
0x1800245ec  lea     rdx, qword_1800DF0D8
0x1800245f3  xor     r8d, r8d
0x1800245f6  mov     [rsi+468h], eax
0x1800245fc  call    MFGetAttributeUINT32
0x180024601  mov     rcx, [rsi+0E0h]
0x180024608  lea     rdx, qword_1800DF098
0x18002460f  mov     r8d, 2
0x180024615  mov     [rsi+5C8h], eax
0x18002461b  call    MFGetAttributeUINT32
0x180024620  mov     rcx, [rsi+0E0h]
0x180024627  lea     rdx, qword_1800DF088
0x18002462e  mov     r8d, 1
0x180024634  mov     [rsi+61Ch], eax
0x18002463a  call    MFGetAttributeUINT32
0x18002463f  mov     rcx, [rsi+0E0h]
0x180024646  lea     rdx, MF_XVP_SAMPLE_LOCK_TIMEOUT
0x18002464d  or      r8d, 0FFFFFFFFh
0x180024651  mov     [rsi+620h], eax
0x180024657  call    MFGetAttributeUINT32
0x18002465c  mov     rcx, [rsi+0E0h]
0x180024663  lea     rdx, MF_XVP_DEFERRED_VP_DESTRUCTION
0x18002466a  xor     r8d, r8d
0x18002466d  mov     [rsi+5E8h], eax
0x180024673  call    MFGetAttributeUINT32
0x180024678  mov     rcx, [rsi+0E0h]
0x18002467f  lea     rdx, qword_1800DF0C8
0x180024686  xor     r8d, r8d
0x180024689  mov     [rsi+5F4h], eax
0x18002468f  call    MFGetAttributeUINT32
0x180024694  mov     rcx, [rsi+0E0h]
0x18002469b  lea     rdx, qword_1800DF078
0x1800246a2  mov     r8d, 1
0x1800246a8  mov     [rsi+5F8h], eax
0x1800246ae  call    MFGetAttributeUINT32
0x1800246b3  mov     rcx, [rsi+0E0h]
0x1800246ba  lea     rdx, qword_1800DF068
0x1800246c1  test    eax, eax
0x1800246c3  setnz   al
0x1800246c6  xor     r8d, r8d
0x1800246c9  mov     [rsi+5ECh], al
0x1800246cf  call    MFGetAttributeUINT32
0x1800246d4  test    eax, eax
0x1800246d6  lea     rbx, [rsi+0C00h]
0x1800246dd  setnz   al
0x1800246e0  mov     [rsi+5EDh], al
0x1800246e6  mov     eax, [rsi+0C5Ch]
0x1800246ec  mov     [rsi+5E4h], eax
0x1800246f2  cmp     [rbx], r15
0x1800246f5  jnz     short loc_180024710
0x1800246f7  cmp     [rsi+464h], r15d
0x1800246fe  jz      short loc_180024771
0x180024700  mov     rcx, rbx
0x180024703  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180024708  mov     rcx, rbx; struct RegistryKeyWatcher **
0x18002470b  call    ?XVPCreateVideoSettingsChangeWatcher@@YAJPEAPEAVRegistryKeyWatcher@@@Z; XVPCreateVideoSettingsChangeWatcher(RegistryKeyWatcher * *)
0x180024710  cmp     [rsi+464h], r15d
0x180024717  jz      short loc_180024771
0x180024719  test    r12d, r12d
0x18002471c  jz      short loc_180024771
0x18002471e  cmp     dword ptr [rsi+3E8h], 1
0x180024725  jnz     loc_18002487E
0x18002472b  mov     rdx, [rsi+0C20h]; struct IMFTelemetrySession *
0x180024732  lea     rcx, [rsi+3F8h]; this
0x180024739  call    ?Initialize@MFLightSensorReader@@QEAAJPEAUIMFTelemetrySession@@@Z; MFLightSensorReader::Initialize(IMFTelemetrySession *)
0x18002473e  test    eax, eax
0x180024740  jns     loc_18002487E
0x180024746  cmp     cs:byte_180153DE0, 1
0x18002474d  jb      short loc_180024771
0x18002474f  mov     rcx, cs:WPP_GLOBAL_Control
0x180024756  lea     r8, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x18002475d  mov     edx, 0AEh
0x180024762  mov     r9, rsi
0x180024765  mov     rcx, [rcx+150h]
0x18002476c  call    WPP_SF_q
0x180024771  mov     [rsi+3E8h], r15d
0x180024778  mov     rcx, rsi; this
0x18002477b  call    ?GetDebugMode@CxCodeVideoProcMFTDataHandler@@AEAAXXZ; CxCodeVideoProcMFTDataHandler::GetDebugMode(void)
0x180024780  mov     rcx, [rsi+0E0h]
0x180024787  lea     rdx, qword_1800DF0B8
0x18002478e  xor     r8d, r8d
0x180024791  call    MFGetAttributeUINT32
0x180024796  test    eax, eax
0x180024798  jz      short loc_1800247A4
0x18002479a  mov     dword ptr [rsi+5CCh], 1
0x1800247a4  cmp     cs:byte_180153DE0, 20h ; ' '
0x1800247ab  jb      loc_18002484E
0x1800247b1  mov     eax, [rsi+464h]
0x1800247b7  lea     r8, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x1800247be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800247c5  mov     edx, 0B0h
0x1800247ca  mov     [rsp+1D0h+var_198], eax
0x1800247ce  mov     r9, rsi
0x1800247d1  mov     eax, [rsi+98h]
0x1800247d7  mov     [rsp+1D0h+var_1A0], eax
0x1800247db  mov     eax, [rsi+468h]
0x1800247e1  mov     rcx, [rcx+150h]
0x1800247e8  mov     dword ptr [rsp+1D0h+var_1A8], eax
0x1800247ec  mov     eax, [rsi+478h]
0x1800247f2  mov     dword ptr [rsp+1D0h+var_1B0], eax
0x1800247f6  call    WPP_SF_qdddd
0x1800247fb  cmp     cs:byte_180153DE0, 20h ; ' '
0x180024802  jb      short loc_18002484E
0x180024804  mov     eax, [rsi+288h]
0x18002480a  lea     r8, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x180024811  mov     rcx, cs:WPP_GLOBAL_Control
0x180024818  mov     edx, 0B1h
0x18002481d  mov     [rsp+1D0h+var_198], eax
0x180024821  mov     r9, rsi
0x180024824  mov     eax, [rsi+28Ch]
0x18002482a  mov     [rsp+1D0h+var_1A0], eax
0x18002482e  mov     eax, [rsi+128h]
0x180024834  mov     rcx, [rcx+150h]
0x18002483b  mov     dword ptr [rsp+1D0h+var_1A8], eax
0x18002483f  mov     eax, [rsi+12Ch]
0x180024845  mov     dword ptr [rsp+1D0h+var_1B0], eax
0x180024849  call    WPP_SF_qdddd
0x18002484e  cmp     [rsi+464h], r15d
0x180024855  jz      short loc_1800248C8
0x180024857  cmp     dword ptr [rsi+98h], 1
0x18002485e  jnz     short loc_1800248C8
0x180024860  mov     ebx, 80004005h
0x180024865  lea     r8, aXvpPlaybackMod; "XVP playback mode and MF_VIDEO_PROCESSO"...
0x18002486c  mov     ecx, ebx
0x18002486e  mov     edx, 62h ; 'b'
0x180024873  call    cs:__imp_RoOriginateErrorW
0x180024879  jmp     loc_1800259DC
0x18002487e  cmp     [rsi+449h], r15b
0x180024885  jz      short loc_180024894
0x180024887  cmp     [rsi+448h], r15b
0x18002488e  jnz     loc_180024778
0x180024894  cmp     cs:byte_180153DE0, 8
0x18002489b  jb      loc_180024778
0x1800248a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800248a8  lea     r8, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x1800248af  mov     edx, 0AFh
0x1800248b4  mov     r9, rsi
0x1800248b7  mov     rcx, [rcx+150h]
0x1800248be  call    WPP_SF_q
0x1800248c3  jmp     loc_180024778
0x1800248c8  lea     rcx, [rsi+180h]; this
0x1800248cf  xor     edx, edx; int
0x1800248d1  call    ?Reset@CxCodeVideoProcSampleInfo@@QEAAXH@Z; CxCodeVideoProcSampleInfo::Reset(int)
0x1800248d6  lea     rcx, [rsi+340h]; this
0x1800248dd  call    ?Reset@CxCodeVideoProcSampleInfo@@QEAAXH@Z; CxCodeVideoProcSampleInfo::Reset(int)
0x1800248e2  lea     rcx, [rsi+948h]
0x1800248e9  mov     [rsi+47Ch], r15
0x1800248f0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800248f5  mov     rcx, rsi; this
0x1800248f8  call    ?IsWarpMode@CxCodeVideoProcMFTDataHandler@@QEAA_NXZ; CxCodeVideoProcMFTDataHandler::IsWarpMode(void)
0x1800248fd  test    al, al
0x1800248ff  jnz     short loc_18002494F
0x180024901  test    r12d, r12d
0x180024904  jz      short loc_180024918
0x180024906  mov     rcx, rsi; this
0x180024909  call    ?CheckD3DVideoDevice@CxCodeVideoProcMFTDataHandler@@QEAAJXZ; CxCodeVideoProcMFTDataHandler::CheckD3DVideoDevice(void)
0x18002490e  mov     ebx, eax
0x180024910  test    eax, eax
0x180024912  jnz     loc_180024DE2
0x180024918  cmp     [rsi+0C28h], r15
0x18002491f  jnz     short loc_18002494F
0x180024921  cmp     cs:byte_180153DE0, 20h ; ' '
0x180024928  jb      short loc_18002494C
0x18002492a  mov     rcx, cs:WPP_GLOBAL_Control
0x180024931  lea     r8, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x180024938  mov     edx, 0B2h
0x18002493d  mov     r9, rsi
0x180024940  mov     rcx, [rcx+150h]
0x180024947  call    WPP_SF_q
0x18002494c  mov     r12d, r15d
0x18002494f  mov     rcx, rsi; this
0x180024952  call    ?LoadRendererEffect@CxCodeVideoProcMFTDataHandler@@QEAAJXZ; CxCodeVideoProcMFTDataHandler::LoadRendererEffect(void)
0x180024957  mov     ebx, eax
0x180024959  test    eax, eax
0x18002495b  jnz     loc_180024DE2
0x180024961  cmp     [rsi+6C8h], r15
0x180024968  jz      short loc_18002497C
0x18002496a  mov     rcx, rsi; this
0x18002496d  call    ?ConfigureRendererEffect@CxCodeVideoProcMFTDataHandler@@QEAAJXZ; CxCodeVideoProcMFTDataHandler::ConfigureRendererEffect(void)
0x180024972  mov     ebx, eax
0x180024974  test    eax, eax
0x180024976  jnz     loc_180024DE2
0x18002497c  mov     r8d, r12d; int
0x18002497f  mov     edx, r14d; int
0x180024982  mov     rcx, rsi; this
0x180024985  call    ?ConfigureConversions@CxCodeVideoProcMFTDataHandler@@AEAAJHH@Z; CxCodeVideoProcMFTDataHandler::ConfigureConversions(int,int)
0x18002498a  mov     ebx, eax
0x18002498c  test    eax, eax
0x18002498e  jnz     loc_180024DE2
0x180024994  mov     r14d, 56555941h
0x18002499a  test    r12d, r12d
0x18002499d  jnz     short loc_180024A10
0x18002499f  mov     r9d, [rsi+0BE4h]
0x1800249a6  test    r9d, r9d
0x1800249a9  jz      short loc_180024A10
0x1800249ab  cmp     [rsi+5ECh], r15b
0x1800249b2  jz      short loc_180024A10
0x1800249b4  mov     ecx, [rsi+96Ch]
0x1800249ba  test    ecx, ecx
0x1800249bc  jz      short loc_180024A10
0x1800249be  mov     eax, [rsi+0FCh]
0x1800249c4  cmp     eax, 15h
0x1800249c7  jz      short loc_1800249CE
0x1800249c9  cmp     eax, r14d
0x1800249cc  jnz     short loc_180024A10
0x1800249ce  cmp     cs:byte_180153DE0, 20h ; ' '
0x1800249d5  jb      short loc_180024A06
0x1800249d7  mov     [rsp+1D0h+var_1A0], r9d
0x1800249dc  lea     r8, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x1800249e3  mov     dword ptr [rsp+1D0h+var_1A8], eax
0x1800249e7  mov     edx, 0B3h
0x1800249ec  mov     dword ptr [rsp+1D0h+var_1B0], ecx
0x1800249f0  mov     r9, rsi
0x1800249f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800249fa  mov     rcx, [rcx+150h]
0x180024a01  call    WPP_SF_qddd
0x180024a06  mov     ebx, 0C00D36BAh
0x180024a0b  jmp     loc_1800259DC
0x180024a10  xor     edx, edx; Val
0x180024a12  lea     rcx, [rbp+0D0h+var_150]; void *
0x180024a16  lea     r8d, [rdx+50h]; Size
0x180024a1a  call    memset_0
0x180024a1f  xor     edx, edx; Val
0x180024a21  lea     rcx, [rbp+0D0h+var_100]; void *
0x180024a25  lea     r8d, [rdx+50h]; Size
0x180024a29  call    memset_0
0x180024a2e  mov     edi, [rsi+0FCh]
0x180024a34  lea     rdx, [rbp+0D0h+var_150]; struct TypeSurface *
0x180024a38  mov     ecx, edi; unsigned int
0x180024a3a  call    ?Find@CtypeSurfaces@@SAJKPEAUTypeSurface@@@Z; CtypeSurfaces::Find(ulong,TypeSurface *)
0x180024a3f  test    eax, eax
0x180024a41  jnz     loc_1800259D2
0x180024a47  mov     ecx, [rsi+268h]; unsigned int
0x180024a4d  lea     rdx, [rbp+0D0h+var_100]; struct TypeSurface *
0x180024a51  call    ?Find@CtypeSurfaces@@SAJKPEAUTypeSurface@@@Z; CtypeSurfaces::Find(ulong,TypeSurface *)
0x180024a56  test    eax, eax
0x180024a58  jnz     loc_1800259D2
0x180024a5e  test    r12d, r12d
0x180024a61  jnz     loc_18002547C
  ... truncated ...
```
