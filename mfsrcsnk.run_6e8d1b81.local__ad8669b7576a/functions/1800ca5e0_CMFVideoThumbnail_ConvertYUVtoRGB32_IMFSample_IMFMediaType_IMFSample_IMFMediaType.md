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
  wchar_t *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  LPVOID v18; // rbx
  int (__fastcall *v19)(LPVOID, GUID *, __int64 *); // rdi
  LPVOID v20; // rdi
  __int64 (__fastcall *v21)(LPVOID, __int64 *); // rbx
  __int64 v22; // rdx
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  wchar_t *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  wchar_t *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  wchar_t *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  LPVOID v38; // rdi
  __int64 (__fastcall *v39)(LPVOID, GUID *, __int64 *); // rbx
  __int64 v40; // rdx
  wchar_t *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 v44; // rdi
  __int64 (__fastcall *v45)(__int64, struct IMFMediaType **); // rbx
  __int64 v46; // rdx
  wchar_t *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  __int64 v50; // rdx
  wchar_t *v51; // rcx
  CallStackTracing *v52; // rax
  struct CallStackContext *v53; // rax
  __int64 v54; // rdx
  wchar_t *v55; // rcx
  CallStackTracing *v56; // rax
  struct CallStackContext *v57; // rax
  __int64 v58; // rdx
  wchar_t *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  __int64 v62; // rdx
  wchar_t *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  __int64 v66; // rdx
  wchar_t *v67; // rcx
  CallStackTracing *v68; // rax
  struct CallStackContext *v69; // rax
  __int64 v70; // rdx
  wchar_t *v71; // rcx
  CallStackTracing *v72; // rax
  struct CallStackContext *v73; // rax
  __int64 v74; // rdx
  wchar_t *v75; // rcx
  CallStackTracing *v76; // rax
  struct CallStackContext *v77; // rax
  __int64 v78; // rdx
  wchar_t *v79; // rcx
  CallStackTracing *v80; // rax
  struct CallStackContext *v81; // rax
  __int64 v82; // rdx
  wchar_t *v83; // rcx
  CallStackTracing *v84; // rax
  struct CallStackContext *v85; // rax
  __int64 v86; // rdx
  wchar_t *v87; // rcx
  CallStackTracing *v88; // rax
  struct CallStackContext *v89; // rax
  __int64 v90; // rdx
  wchar_t *v91; // rcx
  CallStackTracing *v92; // rax
  struct CallStackContext *v93; // rax
  _BYTE v95[8]; // [rsp+30h] [rbp-A1h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-99h] BYREF
  struct IMFMediaType *v97; // [rsp+40h] [rbp-91h] BYREF
  IMFSample *ppIMFSample; // [rsp+48h] [rbp-89h] BYREF
  UINT32 unHeight; // [rsp+50h] [rbp-81h] BYREF
  UINT32 unWidth; // [rsp+54h] [rbp-7Dh] BYREF
  UINT32 pcbImageSize; // [rsp+58h] [rbp-79h] BYREF
  __int64 v102; // [rsp+60h] [rbp-71h] BYREF
  __int64 v103; // [rsp+68h] [rbp-69h] BYREF
  __int64 v104; // [rsp+70h] [rbp-61h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+78h] [rbp-59h] BYREF
  int v106; // [rsp+80h] [rbp-51h] BYREF
  __int64 v107; // [rsp+88h] [rbp-49h] BYREF
  __int128 v108; // [rsp+90h] [rbp-41h] BYREF
  __int128 v109; // [rsp+A0h] [rbp-31h]
  GUID guidSubtype; // [rsp+B0h] [rbp-21h] BYREF
  _BYTE v111[16]; // [rsp+C0h] [rbp-11h] BYREF

  ppBuffer = 0;
  v108 = 0;
  v109 = 0;
  ppIMFSample = 0;
  v107 = 0;
  guidSubtype = MFVideoFormat_ARGB32;
  v97 = 0;
  pcbImageSize = 0;
  v106 = 0;
  ppv = 0;
  v104 = 0;
  v102 = 0;
  unWidth = 0;
  unHeight = 0;
  v103 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v95, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1574);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 50) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 296LL))(*((_QWORD *)this + 50));
    v11 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 50) + 280LL))(
                       *((_QWORD *)this + 50),
                       v111);
    *((_DWORD *)ThreadRelativeContext + 504) = v10;
    *((_OWORD *)ThreadRelativeContext + 125) = v11;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  v13 = CoCreateInstance(&CLSID_VideoProcessorMFT, 0, 1u, &GUID_bf94c121_5b05_4e6f_8000_ba598961414d, &ppv);
  if ( v13 >= 0 )
  {
    v18 = ppv;
    v19 = **(int (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103);
    if ( v19(v18, &GUID_0b5e1c7e_bd76_46bc_896c_b2edb40dd803, &v103) >= 0 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v103 + 32LL))(v103, *((_QWORD *)this + 50));
    v20 = ppv;
    v21 = *(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 64LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102);
    v13 = v21(v20, &v102);
    if ( v13 >= 0 )
    {
      v13 = (*(__int64 (__fastcall **)(__int64, const IID *, __int64))(*(_QWORD *)v102 + 168LL))(
              v102,
              &MF_XVP_DISABLE_FRC,
              1);
      if ( v13 >= 0 )
      {
        v13 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v102 + 168LL))(
                v102,
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
            v38 = ppv;
            v39 = **(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v104);
            v13 = v39(v38, &GUID_44f18199_7981_4f93_abe8_287ff0cccd7a, &v104);
            if ( v13 >= 0 )
            {
              v44 = v104;
              v45 = *(__int64 (__fastcall **)(__int64, struct IMFMediaType **))(*(_QWORD *)v104 + 96LL);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
              v13 = v45(v44, &v97);
              if ( v13 >= 0 )
              {
                v13 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, GUID *))v97->lpVtbl->SetGUID)(
                        v97,
                        &MF_MT_SUBTYPE,
                        &guidSubtype);
                if ( v13 >= 0 )
                {
                  v13 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, __int64))v97->lpVtbl->SetUINT32)(
                          v97,
                          &MF_MT_DEFAULT_STRIDE,
                          1);
                  if ( v13 >= 0 )
                  {
                    v13 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, __int64))v97->lpVtbl->SetUINT64)(
                            v97,
                            &MF_MT_PIXEL_ASPECT_RATIO,
                            0x100000001LL);
                    if ( v13 >= 0 )
                    {
                      v13 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct IMFMediaType *, _QWORD))(*(_QWORD *)ppv + 128LL))(
                              ppv,
                              0,
                              v97,
                              0);
                      if ( v13 >= 0 )
                      {
                        v13 = MFGetAttribute2UINT32asUINT64(v97, &MF_MT_FRAME_SIZE, &unWidth, &unHeight);
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
                                  *((_QWORD *)&v108 + 1) = ppIMFSample;
                                  LODWORD(v109) = 0;
                                  LODWORD(v108) = 0;
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
                                            &v108,
                                            &v106);
                                    if ( v13 >= 0 )
                                    {
                                      *a4 = ppIMFSample;
                                      *a5 = v97;
                                      ppIMFSample = 0;
                                      v97 = 0;
                                      goto LABEL_206;
                                    }
                                    v91 = (wchar_t *)CallStackTracing::s_wpInstance;
                                    if ( !CallStackTracing::s_wpInstance )
                                    {
                                      v92 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v90);
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
                                        CallStackContext::TraceFailure(
                                          v93,
                                          "CMFVideoThumbnail::ConvertYUVtoRGB32",
                                          1610,
                                          v13);
                                    }
                                    if ( g_wppLevels )
                                    {
                                      v17 = 143;
                                      goto LABEL_15;
                                    }
                                  }
                                  else
                                  {
                                    v87 = (wchar_t *)CallStackTracing::s_wpInstance;
                                    if ( !CallStackTracing::s_wpInstance )
                                    {
                                      v88 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v86);
                                      CallStackTracing::s_wpInstance = v88;
                                      if ( v88
                                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v88 + 8LL))(
                                             v88,
                                             2032) )
                                      {
                                        v87 = (wchar_t *)CallStackTracing::s_wpInstance;
                                      }
                                      else
                                      {
                                        v87 = &qword_1801B07E0;
                                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                                      }
                                    }
                                    if ( *((_BYTE *)v87 + 8) )
                                    {
                                      v89 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v87);
                                      if ( *((_DWORD *)v89 + 499) != v13 )
                                        CallStackContext::TraceFailure(
                                          v89,
                                          "CMFVideoThumbnail::ConvertYUVtoRGB32",
                                          1609,
                                          v13);
                                    }
                                    if ( g_wppLevels )
                                    {
                                      v17 = 142;
                                      goto LABEL_15;
                                    }
                                  }
                                }
                                else
                                {
                                  v83 = (wchar_t *)CallStackTracing::s_wpInstance;
                                  if ( !CallStackTracing::s_wpInstance )
                                  {
                                    v84 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v82);
                                    CallStackTracing::s_wpInstance = v84;
                                    if ( v84
                                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v84 + 8LL))(
                                           v84,
                                           2032) )
                                    {
                                      v83 = (wchar_t *)CallStackTracing::s_wpInstance;
                                    }
                                    else
                                    {
                                      v83 = &qword_1801B07E0;
                                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                                    }
                                  }
                                  if ( *((_BYTE *)v83 + 8) )
                                  {
                                    v85 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v83);
                                    if ( *((_DWORD *)v85 + 499) != v13 )
                                      CallStackContext::TraceFailure(
                                        v85,
                                        "CMFVideoThumbnail::ConvertYUVtoRGB32",
                                        1603,
                                        v13);
                                  }
                                  if ( g_wppLevels )
                                  {
                                    v17 = 141;
                                    goto LABEL_15;
                                  }
                                }
                              }
                              else
                              {
                                v79 = (wchar_t *)CallStackTracing::s_wpInstance;
                                if ( !CallStackTracing::s_wpInstance )
                                {
                                  v80 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v78);
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
                                    CallStackContext::TraceFailure(
                                      v81,
                                      "CMFVideoThumbnail::ConvertYUVtoRGB32",
                                      1602,
                                      v13);
                                }
                                if ( g_wppLevels )
                                {
                                  v17 = 140;
                                  goto LABEL_15;
                                }
                              }
                            }
                            else
                            {
                              v75 = (wchar_t *)CallStackTracing::s_wpInstance;
                              if ( !CallStackTracing::s_wpInstance )
                              {
                                v76 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v74);
                                CallStackTracing::s_wpInstance = v76;
                                if ( v76
                                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v76 + 8LL))(
                                       v76,
                                       2032) )
                                {
                                  v75 = (wchar_t *)CallStackTracing::s_wpInstance;
                                }
                                else
                                {
                                  v75 = &qword_1801B07E0;
                                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                                }
                              }
                              if ( *((_BYTE *)v75 + 8) )
                              {
                                v77 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v75);
                                if ( *((_DWORD *)v77 + 499) != v13 )
                                  CallStackContext::TraceFailure(v77, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1601, v13);
                              }
                              if ( g_wppLevels )
                              {
                                v17 = 139;
                                goto LABEL_15;
                              }
                            }
                          }
                          else
                          {
                            v71 = (wchar_t *)CallStackTracing::s_wpInstance;
                            if ( !CallStackTracing::s_wpInstance )
                            {
                              v72 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v70);
                              CallStackTracing::s_wpInstance = v72;
                              if ( v72
                                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v72 + 8LL))(
                                     v72,
                                     2032) )
                              {
                                v71 = (wchar_t *)CallStackTracing::s_wpInstance;
                              }
                              else
                              {
                                v71 = &qword_1801B07E0;
                                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                              }
                            }
                            if ( *((_BYTE *)v71 + 8) )
                            {
                              v73 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v71);
                              if ( *((_DWORD *)v73 + 499) != v13 )
                                CallStackContext::TraceFailure(v73, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1600, v13);
                            }
                            if ( g_wppLevels )
                            {
                              v17 = 138;
                              goto LABEL_15;
                            }
                          }
                        }
                        else
                        {
                          v67 = (wchar_t *)CallStackTracing::s_wpInstance;
                          if ( !CallStackTracing::s_wpInstance )
                          {
                            v68 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v66);
                            CallStackTracing::s_wpInstance = v68;
                            if ( v68
                              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v68 + 8LL))(
                                   v68,
                                   2032) )
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
                              CallStackContext::TraceFailure(v69, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1596, v13);
                          }
                          if ( g_wppLevels )
                          {
                            v17 = 137;
                            goto LABEL_15;
                          }
                        }
                      }
                      else
                      {
                        v63 = (wchar_t *)CallStackTracing::s_wpInstance;
                        if ( !CallStackTracing::s_wpInstance )
                        {
                          v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v62);
                          CallStackTracing::s_wpInstance = v64;
                          if ( v64
                            && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(
                                 v64,
                                 2032) )
                          {
                            v63 = (wchar_t *)CallStackTracing::s_wpInstance;
                          }
                          else
                          {
                            v63 = &qword_1801B07E0;
                            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                          }
                        }
                        if ( *((_BYTE *)v63 + 8) )
                        {
                          v65 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v63);
                          if ( *((_DWORD *)v65 + 499) != v13 )
                            CallStackContext::TraceFailure(v65, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1594, v13);
                        }
                        if ( g_wppLevels )
                        {
                          v17 = 136;
                          goto LABEL_15;
                        }
                      }
                    }
                    else
                    {
                      v59 = (wchar_t *)CallStackTracing::s_wpInstance;
                      if ( !CallStackTracing::s_wpInstance )
                      {
                        v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v58);
                        CallStackTracing::s_wpInstance = v60;
                        if ( v60
                          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(
                               v60,
                               2032) )
                        {
                          v59 = (wchar_t *)CallStackTracing::s_wpInstance;
                        }
                        else
                        {
                          v59 = &qword_1801B07E0;
                          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                        }
                      }
                      if ( *((_BYTE *)v59 + 8) )
                      {
                        v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
                        if ( *((_DWORD *)v61 + 499) != v13 )
                          CallStackContext::TraceFailure(v61, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1593, v13);
                      }
                      if ( g_wppLevels )
                      {
                        v17 = 135;
                        goto LABEL_15;
                      }
                    }
                  }
                  else
                  {
                    v55 = (wchar_t *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v54);
                      CallStackTracing::s_wpInstance = v56;
                      if ( v56
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(
                             v56,
                             2032) )
                      {
                        v55 = (wchar_t *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v55 = &qword_1801B07E0;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                      }
                    }
                    if ( *((_BYTE *)v55 + 8) )
                    {
                      v57 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
                      if ( *((_DWORD *)v57 + 499) != v13 )
                        CallStackContext::TraceFailure(v57, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1592, v13);
                    }
                    if ( g_wppLevels )
                    {
                      v17 = 134;
                      goto LABEL_15;
                    }
                  }
                }
                else
                {
                  v51 = (wchar_t *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v50);
                    CallStackTracing::s_wpInstance = v52;
                    if ( v52
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
                    {
                      v51 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v51 = &qword_1801B07E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                    }
                  }
                  if ( *((_BYTE *)v51 + 8) )
                  {
                    v53 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v51);
                    if ( *((_DWORD *)v53 + 499) != v13 )
                      CallStackContext::TraceFailure(v53, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1591, v13);
                  }
                  if ( g_wppLevels )
                  {
                    v17 = 133;
                    goto LABEL_15;
                  }
                }
              }
              else
              {
                v47 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46);
                  CallStackTracing::s_wpInstance = v48;
                  if ( v48
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
                  {
                    v47 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v47 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                  }
                }
                if ( *((_BYTE *)v47 + 8) )
                {
                  v49 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
                  if ( *((_DWORD *)v49 + 499) != v13 )
                    CallStackContext::TraceFailure(v49, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1590, v13);
                }
                if ( g_wppLevels )
                {
                  v17 = 132;
                  goto LABEL_15;
                }
              }
            }
            else
            {
              v41 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40);
                CallStackTracing::s_wpInstance = v42;
                if ( v42
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
                {
                  v41 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v41 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v41 + 8) )
              {
                v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
                if ( *((_DWORD *)v43 + 499) != v13 )
                  CallStackContext::TraceFailure(v43, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1584, v13);
              }
              if ( g_wppLevels )
              {
                v17 = 131;
                goto LABEL_15;
              }
            }
          }
          else
          {
            v35 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34);
              CallStackTracing::s_wpInstance = v36;
              if ( v36
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
              {
                v35 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v35 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v35 + 8) )
            {
              v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
              if ( *((_DWORD *)v37 + 499) != v13 )
                CallStackContext::TraceFailure(v37, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1583, v13);
            }
            if ( g_wppLevels )
            {
              v17 = 130;
              goto LABEL_15;
            }
          }
        }
        else
        {
          v31 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30);
            CallStackTracing::s_wpInstance = v32;
            if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
            {
              v31 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v31 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v31 + 8) )
          {
            v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
            if ( *((_DWORD *)v33 + 499) != v13 )
              CallStackContext::TraceFailure(v33, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1581, v13);
          }
          if ( g_wppLevels )
          {
            v17 = 129;
            goto LABEL_15;
          }
        }
      }
      else
      {
        v27 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
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
            CallStackContext::TraceFailure(v29, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1580, v13);
        }
        if ( g_wppLevels )
        {
          v17 = 128;
          goto LABEL_15;
        }
      }
    }
    else
    {
      v23 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
        CallStackTracing::s_wpInstance = v24;
        if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
        {
          v23 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v23 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v23 + 8) )
      {
        v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
        if ( *((_DWORD *)v25 + 499) != v13 )
          CallStackContext::TraceFailure(v25, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1579, v13);
      }
      if ( g_wppLevels )
      {
        v17 = 127;
        goto LABEL_15;
      }
    }
  }
  else
  {
    v14 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
      CallStackTracing::s_wpInstance = v15;
      if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
      {
        v14 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v14 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v14 + 8) )
    {
      v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
      if ( *((_DWORD *)v16 + 499) != v13 )
        CallStackContext::TraceFailure(v16, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1574, v13);
    }
    if ( g_wppLevels )
    {
      v17 = 126;
LABEL_15:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, v13);
    }
  }
LABEL_206:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v95);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v104);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v107);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppIMFSample);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppBuffer);
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
