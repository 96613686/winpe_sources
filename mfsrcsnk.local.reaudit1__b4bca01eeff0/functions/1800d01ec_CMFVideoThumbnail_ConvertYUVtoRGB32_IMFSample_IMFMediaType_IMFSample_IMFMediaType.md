# CMFVideoThumbnail::ConvertYUVtoRGB32(IMFSample *,IMFMediaType *,IMFSample * *,IMFMediaType * *)

- ea: `0x1800d01ec`
- end: `0x1800d1168`
- name: `?ConvertYUVtoRGB32@CMFVideoThumbnail@@AEAAJPEAUIMFSample@@PEAUIMFMediaType@@PEAPEAU2@PEAPEAU3@@Z`
- size: `3964`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFSample *, struct IMFMediaType *, struct IMFSample **, struct IMFMediaType **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800e2cb8`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x1800790a8`
- `0x180079680`
- `0x180079a9c`
- `0x1800d01ec`
- `0x180110ed0`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d0330`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d0458`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d0517`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d05d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d0691`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d075a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d081e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d08dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d099e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d0a62`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d0b1f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d0bd8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d0c93`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d0d4e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d0e08`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d0ebf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d0f8b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d1050`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d0330`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d0458`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d0517`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d05d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d0691`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d075a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d081e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d08dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d099e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d0a62`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d0b1f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d0bd8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d0c93`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d0d4e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d0e08`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d0ebf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d0f8b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d1050`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800d0d2c`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800d0d2c`
- `MFPlat!MFCalculateImageSize` at `0x1800d0c71`
- `MFPlat!MFCalculateImageSize` at `0x1800d0c71`
- `MFPlat!MFCreateSample` at `0x1800d0de6`
- `MFPlat!MFCreateSample` at `0x1800d0de6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d030e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d030e`

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
                                        v91 = &qword_1801B97E0;
                                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                                        v87 = &qword_1801B97E0;
                                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                                      v83 = &qword_1801B97E0;
                                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                                    v79 = &qword_1801B97E0;
                                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                                  v75 = &qword_1801B97E0;
                                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                                v71 = &qword_1801B97E0;
                                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                              v67 = &qword_1801B97E0;
                              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                            v63 = &qword_1801B97E0;
                            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                          v59 = &qword_1801B97E0;
                          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                        v55 = &qword_1801B97E0;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                      v51 = &qword_1801B97E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                    v47 = &qword_1801B97E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                  v41 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                v35 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
              v31 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v27 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v23 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v14 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x1800d01ec  push    rbp
0x1800d01ee  push    rbx
0x1800d01ef  push    rsi
0x1800d01f0  push    rdi
0x1800d01f1  push    r12
0x1800d01f3  push    r13
0x1800d01f5  push    r14
0x1800d01f7  push    r15
0x1800d01f9  lea     rbp, [rsp-17h]
0x1800d01fe  sub     rsp, 0E8h
0x1800d0205  mov     rax, cs:__security_cookie
0x1800d020c  xor     rax, rsp
0x1800d020f  mov     [rbp+4Fh+var_50], rax
0x1800d0213  mov     r12, [rbp+4Fh+arg_20]
0x1800d0217  xor     edi, edi
0x1800d0219  xorps   xmm0, xmm0
0x1800d021c  mov     [rbp+4Fh+ppBuffer], rdi
0x1800d0220  movups  [rbp+4Fh+var_90], xmm0
0x1800d0224  mov     r14, r8
0x1800d0227  mov     r13, rdx
0x1800d022a  movups  [rbp+4Fh+var_80], xmm0
0x1800d022e  mov     rsi, rcx
0x1800d0231  mov     r8d, 626h; int
0x1800d0237  movups  xmm0, xmmword ptr cs:MFVideoFormat_ARGB32.Data1
0x1800d023e  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x1800d0245  mov     [rsp+120h+ppIMFSample], rdi
0x1800d024a  lea     rcx, [rsp+120h+var_F0]; this
0x1800d024f  mov     [rbp+4Fh+var_98], rdi
0x1800d0253  movdqu  xmmword ptr [rbp+4Fh+guidSubtype.Data1], xmm0
0x1800d0258  mov     r15, r9
0x1800d025b  mov     [rsp+120h+var_E0], rdi
0x1800d0260  mov     [rbp+4Fh+pcbImageSize], edi
0x1800d0263  mov     [rbp+4Fh+var_A0], edi
0x1800d0266  mov     [rsp+120h+var_E8], rdi
0x1800d026b  mov     [rbp+4Fh+var_B0], rdi
0x1800d026f  mov     [rbp+4Fh+var_C0], rdi
0x1800d0273  mov     [rbp+4Fh+unWidth], edi
0x1800d0276  mov     [rsp+120h+unHeight], edi
0x1800d027a  mov     [rbp+4Fh+var_B8], rdi
0x1800d027e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800d0283  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800d028a  cmp     [rcx+8], dil
0x1800d028e  jz      short loc_1800D02E6
0x1800d0290  cmp     [rsi+190h], rdi
0x1800d0297  jz      short loc_1800D02E6
0x1800d0299  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d029e  mov     rcx, [rsi+190h]
0x1800d02a5  mov     rdi, rax
0x1800d02a8  mov     rdx, [rcx]
0x1800d02ab  mov     rax, [rdx+128h]
0x1800d02b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d02b7  mov     rcx, [rsi+190h]
0x1800d02be  mov     ebx, eax
0x1800d02c0  mov     rdx, [rcx]
0x1800d02c3  mov     rax, [rdx+118h]
0x1800d02ca  lea     rdx, [rbp+4Fh+var_60]
0x1800d02ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d02d3  movups  xmm0, xmmword ptr [rax]
0x1800d02d6  mov     [rdi+7E0h], ebx
0x1800d02dc  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800d02e4  xor     edi, edi
0x1800d02e6  lea     rcx, [rsp+120h+var_E8]
0x1800d02eb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d02f0  xor     edx, edx; pUnkOuter
0x1800d02f2  lea     rax, [rsp+120h+var_E8]
0x1800d02f7  lea     r9, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d; riid
0x1800d02fe  mov     [rsp+120h+ppv], rax; ppv
0x1800d0303  lea     rcx, CLSID_VideoProcessorMFT; rclsid
0x1800d030a  lea     r8d, [rdx+1]; dwClsContext
0x1800d030e  call    cs:__imp_CoCreateInstance
0x1800d0315  nop     dword ptr [rax+rax+00h]
0x1800d031a  mov     ebx, eax
0x1800d031c  test    eax, eax
0x1800d031e  jns     loc_1800D03D7
0x1800d0324  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d032b  test    rcx, rcx
0x1800d032e  jnz     short loc_1800D0377
0x1800d0330  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d0337  nop     dword ptr [rax+rax+00h]
0x1800d033c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d0343  mov     rcx, rax
0x1800d0346  test    rax, rax
0x1800d0349  jz      short loc_1800D0369
0x1800d034b  mov     rax, [rax]
0x1800d034e  mov     edx, 7F0h
0x1800d0353  mov     rax, [rax+8]
0x1800d0357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d035c  test    eax, eax
0x1800d035e  jz      short loc_1800D0369
0x1800d0360  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d0367  jmp     short loc_1800D0377
0x1800d0369  lea     rcx, qword_1801B97E0; this
0x1800d0370  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d0377  cmp     [rcx+8], dil
0x1800d037b  jz      short loc_1800D03A2
0x1800d037d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d0382  cmp     [rax+7CCh], ebx
0x1800d0388  jz      short loc_1800D03A2
0x1800d038a  mov     r9d, ebx; int
0x1800d038d  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x1800d0394  mov     r8d, 626h; int
0x1800d039a  mov     rcx, rax; this
0x1800d039d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d03a2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d03a9  jb      loc_1800D10F0
0x1800d03af  mov     edx, 7Eh ; '~'
0x1800d03b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d03bb  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x1800d03c2  mov     r9, rsi
0x1800d03c5  mov     dword ptr [rsp+120h+ppv], ebx
0x1800d03c9  mov     rcx, [rcx+10h]
0x1800d03cd  call    WPP_SF_qD
0x1800d03d2  jmp     loc_1800D10F0
0x1800d03d7  mov     rbx, [rsp+120h+var_E8]
0x1800d03dc  lea     rcx, [rbp+4Fh+var_B8]
0x1800d03e0  mov     rax, [rbx]
0x1800d03e3  mov     rdi, [rax]
0x1800d03e6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d03eb  lea     r8, [rbp+4Fh+var_B8]
0x1800d03ef  mov     rcx, rbx
0x1800d03f2  lea     rdx, _GUID_0b5e1c7e_bd76_46bc_896c_b2edb40dd803
0x1800d03f9  mov     rax, rdi
0x1800d03fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0401  test    eax, eax
0x1800d0403  js      short loc_1800D041C
0x1800d0405  mov     rcx, [rbp+4Fh+var_B8]
0x1800d0409  mov     rdx, [rsi+190h]
0x1800d0410  mov     rax, [rcx]
0x1800d0413  mov     rax, [rax+20h]
0x1800d0417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d041c  mov     rdi, [rsp+120h+var_E8]
0x1800d0421  lea     rcx, [rbp+4Fh+var_C0]
0x1800d0425  mov     rax, [rdi]
0x1800d0428  mov     rbx, [rax+40h]
0x1800d042c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d0431  lea     rdx, [rbp+4Fh+var_C0]
0x1800d0435  mov     rcx, rdi
0x1800d0438  mov     rax, rbx
0x1800d043b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0440  xor     edi, edi
0x1800d0442  mov     ebx, eax
0x1800d0444  test    eax, eax
0x1800d0446  jns     loc_1800D04E1
0x1800d044c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d0453  test    rcx, rcx
0x1800d0456  jnz     short loc_1800D049F
0x1800d0458  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d045f  nop     dword ptr [rax+rax+00h]
0x1800d0464  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d046b  mov     rcx, rax
0x1800d046e  test    rax, rax
0x1800d0471  jz      short loc_1800D0491
0x1800d0473  mov     rax, [rax]
0x1800d0476  mov     edx, 7F0h
0x1800d047b  mov     rax, [rax+8]
0x1800d047f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0484  test    eax, eax
0x1800d0486  jz      short loc_1800D0491
0x1800d0488  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d048f  jmp     short loc_1800D049F
0x1800d0491  lea     rcx, qword_1801B97E0; this
0x1800d0498  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d049f  cmp     [rcx+8], dil
0x1800d04a3  jz      short loc_1800D04CA
0x1800d04a5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d04aa  cmp     [rax+7CCh], ebx
0x1800d04b0  jz      short loc_1800D04CA
0x1800d04b2  mov     r9d, ebx; int
0x1800d04b5  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x1800d04bc  mov     r8d, 62Bh; int
0x1800d04c2  mov     rcx, rax; this
0x1800d04c5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d04ca  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d04d1  jb      loc_1800D10F0
0x1800d04d7  mov     edx, 7Fh
0x1800d04dc  jmp     loc_1800D03B4
0x1800d04e1  mov     rcx, [rbp+4Fh+var_C0]
0x1800d04e5  lea     rdx, MF_XVP_DISABLE_FRC
0x1800d04ec  mov     r8d, 1
0x1800d04f2  mov     rax, [rcx]
0x1800d04f5  mov     rax, [rax+0A8h]
0x1800d04fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0501  mov     ebx, eax
0x1800d0503  test    eax, eax
0x1800d0505  jns     loc_1800D05A0
0x1800d050b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d0512  test    rcx, rcx
0x1800d0515  jnz     short loc_1800D055E
0x1800d0517  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d051e  nop     dword ptr [rax+rax+00h]
0x1800d0523  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d052a  mov     rcx, rax
0x1800d052d  test    rax, rax
0x1800d0530  jz      short loc_1800D0550
0x1800d0532  mov     rax, [rax]
0x1800d0535  mov     edx, 7F0h
0x1800d053a  mov     rax, [rax+8]
0x1800d053e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0543  test    eax, eax
0x1800d0545  jz      short loc_1800D0550
0x1800d0547  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d054e  jmp     short loc_1800D055E
0x1800d0550  lea     rcx, qword_1801B97E0; this
0x1800d0557  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d055e  cmp     [rcx+8], dil
0x1800d0562  jz      short loc_1800D0589
0x1800d0564  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d0569  cmp     [rax+7CCh], ebx
0x1800d056f  jz      short loc_1800D0589
0x1800d0571  mov     r9d, ebx; int
0x1800d0574  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x1800d057b  mov     r8d, 62Ch; int
0x1800d0581  mov     rcx, rax; this
0x1800d0584  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d0589  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d0590  jb      loc_1800D10F0
0x1800d0596  mov     edx, 80h
0x1800d059b  jmp     loc_1800D03B4
0x1800d05a0  mov     rcx, [rbp+4Fh+var_C0]
0x1800d05a4  lea     rdx, _GUID_2efd8eee_1150_4328_9cf5_66dce933fcf4
0x1800d05ab  mov     r8d, 1
0x1800d05b1  mov     rax, [rcx]
0x1800d05b4  mov     rax, [rax+0A8h]
0x1800d05bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d05c0  mov     ebx, eax
0x1800d05c2  test    eax, eax
0x1800d05c4  jns     loc_1800D065F
0x1800d05ca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d05d1  test    rcx, rcx
0x1800d05d4  jnz     short loc_1800D061D
0x1800d05d6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d05dd  nop     dword ptr [rax+rax+00h]
0x1800d05e2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d05e9  mov     rcx, rax
0x1800d05ec  test    rax, rax
0x1800d05ef  jz      short loc_1800D060F
0x1800d05f1  mov     rax, [rax]
0x1800d05f4  mov     edx, 7F0h
0x1800d05f9  mov     rax, [rax+8]
0x1800d05fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0602  test    eax, eax
0x1800d0604  jz      short loc_1800D060F
0x1800d0606  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d060d  jmp     short loc_1800D061D
0x1800d060f  lea     rcx, qword_1801B97E0; this
0x1800d0616  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d061d  cmp     [rcx+8], dil
0x1800d0621  jz      short loc_1800D0648
0x1800d0623  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d0628  cmp     [rax+7CCh], ebx
0x1800d062e  jz      short loc_1800D0648
0x1800d0630  mov     r9d, ebx; int
0x1800d0633  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x1800d063a  mov     r8d, 62Dh; int
0x1800d0640  mov     rcx, rax; this
0x1800d0643  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d0648  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d064f  jb      loc_1800D10F0
0x1800d0655  mov     edx, 81h
0x1800d065a  jmp     loc_1800D03B4
0x1800d065f  mov     rcx, [rsp+120h+var_E8]
0x1800d0664  xor     r9d, r9d
0x1800d0667  mov     r8, r14
0x1800d066a  xor     edx, edx
0x1800d066c  mov     rax, [rcx]
0x1800d066f  mov     rax, [rax+78h]
0x1800d0673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0678  xor     r14d, r14d
0x1800d067b  mov     ebx, eax
0x1800d067d  test    eax, eax
0x1800d067f  jns     loc_1800D071A
0x1800d0685  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d068c  test    rcx, rcx
0x1800d068f  jnz     short loc_1800D06D8
0x1800d0691  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d0698  nop     dword ptr [rax+rax+00h]
0x1800d069d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d06a4  mov     rcx, rax
0x1800d06a7  test    rax, rax
0x1800d06aa  jz      short loc_1800D06CA
0x1800d06ac  mov     rax, [rax]
0x1800d06af  mov     edx, 7F0h
0x1800d06b4  mov     rax, [rax+8]
0x1800d06b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d06bd  test    eax, eax
0x1800d06bf  jz      short loc_1800D06CA
0x1800d06c1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d06c8  jmp     short loc_1800D06D8
0x1800d06ca  lea     rcx, qword_1801B97E0; this
0x1800d06d1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d06d8  cmp     [rcx+8], r14b
0x1800d06dc  jz      short loc_1800D0703
0x1800d06de  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d06e3  cmp     [rax+7CCh], ebx
0x1800d06e9  jz      short loc_1800D0703
0x1800d06eb  mov     r9d, ebx; int
0x1800d06ee  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x1800d06f5  mov     r8d, 62Fh; int
0x1800d06fb  mov     rcx, rax; this
0x1800d06fe  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
  ... truncated ...
```
