# CMFVideoThumbnail::GetRepresentativeFrame(IMFSourceReader *,IMFSample * *,IMFMediaType * *)

- ea: `0x18006860c`
- end: `0x1800697d9`
- name: `?GetRepresentativeFrame@CMFVideoThumbnail@@AEAAJPEAUIMFSourceReader@@PEAPEAUIMFSample@@PEAPEAUIMFMediaType@@@Z`
- size: `4557`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFSourceReader *, struct IMFSample **, struct IMFMediaType **)`
- caller_count: `1`
- callee_count: `33`
- tags: `broker_com_uri`

## callers

- `0x180067c44`

## callees

- `0x180001a5c`
- `0x180001b20`
- `0x1800023e0`
- `0x1800036b9`
- `0x180005ab8`
- `0x1800090dc`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d44`
- `0x180020d84`
- `0x180020e54`
- `0x180051c90`
- `0x1800644a4`
- `0x1800645a8`
- `0x180064d5c`
- `0x180067afc`
- `0x1800681f8`
- `0x180068280`
- `0x18006860c`
- `0x1800697e0`
- `0x180069acc`
- `0x18006b298`
- `0x18006b7d0`
- `0x18006bbe4`
- `0x18006bf54`
- `0x18006c018`
- `0x18006c16c`
- `0x18006c380`
- `0x1800712e8`
- `0x180071330`
- `0x180071524`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180069412`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180069412`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006949e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800694cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006949e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800694cf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180068e16`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180068e16`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  unsigned int v34; // r15d
  CallStackTracing *v35; // rcx
  struct CallStackContext *v36; // rax
  CMFVideoThumbnail *v37; // rcx
  CallStackTracing *v38; // rcx
  struct CallStackContext *v39; // rax
  unsigned int BytesPerPixel; // eax
  unsigned int v41; // edx
  unsigned int v42; // r9d
  CallStackTracing *v43; // rcx
  struct CallStackContext *v44; // rax
  float v45; // xmm7_4
  float v46; // xmm8_4
  int v47; // r12d
  __int64 v48; // rdx
  HRESULT (__stdcall *ReadSample)(IMFSourceReader *, DWORD, DWORD, DWORD *, DWORD *, LONGLONG *, IMFSample **); // rax
  __int64 v50; // rax
  __int64 v51; // rcx
  __int64 v52; // r15
  HRESULT (__stdcall *v53)(IMFSourceReader *, DWORD, IMFMediaType **); // rbx
  CMFVideoThumbnail *v54; // rcx
  unsigned int v55; // r15d
  CMFVideoThumbnail *v56; // rcx
  unsigned int v57; // eax
  unsigned int v58; // edx
  unsigned int v59; // r9d
  struct IMFSample *v60; // rdx
  CallStackTracing *v61; // rcx
  struct CallStackContext *v62; // rax
  __int64 v63; // rdx
  CallStackTracing *v64; // rcx
  struct CallStackContext *v65; // rax
  CallStackTracing *v66; // rcx
  struct CallStackContext *v67; // rax
  CallStackTracing *v68; // rcx
  struct CallStackContext *v69; // rax
  CallStackTracing *v70; // rcx
  struct CallStackContext *v71; // rax
  CallStackTracing *v72; // rcx
  struct CallStackContext *v73; // rax
  CallStackTracing *v74; // rcx
  struct CallStackContext *v75; // rax
  __int64 v76; // rdx
  CallStackTracing *v77; // rcx
  struct CallStackContext *v78; // rax
  __int64 v79; // rdx
  int v80; // ecx
  __int64 v81; // r8
  struct IMFSample *v82; // r15
  __int64 v83; // rdx
  CallStackTracing *v84; // rcx
  struct CallStackContext *v85; // rax
  __int64 v86; // r8
  int v87; // r13d
  int v88; // edi
  __int64 v89; // r8
  struct IMFMediaType **v90; // rcx
  __int64 v91; // rcx
  __int64 v92; // rcx
  __int64 v93; // r9
  GUID *v94; // rax
  __int64 v95; // rcx
  int v96; // ecx
  int v97; // r8d
  int v98; // r9d
  CallStackTracing *v99; // rcx
  struct CallStackContext *v100; // rax
  unsigned int v102; // [rsp+20h] [rbp-E0h]
  unsigned int v103; // [rsp+20h] [rbp-E0h]
  _BYTE v104[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v105; // [rsp+64h] [rbp-9Ch] BYREF
  struct IMFMediaType *v106; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v107; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v108; // [rsp+74h] [rbp-8Ch] BYREF
  GUID *v109; // [rsp+78h] [rbp-88h] BYREF
  int v110; // [rsp+80h] [rbp-80h]
  int v111; // [rsp+84h] [rbp-7Ch] BYREF
  int v112; // [rsp+88h] [rbp-78h] BYREF
  struct IMFMediaType *v113; // [rsp+90h] [rbp-70h] BYREF
  float v114; // [rsp+98h] [rbp-68h] BYREF
  float v115; // [rsp+9Ch] [rbp-64h] BYREF
  struct IMFSample *v116; // [rsp+A0h] [rbp-60h] BYREF
  PROPVARIANT pvar; // [rsp+A8h] [rbp-58h] BYREF
  struct IMFSample **v118; // [rsp+C0h] [rbp-40h] BYREF
  struct _GUID Buf2; // [rsp+C8h] [rbp-38h] BYREF
  struct _GUID v120; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v121[2]; // [rsp+E8h] [rbp-18h] BYREF
  _MFVideoArea v122; // [rsp+F8h] [rbp-8h] BYREF
  GUID v123; // [rsp+108h] [rbp+8h] BYREF

  v4 = 0;
  v118 = a3;
  v108 = 0;
  v107 = 0;
  v105 = 0;
  v116 = 0;
  v106 = 0;
  v113 = 0;
  v121[0] = a4;
  memset(&pvar, 0, sizeof(pvar));
  v122 = 0;
  Buf2 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v104,
    "CMFVideoThumbnail::GetRepresentativeFrame",
    1050);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 50) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 296LL))(*((_QWORD *)this + 50));
    v11 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, GUID *))(**((_QWORD **)this + 50) + 280LL))(
                       *((_QWORD *)this + 50),
                       &v123);
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
  v16 = (struct _GUID *)&xmmword_1800D79D0;
  while ( 1 )
  {
    v120 = *v16;
    Stride = CMFVideoThumbnail::SetSupportedMediaType(this, a2, &v120);
    if ( Stride >= 0 )
      break;
    if ( ++v16 == (struct _GUID *)_dyn_tls_init_callback )
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
  if ( (unsigned __int8)byte_1800D78D3 >= 0x20u )
    WPP_SF_qs(*((_QWORD *)WPP_GLOBAL_Control + 17), v17, v18, (_DWORD)this, (__int64)&v120);
  CMFVideoThumbnail::TryPutCodecInThumbnailMode(this, a2);
  GetNativeMediaType = a2->lpVtbl->GetNativeMediaType;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v106);
  Stride = ((__int64 (__fastcall *)(struct IMFSourceReader *, __int64, _QWORD, struct IMFMediaType **))GetNativeMediaType)(
             a2,
             4294967292LL,
             0,
             &v106);
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
  Stride = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, struct _GUID *))v106->lpVtbl->GetGUID)(
             v106,
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
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v106);
  Stride = ((__int64 (__fastcall *)(struct IMFSourceReader *, _QWORD, struct IMFMediaType **))GetCurrentMediaType)(
             a2,
             *((unsigned int *)this + 6),
             &v106);
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
  Stride = MFGetAttribute2UINT32asUINT64(v106, &MF_MT_FRAME_SIZE, &v108, &v107);
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
  Stride = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, struct _GUID *))v106->lpVtbl->GetGUID)(
             v106,
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
  v34 = v108;
  Stride = CMFVideoThumbnail::GetStride(this, v106, v108, &v105);
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
  Stride = CMFVideoThumbnail::GetMinDisplayAperture(this, v106, v34, v107, &v122);
  if ( Stride < 0 )
  {
    v38 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v38 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v38 + 8) )
    {
      v39 = CallStackTracing::GetThreadRelativeContext(v38);
      if ( *((_DWORD *)v39 + 499) != Stride )
        CallStackContext::TraceFailure(v39, "CMFVideoThumbnail::GetRepresentativeFrame", 1122, Stride);
    }
    if ( !g_wppLevels )
      goto LABEL_238;
    v15 = 89;
    goto LABEL_12;
  }
  BytesPerPixel = CMFVideoThumbnail::GetBytesPerPixel(v37, &Buf2);
  Stride = CMFVideoThumbnail::CalcOffsetsForComparison(this, v41, BytesPerPixel, v42, v102, &v122);
  if ( Stride < 0 )
  {
    v43 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v43 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v43 + 8) )
    {
      v44 = CallStackTracing::GetThreadRelativeContext(v43);
      if ( *((_DWORD *)v44 + 499) != Stride )
        CallStackContext::TraceFailure(v44, "CMFVideoThumbnail::GetRepresentativeFrame", 1124, Stride);
    }
    if ( !g_wppLevels )
      goto LABEL_238;
    v15 = 90;
LABEL_12:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, Stride);
    goto LABEL_238;
  }
  v110 = 0;
  v45 = 0.0;
  v112 = 0;
  v46 = 0.0;
  v47 = 0;
  v111 = 0;
  if ( (unsigned __int8)byte_1800D78D3 >= 0x20u )
    WPP_SF_qi(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      91,
      &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids,
      this,
      pvar.hVal.QuadPart / 10000);
  ((void (__fastcall *)(struct IMFSourceReader *, GUID *, PROPVARIANT *))a2->lpVtbl->SetCurrentPosition)(
    a2,
    &GUID_00000000_0000_0000_0000_000000000000,
    &pvar);
  while ( 1 )
  {
    v48 = *((unsigned int *)this + 6);
    ReadSample = a2->lpVtbl->ReadSample;
    v109 = 0;
    Stride = ((__int64 (__fastcall *)(struct IMFSourceReader *, __int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))ReadSample)(
               a2,
               v48,
               0,
               0,
               0,
               0,
               0);
    if ( Stride < 0 )
    {
      v99 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v99 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v99 + 8) )
      {
        v100 = CallStackTracing::GetThreadRelativeContext(v99);
        if ( *((_DWORD *)v100 + 499) != Stride )
          CallStackContext::TraceFailure(v100, "CMFVideoThumbnail::GetRepresentativeFrame", 1141, Stride);
      }
      if ( !g_wppLevels )
        goto LABEL_237;
      v63 = 92;
      goto LABEL_236;
    }
    ++v47;
    v50 = CMFVideoThumbnail::ElapsedTime(this);
    v51 = *((_QWORD *)this + 45);
    *(_QWORD *)&v120.Data1 = v50;
    if ( v51 <= v50 )
    {
      if ( (unsigned __int8)byte_1800D78D3 >= 0x20u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 95, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this);
      v112 = 2;
      goto LABEL_200;
    }
    v52 = (v51 - v50) / 10000;
    if ( (unsigned __int8)byte_1800D78D3 >= 0x20u )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 17), 93, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, v52);
    if ( WaitForSingleObject(*((HANDLE *)this + 46), v52) == 258 )
    {
      if ( (unsigned __int8)byte_1800D78D3 >= 0x20u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 94, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this);
      v112 = 1;
LABEL_200:
      v110 = 1;
      goto LABEL_201;
    }
    Stride = *((_DWORD *)this + 94);
    if ( Stride < 0 )
    {
      v77 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v77 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v77 + 8) )
      {
        v78 = CallStackTracing::GetThreadRelativeContext(v77);
        if ( *((_DWORD *)v78 + 499) != Stride )
          CallStackContext::TraceFailure(v78, "CMFVideoThumbnail::GetRepresentativeFrame", 1180, Stride);
      }
      if ( !g_wppLevels )
        goto LABEL_237;
      v63 = 96;
      goto LABEL_236;
    }
    if ( (*((_BYTE *)this + 380) & 0x20) != 0 )
    {
      v53 = a2->lpVtbl->GetCurrentMediaType;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v113);
      Stride = ((__int64 (__fastcall *)(struct IMFSourceReader *, _QWORD, struct IMFMediaType **))v53)(
                 a2,
                 *((unsigned int *)this + 6),
                 &v113);
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
            CallStackContext::TraceFailure(v75, "CMFVideoThumbnail::GetRepresentativeFrame", 1184, Stride);
        }
        if ( !g_wppLevels )
          goto LABEL_237;
        v63 = 97;
      }
      else
      {
        if ( !(unsigned int)CMFVideoThumbnail::IsSupportedMediaType(v54, v113) )
        {
          v72 = CallStackTracing::s_wpInstance;
          Stride = -1072875854;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v72 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v72 + 8) )
          {
            v73 = CallStackTracing::GetThreadRelativeContext(v72);
            if ( *((_DWORD *)v73 + 499) != -1072875854 )
              CallStackContext::TraceFailure(v73, "CMFVideoThumbnail::GetRepresentativeFrame", 1187, -1072875854);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              98,
              &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids,
              this,
              -1072875854);
          goto LABEL_237;
        }
        Stride = MFGetAttribute2UINT32asUINT64(v113, &MF_MT_FRAME_SIZE, &v108, &v107);
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
              CallStackContext::TraceFailure(v71, "CMFVideoThumbnail::GetRepresentativeFrame", 1193, Stride);
          }
          if ( !g_wppLevels )
            goto LABEL_237;
          v63 = 99;
        }
        else
        {
          Stride = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, struct _GUID *))v113->lpVtbl->GetGUID)(
                     v113,
                     &MF_MT_SUBTYPE,
                     &Buf2);
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
                CallStackContext::TraceFailure(v69, "CMFVideoThumbnail::GetRepresentativeFrame", 1194, Stride);
            }
            if ( !g_wppLevels )
              goto LABEL_237;
            v63 = 100;
          }
          else
          {
            v55 = v108;
            Stride = CMFVideoThumbnail::GetStride(this, v113, v108, &v105);
            if ( Stride < 0 )
            {
              v66 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::InitInstance();
                v66 = CallStackTracing::s_wpInstance;
              }
              if ( *((_BYTE *)v66 + 8) )
              {
                v67 = CallStackTracing::GetThreadRelativeContext(v66);
                if ( *((_DWORD *)v67 + 499) != Stride )
                  CallStackContext::TraceFailure(v67, "CMFVideoThumbnail::GetRepresentativeFrame", 1195, Stride);
              }
              if ( !g_wppLevels )
                goto LABEL_237;
              v63 = 101;
            }
            else
            {
              Stride = CMFVideoThumbnail::GetMinDisplayAperture(this, v113, v55, v107, &v122);
              if ( Stride < 0 )
              {
                v64 = CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  CallStackTracing::InitInstance();
                  v64 = CallStackTracing::s_wpInstance;
                }
                if ( *((_BYTE *)v64 + 8) )
                {
                  v65 = CallStackTracing::GetThreadRelativeContext(v64);
                  if ( *((_DWORD *)v65 + 499) != Stride )
                    CallStackContext::TraceFailure(v65, "CMFVideoThumbnail::GetRepresentativeFrame", 1196, Stride);
                }
                if ( !g_wppLevels )
                  goto LABEL_237;
                v63 = 102;
              }
              else
              {
                v57 = CMFVideoThumbnail::GetBytesPerPixel(v56, &Buf2);
                Stride = CMFVideoThumbnail::CalcOffsetsForComparison(this, v58, v57, v59, v103, &v122);
                if ( Stride >= 0 )
                {
                  v4 = 1;
                  goto LABEL_115;
                }
                v61 = CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  CallStackTracing::InitInstance();
                  v61 = CallStackTracing::s_wpInstance;
                }
                if ( *((_BYTE *)v61 + 8) )
                {
                  v62 = CallStackTracing::GetThreadRelativeContext(v61);
                  if ( *((_DWORD *)v62 + 499) != Stride )
                    CallStackContext::TraceFailure(v62, "CMFVideoThumbnail::GetRepresentativeFrame", 1198, Stride);
                }
                if ( !g_wppLevels )
                {
LABEL_237:
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v109);
                  goto LABEL_238;
                }
                v63 = 103;
              }
            }
          }
        }
      }
LABEL_236:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v63,
        &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids,
        this,
        Stride);
      goto LABEL_237;
    }
    v55 = v108;
LABEL_115:
    v60 = (struct IMFSample *)*((_QWORD *)this + 4);
    if ( v60 )
    {
      v115 = 0.0;
      v114 = 0.0;
      if ( (int)CMFVideoThumbnail::AnalyzeSample(this, v60, &Buf2, v55, v107, &v114, &v115) < 0 )
      {
        if ( v45 == 0.0 && v46 == 0.0 )
        {
          Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfSource>::operator=(&v116, *((_QWORD *)this + 4));
          if ( v4 )
          {
            Microsoft::WRL::ComPtr<IMFMediaType>::operator=(&v106, &v113);
            v4 = 0;
          }
          v111 = v47;
        }
      }
      else
      {
        if ( v114 >= v45 && v115 >= v46 )
        {
          v46 = v115;
          v45 = v114;
          Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfSource>::operator=(&v116, *((_QWORD *)this + 4));
          if ( v4 )
          {
            Microsoft::WRL::ComPtr<IMFMediaType>::operator=(&v106, &v113);
            v4 = 0;
          }
          v111 = v47;
        }
        if ( v45 > *((float *)this + 97) && v46 > *((float *)this + 98) )
          goto LABEL_201;
      }
    }
    if ( (*((_BYTE *)this + 380) & 2) != 0 )
      break;
    if ( v47 == *((_DWORD *)this + 96) )
    {
      if ( (unsigned __int8)byte_1800D78D3 >= 0x20u )
      {
        v76 = 105;
        goto LABEL_186;
      }
      goto LABEL_201;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v109);
  }
  if ( (unsigned __int8)byte_1800D78D3 >= 0x20u )
  {
    v76 = 104;
LABEL_186:
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), v76, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this);
  }
LABEL_201:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v109);
  v82 = v116;
  if ( v116 )
  {
    v88 = v111;
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
    v83 = *((_QWORD *)this + 4);
    if ( !v83 )
    {
      v84 = CallStackTracing::s_wpInstance;
      Stride = -1072875854;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v84 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v84 + 8) )
      {
        v85 = CallStackTracing::GetThreadRelativeContext(v84);
        if ( *((_DWORD *)v85 + 499) != -1072875854 )
          CallStackContext::TraceFailure(v85, "CMFVideoThumbnail::GetRepresentativeFrame", 1283, -1072875854);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          106,
          &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids,
          this,
          -1072875854);
      LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
      v87 = v110;
      goto LABEL_221;
    }
    Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfSource>::operator=(&v116, v83);
    if ( v4 )
      Microsoft::WRL::ComPtr<IMFMediaType>::operator=(&v106, &v113);
    v88 = v47;
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
    v82 = v116;
  }
  v87 = v110;
  if ( (unsigned __int8)byte_1800D78D3 >= 0x20u )
  {
    WPP_SF_qddggd(*((_QWORD *)WPP_GLOBAL_Control + 17), v79, v81, this, v88, v47, v45, v46, v110);
    if ( (unsigned __int8)byte_1800D78D3 >= 0x20u )
      WPP_SF_qPPl(*((_QWORD *)WPP_GLOBAL_Control + 17), v108, v89, this, v108, v107, v105);
  }
  if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
    McTemplateU0pqqqxt_EventWriteTransfer(
      v80,
      v79,
      (_DWORD)this,
      *((_DWORD *)this + 7),
      v88,
      v47,
      *((_QWORD *)this + 45),
      v87);
  ((void (__fastcall *)(struct IMFSourceReader *, _QWORD))a2->lpVtbl->Flush)(a2, *((unsigned int *)this + 6));
  v90 = (struct IMFMediaType **)v121[0];
  v116 = 0;
  *v118 = v82;
  *v90 = v106;
  v106 = 0;
LABEL_221:
  if ( v87 )
  {
    v91 = *((_QWORD *)this + 50);
    if ( !v91
      || !(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v91 + 320LL))(
            v91,
            MF_TELEMETRY_EVENT_RATE_EXCEEDED_LIMIT) )
    {
      v92 = *((_QWORD *)this + 50);
      v93 = 0;
      v123 = GUID_00000000_0000_0000_0000_000000000000;
      if ( v92 )
      {
        v94 = (GUID *)(*(__int64 (__fastcall **)(__int64, _QWORD *, __int64, _QWORD))(*(_QWORD *)v92 + 280LL))(
                        v92,
                        v121,
                        v86,
                        0);
        v95 = *((_QWORD *)this + 50);
        v123 = *v94;
        v93 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v95 + 296LL))(v95);
      }
      if ( (unsigned int)dword_1800D00D0 > 2
        && (unsigned __int8)tlgKeywordOn(&dword_1800D00D0, 0x400000000000LL, v86, v93) )
      {
        v118 = (struct IMFSample **)*((_QWORD *)this + 45);
        v114 = *(float *)&v112;
        v112 = *((_DWORD *)this + 7);
        v109 = &v123;
        v121[0] = 0x1000000;
        v115 = *(float *)&Stride;
        v111 = v98;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v96,
          (unsigned int)word_1800C55C2,
          v97,
          v98,
          (__int64)&v109,
          (__int64)&v111,
          (__int64)&v112,
          (__int64)&v114,
          (__int64)&v118,
          (__int64)&v120,
          (__int64)&v115,
          (__int64)v121);
      }
    }
  }
LABEL_238:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v104);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v113);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v106);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
  CMFPropVariant::Clear(&pvar);
  return (unsigned int)Stride;
}

```

## disassembly

```asm
0x18006860c  mov     rax, rsp
0x18006860f  push    rbp
0x180068610  push    rbx
0x180068611  push    rsi
0x180068612  push    rdi
0x180068613  push    r12
0x180068615  push    r13
0x180068617  push    r14
0x180068619  push    r15
0x18006861b  lea     rbp, [rsp-48h]
0x180068620  sub     rsp, 148h
0x180068627  movaps  xmmword ptr [rax-58h], xmm7
0x18006862b  movaps  xmmword ptr [rax-68h], xmm8
0x180068630  mov     rax, cs:__security_cookie
0x180068637  xor     rax, rsp
0x18006863a  mov     [rbp+80h+var_68], rax
0x18006863e  xor     r13d, r13d
0x180068641  mov     [rbp+80h+var_C0], r8
0x180068645  xorps   xmm0, xmm0
0x180068648  mov     [rsp+180h+var_10C], r13d
0x18006864d  mov     r15, r8
0x180068650  mov     [rsp+180h+var_110], r13d
0x180068655  mov     r14, rdx
0x180068658  mov     [rsp+180h+var_11C], r13d
0x18006865d  mov     rsi, rcx
0x180068660  mov     [rbp+80h+var_E0], r13
0x180068664  xor     eax, eax
0x180068666  mov     [rsp+180h+var_118], r13
0x18006866b  xorps   xmm1, xmm1
0x18006866e  mov     qword ptr [rbp+80h+pvar+10h], rax
0x180068672  mov     r8d, 41Ah; int
0x180068678  mov     [rbp+80h+var_F0], r13
0x18006867c  lea     rdx, aCmfvideothumbn_15; "CMFVideoThumbnail::GetRepresentativeFra"...
0x180068683  mov     [rbp+80h+var_98], r9
0x180068687  lea     rcx, [rsp+180h+var_120]; this
0x18006868c  mov     r12, r9
0x18006868f  movups  xmmword ptr [rbp+80h+pvar], xmm0
0x180068693  movups  xmmword ptr [rbp+80h+var_88.OffsetX.fract], xmm0
0x180068697  movups  [rbp+80h+Buf2], xmm1
0x18006869b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800686a0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800686a7  cmp     [rcx+8], r13b
0x1800686ab  jz      short loc_180068707
0x1800686ad  cmp     [rsi+190h], r13
0x1800686b4  jz      short loc_180068707
0x1800686b6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800686bb  mov     rdx, [rsi+190h]
0x1800686c2  mov     rdi, rax
0x1800686c5  mov     rcx, [rdx]
0x1800686c8  mov     rax, [rcx+128h]
0x1800686cf  mov     rcx, rdx
0x1800686d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800686d7  mov     r8, [rsi+190h]
0x1800686de  lea     rdx, [rbp+80h+var_78]
0x1800686e2  mov     ebx, eax
0x1800686e4  mov     rcx, [r8]
0x1800686e7  mov     rax, [rcx+118h]
0x1800686ee  mov     rcx, r8
0x1800686f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800686f6  movups  xmm0, xmmword ptr [rax]
0x1800686f9  mov     [rdi+7E0h], ebx
0x1800686ff  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180068707  mov     [r15], r13
0x18006870a  mov     rdx, r14; struct IMFSourceReader *
0x18006870d  mov     rcx, rsi; this
0x180068710  mov     [r12], r13
0x180068714  call    ?SelectPreferredVideoStream@CMFVideoThumbnail@@AEAAJPEAUIMFSourceReader@@@Z; CMFVideoThumbnail::SelectPreferredVideoStream(IMFSourceReader *)
0x180068719  mov     ebx, eax
0x18006871b  test    eax, eax
0x18006871d  jns     short loc_180068797
0x18006871f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180068726  test    rcx, rcx
0x180068729  jnz     short loc_180068737
0x18006872b  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180068730  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180068737  cmp     [rcx+8], r13b
0x18006873b  jz      short loc_180068762
0x18006873d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180068742  cmp     [rax+7CCh], ebx
0x180068748  jz      short loc_180068762
0x18006874a  mov     r9d, ebx; int
0x18006874d  lea     rdx, aCmfvideothumbn_15; "CMFVideoThumbnail::GetRepresentativeFra"...
0x180068754  mov     r8d, 420h; int
0x18006875a  mov     rcx, rax; this
0x18006875d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180068762  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180068769  jb      loc_18006977A
0x18006876f  mov     edx, 50h ; 'P'
0x180068774  mov     rcx, cs:WPP_GLOBAL_Control
0x18006877b  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x180068782  mov     r9, rsi
0x180068785  mov     dword ptr [rsp+180h+var_160], ebx
0x180068789  mov     rcx, [rcx+10h]
0x18006878d  call    WPP_SF_qD
0x180068792  jmp     loc_18006977A
0x180068797  lea     rdi, xmmword_1800D79D0
0x18006879e  movaps  xmm0, xmmword ptr [rdi]
0x1800687a1  lea     r8, [rbp+80h+var_A8]; struct _GUID *
0x1800687a5  mov     rdx, r14; struct IMFSourceReader *
0x1800687a8  mov     rcx, rsi; this
0x1800687ab  movdqu  xmmword ptr [rbp+80h+var_A8.Data1], xmm0
0x1800687b0  call    ?SetSupportedMediaType@CMFVideoThumbnail@@AEAAJPEAUIMFSourceReader@@AEBU_GUID@@@Z; CMFVideoThumbnail::SetSupportedMediaType(IMFSourceReader *,_GUID const &)
0x1800687b5  mov     ebx, eax
0x1800687b7  test    eax, eax
0x1800687b9  jns     short loc_180068825
0x1800687bb  add     rdi, 10h
0x1800687bf  lea     rax, __dyn_tls_init_callback
0x1800687c6  cmp     rdi, rax
0x1800687c9  jnz     short loc_18006879E
0x1800687cb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800687d2  test    rcx, rcx
0x1800687d5  jnz     short loc_1800687E3
0x1800687d7  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800687dc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800687e3  cmp     [rcx+8], r13b
0x1800687e7  jz      short loc_18006880E
0x1800687e9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800687ee  cmp     [rax+7CCh], ebx
0x1800687f4  jz      short loc_18006880E
0x1800687f6  mov     r9d, ebx; int
0x1800687f9  lea     rdx, aCmfvideothumbn_15; "CMFVideoThumbnail::GetRepresentativeFra"...
0x180068800  mov     r8d, 42Eh; int
0x180068806  mov     rcx, rax; this
0x180068809  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006880e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180068815  jb      loc_18006977A
0x18006881b  mov     edx, 52h ; 'R'
0x180068820  jmp     loc_180068774
0x180068825  cmp     cs:byte_1800D78D3, 20h ; ' '
0x18006882c  jb      short loc_18006884D
0x18006882e  mov     rcx, cs:WPP_GLOBAL_Control
0x180068835  lea     rax, [rbp+80h+var_A8]
0x180068839  mov     r9, rsi
0x18006883c  mov     [rsp+180h+var_160], rax
0x180068841  mov     rcx, [rcx+88h]
0x180068848  call    WPP_SF_qs
0x18006884d  mov     rdx, r14; struct IMFSourceReader *
0x180068850  mov     rcx, rsi; this
0x180068853  call    ?TryPutCodecInThumbnailMode@CMFVideoThumbnail@@AEAAXPEAUIMFSourceReader@@@Z; CMFVideoThumbnail::TryPutCodecInThumbnailMode(IMFSourceReader *)
0x180068858  mov     rax, [r14]
0x18006885b  lea     rcx, [rsp+180h+var_118]
0x180068860  mov     rbx, [rax+28h]
0x180068864  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180068869  lea     r9, [rsp+180h+var_118]
0x18006886e  xor     r8d, r8d
0x180068871  mov     edx, 0FFFFFFFCh
0x180068876  mov     rcx, r14
0x180068879  mov     rax, rbx
0x18006887c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068881  mov     ebx, eax
0x180068883  test    eax, eax
0x180068885  jns     short loc_1800688E1
0x180068887  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006888e  test    rcx, rcx
0x180068891  jnz     short loc_18006889F
0x180068893  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180068898  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18006889f  cmp     [rcx+8], r13b
0x1800688a3  jz      short loc_1800688CA
0x1800688a5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800688aa  cmp     [rax+7CCh], ebx
0x1800688b0  jz      short loc_1800688CA
0x1800688b2  mov     r9d, ebx; int
0x1800688b5  lea     rdx, aCmfvideothumbn_15; "CMFVideoThumbnail::GetRepresentativeFra"...
0x1800688bc  mov     r8d, 439h; int
0x1800688c2  mov     rcx, rax; this
0x1800688c5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800688ca  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800688d1  jb      loc_18006977A
0x1800688d7  mov     edx, 53h ; 'S'
0x1800688dc  jmp     loc_180068774
0x1800688e1  mov     rcx, [rsp+180h+var_118]
0x1800688e6  lea     r8, [rbp+80h+Buf2]
0x1800688ea  lea     rdx, MF_MT_SUBTYPE
0x1800688f1  mov     rax, [rcx]
0x1800688f4  mov     rax, [rax+50h]
0x1800688f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800688fd  mov     ebx, eax
0x1800688ff  test    eax, eax
0x180068901  jns     short loc_18006895D
0x180068903  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006890a  test    rcx, rcx
0x18006890d  jnz     short loc_18006891B
0x18006890f  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180068914  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18006891b  cmp     [rcx+8], r13b
0x18006891f  jz      short loc_180068946
0x180068921  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180068926  cmp     [rax+7CCh], ebx
0x18006892c  jz      short loc_180068946
0x18006892e  mov     r9d, ebx; int
0x180068931  lea     rdx, aCmfvideothumbn_15; "CMFVideoThumbnail::GetRepresentativeFra"...
0x180068938  mov     r8d, 43Ah; int
0x18006893e  mov     rcx, rax; this
0x180068941  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180068946  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006894d  jb      loc_18006977A
0x180068953  mov     edx, 54h ; 'T'
0x180068958  jmp     loc_180068774
0x18006895d  mov     rax, [r14]
0x180068960  lea     r9, [rbp+80h+pvar]
0x180068964  lea     r8, MF_PD_DURATION
0x18006896b  or      edx, 0FFFFFFFFh
0x18006896e  mov     rcx, r14
0x180068971  mov     rax, [rax+60h]
0x180068975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006897a  test    eax, eax
0x18006897c  js      short loc_1800689C8
0x18006897e  mov     r8d, 10h; Size
0x180068984  lea     rdx, [rbp+80h+Buf2]; Buf2
0x180068988  lea     rcx, MFVideoFormat_MSS1; Buf1
0x18006898f  call    memcmp_0
0x180068994  test    eax, eax
0x180068996  jz      short loc_1800689C8
0x180068998  mov     rcx, [rsi+160h]
0x18006899f  mov     rdx, qword ptr [rbp+80h+pvar+8]
0x1800689a3  lea     rax, [rcx+rcx]
0x1800689a7  cmp     rdx, rax
0x1800689aa  jle     short loc_1800689B2
0x1800689ac  mov     qword ptr [rbp+80h+pvar+8], rcx
0x1800689b0  jmp     short loc_1800689D5
0x1800689b2  cmp     rdx, rcx
0x1800689b5  jl      short loc_1800689C8
0x1800689b7  mov     rax, rdx
0x1800689ba  cqo
0x1800689bc  sub     rax, rdx
0x1800689bf  sar     rax, 1
0x1800689c2  mov     qword ptr [rbp+80h+pvar+8], rax
0x1800689c6  jmp     short loc_1800689D5
0x1800689c8  xor     eax, eax
0x1800689ca  xorps   xmm0, xmm0
0x1800689cd  mov     qword ptr [rbp+80h+pvar+10h], rax
0x1800689d1  movups  xmmword ptr [rbp+80h+pvar], xmm0
0x1800689d5  mov     eax, 14h
0x1800689da  lea     rcx, [rsp+180h+var_118]
0x1800689df  mov     word ptr [rbp+80h+pvar], ax
0x1800689e3  mov     rax, [r14]
0x1800689e6  mov     rbx, [rax+30h]
0x1800689ea  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800689ef  mov     edx, [rsi+18h]
0x1800689f2  lea     r8, [rsp+180h+var_118]
0x1800689f7  mov     rcx, r14
0x1800689fa  mov     rax, rbx
0x1800689fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068a02  mov     ebx, eax
0x180068a04  test    eax, eax
0x180068a06  jns     short loc_180068A62
0x180068a08  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180068a0f  test    rcx, rcx
0x180068a12  jnz     short loc_180068A20
0x180068a14  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180068a19  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180068a20  cmp     [rcx+8], r13b
0x180068a24  jz      short loc_180068A4B
0x180068a26  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180068a2b  cmp     [rax+7CCh], ebx
0x180068a31  jz      short loc_180068A4B
0x180068a33  mov     r9d, ebx; int
0x180068a36  lea     rdx, aCmfvideothumbn_15; "CMFVideoThumbnail::GetRepresentativeFra"...
0x180068a3d  mov     r8d, 45Eh; int
0x180068a43  mov     rcx, rax; this
0x180068a46  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180068a4b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180068a52  jb      loc_18006977A
0x180068a58  mov     edx, 55h ; 'U'
0x180068a5d  jmp     loc_180068774
0x180068a62  mov     rcx, [rsp+180h+var_118]
0x180068a67  lea     r9, [rsp+180h+var_110]
0x180068a6c  lea     r8, [rsp+180h+var_10C]
0x180068a71  lea     rdx, MF_MT_FRAME_SIZE
0x180068a78  call    MFGetAttribute2UINT32asUINT64
0x180068a7d  mov     ebx, eax
0x180068a7f  test    eax, eax
0x180068a81  jns     short loc_180068ADD
0x180068a83  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180068a8a  test    rcx, rcx
0x180068a8d  jnz     short loc_180068A9B
0x180068a8f  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180068a94  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180068a9b  cmp     [rcx+8], r13b
0x180068a9f  jz      short loc_180068AC6
0x180068aa1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180068aa6  cmp     [rax+7CCh], ebx
0x180068aac  jz      short loc_180068AC6
0x180068aae  mov     r9d, ebx; int
0x180068ab1  lea     rdx, aCmfvideothumbn_15; "CMFVideoThumbnail::GetRepresentativeFra"...
0x180068ab8  mov     r8d, 45Fh; int
0x180068abe  mov     rcx, rax; this
0x180068ac1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180068ac6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180068acd  jb      loc_18006977A
0x180068ad3  mov     edx, 56h ; 'V'
0x180068ad8  jmp     loc_180068774
0x180068add  mov     rcx, [rsp+180h+var_118]
0x180068ae2  lea     r8, [rbp+80h+Buf2]
0x180068ae6  lea     rdx, MF_MT_SUBTYPE
0x180068aed  mov     rax, [rcx]
0x180068af0  mov     rax, [rax+50h]
0x180068af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068af9  mov     ebx, eax
  ... truncated ...
```
