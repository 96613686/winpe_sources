# CMFVideoThumbnail::ConvertYUVtoRGB32(IMFSample *,IMFMediaType *,IMFSample * *,IMFMediaType * *)

- ea: `0x1800ca5e0`
- end: `0x1800cb4d7`
- name: `?ConvertYUVtoRGB32@CMFVideoThumbnail@@AEAAJPEAUIMFSample@@PEAUIMFMediaType@@PEAPEAU2@PEAPEAU3@@Z`
- size: `3831`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFSample *, struct IMFMediaType *, struct IMFSample **, struct IMFMediaType **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800dc788`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x1800734a8`
- `0x180073b14`
- `0x180073e00`
- `0x1800ca5e0`
- `0x1801099f0`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ca71e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ca840`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ca8f9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ca9b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800caa67`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cab2a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cabe8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800caca0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cad5c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cae1a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800caed1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800caf84`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cb033`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cb0e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cb190`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cb241`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cb307`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cb3c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ca71e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ca840`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ca8f9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ca9b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800caa67`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cab2a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cabe8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800caca0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cad5c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cae1a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800caed1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800caf84`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cb033`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cb0e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cb190`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cb241`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cb307`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cb3c6`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800cb0c6`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800cb0c6`
- `MFPlat!MFCalculateImageSize` at `0x1800cb017`
- `MFPlat!MFCalculateImageSize` at `0x1800cb017`
- `MFPlat!MFCreateSample` at `0x1800cb174`
- `MFPlat!MFCreateSample` at `0x1800cb174`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ca702`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ca702`

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
  wchar_t *v16; // rcx
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
  wchar_t *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  wchar_t *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  wchar_t *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // r9
  wchar_t *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  LPVOID v48; // rdi
  __int64 (__fastcall *v49)(LPVOID, GUID *, __int64 *); // rbx
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // r9
  wchar_t *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  __int64 v56; // rdi
  __int64 (__fastcall *v57)(__int64, struct IMFMediaType **); // rbx
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 v60; // r9
  wchar_t *v61; // rcx
  CallStackTracing *v62; // rax
  struct CallStackContext *v63; // rax
  __int64 v64; // rdx
  __int64 v65; // r8
  __int64 v66; // r9
  wchar_t *v67; // rcx
  CallStackTracing *v68; // rax
  struct CallStackContext *v69; // rax
  __int64 v70; // rdx
  __int64 v71; // r8
  __int64 v72; // r9
  wchar_t *v73; // rcx
  CallStackTracing *v74; // rax
  struct CallStackContext *v75; // rax
  __int64 v76; // rdx
  __int64 v77; // r8
  __int64 v78; // r9
  wchar_t *v79; // rcx
  CallStackTracing *v80; // rax
  struct CallStackContext *v81; // rax
  __int64 v82; // rdx
  __int64 v83; // r8
  __int64 v84; // r9
  wchar_t *v85; // rcx
  CallStackTracing *v86; // rax
  struct CallStackContext *v87; // rax
  __int64 v88; // rdx
  __int64 v89; // r8
  __int64 v90; // r9
  wchar_t *v91; // rcx
  CallStackTracing *v92; // rax
  struct CallStackContext *v93; // rax
  __int64 v94; // rdx
  __int64 v95; // r8
  __int64 v96; // r9
  wchar_t *v97; // rcx
  CallStackTracing *v98; // rax
  struct CallStackContext *v99; // rax
  __int64 v100; // rdx
  __int64 v101; // r8
  __int64 v102; // r9
  wchar_t *v103; // rcx
  CallStackTracing *v104; // rax
  struct CallStackContext *v105; // rax
  __int64 v106; // rdx
  __int64 v107; // r8
  __int64 v108; // r9
  wchar_t *v109; // rcx
  CallStackTracing *v110; // rax
  struct CallStackContext *v111; // rax
  __int64 v112; // rdx
  __int64 v113; // r8
  __int64 v114; // r9
  wchar_t *v115; // rcx
  CallStackTracing *v116; // rax
  struct CallStackContext *v117; // rax
  __int64 v118; // rdx
  __int64 v119; // r8
  __int64 v120; // r9
  wchar_t *v121; // rcx
  CallStackTracing *v122; // rax
  struct CallStackContext *v123; // rax
  __int64 v124; // rdx
  __int64 v125; // r8
  __int64 v126; // r9
  wchar_t *v127; // rcx
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
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&ppv);
  v13 = CoCreateInstance(&CLSID_VideoProcessorMFT, 0, 1u, &GUID_bf94c121_5b05_4e6f_8000_ba598961414d, &ppv);
  if ( v13 >= 0 )
  {
    v20 = ppv;
    v21 = **(int (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v139);
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
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v140);
            v13 = v49(v48, &GUID_44f18199_7981_4f93_abe8_287ff0cccd7a, &v140);
            if ( v13 >= 0 )
            {
              v56 = v140;
              v57 = *(__int64 (__fastcall **)(__int64, struct IMFMediaType **))(*(_QWORD *)v140 + 96LL);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v133);
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
                            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&ppBuffer);
                            v13 = MFCreateMemoryBuffer(pcbImageSize, &ppBuffer);
                            if ( v13 >= 0 )
                            {
                              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&ppIMFSample);
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
                                    v127 = (wchar_t *)CallStackTracing::s_wpInstance;
                                    if ( !CallStackTracing::s_wpInstance )
                                    {
                                      v128 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v124, v125, v126);
                                      CallStackTracing::s_wpInstance = v128;
                                      if ( v128
                                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v128 + 8LL))(
                                             v128,
                                             2032) )
                                      {
                                        v127 = (wchar_t *)CallStackTracing::s_wpInstance;
                                      }
                                      else
                                      {
                                        v127 = &qword_1801B07E0;
                                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                                    v121 = (wchar_t *)CallStackTracing::s_wpInstance;
                                    if ( !CallStackTracing::s_wpInstance )
                                    {
                                      v122 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v118, v119, v120);
                                      CallStackTracing::s_wpInstance = v122;
                                      if ( v122
                                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v122 + 8LL))(
                                             v122,
                                             2032) )
                                      {
                                        v121 = (wchar_t *)CallStackTracing::s_wpInstance;
                                      }
                                      else
                                      {
                                        v121 = &qword_1801B07E0;
                                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                                  v115 = (wchar_t *)CallStackTracing::s_wpInstance;
                                  if ( !CallStackTracing::s_wpInstance )
                                  {
                                    v116 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v112, v113, v114);
                                    CallStackTracing::s_wpInstance = v116;
                                    if ( v116
                                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v116 + 8LL))(
                                           v116,
                                           2032) )
                                    {
                                      v115 = (wchar_t *)CallStackTracing::s_wpInstance;
                                    }
                                    else
                                    {
                                      v115 = &qword_1801B07E0;
                                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                                v109 = (wchar_t *)CallStackTracing::s_wpInstance;
                                if ( !CallStackTracing::s_wpInstance )
                                {
                                  v110 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v106, v107, v108);
                                  CallStackTracing::s_wpInstance = v110;
                                  if ( v110
                                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v110 + 8LL))(
                                         v110,
                                         2032) )
                                  {
                                    v109 = (wchar_t *)CallStackTracing::s_wpInstance;
                                  }
                                  else
                                  {
                                    v109 = &qword_1801B07E0;
                                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                              v103 = (wchar_t *)CallStackTracing::s_wpInstance;
                              if ( !CallStackTracing::s_wpInstance )
                              {
                                v104 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v100, v101, v102);
                                CallStackTracing::s_wpInstance = v104;
                                if ( v104
                                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v104 + 8LL))(
                                       v104,
                                       2032) )
                                {
                                  v103 = (wchar_t *)CallStackTracing::s_wpInstance;
                                }
                                else
                                {
                                  v103 = &qword_1801B07E0;
                                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                            v97 = (wchar_t *)CallStackTracing::s_wpInstance;
                            if ( !CallStackTracing::s_wpInstance )
                            {
                              v98 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v94, v95, v96);
                              CallStackTracing::s_wpInstance = v98;
                              if ( v98
                                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v98 + 8LL))(
                                     v98,
                                     2032) )
                              {
                                v97 = (wchar_t *)CallStackTracing::s_wpInstance;
                              }
                              else
                              {
                                v97 = &qword_1801B07E0;
                                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                          v91 = (wchar_t *)CallStackTracing::s_wpInstance;
                          if ( !CallStackTracing::s_wpInstance )
                          {
                            v92 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v88, v89, v90);
                            CallStackTracing::s_wpInstance = v92;
                            if ( v92
                              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v92 + 8LL))(
                                   v92,
                                   2032) )
                            {
                              v91 = (wchar_t *)CallStackTracing::s_wpInstance;
                            }
                            else
                            {
                              v91 = &qword_1801B07E0;
                              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                        v85 = (wchar_t *)CallStackTracing::s_wpInstance;
                        if ( !CallStackTracing::s_wpInstance )
                        {
                          v86 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v82, v83, v84);
                          CallStackTracing::s_wpInstance = v86;
                          if ( v86
                            && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v86 + 8LL))(
                                 v86,
                                 2032) )
                          {
                            v85 = (wchar_t *)CallStackTracing::s_wpInstance;
                          }
                          else
                          {
                            v85 = &qword_1801B07E0;
                            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                      v79 = (wchar_t *)CallStackTracing::s_wpInstance;
                      if ( !CallStackTracing::s_wpInstance )
                      {
                        v80 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v76, v77, v78);
                        CallStackTracing::s_wpInstance = v80;
                        if ( v80
                          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v80 + 8LL))(
                               v80,
                               2032) )
                        {
                          v79 = (wchar_t *)CallStackTracing::s_wpInstance;
                        }
                        else
                        {
                          v79 = &qword_1801B07E0;
                          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                    v73 = (wchar_t *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v74 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v70, v71, v72);
                      CallStackTracing::s_wpInstance = v74;
                      if ( v74
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v74 + 8LL))(
                             v74,
                             2032) )
                      {
                        v73 = (wchar_t *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v73 = &qword_1801B07E0;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                  v67 = (wchar_t *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v68 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v64, v65, v66);
                    CallStackTracing::s_wpInstance = v68;
                    if ( v68
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v68 + 8LL))(v68, 2032) )
                    {
                      v67 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v67 = &qword_1801B07E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                v61 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v58, v59, v60);
                  CallStackTracing::s_wpInstance = v62;
                  if ( v62
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(v62, 2032) )
                  {
                    v61 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v61 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
              v53 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v50, v51, v52);
                CallStackTracing::s_wpInstance = v54;
                if ( v54
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
                {
                  v53 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v53 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v45 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v42, v43, v44);
              CallStackTracing::s_wpInstance = v46;
              if ( v46
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
              {
                v45 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v45 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v39 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36, v37, v38);
            CallStackTracing::s_wpInstance = v40;
            if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
            {
              v39 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v39 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v33 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30, v31, v32);
          CallStackTracing::s_wpInstance = v34;
          if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
          {
            v33 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v33 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
      v27 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25, v26);
        CallStackTracing::s_wpInstance = v28;
        if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
        {
          v27 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v27 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
    v16 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v14, v15);
      CallStackTracing::s_wpInstance = v17;
      if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
      {
        v16 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v16 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v139);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v138);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v140);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&ppv);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v133);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v143);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&ppIMFSample);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&ppBuffer);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800ca5e0  push    rbp
0x1800ca5e2  push    rbx
0x1800ca5e3  push    rsi
0x1800ca5e4  push    rdi
0x1800ca5e5  push    r12
0x1800ca5e7  push    r13
0x1800ca5e9  push    r14
0x1800ca5eb  push    r15
0x1800ca5ed  lea     rbp, [rsp-17h]
0x1800ca5f2  sub     rsp, 0E8h
0x1800ca5f9  mov     rax, cs:__security_cookie
0x1800ca600  xor     rax, rsp
0x1800ca603  mov     [rbp+4Fh+var_50], rax
0x1800ca607  mov     r12, [rbp+4Fh+arg_20]
0x1800ca60b  xor     edi, edi
0x1800ca60d  xorps   xmm0, xmm0
0x1800ca610  mov     [rbp+4Fh+ppBuffer], rdi
0x1800ca614  movups  [rbp+4Fh+var_90], xmm0
0x1800ca618  mov     r14, r8
0x1800ca61b  mov     r13, rdx
0x1800ca61e  movups  [rbp+4Fh+var_80], xmm0
0x1800ca622  mov     rsi, rcx
0x1800ca625  mov     r8d, 626h; int
0x1800ca62b  movups  xmm0, xmmword ptr cs:MFVideoFormat_ARGB32.Data1
0x1800ca632  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x1800ca639  mov     [rsp+120h+ppIMFSample], rdi
0x1800ca63e  lea     rcx, [rsp+120h+var_F0]; this
0x1800ca643  mov     [rbp+4Fh+var_98], rdi
0x1800ca647  movdqu  xmmword ptr [rbp+4Fh+guidSubtype.Data1], xmm0
0x1800ca64c  mov     r15, r9
0x1800ca64f  mov     [rsp+120h+var_E0], rdi
0x1800ca654  mov     [rbp+4Fh+pcbImageSize], edi
0x1800ca657  mov     [rbp+4Fh+var_A0], edi
0x1800ca65a  mov     [rsp+120h+var_E8], rdi
0x1800ca65f  mov     [rbp+4Fh+var_B0], rdi
0x1800ca663  mov     [rbp+4Fh+var_C0], rdi
0x1800ca667  mov     [rbp+4Fh+unWidth], edi
0x1800ca66a  mov     [rsp+120h+unHeight], edi
0x1800ca66e  mov     [rbp+4Fh+var_B8], rdi
0x1800ca672  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800ca677  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ca67e  cmp     [rcx+8], dil
0x1800ca682  jz      short loc_1800CA6DA
0x1800ca684  cmp     [rsi+190h], rdi
0x1800ca68b  jz      short loc_1800CA6DA
0x1800ca68d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ca692  mov     rcx, [rsi+190h]
0x1800ca699  mov     rdi, rax
0x1800ca69c  mov     rdx, [rcx]
0x1800ca69f  mov     rax, [rdx+128h]
0x1800ca6a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca6ab  mov     rcx, [rsi+190h]
0x1800ca6b2  mov     ebx, eax
0x1800ca6b4  mov     rdx, [rcx]
0x1800ca6b7  mov     rax, [rdx+118h]
0x1800ca6be  lea     rdx, [rbp+4Fh+var_60]
0x1800ca6c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca6c7  movups  xmm0, xmmword ptr [rax]
0x1800ca6ca  mov     [rdi+7E0h], ebx
0x1800ca6d0  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800ca6d8  xor     edi, edi
0x1800ca6da  lea     rcx, [rsp+120h+var_E8]
0x1800ca6df  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ca6e4  xor     edx, edx; pUnkOuter
0x1800ca6e6  lea     rax, [rsp+120h+var_E8]
0x1800ca6eb  lea     r9, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d; riid
0x1800ca6f2  mov     [rsp+120h+ppv], rax; ppv
0x1800ca6f7  lea     rcx, CLSID_VideoProcessorMFT; rclsid
0x1800ca6fe  lea     r8d, [rdx+1]; dwClsContext
0x1800ca702  call    cs:__imp_CoCreateInstance
0x1800ca708  mov     ebx, eax
0x1800ca70a  test    eax, eax
0x1800ca70c  jns     loc_1800CA7BF
0x1800ca712  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca719  test    rcx, rcx
0x1800ca71c  jnz     short loc_1800CA75F
0x1800ca71e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ca724  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca72b  mov     rcx, rax
0x1800ca72e  test    rax, rax
0x1800ca731  jz      short loc_1800CA751
0x1800ca733  mov     rax, [rax]
0x1800ca736  mov     edx, 7F0h
0x1800ca73b  mov     rax, [rax+8]
0x1800ca73f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca744  test    eax, eax
0x1800ca746  jz      short loc_1800CA751
0x1800ca748  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca74f  jmp     short loc_1800CA75F
0x1800ca751  lea     rcx, qword_1801B07E0; this
0x1800ca758  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca75f  cmp     [rcx+8], dil
0x1800ca763  jz      short loc_1800CA78A
0x1800ca765  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ca76a  cmp     [rax+7CCh], ebx
0x1800ca770  jz      short loc_1800CA78A
0x1800ca772  mov     r9d, ebx; int
0x1800ca775  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x1800ca77c  mov     r8d, 626h; int
0x1800ca782  mov     rcx, rax; this
0x1800ca785  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ca78a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ca791  jb      loc_1800CB460
0x1800ca797  mov     edx, 7Eh ; '~'
0x1800ca79c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ca7a3  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x1800ca7aa  mov     r9, rsi
0x1800ca7ad  mov     dword ptr [rsp+120h+ppv], ebx
0x1800ca7b1  mov     rcx, [rcx+10h]
0x1800ca7b5  call    WPP_SF_qD
0x1800ca7ba  jmp     loc_1800CB460
0x1800ca7bf  mov     rbx, [rsp+120h+var_E8]
0x1800ca7c4  lea     rcx, [rbp+4Fh+var_B8]
0x1800ca7c8  mov     rax, [rbx]
0x1800ca7cb  mov     rdi, [rax]
0x1800ca7ce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ca7d3  lea     r8, [rbp+4Fh+var_B8]
0x1800ca7d7  mov     rcx, rbx
0x1800ca7da  lea     rdx, _GUID_0b5e1c7e_bd76_46bc_896c_b2edb40dd803
0x1800ca7e1  mov     rax, rdi
0x1800ca7e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca7e9  test    eax, eax
0x1800ca7eb  js      short loc_1800CA804
0x1800ca7ed  mov     rcx, [rbp+4Fh+var_B8]
0x1800ca7f1  mov     rdx, [rsi+190h]
0x1800ca7f8  mov     rax, [rcx]
0x1800ca7fb  mov     rax, [rax+20h]
0x1800ca7ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca804  mov     rdi, [rsp+120h+var_E8]
0x1800ca809  lea     rcx, [rbp+4Fh+var_C0]
0x1800ca80d  mov     rax, [rdi]
0x1800ca810  mov     rbx, [rax+40h]
0x1800ca814  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ca819  lea     rdx, [rbp+4Fh+var_C0]
0x1800ca81d  mov     rcx, rdi
0x1800ca820  mov     rax, rbx
0x1800ca823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca828  xor     edi, edi
0x1800ca82a  mov     ebx, eax
0x1800ca82c  test    eax, eax
0x1800ca82e  jns     loc_1800CA8C3
0x1800ca834  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca83b  test    rcx, rcx
0x1800ca83e  jnz     short loc_1800CA881
0x1800ca840  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ca846  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca84d  mov     rcx, rax
0x1800ca850  test    rax, rax
0x1800ca853  jz      short loc_1800CA873
0x1800ca855  mov     rax, [rax]
0x1800ca858  mov     edx, 7F0h
0x1800ca85d  mov     rax, [rax+8]
0x1800ca861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca866  test    eax, eax
0x1800ca868  jz      short loc_1800CA873
0x1800ca86a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca871  jmp     short loc_1800CA881
0x1800ca873  lea     rcx, qword_1801B07E0; this
0x1800ca87a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca881  cmp     [rcx+8], dil
0x1800ca885  jz      short loc_1800CA8AC
0x1800ca887  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ca88c  cmp     [rax+7CCh], ebx
0x1800ca892  jz      short loc_1800CA8AC
0x1800ca894  mov     r9d, ebx; int
0x1800ca897  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x1800ca89e  mov     r8d, 62Bh; int
0x1800ca8a4  mov     rcx, rax; this
0x1800ca8a7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ca8ac  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ca8b3  jb      loc_1800CB460
0x1800ca8b9  mov     edx, 7Fh
0x1800ca8be  jmp     loc_1800CA79C
0x1800ca8c3  mov     rcx, [rbp+4Fh+var_C0]
0x1800ca8c7  lea     rdx, MF_XVP_DISABLE_FRC
0x1800ca8ce  mov     r8d, 1
0x1800ca8d4  mov     rax, [rcx]
0x1800ca8d7  mov     rax, [rax+0A8h]
0x1800ca8de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca8e3  mov     ebx, eax
0x1800ca8e5  test    eax, eax
0x1800ca8e7  jns     loc_1800CA97C
0x1800ca8ed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca8f4  test    rcx, rcx
0x1800ca8f7  jnz     short loc_1800CA93A
0x1800ca8f9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ca8ff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca906  mov     rcx, rax
0x1800ca909  test    rax, rax
0x1800ca90c  jz      short loc_1800CA92C
0x1800ca90e  mov     rax, [rax]
0x1800ca911  mov     edx, 7F0h
0x1800ca916  mov     rax, [rax+8]
0x1800ca91a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca91f  test    eax, eax
0x1800ca921  jz      short loc_1800CA92C
0x1800ca923  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca92a  jmp     short loc_1800CA93A
0x1800ca92c  lea     rcx, qword_1801B07E0; this
0x1800ca933  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca93a  cmp     [rcx+8], dil
0x1800ca93e  jz      short loc_1800CA965
0x1800ca940  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ca945  cmp     [rax+7CCh], ebx
0x1800ca94b  jz      short loc_1800CA965
0x1800ca94d  mov     r9d, ebx; int
0x1800ca950  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x1800ca957  mov     r8d, 62Ch; int
0x1800ca95d  mov     rcx, rax; this
0x1800ca960  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ca965  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ca96c  jb      loc_1800CB460
0x1800ca972  mov     edx, 80h
0x1800ca977  jmp     loc_1800CA79C
0x1800ca97c  mov     rcx, [rbp+4Fh+var_C0]
0x1800ca980  lea     rdx, _GUID_2efd8eee_1150_4328_9cf5_66dce933fcf4
0x1800ca987  mov     r8d, 1
0x1800ca98d  mov     rax, [rcx]
0x1800ca990  mov     rax, [rax+0A8h]
0x1800ca997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca99c  mov     ebx, eax
0x1800ca99e  test    eax, eax
0x1800ca9a0  jns     loc_1800CAA35
0x1800ca9a6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca9ad  test    rcx, rcx
0x1800ca9b0  jnz     short loc_1800CA9F3
0x1800ca9b2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ca9b8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca9bf  mov     rcx, rax
0x1800ca9c2  test    rax, rax
0x1800ca9c5  jz      short loc_1800CA9E5
0x1800ca9c7  mov     rax, [rax]
0x1800ca9ca  mov     edx, 7F0h
0x1800ca9cf  mov     rax, [rax+8]
0x1800ca9d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca9d8  test    eax, eax
0x1800ca9da  jz      short loc_1800CA9E5
0x1800ca9dc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca9e3  jmp     short loc_1800CA9F3
0x1800ca9e5  lea     rcx, qword_1801B07E0; this
0x1800ca9ec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca9f3  cmp     [rcx+8], dil
0x1800ca9f7  jz      short loc_1800CAA1E
0x1800ca9f9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ca9fe  cmp     [rax+7CCh], ebx
0x1800caa04  jz      short loc_1800CAA1E
0x1800caa06  mov     r9d, ebx; int
0x1800caa09  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x1800caa10  mov     r8d, 62Dh; int
0x1800caa16  mov     rcx, rax; this
0x1800caa19  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800caa1e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800caa25  jb      loc_1800CB460
0x1800caa2b  mov     edx, 81h
0x1800caa30  jmp     loc_1800CA79C
0x1800caa35  mov     rcx, [rsp+120h+var_E8]
0x1800caa3a  xor     r9d, r9d
0x1800caa3d  mov     r8, r14
0x1800caa40  xor     edx, edx
0x1800caa42  mov     rax, [rcx]
0x1800caa45  mov     rax, [rax+78h]
0x1800caa49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800caa4e  xor     r14d, r14d
0x1800caa51  mov     ebx, eax
0x1800caa53  test    eax, eax
0x1800caa55  jns     loc_1800CAAEA
0x1800caa5b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800caa62  test    rcx, rcx
0x1800caa65  jnz     short loc_1800CAAA8
0x1800caa67  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800caa6d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800caa74  mov     rcx, rax
0x1800caa77  test    rax, rax
0x1800caa7a  jz      short loc_1800CAA9A
0x1800caa7c  mov     rax, [rax]
0x1800caa7f  mov     edx, 7F0h
0x1800caa84  mov     rax, [rax+8]
0x1800caa88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800caa8d  test    eax, eax
0x1800caa8f  jz      short loc_1800CAA9A
0x1800caa91  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800caa98  jmp     short loc_1800CAAA8
0x1800caa9a  lea     rcx, qword_1801B07E0; this
0x1800caaa1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800caaa8  cmp     [rcx+8], r14b
0x1800caaac  jz      short loc_1800CAAD3
0x1800caaae  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800caab3  cmp     [rax+7CCh], ebx
0x1800caab9  jz      short loc_1800CAAD3
0x1800caabb  mov     r9d, ebx; int
0x1800caabe  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x1800caac5  mov     r8d, 62Fh; int
0x1800caacb  mov     rcx, rax; this
0x1800caace  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800caad3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800caada  jb      loc_1800CB460
0x1800caae0  mov     edx, 82h
0x1800caae5  jmp     loc_1800CA79C
0x1800caaea  mov     rdi, [rsp+120h+var_E8]
0x1800caaef  lea     rcx, [rbp+4Fh+var_B0]
  ... truncated ...
```
