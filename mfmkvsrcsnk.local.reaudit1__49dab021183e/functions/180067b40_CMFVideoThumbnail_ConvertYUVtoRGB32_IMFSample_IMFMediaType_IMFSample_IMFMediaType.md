# CMFVideoThumbnail::ConvertYUVtoRGB32(IMFSample *,IMFMediaType *,IMFSample * *,IMFMediaType * *)

- ea: `0x180067b40`
- end: `0x180068abc`
- name: `?ConvertYUVtoRGB32@CMFVideoThumbnail@@AEAAJPEAUIMFSample@@PEAUIMFMediaType@@PEAPEAU2@PEAPEAU3@@Z`
- size: `3964`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFSample *, struct IMFMediaType *, struct IMFSample **, struct IMFMediaType **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006c8f0`

## callees

- `0x180002400`
- `0x180005c68`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180053ff8`
- `0x180067b40`
- `0x18006c764`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180067c62`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180067c62`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067c84`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067dac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067e6b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067f2a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067fe5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800680ae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180068172`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180068230`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800682f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800683b6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180068473`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006852c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800685e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800686a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006875c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180068813`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800688df`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800689a4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067c84`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067dac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067e6b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067f2a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067fe5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800680ae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180068172`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180068230`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800682f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800683b6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180068473`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006852c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800685e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800686a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006875c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180068813`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800688df`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800689a4`
- `MFPlat!MFCreateSample` at `0x18006873a`
- `MFPlat!MFCreateSample` at `0x18006873a`
- `MFPlat!MFCalculateImageSize` at `0x1800685c5`
- `MFPlat!MFCalculateImageSize` at `0x1800685c5`
- `MFPlat!MFCreateMemoryBuffer` at `0x180068680`
- `MFPlat!MFCreateMemoryBuffer` at `0x180068680`

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
                                        v127 = &qword_1800DBF70;
                                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                                        v121 = &qword_1800DBF70;
                                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                                      v115 = &qword_1800DBF70;
                                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                                    v109 = &qword_1800DBF70;
                                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                                  v103 = &qword_1800DBF70;
                                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                                v97 = &qword_1800DBF70;
                                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                              v91 = &qword_1800DBF70;
                              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                            v85 = &qword_1800DBF70;
                            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                          v79 = &qword_1800DBF70;
                          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                        v73 = &qword_1800DBF70;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                      v67 = &qword_1800DBF70;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                    v61 = &qword_1800DBF70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                  v53 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                v45 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
              v39 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v33 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v27 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v16 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x180067b40  push    rbp
0x180067b42  push    rbx
0x180067b43  push    rsi
0x180067b44  push    rdi
0x180067b45  push    r12
0x180067b47  push    r13
0x180067b49  push    r14
0x180067b4b  push    r15
0x180067b4d  lea     rbp, [rsp-17h]
0x180067b52  sub     rsp, 0E8h
0x180067b59  mov     rax, cs:__security_cookie
0x180067b60  xor     rax, rsp
0x180067b63  mov     [rbp+4Fh+var_50], rax
0x180067b67  mov     r12, [rbp+4Fh+arg_20]
0x180067b6b  xor     edi, edi
0x180067b6d  xorps   xmm0, xmm0
0x180067b70  mov     [rbp+4Fh+ppBuffer], rdi
0x180067b74  movups  [rbp+4Fh+var_90], xmm0
0x180067b78  mov     r14, r8
0x180067b7b  mov     r13, rdx
0x180067b7e  movups  [rbp+4Fh+var_80], xmm0
0x180067b82  mov     rsi, rcx
0x180067b85  mov     r8d, 626h; int
0x180067b8b  movups  xmm0, xmmword ptr cs:MFVideoFormat_ARGB32.Data1
0x180067b92  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x180067b99  mov     [rsp+120h+ppIMFSample], rdi
0x180067b9e  lea     rcx, [rsp+120h+var_F0]; this
0x180067ba3  mov     [rbp+4Fh+var_98], rdi
0x180067ba7  movdqu  xmmword ptr [rbp+4Fh+guidSubtype.Data1], xmm0
0x180067bac  mov     r15, r9
0x180067baf  mov     [rsp+120h+var_E0], rdi
0x180067bb4  mov     [rbp+4Fh+pcbImageSize], edi
0x180067bb7  mov     [rbp+4Fh+var_A0], edi
0x180067bba  mov     [rsp+120h+var_E8], rdi
0x180067bbf  mov     [rbp+4Fh+var_B0], rdi
0x180067bc3  mov     [rbp+4Fh+var_C0], rdi
0x180067bc7  mov     [rbp+4Fh+unWidth], edi
0x180067bca  mov     [rsp+120h+unHeight], edi
0x180067bce  mov     [rbp+4Fh+var_B8], rdi
0x180067bd2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180067bd7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180067bde  cmp     [rcx+8], dil
0x180067be2  jz      short loc_180067C3A
0x180067be4  cmp     [rsi+190h], rdi
0x180067beb  jz      short loc_180067C3A
0x180067bed  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180067bf2  mov     rcx, [rsi+190h]
0x180067bf9  mov     rdi, rax
0x180067bfc  mov     rdx, [rcx]
0x180067bff  mov     rax, [rdx+128h]
0x180067c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067c0b  mov     rcx, [rsi+190h]
0x180067c12  mov     ebx, eax
0x180067c14  mov     rdx, [rcx]
0x180067c17  mov     rax, [rdx+118h]
0x180067c1e  lea     rdx, [rbp+4Fh+var_60]
0x180067c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067c27  movups  xmm0, xmmword ptr [rax]
0x180067c2a  mov     [rdi+7E0h], ebx
0x180067c30  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180067c38  xor     edi, edi
0x180067c3a  lea     rcx, [rsp+120h+var_E8]
0x180067c3f  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x180067c44  xor     edx, edx; pUnkOuter
0x180067c46  lea     rax, [rsp+120h+var_E8]
0x180067c4b  lea     r9, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d; riid
0x180067c52  mov     [rsp+120h+ppv], rax; ppv
0x180067c57  lea     rcx, CLSID_VideoProcessorMFT; rclsid
0x180067c5e  lea     r8d, [rdx+1]; dwClsContext
0x180067c62  call    cs:__imp_CoCreateInstance
0x180067c69  nop     dword ptr [rax+rax+00h]
0x180067c6e  mov     ebx, eax
0x180067c70  test    eax, eax
0x180067c72  jns     loc_180067D2B
0x180067c78  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067c7f  test    rcx, rcx
0x180067c82  jnz     short loc_180067CCB
0x180067c84  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180067c8b  nop     dword ptr [rax+rax+00h]
0x180067c90  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180067c97  mov     rcx, rax
0x180067c9a  test    rax, rax
0x180067c9d  jz      short loc_180067CBD
0x180067c9f  mov     rax, [rax]
0x180067ca2  mov     edx, 7F0h
0x180067ca7  mov     rax, [rax+8]
0x180067cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067cb0  test    eax, eax
0x180067cb2  jz      short loc_180067CBD
0x180067cb4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067cbb  jmp     short loc_180067CCB
0x180067cbd  lea     rcx, qword_1800DBF70; this
0x180067cc4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180067ccb  cmp     [rcx+8], dil
0x180067ccf  jz      short loc_180067CF6
0x180067cd1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180067cd6  cmp     [rax+7CCh], ebx
0x180067cdc  jz      short loc_180067CF6
0x180067cde  mov     r9d, ebx; int
0x180067ce1  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x180067ce8  mov     r8d, 626h; int
0x180067cee  mov     rcx, rax; this
0x180067cf1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180067cf6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180067cfd  jb      loc_180068A44
0x180067d03  mov     edx, 7Eh ; '~'
0x180067d08  mov     rcx, cs:WPP_GLOBAL_Control
0x180067d0f  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x180067d16  mov     r9, rsi
0x180067d19  mov     dword ptr [rsp+120h+ppv], ebx
0x180067d1d  mov     rcx, [rcx+10h]
0x180067d21  call    WPP_SF_qD
0x180067d26  jmp     loc_180068A44
0x180067d2b  mov     rbx, [rsp+120h+var_E8]
0x180067d30  lea     rcx, [rbp+4Fh+var_B8]
0x180067d34  mov     rax, [rbx]
0x180067d37  mov     rdi, [rax]
0x180067d3a  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x180067d3f  lea     r8, [rbp+4Fh+var_B8]
0x180067d43  mov     rcx, rbx
0x180067d46  lea     rdx, _GUID_0b5e1c7e_bd76_46bc_896c_b2edb40dd803
0x180067d4d  mov     rax, rdi
0x180067d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067d55  test    eax, eax
0x180067d57  js      short loc_180067D70
0x180067d59  mov     rcx, [rbp+4Fh+var_B8]
0x180067d5d  mov     rdx, [rsi+190h]
0x180067d64  mov     rax, [rcx]
0x180067d67  mov     rax, [rax+20h]
0x180067d6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067d70  mov     rdi, [rsp+120h+var_E8]
0x180067d75  lea     rcx, [rbp+4Fh+var_C0]
0x180067d79  mov     rax, [rdi]
0x180067d7c  mov     rbx, [rax+40h]
0x180067d80  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180067d85  lea     rdx, [rbp+4Fh+var_C0]
0x180067d89  mov     rcx, rdi
0x180067d8c  mov     rax, rbx
0x180067d8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067d94  xor     edi, edi
0x180067d96  mov     ebx, eax
0x180067d98  test    eax, eax
0x180067d9a  jns     loc_180067E35
0x180067da0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067da7  test    rcx, rcx
0x180067daa  jnz     short loc_180067DF3
0x180067dac  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180067db3  nop     dword ptr [rax+rax+00h]
0x180067db8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180067dbf  mov     rcx, rax
0x180067dc2  test    rax, rax
0x180067dc5  jz      short loc_180067DE5
0x180067dc7  mov     rax, [rax]
0x180067dca  mov     edx, 7F0h
0x180067dcf  mov     rax, [rax+8]
0x180067dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067dd8  test    eax, eax
0x180067dda  jz      short loc_180067DE5
0x180067ddc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067de3  jmp     short loc_180067DF3
0x180067de5  lea     rcx, qword_1800DBF70; this
0x180067dec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180067df3  cmp     [rcx+8], dil
0x180067df7  jz      short loc_180067E1E
0x180067df9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180067dfe  cmp     [rax+7CCh], ebx
0x180067e04  jz      short loc_180067E1E
0x180067e06  mov     r9d, ebx; int
0x180067e09  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x180067e10  mov     r8d, 62Bh; int
0x180067e16  mov     rcx, rax; this
0x180067e19  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180067e1e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180067e25  jb      loc_180068A44
0x180067e2b  mov     edx, 7Fh
0x180067e30  jmp     loc_180067D08
0x180067e35  mov     rcx, [rbp+4Fh+var_C0]
0x180067e39  lea     rdx, MF_XVP_DISABLE_FRC
0x180067e40  mov     r8d, 1
0x180067e46  mov     rax, [rcx]
0x180067e49  mov     rax, [rax+0A8h]
0x180067e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067e55  mov     ebx, eax
0x180067e57  test    eax, eax
0x180067e59  jns     loc_180067EF4
0x180067e5f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067e66  test    rcx, rcx
0x180067e69  jnz     short loc_180067EB2
0x180067e6b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180067e72  nop     dword ptr [rax+rax+00h]
0x180067e77  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180067e7e  mov     rcx, rax
0x180067e81  test    rax, rax
0x180067e84  jz      short loc_180067EA4
0x180067e86  mov     rax, [rax]
0x180067e89  mov     edx, 7F0h
0x180067e8e  mov     rax, [rax+8]
0x180067e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067e97  test    eax, eax
0x180067e99  jz      short loc_180067EA4
0x180067e9b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067ea2  jmp     short loc_180067EB2
0x180067ea4  lea     rcx, qword_1800DBF70; this
0x180067eab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180067eb2  cmp     [rcx+8], dil
0x180067eb6  jz      short loc_180067EDD
0x180067eb8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180067ebd  cmp     [rax+7CCh], ebx
0x180067ec3  jz      short loc_180067EDD
0x180067ec5  mov     r9d, ebx; int
0x180067ec8  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x180067ecf  mov     r8d, 62Ch; int
0x180067ed5  mov     rcx, rax; this
0x180067ed8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180067edd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180067ee4  jb      loc_180068A44
0x180067eea  mov     edx, 80h
0x180067eef  jmp     loc_180067D08
0x180067ef4  mov     rcx, [rbp+4Fh+var_C0]
0x180067ef8  lea     rdx, _GUID_2efd8eee_1150_4328_9cf5_66dce933fcf4
0x180067eff  mov     r8d, 1
0x180067f05  mov     rax, [rcx]
0x180067f08  mov     rax, [rax+0A8h]
0x180067f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067f14  mov     ebx, eax
0x180067f16  test    eax, eax
0x180067f18  jns     loc_180067FB3
0x180067f1e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067f25  test    rcx, rcx
0x180067f28  jnz     short loc_180067F71
0x180067f2a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180067f31  nop     dword ptr [rax+rax+00h]
0x180067f36  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180067f3d  mov     rcx, rax
0x180067f40  test    rax, rax
0x180067f43  jz      short loc_180067F63
0x180067f45  mov     rax, [rax]
0x180067f48  mov     edx, 7F0h
0x180067f4d  mov     rax, [rax+8]
0x180067f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067f56  test    eax, eax
0x180067f58  jz      short loc_180067F63
0x180067f5a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067f61  jmp     short loc_180067F71
0x180067f63  lea     rcx, qword_1800DBF70; this
0x180067f6a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180067f71  cmp     [rcx+8], dil
0x180067f75  jz      short loc_180067F9C
0x180067f77  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180067f7c  cmp     [rax+7CCh], ebx
0x180067f82  jz      short loc_180067F9C
0x180067f84  mov     r9d, ebx; int
0x180067f87  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x180067f8e  mov     r8d, 62Dh; int
0x180067f94  mov     rcx, rax; this
0x180067f97  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180067f9c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180067fa3  jb      loc_180068A44
0x180067fa9  mov     edx, 81h
0x180067fae  jmp     loc_180067D08
0x180067fb3  mov     rcx, [rsp+120h+var_E8]
0x180067fb8  xor     r9d, r9d
0x180067fbb  mov     r8, r14
0x180067fbe  xor     edx, edx
0x180067fc0  mov     rax, [rcx]
0x180067fc3  mov     rax, [rax+78h]
0x180067fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067fcc  xor     r14d, r14d
0x180067fcf  mov     ebx, eax
0x180067fd1  test    eax, eax
0x180067fd3  jns     loc_18006806E
0x180067fd9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067fe0  test    rcx, rcx
0x180067fe3  jnz     short loc_18006802C
0x180067fe5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180067fec  nop     dword ptr [rax+rax+00h]
0x180067ff1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180067ff8  mov     rcx, rax
0x180067ffb  test    rax, rax
0x180067ffe  jz      short loc_18006801E
0x180068000  mov     rax, [rax]
0x180068003  mov     edx, 7F0h
0x180068008  mov     rax, [rax+8]
0x18006800c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068011  test    eax, eax
0x180068013  jz      short loc_18006801E
0x180068015  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006801c  jmp     short loc_18006802C
0x18006801e  lea     rcx, qword_1800DBF70; this
0x180068025  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006802c  cmp     [rcx+8], r14b
0x180068030  jz      short loc_180068057
0x180068032  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180068037  cmp     [rax+7CCh], ebx
0x18006803d  jz      short loc_180068057
0x18006803f  mov     r9d, ebx; int
0x180068042  lea     rdx, aCmfvideothumbn_20; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x180068049  mov     r8d, 62Fh; int
0x18006804f  mov     rcx, rax; this
0x180068052  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
  ... truncated ...
```
