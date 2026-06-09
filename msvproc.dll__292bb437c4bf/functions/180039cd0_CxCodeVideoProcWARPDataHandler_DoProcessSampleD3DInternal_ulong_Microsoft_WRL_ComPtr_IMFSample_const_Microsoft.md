# CxCodeVideoProcWARPDataHandler::DoProcessSampleD3DInternal(ulong,Microsoft::WRL::ComPtr<IMFSample> const &,Microsoft::WRL::ComPtr<IMFSample> const &,D3D11_VIDEO_FRAME_FORMAT,int)

- ea: `0x180039cd0`
- end: `0x18003ac1b`
- name: `?DoProcessSampleD3DInternal@CxCodeVideoProcWARPDataHandler@@UEAAJKAEBV?$ComPtr@UIMFSample@@@WRL@Microsoft@@0W4D3D11_VIDEO_FRAME_FORMAT@@H@Z`
- size: `3915`
- prototype: ``
- caller_count: `0`
- callee_count: `28`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180009470`
- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000cb40`
- `0x18000ec20`
- `0x18000ecf0`
- `0x1800158d0`
- `0x18001ba94`
- `0x18001bdb0`
- `0x18001e060`
- `0x18003639c`
- `0x180039cd0`
- `0x18003ac24`
- `0x180054140`
- `0x180054ee4`
- `0x180059bac`
- `0x180063110`
- `0x1800705d0`
- `0x18009faf0`
- `0x18009fb94`
- `0x18009fbf0`
- `0x18009fc2c`
- `0x1800a0070`
- `0x1800a0098`
- `0x1800bd094`
- `0x1800bd59c`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFCopyImage` at `0x18003a1c6`
- `MFPlat!MFCopyImage` at `0x18003a75c`
- `MFPlat!MFCopyImage` at `0x18003a1c6`
- `MFPlat!MFCopyImage` at `0x18003a75c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039db3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039e92`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039f97`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a086`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a1f9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a2a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a33a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a3c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a500`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a5bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a77c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a949`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a9f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003aa86`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ab1a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039db3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039e92`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039f97`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a086`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a1f9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a2a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a33a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a3c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a500`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a5bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a77c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a949`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a9f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003aa86`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ab1a`

## string_xrefs

- `0x18003a27c`: `Invalid stride on input copy`
- `0x18003a91e`: `Invalid stride on input copy`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcWARPDataHandler::DoProcessSampleD3DInternal(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        int a5,
        int a6)
{
  _DWORD *v8; // rax
  int v9; // r15d
  __int64 v10; // rcx
  int v11; // ebx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  unsigned int v16; // edx
  struct IMFSample *InputSample; // rdi
  HRESULT (__stdcall *GetBufferByIndex)(IMFSample *, DWORD, IMFMediaBuffer **); // rbx
  unsigned int v19; // edx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  struct IMFSample *v23; // rdi
  HRESULT (__stdcall *v24)(IMFSample *, DWORD, IMFMediaBuffer **); // rbx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, _QWORD, __int64 *); // rbx
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdi
  void (__fastcall *v31)(__int64, __int64, _BYTE *); // rbx
  unsigned int v32; // edx
  __int64 v33; // r8
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  DWORD dwWidthInBytes; // edi
  struct IMFMediaType *v38; // rax
  struct IMFMediaBuffer *v39; // r9
  unsigned int v40; // r8d
  unsigned int v41; // ecx
  __int64 *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  __int64 v45; // rdx
  __int64 *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  __int64 v49; // rdx
  __int64 *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  __int64 *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct IMFSample *v56; // rax
  __int64 *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  unsigned int v60; // edx
  __int64 v61; // r8
  __int64 *v62; // rcx
  CallStackTracing *v63; // rax
  struct CallStackContext *v64; // rax
  int v65; // r15d
  DWORD v66; // edi
  __int64 v67; // rax
  int v68; // r13d
  CMFTMultiStreamTypeHandler *v69; // rcx
  struct IMFMediaType *v70; // rax
  struct IMFMediaBuffer *v71; // r9
  unsigned int v72; // r8d
  _DWORD *v73; // rax
  unsigned int v74; // eax
  DWORD dwLines; // eax
  __int64 *v76; // rcx
  CallStackTracing *v77; // rax
  unsigned int v78; // eax
  __int64 v79; // rcx
  __int64 v80; // rbx
  __int128 v81; // xmm0
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
  __int64 *v92; // rcx
  CallStackTracing *v93; // rax
  struct CallStackContext *v94; // rax
  _BYTE v96[4]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v97; // [rsp+34h] [rbp-CCh] BYREF
  int v98; // [rsp+38h] [rbp-C8h]
  __int64 v99; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v100[8]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v101; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v102[8]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v103[24]; // [rsp+60h] [rbp-A0h] BYREF
  BYTE *pDest; // [rsp+78h] [rbp-88h]
  LONG lDestStride; // [rsp+80h] [rbp-80h]
  _BYTE v106[56]; // [rsp+B0h] [rbp-50h] BYREF
  BYTE *pSrc; // [rsp+E8h] [rbp-18h]
  LONG lSrcStride[6]; // [rsp+F8h] [rbp-8h]
  _BYTE v109[4]; // [rsp+110h] [rbp+10h] BYREF
  int v110; // [rsp+114h] [rbp+14h]
  unsigned int v111; // [rsp+124h] [rbp+24h]
  unsigned int v112; // [rsp+128h] [rbp+28h]
  unsigned int v113; // [rsp+12Ch] [rbp+2Ch]
  unsigned int v114; // [rsp+130h] [rbp+30h]
  __int64 (__fastcall *v115)(__int64, BYTE **); // [rsp+158h] [rbp+58h]
  struct tagRECT v116; // [rsp+160h] [rbp+60h] BYREF
  struct tagRECT v117; // [rsp+170h] [rbp+70h] BYREF
  BYTE *v118; // [rsp+180h] [rbp+80h] BYREF
  LONG v119; // [rsp+188h] [rbp+88h]
  int v120; // [rsp+18Ch] [rbp+8Ch]
  BYTE *v121; // [rsp+190h] [rbp+90h]
  LONG v122; // [rsp+198h] [rbp+98h]
  unsigned int v123; // [rsp+19Ch] [rbp+9Ch]
  __int128 v124; // [rsp+1A0h] [rbp+A0h]
  __int128 v125; // [rsp+1B0h] [rbp+B0h]
  LONG v126; // [rsp+1D0h] [rbp+D0h]
  int v127; // [rsp+1D4h] [rbp+D4h]
  int v128; // [rsp+1D8h] [rbp+D8h]
  int v129; // [rsp+1E0h] [rbp+E0h]
  __int128 v130; // [rsp+1E4h] [rbp+E4h]

  `vector constructor iterator'(&v101, 8u, 2u, Microsoft::WRL::ComPtr<ID3D11ComputeShader>::ComPtr<ID3D11ComputeShader>);
  `vector constructor iterator'(&v99, 8u, 2u, Microsoft::WRL::ComPtr<ID3D11ComputeShader>::ComPtr<ID3D11ComputeShader>);
  v117 = 0;
  v116 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v96,
    "CxCodeVideoProcWARPDataHandler::DoProcessSampleD3DInternal",
    103);
  v8 = *(_DWORD **)(a1 + 16);
  v9 = 0;
  if ( v8[91] && *v8 )
  {
    v10 = *a3;
    v97 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v10 + 312LL))(v10, &v97);
    if ( v11 >= 0 )
    {
      CxCodeVideoProcMFTDataHandler::GetSourceRects(*(CxCodeVideoProcMFTDataHandler **)(a1 + 32), v97, &v117, &v116);
      InputSample = CxCodeVideoProcMFTDataHandler::GetInputSample(*(CxCodeVideoProcMFTDataHandler **)(a1 + 32), v16);
      GetBufferByIndex = InputSample->lpVtbl->GetBufferByIndex;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v101);
      v11 = ((__int64 (__fastcall *)(struct IMFSample *, _QWORD, __int64 *))GetBufferByIndex)(InputSample, 0, &v101);
      if ( v11 >= 0 )
      {
        if ( *(_DWORD *)(*(_QWORD *)(a1 + 16) + 356LL) == 1 )
        {
          v23 = CxCodeVideoProcMFTDataHandler::GetInputSample(*(CxCodeVideoProcMFTDataHandler **)(a1 + 32), v19);
          v24 = v23->lpVtbl->GetBufferByIndex;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v102);
          ((void (__fastcall *)(struct IMFSample *, __int64, _BYTE *))v24)(v23, 1, v102);
        }
        v25 = *a3;
        v26 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)*a3 + 320LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v99);
        v11 = v26(v25, 0, &v99);
        if ( v11 >= 0 )
        {
          if ( *(_DWORD *)(*(_QWORD *)(a1 + 16) + 744LL) == 1 )
          {
            v30 = *a3;
            v31 = *(void (__fastcall **)(__int64, __int64, _BYTE *))(*(_QWORD *)*a3 + 320LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v100);
            v31(v30, 1, v100);
          }
          memset_0(v109, 0, 0x50u);
          v11 = CtypeSurfaces::Find(*(_DWORD *)(*(_QWORD *)(a1 + 16) + 4LL), (struct TypeSurface *)v109);
          if ( v11 >= 0 )
          {
            dwWidthInBytes = (unsigned int)(*(_DWORD *)(v33 + 52) * v110) >> 3;
            while ( v9 < 2 && *(_QWORD *)&v102[8 * v9 - 8] )
            {
              v38 = CxCodeVideoProcMFTDataHandler::PInputType(*(CxCodeVideoProcMFTDataHandler **)(a1 + 32), v32);
              VideoBufferLock::VideoBufferLock((VideoBufferLock *)v106, v39, v38);
              TextureLock::TextureLock((TextureLock *)v103, *(struct ID3D11Texture2D **)(a1 + 8LL * v9 + 1176), v40);
              v11 = VideoBufferLock::lock((VideoBufferLock *)v106, MF2DBuffer_LockFlags_Read);
              if ( v11 < 0 )
              {
                v53 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                  CallStackTracing::s_wpInstance = v54;
                  if ( v54
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
                  {
                    v53 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v53 = &qword_180153440;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
                  }
                }
                if ( *((_BYTE *)v53 + 8) )
                {
                  ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v53);
                  if ( *((_DWORD *)ThreadRelativeContext + 499) != v11 )
                    CallStackContext::TraceFailure(
                      ThreadRelativeContext,
                      "CxCodeVideoProcWARPDataHandler::DoProcessSampleD3DInternal",
                      139,
                      v11);
                }
                if ( !g_wppLevels )
                  goto LABEL_104;
                v45 = 26;
LABEL_103:
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v45,
                  WPP_2ecf8b1eac483ccb03f9c6d0bdefe8d2_Traceguids,
                  a1,
                  v11);
                goto LABEL_104;
              }
              v11 = TextureLock::lock((TextureLock *)v103, D3D11_MAP_WRITE_DISCARD, D3D11_CPU_ACCESS_WRITE);
              if ( v11 < 0 )
              {
                v50 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                  CallStackTracing::s_wpInstance = v51;
                  if ( v51
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
                  {
                    v50 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v50 = &qword_180153440;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
                  }
                }
                if ( *((_BYTE *)v50 + 8) )
                {
                  v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
                  if ( *((_DWORD *)v52 + 499) != v11 )
                    CallStackContext::TraceFailure(
                      v52,
                      "CxCodeVideoProcWARPDataHandler::DoProcessSampleD3DInternal",
                      140,
                      v11);
                }
                if ( !g_wppLevels )
                  goto LABEL_104;
                v45 = 27;
                goto LABEL_103;
              }
              if ( lDestStride < dwWidthInBytes )
                goto LABEL_72;
              v41 = -lSrcStride[0];
              if ( lSrcStride[0] > 0 )
                v41 = lSrcStride[0];
              if ( v41 < dwWidthInBytes )
              {
LABEL_72:
                XvpOriginateError<29>(
                  "CxCodeVideoProcWARPDataHandler::DoProcessSampleD3DInternal",
                  2147500033LL,
                  L"Invalid stride on input copy");
                v46 = (__int64 *)CallStackTracing::s_wpInstance;
                v11 = -2147467259;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                  CallStackTracing::s_wpInstance = v47;
                  if ( v47
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
                  {
                    v46 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v46 = &qword_180153440;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
                  }
                }
                if ( *((_BYTE *)v46 + 8) )
                {
                  v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
                  if ( *((_DWORD *)v48 + 499) != -2147467259 )
                    CallStackContext::TraceFailure(
                      v48,
                      "CxCodeVideoProcWARPDataHandler::DoProcessSampleD3DInternal",
                      145,
                      -2147467259);
                }
                if ( g_wppLevels )
                {
                  v49 = 28;
LABEL_82:
                  WPP_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v49,
                    WPP_2ecf8b1eac483ccb03f9c6d0bdefe8d2_Traceguids,
                    a1,
                    -2147467259);
                }
                goto LABEL_104;
              }
              v11 = MFCopyImage(pDest, lDestStride, pSrc, lSrcStride[0], dwWidthInBytes, lSrcStride[1] / v41);
              if ( v11 < 0 )
              {
                v42 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                  CallStackTracing::s_wpInstance = v43;
                  if ( v43
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
                  {
                    v42 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v42 = &qword_180153440;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
                  }
                }
                if ( *((_BYTE *)v42 + 8) )
                {
                  v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
                  if ( *((_DWORD *)v44 + 499) != v11 )
                    CallStackContext::TraceFailure(
                      v44,
                      "CxCodeVideoProcWARPDataHandler::DoProcessSampleD3DInternal",
                      147,
                      v11);
                }
                if ( g_wppLevels )
                {
                  v45 = 29;
                  goto LABEL_103;
                }
LABEL_104:
                TextureLock::~TextureLock((TextureLock *)v103);
                VideoBufferLock::~VideoBufferLock((VideoBufferLock *)v106);
                goto LABEL_202;
              }
              TextureLock::~TextureLock((TextureLock *)v103);
              VideoBufferLock::~VideoBufferLock((VideoBufferLock *)v106);
              ++v9;
            }
            v56 = CxCodeVideoProcMFTDataHandler::GetInputSample(*(CxCodeVideoProcMFTDataHandler **)(a1 + 32), v32);
            ((void (__fastcall *)(struct IMFSample *, _QWORD))v56->lpVtbl->CopyAllItems)(v56, *(_QWORD *)(a1 + 1192));
            (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a3 + 256LL))(*a3, *(_QWORD *)(a1 + 1216));
            v11 = CxCodeVideoProcD3D11DataHandler::DoProcessSampleD3DInternal(
                    (CxCodeVideoProcD3D11DataHandler *)(a1 + 1232),
                    a5,
                    a6);
            if ( v11 >= 0 )
            {
              memset_0(v109, 0, 0x50u);
              v11 = CtypeSurfaces::Find(*(_DWORD *)(*(_QWORD *)(a1 + 16) + 368LL), (struct TypeSurface *)v109);
              if ( v11 >= 0 )
              {
                v65 = 0;
                v66 = (unsigned int)(*(_DWORD *)(v61 + 404) * v110) >> 3;
                while ( v65 < 2 && *(_QWORD *)&v100[8 * v65 - 8] )
                {
                  v67 = *(_QWORD *)(a1 + 16);
                  v68 = *(_DWORD *)(v67 + 404);
                  v69 = *(CMFTMultiStreamTypeHandler **)(*(_QWORD *)(a1 + 32) + 8LL);
                  v98 = *(_DWORD *)(v67 + 400);
                  v70 = CMFTMultiStreamTypeHandler::POutputType(v69, v60);
                  VideoBufferLock::VideoBufferLock((VideoBufferLock *)v106, v71, v70);
                  TextureLock::TextureLock(
                    (TextureLock *)v103,
                    *(struct ID3D11Texture2D **)(a1 + 8LL * v65 + 1200),
                    v72);
                  v11 = VideoBufferLock::lock((VideoBufferLock *)v106, MF2DBuffer_LockFlags_Write);
                  if ( v11 < 0 )
                  {
                    v89 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v90 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                      CallStackTracing::s_wpInstance = v90;
                      if ( v90
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v90 + 8LL))(
                             v90,
                             2032) )
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
                      if ( *((_DWORD *)v91 + 499) != v11 )
                        CallStackContext::TraceFailure(
                          v91,
                          "CxCodeVideoProcWARPDataHandler::DoProcessSampleD3DInternal",
                          164,
                          v11);
                    }
                    if ( g_wppLevels )
                    {
                      v45 = 32;
                      goto LABEL_103;
                    }
                    goto LABEL_104;
                  }
                  v11 = TextureLock::lock((TextureLock *)v103, D3D11_MAP_READ, D3D11_CPU_ACCESS_READ);
                  if ( v11 < 0 )
                  {
                    v86 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v87 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                      CallStackTracing::s_wpInstance = v87;
                      if ( v87
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v87 + 8LL))(
                             v87,
                             2032) )
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
                      if ( *((_DWORD *)v88 + 499) != v11 )
                        CallStackContext::TraceFailure(
                          v88,
                          "CxCodeVideoProcWARPDataHandler::DoProcessSampleD3DInternal",
                          165,
                          v11);
                    }
                    if ( g_wppLevels )
                    {
                      v45 = 33;
                      goto LABEL_103;
                    }
                    goto LABEL_104;
                  }
                  v73 = *(_DWORD **)(a1 + 16);
                  if ( v73[102] || v73[103] || v68 != v73[104] || v98 != v73[105] )
                  {
                    v118 = pSrc;
                    v119 = lSrcStride[0];
                    v121 = pDest;
                    v122 = lDestStride;
                    v124 = 0;
                    v125 = 0;
                    v78 = TextureLock::lines((TextureLock *)v103);
                    v79 = *(_QWORD *)(a1 + 16);
                    v123 = v78;
                    v126 = lDestStride;
                    v120 = *(_DWORD *)(v79 + 400);
                    if ( v113 )
                      v127 = v111 / v113;
                    else
                      v127 = 0;
                    if ( v114 )
                      v128 = v112 / v114;
                    else
                      v128 = 0;
                    v80 = v79 + 408;
                    v81 = *(_OWORD *)(v79 + 408);
                    v129 = v110;
                    v130 = v81;
                    ParameterBase::InitSafeBuffers(
                      (ParameterBase *)&v118,
                      *(_DWORD *)(v79 + 368),
                      *(_DWORD *)(v79 + 368));
                    if ( !v115 )
                    {
                      v11 = XvpOriginateError<27>(
                              "CxCodeVideoProcWARPDataHandler::DoProcessSampleD3DInternal",
                              2147500033LL,
                              L"No copier found for format");
                      goto LABEL_104;
                    }
                    v11 = v115(v80, &v118);
                    if ( v11 )
                      goto LABEL_104;
                  }
                  else
                  {
                    if ( lDestStride < v66 )
                      goto LABEL_160;
                    v74 = -lSrcStride[0];
                    if ( lSrcStride[0] > 0 )
                      v74 = lSrcStride[0];
                    if ( v74 < v66 )
                    {
LABEL_160:
                      XvpOriginateError<29>(
                        "CxCodeVideoProcWARPDataHandler::DoProcessSampleD3DInternal",
                        2147500033LL,
                        L"Invalid stride on input copy");
                      v83 = (__int64 *)CallStackTracing::s_wpInstance;
                      v11 = -2147467259;
                      if ( !CallStackTracing::s_wpInstance )
                      {
                        v84 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                        CallStackTracing::s_wpInstance = v84;
                        if ( v84
                          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v84 + 8LL))(
                               v84,
                               2032) )
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
                        if ( *((_DWORD *)v85 + 499) != -2147467259 )
                          CallStackContext::TraceFailure(
                            v85,
                            "CxCodeVideoProcWARPDataHandler::DoProcessSampleD3DInternal",
                            197,
                            -2147467259);
                      }
                      if ( g_wppLevels )
                      {
                        v49 = 34;
                        goto LABEL_82;
                      }
                      goto LABEL_104;
                    }
                    dwLines = TextureLock::lines((TextureLock *)v103);
                    v11 = MFCopyImage(pSrc, lSrcStride[0], pDest, lDestStride, v66, dwLines);
                    if ( v11 < 0 )
                    {
                      v76 = (__int64 *)CallStackTracing::s_wpInstance;
                      if ( !CallStackTracing::s_wpInstance )
                      {
                        v77 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                        CallStackTracing::s_wpInstance = v77;
                        if ( v77
                          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v77 + 8LL))(
                               v77,
                               2032) )
                        {
                          v76 = (__int64 *)CallStackTracing::s_wpInstance;
                        }
                        else
                        {
                          v76 = &qword_180153440;
                          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
                        }
                      }
                      if ( *((_BYTE *)v76 + 8) )
                      {
                        v82 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v76);
                        if ( *((_DWORD *)v82 + 499) != v11 )
                          CallStackContext::TraceFailure(
                            v82,
                            "CxCodeVideoProcWARPDataHandler::DoProcessSampleD3DInternal",
                            199,
                            v11);
                      }
                      if ( g_wppLevels )
                      {
                        v45 = 35;
                        goto LABEL_103;
                      }
                      goto LABEL_104;
                    }
                  }
                  TextureLock::~TextureLock((TextureLock *)v103);
                  VideoBufferLock::~VideoBufferLock((VideoBufferLock *)v106);
                  ++v65;
                }
              }
              else
              {
                v62 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v63 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                  CallStackTracing::s_wpInstance = v63;
                  if ( v63
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v63 + 8LL))(v63, 2032) )
                  {
                    v62 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v62 = &qword_180153440;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
                  }
                }
                if ( *((_BYTE *)v62 + 8) )
                {
                  v64 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v62);
                  if ( *((_DWORD *)v64 + 499) != v11 )
                    CallStackContext::TraceFailure(
                      v64,
                      "CxCodeVideoProcWARPDataHandler::DoProcessSampleD3DInternal",
                      155,
                      v11);
                }
                if ( g_wppLevels )
                {
                  v15 = 31;
                  goto LABEL_201;
                }
              }
            }
            else
            {
              v57 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                CallStackTracing::s_wpInstance = v58;
                if ( v58
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v58 + 8LL))(v58, 2032) )
                {
                  v57 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v57 = &qword_180153440;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
                }
              }
              if ( *((_BYTE *)v57 + 8) )
              {
                v59 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v57);
                if ( *((_DWORD *)v59 + 499) != v11 )
                  CallStackContext::TraceFailure(
                    v59,
                    "CxCodeVideoProcWARPDataHandler::DoProcessSampleD3DInternal",
                    152,
                    v11);
              }
              if ( g_wppLevels )
              {
                v15 = 30;
                goto LABEL_201;
              }
            }
          }
          else
          {
            v34 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v35;
              if ( v35
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
              {
                v34 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v34 = &qword_180153440;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
              }
            }
            if ( *((_BYTE *)v34 + 8) )
            {
              v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
              if ( *((_DWORD *)v36 + 499) != v11 )
                CallStackContext::TraceFailure(
                  v36,
                  "CxCodeVideoProcWARPDataHandler::DoProcessSampleD3DInternal",
                  131,
                  v11);
            }
            if ( g_wppLevels )
            {
              v15 = 25;
              goto LABEL_201;
            }
          }
        }
        else
        {
          v27 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v28;
            if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
            {
              v27 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v27 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v27 + 8) )
          {
            v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
            if ( *((_DWORD *)v29 + 499) != v11 )
              CallStackContext::TraceFailure(
                v29,
                "CxCodeVideoProcWARPDataHandler::DoProcessSampleD3DInternal",
                124,
                v11);
          }
          if ( g_wppLevels )
          {
            v15 = 24;
            goto LABEL_201;
          }
        }
      }
      else
      {
        v20 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v21;
          if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
          {
            v20 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v20 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v20 + 8) )
        {
          v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
          if ( *((_DWORD *)v22 + 499) != v11 )
            CallStackContext::TraceFailure(v22, "CxCodeVideoProcWARPDataHandler::DoProcessSampleD3DInternal", 118, v11);
        }
        if ( g_wppLevels )
        {
          v15 = 23;
          goto LABEL_201;
        }
      }
    }
    else
    {
      v12 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v13;
        if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
        {
          v12 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
        if ( *((_DWORD *)v14 + 499) != v11 )
          CallStackContext::TraceFailure(v14, "CxCodeVideoProcWARPDataHandler::DoProcessSampleD3DInternal", 112, v11);
      }
      if ( g_wppLevels )
      {
        v15 = 22;
LABEL_201:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, WPP_2ecf8b1eac483ccb03f9c6d0bdefe8d2_Traceguids, a1, v11);
      }
    }
  }
  else
  {
    v92 = (__int64 *)CallStackTracing::s_wpInstance;
    v11 = -1072861856;
    if ( !CallStackTracing::s_wpInstance )
    {
      v93 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v93;
      if ( v93 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v93 + 8LL))(v93, 2032) )
      {
        v92 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v92 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v92 + 8) )
    {
      v94 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v92);
      if ( *((_DWORD *)v94 + 499) != -1072861856 )
        CallStackContext::TraceFailure(
          v94,
          "CxCodeVideoProcWARPDataHandler::DoProcessSampleD3DInternal",
          107,
          -1072861856);
    }
    if ( g_wppLevels )
    {
      v15 = 21;
      goto LABEL_201;
    }
  }
LABEL_202:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v96);
  `vector destructor iterator'(&v99, 8u, 2u, Microsoft::WRL::ComPtr<ID3D11ComputeShader>::~ComPtr<ID3D11ComputeShader>);
  `vector destructor iterator'(&v101, 8u, 2u, Microsoft::WRL::ComPtr<ID3D11ComputeShader>::~ComPtr<ID3D11ComputeShader>);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180039cd0  mov     [rsp-8+arg_18], rbx
0x180039cd5  push    rbp
0x180039cd6  push    rsi
0x180039cd7  push    rdi
0x180039cd8  push    r12
0x180039cda  push    r13
0x180039cdc  push    r14
0x180039cde  push    r15
0x180039ce0  lea     rbp, [rsp-110h]
0x180039ce8  sub     rsp, 210h
0x180039cef  mov     rax, cs:__security_cookie
0x180039cf6  xor     rax, rsp
0x180039cf9  mov     [rbp+140h+var_40], rax
0x180039d00  mov     ebx, 2
0x180039d05  lea     r9, ??0?$ComPtr@UID3D11ComputeShader@@@WRL@Microsoft@@QEAA@XZ; void *(*)(void *)
0x180039d0c  mov     r12, r8
0x180039d0f  mov     r13d, edx
0x180039d12  mov     r14, rcx
0x180039d15  mov     r8d, ebx; unsigned __int64
0x180039d18  lea     rcx, [rsp+240h+var_1F0]; void *
0x180039d1d  lea     edi, [rbx+6]
0x180039d20  mov     edx, edi; unsigned __int64
0x180039d22  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z
0x180039d27  lea     r9, ??0?$ComPtr@UID3D11ComputeShader@@@WRL@Microsoft@@QEAA@XZ; void *(*)(void *)
0x180039d2e  mov     r8d, ebx; unsigned __int64
0x180039d31  mov     edx, edi; unsigned __int64
0x180039d33  lea     rcx, [rsp+240h+var_200]; void *
0x180039d38  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z
0x180039d3d  xorps   xmm0, xmm0
0x180039d40  lea     rsi, aCxcodevideopro_109
0x180039d47  xorps   xmm1, xmm1
0x180039d4a  lea     r8d, [rbx+65h]; int
0x180039d4e  mov     rdx, rsi; char *
0x180039d51  lea     rcx, [rsp+240h+var_210]; this
0x180039d56  movups  xmmword ptr [rbp+140h+var_D0.left], xmm0
0x180039d5a  movups  xmmword ptr [rbp+140h+var_E0.left], xmm1
0x180039d5e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z
0x180039d63  mov     rax, [r14+10h]
0x180039d67  xor     r15d, r15d
0x180039d6a  cmp     [rax+16Ch], r15d
0x180039d71  jz      loc_18003AB09
0x180039d77  cmp     [rax], r15d
0x180039d7a  jz      loc_18003AB09
0x180039d80  mov     rcx, [r12]
0x180039d84  lea     rdx, [rsp+240h+var_20C]
0x180039d89  mov     [rsp+240h+var_20C], r15d
0x180039d8e  mov     rax, [rcx]
0x180039d91  mov     rax, [rax+138h]
0x180039d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039d9d  mov     ebx, eax
0x180039d9f  test    eax, eax
0x180039da1  jns     loc_180039E35
0x180039da7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x180039dae  test    rcx, rcx
0x180039db1  jnz     short loc_180039DF4
0x180039db3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180039db9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax
0x180039dc0  mov     rcx, rax
0x180039dc3  test    rax, rax
0x180039dc6  jz      short loc_180039DE6
0x180039dc8  mov     rax, [rax]
0x180039dcb  mov     edx, 7F0h
0x180039dd0  mov     rax, [rax+8]
0x180039dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039dd9  test    eax, eax
0x180039ddb  jz      short loc_180039DE6
0x180039ddd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x180039de4  jmp     short loc_180039DF4
0x180039de6  lea     rcx, qword_180153440; this
0x180039ded  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx
0x180039df4  cmp     [rcx+8], r15b
0x180039df8  jz      short loc_180039E1B
0x180039dfa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ
0x180039dff  cmp     [rax+7CCh], ebx
0x180039e05  jz      short loc_180039E1B
0x180039e07  mov     r9d, ebx; int
0x180039e0a  mov     r8d, 70h ; 'p'; int
0x180039e10  mov     rdx, rsi; char *
0x180039e13  mov     rcx, rax; this
0x180039e16  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z
0x180039e1b  mov     esi, 1
0x180039e20  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil
0x180039e27  jb      loc_18003ABB1
0x180039e2d  lea     edx, [rsi+15h]
0x180039e30  jmp     loc_18003AB93
0x180039e35  mov     edx, [rsp+240h+var_20C]; unsigned int
0x180039e39  lea     r9, [rbp+140h+var_E0]; struct tagRECT *
0x180039e3d  mov     rcx, [r14+20h]; this
0x180039e41  lea     r8, [rbp+140h+var_D0]; struct tagRECT *
0x180039e45  call    ?GetSourceRects@CxCodeVideoProcMFTDataHandler@@QEAAXKPEAUtagRECT@@0@Z
0x180039e4a  mov     rcx, [r14+20h]; this
0x180039e4e  call    ?GetInputSample@CxCodeVideoProcMFTDataHandler@@QEAAPEAUIMFSample@@K@Z
0x180039e53  mov     rdi, rax
0x180039e56  mov     rcx, [rax]
0x180039e59  mov     rbx, [rcx+140h]
0x180039e60  lea     rcx, [rsp+240h+var_1F0]
0x180039e65  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ
0x180039e6a  lea     r8, [rsp+240h+var_1F0]
0x180039e6f  xor     edx, edx
0x180039e71  mov     rcx, rdi
0x180039e74  mov     rax, rbx
0x180039e77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e7c  mov     ebx, eax
0x180039e7e  test    eax, eax
0x180039e80  jns     loc_180039F14
0x180039e86  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x180039e8d  test    rcx, rcx
0x180039e90  jnz     short loc_180039ED3
0x180039e92  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180039e98  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax
0x180039e9f  mov     rcx, rax
0x180039ea2  test    rax, rax
0x180039ea5  jz      short loc_180039EC5
0x180039ea7  mov     rax, [rax]
0x180039eaa  mov     edx, 7F0h
0x180039eaf  mov     rax, [rax+8]
0x180039eb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039eb8  test    eax, eax
0x180039eba  jz      short loc_180039EC5
0x180039ebc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x180039ec3  jmp     short loc_180039ED3
0x180039ec5  lea     rcx, qword_180153440; this
0x180039ecc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx
0x180039ed3  cmp     [rcx+8], r15b
0x180039ed7  jz      short loc_180039EFA
0x180039ed9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ
0x180039ede  cmp     [rax+7CCh], ebx
0x180039ee4  jz      short loc_180039EFA
0x180039ee6  mov     r9d, ebx; int
0x180039ee9  mov     r8d, 76h ; 'v'; int
0x180039eef  mov     rdx, rsi; char *
0x180039ef2  mov     rcx, rax; this
0x180039ef5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z
0x180039efa  mov     esi, 1
0x180039eff  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil
0x180039f06  jb      loc_18003ABB1
0x180039f0c  lea     edx, [rsi+16h]
0x180039f0f  jmp     loc_18003AB93
0x180039f14  mov     rax, [r14+10h]
0x180039f18  mov     esi, 1
0x180039f1d  cmp     [rax+164h], esi
0x180039f23  jnz     short loc_180039F57
0x180039f25  mov     rcx, [r14+20h]; this
0x180039f29  call    ?GetInputSample@CxCodeVideoProcMFTDataHandler@@QEAAPEAUIMFSample@@K@Z
0x180039f2e  mov     rdi, rax
0x180039f31  mov     rcx, [rax]
0x180039f34  mov     rbx, [rcx+140h]
0x180039f3b  lea     rcx, [rsp+240h+var_1E8]
0x180039f40  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ
0x180039f45  lea     r8, [rsp+240h+var_1E8]
0x180039f4a  mov     edx, esi
0x180039f4c  mov     rcx, rdi
0x180039f4f  mov     rax, rbx
0x180039f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039f57  mov     rdi, [r12]
0x180039f5b  lea     rcx, [rsp+240h+var_200]
0x180039f60  mov     rax, [rdi]
0x180039f63  mov     rbx, [rax+140h]
0x180039f6a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ
0x180039f6f  lea     r8, [rsp+240h+var_200]
0x180039f74  xor     edx, edx
0x180039f76  mov     rcx, rdi
0x180039f79  mov     rax, rbx
0x180039f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039f81  mov     ebx, eax
0x180039f83  test    eax, eax
0x180039f85  jns     loc_18003A01A
0x180039f8b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x180039f92  test    rcx, rcx
0x180039f95  jnz     short loc_180039FD8
0x180039f97  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180039f9d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax
0x180039fa4  mov     rcx, rax
0x180039fa7  test    rax, rax
0x180039faa  jz      short loc_180039FCA
0x180039fac  mov     rax, [rax]
0x180039faf  mov     edx, 7F0h
0x180039fb4  mov     rax, [rax+8]
0x180039fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039fbd  test    eax, eax
0x180039fbf  jz      short loc_180039FCA
0x180039fc1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x180039fc8  jmp     short loc_180039FD8
0x180039fca  lea     rcx, qword_180153440; this
0x180039fd1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx
0x180039fd8  cmp     [rcx+8], r15b
0x180039fdc  jz      short loc_18003A003
0x180039fde  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ
0x180039fe3  cmp     [rax+7CCh], ebx
0x180039fe9  jz      short loc_18003A003
0x180039feb  mov     r9d, ebx; int
0x180039fee  lea     rdx, aCxcodevideopro_109
0x180039ff5  mov     r8d, 7Ch ; '|'; int
0x180039ffb  mov     rcx, rax; this
0x180039ffe  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z
0x18003a003  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil
0x18003a00a  jb      loc_18003ABB1
0x18003a010  mov     edx, 18h
0x18003a015  jmp     loc_18003AB93
0x18003a01a  mov     rax, [r14+10h]
0x18003a01e  cmp     [rax+2E8h], esi
0x18003a024  jnz     short loc_18003A050
0x18003a026  mov     rdi, [r12]
0x18003a02a  lea     rcx, [rsp+240h+var_1F8]
0x18003a02f  mov     rax, [rdi]
0x18003a032  mov     rbx, [rax+140h]
0x18003a039  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ
0x18003a03e  lea     r8, [rsp+240h+var_1F8]
0x18003a043  mov     edx, esi
0x18003a045  mov     rcx, rdi
0x18003a048  mov     rax, rbx
0x18003a04b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a050  xor     edx, edx; Val
0x18003a052  lea     rcx, [rbp+140h+var_130]; void *
0x18003a056  lea     r8d, [rdx+50h]; Size
0x18003a05a  call    memset_0
0x18003a05f  mov     r8, [r14+10h]
0x18003a063  lea     rdx, [rbp+140h+var_130]; struct TypeSurface *
0x18003a067  mov     ecx, [r8+4]; unsigned int
0x18003a06b  call    ?Find@CtypeSurfaces@@SAJKPEAUTypeSurface@@@Z
0x18003a070  mov     ebx, eax
0x18003a072  test    eax, eax
0x18003a074  jns     loc_18003A109
0x18003a07a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x18003a081  test    rcx, rcx
0x18003a084  jnz     short loc_18003A0C7
0x18003a086  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003a08c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax
0x18003a093  mov     rcx, rax
0x18003a096  test    rax, rax
0x18003a099  jz      short loc_18003A0B9
0x18003a09b  mov     rax, [rax]
0x18003a09e  mov     edx, 7F0h
0x18003a0a3  mov     rax, [rax+8]
0x18003a0a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a0ac  test    eax, eax
0x18003a0ae  jz      short loc_18003A0B9
0x18003a0b0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x18003a0b7  jmp     short loc_18003A0C7
0x18003a0b9  lea     rcx, qword_180153440; this
0x18003a0c0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx
0x18003a0c7  cmp     [rcx+8], r15b
0x18003a0cb  jz      short loc_18003A0F2
0x18003a0cd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ
0x18003a0d2  cmp     [rax+7CCh], ebx
0x18003a0d8  jz      short loc_18003A0F2
0x18003a0da  mov     r9d, ebx; int
0x18003a0dd  lea     rdx, aCxcodevideopro_109
0x18003a0e4  mov     r8d, 83h; int
0x18003a0ea  mov     rcx, rax; this
0x18003a0ed  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z
0x18003a0f2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil
0x18003a0f9  jb      loc_18003ABB1
0x18003a0ff  mov     edx, 19h
0x18003a104  jmp     loc_18003AB93
0x18003a109  mov     edi, [rbp+140h+var_12C]
0x18003a10c  imul    edi, [r8+34h]
0x18003a111  shr     edi, 3
0x18003a114  cmp     r15d, 2
0x18003a118  jge     loc_18003A479
0x18003a11e  movsxd  rbx, r15d
0x18003a121  mov     r9, [rsp+rbx*8+240h+var_1F0]
0x18003a126  test    r9, r9
0x18003a129  jz      loc_18003A479
0x18003a12f  mov     rcx, [r14+20h]; this
0x18003a133  call    ?PInputType@CxCodeVideoProcMFTDataHandler@@QEAAPEAUIMFMediaType@@K@Z
0x18003a138  mov     r8, rax; struct IMFMediaType *
0x18003a13b  lea     rcx, [rbp+140h+var_190]; this
0x18003a13f  mov     rdx, r9; struct IMFMediaBuffer *
0x18003a142  call    ??0VideoBufferLock@@QEAA@PEAUIMFMediaBuffer@@PEAUIMFMediaType@@@Z
0x18003a147  mov     rdx, [r14+rbx*8+498h]; struct ID3D11Texture2D *
0x18003a14f  lea     rcx, [rsp+240h+var_1E0]; this
0x18003a154  call    ??0TextureLock@@QEAA@PEAUID3D11Texture2D@@I@Z
0x18003a159  mov     edx, esi; enum _MF2DBuffer_LockFlags
0x18003a15b  lea     rcx, [rbp+140h+var_190]; this
0x18003a15f  call    ?lock@VideoBufferLock@@QEAAJW4_MF2DBuffer_LockFlags@@@Z
0x18003a164  mov     ebx, eax
0x18003a166  test    eax, eax
0x18003a168  js      loc_18003A3BD
0x18003a16e  mov     edx, 4; enum D3D11_MAP
0x18003a173  lea     rcx, [rsp+240h+var_1E0]; this
0x18003a178  mov     r8d, 10000h; enum D3D11_CPU_ACCESS_FLAG
0x18003a17e  call    ?lock@TextureLock@@QEAAJW4D3D11_MAP@@W4D3D11_CPU_ACCESS_FLAG@@@Z
0x18003a183  mov     ebx, eax
0x18003a185  test    eax, eax
0x18003a187  js      loc_18003A32E
0x18003a18d  cmp     [rbp+140h+lDestStride], edi
0x18003a190  jb      loc_18003A27C
0x18003a196  mov     r9, qword ptr [rbp+140h+lSrcStride]; lSrcStride
0x18003a19a  mov     ecx, r9d
0x18003a19d  neg     ecx
0x18003a19f  cmovs   ecx, r9d
0x18003a1a3  cmp     ecx, edi
0x18003a1a5  jb      loc_18003A27C
0x18003a1ab  mov     eax, [rbp+140h+lSrcStride+4]
0x18003a1ae  xor     edx, edx
0x18003a1b0  mov     r8, [rbp+140h+pSrc]; pSrc
0x18003a1b4  div     ecx
0x18003a1b6  mov     edx, [rbp+140h+lDestStride]; lDestStride
0x18003a1b9  mov     rcx, [rsp+240h+pDest]; pDest
  ... truncated ...
```
