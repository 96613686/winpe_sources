# CMFVideoThumbnail::ConvertYUVtoRGB32(IMFSample *,IMFMediaType *,IMFSample * *,IMFMediaType * *)

- ea: `0x180064fc8`
- end: `0x180065ebf`
- name: `?ConvertYUVtoRGB32@CMFVideoThumbnail@@AEAAJPEAUIMFSample@@PEAUIMFMediaType@@PEAPEAU2@PEAPEAU3@@Z`
- size: `3831`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFSample *, struct IMFMediaType *, struct IMFSample **, struct IMFMediaType **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180069c10`

## callees

- `0x1800023e0`
- `0x180005ab8`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180051c90`
- `0x180064fc8`
- `0x180069a78`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800650ea`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800650ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065106`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065228`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800652e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006539a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006544f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065512`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800655d0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065688`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065744`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065802`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800658b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006596c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065a1b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065aca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065b78`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065c29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065cef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065dae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065106`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065228`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800652e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006539a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006544f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065512`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800655d0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065688`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065744`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065802`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800658b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006596c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065a1b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065aca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065b78`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065c29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065cef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065dae`
- `MFPlat!MFCreateSample` at `0x180065b5c`
- `MFPlat!MFCreateSample` at `0x180065b5c`
- `MFPlat!MFCalculateImageSize` at `0x1800659ff`
- `MFPlat!MFCalculateImageSize` at `0x1800659ff`
- `MFPlat!MFCreateMemoryBuffer` at `0x180065aae`
- `MFPlat!MFCreateMemoryBuffer` at `0x180065aae`

## pseudocode

```c
__int64 __fastcall CMFVideoThumbnail::ConvertYUVtoRGB32(
        CMFVideoThumbnail *this,
        struct IMFSample *a2,
        struct IMFMediaType *a3,
        struct IMFSample **a4,
        struct IMFMediaType **a5)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v10; // ebx
  __int128 v11; // xmm0
  __int64 v12; // rdx
  HRESULT v13; // ebx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  LPVOID v20; // rbx
  int (__fastcall *v21)(LPVOID, GUID *, __int64 *); // rdi
  LPVOID v22; // rdi
  __int64 (__fastcall *v23)(LPVOID, __int64 *); // rbx
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  LPVOID v48; // rdi
  __int64 (__fastcall *v49)(LPVOID, GUID *, __int64 *); // rbx
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // r9
  __int64 *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  __int64 v56; // rdi
  __int64 (__fastcall *v57)(__int64, struct IMFMediaType **); // rbx
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 v60; // r9
  __int64 *v61; // rcx
  CallStackTracing *v62; // rax
  struct CallStackContext *v63; // rax
  __int64 v64; // rdx
  __int64 v65; // r8
  __int64 v66; // r9
  __int64 *v67; // rcx
  CallStackTracing *v68; // rax
  struct CallStackContext *v69; // rax
  __int64 v70; // rdx
  __int64 v71; // r8
  __int64 v72; // r9
  __int64 *v73; // rcx
  CallStackTracing *v74; // rax
  struct CallStackContext *v75; // rax
  __int64 v76; // rdx
  __int64 v77; // r8
  __int64 v78; // r9
  __int64 *v79; // rcx
  CallStackTracing *v80; // rax
  struct CallStackContext *v81; // rax
  __int64 v82; // rdx
  __int64 v83; // r8
  __int64 v84; // r9
  __int64 *v85; // rcx
  CallStackTracing *v86; // rax
  struct CallStackContext *v87; // rax
  __int64 v88; // rdx
  __int64 v89; // r8
  __int64 v90; // r9
  __int64 *v91; // rcx
  CallStackTracing *v92; // rax
  struct CallStackContext *v93; // rax
  __int64 v94; // rdx
  __int64 v95; // r8
  __int64 v96; // r9
  __int64 *v97; // rcx
  CallStackTracing *v98; // rax
  struct CallStackContext *v99; // rax
  __int64 v100; // rdx
  __int64 v101; // r8
  __int64 v102; // r9
  __int64 *v103; // rcx
  CallStackTracing *v104; // rax
  struct CallStackContext *v105; // rax
  __int64 v106; // rdx
  __int64 v107; // r8
  __int64 v108; // r9
  __int64 *v109; // rcx
  CallStackTracing *v110; // rax
  struct CallStackContext *v111; // rax
  __int64 v112; // rdx
  __int64 v113; // r8
  __int64 v114; // r9
  __int64 *v115; // rcx
  CallStackTracing *v116; // rax
  struct CallStackContext *v117; // rax
  __int64 v118; // rdx
  __int64 v119; // r8
  __int64 v120; // r9
  __int64 *v121; // rcx
  CallStackTracing *v122; // rax
  struct CallStackContext *v123; // rax
  __int64 v124; // rdx
  __int64 v125; // r8
  __int64 v126; // r9
  __int64 *v127; // rcx
  CallStackTracing *v128; // rax
  struct CallStackContext *v129; // rax
  _BYTE v131[8]; // [rsp+30h] [rbp-A1h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-99h] BYREF
  struct IMFMediaType *v133; // [rsp+40h] [rbp-91h] BYREF
  IMFSample *ppIMFSample; // [rsp+48h] [rbp-89h] BYREF
  UINT32 unHeight; // [rsp+50h] [rbp-81h] BYREF
  UINT32 unWidth; // [rsp+54h] [rbp-7Dh] BYREF
  UINT32 pcbImageSize; // [rsp+58h] [rbp-79h] BYREF
  __int64 v138; // [rsp+60h] [rbp-71h] BYREF
  __int64 v139; // [rsp+68h] [rbp-69h] BYREF
  __int64 v140; // [rsp+70h] [rbp-61h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+78h] [rbp-59h] BYREF
  int v142; // [rsp+80h] [rbp-51h] BYREF
  __int64 v143; // [rsp+88h] [rbp-49h] BYREF
  __int128 v144; // [rsp+90h] [rbp-41h] BYREF
  __int128 v145; // [rsp+A0h] [rbp-31h]
  GUID guidSubtype; // [rsp+B0h] [rbp-21h] BYREF
  _BYTE v147[16]; // [rsp+C0h] [rbp-11h] BYREF

  ppBuffer = 0;
  v144 = 0;
  v145 = 0;
  ppIMFSample = 0;
  v143 = 0;
  guidSubtype = MFVideoFormat_ARGB32;
  v133 = 0;
  pcbImageSize = 0;
  v142 = 0;
  ppv = 0;
  v140 = 0;
  v138 = 0;
  unWidth = 0;
  unHeight = 0;
  v139 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v131, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1574);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 50) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 296LL))(*((_QWORD *)this + 50));
    v11 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 50) + 280LL))(
                       *((_QWORD *)this + 50),
                       v147);
    *((_DWORD *)ThreadRelativeContext + 504) = v10;
    *((_OWORD *)ThreadRelativeContext + 125) = v11;
  }
  Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&ppv);
  v13 = CoCreateInstance(&CLSID_VideoProcessorMFT, 0, 1u, &GUID_bf94c121_5b05_4e6f_8000_ba598961414d, &ppv);
  if ( v13 >= 0 )
  {
    v20 = ppv;
    v21 = **(int (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv;
    Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&v139);
    if ( v21(v20, &GUID_0b5e1c7e_bd76_46bc_896c_b2edb40dd803, &v139) >= 0 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v139 + 32LL))(v139, *((_QWORD *)this + 50));
    v22 = ppv;
    v23 = *(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 64LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v138);
    v13 = v23(v22, &v138);
    if ( v13 >= 0 )
    {
      v13 = (*(__int64 (__fastcall **)(__int64, const IID *, __int64))(*(_QWORD *)v138 + 168LL))(
              v138,
              &MF_XVP_DISABLE_FRC,
              1);
      if ( v13 >= 0 )
      {
        v13 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v138 + 168LL))(
                v138,
                &GUID_2efd8eee_1150_4328_9cf5_66dce933fcf4,
                1);
        if ( v13 >= 0 )
        {
          v13 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct IMFMediaType *, _QWORD))(*(_QWORD *)ppv + 120LL))(
                  ppv,
                  0,
                  a3,
                  0);
          if ( v13 >= 0 )
          {
            v48 = ppv;
            v49 = **(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv;
            Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&v140);
            v13 = v49(v48, &GUID_44f18199_7981_4f93_abe8_287ff0cccd7a, &v140);
            if ( v13 >= 0 )
            {
              v56 = v140;
              v57 = *(__int64 (__fastcall **)(__int64, struct IMFMediaType **))(*(_QWORD *)v140 + 96LL);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
              v13 = v57(v56, &v133);
              if ( v13 >= 0 )
              {
                v13 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, GUID *))v133->lpVtbl->SetGUID)(
                        v133,
                        &MF_MT_SUBTYPE,
                        &guidSubtype);
                if ( v13 >= 0 )
                {
                  v13 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, __int64))v133->lpVtbl->SetUINT32)(
                          v133,
                          &MF_MT_DEFAULT_STRIDE,
                          1);
                  if ( v13 >= 0 )
                  {
                    v13 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, __int64))v133->lpVtbl->SetUINT64)(
                            v133,
                            &MF_MT_PIXEL_ASPECT_RATIO,
                            0x100000001LL);
                    if ( v13 >= 0 )
                    {
                      v13 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct IMFMediaType *, _QWORD))(*(_QWORD *)ppv + 128LL))(
                              ppv,
                              0,
                              v133,
                              0);
                      if ( v13 >= 0 )
                      {
                        v13 = MFGetAttribute2UINT32asUINT64(v133, &MF_MT_FRAME_SIZE, &unWidth, &unHeight);
                        if ( v13 >= 0 )
                        {
                          v13 = MFCalculateImageSize(&guidSubtype, unWidth, unHeight, &pcbImageSize);
                          if ( v13 >= 0 )
                          {
                            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppBuffer);
                            v13 = MFCreateMemoryBuffer(pcbImageSize, &ppBuffer);
                            if ( v13 >= 0 )
                            {
                              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppIMFSample);
                              v13 = MFCreateSample(&ppIMFSample);
                              if ( v13 >= 0 )
                              {
                                v13 = ((__int64 (__fastcall *)(IMFSample *, IMFMediaBuffer *))ppIMFSample->lpVtbl->AddBuffer)(
                                        ppIMFSample,
                                        ppBuffer);
                                if ( v13 >= 0 )
                                {
                                  *((_QWORD *)&v144 + 1) = ppIMFSample;
                                  LODWORD(v145) = 0;
                                  LODWORD(v144) = 0;
                                  v13 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct IMFSample *, _QWORD))(*(_QWORD *)ppv + 192LL))(
                                          ppv,
                                          0,
                                          a2,
                                          0);
                                  if ( v13 >= 0 )
                                  {
                                    v13 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, __int128 *, int *))(*(_QWORD *)ppv + 200LL))(
                                            ppv,
                                            0,
                                            1,
                                            &v144,
                                            &v142);
                                    if ( v13 >= 0 )
                                    {
                                      *a4 = ppIMFSample;
                                      *a5 = v133;
                                      ppIMFSample = 0;
                                      v133 = 0;
                                      goto LABEL_206;
                                    }
                                    v127 = (__int64 *)CallStackTracing::s_wpInstance;
                                    if ( !CallStackTracing::s_wpInstance )
                                    {
                                      v128 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v124, v125, v126);
                                      CallStackTracing::s_wpInstance = v128;
                                      if ( v128
                                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v128 + 8LL))(
                                             v128,
                                             2032) )
                                      {
                                        v127 = (__int64 *)CallStackTracing::s_wpInstance;
                                      }
                                      else
                                      {
                                        v127 = &qword_1800D6F70;
                                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                                      }
                                    }
                                    if ( *((_BYTE *)v127 + 8) )
                                    {
                                      v129 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v127);
                                      if ( *((_DWORD *)v129 + 499) != v13 )
                                        CallStackContext::TraceFailure(
                                          v129,
                                          "CMFVideoThumbnail::ConvertYUVtoRGB32",
                                          1610,
                                          v13);
                                    }
                                    if ( g_wppLevels )
                                    {
                                      v19 = 143;
                                      goto LABEL_15;
                                    }
                                  }
                                  else
                                  {
                                    v121 = (__int64 *)CallStackTracing::s_wpInstance;
                                    if ( !CallStackTracing::s_wpInstance )
                                    {
                                      v122 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v118, v119, v120);
                                      CallStackTracing::s_wpInstance = v122;
                                      if ( v122
                                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v122 + 8LL))(
                                             v122,
                                             2032) )
                                      {
                                        v121 = (__int64 *)CallStackTracing::s_wpInstance;
                                      }
                                      else
                                      {
                                        v121 = &qword_1800D6F70;
                                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                                      }
                                    }
                                    if ( *((_BYTE *)v121 + 8) )
                                    {
                                      v123 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v121);
                                      if ( *((_DWORD *)v123 + 499) != v13 )
                                        CallStackContext::TraceFailure(
                                          v123,
                                          "CMFVideoThumbnail::ConvertYUVtoRGB32",
                                          1609,
                                          v13);
                                    }
                                    if ( g_wppLevels )
                                    {
                                      v19 = 142;
                                      goto LABEL_15;
                                    }
                                  }
                                }
                                else
                                {
                                  v115 = (__int64 *)CallStackTracing::s_wpInstance;
                                  if ( !CallStackTracing::s_wpInstance )
                                  {
                                    v116 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v112, v113, v114);
                                    CallStackTracing::s_wpInstance = v116;
                                    if ( v116
                                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v116 + 8LL))(
                                           v116,
                                           2032) )
                                    {
                                      v115 = (__int64 *)CallStackTracing::s_wpInstance;
                                    }
                                    else
                                    {
                                      v115 = &qword_1800D6F70;
                                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                                    }
                                  }
                                  if ( *((_BYTE *)v115 + 8) )
                                  {
                                    v117 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v115);
                                    if ( *((_DWORD *)v117 + 499) != v13 )
                                      CallStackContext::TraceFailure(
                                        v117,
                                        "CMFVideoThumbnail::ConvertYUVtoRGB32",
                                        1603,
                                        v13);
                                  }
                                  if ( g_wppLevels )
                                  {
                                    v19 = 141;
                                    goto LABEL_15;
                                  }
                                }
                              }
                              else
                              {
                                v109 = (__int64 *)CallStackTracing::s_wpInstance;
                                if ( !CallStackTracing::s_wpInstance )
                                {
                                  v110 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v106, v107, v108);
                                  CallStackTracing::s_wpInstance = v110;
                                  if ( v110
                                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v110 + 8LL))(
                                         v110,
                                         2032) )
                                  {
                                    v109 = (__int64 *)CallStackTracing::s_wpInstance;
                                  }
                                  else
                                  {
                                    v109 = &qword_1800D6F70;
                                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                                  }
                                }
                                if ( *((_BYTE *)v109 + 8) )
                                {
                                  v111 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v109);
                                  if ( *((_DWORD *)v111 + 499) != v13 )
                                    CallStackContext::TraceFailure(
                                      v111,
                                      "CMFVideoThumbnail::ConvertYUVtoRGB32",
                                      1602,
                                      v13);
                                }
                                if ( g_wppLevels )
                                {
                                  v19 = 140;
                                  goto LABEL_15;
                                }
                              }
                            }
                            else
                            {
                              v103 = (__int64 *)CallStackTracing::s_wpInstance;
                              if ( !CallStackTracing::s_wpInstance )
                              {
                                v104 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v100, v101, v102);
                                CallStackTracing::s_wpInstance = v104;
                                if ( v104
                                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v104 + 8LL))(
                                       v104,
                                       2032) )
                                {
                                  v103 = (__int64 *)CallStackTracing::s_wpInstance;
                                }
                                else
                                {
                                  v103 = &qword_1800D6F70;
                                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                                }
                              }
                              if ( *((_BYTE *)v103 + 8) )
                              {
                                v105 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v103);
                                if ( *((_DWORD *)v105 + 499) != v13 )
                                  CallStackContext::TraceFailure(
                                    v105,
                                    "CMFVideoThumbnail::ConvertYUVtoRGB32",
                                    1601,
                                    v13);
                              }
                              if ( g_wppLevels )
                              {
                                v19 = 139;
                                goto LABEL_15;
                              }
                            }
                          }
                          else
                          {
                            v97 = (__int64 *)CallStackTracing::s_wpInstance;
                            if ( !CallStackTracing::s_wpInstance )
                            {
                              v98 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v94, v95, v96);
                              CallStackTracing::s_wpInstance = v98;
                              if ( v98
                                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v98 + 8LL))(
                                     v98,
                                     2032) )
                              {
                                v97 = (__int64 *)CallStackTracing::s_wpInstance;
                              }
                              else
                              {
                                v97 = &qword_1800D6F70;
                                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                              }
                            }
                            if ( *((_BYTE *)v97 + 8) )
                            {
                              v99 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v97);
                              if ( *((_DWORD *)v99 + 499) != v13 )
                                CallStackContext::TraceFailure(v99, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1600, v13);
                            }
                            if ( g_wppLevels )
                            {
                              v19 = 138;
                              goto LABEL_15;
                            }
                          }
                        }
                        else
                        {
                          v91 = (__int64 *)CallStackTracing::s_wpInstance;
                          if ( !CallStackTracing::s_wpInstance )
                          {
                            v92 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v88, v89, v90);
                            CallStackTracing::s_wpInstance = v92;
                            if ( v92
                              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v92 + 8LL))(
                                   v92,
                                   2032) )
                            {
                              v91 = (__int64 *)CallStackTracing::s_wpInstance;
                            }
                            else
                            {
                              v91 = &qword_1800D6F70;
                              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                            }
                          }
                          if ( *((_BYTE *)v91 + 8) )
                          {
                            v93 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v91);
                            if ( *((_DWORD *)v93 + 499) != v13 )
                              CallStackContext::TraceFailure(v93, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1596, v13);
                          }
                          if ( g_wppLevels )
                          {
                            v19 = 137;
                            goto LABEL_15;
                          }
                        }
                      }
                      else
                      {
                        v85 = (__int64 *)CallStackTracing::s_wpInstance;
                        if ( !CallStackTracing::s_wpInstance )
                        {
                          v86 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v82, v83, v84);
                          CallStackTracing::s_wpInstance = v86;
                          if ( v86
                            && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v86 + 8LL))(
                                 v86,
                                 2032) )
                          {
                            v85 = (__int64 *)CallStackTracing::s_wpInstance;
                          }
                          else
                          {
                            v85 = &qword_1800D6F70;
                            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                          }
                        }
                        if ( *((_BYTE *)v85 + 8) )
                        {
                          v87 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v85);
                          if ( *((_DWORD *)v87 + 499) != v13 )
                            CallStackContext::TraceFailure(v87, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1594, v13);
                        }
                        if ( g_wppLevels )
                        {
                          v19 = 136;
                          goto LABEL_15;
                        }
                      }
                    }
                    else
                    {
                      v79 = (__int64 *)CallStackTracing::s_wpInstance;
                      if ( !CallStackTracing::s_wpInstance )
                      {
                        v80 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v76, v77, v78);
                        CallStackTracing::s_wpInstance = v80;
                        if ( v80
                          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v80 + 8LL))(
                               v80,
                               2032) )
                        {
                          v79 = (__int64 *)CallStackTracing::s_wpInstance;
                        }
                        else
                        {
                          v79 = &qword_1800D6F70;
                          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                        }
                      }
                      if ( *((_BYTE *)v79 + 8) )
                      {
                        v81 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v79);
                        if ( *((_DWORD *)v81 + 499) != v13 )
                          CallStackContext::TraceFailure(v81, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1593, v13);
                      }
                      if ( g_wppLevels )
                      {
                        v19 = 135;
                        goto LABEL_15;
                      }
                    }
                  }
                  else
                  {
                    v73 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v74 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v70, v71, v72);
                      CallStackTracing::s_wpInstance = v74;
                      if ( v74
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v74 + 8LL))(
                             v74,
                             2032) )
                      {
                        v73 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v73 = &qword_1800D6F70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                      }
                    }
                    if ( *((_BYTE *)v73 + 8) )
                    {
                      v75 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v73);
                      if ( *((_DWORD *)v75 + 499) != v13 )
                        CallStackContext::TraceFailure(v75, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1592, v13);
                    }
                    if ( g_wppLevels )
                    {
                      v19 = 134;
                      goto LABEL_15;
                    }
                  }
                }
                else
                {
                  v67 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v68 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v64, v65, v66);
                    CallStackTracing::s_wpInstance = v68;
                    if ( v68
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v68 + 8LL))(v68, 2032) )
                    {
                      v67 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v67 = &qword_1800D6F70;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                    }
                  }
                  if ( *((_BYTE *)v67 + 8) )
                  {
                    v69 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v67);
                    if ( *((_DWORD *)v69 + 499) != v13 )
                      CallStackContext::TraceFailure(v69, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1591, v13);
                  }
                  if ( g_wppLevels )
                  {
                    v19 = 133;
                    goto LABEL_15;
                  }
                }
              }
              else
              {
                v61 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v58, v59, v60);
                  CallStackTracing::s_wpInstance = v62;
                  if ( v62
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(v62, 2032) )
                  {
                    v61 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v61 = &qword_1800D6F70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                  }
                }
                if ( *((_BYTE *)v61 + 8) )
                {
                  v63 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v61);
                  if ( *((_DWORD *)v63 + 499) != v13 )
                    CallStackContext::TraceFailure(v63, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1590, v13);
                }
                if ( g_wppLevels )
                {
                  v19 = 132;
                  goto LABEL_15;
                }
              }
            }
            else
            {
              v53 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v50, v51, v52);
                CallStackTracing::s_wpInstance = v54;
                if ( v54
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
                {
                  v53 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v53 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                }
              }
              if ( *((_BYTE *)v53 + 8) )
              {
                v55 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v53);
                if ( *((_DWORD *)v55 + 499) != v13 )
                  CallStackContext::TraceFailure(v55, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1584, v13);
              }
              if ( g_wppLevels )
              {
                v19 = 131;
                goto LABEL_15;
              }
            }
          }
          else
          {
            v45 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v42, v43, v44);
              CallStackTracing::s_wpInstance = v46;
              if ( v46
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
              {
                v45 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v45 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
              }
            }
            if ( *((_BYTE *)v45 + 8) )
            {
              v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
              if ( *((_DWORD *)v47 + 499) != v13 )
                CallStackContext::TraceFailure(v47, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1583, v13);
            }
            if ( g_wppLevels )
            {
              v19 = 130;
              goto LABEL_15;
            }
          }
        }
        else
        {
          v39 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36, v37, v38);
            CallStackTracing::s_wpInstance = v40;
            if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
            {
              v39 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v39 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v39 + 8) )
          {
            v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
            if ( *((_DWORD *)v41 + 499) != v13 )
              CallStackContext::TraceFailure(v41, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1581, v13);
          }
          if ( g_wppLevels )
          {
            v19 = 129;
            goto LABEL_15;
          }
        }
      }
      else
      {
        v33 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30, v31, v32);
          CallStackTracing::s_wpInstance = v34;
          if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
          {
            v33 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v33 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v33 + 8) )
        {
          v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
          if ( *((_DWORD *)v35 + 499) != v13 )
            CallStackContext::TraceFailure(v35, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1580, v13);
        }
        if ( g_wppLevels )
        {
          v19 = 128;
          goto LABEL_15;
        }
      }
    }
    else
    {
      v27 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25, v26);
        CallStackTracing::s_wpInstance = v28;
        if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
        {
          v27 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v27 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v27 + 8) )
      {
        v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
        if ( *((_DWORD *)v29 + 499) != v13 )
          CallStackContext::TraceFailure(v29, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1579, v13);
      }
      if ( g_wppLevels )
      {
        v19 = 127;
        goto LABEL_15;
      }
    }
  }
  else
  {
    v16 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v14, v15);
      CallStackTracing::s_wpInstance = v17;
      if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
      {
        v16 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v16 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v16 + 8) )
    {
      v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
      if ( *((_DWORD *)v18 + 499) != v13 )
        CallStackContext::TraceFailure(v18, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1574, v13);
    }
    if ( g_wppLevels )
    {
      v19 = 126;
LABEL_15:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, v13);
    }
  }
LABEL_206:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v131);
  Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&v139);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v138);
  Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&v140);
  Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&ppv);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v143);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppIMFSample);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppBuffer);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180064fc8  push    rbp
0x180064fca  push    rbx
0x180064fcb  push    rsi
0x180064fcc  push    rdi
0x180064fcd  push    r12
0x180064fcf  push    r13
0x180064fd1  push    r14
0x180064fd3  push    r15
0x180064fd5  lea     rbp, [rsp-17h]
0x180064fda  sub     rsp, 0E8h
0x180064fe1  mov     rax, cs:__security_cookie
0x180064fe8  xor     rax, rsp
0x180064feb  mov     [rbp+4Fh+var_50], rax
0x180064fef  mov     r12, [rbp+4Fh+arg_20]
0x180064ff3  xor     edi, edi
0x180064ff5  xorps   xmm0, xmm0
0x180064ff8  mov     [rbp+4Fh+ppBuffer], rdi
0x180064ffc  movups  [rbp+4Fh+var_90], xmm0
0x180065000  mov     r14, r8
0x180065003  mov     r13, rdx
0x180065006  movups  [rbp+4Fh+var_80], xmm0
0x18006500a  mov     rsi, rcx
0x18006500d  mov     r8d, 626h; int
0x180065013  movups  xmm0, xmmword ptr cs:MFVideoFormat_ARGB32.Data1
0x18006501a  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x180065021  mov     [rsp+120h+ppIMFSample], rdi
0x180065026  lea     rcx, [rsp+120h+var_F0]; this
0x18006502b  mov     [rbp+4Fh+var_98], rdi
0x18006502f  movdqu  xmmword ptr [rbp+4Fh+guidSubtype.Data1], xmm0
0x180065034  mov     r15, r9
0x180065037  mov     [rsp+120h+var_E0], rdi
0x18006503c  mov     [rbp+4Fh+pcbImageSize], edi
0x18006503f  mov     [rbp+4Fh+var_A0], edi
0x180065042  mov     [rsp+120h+var_E8], rdi
0x180065047  mov     [rbp+4Fh+var_B0], rdi
0x18006504b  mov     [rbp+4Fh+var_C0], rdi
0x18006504f  mov     [rbp+4Fh+unWidth], edi
0x180065052  mov     [rsp+120h+unHeight], edi
0x180065056  mov     [rbp+4Fh+var_B8], rdi
0x18006505a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006505f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180065066  cmp     [rcx+8], dil
0x18006506a  jz      short loc_1800650C2
0x18006506c  cmp     [rsi+190h], rdi
0x180065073  jz      short loc_1800650C2
0x180065075  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006507a  mov     rcx, [rsi+190h]
0x180065081  mov     rdi, rax
0x180065084  mov     rdx, [rcx]
0x180065087  mov     rax, [rdx+128h]
0x18006508e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065093  mov     rcx, [rsi+190h]
0x18006509a  mov     ebx, eax
0x18006509c  mov     rdx, [rcx]
0x18006509f  mov     rax, [rdx+118h]
0x1800650a6  lea     rdx, [rbp+4Fh+var_60]
0x1800650aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800650af  movups  xmm0, xmmword ptr [rax]
0x1800650b2  mov     [rdi+7E0h], ebx
0x1800650b8  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800650c0  xor     edi, edi
0x1800650c2  lea     rcx, [rsp+120h+var_E8]
0x1800650c7  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x1800650cc  xor     edx, edx; pUnkOuter
0x1800650ce  lea     rax, [rsp+120h+var_E8]
0x1800650d3  lea     r9, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d; riid
0x1800650da  mov     [rsp+120h+ppv], rax; ppv
0x1800650df  lea     rcx, CLSID_VideoProcessorMFT; rclsid
0x1800650e6  lea     r8d, [rdx+1]; dwClsContext
0x1800650ea  call    cs:__imp_CoCreateInstance
0x1800650f0  mov     ebx, eax
0x1800650f2  test    eax, eax
0x1800650f4  jns     loc_1800651A7
0x1800650fa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180065101  test    rcx, rcx
0x180065104  jnz     short loc_180065147
0x180065106  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006510c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180065113  mov     rcx, rax
0x180065116  test    rax, rax
0x180065119  jz      short loc_180065139
0x18006511b  mov     rax, [rax]
0x18006511e  mov     edx, 7F0h
0x180065123  mov     rax, [rax+8]
0x180065127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006512c  test    eax, eax
0x18006512e  jz      short loc_180065139
0x180065130  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180065137  jmp     short loc_180065147
0x180065139  lea     rcx, qword_1800D6F70; this
0x180065140  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180065147  cmp     [rcx+8], dil
0x18006514b  jz      short loc_180065172
0x18006514d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180065152  cmp     [rax+7CCh], ebx
0x180065158  jz      short loc_180065172
0x18006515a  mov     r9d, ebx; int
0x18006515d  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x180065164  mov     r8d, 626h; int
0x18006516a  mov     rcx, rax; this
0x18006516d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180065172  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180065179  jb      loc_180065E48
0x18006517f  mov     edx, 7Eh ; '~'
0x180065184  mov     rcx, cs:WPP_GLOBAL_Control
0x18006518b  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x180065192  mov     r9, rsi
0x180065195  mov     dword ptr [rsp+120h+ppv], ebx
0x180065199  mov     rcx, [rcx+10h]
0x18006519d  call    WPP_SF_qD
0x1800651a2  jmp     loc_180065E48
0x1800651a7  mov     rbx, [rsp+120h+var_E8]
0x1800651ac  lea     rcx, [rbp+4Fh+var_B8]
0x1800651b0  mov     rax, [rbx]
0x1800651b3  mov     rdi, [rax]
0x1800651b6  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x1800651bb  lea     r8, [rbp+4Fh+var_B8]
0x1800651bf  mov     rcx, rbx
0x1800651c2  lea     rdx, _GUID_0b5e1c7e_bd76_46bc_896c_b2edb40dd803
0x1800651c9  mov     rax, rdi
0x1800651cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800651d1  test    eax, eax
0x1800651d3  js      short loc_1800651EC
0x1800651d5  mov     rcx, [rbp+4Fh+var_B8]
0x1800651d9  mov     rdx, [rsi+190h]
0x1800651e0  mov     rax, [rcx]
0x1800651e3  mov     rax, [rax+20h]
0x1800651e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800651ec  mov     rdi, [rsp+120h+var_E8]
0x1800651f1  lea     rcx, [rbp+4Fh+var_C0]
0x1800651f5  mov     rax, [rdi]
0x1800651f8  mov     rbx, [rax+40h]
0x1800651fc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180065201  lea     rdx, [rbp+4Fh+var_C0]
0x180065205  mov     rcx, rdi
0x180065208  mov     rax, rbx
0x18006520b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065210  xor     edi, edi
0x180065212  mov     ebx, eax
0x180065214  test    eax, eax
0x180065216  jns     loc_1800652AB
0x18006521c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180065223  test    rcx, rcx
0x180065226  jnz     short loc_180065269
0x180065228  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006522e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180065235  mov     rcx, rax
0x180065238  test    rax, rax
0x18006523b  jz      short loc_18006525B
0x18006523d  mov     rax, [rax]
0x180065240  mov     edx, 7F0h
0x180065245  mov     rax, [rax+8]
0x180065249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006524e  test    eax, eax
0x180065250  jz      short loc_18006525B
0x180065252  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180065259  jmp     short loc_180065269
0x18006525b  lea     rcx, qword_1800D6F70; this
0x180065262  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180065269  cmp     [rcx+8], dil
0x18006526d  jz      short loc_180065294
0x18006526f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180065274  cmp     [rax+7CCh], ebx
0x18006527a  jz      short loc_180065294
0x18006527c  mov     r9d, ebx; int
0x18006527f  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x180065286  mov     r8d, 62Bh; int
0x18006528c  mov     rcx, rax; this
0x18006528f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180065294  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006529b  jb      loc_180065E48
0x1800652a1  mov     edx, 7Fh
0x1800652a6  jmp     loc_180065184
0x1800652ab  mov     rcx, [rbp+4Fh+var_C0]
0x1800652af  lea     rdx, MF_XVP_DISABLE_FRC
0x1800652b6  mov     r8d, 1
0x1800652bc  mov     rax, [rcx]
0x1800652bf  mov     rax, [rax+0A8h]
0x1800652c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800652cb  mov     ebx, eax
0x1800652cd  test    eax, eax
0x1800652cf  jns     loc_180065364
0x1800652d5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800652dc  test    rcx, rcx
0x1800652df  jnz     short loc_180065322
0x1800652e1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800652e7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800652ee  mov     rcx, rax
0x1800652f1  test    rax, rax
0x1800652f4  jz      short loc_180065314
0x1800652f6  mov     rax, [rax]
0x1800652f9  mov     edx, 7F0h
0x1800652fe  mov     rax, [rax+8]
0x180065302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065307  test    eax, eax
0x180065309  jz      short loc_180065314
0x18006530b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180065312  jmp     short loc_180065322
0x180065314  lea     rcx, qword_1800D6F70; this
0x18006531b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180065322  cmp     [rcx+8], dil
0x180065326  jz      short loc_18006534D
0x180065328  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006532d  cmp     [rax+7CCh], ebx
0x180065333  jz      short loc_18006534D
0x180065335  mov     r9d, ebx; int
0x180065338  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x18006533f  mov     r8d, 62Ch; int
0x180065345  mov     rcx, rax; this
0x180065348  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006534d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180065354  jb      loc_180065E48
0x18006535a  mov     edx, 80h
0x18006535f  jmp     loc_180065184
0x180065364  mov     rcx, [rbp+4Fh+var_C0]
0x180065368  lea     rdx, _GUID_2efd8eee_1150_4328_9cf5_66dce933fcf4
0x18006536f  mov     r8d, 1
0x180065375  mov     rax, [rcx]
0x180065378  mov     rax, [rax+0A8h]
0x18006537f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065384  mov     ebx, eax
0x180065386  test    eax, eax
0x180065388  jns     loc_18006541D
0x18006538e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180065395  test    rcx, rcx
0x180065398  jnz     short loc_1800653DB
0x18006539a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800653a0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800653a7  mov     rcx, rax
0x1800653aa  test    rax, rax
0x1800653ad  jz      short loc_1800653CD
0x1800653af  mov     rax, [rax]
0x1800653b2  mov     edx, 7F0h
0x1800653b7  mov     rax, [rax+8]
0x1800653bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800653c0  test    eax, eax
0x1800653c2  jz      short loc_1800653CD
0x1800653c4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800653cb  jmp     short loc_1800653DB
0x1800653cd  lea     rcx, qword_1800D6F70; this
0x1800653d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800653db  cmp     [rcx+8], dil
0x1800653df  jz      short loc_180065406
0x1800653e1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800653e6  cmp     [rax+7CCh], ebx
0x1800653ec  jz      short loc_180065406
0x1800653ee  mov     r9d, ebx; int
0x1800653f1  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x1800653f8  mov     r8d, 62Dh; int
0x1800653fe  mov     rcx, rax; this
0x180065401  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180065406  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006540d  jb      loc_180065E48
0x180065413  mov     edx, 81h
0x180065418  jmp     loc_180065184
0x18006541d  mov     rcx, [rsp+120h+var_E8]
0x180065422  xor     r9d, r9d
0x180065425  mov     r8, r14
0x180065428  xor     edx, edx
0x18006542a  mov     rax, [rcx]
0x18006542d  mov     rax, [rax+78h]
0x180065431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065436  xor     r14d, r14d
0x180065439  mov     ebx, eax
0x18006543b  test    eax, eax
0x18006543d  jns     loc_1800654D2
0x180065443  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006544a  test    rcx, rcx
0x18006544d  jnz     short loc_180065490
0x18006544f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180065455  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006545c  mov     rcx, rax
0x18006545f  test    rax, rax
0x180065462  jz      short loc_180065482
0x180065464  mov     rax, [rax]
0x180065467  mov     edx, 7F0h
0x18006546c  mov     rax, [rax+8]
0x180065470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065475  test    eax, eax
0x180065477  jz      short loc_180065482
0x180065479  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180065480  jmp     short loc_180065490
0x180065482  lea     rcx, qword_1800D6F70; this
0x180065489  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180065490  cmp     [rcx+8], r14b
0x180065494  jz      short loc_1800654BB
0x180065496  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006549b  cmp     [rax+7CCh], ebx
0x1800654a1  jz      short loc_1800654BB
0x1800654a3  mov     r9d, ebx; int
0x1800654a6  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x1800654ad  mov     r8d, 62Fh; int
0x1800654b3  mov     rcx, rax; this
0x1800654b6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800654bb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800654c2  jb      loc_180065E48
0x1800654c8  mov     edx, 82h
0x1800654cd  jmp     loc_180065184
0x1800654d2  mov     rdi, [rsp+120h+var_E8]
0x1800654d7  lea     rcx, [rbp+4Fh+var_B0]
  ... truncated ...
```
