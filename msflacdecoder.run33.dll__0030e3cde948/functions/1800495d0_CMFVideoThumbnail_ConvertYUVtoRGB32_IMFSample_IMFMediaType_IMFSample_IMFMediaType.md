# CMFVideoThumbnail::ConvertYUVtoRGB32(IMFSample *,IMFMediaType *,IMFSample * *,IMFMediaType * *)

- ea: `0x1800495d0`
- end: `0x18004a4d1`
- name: `?ConvertYUVtoRGB32@CMFVideoThumbnail@@AEAAJPEAUIMFSample@@PEAUIMFMediaType@@PEAPEAU2@PEAPEAU3@@Z`
- size: `3841`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFSample *, struct IMFMediaType *, struct IMFSample **, struct IMFMediaType **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004e1fc`

## callees

- `0x180001e80`
- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x1800462a0`
- `0x180048710`
- `0x1800495d0`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800496f2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800496f2`
- `MFPlat!MFCalculateImageSize` at `0x18004a00b`
- `MFPlat!MFCalculateImageSize` at `0x18004a00b`
- `MFPlat!MFCreateMemoryBuffer` at `0x18004a0bb`
- `MFPlat!MFCreateMemoryBuffer` at `0x18004a0bb`
- `MFPlat!MFCreateSample` at `0x18004a16a`
- `MFPlat!MFCreateSample` at `0x18004a16a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004970e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049830`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800498e9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800499a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049a57`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049b1a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049bd8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049c90`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049d4c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049e0b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049ec3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049f77`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a027`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a0d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a186`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a238`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a2ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a3bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004970e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049830`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800498e9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800499a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049a57`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049b1a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049bd8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049c90`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049d4c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049e0b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049ec3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049f77`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a027`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a0d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a186`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a238`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a2ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a3bf`

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
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  LPVOID v18; // rbx
  int (__fastcall *v19)(LPVOID, GUID *, __int64 *); // rdi
  LPVOID v20; // rdi
  __int64 (__fastcall *v21)(LPVOID, __int64 *); // rbx
  __int64 v22; // rdx
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  LPVOID v38; // rdi
  __int64 (__fastcall *v39)(LPVOID, GUID *, __int64 *); // rbx
  __int64 v40; // rdx
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 v44; // rdi
  __int64 (__fastcall *v45)(__int64, struct IMFMediaType **); // rbx
  __int64 v46; // rdx
  __int64 *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  __int64 v50; // rdx
  __int64 *v51; // rcx
  CallStackTracing *v52; // rax
  struct CallStackContext *v53; // rax
  __int64 v54; // rdx
  __int64 *v55; // rcx
  CallStackTracing *v56; // rax
  struct CallStackContext *v57; // rax
  __int64 v58; // rdx
  __int64 *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  __int64 v62; // rdx
  __int64 *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  __int64 v66; // rdx
  __int64 *v67; // rcx
  CallStackTracing *v68; // rax
  struct CallStackContext *v69; // rax
  __int64 v70; // rdx
  __int64 *v71; // rcx
  CallStackTracing *v72; // rax
  struct CallStackContext *v73; // rax
  __int64 v74; // rdx
  __int64 *v75; // rcx
  CallStackTracing *v76; // rax
  struct CallStackContext *v77; // rax
  __int64 v78; // rdx
  __int64 *v79; // rcx
  CallStackTracing *v80; // rax
  struct CallStackContext *v81; // rax
  __int64 v82; // rdx
  __int64 *v83; // rcx
  CallStackTracing *v84; // rax
  struct CallStackContext *v85; // rax
  __int64 v86; // rdx
  __int64 *v87; // rcx
  CallStackTracing *v88; // rax
  struct CallStackContext *v89; // rax
  __int64 v90; // rdx
  __int64 *v91; // rcx
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
                                    v91 = (__int64 *)CallStackTracing::s_wpInstance;
                                    if ( !CallStackTracing::s_wpInstance )
                                    {
                                      v92 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v90);
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
                                        v91 = &qword_18006EB20;
                                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
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
                                    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                                    {
                                      v17 = 143;
                                      goto LABEL_15;
                                    }
                                  }
                                  else
                                  {
                                    v87 = (__int64 *)CallStackTracing::s_wpInstance;
                                    if ( !CallStackTracing::s_wpInstance )
                                    {
                                      v88 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v86);
                                      CallStackTracing::s_wpInstance = v88;
                                      if ( v88
                                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v88 + 8LL))(
                                             v88,
                                             2032) )
                                      {
                                        v87 = (__int64 *)CallStackTracing::s_wpInstance;
                                      }
                                      else
                                      {
                                        v87 = &qword_18006EB20;
                                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
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
                                    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                                    {
                                      v17 = 142;
                                      goto LABEL_15;
                                    }
                                  }
                                }
                                else
                                {
                                  v83 = (__int64 *)CallStackTracing::s_wpInstance;
                                  if ( !CallStackTracing::s_wpInstance )
                                  {
                                    v84 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v82);
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
                                      v83 = &qword_18006EB20;
                                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
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
                                  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                                  {
                                    v17 = 141;
                                    goto LABEL_15;
                                  }
                                }
                              }
                              else
                              {
                                v79 = (__int64 *)CallStackTracing::s_wpInstance;
                                if ( !CallStackTracing::s_wpInstance )
                                {
                                  v80 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v78);
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
                                    v79 = &qword_18006EB20;
                                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
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
                                if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                                {
                                  v17 = 140;
                                  goto LABEL_15;
                                }
                              }
                            }
                            else
                            {
                              v75 = (__int64 *)CallStackTracing::s_wpInstance;
                              if ( !CallStackTracing::s_wpInstance )
                              {
                                v76 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v74);
                                CallStackTracing::s_wpInstance = v76;
                                if ( v76
                                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v76 + 8LL))(
                                       v76,
                                       2032) )
                                {
                                  v75 = (__int64 *)CallStackTracing::s_wpInstance;
                                }
                                else
                                {
                                  v75 = &qword_18006EB20;
                                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                                }
                              }
                              if ( *((_BYTE *)v75 + 8) )
                              {
                                v77 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v75);
                                if ( *((_DWORD *)v77 + 499) != v13 )
                                  CallStackContext::TraceFailure(v77, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1601, v13);
                              }
                              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                              {
                                v17 = 139;
                                goto LABEL_15;
                              }
                            }
                          }
                          else
                          {
                            v71 = (__int64 *)CallStackTracing::s_wpInstance;
                            if ( !CallStackTracing::s_wpInstance )
                            {
                              v72 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v70);
                              CallStackTracing::s_wpInstance = v72;
                              if ( v72
                                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v72 + 8LL))(
                                     v72,
                                     2032) )
                              {
                                v71 = (__int64 *)CallStackTracing::s_wpInstance;
                              }
                              else
                              {
                                v71 = &qword_18006EB20;
                                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                              }
                            }
                            if ( *((_BYTE *)v71 + 8) )
                            {
                              v73 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v71);
                              if ( *((_DWORD *)v73 + 499) != v13 )
                                CallStackContext::TraceFailure(v73, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1600, v13);
                            }
                            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                            {
                              v17 = 138;
                              goto LABEL_15;
                            }
                          }
                        }
                        else
                        {
                          v67 = (__int64 *)CallStackTracing::s_wpInstance;
                          if ( !CallStackTracing::s_wpInstance )
                          {
                            v68 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v66);
                            CallStackTracing::s_wpInstance = v68;
                            if ( v68
                              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v68 + 8LL))(
                                   v68,
                                   2032) )
                            {
                              v67 = (__int64 *)CallStackTracing::s_wpInstance;
                            }
                            else
                            {
                              v67 = &qword_18006EB20;
                              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                            }
                          }
                          if ( *((_BYTE *)v67 + 8) )
                          {
                            v69 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v67);
                            if ( *((_DWORD *)v69 + 499) != v13 )
                              CallStackContext::TraceFailure(v69, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1596, v13);
                          }
                          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                          {
                            v17 = 137;
                            goto LABEL_15;
                          }
                        }
                      }
                      else
                      {
                        v63 = (__int64 *)CallStackTracing::s_wpInstance;
                        if ( !CallStackTracing::s_wpInstance )
                        {
                          v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v62);
                          CallStackTracing::s_wpInstance = v64;
                          if ( v64
                            && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(
                                 v64,
                                 2032) )
                          {
                            v63 = (__int64 *)CallStackTracing::s_wpInstance;
                          }
                          else
                          {
                            v63 = &qword_18006EB20;
                            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                          }
                        }
                        if ( *((_BYTE *)v63 + 8) )
                        {
                          v65 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v63);
                          if ( *((_DWORD *)v65 + 499) != v13 )
                            CallStackContext::TraceFailure(v65, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1594, v13);
                        }
                        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                        {
                          v17 = 136;
                          goto LABEL_15;
                        }
                      }
                    }
                    else
                    {
                      v59 = (__int64 *)CallStackTracing::s_wpInstance;
                      if ( !CallStackTracing::s_wpInstance )
                      {
                        v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v58);
                        CallStackTracing::s_wpInstance = v60;
                        if ( v60
                          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(
                               v60,
                               2032) )
                        {
                          v59 = (__int64 *)CallStackTracing::s_wpInstance;
                        }
                        else
                        {
                          v59 = &qword_18006EB20;
                          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                        }
                      }
                      if ( *((_BYTE *)v59 + 8) )
                      {
                        v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
                        if ( *((_DWORD *)v61 + 499) != v13 )
                          CallStackContext::TraceFailure(v61, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1593, v13);
                      }
                      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                      {
                        v17 = 135;
                        goto LABEL_15;
                      }
                    }
                  }
                  else
                  {
                    v55 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v54);
                      CallStackTracing::s_wpInstance = v56;
                      if ( v56
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(
                             v56,
                             2032) )
                      {
                        v55 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v55 = &qword_18006EB20;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                      }
                    }
                    if ( *((_BYTE *)v55 + 8) )
                    {
                      v57 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
                      if ( *((_DWORD *)v57 + 499) != v13 )
                        CallStackContext::TraceFailure(v57, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1592, v13);
                    }
                    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                    {
                      v17 = 134;
                      goto LABEL_15;
                    }
                  }
                }
                else
                {
                  v51 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v50);
                    CallStackTracing::s_wpInstance = v52;
                    if ( v52
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
                    {
                      v51 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v51 = &qword_18006EB20;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                    }
                  }
                  if ( *((_BYTE *)v51 + 8) )
                  {
                    v53 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v51);
                    if ( *((_DWORD *)v53 + 499) != v13 )
                      CallStackContext::TraceFailure(v53, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1591, v13);
                  }
                  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  {
                    v17 = 133;
                    goto LABEL_15;
                  }
                }
              }
              else
              {
                v47 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46);
                  CallStackTracing::s_wpInstance = v48;
                  if ( v48
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
                  {
                    v47 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v47 = &qword_18006EB20;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                  }
                }
                if ( *((_BYTE *)v47 + 8) )
                {
                  v49 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
                  if ( *((_DWORD *)v49 + 499) != v13 )
                    CallStackContext::TraceFailure(v49, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1590, v13);
                }
                if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                {
                  v17 = 132;
                  goto LABEL_15;
                }
              }
            }
            else
            {
              v41 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40);
                CallStackTracing::s_wpInstance = v42;
                if ( v42
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
                {
                  v41 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v41 = &qword_18006EB20;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                }
              }
              if ( *((_BYTE *)v41 + 8) )
              {
                v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
                if ( *((_DWORD *)v43 + 499) != v13 )
                  CallStackContext::TraceFailure(v43, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1584, v13);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v17 = 131;
                goto LABEL_15;
              }
            }
          }
          else
          {
            v35 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34);
              CallStackTracing::s_wpInstance = v36;
              if ( v36
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
              {
                v35 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v35 = &qword_18006EB20;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
              }
            }
            if ( *((_BYTE *)v35 + 8) )
            {
              v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
              if ( *((_DWORD *)v37 + 499) != v13 )
                CallStackContext::TraceFailure(v37, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1583, v13);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v17 = 130;
              goto LABEL_15;
            }
          }
        }
        else
        {
          v31 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30);
            CallStackTracing::s_wpInstance = v32;
            if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
            {
              v31 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v31 = &qword_18006EB20;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
            }
          }
          if ( *((_BYTE *)v31 + 8) )
          {
            v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
            if ( *((_DWORD *)v33 + 499) != v13 )
              CallStackContext::TraceFailure(v33, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1581, v13);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v17 = 129;
            goto LABEL_15;
          }
        }
      }
      else
      {
        v27 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
          CallStackTracing::s_wpInstance = v28;
          if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
          {
            v27 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v27 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v27 + 8) )
        {
          v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
          if ( *((_DWORD *)v29 + 499) != v13 )
            CallStackContext::TraceFailure(v29, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1580, v13);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v17 = 128;
          goto LABEL_15;
        }
      }
    }
    else
    {
      v23 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
        CallStackTracing::s_wpInstance = v24;
        if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
        {
          v23 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v23 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v23 + 8) )
      {
        v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
        if ( *((_DWORD *)v25 + 499) != v13 )
          CallStackContext::TraceFailure(v25, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1579, v13);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v17 = 127;
        goto LABEL_15;
      }
    }
  }
  else
  {
    v14 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
      CallStackTracing::s_wpInstance = v15;
      if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
      {
        v14 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v14 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v14 + 8) )
    {
      v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
      if ( *((_DWORD *)v16 + 499) != v13 )
        CallStackContext::TraceFailure(v16, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1574, v13);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v17 = 126;
LABEL_15:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, v13);
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
0x1800495d0  push    rbp
0x1800495d2  push    rbx
0x1800495d3  push    rsi
0x1800495d4  push    rdi
0x1800495d5  push    r12
0x1800495d7  push    r13
0x1800495d9  push    r14
0x1800495db  push    r15
0x1800495dd  lea     rbp, [rsp-17h]
0x1800495e2  sub     rsp, 0E8h
0x1800495e9  mov     rax, cs:__security_cookie
0x1800495f0  xor     rax, rsp
0x1800495f3  mov     [rbp+4Fh+var_50], rax
0x1800495f7  mov     r12, [rbp+4Fh+arg_20]
0x1800495fb  xor     edi, edi
0x1800495fd  xorps   xmm0, xmm0
0x180049600  mov     [rbp+4Fh+ppBuffer], rdi
0x180049604  movups  [rbp+4Fh+var_90], xmm0
0x180049608  mov     r14, r8
0x18004960b  mov     r13, rdx
0x18004960e  movups  [rbp+4Fh+var_80], xmm0
0x180049612  mov     rsi, rcx
0x180049615  mov     r8d, 626h; int
0x18004961b  movups  xmm0, xmmword ptr cs:MFVideoFormat_ARGB32.Data1
0x180049622  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x180049629  mov     [rsp+120h+ppIMFSample], rdi
0x18004962e  lea     rcx, [rsp+120h+var_F0]; this
0x180049633  mov     [rbp+4Fh+var_98], rdi
0x180049637  movdqu  xmmword ptr [rbp+4Fh+guidSubtype.Data1], xmm0
0x18004963c  mov     r15, r9
0x18004963f  mov     [rsp+120h+var_E0], rdi
0x180049644  mov     [rbp+4Fh+pcbImageSize], edi
0x180049647  mov     [rbp+4Fh+var_A0], edi
0x18004964a  mov     [rsp+120h+var_E8], rdi
0x18004964f  mov     [rbp+4Fh+var_B0], rdi
0x180049653  mov     [rbp+4Fh+var_C0], rdi
0x180049657  mov     [rbp+4Fh+unWidth], edi
0x18004965a  mov     [rsp+120h+unHeight], edi
0x18004965e  mov     [rbp+4Fh+var_B8], rdi
0x180049662  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180049667  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004966e  cmp     [rcx+8], dil
0x180049672  jz      short loc_1800496CA
0x180049674  cmp     [rsi+190h], rdi
0x18004967b  jz      short loc_1800496CA
0x18004967d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180049682  mov     rcx, [rsi+190h]
0x180049689  mov     rdi, rax
0x18004968c  mov     rdx, [rcx]
0x18004968f  mov     rax, [rdx+128h]
0x180049696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004969b  mov     rcx, [rsi+190h]
0x1800496a2  mov     ebx, eax
0x1800496a4  mov     rdx, [rcx]
0x1800496a7  mov     rax, [rdx+118h]
0x1800496ae  lea     rdx, [rbp+4Fh+var_60]
0x1800496b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800496b7  movups  xmm0, xmmword ptr [rax]
0x1800496ba  mov     [rdi+7E0h], ebx
0x1800496c0  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800496c8  xor     edi, edi
0x1800496ca  lea     rcx, [rsp+120h+var_E8]
0x1800496cf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800496d4  xor     edx, edx; pUnkOuter
0x1800496d6  lea     rax, [rsp+120h+var_E8]
0x1800496db  lea     r9, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d; riid
0x1800496e2  mov     [rsp+120h+ppv], rax; ppv
0x1800496e7  lea     rcx, CLSID_VideoProcessorMFT; rclsid
0x1800496ee  lea     r8d, [rdx+1]; dwClsContext
0x1800496f2  call    cs:__imp_CoCreateInstance
0x1800496f8  mov     ebx, eax
0x1800496fa  test    eax, eax
0x1800496fc  jns     loc_1800497AF
0x180049702  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180049709  test    rcx, rcx
0x18004970c  jnz     short loc_18004974F
0x18004970e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180049714  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004971b  mov     rcx, rax
0x18004971e  test    rax, rax
0x180049721  jz      short loc_180049741
0x180049723  mov     rax, [rax]
0x180049726  mov     edx, 7F0h
0x18004972b  mov     rax, [rax+8]
0x18004972f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049734  test    eax, eax
0x180049736  jz      short loc_180049741
0x180049738  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004973f  jmp     short loc_18004974F
0x180049741  lea     rcx, qword_18006EB20; this
0x180049748  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004974f  cmp     [rcx+8], dil
0x180049753  jz      short loc_18004977A
0x180049755  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004975a  cmp     [rax+7CCh], ebx
0x180049760  jz      short loc_18004977A
0x180049762  mov     r9d, ebx; int
0x180049765  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x18004976c  mov     r8d, 626h; int
0x180049772  mov     rcx, rax; this
0x180049775  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004977a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004977f  cmp     al, 1
0x180049781  jb      loc_18004A45A
0x180049787  mov     edx, 7Eh ; '~'
0x18004978c  mov     rcx, cs:WPP_GLOBAL_Control
0x180049793  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x18004979a  mov     r9, rsi
0x18004979d  mov     dword ptr [rsp+120h+ppv], ebx
0x1800497a1  mov     rcx, [rcx+10h]
0x1800497a5  call    WPP_SF_qd
0x1800497aa  jmp     loc_18004A45A
0x1800497af  mov     rbx, [rsp+120h+var_E8]
0x1800497b4  lea     rcx, [rbp+4Fh+var_B8]
0x1800497b8  mov     rax, [rbx]
0x1800497bb  mov     rdi, [rax]
0x1800497be  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800497c3  lea     r8, [rbp+4Fh+var_B8]
0x1800497c7  mov     rcx, rbx
0x1800497ca  lea     rdx, _GUID_0b5e1c7e_bd76_46bc_896c_b2edb40dd803
0x1800497d1  mov     rax, rdi
0x1800497d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800497d9  test    eax, eax
0x1800497db  js      short loc_1800497F4
0x1800497dd  mov     rcx, [rbp+4Fh+var_B8]
0x1800497e1  mov     rdx, [rsi+190h]
0x1800497e8  mov     rax, [rcx]
0x1800497eb  mov     rax, [rax+20h]
0x1800497ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800497f4  mov     rdi, [rsp+120h+var_E8]
0x1800497f9  lea     rcx, [rbp+4Fh+var_C0]
0x1800497fd  mov     rax, [rdi]
0x180049800  mov     rbx, [rax+40h]
0x180049804  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180049809  lea     rdx, [rbp+4Fh+var_C0]
0x18004980d  mov     rcx, rdi
0x180049810  mov     rax, rbx
0x180049813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049818  xor     edi, edi
0x18004981a  mov     ebx, eax
0x18004981c  test    eax, eax
0x18004981e  jns     loc_1800498B3
0x180049824  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004982b  test    rcx, rcx
0x18004982e  jnz     short loc_180049871
0x180049830  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180049836  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004983d  mov     rcx, rax
0x180049840  test    rax, rax
0x180049843  jz      short loc_180049863
0x180049845  mov     rax, [rax]
0x180049848  mov     edx, 7F0h
0x18004984d  mov     rax, [rax+8]
0x180049851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049856  test    eax, eax
0x180049858  jz      short loc_180049863
0x18004985a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180049861  jmp     short loc_180049871
0x180049863  lea     rcx, qword_18006EB20; this
0x18004986a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180049871  cmp     [rcx+8], dil
0x180049875  jz      short loc_18004989C
0x180049877  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004987c  cmp     [rax+7CCh], ebx
0x180049882  jz      short loc_18004989C
0x180049884  mov     r9d, ebx; int
0x180049887  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x18004988e  mov     r8d, 62Bh; int
0x180049894  mov     rcx, rax; this
0x180049897  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004989c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800498a1  cmp     al, 1
0x1800498a3  jb      loc_18004A45A
0x1800498a9  mov     edx, 7Fh
0x1800498ae  jmp     loc_18004978C
0x1800498b3  mov     rcx, [rbp+4Fh+var_C0]
0x1800498b7  lea     rdx, MF_XVP_DISABLE_FRC
0x1800498be  mov     r8d, 1
0x1800498c4  mov     rax, [rcx]
0x1800498c7  mov     rax, [rax+0A8h]
0x1800498ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800498d3  mov     ebx, eax
0x1800498d5  test    eax, eax
0x1800498d7  jns     loc_18004996C
0x1800498dd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800498e4  test    rcx, rcx
0x1800498e7  jnz     short loc_18004992A
0x1800498e9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800498ef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800498f6  mov     rcx, rax
0x1800498f9  test    rax, rax
0x1800498fc  jz      short loc_18004991C
0x1800498fe  mov     rax, [rax]
0x180049901  mov     edx, 7F0h
0x180049906  mov     rax, [rax+8]
0x18004990a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004990f  test    eax, eax
0x180049911  jz      short loc_18004991C
0x180049913  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004991a  jmp     short loc_18004992A
0x18004991c  lea     rcx, qword_18006EB20; this
0x180049923  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004992a  cmp     [rcx+8], dil
0x18004992e  jz      short loc_180049955
0x180049930  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180049935  cmp     [rax+7CCh], ebx
0x18004993b  jz      short loc_180049955
0x18004993d  mov     r9d, ebx; int
0x180049940  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x180049947  mov     r8d, 62Ch; int
0x18004994d  mov     rcx, rax; this
0x180049950  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180049955  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004995a  cmp     al, 1
0x18004995c  jb      loc_18004A45A
0x180049962  mov     edx, 80h
0x180049967  jmp     loc_18004978C
0x18004996c  mov     rcx, [rbp+4Fh+var_C0]
0x180049970  lea     rdx, _GUID_2efd8eee_1150_4328_9cf5_66dce933fcf4
0x180049977  mov     r8d, 1
0x18004997d  mov     rax, [rcx]
0x180049980  mov     rax, [rax+0A8h]
0x180049987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004998c  mov     ebx, eax
0x18004998e  test    eax, eax
0x180049990  jns     loc_180049A25
0x180049996  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004999d  test    rcx, rcx
0x1800499a0  jnz     short loc_1800499E3
0x1800499a2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800499a8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800499af  mov     rcx, rax
0x1800499b2  test    rax, rax
0x1800499b5  jz      short loc_1800499D5
0x1800499b7  mov     rax, [rax]
0x1800499ba  mov     edx, 7F0h
0x1800499bf  mov     rax, [rax+8]
0x1800499c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800499c8  test    eax, eax
0x1800499ca  jz      short loc_1800499D5
0x1800499cc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800499d3  jmp     short loc_1800499E3
0x1800499d5  lea     rcx, qword_18006EB20; this
0x1800499dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800499e3  cmp     [rcx+8], dil
0x1800499e7  jz      short loc_180049A0E
0x1800499e9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800499ee  cmp     [rax+7CCh], ebx
0x1800499f4  jz      short loc_180049A0E
0x1800499f6  mov     r9d, ebx; int
0x1800499f9  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x180049a00  mov     r8d, 62Dh; int
0x180049a06  mov     rcx, rax; this
0x180049a09  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180049a0e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180049a13  cmp     al, 1
0x180049a15  jb      loc_18004A45A
0x180049a1b  mov     edx, 81h
0x180049a20  jmp     loc_18004978C
0x180049a25  mov     rcx, [rsp+120h+var_E8]
0x180049a2a  xor     r9d, r9d
0x180049a2d  mov     r8, r14
0x180049a30  xor     edx, edx
0x180049a32  mov     rax, [rcx]
0x180049a35  mov     rax, [rax+78h]
0x180049a39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049a3e  xor     r14d, r14d
0x180049a41  mov     ebx, eax
0x180049a43  test    eax, eax
0x180049a45  jns     loc_180049ADA
0x180049a4b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180049a52  test    rcx, rcx
0x180049a55  jnz     short loc_180049A98
0x180049a57  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180049a5d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180049a64  mov     rcx, rax
0x180049a67  test    rax, rax
0x180049a6a  jz      short loc_180049A8A
0x180049a6c  mov     rax, [rax]
0x180049a6f  mov     edx, 7F0h
0x180049a74  mov     rax, [rax+8]
0x180049a78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049a7d  test    eax, eax
0x180049a7f  jz      short loc_180049A8A
0x180049a81  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180049a88  jmp     short loc_180049A98
0x180049a8a  lea     rcx, qword_18006EB20; this
0x180049a91  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180049a98  cmp     [rcx+8], r14b
0x180049a9c  jz      short loc_180049AC3
0x180049a9e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180049aa3  cmp     [rax+7CCh], ebx
0x180049aa9  jz      short loc_180049AC3
0x180049aab  mov     r9d, ebx; int
0x180049aae  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x180049ab5  mov     r8d, 62Fh; int
0x180049abb  mov     rcx, rax; this
0x180049abe  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180049ac3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180049ac8  cmp     al, 1
  ... truncated ...
```
