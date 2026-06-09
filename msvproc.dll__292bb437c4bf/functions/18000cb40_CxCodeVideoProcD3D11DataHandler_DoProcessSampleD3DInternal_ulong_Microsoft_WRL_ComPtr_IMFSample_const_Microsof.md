# CxCodeVideoProcD3D11DataHandler::DoProcessSampleD3DInternal(ulong,Microsoft::WRL::ComPtr<IMFSample> const &,Microsoft::WRL::ComPtr<IMFSample> const &,D3D11_VIDEO_FRAME_FORMAT,int)

- ea: `0x18000cb40`
- end: `0x18000e080`
- name: `?DoProcessSampleD3DInternal@CxCodeVideoProcD3D11DataHandler@@UEAAJKAEBV?$ComPtr@UIMFSample@@@WRL@Microsoft@@0W4D3D11_VIDEO_FRAME_FORMAT@@H@Z`
- size: `5440`
- prototype: `__int64 __usercall@<rax>(CxCodeVideoProcD3D11DataHandler *this@<rcx>, int, int)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180039cd0`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000caec`
- `0x18000cb40`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18000edd8`
- `0x18000f150`
- `0x18000f180`
- `0x1800112b0`
- `0x18001ba40`
- `0x1800282ec`
- `0x18003639c`
- `0x1800364d0`
- `0x180036fe0`
- `0x18003c230`
- `0x18003d0d4`
- `0x18003e388`
- `0x18003eb08`
- `0x180054140`
- `0x18006bf40`
- `0x1800705f0`
- `0x1800b4524`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18000d308`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18000d5a4`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18000d308`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18000d5a4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000d0af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000d324`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000d3af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000d42c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000d4a9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000d526`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000d5c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000d63d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000d718`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000d795`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000d841`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000d8be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000d0af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000d324`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000d3af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000d42c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000d4a9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000d526`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000d5c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000d63d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000d718`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000d795`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000d841`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000d8be`

## string_xrefs

- `0x18000d2f7`: `Interlaced content not supported by shader fallback path`
- `0x18000d593`: `Interlaced content not supported by shader fallback path`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcD3D11DataHandler::DoProcessSampleD3DInternal(
        CxCodeVideoProcD3D11DataHandler *this,
        unsigned int a2,
        struct IMFSample **a3,
        struct IMFSample **a4,
        int a5,
        int a6)
{
  CallStackTracing *v7; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  struct IMFSample *v14; // r14
  struct IMFSampleVtbl *lpVtbl; // rax
  struct IMFSample *v16; // r12
  struct IMFSample *v17; // rbx
  __int64 v18; // rax
  unsigned int v19; // esi
  struct IMFSample *v20; // rcx
  struct IMFSampleVtbl *v21; // rax
  int updated; // r13d
  __int64 v23; // rax
  __int64 v24; // rdi
  LONG v25; // ecx
  LONG v26; // edx
  LONG v27; // r8d
  LONG v28; // eax
  CMFTMultiStreamTypeHandler *v29; // rcx
  struct IMFMediaType *v30; // rax
  unsigned int v31; // edx
  int v32; // esi
  struct IMFMediaType *v33; // rax
  unsigned int v34; // edx
  int v35; // edx
  int v36; // r8d
  LONG top; // r10d
  LONG bottom; // esi
  __int64 left; // r9
  LONG right; // r11d
  int v41; // ecx
  struct IMFSampleVtbl *v42; // rax
  unsigned int v43; // edx
  __int64 v44; // rax
  char v45; // di
  unsigned int v46; // edx
  unsigned int v47; // edx
  __int64 v48; // rsi
  void (__fastcall *v49)(__int64, __int64, __int64 *, __int64 *); // rdi
  __int64 v50; // rdx
  __int64 v51; // r9
  _DWORD *v52; // rax
  enum DXGI_FORMAT v53; // edi
  _DWORD *v54; // rax
  struct IMFSample **v55; // rdi
  struct IMFSample *v56; // rdi
  struct IMFSample *v57; // rcx
  __int64 v58; // rax
  enum DXGI_FORMAT *v59; // rax
  struct IMFSample *v60; // rcx
  __int64 v61; // rax
  _DWORD *v62; // rcx
  __int64 v63; // rax
  struct IMFSample **v64; // rdi
  struct IMFSample *v65; // rcx
  __int64 *v66; // rcx
  CallStackTracing *v67; // rax
  CallStackTracing *v68; // rcx
  struct IMFSample *v70; // rcx
  struct IMFSample *v71; // rcx
  __int64 *v72; // rcx
  CallStackTracing *v73; // rax
  __int64 *v74; // rcx
  CallStackTracing *v75; // rax
  struct CallStackContext *v76; // rax
  __int64 *v77; // rcx
  CallStackTracing *v78; // rax
  struct CallStackContext *v79; // rax
  __int64 *v80; // rcx
  CallStackTracing *v81; // rax
  struct CallStackContext *v82; // rax
  __int64 *v83; // rcx
  CallStackTracing *v84; // rax
  struct CallStackContext *v85; // rax
  __int64 *v86; // rcx
  CallStackTracing *v87; // rax
  struct CallStackContext *v88; // rax
  __int64 *v89; // rcx
  CallStackTracing *v90; // rax
  struct CallStackContext *v91; // rax
  struct CallStackContext *v92; // rax
  struct CallStackContext *v93; // rax
  __int64 *v94; // rcx
  CallStackTracing *v95; // rax
  struct CallStackContext *v96; // rax
  __int64 *v97; // rcx
  CallStackTracing *v98; // rax
  struct CallStackContext *v99; // rax
  struct CallStackContext *v100; // rax
  __int64 *v101; // rcx
  CallStackTracing *v102; // rax
  struct CallStackContext *v103; // rax
  __int64 *v104; // rcx
  CallStackTracing *v105; // rax
  struct CallStackContext *v106; // rax
  __int64 v107; // rdx
  int v108; // eax
  int v109; // eax
  struct IMFSample **v110; // rdx
  int v111; // edi
  _QWORD *InputSamples; // rax
  _DWORD *v113; // rax
  unsigned int v114; // ecx
  unsigned int v115; // edx
  __int64 v116; // rax
  unsigned int v117; // r13d
  __int64 v118; // r8
  _QWORD *v119; // rax
  HRESULT (__stdcall *GetUnknown)(IMFSample *, const GUID *const, const IID *const, LPVOID *); // rdi
  unsigned int v121; // [rsp+50h] [rbp-B0h] BYREF
  enum DXGI_FORMAT v122; // [rsp+54h] [rbp-ACh]
  int v123; // [rsp+58h] [rbp-A8h]
  struct tagRECT v124; // [rsp+5Ch] [rbp-A4h]
  struct IMFSample *v125; // [rsp+70h] [rbp-90h] BYREF
  struct IMFSample *v126; // [rsp+78h] [rbp-88h] BYREF
  char v127[4]; // [rsp+80h] [rbp-80h] BYREF
  struct tagRECT v128; // [rsp+84h] [rbp-7Ch]
  unsigned int v129; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned int v130; // [rsp+98h] [rbp-68h]
  struct IMFSample *v131; // [rsp+A0h] [rbp-60h] BYREF
  struct IMFSample **v132; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v133; // [rsp+B0h] [rbp-50h]
  enum DXGI_FORMAT v134; // [rsp+B4h] [rbp-4Ch]
  int v135; // [rsp+B8h] [rbp-48h]
  __int64 *v136; // [rsp+C0h] [rbp-40h]
  struct tagRECT v137; // [rsp+C8h] [rbp-38h] BYREF
  struct tagRECT v138; // [rsp+D8h] [rbp-28h] BYREF
  int v139; // [rsp+F0h] [rbp-10h]
  __int64 v140; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v141; // [rsp+100h] [rbp+0h]
  __int64 v142; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v143[360]; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v144; // [rsp+278h] [rbp+178h] BYREF

  v136 = (__int64 *)a3;
  v7 = CallStackTracing::s_wpInstance;
  v132 = a4;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v7 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v7 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v7);
    v12 = *((unsigned int *)ThreadRelativeContext + 497);
    if ( (unsigned int)v12 < *((_DWORD *)ThreadRelativeContext + 498) )
    {
      v13 = 2 * v12;
      *((_QWORD *)ThreadRelativeContext + v13) = "CxCodeVideoProcD3D11DataHandler::DoProcessSampleD3DInternal";
      *((_DWORD *)ThreadRelativeContext + 2 * v13 + 2) = 5591;
    }
    ++*((_DWORD *)ThreadRelativeContext + 497);
  }
  v14 = *a3;
  v131 = v14;
  if ( v14 )
  {
    ((void (__fastcall *)(struct IMFSample *))v14->lpVtbl->AddRef)(v14);
    lpVtbl = v14->lpVtbl;
    v16 = v14;
    v126 = v14;
    ((void (__fastcall *)(struct IMFSample *))lpVtbl->AddRef)(v14);
  }
  else
  {
    v16 = 0;
    v126 = 0;
  }
  v17 = *a4;
  v125 = v17;
  if ( v17 )
    ((void (__fastcall *)(struct IMFSample *))v17->lpVtbl->AddRef)(v17);
  v18 = *((_QWORD *)this + 2);
  v135 = (a2 >> 28) & 1;
  v19 = 0;
  v122 = *(_DWORD *)(v18 + 328);
  v134 = *(_DWORD *)(v18 + 564);
  v20 = *a3;
  v139 = 0;
  v142 = 0;
  v144 = 1;
  v137 = 0;
  v129 = 0;
  v138 = 0;
  v21 = v20->lpVtbl;
  v123 = 0;
  updated = ((__int64 (__fastcall *)(struct IMFSample *, unsigned int *))v21->GetBufferCount)(v20, &v129);
  if ( updated < 0 )
  {
    v74 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v75 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v75;
      if ( v75 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v75 + 8LL))(v75, 2032) )
      {
        v74 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v74 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v74 + 8) )
    {
      v76 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v74);
      if ( *((_DWORD *)v76 + 499) != updated )
        CallStackContext::TraceFailure(
          v76,
          "CxCodeVideoProcD3D11DataHandler::DoProcessSampleD3DInternal",
          5606,
          updated);
    }
    if ( g_wppLevels )
    {
      v107 = 343;
LABEL_187:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v107,
        &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
        this,
        updated);
      goto LABEL_80;
    }
    goto LABEL_80;
  }
  v133 = v129;
  v23 = 352;
  v130 = 0;
  v24 = *((_QWORD *)this + 4);
  if ( !*(_DWORD *)(v24 + 368) )
    v23 = 320;
  v25 = *(_DWORD *)(v23 + v24);
  v26 = *(_DWORD *)(v23 + v24 + 4);
  v27 = *(_DWORD *)(v23 + v24 + 8);
  v28 = *(_DWORD *)(v23 + v24 + 12);
  v128.left = v25;
  v128.top = v26;
  v124.left = v25;
  v29 = *(CMFTMultiStreamTypeHandler **)(v24 + 8);
  v124.top = v26;
  v128.right = v27;
  v128.bottom = v28;
  v124.right = v27;
  v124.bottom = v28;
  v30 = CMFTMultiStreamTypeHandler::PInputType(v29, 0);
  v121 = v31;
  if ( ((int (__fastcall *)(struct IMFMediaType *, __int64 *, unsigned int *))v30->lpVtbl->GetUINT32)(
         v30,
         MF_MT_VIDEO_3D_LEFT_IS_BASE,
         &v121) >= 0 )
    v32 = v121;
  else
    v32 = 1;
  v33 = CMFTMultiStreamTypeHandler::PInputType(*(CMFTMultiStreamTypeHandler **)(v24 + 8), 0);
  v121 = v34;
  if ( ((int (__fastcall *)(struct IMFMediaType *, __int64 *, unsigned int *))v33->lpVtbl->GetUINT32)(
         v33,
         MF_MT_VIDEO_3D_FIRST_IS_LEFT,
         &v121) >= 0 )
    v35 = v121;
  else
    v35 = 1;
  if ( v32 )
  {
    if ( v35 )
    {
LABEL_20:
      v36 = 1;
      goto LABEL_21;
    }
  }
  else if ( !v35 )
  {
    goto LABEL_20;
  }
  v36 = 0;
LABEL_21:
  top = v128.top;
  bottom = v128.bottom;
  left = (unsigned int)v128.left;
  right = v128.right;
  if ( *(_DWORD *)(v24 + 604) == 2 )
  {
    v109 = *(_DWORD *)(v24 + 308);
    v124.right = v128.right + v109;
    v124.left = v109 + v128.left;
  }
  else if ( *(_DWORD *)(v24 + 604) == 3 )
  {
    v108 = *(_DWORD *)(v24 + 304);
    v124.bottom = v128.bottom + v108;
    v124.top = v108 + v128.top;
  }
  v41 = *(_DWORD *)(v24 + 992);
  if ( !v41 )
  {
    if ( v36 )
    {
LABEL_115:
      v137.left = left;
      v137.top = top;
      v137.right = right;
      v137.bottom = bottom;
      goto LABEL_26;
    }
LABEL_114:
    left = (unsigned int)v124.left;
    bottom = v124.bottom;
    right = v124.right;
    top = v124.top;
    goto LABEL_115;
  }
  if ( v41 != 1 )
    goto LABEL_26;
  if ( v133 < 2 )
  {
    if ( v36 )
      goto LABEL_115;
    goto LABEL_114;
  }
  if ( v35 )
  {
    v138 = v124;
    goto LABEL_115;
  }
  v137 = v124;
  v138 = v128;
LABEL_26:
  v42 = v17->lpVtbl;
  v121 = 0;
  if ( ((int (__fastcall *)(struct IMFSample *, __int64 *, unsigned int *, __int64))v42->GetUINT32)(
         v17,
         MFSampleExtension_Rolling420_FrameCounter,
         &v121,
         left) < 0 )
    v121 = 4;
  v44 = *((_QWORD *)this + 2);
  if ( !*(_DWORD *)(v44 + 988)
    && !*(_DWORD *)(v44 + 992)
    && !*(_DWORD *)(v44 + 892)
    && (!*(_QWORD *)(v44 + 1488) || !*(_DWORD *)(v44 + 2144)) )
  {
    v45 = 0;
LABEL_36:
    v47 = v130;
    v19 = v130;
    goto LABEL_37;
  }
  v45 = 1;
  if ( !(unsigned int)IsProtectedSample(v14, v43) && !(unsigned int)IsProtectedSample(v17, v46) )
    goto LABEL_36;
  v19 = 1;
  v47 = 0x80000;
  v123 = 1;
LABEL_37:
  if ( v47 == *(_DWORD *)(*((_QWORD *)this + 2) + 1208LL)
    || (updated = CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples(this, v47), updated >= 0) )
  {
    if ( !xvpDataHandlerState::CanUseSphereViewOpt(*((xvpDataHandlerState **)this + 2))
      || !*((_BYTE *)this + 250)
      || (updated = CxCodeVideoProcD3D11DataHandler::UpdateSphereMapTempTexture(this), updated >= 0) )
    {
      if ( v45 || *(_QWORD *)(*((_QWORD *)this + 2) + 1488LL) )
      {
        v48 = *((_QWORD *)this + 286);
        v49 = *(void (__fastcall **)(__int64, __int64, __int64 *, __int64 *))(*(_QWORD *)v48 + 712LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v142);
        v49(v48, 2, &v140, &v142);
        (*(void (__fastcall **)(_QWORD, unsigned int *, _BYTE *))(**((_QWORD **)this + 286) + 760LL))(
          *((_QWORD *)this + 286),
          &v144,
          v143);
        v139 = 1;
      }
      v50 = *((_QWORD *)this + 2);
      if ( *(_QWORD *)(v50 + 1488) )
      {
        if ( *(_DWORD *)(v50 + 2104) == 1 )
        {
          Microsoft::WRL::ComPtr<ID3D11VideoProcessor>::operator=(&v131, v50 + 2128);
          v14 = v131;
        }
        else
        {
          if ( *(_DWORD *)(v50 + 2144) || *(_DWORD *)(v50 + 992) || *(_DWORD *)(v50 + 892) || *(_DWORD *)(v50 + 988) )
          {
            if ( !*(_QWORD *)(v50 + 2128) )
              CxCodeVideoProcD3D11DataHandler::CreateRendererEffectIntermediate(this, *(_DWORD *)(v50 + 1208));
            v110 = (struct IMFSample **)(*((_QWORD *)this + 2) + 2128LL);
            v111 = 0;
          }
          else
          {
            v110 = &v131;
            v111 = 1;
          }
          Microsoft::WRL::ComPtr<ID3D11VideoProcessor>::operator=(&v126, v110);
          if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 42),
              346,
              &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
              this,
              v111);
          InputSamples = (_QWORD *)CxCodeVideoProcD3DDataHandler::GetInputSamples(this);
          v16 = v126;
          updated = RendererEffectWrapper::ProcessFrame(
                      (RendererEffectWrapper *)(*((_QWORD *)this + 2) + 1336LL),
                      InputSamples,
                      (__int64)v126);
          if ( updated < 0 )
          {
            v83 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v84 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v84;
              if ( v84
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v84 + 8LL))(v84, 2032) )
              {
                v83 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v83 = &qword_180153440;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
              }
            }
            if ( *((_BYTE *)v83 + 8) )
            {
              v85 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v83);
              if ( *((_DWORD *)v85 + 499) != updated )
                CallStackContext::TraceFailure(
                  v85,
                  "CxCodeVideoProcD3D11DataHandler::DoProcessSampleD3DInternal",
                  5662,
                  updated);
            }
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                347,
                &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
                this,
                updated);
            v19 = v123;
            goto LABEL_80;
          }
          Microsoft::WRL::ComPtr<ID3D11VideoProcessor>::operator=(&v125, &v126);
          v17 = v125;
          v122 = *(_DWORD *)(*((_QWORD *)this + 2) + 1204LL);
        }
      }
      v19 = v123;
      if ( v123 )
      {
        (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 288) + 1160LL))(*((_QWORD *)this + 288), 1);
        if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 42), 348, &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids, this);
      }
      CxCodeVideoProcD3D11DataHandler::ProcessOutsideMode(this);
      v52 = (_DWORD *)*((_QWORD *)this + 2);
      if ( v52[247] )
      {
        if ( a5 )
        {
          RoOriginateErrorW(3222091478LL, 56, L"Interlaced content not supported by shader fallback path", v51);
          v86 = (__int64 *)CallStackTracing::s_wpInstance;
          updated = -1072875818;
          if ( !CallStackTracing::s_wpInstance )
          {
            v87 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v87;
            if ( v87 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v87 + 8LL))(v87, 2032) )
            {
              v86 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v86 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v86 + 8) )
          {
            v88 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v86);
            if ( *((_DWORD *)v88 + 499) != -1072875818 )
              CallStackContext::TraceFailure(
                v88,
                "CxCodeVideoProcD3D11DataHandler::DoProcessSampleD3DInternal",
                5683,
                -1072875818);
          }
          if ( g_wppLevels )
          {
            v107 = 349;
            goto LABEL_187;
          }
          goto LABEL_80;
        }
        if ( v52[536] || v52[248] || v52[223] )
        {
          Microsoft::WRL::ComPtr<ID3D11VideoProcessor>::operator=(&v126, (char *)this + 1176);
          v114 = 0;
          v115 = 0;
          v53 = *(_DWORD *)(*((_QWORD *)this + 2) + 1200LL);
        }
        else
        {
          Microsoft::WRL::ComPtr<ID3D11VideoProcessor>::operator=(&v126, &v131);
          v113 = (_DWORD *)*((_QWORD *)this + 2);
          v53 = v113[141];
          v114 = v113[107];
          v115 = v113[106];
        }
        v16 = v126;
        updated = CxCodeVideoProcD3D11DataHandler::DoProcessSamplePreConvertFallback(
                    this,
                    v17,
                    v126,
                    (struct tagPOINT)(v115 | ((unsigned __int64)v114 << 32)),
                    v122,
                    v53);
        if ( updated < 0 )
        {
          v89 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v90 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v90;
            if ( v90 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v90 + 8LL))(v90, 2032) )
            {
              v89 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v89 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v89 + 8) )
          {
            v91 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v89);
            if ( *((_DWORD *)v91 + 499) != updated )
              CallStackContext::TraceFailure(
                v91,
                "CxCodeVideoProcD3D11DataHandler::DoProcessSampleD3DInternal",
                5690,
                updated);
          }
          if ( g_wppLevels )
          {
            v107 = 350;
            goto LABEL_187;
          }
          goto LABEL_80;
        }
        Microsoft::WRL::ComPtr<ID3D11VideoProcessor>::operator=(&v125, &v126);
        v17 = v125;
        v122 = v53;
      }
      else
      {
        v53 = v134;
      }
      v54 = (_DWORD *)*((_QWORD *)this + 2);
      if ( v54[536] && !v54[246] )
      {
        v55 = (struct IMFSample **)((char *)this + 1168);
        if ( !v54[248] )
          v55 = &v131;
        v56 = *v55;
        if ( v16 != v56 )
        {
          if ( v56 )
            ((void (__fastcall *)(struct IMFSample *))v56->lpVtbl->AddRef)(v56);
          v57 = v16;
          v16 = v56;
          if ( v57 )
            ((void (__fastcall *)(struct IMFSample *))v57->lpVtbl->Release)(v57);
        }
        v58 = *((_QWORD *)this + 2);
        if ( *(_DWORD *)(v58 + 992) )
          v59 = (enum DXGI_FORMAT *)(v58 + 1196);
        else
          v59 = (enum DXGI_FORMAT *)(v58 + 564);
        v53 = *v59;
        updated = CxCodeVideoProcD3D11DataHandler::DoProcessSampleVPBlt(
                    this,
                    &v137,
                    &v138,
                    v17,
                    v16,
                    a6,
                    v135,
                    v122,
                    *v59);
        if ( updated < 0 )
        {
          v68 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v68 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v68 + 8) )
          {
            v92 = CallStackTracing::GetThreadRelativeContext(v68);
            if ( *((_DWORD *)v92 + 499) != updated )
              CallStackContext::TraceFailure(
                v92,
                "CxCodeVideoProcD3D11DataHandler::DoProcessSampleD3DInternal",
                5700,
                updated);
          }
          if ( g_wppLevels )
          {
            v107 = 351;
            goto LABEL_187;
          }
          goto LABEL_80;
        }
        if ( v17 != v16 )
        {
          if ( v16 )
            ((void (__fastcall *)(struct IMFSample *))v16->lpVtbl->AddRef)(v16);
          v60 = v17;
          v17 = v16;
          if ( v60 )
            ((void (__fastcall *)(struct IMFSample *))v60->lpVtbl->Release)(v60);
        }
        v122 = v53;
      }
      v61 = *((_QWORD *)this + 2);
      v62 = (_DWORD *)(v61 + 892);
      if ( *(_DWORD *)(v61 + 992) || *v62 )
      {
        if ( v17 == *v132 && a5 )
        {
          RoOriginateErrorW(3222091478LL, 56, L"Interlaced content not supported by shader fallback path", v51);
          v72 = (__int64 *)CallStackTracing::s_wpInstance;
          updated = -1072875818;
          if ( !CallStackTracing::s_wpInstance )
          {
            v73 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v73;
            if ( v73 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v73 + 8LL))(v73, 2032) )
            {
              v72 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v72 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v72 + 8) )
          {
            v93 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v72);
            if ( *((_DWORD *)v93 + 499) != -1072875818 )
              CallStackContext::TraceFailure(
                v93,
                "CxCodeVideoProcD3D11DataHandler::DoProcessSampleD3DInternal",
                5722,
                -1072875818);
          }
          if ( g_wppLevels )
          {
            v107 = 352;
            goto LABEL_187;
          }
          goto LABEL_80;
        }
        if ( *v62 )
        {
          v116 = MFD3D::D3DCbufferWrapper<_stD3D11ColorConversionGlobals>::operator->((char *)this + 448);
          v117 = v121;
          v118 = v121;
          *(_DWORD *)(v116 + 48) = v121;
          (*(void (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)*v136 + 168LL))(
            *v136,
            MFSampleExtension_Rolling420_FrameCounter,
            v118);
          if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 42),
              353,
              &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
              this,
              v117);
        }
        if ( v16 != v14 )
        {
          if ( v14 )
            ((void (__fastcall *)(struct IMFSample *))v14->lpVtbl->AddRef)(v14);
          v70 = v16;
          v16 = v14;
          if ( v70 )
            ((void (__fastcall *)(struct IMFSample *))v70->lpVtbl->Release)(v70);
        }
        updated = CxCodeVideoProcD3D11DataHandler::DoProcessSampleShaderFallback(
                    this,
                    &v137,
                    &v138,
                    v17,
                    v16,
                    v122,
                    v53);
        if ( updated < 0 )
        {
          v94 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v95 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v95;
            if ( v95 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v95 + 8LL))(v95, 2032) )
            {
              v94 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v94 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v94 + 8) )
          {
            v96 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v94);
            if ( *((_DWORD *)v96 + 499) != updated )
              CallStackContext::TraceFailure(
                v96,
                "CxCodeVideoProcD3D11DataHandler::DoProcessSampleD3DInternal",
                5735,
                updated);
          }
          if ( g_wppLevels )
          {
            v107 = 354;
            goto LABEL_187;
          }
          goto LABEL_80;
        }
        if ( v17 != v16 )
        {
          if ( v16 )
            ((void (__fastcall *)(struct IMFSample *))v16->lpVtbl->AddRef)(v16);
          v71 = v17;
          v17 = v16;
          if ( v71 )
            ((void (__fastcall *)(struct IMFSample *))v71->lpVtbl->Release)(v71);
        }
      }
      v63 = *((_QWORD *)this + 2);
      if ( !*(_QWORD *)(v63 + 1488) || *(_DWORD *)(v63 + 2104) != 1 )
        goto LABEL_80;
      v64 = v132;
      if ( v17 != *v132 )
      {
        updated = ((__int64 (__fastcall *)(struct IMFSample *, struct IMFSample *))(*v132)->lpVtbl->CopyAllItems)(
                    *v132,
                    v17);
        if ( updated < 0 )
        {
          v97 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v98 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v98;
            if ( v98 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v98 + 8LL))(v98, 2032) )
            {
              v97 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v97 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v97 + 8) )
          {
            v99 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v97);
            if ( *((_DWORD *)v99 + 499) != updated )
              CallStackContext::TraceFailure(
                v99,
                "CxCodeVideoProcD3D11DataHandler::DoProcessSampleD3DInternal",
                5746,
                updated);
          }
          if ( g_wppLevels )
          {
            v107 = 355;
            goto LABEL_187;
          }
          goto LABEL_80;
        }
        v65 = *v64;
        v132 = 0;
        if ( ((int (__fastcall *)(struct IMFSample *, struct IMFSample ***))v65->lpVtbl->GetSampleDuration)(v65, &v132) >= 0 )
        {
          updated = ((__int64 (__fastcall *)(struct IMFSample *, struct IMFSample **))v17->lpVtbl->SetSampleDuration)(
                      v17,
                      v132);
          if ( updated < 0 )
          {
            v66 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v67;
              if ( v67
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v67 + 8LL))(v67, 2032) )
              {
                v66 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v66 = &qword_180153440;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
              }
            }
            if ( *((_BYTE *)v66 + 8) )
            {
              v100 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v66);
              if ( *((_DWORD *)v100 + 499) != updated )
                CallStackContext::TraceFailure(
                  v100,
                  "CxCodeVideoProcD3D11DataHandler::DoProcessSampleD3DInternal",
                  5752,
                  updated);
            }
            if ( g_wppLevels )
            {
              v107 = 356;
              goto LABEL_187;
            }
            goto LABEL_80;
          }
        }
      }
      if ( v19 )
      {
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 288) + 1160LL))(*((_QWORD *)this + 288), 0);
        v19 = 0;
      }
      v119 = (_QWORD *)CxCodeVideoProcD3DDataHandler::GetInputSamples(this);
      updated = RendererEffectWrapper::ProcessFrame(
                  (RendererEffectWrapper *)(*((_QWORD *)this + 2) + 1336LL),
                  v119,
                  *v136);
      if ( updated < 0 )
      {
        v101 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v102 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v102;
          if ( v102 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v102 + 8LL))(v102, 2032) )
          {
            v101 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v101 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v101 + 8) )
        {
          v103 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v101);
          if ( *((_DWORD *)v103 + 499) != updated )
            CallStackContext::TraceFailure(
              v103,
              "CxCodeVideoProcD3D11DataHandler::DoProcessSampleD3DInternal",
              5763,
              updated);
        }
        if ( g_wppLevels )
        {
          v107 = 357;
          goto LABEL_187;
        }
      }
      else
      {
        v125 = 0;
        GetUnknown = v17->lpVtbl->GetUnknown;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v125);
        if ( !((unsigned int (__fastcall *)(struct IMFSample *, __int64 *, GUID *, struct IMFSample **))GetUnknown)(
                v17,
                MF_SA_HISTOGRAM_BOUNDS,
                &GUID_c40a00f2_b93a_4d80_ae8c_5a1c634f58e4,
                &v125) )
        {
          updated = ((__int64 (__fastcall *)(struct IMFSample *, __int64 *))v17->lpVtbl->DeleteItem)(
                      v17,
                      MF_SA_HISTOGRAM_BOUNDS);
          if ( updated < 0 )
          {
            v104 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v105 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v105;
              if ( v105
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v105 + 8LL))(v105, 2032) )
              {
                v104 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v104 = &qword_180153440;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
              }
            }
            if ( *((_BYTE *)v104 + 8) )
            {
              v106 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v104);
              if ( *((_DWORD *)v106 + 499) != updated )
                CallStackContext::TraceFailure(
                  v106,
                  "CxCodeVideoProcD3D11DataHandler::DoProcessSampleD3DInternal",
                  5771,
                  updated);
            }
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                358,
                &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
                this,
                updated);
          }
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v125);
      }
      goto LABEL_80;
    }
    v80 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v81 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v81;
      if ( v81 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v81 + 8LL))(v81, 2032) )
      {
        v80 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v80 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v80 + 8) )
    {
      v82 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v80);
      if ( *((_DWORD *)v82 + 499) != updated )
        CallStackContext::TraceFailure(
          v82,
          "CxCodeVideoProcD3D11DataHandler::DoProcessSampleD3DInternal",
          5632,
          updated);
    }
    if ( g_wppLevels )
    {
      v107 = 345;
      goto LABEL_187;
    }
  }
  else
  {
    v77 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v78 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v78;
      if ( v78 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v78 + 8LL))(v78, 2032) )
      {
        v77 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v77 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v77 + 8) )
    {
      v79 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v77);
      if ( *((_DWORD *)v79 + 499) != updated )
        CallStackContext::TraceFailure(
          v79,
          "CxCodeVideoProcD3D11DataHandler::DoProcessSampleD3DInternal",
          5626,
          updated);
    }
    if ( g_wppLevels )
    {
      v107 = 344;
      goto LABEL_187;
    }
  }
LABEL_80:
  if ( v139 )
  {
    (*(void (__fastcall **)(_QWORD, _QWORD, _BYTE *))(**((_QWORD **)this + 286) + 352LL))(
      *((_QWORD *)this + 286),
      v144,
      v143);
    (*(void (__fastcall **)(_QWORD, __int64, __int64 *, __int64))(**((_QWORD **)this + 286) + 264LL))(
      *((_QWORD *)this + 286),
      2,
      &v140,
      v142);
    _mm_lfence();
    if ( v140 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v140 + 16LL))(v140);
      v140 = 0;
    }
    if ( v141 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v141 + 16LL))(v141);
      v141 = 0;
    }
  }
  if ( v19 )
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 288) + 1160LL))(*((_QWORD *)this + 288), 0);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v142);
  if ( v17 )
    ((void (__fastcall *)(struct IMFSample *))v17->lpVtbl->Release)(v17);
  if ( v16 )
    ((void (__fastcall *)(struct IMFSample *))v16->lpVtbl->Release)(v16);
  if ( v14 )
    ((void (__fastcall *)(struct IMFSample *))v14->lpVtbl->Release)(v14);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v127);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18000cb40  mov     [rsp-8+arg_8], rbx
0x18000cb45  push    rbp
0x18000cb46  push    rsi
0x18000cb47  push    rdi
0x18000cb48  push    r12
0x18000cb4a  push    r13
0x18000cb4c  push    r14
0x18000cb4e  push    r15
0x18000cb50  lea     rbp, [rsp-190h]
0x18000cb58  sub     rsp, 290h
0x18000cb5f  mov     rax, cs:__security_cookie
0x18000cb66  xor     rax, rsp
0x18000cb69  mov     [rbp+1C0h+var_40], rax
0x18000cb70  mov     r15, rcx
0x18000cb73  mov     [rbp+1C0h+var_200], r8
0x18000cb77  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18000cb7e  mov     rbx, r9
0x18000cb81  mov     [rbp+1C0h+var_218], rbx
0x18000cb85  mov     r13, r8
0x18000cb88  mov     edi, edx
0x18000cb8a  test    rcx, rcx
0x18000cb8d  jz      loc_18000D257
0x18000cb93  cmp     byte ptr [rcx+8], 0
0x18000cb97  lea     rsi, aCxcodevideopro; "CxCodeVideoProcD3D11DataHandler::DoProc"...
0x18000cb9e  jz      short loc_18000CBC8
0x18000cba0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000cba5  mov     ecx, [rax+7C4h]
0x18000cbab  cmp     ecx, [rax+7C8h]
0x18000cbb1  jnb     short loc_18000CBC2
0x18000cbb3  add     rcx, rcx
0x18000cbb6  mov     [rax+rcx*8], rsi
0x18000cbba  mov     dword ptr [rax+rcx*8+8], 15D7h
0x18000cbc2  inc     dword ptr [rax+7C4h]
0x18000cbc8  mov     r14, [r13+0]
0x18000cbcc  mov     [rbp+1C0h+var_220], r14
0x18000cbd0  test    r14, r14
0x18000cbd3  jz      loc_18000D92B
0x18000cbd9  mov     rax, [r14]
0x18000cbdc  mov     rcx, r14
0x18000cbdf  mov     rax, [rax+8]
0x18000cbe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbe8  mov     rax, [r14]
0x18000cbeb  mov     rcx, r14
0x18000cbee  mov     r12, r14
0x18000cbf1  mov     [rsp+2C0h+var_248], r14
0x18000cbf6  mov     rax, [rax+8]
0x18000cbfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbff  mov     rbx, [rbx]
0x18000cc02  mov     [rsp+2C0h+var_250], rbx
0x18000cc07  test    rbx, rbx
0x18000cc0a  jz      short loc_18000CC1B
0x18000cc0c  mov     rax, [rbx]
0x18000cc0f  mov     rcx, rbx
0x18000cc12  mov     rax, [rax+8]
0x18000cc16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc1b  mov     rax, [r15+10h]
0x18000cc1f  lea     rdx, [rbp+1C0h+var_22C]
0x18000cc23  shr     edi, 1Ch
0x18000cc26  xorps   xmm0, xmm0
0x18000cc29  and     edi, 1
0x18000cc2c  xorps   xmm1, xmm1
0x18000cc2f  mov     [rbp+1C0h+var_208], edi
0x18000cc32  xor     edi, edi
0x18000cc34  mov     ecx, [rax+148h]
0x18000cc3a  mov     esi, edi
0x18000cc3c  mov     [rsp+2C0h+var_26C], ecx
0x18000cc40  mov     ecx, [rax+234h]
0x18000cc46  mov     [rbp+1C0h+var_20C], ecx
0x18000cc49  mov     rcx, [r13+0]
0x18000cc4d  mov     [rbp+1C0h+var_1D0], edi
0x18000cc50  mov     [rbp+1C0h+var_1B8], rdi
0x18000cc54  mov     [rbp+1C0h+var_48], 1
0x18000cc5e  movups  xmmword ptr [rbp+1C0h+var_1F8.left], xmm0
0x18000cc62  mov     [rbp+1C0h+var_22C], edi
0x18000cc65  movups  xmmword ptr [rbp+1C0h+var_1E8.left], xmm1
0x18000cc69  mov     rax, [rcx]
0x18000cc6c  mov     [rsp+2C0h+var_268], edi
0x18000cc70  mov     rax, [rax+138h]
0x18000cc77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc7c  mov     r13d, eax
0x18000cc7f  test    eax, eax
0x18000cc81  js      loc_18000D39F
0x18000cc87  mov     eax, [rbp+1C0h+var_22C]
0x18000cc8a  mov     ecx, 140h
0x18000cc8f  mov     [rbp+1C0h+var_210], eax
0x18000cc92  mov     eax, 160h
0x18000cc97  mov     [rbp+1C0h+var_228], edi
0x18000cc9a  mov     rdi, [r15+20h]
0x18000cc9e  cmp     [rdi+170h], esi
0x18000cca4  cmovz   eax, ecx
0x18000cca7  mov     ecx, [rax+rdi]
0x18000ccaa  mov     edx, [rax+rdi+4]
0x18000ccae  mov     r8d, [rax+rdi+8]
0x18000ccb3  mov     eax, [rax+rdi+0Ch]
0x18000ccb7  mov     [rbp+1C0h+var_23C], ecx
0x18000ccba  mov     [rbp+1C0h+var_238], edx
0x18000ccbd  mov     [rsp+2C0h+var_264], ecx
0x18000ccc1  mov     rcx, [rdi+8]; this
0x18000ccc5  mov     [rsp+2C0h+var_260], edx
0x18000ccc9  xor     edx, edx; unsigned int
0x18000cccb  mov     [rbp+1C0h+var_234], r8d
0x18000cccf  mov     [rbp+1C0h+var_230], eax
0x18000ccd2  mov     [rsp+2C0h+var_25C], r8d
0x18000ccd7  mov     [rsp+2C0h+var_258], eax
0x18000ccdb  call    ?PInputType@CMFTMultiStreamTypeHandler@@QEAAPEAUIMFMediaType@@K@Z; CMFTMultiStreamTypeHandler::PInputType(ulong)
0x18000cce0  mov     r10, rax
0x18000cce3  mov     [rsp+2C0h+var_270], edx
0x18000cce7  lea     r8, [rsp+2C0h+var_270]
0x18000ccec  lea     rdx, MF_MT_VIDEO_3D_LEFT_IS_BASE
0x18000ccf3  mov     rcx, [rax]
0x18000ccf6  mov     rax, [rcx+38h]
0x18000ccfa  mov     rcx, r10
0x18000ccfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd02  test    eax, eax
0x18000cd04  jns     loc_18000D98D
0x18000cd0a  mov     esi, 1
0x18000cd0f  mov     rcx, [rdi+8]; this
0x18000cd13  xor     edx, edx; unsigned int
0x18000cd15  call    ?PInputType@CMFTMultiStreamTypeHandler@@QEAAPEAUIMFMediaType@@K@Z; CMFTMultiStreamTypeHandler::PInputType(ulong)
0x18000cd1a  mov     r10, rax
0x18000cd1d  mov     [rsp+2C0h+var_270], edx
0x18000cd21  lea     r8, [rsp+2C0h+var_270]
0x18000cd26  lea     rdx, MF_MT_VIDEO_3D_FIRST_IS_LEFT
0x18000cd2d  mov     rcx, [rax]
0x18000cd30  mov     rax, [rcx+38h]
0x18000cd34  mov     rcx, r10
0x18000cd37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd3c  test    eax, eax
0x18000cd3e  jns     loc_18000D996
0x18000cd44  mov     edx, 1
0x18000cd49  test    esi, esi
0x18000cd4b  jz      loc_18000D99F
0x18000cd51  test    edx, edx
0x18000cd53  jz      loc_18000D2E2
0x18000cd59  mov     r8d, 1
0x18000cd5f  mov     ecx, [rdi+25Ch]
0x18000cd65  mov     r10d, [rbp+1C0h+var_238]
0x18000cd69  mov     esi, [rbp+1C0h+var_230]
0x18000cd6c  mov     r9d, [rbp+1C0h+var_23C]
0x18000cd70  mov     r11d, [rbp+1C0h+var_234]
0x18000cd74  sub     ecx, 2
0x18000cd77  jz      loc_18000D9C5
0x18000cd7d  cmp     ecx, 1
0x18000cd80  jz      loc_18000D9AC
0x18000cd86  mov     ecx, [rdi+3E0h]
0x18000cd8c  test    ecx, ecx
0x18000cd8e  jz      loc_18000D373
0x18000cd94  cmp     ecx, 1
0x18000cd97  jz      loc_18000D9DF
0x18000cd9d  mov     rax, [rbx]
0x18000cda0  lea     r8, [rsp+2C0h+var_270]
0x18000cda5  lea     rdx, MFSampleExtension_Rolling420_FrameCounter
0x18000cdac  mov     [rsp+2C0h+var_270], 0
0x18000cdb4  mov     rcx, rbx
0x18000cdb7  mov     rax, [rax+38h]
0x18000cdbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdc0  test    eax, eax
0x18000cdc2  jns     loc_18000DA44
0x18000cdc8  mov     [rsp+2C0h+var_270], 4
0x18000cdd0  mov     rax, [r15+10h]
0x18000cdd4  cmp     dword ptr [rax+3DCh], 0
0x18000cddb  jz      short loc_18000CE08
0x18000cddd  mov     rcx, r14; this
0x18000cde0  mov     dil, 1
0x18000cde3  call    ?IsProtectedSample@@YAHPEAUIMFSample@@K@Z; IsProtectedSample(IMFSample *,ulong)
0x18000cde8  test    eax, eax
0x18000cdea  jnz     short loc_18000CDF8
0x18000cdec  mov     rcx, rbx; this
0x18000cdef  call    ?IsProtectedSample@@YAHPEAUIMFSample@@K@Z; IsProtectedSample(IMFSample *,ulong)
0x18000cdf4  test    eax, eax
0x18000cdf6  jz      short loc_18000CE2B
0x18000cdf8  mov     esi, 1
0x18000cdfd  mov     edx, 80000h
0x18000ce02  mov     [rsp+2C0h+var_268], esi
0x18000ce06  jmp     short loc_18000CE30
0x18000ce08  cmp     dword ptr [rax+3E0h], 0
0x18000ce0f  jnz     short loc_18000CDDD
0x18000ce11  cmp     dword ptr [rax+37Ch], 0
0x18000ce18  jnz     short loc_18000CDDD
0x18000ce1a  cmp     qword ptr [rax+5D0h], 0
0x18000ce22  jnz     loc_18000DA51
0x18000ce28  xor     dil, dil
0x18000ce2b  mov     edx, [rbp+1C0h+var_228]; unsigned int
0x18000ce2e  mov     esi, edx
0x18000ce30  mov     rax, [r15+10h]
0x18000ce34  cmp     edx, [rax+4B8h]
0x18000ce3a  jnz     loc_18000DA63
0x18000ce40  mov     rcx, [r15+10h]; this
0x18000ce44  call    ?CanUseSphereViewOpt@xvpDataHandlerState@@QEBA_NXZ; xvpDataHandlerState::CanUseSphereViewOpt(void)
0x18000ce49  test    al, al
0x18000ce4b  jnz     loc_18000DAD0
0x18000ce51  test    dil, dil
0x18000ce54  jnz     short loc_18000CE64
0x18000ce56  mov     rax, [r15+10h]
0x18000ce5a  cmp     qword ptr [rax+5D0h], 0
0x18000ce62  jz      short loc_18000CEBE
0x18000ce64  mov     rsi, [r15+8F0h]
0x18000ce6b  lea     rcx, [rbp+1C0h+var_1B8]
0x18000ce6f  mov     rax, [rsi]
0x18000ce72  mov     rdi, [rax+2C8h]
0x18000ce79  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000ce7e  lea     r9, [rbp+1C0h+var_1B8]
0x18000ce82  mov     edx, 2
0x18000ce87  lea     r8, [rbp+1C0h+var_1C8]
0x18000ce8b  mov     rcx, rsi
0x18000ce8e  mov     rax, rdi
0x18000ce91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce96  mov     rcx, [r15+8F0h]
0x18000ce9d  lea     r8, [rbp+1C0h+var_1B0]
0x18000cea1  lea     rdx, [rbp+1C0h+var_48]
0x18000cea8  mov     rax, [rcx]
0x18000ceab  mov     rax, [rax+2F8h]
0x18000ceb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ceb7  mov     [rbp+1C0h+var_1D0], 1
0x18000cebe  mov     rdx, [r15+10h]
0x18000cec2  cmp     qword ptr [rdx+5D0h], 0
0x18000ceca  jnz     loc_18000DB22
0x18000ced0  mov     esi, [rsp+2C0h+var_268]
0x18000ced4  test    esi, esi
0x18000ced6  jnz     loc_18000DC74
0x18000cedc  mov     rcx, r15; this
0x18000cedf  call    ?ProcessOutsideMode@CxCodeVideoProcD3D11DataHandler@@QEAAXXZ; CxCodeVideoProcD3D11DataHandler::ProcessOutsideMode(void)
0x18000cee4  mov     rax, [r15+10h]
0x18000cee8  cmp     dword ptr [rax+3DCh], 0
0x18000ceef  jnz     loc_18000DCC3
0x18000cef5  mov     edi, [rbp+1C0h+var_20C]
0x18000cef8  mov     rax, [r15+10h]
0x18000cefc  cmp     dword ptr [rax+860h], 0
0x18000cf03  jz      loc_18000CFEB
0x18000cf09  cmp     dword ptr [rax+3D8h], 0
0x18000cf10  jnz     loc_18000CFEB
0x18000cf16  cmp     dword ptr [rax+3E0h], 0
0x18000cf1d  lea     rdi, [r15+490h]
0x18000cf24  jnz     short loc_18000CF2A
0x18000cf26  lea     rdi, [rbp+1C0h+var_220]
0x18000cf2a  mov     rdi, [rdi]
0x18000cf2d  cmp     r12, rdi
0x18000cf30  jz      short loc_18000CF5D
0x18000cf32  test    rdi, rdi
0x18000cf35  jz      short loc_18000CF46
0x18000cf37  mov     rax, [rdi]
0x18000cf3a  mov     rcx, rdi
0x18000cf3d  mov     rax, [rax+8]
0x18000cf41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf46  mov     rcx, r12
0x18000cf49  mov     r12, rdi
0x18000cf4c  test    rcx, rcx
0x18000cf4f  jz      short loc_18000CF5D
0x18000cf51  mov     rax, [rcx]
0x18000cf54  mov     rax, [rax+10h]
0x18000cf58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf5d  mov     rax, [r15+10h]
0x18000cf61  cmp     dword ptr [rax+3E0h], 0
0x18000cf68  jnz     loc_18000DDE1
0x18000cf6e  add     rax, 234h
0x18000cf74  mov     edi, [rax]
0x18000cf76  lea     r8, [rbp+1C0h+var_1E8]; struct tagRECT *
0x18000cf7a  mov     eax, [rsp+2C0h+var_26C]
0x18000cf7e  lea     rdx, [rbp+1C0h+var_1F8]; struct tagRECT *
0x18000cf82  mov     [rsp+2C0h+var_280], edi; enum DXGI_FORMAT
0x18000cf86  mov     r9, rbx; struct IMFSample *
0x18000cf89  mov     [rsp+2C0h+var_288], eax; enum DXGI_FORMAT
0x18000cf8d  mov     rcx, r15; this
0x18000cf90  mov     eax, [rbp+1C0h+var_208]
0x18000cf93  mov     [rsp+2C0h+var_290], eax; int
0x18000cf97  mov     eax, [rbp+1C0h+arg_28]
0x18000cf9d  mov     [rsp+2C0h+var_298], eax; int
0x18000cfa1  mov     qword ptr [rsp+2C0h+var_2A0], r12; struct IMFSample *
0x18000cfa6  call    ?DoProcessSampleVPBlt@CxCodeVideoProcD3D11DataHandler@@IEAAJAEAUtagRECT@@0PEAUIMFSample@@1HHW4DXGI_FORMAT@@2@Z; CxCodeVideoProcD3D11DataHandler::DoProcessSampleVPBlt(tagRECT &,tagRECT &,IMFSample *,IMFSample *,int,int,DXGI_FORMAT,DXGI_FORMAT)
0x18000cfab  mov     r13d, eax
0x18000cfae  test    eax, eax
0x18000cfb0  js      loc_18000D0ED
0x18000cfb6  cmp     rbx, r12
0x18000cfb9  jz      short loc_18000CFE7
0x18000cfbb  test    r12, r12
0x18000cfbe  jz      short loc_18000CFD0
0x18000cfc0  mov     rax, [r12]
0x18000cfc4  mov     rcx, r12
0x18000cfc7  mov     rax, [rax+8]
0x18000cfcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfd0  mov     rcx, rbx
0x18000cfd3  mov     rbx, r12
0x18000cfd6  test    rcx, rcx
0x18000cfd9  jz      short loc_18000CFE7
0x18000cfdb  mov     rax, [rcx]
0x18000cfde  mov     rax, [rax+10h]
0x18000cfe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfe7  mov     [rsp+2C0h+var_26C], edi
0x18000cfeb  mov     rax, [r15+10h]
0x18000cfef  cmp     dword ptr [rax+3E0h], 0
0x18000cff6  lea     rcx, [rax+37Ch]
0x18000cffd  jnz     loc_18000D1A4
0x18000d003  cmp     dword ptr [rcx], 0
0x18000d006  jnz     loc_18000D1A4
0x18000d00c  mov     rax, [r15+10h]
0x18000d010  cmp     qword ptr [rax+5D0h], 0
0x18000d018  jz      loc_18000D114
0x18000d01e  cmp     dword ptr [rax+838h], 1
0x18000d025  jnz     loc_18000D114
0x18000d02b  mov     rdi, [rbp+1C0h+var_218]
  ... truncated ...
```
