# CxCodeVideoProcD3D11DataHandler::CreateD3DVideoProcessorInternal(void)

- ea: `0x18006dad0`
- end: `0x18006eb1e`
- name: `?CreateD3DVideoProcessorInternal@CxCodeVideoProcD3D11DataHandler@@MEAAJXZ`
- size: `4174`
- prototype: `__int64 __fastcall(CxCodeVideoProcD3D11DataHandler *__hidden this)`
- caller_count: `1`
- callee_count: `33`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180025ef0`

## callees

- `0x18000955c`
- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000caec`
- `0x18000ec20`
- `0x18000ecf0`
- `0x180012480`
- `0x180017f20`
- `0x180036044`
- `0x180036268`
- `0x18003639c`
- `0x1800364d0`
- `0x180036fe0`
- `0x180037080`
- `0x180040418`
- `0x180045a50`
- `0x18004fc40`
- `0x180053c54`
- `0x180054140`
- `0x180059968`
- `0x180063110`
- `0x180066ee0`
- `0x180066fc4`
- `0x18006ba7c`
- `0x18006dad0`
- `0x18006fa30`
- `0x18007088c`
- `0x180072d1c`
- `0x180072dbc`
- `0x180072f68`
- `0x1800ca098`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18006e1c5`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18006e1c5`

## string_xrefs

- `0x18006db05`: `CxCodeVideoProcD3D11DataHandler::CreateD3DVideoProcessorInternal`
- `0x18006dbb1`: `CxCodeVideoProcD3D11DataHandler::CreateD3DVideoProcessorInternal`
- `0x18006dc16`: `CxCodeVideoProcD3D11DataHandler::CreateD3DVideoProcessorInternal`
- `0x18006dc95`: `CxCodeVideoProcD3D11DataHandler::CreateD3DVideoProcessorInternal`
- `0x18006dd31`: `CxCodeVideoProcD3D11DataHandler::CreateD3DVideoProcessorInternal`
- `0x18006e186`: `CxCodeVideoProcD3D11DataHandler::CreateD3DVideoProcessorInternal`
- `0x18006e1f9`: `CxCodeVideoProcD3D11DataHandler::CreateD3DVideoProcessorInternal`
- `0x18006e43e`: `CxCodeVideoProcD3D11DataHandler::CreateD3DVideoProcessorInternal`
- `0x18006e641`: `CxCodeVideoProcD3D11DataHandler::CreateD3DVideoProcessorInternal`
- `0x18006e7d7`: `CxCodeVideoProcD3D11DataHandler::CreateD3DVideoProcessorInternal`
- `0x18006e910`: `CxCodeVideoProcD3D11DataHandler::CreateD3DVideoProcessorInternal`
- `0x18006ea18`: `CxCodeVideoProcD3D11DataHandler::CreateD3DVideoProcessorInternal`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcD3D11DataHandler::CreateD3DVideoProcessorInternal(CMFTMultiStreamTypeHandler **this)
{
  CMFTMultiStreamTypeHandler *v2; // rax
  int v3; // ebx
  CallStackTracing *v4; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v6; // rdx
  CallStackTracing *v7; // rcx
  struct CallStackContext *v8; // rax
  CMFTMultiStreamTypeHandler *v9; // rcx
  CallStackTracing *v10; // rcx
  struct CallStackContext *v11; // rax
  CMFTMultiStreamTypeHandler *v12; // rdx
  CallStackTracing *v13; // rcx
  struct CallStackContext *v14; // rax
  char v15; // bl
  CMFTMultiStreamTypeHandler *v16; // rax
  unsigned int v17; // ecx
  unsigned int v18; // r8d
  char v19; // al
  unsigned int v20; // edx
  CMFTMultiStreamTypeHandler *v21; // r10
  char v22; // r12
  unsigned int v23; // edx
  CMFTMultiStreamTypeHandler *v24; // rcx
  __int64 v25; // r10
  MFMEDIATYPEUtils *v26; // r8
  struct DXGI_HDR_METADATA_HDR10 *v27; // r8
  CMFTMultiStreamTypeHandler *v28; // r15
  CMFTMultiStreamTypeHandler *v29; // rcx
  enum _MFVideoTransferFunction v30; // edx
  CMFTMultiStreamTypeHandler *v31; // r15
  CMFTMultiStreamTypeHandler *v32; // rcx
  _DWORD *v33; // r8
  __int64 v34; // r9
  char v35; // al
  unsigned int v36; // edi
  CallStackTracing *v37; // rcx
  struct CallStackContext *v38; // rax
  CallStackTracing *v39; // rcx
  struct CallStackContext *v40; // rax
  int *v41; // r10
  int v42; // ecx
  int v43; // ecx
  int v44; // ecx
  int v45; // ecx
  int v46; // ecx
  int v47; // ecx
  bool v48; // r14
  int v49; // ecx
  int v50; // ecx
  int v51; // ecx
  int v52; // ecx
  int v53; // ecx
  int v54; // ecx
  int v55; // ecx
  unsigned __int8 v56; // si
  int v57; // eax
  int v58; // eax
  unsigned __int8 v59; // bl
  CMFTMultiStreamTypeHandler *v60; // rcx
  CMFTMultiStreamTypeHandler *v61; // rcx
  CMFTMultiStreamTypeHandler *v62; // rax
  CallStackTracing *v63; // rcx
  struct CallStackContext *v64; // rax
  bool v65; // zf
  CMFTMultiStreamTypeHandler *v66; // rbx
  __m128i si128; // xmm6
  enum DXGI_FORMAT v68; // edx
  int matched; // eax
  CallStackTracing *v70; // rcx
  struct CallStackContext *v71; // rax
  __m128i v72; // xmm0
  __int128 v73; // xmm1
  CMFTMultiStreamTypeHandler *v74; // rcx
  int v75; // eax
  __int128 v76; // xmm0
  __int128 v77; // xmm1
  __int128 v78; // xmm0
  CallStackTracing *v79; // rcx
  struct CallStackContext *v80; // rax
  int v81; // ecx
  CMFTMultiStreamTypeHandler *v82; // rax
  int v83; // ecx
  CMFTMultiStreamTypeHandler *v84; // rax
  int v85; // ecx
  CMFTMultiStreamTypeHandler *v86; // rax
  int v87; // ecx
  CallStackTracing *v88; // rcx
  struct CallStackContext *v89; // rax
  unsigned int *v90; // rcx
  unsigned int v91; // eax
  CMFTMultiStreamTypeHandler *v92; // rax
  CallStackTracing *v93; // rcx
  struct CallStackContext *v94; // rax
  unsigned int v96; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v97[4]; // [rsp+8Ch] [rbp-7Ch] BYREF
  MFMEDIATYPEUtils *v98; // [rsp+90h] [rbp-78h]
  __m128i v99; // [rsp+98h] [rbp-70h] BYREF
  __m128i v100; // [rsp+A8h] [rbp-60h]
  __int128 v101; // [rsp+B8h] [rbp-50h]
  __int128 v102; // [rsp+C8h] [rbp-40h]
  __int128 v103; // [rsp+D8h] [rbp-30h]
  __int128 v104; // [rsp+E8h] [rbp-20h]
  int v105; // [rsp+F8h] [rbp-10h]
  _BYTE v106[56]; // [rsp+128h] [rbp+20h] BYREF
  __int64 v107; // [rsp+160h] [rbp+58h]
  int v108; // [rsp+170h] [rbp+68h] BYREF
  __int128 v109; // [rsp+174h] [rbp+6Ch]
  _BYTE v110[28]; // [rsp+184h] [rbp+7Ch] BYREF
  _OWORD v111[2]; // [rsp+1A0h] [rbp+98h] BYREF
  int v112; // [rsp+1C0h] [rbp+B8h]

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v97,
    "CxCodeVideoProcD3D11DataHandler::CreateD3DVideoProcessorInternal",
    2108);
  v112 = 0;
  memset(v111, 0, sizeof(v111));
  CxCodeVideoProcD3D11DataHandler::EnsureD3D11Context((CxCodeVideoProcD3D11DataHandler *)this);
  v2 = this[2];
  if ( *((_DWORD *)v2 + 246) )
  {
    *((_DWORD *)v2 + 536) = 0;
    v3 = CxCodeVideoProcD3DDataHandler::ResolveFallbackShader(
           (CxCodeVideoProcD3DDataHandler *)this,
           *((enum DXGI_FORMAT *)this[2] + 82),
           *((enum DXGI_FORMAT *)this[2] + 141),
           0);
    if ( v3 < 0 )
    {
      v4 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v4 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v4 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v4);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v3 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CxCodeVideoProcD3D11DataHandler::CreateD3DVideoProcessorInternal",
            2117,
            v3);
      }
      if ( g_wppLevels )
      {
        v6 = 102;
LABEL_185:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids, this, v3);
        goto LABEL_186;
      }
      goto LABEL_186;
    }
LABEL_119:
    v61 = this[2];
    if ( *((_DWORD *)v61 + 246) )
    {
      *((_DWORD *)v61 + 227) = 0;
      *((_DWORD *)this[2] + 228) = 0;
      *((_DWORD *)this[2] + 229) = 0;
      v92 = this[2];
      if ( *((_DWORD *)v92 + 331) || *((_DWORD *)v92 + 332) )
      {
        v3 = MF::OriginateError<36>(3222091478LL, L"shading cannot support constriction");
        if ( v3 < 0 )
        {
          v93 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v93 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v93 + 8) )
          {
            v94 = CallStackTracing::GetThreadRelativeContext(v93);
            if ( *((_DWORD *)v94 + 499) != v3 )
              CallStackContext::TraceFailure(
                v94,
                "CxCodeVideoProcD3D11DataHandler::CreateD3DVideoProcessorInternal",
                2281,
                v3);
          }
          if ( g_wppLevels )
          {
            v6 = 122;
            goto LABEL_185;
          }
          goto LABEL_186;
        }
      }
    }
    else
    {
      *((_DWORD *)v61 + 227) = BYTE4(v111[0]) & 0x40;
      v62 = this[2];
      if ( (*((_DWORD *)v62 + 331) || *((_DWORD *)v62 + 332)) && (BYTE4(v111[0]) & 2) == 0 )
      {
        v3 = MF::OriginateError<32>(3222091478LL, L"VP doesn't support constriction");
        if ( v3 < 0 )
        {
          v63 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v63 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v63 + 8) )
          {
            v64 = CallStackTracing::GetThreadRelativeContext(v63);
            if ( *((_DWORD *)v64 + 499) != v3 )
              CallStackContext::TraceFailure(
                v64,
                "CxCodeVideoProcD3D11DataHandler::CreateD3DVideoProcessorInternal",
                2265,
                v3);
          }
          if ( g_wppLevels )
          {
            v6 = 121;
            goto LABEL_185;
          }
          goto LABEL_186;
        }
      }
      *((_DWORD *)this[2] + 228) = v111[0] & 0x10;
      if ( !this[291] || (v81 = 1, (WORD2(v111[0]) & 0x200) == 0) )
        v81 = 0;
      *((_DWORD *)this[2] + 229) = v81;
    }
    v82 = this[2];
    if ( !*((_DWORD *)v82 + 227) && *((_DWORD *)v82 + 326)
      || !*((_DWORD *)v82 + 229) && *((_DWORD *)v82 + 328)
      || (v83 = 0, *((_DWORD *)v82 + 310)) )
    {
      v83 = 1;
    }
    *((_DWORD *)v82 + 230) = v83;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 148);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 149);
    v84 = this[2];
    if ( *((_DWORD *)v84 + 248) || (v85 = 0, *((_DWORD *)v84 + 230)) )
      v85 = 1;
    *((_DWORD *)v84 + 248) = v85;
    v86 = this[2];
    if ( *((_DWORD *)v86 + 248) || (v87 = 0, *((_DWORD *)v86 + 187)) )
      v87 = 1;
    *((_DWORD *)v86 + 248) = v87;
    v3 = CxCodeVideoProcD3DDataHandler::PostModeD3DConfigure((CxCodeVideoProcD3DDataHandler *)this);
    if ( v3 < 0 )
    {
      v88 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v88 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v88 + 8) )
      {
        v89 = CallStackTracing::GetThreadRelativeContext(v88);
        if ( *((_DWORD *)v89 + 499) != v3 )
          CallStackContext::TraceFailure(
            v89,
            "CxCodeVideoProcD3D11DataHandler::CreateD3DVideoProcessorInternal",
            2300,
            v3);
      }
      if ( g_wppLevels )
      {
        v6 = 123;
        goto LABEL_185;
      }
    }
    goto LABEL_186;
  }
  v3 = CxCodeVideoProcD3D11DataHandler::EnsureD3D11VideoProcessor((CxCodeVideoProcD3D11DataHandler *)this);
  if ( v3 >= 0 )
  {
    v9 = this[293];
    if ( v9 )
    {
      v3 = (*(__int64 (__fastcall **)(CMFTMultiStreamTypeHandler *, _OWORD *))(*(_QWORD *)v9 + 72LL))(v9, v111);
      if ( v3 < 0 )
      {
        v10 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v10 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v10 + 8) )
        {
          v11 = CallStackTracing::GetThreadRelativeContext(v10);
          if ( *((_DWORD *)v11 + 499) != v3 )
            CallStackContext::TraceFailure(
              v11,
              "CxCodeVideoProcD3D11DataHandler::CreateD3DVideoProcessorInternal",
              2125,
              v3);
        }
        if ( g_wppLevels )
        {
          v6 = 104;
          goto LABEL_185;
        }
        goto LABEL_186;
      }
    }
    v12 = this[2];
    v96 = 0;
    v3 = CxCodeVideoProcD3D11DataHandler::CheckVPConversionSupport(
           (CxCodeVideoProcD3D11DataHandler *)this,
           (enum DXGI_FORMAT)*((_DWORD *)v12 + 82),
           (enum DXGI_COLOR_SPACE_TYPE)*((_DWORD *)v12 + 78),
           (enum DXGI_FORMAT)*((_DWORD *)v12 + 141),
           (enum DXGI_COLOR_SPACE_TYPE)*((_DWORD *)v12 + 139),
           &v96,
           0);
    if ( v3 < 0 )
    {
      v13 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v13 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        v14 = CallStackTracing::GetThreadRelativeContext(v13);
        if ( *((_DWORD *)v14 + 499) != v3 )
          CallStackContext::TraceFailure(
            v14,
            "CxCodeVideoProcD3D11DataHandler::CreateD3DVideoProcessorInternal",
            2132,
            v3);
      }
      if ( g_wppLevels )
      {
        v6 = 105;
        goto LABEL_185;
      }
      goto LABEL_186;
    }
    if ( !this[292] || (v15 = 1, (WORD2(v111[0]) & 0x800) == 0) )
      v15 = 0;
    v16 = this[2];
    v17 = *((_DWORD *)v16 + 321);
    v18 = *((_DWORD *)v16 + 124);
    if ( v18 < v17 )
    {
      if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
        WPP_SF_qdd(
          *((_QWORD *)WPP_GLOBAL_Control + 42),
          106,
          &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
          this,
          v18,
          v17);
      v15 = 0;
    }
    v19 = IsMFXboxVPBltPlatformSupportsHDR8Present();
    v21 = this[2];
    v22 = v15;
    if ( v19 )
      v22 = 1;
    if ( *((_QWORD *)v21 + 186) && (*((_BYTE *)v21 + 2104) & 4) != 0 )
      CMFTMultiStreamTypeHandler::POutputType(this[3], v20);
    else
      CMFTMultiStreamTypeHandler::PInputType(this[3], 0);
    v98 = (MFMEDIATYPEUtils *)CMFTMultiStreamTypeHandler::POutputType(v24, v23);
    if ( (int)MFMEDIATYPEUtils::GetHDRMetaDataFromMediaType(
                v26,
                (struct IMFMediaType *)(v25 + 924),
                (struct DXGI_HDR_METADATA_HDR10 *)v26) < 0 )
    {
      v29 = this[2];
      *((_DWORD *)v29 + 231) = 1081376000;
      *((_DWORD *)v29 + 232) = 1966095000;
      *((_DWORD *)v29 + 233) = 196615500;
      *((_DWORD *)v29 + 234) = 1078082835;
      *((_DWORD *)v29 + 235) = 80;
      *((_QWORD *)v29 + 118) = 1;
      if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 42), 108, &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids, this);
    }
    else if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
    {
      v28 = this[2];
      WPP_SF_qdddddddddddd(
        *((_QWORD *)WPP_GLOBAL_Control + 42),
        107,
        *((unsigned __int16 *)v28 + 469),
        (_DWORD)this,
        *((_WORD *)v28 + 462),
        *((_WORD *)v28 + 463),
        *((_WORD *)v28 + 464),
        *((_WORD *)v28 + 465),
        *((_WORD *)v28 + 466),
        *((_WORD *)v28 + 467),
        *((_WORD *)v28 + 468),
        *((_WORD *)v28 + 469),
        *((_DWORD *)v28 + 235),
        *((_DWORD *)v28 + 236),
        *((_WORD *)v28 + 474),
        *((_WORD *)v28 + 475));
    }
    if ( (int)MFMEDIATYPEUtils::GetHDRMetaDataFromMediaType(v98, (struct IMFMediaType *)this[2] + 119, v27) < 0 )
    {
      v32 = this[2];
      *((_DWORD *)v32 + 238) = 1081376000;
      *((_DWORD *)v32 + 239) = 1966095000;
      *((_DWORD *)v32 + 240) = 196615500;
      *((_DWORD *)v32 + 241) = 1078082835;
      *((_DWORD *)v32 + 242) = 80;
      *(_QWORD *)((char *)v32 + 972) = 1;
      if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 42), 110, &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids, this);
    }
    else if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
    {
      v31 = this[2];
      WPP_SF_qdddddddddddd(
        *((_QWORD *)WPP_GLOBAL_Control + 42),
        109,
        *((unsigned __int16 *)v31 + 483),
        (_DWORD)this,
        *((_WORD *)v31 + 476),
        *((_WORD *)v31 + 477),
        *((_WORD *)v31 + 478),
        *((_WORD *)v31 + 479),
        *((_WORD *)v31 + 480),
        *((_WORD *)v31 + 481),
        *((_WORD *)v31 + 482),
        *((_WORD *)v31 + 483),
        *((_DWORD *)v31 + 242),
        *((_DWORD *)v31 + 243),
        *((_WORD *)v31 + 488),
        *((_WORD *)v31 + 489));
    }
    if ( !(unsigned int)MFMEDIATYPEUtils::MFMEDIATYPEUtilsHelper::IsTransferFunctionHDR(
                          (MFMEDIATYPEUtils::MFMEDIATYPEUtilsHelper *)*((unsigned int *)this[2] + 74),
                          v30)
      || (v35 = 1, v33[235] <= (unsigned int)(v33[242] + 50)) )
    {
      v35 = 0;
    }
    if ( v22 || !v35 )
      v36 = v96;
    else
      v36 = v96 & 0xFFFFFFFC;
    if ( (v36 & 3) != 3 )
    {
      if ( v33[314] == 2 )
      {
        v3 = -1072861834;
        RoOriginateErrorW(3222105462LL, 16, L"Unsupported type", v34);
        v39 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v39 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v39 + 8) )
        {
          v40 = CallStackTracing::GetThreadRelativeContext(v39);
          if ( *((_DWORD *)v40 + 499) != -1072861834 )
            CallStackContext::TraceFailure(
              v40,
              "CxCodeVideoProcD3D11DataHandler::CreateD3DVideoProcessorInternal",
              2199,
              -1072861834);
        }
        if ( g_wppLevels )
        {
          v6 = 113;
          goto LABEL_185;
        }
        goto LABEL_186;
      }
      if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 42),
          111,
          &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
          this,
          v33[82]);
      v3 = CxCodeVideoProcD3DDataHandler::ResolveFallbackShader(
             (CxCodeVideoProcD3DDataHandler *)this,
             *((enum DXGI_FORMAT *)this[2] + 82),
             *((enum DXGI_FORMAT *)this[2] + 141),
             0);
      if ( v3 < 0 )
      {
        v37 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v37 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v37 + 8) )
        {
          v38 = CallStackTracing::GetThreadRelativeContext(v37);
          if ( *((_DWORD *)v38 + 499) != v3 )
            CallStackContext::TraceFailure(
              v38,
              "CxCodeVideoProcD3D11DataHandler::CreateD3DVideoProcessorInternal",
              2195,
              v3);
        }
        if ( g_wppLevels )
        {
          v6 = 112;
          goto LABEL_185;
        }
        goto LABEL_186;
      }
    }
    v41 = (int *)this[2];
    v42 = v41[78];
    v48 = 1;
    if ( v42 )
    {
      v43 = v42 - 1;
      if ( v43 )
      {
        v44 = v43 - 1;
        if ( v44 )
        {
          v45 = v44 - 3;
          if ( v45 )
          {
            v46 = v45 - 1;
            if ( v46 )
            {
              v47 = v46 - 1;
              if ( v47 )
              {
                if ( (unsigned int)(v47 - 1) >= 2 )
                  v48 = 0;
              }
            }
          }
        }
      }
    }
    v49 = v41[139];
    if ( !v49
      || (v50 = v49 - 1) == 0
      || (v51 = v50 - 1) == 0
      || (v52 = v51 - 3) == 0
      || (v53 = v52 - 1) == 0
      || (v54 = v53 - 1) == 0
      || (v55 = v54 - 1) == 0
      || (v56 = 0, v55 == 1) )
    {
      v56 = 1;
    }
    v57 = v41[74];
    if ( v57 >= 15 || v57 == 1 || (v58 = v41[135], v58 >= 15) || v58 == 1 || v41[73] >= 9 || (v59 = 0, v41[134] >= 9) )
      v59 = 1;
    if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
      WPP_SF_qdddddd(
        *((_QWORD *)WPP_GLOBAL_Control + 42),
        114,
        &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
        this,
        v36,
        v48,
        v56,
        v59,
        v41[79],
        v41[140]);
    if ( !v48 || !v56 || v59 )
    {
      v60 = this[2];
      if ( *((_DWORD *)v60 + 79) || *((_DWORD *)v60 + 140) || (v36 & 4) == 0 )
      {
        v65 = *((_DWORD *)v60 + 82) == 104;
        v96 = 0;
        if ( v65
          && *((_DWORD *)v60 + 141) == 28
          && *((_DWORD *)v60 + 78) == 13
          && !*((_DWORD *)v60 + 139)
          && (int)CxCodeVideoProcD3D11DataHandler::CheckVPConversionSupport(
                    (CxCodeVideoProcD3D11DataHandler *)this,
                    DXGI_FORMAT_P010,
                    DXGI_COLOR_SPACE_YCBCR_STUDIO_G2084_LEFT_P2020,
                    DXGI_FORMAT_R10G10B10A2_UNORM,
                    DXGI_COLOR_SPACE_RGB_FULL_G2084_NONE_P2020,
                    &v96,
                    0) >= 0
          && (v96 & 7) == 7 )
        {
          if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
            WPP_SF_qddd(
              *((_QWORD *)WPP_GLOBAL_Control + 42),
              115,
              &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
              this,
              *((_DWORD *)this[2] + 78),
              12,
              *((_DWORD *)this[2] + 139));
          v66 = this[2];
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          *(_DWORD *)&v106[8] = -1;
          v68 = *((_DWORD *)v66 + 141);
          v107 = 0;
          memset(&v106[12], 0, 44);
          *(_QWORD *)v106 = 0;
          v108 = -1;
          v100 = _mm_load_si128((const __m128i *)&_xmm);
          v96 = 0;
          v101 = *(_OWORD *)v106;
          v105 = 0;
          v102 = *(_OWORD *)&v106[16];
          v103 = *(_OWORD *)&v106[32];
          memset(v110, 0, sizeof(v110));
          v99 = si128;
          v104 = 0u;
          v109 = 0;
          if ( !(unsigned int)LookupFallbackShaderClass(
                                DXGI_FORMAT_R10G10B10A2_UNORM,
                                v68,
                                (enum FallbackColorConversionShaderClass *)&v96)
            || (matched = MatchConcreateFallbackShader(
                            v96,
                            0,
                            *((unsigned int *)v66 + 223),
                            0,
                            0,
                            *((_DWORD *)v66 + 314) == 4,
                            &v108,
                            &v99),
                si128 = v99,
                !matched) )
          {
            v3 = MF::OriginateError<41>(2147549183LL, L"VPBlt intermediate post-shader not found");
            if ( v3 < 0 )
            {
              v70 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::InitInstance();
                v70 = CallStackTracing::s_wpInstance;
              }
              if ( *((_BYTE *)v70 + 8) )
              {
                v71 = CallStackTracing::GetThreadRelativeContext(v70);
                if ( *((_DWORD *)v71 + 499) != v3 )
                  CallStackContext::TraceFailure(
                    v71,
                    "CxCodeVideoProcD3D11DataHandler::CreateD3DVideoProcessorInternal",
                    2235,
                    v3);
              }
              if ( g_wppLevels )
              {
                v6 = 116;
                goto LABEL_185;
              }
              goto LABEL_186;
            }
          }
          v72 = v100;
          v73 = v101;
          *((_DWORD *)this[2] + 248) = 1;
          *((_DWORD *)this[2] + 299) = 24;
          v74 = this[2];
          v75 = v105;
          *(__m128i *)((char *)v74 + 996) = si128;
          *(__m128i *)((char *)v74 + 1012) = v72;
          v76 = v102;
          *(_OWORD *)((char *)v74 + 1028) = v73;
          v77 = v103;
          *(_OWORD *)((char *)v74 + 1044) = v76;
          v78 = v104;
          *(_OWORD *)((char *)v74 + 1060) = v77;
          *(_OWORD *)((char *)v74 + 1076) = v78;
          *((_DWORD *)v74 + 273) = v75;
          if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
            WPP_SF_qddddddd(
              *((_QWORD *)WPP_GLOBAL_Control + 42),
              117,
              &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
              this,
              *((_DWORD *)this[2] + 82),
              *((_DWORD *)this[2] + 78),
              24,
              12,
              *((_DWORD *)this[2] + 141),
              *((_DWORD *)this[2] + 139),
              _mm_cvtsi128_si32(_mm_srli_si128(si128, 4)));
        }
        else
        {
          if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
            WPP_SF_qdd(
              *((_QWORD *)WPP_GLOBAL_Control + 42),
              118,
              &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
              this,
              *((_DWORD *)this[2] + 78),
              *((_DWORD *)this[2] + 139));
          v3 = CxCodeVideoProcD3DDataHandler::ResolveFallbackShader(
                 (CxCodeVideoProcD3DDataHandler *)this,
                 *((enum DXGI_FORMAT *)this[2] + 82),
                 *((enum DXGI_FORMAT *)this[2] + 141),
                 0);
          if ( v3 < 0 )
          {
            v79 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::InitInstance();
              v79 = CallStackTracing::s_wpInstance;
            }
            if ( *((_BYTE *)v79 + 8) )
            {
              v80 = CallStackTracing::GetThreadRelativeContext(v79);
              if ( *((_DWORD *)v80 + 499) != v3 )
                CallStackContext::TraceFailure(
                  v80,
                  "CxCodeVideoProcD3D11DataHandler::CreateD3DVideoProcessorInternal",
                  2245,
                  v3);
            }
            if ( g_wppLevels )
            {
              v6 = 119;
              goto LABEL_185;
            }
            goto LABEL_186;
          }
        }
      }
      else if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
      {
        WPP_SF_qdd(
          *((_QWORD *)WPP_GLOBAL_Control + 42),
          120,
          &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
          this,
          *((_DWORD *)v60 + 78),
          *((_DWORD *)v60 + 139));
      }
    }
    goto LABEL_119;
  }
  v7 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v7 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v7 + 8) )
  {
    v8 = CallStackTracing::GetThreadRelativeContext(v7);
    if ( *((_DWORD *)v8 + 499) != v3 )
      CallStackContext::TraceFailure(v8, "CxCodeVideoProcD3D11DataHandler::CreateD3DVideoProcessorInternal", 2121, v3);
  }
  if ( g_wppLevels )
  {
    v6 = 103;
    goto LABEL_185;
  }
LABEL_186:
  if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
  {
    v90 = (unsigned int *)this[2];
    v91 = v90 ? v90[219] : 0;
    WPP_SF_qddddddddd(
      *((_QWORD *)WPP_GLOBAL_Control + 42),
      v90[536],
      v90[216],
      this,
      v90[230],
      v90[227],
      v90[246],
      v91,
      v90[247],
      v90[248],
      v90[223],
      v90[216],
      v90[536]);
    if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
      WPP_SF_qdd(
        *((_QWORD *)WPP_GLOBAL_Control + 42),
        126,
        &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
        this,
        *((_DWORD *)this[2] + 275),
        *((_DWORD *)this[2] + 250));
  }
  if ( v3 < 0 )
    CxCodeVideoProcD3D11DataHandler::DestroyD3DResources((CxCodeVideoProcD3D11DataHandler *)this);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v97);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18006dad0  mov     rax, rsp
0x18006dad3  push    rbp
0x18006dad4  push    rbx
0x18006dad5  push    rsi
0x18006dad6  push    rdi
0x18006dad7  push    r12
0x18006dad9  push    r13
0x18006dadb  push    r14
0x18006dadd  push    r15
0x18006dadf  lea     rbp, [rax-128h]
0x18006dae6  sub     rsp, 1E8h
0x18006daed  movaps  xmmword ptr [rax-58h], xmm6
0x18006daf1  mov     rax, cs:__security_cookie
0x18006daf8  xor     rax, rsp
0x18006dafb  mov     [rbp+120h+var_60], rax
0x18006db02  mov     r13, rcx
0x18006db05  lea     rdx, aCxcodevideopro_81; "CxCodeVideoProcD3D11DataHandler::Create"...
0x18006db0c  lea     rcx, [rbp+120h+var_19C]; this
0x18006db10  mov     r8d, 83Ch; int
0x18006db16  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006db1b  xorps   xmm0, xmm0
0x18006db1e  xor     eax, eax
0x18006db20  mov     rcx, r13; this
0x18006db23  mov     [rbp+120h+var_68], eax
0x18006db29  movups  [rbp+120h+var_88], xmm0
0x18006db30  movups  [rbp+120h+var_78], xmm0
0x18006db37  call    ?EnsureD3D11Context@CxCodeVideoProcD3D11DataHandler@@AEAAXXZ; CxCodeVideoProcD3D11DataHandler::EnsureD3D11Context(void)
0x18006db3c  mov     rax, [r13+10h]
0x18006db40  xor     r15d, r15d
0x18006db43  mov     r12d, 1
0x18006db49  mov     rcx, r13; this
0x18006db4c  cmp     [rax+3D8h], r15d
0x18006db53  jz      loc_18006DBDD
0x18006db59  mov     [rax+860h], r15d
0x18006db60  xor     r9d, r9d; bool
0x18006db63  mov     rdx, [r13+10h]
0x18006db67  mov     r8d, [rdx+234h]; enum DXGI_FORMAT
0x18006db6e  mov     edx, [rdx+148h]; enum DXGI_FORMAT
0x18006db74  call    ?ResolveFallbackShader@CxCodeVideoProcD3DDataHandler@@IEAAJW4DXGI_FORMAT@@0_N@Z; CxCodeVideoProcD3DDataHandler::ResolveFallbackShader(DXGI_FORMAT,DXGI_FORMAT,bool)
0x18006db79  mov     ebx, eax
0x18006db7b  test    eax, eax
0x18006db7d  jns     loc_18006E3AE
0x18006db83  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006db8a  test    rcx, rcx
0x18006db8d  jnz     short loc_18006DB9B
0x18006db8f  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18006db94  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18006db9b  cmp     [rcx+8], r15b
0x18006db9f  jz      short loc_18006DBC6
0x18006dba1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006dba6  cmp     [rax+7CCh], ebx
0x18006dbac  jz      short loc_18006DBC6
0x18006dbae  mov     r9d, ebx; int
0x18006dbb1  lea     rdx, aCxcodevideopro_81; "CxCodeVideoProcD3D11DataHandler::Create"...
0x18006dbb8  mov     r8d, 845h; int
0x18006dbbe  mov     rcx, rax; this
0x18006dbc1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006dbc6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18006dbcd  jb      loc_18006E951
0x18006dbd3  mov     edx, 66h ; 'f'
0x18006dbd8  jmp     loc_18006E933
0x18006dbdd  call    ?EnsureD3D11VideoProcessor@CxCodeVideoProcD3D11DataHandler@@IEAAJXZ; CxCodeVideoProcD3D11DataHandler::EnsureD3D11VideoProcessor(void)
0x18006dbe2  mov     ebx, eax
0x18006dbe4  test    eax, eax
0x18006dbe6  jns     short loc_18006DC42
0x18006dbe8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006dbef  test    rcx, rcx
0x18006dbf2  jnz     short loc_18006DC00
0x18006dbf4  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18006dbf9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18006dc00  cmp     [rcx+8], r15b
0x18006dc04  jz      short loc_18006DC2B
0x18006dc06  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006dc0b  cmp     [rax+7CCh], ebx
0x18006dc11  jz      short loc_18006DC2B
0x18006dc13  mov     r9d, ebx; int
0x18006dc16  lea     rdx, aCxcodevideopro_81; "CxCodeVideoProcD3D11DataHandler::Create"...
0x18006dc1d  mov     r8d, 849h; int
0x18006dc23  mov     rcx, rax; this
0x18006dc26  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006dc2b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18006dc32  jb      loc_18006E951
0x18006dc38  mov     edx, 67h ; 'g'
0x18006dc3d  jmp     loc_18006E933
0x18006dc42  mov     rcx, [r13+928h]
0x18006dc49  test    rcx, rcx
0x18006dc4c  jz      short loc_18006DCC1
0x18006dc4e  mov     rax, [rcx]
0x18006dc51  lea     rdx, [rbp+120h+var_88]
0x18006dc58  mov     rax, [rax+48h]
0x18006dc5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dc61  mov     ebx, eax
0x18006dc63  test    eax, eax
0x18006dc65  jns     short loc_18006DCC1
0x18006dc67  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006dc6e  test    rcx, rcx
0x18006dc71  jnz     short loc_18006DC7F
0x18006dc73  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18006dc78  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18006dc7f  cmp     [rcx+8], r15b
0x18006dc83  jz      short loc_18006DCAA
0x18006dc85  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006dc8a  cmp     [rax+7CCh], ebx
0x18006dc90  jz      short loc_18006DCAA
0x18006dc92  mov     r9d, ebx; int
0x18006dc95  lea     rdx, aCxcodevideopro_81; "CxCodeVideoProcD3D11DataHandler::Create"...
0x18006dc9c  mov     r8d, 84Dh; int
0x18006dca2  mov     rcx, rax; this
0x18006dca5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006dcaa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18006dcb1  jb      loc_18006E951
0x18006dcb7  mov     edx, 68h ; 'h'
0x18006dcbc  jmp     loc_18006E933
0x18006dcc1  mov     rdx, [r13+10h]
0x18006dcc5  lea     rax, [rbp+120h+var_1A0]
0x18006dcc9  mov     [rsp+220h+var_1F0], r15d; int
0x18006dcce  mov     rcx, r13; this
0x18006dcd1  mov     [rsp+220h+var_1F8], rax; unsigned int *
0x18006dcd6  mov     [rbp+120h+var_1A0], r15d
0x18006dcda  mov     eax, [rdx+22Ch]
0x18006dce0  mov     r9d, [rdx+234h]; enum DXGI_FORMAT
0x18006dce7  mov     r8d, [rdx+138h]; enum DXGI_COLOR_SPACE_TYPE
0x18006dcee  mov     edx, [rdx+148h]; enum DXGI_FORMAT
0x18006dcf4  mov     [rsp+220h+var_200], eax; enum DXGI_COLOR_SPACE_TYPE
0x18006dcf8  call    ?CheckVPConversionSupport@CxCodeVideoProcD3D11DataHandler@@EEAAJW4DXGI_FORMAT@@W4DXGI_COLOR_SPACE_TYPE@@01PEAIH@Z; CxCodeVideoProcD3D11DataHandler::CheckVPConversionSupport(DXGI_FORMAT,DXGI_COLOR_SPACE_TYPE,DXGI_FORMAT,DXGI_COLOR_SPACE_TYPE,uint *,int)
0x18006dcfd  mov     ebx, eax
0x18006dcff  test    eax, eax
0x18006dd01  jns     short loc_18006DD5D
0x18006dd03  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006dd0a  test    rcx, rcx
0x18006dd0d  jnz     short loc_18006DD1B
0x18006dd0f  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18006dd14  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18006dd1b  cmp     [rcx+8], r15b
0x18006dd1f  jz      short loc_18006DD46
0x18006dd21  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006dd26  cmp     [rax+7CCh], ebx
0x18006dd2c  jz      short loc_18006DD46
0x18006dd2e  mov     r9d, ebx; int
0x18006dd31  lea     rdx, aCxcodevideopro_81; "CxCodeVideoProcD3D11DataHandler::Create"...
0x18006dd38  mov     r8d, 854h; int
0x18006dd3e  mov     rcx, rax; this
0x18006dd41  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006dd46  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18006dd4d  jb      loc_18006E951
0x18006dd53  mov     edx, 69h ; 'i'
0x18006dd58  jmp     loc_18006E933
0x18006dd5d  cmp     [r13+920h], r15
0x18006dd64  jz      short loc_18006DD75
0x18006dd66  test    dword ptr [rbp+120h+var_88+4], 800h
0x18006dd70  mov     bl, r12b
0x18006dd73  jnz     short loc_18006DD78
0x18006dd75  mov     bl, r15b
0x18006dd78  mov     rax, [r13+10h]
0x18006dd7c  mov     ecx, [rax+504h]
0x18006dd82  mov     r8d, [rax+1F0h]
0x18006dd89  cmp     r8d, ecx
0x18006dd8c  jnb     short loc_18006DDC5
0x18006dd8e  cmp     cs:byte_180153DE0, 20h ; ' '
0x18006dd95  jb      short loc_18006DDC2
0x18006dd97  mov     dword ptr [rsp+220h+var_1F8], ecx
0x18006dd9b  mov     edx, 6Ah ; 'j'
0x18006dda0  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dda7  mov     r9, r13
0x18006ddaa  mov     [rsp+220h+var_200], r8d
0x18006ddaf  lea     r8, WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids
0x18006ddb6  mov     rcx, [rcx+150h]
0x18006ddbd  call    WPP_SF_qdd
0x18006ddc2  mov     bl, r15b
0x18006ddc5  call    IsMFXboxVPBltPlatformSupportsHDR8Present
0x18006ddca  mov     r10, [r13+10h]
0x18006ddce  test    al, al
0x18006ddd0  movzx   r12d, bl
0x18006ddd4  mov     ebx, 1
0x18006ddd9  cmovnz  r12d, ebx
0x18006dddd  cmp     [r10+5D0h], r15
0x18006dde4  jz      short loc_18006DDFB
0x18006dde6  test    byte ptr [r10+838h], 4
0x18006ddee  jz      short loc_18006DDFB
0x18006ddf0  mov     rcx, [r13+18h]; this
0x18006ddf4  call    ?POutputType@CMFTMultiStreamTypeHandler@@QEAAPEAUIMFMediaType@@K@Z; CMFTMultiStreamTypeHandler::POutputType(ulong)
0x18006ddf9  jmp     short loc_18006DE06
0x18006ddfb  mov     rcx, [r13+18h]; this
0x18006ddff  xor     edx, edx; unsigned int
0x18006de01  call    ?PInputType@CMFTMultiStreamTypeHandler@@QEAAPEAUIMFMediaType@@K@Z; CMFTMultiStreamTypeHandler::PInputType(ulong)
0x18006de06  mov     r8, rax
0x18006de09  call    ?POutputType@CMFTMultiStreamTypeHandler@@QEAAPEAUIMFMediaType@@K@Z; CMFTMultiStreamTypeHandler::POutputType(ulong)
0x18006de0e  lea     rdx, [r10+39Ch]; struct IMFMediaType *
0x18006de15  mov     [rbp+120h+var_198], rax
0x18006de19  mov     rcx, r8; this
0x18006de1c  call    ?GetHDRMetaDataFromMediaType@MFMEDIATYPEUtils@@YAJPEAUIMFMediaType@@PEAUDXGI_HDR_METADATA_HDR10@@@Z; MFMEDIATYPEUtils::GetHDRMetaDataFromMediaType(IMFMediaType *,DXGI_HDR_METADATA_HDR10 *)
0x18006de21  test    eax, eax
0x18006de23  js      loc_18006DEED
0x18006de29  cmp     cs:byte_180153DE0, 20h ; ' '
0x18006de30  jb      loc_18006DF55
0x18006de36  mov     r15, [r13+10h]
0x18006de3a  mov     edx, 6Bh ; 'k'
0x18006de3f  movzx   eax, word ptr [r15+3B6h]
0x18006de47  movzx   ecx, word ptr [r15+3B4h]
0x18006de4f  movzx   r9d, word ptr [r15+3A8h]
0x18006de57  movzx   r8d, word ptr [r15+3AAh]
0x18006de5f  movzx   r10d, word ptr [r15+3A6h]
0x18006de67  movzx   r11d, word ptr [r15+3A4h]
0x18006de6f  movzx   ebx, word ptr [r15+3A2h]
0x18006de77  movzx   edi, word ptr [r15+3A0h]
0x18006de7f  movzx   esi, word ptr [r15+39Eh]
0x18006de87  movzx   r14d, word ptr [r15+39Ch]
0x18006de8f  mov     [rsp+78h], eax
0x18006de93  mov     eax, [r15+3B0h]
0x18006de9a  mov     [rsp+220h+var_1B0], ecx
0x18006de9e  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dea5  mov     [rsp+220h+var_1B8], eax
0x18006dea9  mov     eax, [r15+3ACh]
0x18006deb0  mov     [rsp+220h+var_1C0], eax
0x18006deb4  mov     rcx, [rcx+150h]
0x18006debb  mov     [rsp+220h+var_1C8], r8d
0x18006dec0  mov     [rsp+220h+var_1D0], r9d
0x18006dec5  mov     r9, r13
0x18006dec8  mov     [rsp+220h+var_1D8], r10d
0x18006decd  mov     [rsp+220h+var_1E0], r11d
0x18006ded2  mov     [rsp+220h+var_1E8], ebx
0x18006ded6  mov     [rsp+220h+var_1F0], edi
0x18006deda  mov     dword ptr [rsp+220h+var_1F8], esi
0x18006dede  mov     [rsp+220h+var_200], r14d
0x18006dee3  call    WPP_SF_qdddddddddddd
0x18006dee8  xor     r15d, r15d
0x18006deeb  jmp     short loc_18006DF55
0x18006deed  mov     rcx, [r13+10h]
0x18006def1  mov     dword ptr [rcx+39Ch], 40747D00h
0x18006defb  mov     dword ptr [rcx+3A0h], 75303A98h
0x18006df05  mov     dword ptr [rcx+3A4h], 0BB81D4Ch
0x18006df0f  mov     dword ptr [rcx+3A8h], 40423D13h
0x18006df19  mov     dword ptr [rcx+3ACh], 50h ; 'P'
0x18006df23  mov     [rcx+3B0h], rbx
0x18006df2a  cmp     cs:byte_180153DE0, 20h ; ' '
0x18006df31  jb      short loc_18006DF55
0x18006df33  mov     rcx, cs:WPP_GLOBAL_Control
0x18006df3a  lea     r8, WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids
0x18006df41  mov     edx, 6Ch ; 'l'
0x18006df46  mov     r9, r13
0x18006df49  mov     rcx, [rcx+150h]
0x18006df50  call    WPP_SF_q
0x18006df55  mov     rdx, [r13+10h]
0x18006df59  mov     rcx, [rbp+120h+var_198]; this
0x18006df5d  add     rdx, 3B8h; struct IMFMediaType *
0x18006df64  call    ?GetHDRMetaDataFromMediaType@MFMEDIATYPEUtils@@YAJPEAUIMFMediaType@@PEAUDXGI_HDR_METADATA_HDR10@@@Z; MFMEDIATYPEUtils::GetHDRMetaDataFromMediaType(IMFMediaType *,DXGI_HDR_METADATA_HDR10 *)
0x18006df69  test    eax, eax
0x18006df6b  js      loc_18006E035
0x18006df71  cmp     cs:byte_180153DE0, 20h ; ' '
0x18006df78  jb      loc_18006E0A1
0x18006df7e  mov     r15, [r13+10h]
0x18006df82  mov     edx, 6Dh ; 'm'
0x18006df87  movzx   eax, word ptr [r15+3D2h]
0x18006df8f  movzx   ecx, word ptr [r15+3D0h]
0x18006df97  movzx   r9d, word ptr [r15+3C4h]
0x18006df9f  movzx   r8d, word ptr [r15+3C6h]
0x18006dfa7  movzx   r10d, word ptr [r15+3C2h]
0x18006dfaf  movzx   r11d, word ptr [r15+3C0h]
0x18006dfb7  movzx   ebx, word ptr [r15+3BEh]
0x18006dfbf  movzx   edi, word ptr [r15+3BCh]
0x18006dfc7  movzx   esi, word ptr [r15+3BAh]
0x18006dfcf  movzx   r14d, word ptr [r15+3B8h]
0x18006dfd7  mov     [rsp+78h], eax
0x18006dfdb  mov     eax, [r15+3CCh]
0x18006dfe2  mov     [rsp+220h+var_1B0], ecx
0x18006dfe6  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dfed  mov     [rsp+220h+var_1B8], eax
0x18006dff1  mov     eax, [r15+3C8h]
0x18006dff8  mov     [rsp+220h+var_1C0], eax
0x18006dffc  mov     rcx, [rcx+150h]
0x18006e003  mov     [rsp+220h+var_1C8], r8d
0x18006e008  mov     [rsp+220h+var_1D0], r9d
0x18006e00d  mov     r9, r13
0x18006e010  mov     [rsp+220h+var_1D8], r10d
0x18006e015  mov     [rsp+220h+var_1E0], r11d
0x18006e01a  mov     [rsp+220h+var_1E8], ebx
0x18006e01e  mov     [rsp+220h+var_1F0], edi
0x18006e022  mov     dword ptr [rsp+220h+var_1F8], esi
0x18006e026  mov     [rsp+220h+var_200], r14d
0x18006e02b  call    WPP_SF_qdddddddddddd
0x18006e030  xor     r15d, r15d
0x18006e033  jmp     short loc_18006E0A1
0x18006e035  mov     rcx, [r13+10h]
0x18006e039  mov     dword ptr [rcx+3B8h], 40747D00h
0x18006e043  mov     dword ptr [rcx+3BCh], 75303A98h
0x18006e04d  mov     dword ptr [rcx+3C0h], 0BB81D4Ch
0x18006e057  mov     dword ptr [rcx+3C4h], 40423D13h
0x18006e061  mov     dword ptr [rcx+3C8h], 50h ; 'P'
0x18006e06b  mov     qword ptr [rcx+3CCh], 1
0x18006e076  cmp     cs:byte_180153DE0, 20h ; ' '
0x18006e07d  jb      short loc_18006E0A1
0x18006e07f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e086  lea     r8, WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids
0x18006e08d  mov     edx, 6Eh ; 'n'
0x18006e092  mov     r9, r13
0x18006e095  mov     rcx, [rcx+150h]
0x18006e09c  call    WPP_SF_q
0x18006e0a1  mov     r8, [r13+10h]
0x18006e0a5  mov     ecx, [r8+128h]; this
0x18006e0ac  call    ?IsTransferFunctionHDR@MFMEDIATYPEUtilsHelper@MFMEDIATYPEUtils@@YAHW4_MFVideoTransferFunction@@@Z; MFMEDIATYPEUtils::MFMEDIATYPEUtilsHelper::IsTransferFunctionHDR(_MFVideoTransferFunction)
  ... truncated ...
```
