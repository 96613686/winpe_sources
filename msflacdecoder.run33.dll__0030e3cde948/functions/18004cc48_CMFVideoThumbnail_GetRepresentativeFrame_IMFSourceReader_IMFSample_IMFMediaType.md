# CMFVideoThumbnail::GetRepresentativeFrame(IMFSourceReader *,IMFSample * *,IMFMediaType * *)

- ea: `0x18004cc48`
- end: `0x18004de01`
- name: `?GetRepresentativeFrame@CMFVideoThumbnail@@AEAAJPEAUIMFSourceReader@@PEAPEAUIMFSample@@PEAPEAUIMFMediaType@@@Z`
- size: `4537`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFSourceReader *, struct IMFSample **, struct IMFMediaType **)`
- caller_count: `1`
- callee_count: `33`
- tags: `broker_com_uri`

## callers

- `0x18004c254`

## callees

- `0x180001270`
- `0x1800014e4`
- `0x180001e80`
- `0x180016b18`
- `0x180020484`
- `0x180027c38`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180034a04`
- `0x180039e18`
- `0x180039e60`
- `0x1800462a0`
- `0x180048710`
- `0x180048b84`
- `0x180048bd8`
- `0x180048cd8`
- `0x180049364`
- `0x18004c114`
- `0x18004c808`
- `0x18004c8a0`
- `0x18004cc48`
- `0x18004de08`
- `0x18004e0bc`
- `0x18004f888`
- `0x18004fdc0`
- `0x1800501d4`
- `0x180050544`
- `0x180050608`
- `0x18005075c`
- `0x1800507e8`
- `0x1800509c4`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004d449`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004d449`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004dac0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004daf1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004dac0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004daf1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004da34`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004da34`

## pseudocode

```c
__int64 __fastcall CMFVideoThumbnail::GetRepresentativeFrame(
        CMFVideoThumbnail *this,
        struct IMFSourceReader *a2,
        struct IMFSample **a3,
        struct IMFMediaType **a4)
{
  int v4; // r13d
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v10; // ebx
  __int128 v11; // xmm0
  int Stride; // ebx
  CallStackTracing *v13; // rcx
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  struct _GUID *v16; // rdi
  int v17; // edx
  int v18; // r8d
  CallStackTracing *v19; // rcx
  struct CallStackContext *v20; // rax
  HRESULT (__stdcall *GetNativeMediaType)(IMFSourceReader *, DWORD, DWORD, IMFMediaType **); // rbx
  CallStackTracing *v22; // rcx
  struct CallStackContext *v23; // rax
  CallStackTracing *v24; // rcx
  struct CallStackContext *v25; // rax
  LARGE_INTEGER v26; // rcx
  HRESULT (__stdcall *GetCurrentMediaType)(IMFSourceReader *, DWORD, IMFMediaType **); // rbx
  CallStackTracing *v28; // rcx
  struct CallStackContext *v29; // rax
  CallStackTracing *v30; // rcx
  struct CallStackContext *v31; // rax
  CallStackTracing *v32; // rcx
  struct CallStackContext *v33; // rax
  unsigned int v34; // edi
  CallStackTracing *v35; // rcx
  struct CallStackContext *v36; // rax
  unsigned int v37; // r15d
  CMFVideoThumbnail *v38; // rcx
  CallStackTracing *v39; // rcx
  struct CallStackContext *v40; // rax
  int BytesPerPixel; // eax
  __int64 v42; // rdx
  int v43; // r9d
  __int64 v44; // r8
  CallStackTracing *v45; // rcx
  struct CallStackContext *v46; // rax
  float v47; // xmm7_4
  float v48; // xmm8_4
  int v49; // r12d
  __int64 v50; // rdx
  HRESULT (__stdcall *ReadSample)(IMFSourceReader *, DWORD, DWORD, DWORD *, DWORD *, LONGLONG *, IMFSample **); // rax
  __int64 v52; // rax
  __int64 v53; // r8
  __int64 v54; // rcx
  __int64 v55; // rdi
  __int64 v56; // r8
  HRESULT (__stdcall *v57)(IMFSourceReader *, DWORD, IMFMediaType **); // rbx
  CMFVideoThumbnail *v58; // rcx
  unsigned int v59; // edi
  CMFVideoThumbnail *v60; // rcx
  int v61; // eax
  __int64 v62; // rdx
  int v63; // r9d
  struct IMFSample *v64; // rdx
  CallStackTracing *v65; // rcx
  struct CallStackContext *v66; // rax
  __int64 v67; // rdx
  CallStackTracing *v68; // rcx
  struct CallStackContext *v69; // rax
  CallStackTracing *v70; // rcx
  struct CallStackContext *v71; // rax
  CallStackTracing *v72; // rcx
  struct CallStackContext *v73; // rax
  CallStackTracing *v74; // rcx
  struct CallStackContext *v75; // rax
  CallStackTracing *v76; // rcx
  struct CallStackContext *v77; // rax
  CallStackTracing *v78; // rcx
  struct CallStackContext *v79; // rax
  __int64 v80; // rdx
  CallStackTracing *v81; // rcx
  struct CallStackContext *v82; // rax
  __int64 v83; // rdx
  int v84; // ecx
  __int64 v85; // r8
  struct IMFSample *v86; // rdi
  __int64 v87; // rdx
  CallStackTracing *v88; // rcx
  struct CallStackContext *v89; // rax
  int v90; // r15d
  int v91; // r13d
  __int64 v92; // r8
  struct IMFMediaType **v93; // rcx
  __int64 v94; // rcx
  __int64 v95; // rcx
  __int64 v96; // r8
  GUID *v97; // rax
  __int64 v98; // rcx
  int v99; // ecx
  int v100; // r8d
  int v101; // r9d
  CallStackTracing *v102; // rcx
  struct CallStackContext *v103; // rax
  unsigned int v105; // [rsp+20h] [rbp-E0h]
  unsigned int v106; // [rsp+20h] [rbp-E0h]
  _BYTE v107[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v108; // [rsp+64h] [rbp-9Ch] BYREF
  struct IMFMediaType *v109; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v110; // [rsp+70h] [rbp-90h] BYREF
  GUID *v111; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v112; // [rsp+80h] [rbp-80h] BYREF
  int v113; // [rsp+84h] [rbp-7Ch]
  int v114; // [rsp+88h] [rbp-78h] BYREF
  int v115; // [rsp+8Ch] [rbp-74h] BYREF
  struct IMFMediaType *v116; // [rsp+90h] [rbp-70h] BYREF
  float v117; // [rsp+98h] [rbp-68h] BYREF
  float v118; // [rsp+9Ch] [rbp-64h] BYREF
  struct IMFSample *v119; // [rsp+A0h] [rbp-60h] BYREF
  PROPVARIANT pvar; // [rsp+A8h] [rbp-58h] BYREF
  struct IMFSample **v121; // [rsp+C0h] [rbp-40h] BYREF
  struct _GUID Buf2; // [rsp+C8h] [rbp-38h] BYREF
  struct _GUID v123; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v124[2]; // [rsp+E8h] [rbp-18h] BYREF
  _MFVideoArea v125; // [rsp+F8h] [rbp-8h] BYREF
  GUID v126; // [rsp+108h] [rbp+8h] BYREF

  v4 = 0;
  v121 = a3;
  v110 = 0;
  v112 = 0;
  v108 = 0;
  v119 = 0;
  v109 = 0;
  v116 = 0;
  v124[0] = a4;
  memset(&pvar, 0, sizeof(pvar));
  v125 = 0;
  Buf2 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v107,
    "CMFVideoThumbnail::GetRepresentativeFrame",
    1050);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 50) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 296LL))(*((_QWORD *)this + 50));
    v11 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, GUID *))(**((_QWORD **)this + 50) + 280LL))(
                       *((_QWORD *)this + 50),
                       &v126);
    *((_DWORD *)ThreadRelativeContext + 504) = v10;
    *((_OWORD *)ThreadRelativeContext + 125) = v11;
  }
  *a3 = 0;
  *a4 = 0;
  Stride = CMFVideoThumbnail::SelectPreferredVideoStream(this, a2);
  if ( Stride < 0 )
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
      if ( *((_DWORD *)v14 + 499) != Stride )
        CallStackContext::TraceFailure(v14, "CMFVideoThumbnail::GetRepresentativeFrame", 1056, Stride);
    }
    if ( !g_wppLevels )
      goto LABEL_238;
    v15 = 80;
    goto LABEL_12;
  }
  v16 = (struct _GUID *)&xmmword_18006F5C0;
  while ( 1 )
  {
    v123 = *v16;
    Stride = CMFVideoThumbnail::SetSupportedMediaType(this, a2, &v123);
    if ( Stride >= 0 )
      break;
    if ( ++v16 == (struct _GUID *)&_dyn_tls_init_callback )
    {
      v19 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v19 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v19 + 8) )
      {
        v20 = CallStackTracing::GetThreadRelativeContext(v19);
        if ( *((_DWORD *)v20 + 499) != Stride )
          CallStackContext::TraceFailure(v20, "CMFVideoThumbnail::GetRepresentativeFrame", 1070, Stride);
      }
      if ( !g_wppLevels )
        goto LABEL_238;
      v15 = 82;
      goto LABEL_12;
    }
  }
  if ( (unsigned __int8)byte_18006E80B >= 0x20u )
    WPP_SF_qs(*((_QWORD *)WPP_GLOBAL_Control + 17), v17, v18, (_DWORD)this, (__int64)&v123);
  CMFVideoThumbnail::TryPutCodecInThumbnailMode(this, a2);
  GetNativeMediaType = a2->lpVtbl->GetNativeMediaType;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v109);
  Stride = ((__int64 (__fastcall *)(struct IMFSourceReader *, __int64, _QWORD, struct IMFMediaType **))GetNativeMediaType)(
             a2,
             4294967292LL,
             0,
             &v109);
  if ( Stride < 0 )
  {
    v22 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v22 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v22 + 8) )
    {
      v23 = CallStackTracing::GetThreadRelativeContext(v22);
      if ( *((_DWORD *)v23 + 499) != Stride )
        CallStackContext::TraceFailure(v23, "CMFVideoThumbnail::GetRepresentativeFrame", 1081, Stride);
    }
    if ( !g_wppLevels )
      goto LABEL_238;
    v15 = 83;
    goto LABEL_12;
  }
  Stride = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, struct _GUID *))v109->lpVtbl->GetGUID)(
             v109,
             &MF_MT_SUBTYPE,
             &Buf2);
  if ( Stride < 0 )
  {
    v24 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v24 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v24 + 8) )
    {
      v25 = CallStackTracing::GetThreadRelativeContext(v24);
      if ( *((_DWORD *)v25 + 499) != Stride )
        CallStackContext::TraceFailure(v25, "CMFVideoThumbnail::GetRepresentativeFrame", 1082, Stride);
    }
    if ( !g_wppLevels )
      goto LABEL_238;
    v15 = 84;
    goto LABEL_12;
  }
  if ( ((int (__fastcall *)(struct IMFSourceReader *, __int64, const IID *, PROPVARIANT *))a2->lpVtbl->GetPresentationAttribute)(
         a2,
         0xFFFFFFFFLL,
         &MF_PD_DURATION,
         &pvar) < 0
    || !memcmp_0(&MFVideoFormat_MSS1, &Buf2, 0x10u) )
  {
    goto LABEL_47;
  }
  v26 = *(LARGE_INTEGER *)((char *)this + 352);
  if ( pvar.hVal.QuadPart <= 2 * v26.QuadPart )
  {
    if ( pvar.hVal.QuadPart >= v26.QuadPart )
    {
      pvar.hVal.QuadPart /= 2LL;
      goto LABEL_48;
    }
LABEL_47:
    memset(&pvar, 0, sizeof(pvar));
    goto LABEL_48;
  }
  pvar.hVal.QuadPart = *((_QWORD *)this + 44);
LABEL_48:
  pvar.vt = 20;
  GetCurrentMediaType = a2->lpVtbl->GetCurrentMediaType;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v109);
  Stride = ((__int64 (__fastcall *)(struct IMFSourceReader *, _QWORD, struct IMFMediaType **))GetCurrentMediaType)(
             a2,
             *((unsigned int *)this + 6),
             &v109);
  if ( Stride < 0 )
  {
    v28 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v28 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v28 + 8) )
    {
      v29 = CallStackTracing::GetThreadRelativeContext(v28);
      if ( *((_DWORD *)v29 + 499) != Stride )
        CallStackContext::TraceFailure(v29, "CMFVideoThumbnail::GetRepresentativeFrame", 1118, Stride);
    }
    if ( !g_wppLevels )
      goto LABEL_238;
    v15 = 85;
    goto LABEL_12;
  }
  Stride = MFGetAttribute2UINT32asUINT64(v109, &MF_MT_FRAME_SIZE, &v110, &v112);
  if ( Stride < 0 )
  {
    v30 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v30 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v30 + 8) )
    {
      v31 = CallStackTracing::GetThreadRelativeContext(v30);
      if ( *((_DWORD *)v31 + 499) != Stride )
        CallStackContext::TraceFailure(v31, "CMFVideoThumbnail::GetRepresentativeFrame", 1119, Stride);
    }
    if ( !g_wppLevels )
      goto LABEL_238;
    v15 = 86;
    goto LABEL_12;
  }
  Stride = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, struct _GUID *))v109->lpVtbl->GetGUID)(
             v109,
             &MF_MT_SUBTYPE,
             &Buf2);
  if ( Stride < 0 )
  {
    v32 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v32 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v32 + 8) )
    {
      v33 = CallStackTracing::GetThreadRelativeContext(v32);
      if ( *((_DWORD *)v33 + 499) != Stride )
        CallStackContext::TraceFailure(v33, "CMFVideoThumbnail::GetRepresentativeFrame", 1120, Stride);
    }
    if ( !g_wppLevels )
      goto LABEL_238;
    v15 = 87;
    goto LABEL_12;
  }
  v34 = v110;
  Stride = CMFVideoThumbnail::GetStride(this, v109, v110, &v108);
  if ( Stride < 0 )
  {
    v35 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v35 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v35 + 8) )
    {
      v36 = CallStackTracing::GetThreadRelativeContext(v35);
      if ( *((_DWORD *)v36 + 499) != Stride )
        CallStackContext::TraceFailure(v36, "CMFVideoThumbnail::GetRepresentativeFrame", 1121, Stride);
    }
    if ( !g_wppLevels )
      goto LABEL_238;
    v15 = 88;
    goto LABEL_12;
  }
  v37 = v112;
  Stride = CMFVideoThumbnail::GetMinDisplayAperture(this, v109, v34, v112, &v125);
  if ( Stride < 0 )
  {
    v39 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v39 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v39 + 8) )
    {
      v40 = CallStackTracing::GetThreadRelativeContext(v39);
      if ( *((_DWORD *)v40 + 499) != Stride )
        CallStackContext::TraceFailure(v40, "CMFVideoThumbnail::GetRepresentativeFrame", 1122, Stride);
    }
    if ( !g_wppLevels )
      goto LABEL_238;
    v15 = 89;
    goto LABEL_12;
  }
  BytesPerPixel = CMFVideoThumbnail::GetBytesPerPixel(v38, &Buf2);
  Stride = CMFVideoThumbnail::CalcOffsetsForComparison(this, v42, BytesPerPixel, v43, v105, &v125);
  if ( Stride < 0 )
  {
    v45 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v45 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v45 + 8) )
    {
      v46 = CallStackTracing::GetThreadRelativeContext(v45);
      if ( *((_DWORD *)v46 + 499) != Stride )
        CallStackContext::TraceFailure(v46, "CMFVideoThumbnail::GetRepresentativeFrame", 1124, Stride);
    }
    if ( !g_wppLevels )
      goto LABEL_238;
    v15 = 90;
LABEL_12:
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, Stride);
    goto LABEL_238;
  }
  v47 = 0.0;
  v113 = 0;
  v48 = 0.0;
  v115 = 0;
  v49 = 0;
  v114 = 0;
  if ( (unsigned __int8)byte_18006E80B >= 0x20u )
    WPP_SF_qi(*((_QWORD *)WPP_GLOBAL_Control + 17), 91, v44, this, pvar.hVal.QuadPart / 10000);
  ((void (__fastcall *)(struct IMFSourceReader *, GUID *, PROPVARIANT *))a2->lpVtbl->SetCurrentPosition)(
    a2,
    &GUID_00000000_0000_0000_0000_000000000000,
    &pvar);
  while ( 1 )
  {
    v50 = *((unsigned int *)this + 6);
    ReadSample = a2->lpVtbl->ReadSample;
    v111 = 0;
    Stride = ((__int64 (__fastcall *)(struct IMFSourceReader *, __int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))ReadSample)(
               a2,
               v50,
               0,
               0,
               0,
               0,
               0);
    if ( Stride < 0 )
    {
      v102 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v102 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v102 + 8) )
      {
        v103 = CallStackTracing::GetThreadRelativeContext(v102);
        if ( *((_DWORD *)v103 + 499) != Stride )
          CallStackContext::TraceFailure(v103, "CMFVideoThumbnail::GetRepresentativeFrame", 1141, Stride);
      }
      if ( !g_wppLevels )
        goto LABEL_237;
      v67 = 92;
      goto LABEL_236;
    }
    ++v49;
    v52 = CMFVideoThumbnail::ElapsedTime(this);
    v54 = *((_QWORD *)this + 45);
    *(_QWORD *)&v123.Data1 = v52;
    if ( v54 <= v52 )
    {
      if ( (unsigned __int8)byte_18006E80B >= 0x20u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 95, v53, this);
      v115 = 2;
      goto LABEL_200;
    }
    v55 = (v54 - v52) / 10000;
    if ( (unsigned __int8)byte_18006E80B >= 0x20u )
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 17), 93, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, v55);
    if ( WaitForSingleObject(*((HANDLE *)this + 46), v55) == 258 )
    {
      if ( (unsigned __int8)byte_18006E80B >= 0x20u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 94, v56, this);
      v115 = 1;
LABEL_200:
      v113 = 1;
      goto LABEL_201;
    }
    Stride = *((_DWORD *)this + 94);
    if ( Stride < 0 )
    {
      v81 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v81 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v81 + 8) )
      {
        v82 = CallStackTracing::GetThreadRelativeContext(v81);
        if ( *((_DWORD *)v82 + 499) != Stride )
          CallStackContext::TraceFailure(v82, "CMFVideoThumbnail::GetRepresentativeFrame", 1180, Stride);
      }
      if ( !g_wppLevels )
        goto LABEL_237;
      v67 = 96;
      goto LABEL_236;
    }
    if ( (*((_BYTE *)this + 380) & 0x20) != 0 )
    {
      v57 = a2->lpVtbl->GetCurrentMediaType;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
      Stride = ((__int64 (__fastcall *)(struct IMFSourceReader *, _QWORD, struct IMFMediaType **))v57)(
                 a2,
                 *((unsigned int *)this + 6),
                 &v116);
      if ( Stride < 0 )
      {
        v78 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v78 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v78 + 8) )
        {
          v79 = CallStackTracing::GetThreadRelativeContext(v78);
          if ( *((_DWORD *)v79 + 499) != Stride )
            CallStackContext::TraceFailure(v79, "CMFVideoThumbnail::GetRepresentativeFrame", 1184, Stride);
        }
        if ( !g_wppLevels )
          goto LABEL_237;
        v67 = 97;
      }
      else
      {
        if ( !(unsigned int)CMFVideoThumbnail::IsSupportedMediaType(v58, v116) )
        {
          v76 = CallStackTracing::s_wpInstance;
          Stride = -1072875854;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v76 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v76 + 8) )
          {
            v77 = CallStackTracing::GetThreadRelativeContext(v76);
            if ( *((_DWORD *)v77 + 499) != -1072875854 )
              CallStackContext::TraceFailure(v77, "CMFVideoThumbnail::GetRepresentativeFrame", 1187, -1072875854);
          }
          if ( g_wppLevels )
            WPP_SF_qd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              98,
              &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids,
              this,
              -1072875854);
          goto LABEL_237;
        }
        Stride = MFGetAttribute2UINT32asUINT64(v116, &MF_MT_FRAME_SIZE, &v110, &v112);
        if ( Stride < 0 )
        {
          v74 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v74 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v74 + 8) )
          {
            v75 = CallStackTracing::GetThreadRelativeContext(v74);
            if ( *((_DWORD *)v75 + 499) != Stride )
              CallStackContext::TraceFailure(v75, "CMFVideoThumbnail::GetRepresentativeFrame", 1193, Stride);
          }
          if ( !g_wppLevels )
            goto LABEL_237;
          v67 = 99;
        }
        else
        {
          Stride = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, struct _GUID *))v116->lpVtbl->GetGUID)(
                     v116,
                     &MF_MT_SUBTYPE,
                     &Buf2);
          if ( Stride < 0 )
          {
            v72 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::InitInstance();
              v72 = CallStackTracing::s_wpInstance;
            }
            if ( *((_BYTE *)v72 + 8) )
            {
              v73 = CallStackTracing::GetThreadRelativeContext(v72);
              if ( *((_DWORD *)v73 + 499) != Stride )
                CallStackContext::TraceFailure(v73, "CMFVideoThumbnail::GetRepresentativeFrame", 1194, Stride);
            }
            if ( !g_wppLevels )
              goto LABEL_237;
            v67 = 100;
          }
          else
          {
            v59 = v110;
            Stride = CMFVideoThumbnail::GetStride(this, v116, v110, &v108);
            if ( Stride < 0 )
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
                if ( *((_DWORD *)v71 + 499) != Stride )
                  CallStackContext::TraceFailure(v71, "CMFVideoThumbnail::GetRepresentativeFrame", 1195, Stride);
              }
              if ( !g_wppLevels )
                goto LABEL_237;
              v67 = 101;
            }
            else
            {
              v37 = v112;
              Stride = CMFVideoThumbnail::GetMinDisplayAperture(this, v116, v59, v112, &v125);
              if ( Stride < 0 )
              {
                v68 = CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  CallStackTracing::InitInstance();
                  v68 = CallStackTracing::s_wpInstance;
                }
                if ( *((_BYTE *)v68 + 8) )
                {
                  v69 = CallStackTracing::GetThreadRelativeContext(v68);
                  if ( *((_DWORD *)v69 + 499) != Stride )
                    CallStackContext::TraceFailure(v69, "CMFVideoThumbnail::GetRepresentativeFrame", 1196, Stride);
                }
                if ( !g_wppLevels )
                  goto LABEL_237;
                v67 = 102;
              }
              else
              {
                v61 = CMFVideoThumbnail::GetBytesPerPixel(v60, &Buf2);
                Stride = CMFVideoThumbnail::CalcOffsetsForComparison(this, v62, v61, v63, v106, &v125);
                if ( Stride >= 0 )
                {
                  v4 = 1;
                  goto LABEL_115;
                }
                v65 = CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  CallStackTracing::InitInstance();
                  v65 = CallStackTracing::s_wpInstance;
                }
                if ( *((_BYTE *)v65 + 8) )
                {
                  v66 = CallStackTracing::GetThreadRelativeContext(v65);
                  if ( *((_DWORD *)v66 + 499) != Stride )
                    CallStackContext::TraceFailure(v66, "CMFVideoThumbnail::GetRepresentativeFrame", 1198, Stride);
                }
                if ( !g_wppLevels )
                {
LABEL_237:
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v111);
                  goto LABEL_238;
                }
                v67 = 103;
              }
            }
          }
        }
      }
LABEL_236:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v67,
        &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids,
        this,
        Stride);
      goto LABEL_237;
    }
    v59 = v110;
LABEL_115:
    v64 = (struct IMFSample *)*((_QWORD *)this + 4);
    if ( v64 )
    {
      v118 = 0.0;
      v117 = 0.0;
      if ( (int)CMFVideoThumbnail::AnalyzeSample(this, v64, &Buf2, v59, v37, &v117, &v118) < 0 )
      {
        if ( v47 == 0.0 && v48 == 0.0 )
        {
          Microsoft::WRL::ComPtr<IMFSample>::operator=(&v119, *((_QWORD *)this + 4));
          if ( v4 )
          {
            Microsoft::WRL::ComPtr<IMFMediaType>::operator=(&v109, &v116);
            v4 = 0;
          }
          v114 = v49;
        }
      }
      else
      {
        if ( v117 >= v47 && v118 >= v48 )
        {
          v48 = v118;
          v47 = v117;
          Microsoft::WRL::ComPtr<IMFSample>::operator=(&v119, *((_QWORD *)this + 4));
          if ( v4 )
          {
            Microsoft::WRL::ComPtr<IMFMediaType>::operator=(&v109, &v116);
            v4 = 0;
          }
          v114 = v49;
        }
        if ( v47 > *((float *)this + 97) && v48 > *((float *)this + 98) )
          goto LABEL_201;
      }
    }
    if ( (*((_BYTE *)this + 380) & 2) != 0 )
      break;
    if ( v49 == *((_DWORD *)this + 96) )
    {
      if ( (unsigned __int8)byte_18006E80B >= 0x20u )
      {
        v80 = 105;
        goto LABEL_186;
      }
      goto LABEL_201;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v111);
  }
  if ( (unsigned __int8)byte_18006E80B >= 0x20u )
  {
    v80 = 104;
LABEL_186:
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), v80, v56, this);
  }
LABEL_201:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v111);
  v86 = v119;
  if ( v119 )
  {
    v91 = v114;
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
    v87 = *((_QWORD *)this + 4);
    if ( !v87 )
    {
      v88 = CallStackTracing::s_wpInstance;
      Stride = -1072875854;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v88 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v88 + 8) )
      {
        v89 = CallStackTracing::GetThreadRelativeContext(v88);
        if ( *((_DWORD *)v89 + 499) != -1072875854 )
          CallStackContext::TraceFailure(v89, "CMFVideoThumbnail::GetRepresentativeFrame", 1283, -1072875854);
      }
      if ( g_wppLevels )
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          106,
          &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids,
          this,
          -1072875854);
      LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
      v90 = v113;
      goto LABEL_221;
    }
    Microsoft::WRL::ComPtr<IMFSample>::operator=(&v119, v87);
    if ( v4 )
      Microsoft::WRL::ComPtr<IMFMediaType>::operator=(&v109, &v116);
    v91 = v49;
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
    v86 = v119;
  }
  v90 = v113;
  if ( (unsigned __int8)byte_18006E80B >= 0x20u )
  {
    WPP_SF_qddggd(*((_QWORD *)WPP_GLOBAL_Control + 17), v83, v85, this, v91, v49, v47, v48, v113);
    if ( (unsigned __int8)byte_18006E80B >= 0x20u )
      WPP_SF_qPPl(*((_QWORD *)WPP_GLOBAL_Control + 17), v110, v92, this, v110, v112, v108);
  }
  if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
    McTemplateU0pqqqxt_EventWriteTransfer(
      v84,
      v83,
      (_DWORD)this,
      *((_DWORD *)this + 7),
      v91,
      v49,
      *((_QWORD *)this + 45),
      v90);
  ((void (__fastcall *)(struct IMFSourceReader *, _QWORD))a2->lpVtbl->Flush)(a2, *((unsigned int *)this + 6));
  v93 = (struct IMFMediaType **)v124[0];
  v119 = 0;
  *v121 = v86;
  *v93 = v109;
  v109 = 0;
LABEL_221:
  if ( v90 )
  {
    v94 = *((_QWORD *)this + 50);
    if ( !v94
      || !(*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)v94 + 320LL))(
            v94,
            &MF_TELEMETRY_EVENT_RATE_EXCEEDED_LIMIT) )
    {
      v95 = *((_QWORD *)this + 50);
      v96 = 0;
      v126 = GUID_00000000_0000_0000_0000_000000000000;
      if ( v95 )
      {
        v97 = (GUID *)(*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD))(*(_QWORD *)v95 + 280LL))(v95, v124, 0);
        v98 = *((_QWORD *)this + 50);
        v126 = *v97;
        v96 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v98 + 296LL))(v98);
      }
      if ( (unsigned int)dword_18006E218 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18006E218, 0x400000000000LL, v96) )
      {
        v121 = (struct IMFSample **)*((_QWORD *)this + 45);
        v117 = *(float *)&v115;
        v115 = *((_DWORD *)this + 7);
        v111 = &v126;
        v124[0] = 0x1000000;
        v118 = *(float *)&Stride;
        v114 = v100;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v99,
          (unsigned int)&unk_180067862,
          v100,
          v101,
          (__int64)&v111,
          (__int64)&v114,
          (__int64)&v115,
          (__int64)&v117,
          (__int64)&v121,
          (__int64)&v123,
          (__int64)&v118,
          (__int64)v124);
      }
    }
  }
LABEL_238:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v107);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v109);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v119);
  CMFPropVariant::Clear(&pvar);
  return (unsigned int)Stride;
}

```

## disassembly

```asm
0x18004cc48  mov     rax, rsp
0x18004cc4b  push    rbp
0x18004cc4c  push    rbx
0x18004cc4d  push    rsi
0x18004cc4e  push    rdi
0x18004cc4f  push    r12
0x18004cc51  push    r13
0x18004cc53  push    r14
0x18004cc55  push    r15
0x18004cc57  lea     rbp, [rsp-48h]
0x18004cc5c  sub     rsp, 148h
0x18004cc63  movaps  xmmword ptr [rax-58h], xmm7
0x18004cc67  movaps  xmmword ptr [rax-68h], xmm8
0x18004cc6c  mov     rax, cs:__security_cookie
0x18004cc73  xor     rax, rsp
0x18004cc76  mov     [rbp+80h+var_68], rax
0x18004cc7a  xor     r13d, r13d
0x18004cc7d  mov     [rbp+80h+var_C0], r8
0x18004cc81  xorps   xmm0, xmm0
0x18004cc84  mov     [rsp+180h+var_110], r13d
0x18004cc89  mov     r15, r8
0x18004cc8c  mov     [rbp+80h+var_100], r13d
0x18004cc90  mov     r14, rdx
0x18004cc93  mov     [rsp+180h+var_11C], r13d
0x18004cc98  mov     rsi, rcx
0x18004cc9b  mov     [rbp+80h+var_E0], r13
0x18004cc9f  xor     eax, eax
0x18004cca1  mov     [rsp+180h+var_118], r13
0x18004cca6  xorps   xmm1, xmm1
0x18004cca9  mov     qword ptr [rbp+80h+pvar+10h], rax
0x18004ccad  mov     r8d, 41Ah; int
0x18004ccb3  mov     [rbp+80h+var_F0], r13
0x18004ccb7  lea     rdx, aCmfvideothumbn_15; "CMFVideoThumbnail::GetRepresentativeFra"...
0x18004ccbe  mov     [rbp+80h+var_98], r9
0x18004ccc2  lea     rcx, [rsp+180h+var_120]; this
0x18004ccc7  mov     r12, r9
0x18004ccca  movups  xmmword ptr [rbp+80h+pvar], xmm0
0x18004ccce  movups  xmmword ptr [rbp+80h+var_88.OffsetX.fract], xmm0
0x18004ccd2  movups  [rbp+80h+Buf2], xmm1
0x18004ccd6  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004ccdb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004cce2  cmp     [rcx+8], r13b
0x18004cce6  jz      short loc_18004CD42
0x18004cce8  cmp     [rsi+190h], r13
0x18004ccef  jz      short loc_18004CD42
0x18004ccf1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004ccf6  mov     rdx, [rsi+190h]
0x18004ccfd  mov     rdi, rax
0x18004cd00  mov     rcx, [rdx]
0x18004cd03  mov     rax, [rcx+128h]
0x18004cd0a  mov     rcx, rdx
0x18004cd0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cd12  mov     r8, [rsi+190h]
0x18004cd19  lea     rdx, [rbp+80h+var_78]
0x18004cd1d  mov     ebx, eax
0x18004cd1f  mov     rcx, [r8]
0x18004cd22  mov     rax, [rcx+118h]
0x18004cd29  mov     rcx, r8
0x18004cd2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cd31  movups  xmm0, xmmword ptr [rax]
0x18004cd34  mov     [rdi+7E0h], ebx
0x18004cd3a  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18004cd42  mov     [r15], r13
0x18004cd45  mov     rdx, r14; struct IMFSourceReader *
0x18004cd48  mov     rcx, rsi; this
0x18004cd4b  mov     [r12], r13
0x18004cd4f  call    ?SelectPreferredVideoStream@CMFVideoThumbnail@@AEAAJPEAUIMFSourceReader@@@Z; CMFVideoThumbnail::SelectPreferredVideoStream(IMFSourceReader *)
0x18004cd54  mov     ebx, eax
0x18004cd56  test    eax, eax
0x18004cd58  jns     short loc_18004CDD2
0x18004cd5a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cd61  test    rcx, rcx
0x18004cd64  jnz     short loc_18004CD72
0x18004cd66  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004cd6b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004cd72  cmp     [rcx+8], r13b
0x18004cd76  jz      short loc_18004CD9D
0x18004cd78  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004cd7d  cmp     [rax+7CCh], ebx
0x18004cd83  jz      short loc_18004CD9D
0x18004cd85  mov     r9d, ebx; int
0x18004cd88  lea     rdx, aCmfvideothumbn_15; "CMFVideoThumbnail::GetRepresentativeFra"...
0x18004cd8f  mov     r8d, 420h; int
0x18004cd95  mov     rcx, rax; this
0x18004cd98  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004cd9d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004cda4  jb      loc_18004DDA2
0x18004cdaa  mov     edx, 50h ; 'P'
0x18004cdaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cdb6  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x18004cdbd  mov     r9, rsi
0x18004cdc0  mov     dword ptr [rsp+180h+var_160], ebx
0x18004cdc4  mov     rcx, [rcx+10h]
0x18004cdc8  call    WPP_SF_qd
0x18004cdcd  jmp     loc_18004DDA2
0x18004cdd2  lea     rdi, xmmword_18006F5C0
0x18004cdd9  movaps  xmm0, xmmword ptr [rdi]
0x18004cddc  lea     r8, [rbp+80h+var_A8]; struct _GUID *
0x18004cde0  mov     rdx, r14; struct IMFSourceReader *
0x18004cde3  mov     rcx, rsi; this
0x18004cde6  movdqu  xmmword ptr [rbp+80h+var_A8.Data1], xmm0
0x18004cdeb  call    ?SetSupportedMediaType@CMFVideoThumbnail@@AEAAJPEAUIMFSourceReader@@AEBU_GUID@@@Z; CMFVideoThumbnail::SetSupportedMediaType(IMFSourceReader *,_GUID const &)
0x18004cdf0  mov     ebx, eax
0x18004cdf2  test    eax, eax
0x18004cdf4  jns     short loc_18004CE60
0x18004cdf6  add     rdi, 10h
0x18004cdfa  lea     rax, __dyn_tls_init_callback
0x18004ce01  cmp     rdi, rax
0x18004ce04  jnz     short loc_18004CDD9
0x18004ce06  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ce0d  test    rcx, rcx
0x18004ce10  jnz     short loc_18004CE1E
0x18004ce12  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004ce17  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004ce1e  cmp     [rcx+8], r13b
0x18004ce22  jz      short loc_18004CE49
0x18004ce24  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004ce29  cmp     [rax+7CCh], ebx
0x18004ce2f  jz      short loc_18004CE49
0x18004ce31  mov     r9d, ebx; int
0x18004ce34  lea     rdx, aCmfvideothumbn_15; "CMFVideoThumbnail::GetRepresentativeFra"...
0x18004ce3b  mov     r8d, 42Eh; int
0x18004ce41  mov     rcx, rax; this
0x18004ce44  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004ce49  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004ce50  jb      loc_18004DDA2
0x18004ce56  mov     edx, 52h ; 'R'
0x18004ce5b  jmp     loc_18004CDAF
0x18004ce60  cmp     cs:byte_18006E80B, 20h ; ' '
0x18004ce67  jb      short loc_18004CE88
0x18004ce69  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ce70  lea     rax, [rbp+80h+var_A8]
0x18004ce74  mov     r9, rsi
0x18004ce77  mov     [rsp+180h+var_160], rax
0x18004ce7c  mov     rcx, [rcx+88h]
0x18004ce83  call    WPP_SF_qs
0x18004ce88  mov     rdx, r14; struct IMFSourceReader *
0x18004ce8b  mov     rcx, rsi; this
0x18004ce8e  call    ?TryPutCodecInThumbnailMode@CMFVideoThumbnail@@AEAAXPEAUIMFSourceReader@@@Z; CMFVideoThumbnail::TryPutCodecInThumbnailMode(IMFSourceReader *)
0x18004ce93  mov     rax, [r14]
0x18004ce96  lea     rcx, [rsp+180h+var_118]
0x18004ce9b  mov     rbx, [rax+28h]
0x18004ce9f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004cea4  lea     r9, [rsp+180h+var_118]
0x18004cea9  xor     r8d, r8d
0x18004ceac  mov     edx, 0FFFFFFFCh
0x18004ceb1  mov     rcx, r14
0x18004ceb4  mov     rax, rbx
0x18004ceb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cebc  mov     ebx, eax
0x18004cebe  test    eax, eax
0x18004cec0  jns     short loc_18004CF1C
0x18004cec2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cec9  test    rcx, rcx
0x18004cecc  jnz     short loc_18004CEDA
0x18004cece  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004ced3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004ceda  cmp     [rcx+8], r13b
0x18004cede  jz      short loc_18004CF05
0x18004cee0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004cee5  cmp     [rax+7CCh], ebx
0x18004ceeb  jz      short loc_18004CF05
0x18004ceed  mov     r9d, ebx; int
0x18004cef0  lea     rdx, aCmfvideothumbn_15; "CMFVideoThumbnail::GetRepresentativeFra"...
0x18004cef7  mov     r8d, 439h; int
0x18004cefd  mov     rcx, rax; this
0x18004cf00  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004cf05  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004cf0c  jb      loc_18004DDA2
0x18004cf12  mov     edx, 53h ; 'S'
0x18004cf17  jmp     loc_18004CDAF
0x18004cf1c  mov     rcx, [rsp+180h+var_118]
0x18004cf21  lea     r8, [rbp+80h+Buf2]
0x18004cf25  lea     rdx, MF_MT_SUBTYPE
0x18004cf2c  mov     rax, [rcx]
0x18004cf2f  mov     rax, [rax+50h]
0x18004cf33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cf38  mov     ebx, eax
0x18004cf3a  test    eax, eax
0x18004cf3c  jns     short loc_18004CF98
0x18004cf3e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cf45  test    rcx, rcx
0x18004cf48  jnz     short loc_18004CF56
0x18004cf4a  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004cf4f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004cf56  cmp     [rcx+8], r13b
0x18004cf5a  jz      short loc_18004CF81
0x18004cf5c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004cf61  cmp     [rax+7CCh], ebx
0x18004cf67  jz      short loc_18004CF81
0x18004cf69  mov     r9d, ebx; int
0x18004cf6c  lea     rdx, aCmfvideothumbn_15; "CMFVideoThumbnail::GetRepresentativeFra"...
0x18004cf73  mov     r8d, 43Ah; int
0x18004cf79  mov     rcx, rax; this
0x18004cf7c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004cf81  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004cf88  jb      loc_18004DDA2
0x18004cf8e  mov     edx, 54h ; 'T'
0x18004cf93  jmp     loc_18004CDAF
0x18004cf98  mov     rax, [r14]
0x18004cf9b  lea     r9, [rbp+80h+pvar]
0x18004cf9f  lea     r8, MF_PD_DURATION
0x18004cfa6  or      edx, 0FFFFFFFFh
0x18004cfa9  mov     rcx, r14
0x18004cfac  mov     rax, [rax+60h]
0x18004cfb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cfb5  test    eax, eax
0x18004cfb7  js      short loc_18004D003
0x18004cfb9  mov     r8d, 10h; Size
0x18004cfbf  lea     rdx, [rbp+80h+Buf2]; Buf2
0x18004cfc3  lea     rcx, MFVideoFormat_MSS1; Buf1
0x18004cfca  call    memcmp_0
0x18004cfcf  test    eax, eax
0x18004cfd1  jz      short loc_18004D003
0x18004cfd3  mov     rcx, [rsi+160h]
0x18004cfda  mov     rdx, qword ptr [rbp+80h+pvar+8]
0x18004cfde  lea     rax, [rcx+rcx]
0x18004cfe2  cmp     rdx, rax
0x18004cfe5  jle     short loc_18004CFED
0x18004cfe7  mov     qword ptr [rbp+80h+pvar+8], rcx
0x18004cfeb  jmp     short loc_18004D010
0x18004cfed  cmp     rdx, rcx
0x18004cff0  jl      short loc_18004D003
0x18004cff2  mov     rax, rdx
0x18004cff5  cqo
0x18004cff7  sub     rax, rdx
0x18004cffa  sar     rax, 1
0x18004cffd  mov     qword ptr [rbp+80h+pvar+8], rax
0x18004d001  jmp     short loc_18004D010
0x18004d003  xor     eax, eax
0x18004d005  xorps   xmm0, xmm0
0x18004d008  mov     qword ptr [rbp+80h+pvar+10h], rax
0x18004d00c  movups  xmmword ptr [rbp+80h+pvar], xmm0
0x18004d010  mov     eax, 14h
0x18004d015  lea     rcx, [rsp+180h+var_118]
0x18004d01a  mov     word ptr [rbp+80h+pvar], ax
0x18004d01e  mov     rax, [r14]
0x18004d021  mov     rbx, [rax+30h]
0x18004d025  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d02a  mov     edx, [rsi+18h]
0x18004d02d  lea     r8, [rsp+180h+var_118]
0x18004d032  mov     rcx, r14
0x18004d035  mov     rax, rbx
0x18004d038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d03d  mov     ebx, eax
0x18004d03f  test    eax, eax
0x18004d041  jns     short loc_18004D09D
0x18004d043  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d04a  test    rcx, rcx
0x18004d04d  jnz     short loc_18004D05B
0x18004d04f  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004d054  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004d05b  cmp     [rcx+8], r13b
0x18004d05f  jz      short loc_18004D086
0x18004d061  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004d066  cmp     [rax+7CCh], ebx
0x18004d06c  jz      short loc_18004D086
0x18004d06e  mov     r9d, ebx; int
0x18004d071  lea     rdx, aCmfvideothumbn_15; "CMFVideoThumbnail::GetRepresentativeFra"...
0x18004d078  mov     r8d, 45Eh; int
0x18004d07e  mov     rcx, rax; this
0x18004d081  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004d086  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004d08d  jb      loc_18004DDA2
0x18004d093  mov     edx, 55h ; 'U'
0x18004d098  jmp     loc_18004CDAF
0x18004d09d  mov     rcx, [rsp+180h+var_118]
0x18004d0a2  lea     r9, [rbp+80h+var_100]
0x18004d0a6  lea     r8, [rsp+180h+var_110]
0x18004d0ab  lea     rdx, MF_MT_FRAME_SIZE
0x18004d0b2  call    MFGetAttribute2UINT32asUINT64
0x18004d0b7  mov     ebx, eax
0x18004d0b9  test    eax, eax
0x18004d0bb  jns     short loc_18004D117
0x18004d0bd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d0c4  test    rcx, rcx
0x18004d0c7  jnz     short loc_18004D0D5
0x18004d0c9  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004d0ce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004d0d5  cmp     [rcx+8], r13b
0x18004d0d9  jz      short loc_18004D100
0x18004d0db  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004d0e0  cmp     [rax+7CCh], ebx
0x18004d0e6  jz      short loc_18004D100
0x18004d0e8  mov     r9d, ebx; int
0x18004d0eb  lea     rdx, aCmfvideothumbn_15; "CMFVideoThumbnail::GetRepresentativeFra"...
0x18004d0f2  mov     r8d, 45Fh; int
0x18004d0f8  mov     rcx, rax; this
0x18004d0fb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004d100  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004d107  jb      loc_18004DDA2
0x18004d10d  mov     edx, 56h ; 'V'
0x18004d112  jmp     loc_18004CDAF
0x18004d117  mov     rcx, [rsp+180h+var_118]
0x18004d11c  lea     r8, [rbp+80h+Buf2]
0x18004d120  lea     rdx, MF_MT_SUBTYPE
0x18004d127  mov     rax, [rcx]
0x18004d12a  mov     rax, [rax+50h]
0x18004d12e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d133  mov     ebx, eax
  ... truncated ...
```
