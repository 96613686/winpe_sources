# CMFVideoThumbnail::Generate(IStream *,tagPROPVARIANT *)

- ea: `0x180067c44`
- end: `0x1800681f0`
- name: `?Generate@CMFVideoThumbnail@@QEAAJPEAUIStream@@PEAUtagPROPVARIANT@@@Z`
- size: `1452`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, IStream *pStream, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800535e0`

## callees

- `0x1800023e0`
- `0x180005ab8`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180052754`
- `0x18006764c`
- `0x1800678b0`
- `0x180067c44`
- `0x18006860c`
- `0x180069a78`
- `0x180069c10`
- `0x18006bb9c`
- `0x18006bee4`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067d41`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067dec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067ed5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067f83`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006803e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800680e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067d41`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067dec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067ed5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067f83`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006803e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800680e6`
- `MFPlat!MFCreateMFByteStreamOnStream` at `0x180067dd0`
- `MFPlat!MFCreateMFByteStreamOnStream` at `0x180067dd0`

## pseudocode

```c
__int64 __fastcall CMFVideoThumbnail::Generate(CMFVideoThumbnail *this, IStream *pStream, struct tagPROPVARIANT *a3)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v7; // ebx
  __int128 v8; // xmm0
  __int64 v9; // rdx
  HRESULT started; // ebx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  struct IUnknown **v47; // rcx
  _BYTE v49[8]; // [rsp+30h] [rbp-40h] BYREF
  struct IMFSourceReader *v50; // [rsp+38h] [rbp-38h] BYREF
  struct IMFMediaType *v51; // [rsp+40h] [rbp-30h] BYREF
  struct IMFSample *v52; // [rsp+48h] [rbp-28h] BYREF
  IMFByteStream *ppByteStream; // [rsp+50h] [rbp-20h] BYREF
  _BYTE v54[16]; // [rsp+58h] [rbp-18h] BYREF

  if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
    McTemplateU0pq_EventWriteTransfer(
      this,
      Property_Handler_ThumbnailGeneration_Start,
      this,
      *((unsigned int *)this + 7));
  ppByteStream = 0;
  v50 = 0;
  v52 = 0;
  v51 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v49, "CMFVideoThumbnail::Generate", 317);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 50) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 296LL))(*((_QWORD *)this + 50));
    v8 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 50) + 280LL))(
                      *((_QWORD *)this + 50),
                      v54);
    *((_DWORD *)ThreadRelativeContext + 504) = v7;
    *((_OWORD *)ThreadRelativeContext + 125) = v8;
  }
  started = CMFVideoThumbnail::StartTiming(this);
  if ( started >= 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppByteStream);
    started = MFCreateMFByteStreamOnStream(pStream, &ppByteStream);
    if ( started >= 0 )
    {
      Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&v50);
      started = CMFVideoThumbnail::CreateSourceReaderFromMFSource(this, ppByteStream, &v50);
      if ( !started )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
        started = CMFVideoThumbnail::GetRepresentativeFrame(this, v50, &v52, &v51);
      }
      if ( started < 0 )
      {
        if ( (unsigned int)(*((_DWORD *)this + 7) - 4) > 1 )
        {
          v26 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24, v25);
            CallStackTracing::s_wpInstance = v27;
            if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
            {
              v26 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v26 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v26 + 8) )
          {
            v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
            if ( *((_DWORD *)v28 + 499) != started )
              CallStackContext::TraceFailure(v28, "CMFVideoThumbnail::Generate", 353, started);
          }
          if ( g_wppLevels )
          {
            v16 = 18;
            goto LABEL_75;
          }
          goto LABEL_76;
        }
        Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&v50);
        started = CMFVideoThumbnail::CreateSourceReaderFromDShowSource(this, ppByteStream, &v50);
        if ( started < 0 )
        {
          v32 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30, v31);
            CallStackTracing::s_wpInstance = v33;
            if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
            {
              v32 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v32 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v32 + 8) )
          {
            v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
            if ( *((_DWORD *)v34 + 499) != started )
              CallStackContext::TraceFailure(v34, "CMFVideoThumbnail::Generate", 360, started);
          }
          if ( g_wppLevels )
          {
            v16 = 19;
            goto LABEL_75;
          }
          goto LABEL_76;
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
        started = CMFVideoThumbnail::GetRepresentativeFrame(this, v50, &v52, &v51);
        if ( started < 0 )
        {
          v38 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35, v36, v37);
            CallStackTracing::s_wpInstance = v39;
            if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
            {
              v38 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v38 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v38 + 8) )
          {
            v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
            if ( *((_DWORD *)v40 + 499) != started )
              CallStackContext::TraceFailure(v40, "CMFVideoThumbnail::Generate", 362, started);
          }
          if ( g_wppLevels )
          {
            v16 = 20;
            goto LABEL_75;
          }
          goto LABEL_76;
        }
      }
      started = CMFVideoThumbnail::MFSampleToThumbnailStream(this, v51, v52, a3);
      if ( started < 0 )
      {
        v44 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v42, v43);
          CallStackTracing::s_wpInstance = v45;
          if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
          {
            v44 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v44 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v44 + 8) )
        {
          v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
          if ( *((_DWORD *)v46 + 499) != started )
            CallStackContext::TraceFailure(v46, "CMFVideoThumbnail::Generate", 365, started);
        }
        if ( g_wppLevels )
        {
          v16 = 21;
          goto LABEL_75;
        }
      }
      goto LABEL_76;
    }
    v20 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17, v18, v19);
      CallStackTracing::s_wpInstance = v21;
      if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
      {
        v20 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v20 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v20 + 8) )
    {
      v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
      if ( *((_DWORD *)v22 + 499) != started )
        CallStackContext::TraceFailure(v22, "CMFVideoThumbnail::Generate", 332, started);
    }
    if ( g_wppLevels )
    {
      v16 = 17;
      goto LABEL_75;
    }
  }
  else
  {
    v13 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v11, v12);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v13 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)v15 + 499) != started )
        CallStackContext::TraceFailure(v15, "CMFVideoThumbnail::Generate", 319, started);
    }
    if ( g_wppLevels )
    {
      v16 = 16;
LABEL_75:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids,
        this,
        started);
    }
  }
LABEL_76:
  v47 = (struct IUnknown **)((char *)this + 32);
  if ( *((_QWORD *)this + 4) )
    ATL::AtlComPtrAssign(v47, 0);
  if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
    McTemplateU0pq_EventWriteTransfer(v47, Property_Handler_ThumbnailGeneration_End, this, *((unsigned int *)this + 7));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v49);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
  Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&v50);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppByteStream);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x180067c44  push    rbp
0x180067c46  push    rbx
0x180067c47  push    rsi
0x180067c48  push    rdi
0x180067c49  push    r12
0x180067c4b  push    r14
0x180067c4d  push    r15
0x180067c4f  mov     rbp, rsp
0x180067c52  sub     rsp, 70h
0x180067c56  mov     rax, cs:__security_cookie
0x180067c5d  xor     rax, rsp
0x180067c60  mov     [rbp+var_8], rax
0x180067c64  test    cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 1
0x180067c6b  mov     r15, r8
0x180067c6e  mov     r14, rdx
0x180067c71  mov     rsi, rcx
0x180067c74  jz      short loc_180067C89
0x180067c76  mov     r9d, [rcx+1Ch]
0x180067c7a  lea     rdx, Property_Handler_ThumbnailGeneration_Start
0x180067c81  mov     r8, rcx
0x180067c84  call    McTemplateU0pq_EventWriteTransfer
0x180067c89  xor     r12d, r12d
0x180067c8c  lea     rdi, aCmfvideothumbn_6; "CMFVideoThumbnail::Generate"
0x180067c93  mov     rdx, rdi; char *
0x180067c96  mov     [rbp+ppByteStream], r12
0x180067c9a  mov     r8d, 13Dh; int
0x180067ca0  mov     [rbp+var_38], r12
0x180067ca4  lea     rcx, [rbp+var_40]; this
0x180067ca8  mov     [rbp+var_28], r12
0x180067cac  mov     [rbp+var_30], r12
0x180067cb0  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180067cb5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180067cbc  cmp     [rcx+8], r12b
0x180067cc0  jz      short loc_180067D23
0x180067cc2  cmp     [rsi+190h], r12
0x180067cc9  jz      short loc_180067D23
0x180067ccb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180067cd0  mov     rdx, [rsi+190h]
0x180067cd7  mov     rdi, rax
0x180067cda  mov     rcx, [rdx]
0x180067cdd  mov     rax, [rcx+128h]
0x180067ce4  mov     rcx, rdx
0x180067ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067cec  mov     r8, [rsi+190h]
0x180067cf3  lea     rdx, [rbp+var_18]
0x180067cf7  mov     ebx, eax
0x180067cf9  mov     rcx, [r8]
0x180067cfc  mov     rax, [rcx+118h]
0x180067d03  mov     rcx, r8
0x180067d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067d0b  movups  xmm0, xmmword ptr [rax]
0x180067d0e  mov     [rdi+7E0h], ebx
0x180067d14  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180067d1c  lea     rdi, aCmfvideothumbn_6; "CMFVideoThumbnail::Generate"
0x180067d23  mov     rcx, rsi; this
0x180067d26  call    ?StartTiming@CMFVideoThumbnail@@AEAAJXZ; CMFVideoThumbnail::StartTiming(void)
0x180067d2b  mov     ebx, eax
0x180067d2d  test    eax, eax
0x180067d2f  jns     loc_180067DC0
0x180067d35  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067d3c  test    rcx, rcx
0x180067d3f  jnz     short loc_180067D82
0x180067d41  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180067d47  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180067d4e  mov     rcx, rax
0x180067d51  test    rax, rax
0x180067d54  jz      short loc_180067D74
0x180067d56  mov     rax, [rax]
0x180067d59  mov     edx, 7F0h
0x180067d5e  mov     rax, [rax+8]
0x180067d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067d67  test    eax, eax
0x180067d69  jz      short loc_180067D74
0x180067d6b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067d72  jmp     short loc_180067D82
0x180067d74  lea     rcx, qword_1800D6F70; this
0x180067d7b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180067d82  cmp     [rcx+8], r12b
0x180067d86  jz      short loc_180067DA9
0x180067d88  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180067d8d  cmp     [rax+7CCh], ebx
0x180067d93  jz      short loc_180067DA9
0x180067d95  mov     r9d, ebx; int
0x180067d98  mov     r8d, 13Fh; int
0x180067d9e  mov     rdx, rdi; char *
0x180067da1  mov     rcx, rax; this
0x180067da4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180067da9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180067db0  jb      loc_18006817A
0x180067db6  mov     edx, 10h
0x180067dbb  jmp     loc_18006815C
0x180067dc0  lea     rcx, [rbp+ppByteStream]
0x180067dc4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180067dc9  lea     rdx, [rbp+ppByteStream]; ppByteStream
0x180067dcd  mov     rcx, r14; pStream
0x180067dd0  call    cs:__imp_MFCreateMFByteStreamOnStream
0x180067dd6  mov     ebx, eax
0x180067dd8  test    eax, eax
0x180067dda  jns     loc_180067E6B
0x180067de0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067de7  test    rcx, rcx
0x180067dea  jnz     short loc_180067E2D
0x180067dec  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180067df2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180067df9  mov     rcx, rax
0x180067dfc  test    rax, rax
0x180067dff  jz      short loc_180067E1F
0x180067e01  mov     rax, [rax]
0x180067e04  mov     edx, 7F0h
0x180067e09  mov     rax, [rax+8]
0x180067e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067e12  test    eax, eax
0x180067e14  jz      short loc_180067E1F
0x180067e16  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067e1d  jmp     short loc_180067E2D
0x180067e1f  lea     rcx, qword_1800D6F70; this
0x180067e26  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180067e2d  cmp     [rcx+8], r12b
0x180067e31  jz      short loc_180067E54
0x180067e33  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180067e38  cmp     [rax+7CCh], ebx
0x180067e3e  jz      short loc_180067E54
0x180067e40  mov     r9d, ebx; int
0x180067e43  mov     r8d, 14Ch; int
0x180067e49  mov     rdx, rdi; char *
0x180067e4c  mov     rcx, rax; this
0x180067e4f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180067e54  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180067e5b  jb      loc_18006817A
0x180067e61  mov     edx, 11h
0x180067e66  jmp     loc_18006815C
0x180067e6b  lea     rcx, [rbp+var_38]
0x180067e6f  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x180067e74  mov     rdx, [rbp+ppByteStream]; struct IMFByteStream *
0x180067e78  lea     r8, [rbp+var_38]; struct IMFSourceReader **
0x180067e7c  mov     rcx, rsi; this
0x180067e7f  call    ?CreateSourceReaderFromMFSource@CMFVideoThumbnail@@AEAAJPEAUIMFByteStream@@PEAPEAUIMFSourceReader@@@Z; CMFVideoThumbnail::CreateSourceReaderFromMFSource(IMFByteStream *,IMFSourceReader * *)
0x180067e84  mov     ebx, eax
0x180067e86  test    eax, eax
0x180067e88  jnz     short loc_180067EB2
0x180067e8a  lea     rcx, [rbp+var_30]
0x180067e8e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180067e93  lea     rcx, [rbp+var_28]
0x180067e97  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180067e9c  mov     rdx, [rbp+var_38]; struct IMFSourceReader *
0x180067ea0  lea     r9, [rbp+var_30]; struct IMFMediaType **
0x180067ea4  lea     r8, [rbp+var_28]; struct IMFSample **
0x180067ea8  mov     rcx, rsi; this
0x180067eab  call    ?GetRepresentativeFrame@CMFVideoThumbnail@@AEAAJPEAUIMFSourceReader@@PEAPEAUIMFSample@@PEAPEAUIMFMediaType@@@Z; CMFVideoThumbnail::GetRepresentativeFrame(IMFSourceReader *,IMFSample * *,IMFMediaType * *)
0x180067eb0  mov     ebx, eax
0x180067eb2  test    ebx, ebx
0x180067eb4  jns     loc_1800680BD
0x180067eba  mov     eax, [rsi+1Ch]
0x180067ebd  sub     eax, 4
0x180067ec0  cmp     eax, 1
0x180067ec3  jbe     loc_180067F54
0x180067ec9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067ed0  test    rcx, rcx
0x180067ed3  jnz     short loc_180067F16
0x180067ed5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180067edb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180067ee2  mov     rcx, rax
0x180067ee5  test    rax, rax
0x180067ee8  jz      short loc_180067F08
0x180067eea  mov     rax, [rax]
0x180067eed  mov     edx, 7F0h
0x180067ef2  mov     rax, [rax+8]
0x180067ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067efb  test    eax, eax
0x180067efd  jz      short loc_180067F08
0x180067eff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067f06  jmp     short loc_180067F16
0x180067f08  lea     rcx, qword_1800D6F70; this
0x180067f0f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180067f16  cmp     [rcx+8], r12b
0x180067f1a  jz      short loc_180067F3D
0x180067f1c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180067f21  cmp     [rax+7CCh], ebx
0x180067f27  jz      short loc_180067F3D
0x180067f29  mov     r9d, ebx; int
0x180067f2c  mov     r8d, 161h; int
0x180067f32  mov     rdx, rdi; char *
0x180067f35  mov     rcx, rax; this
0x180067f38  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180067f3d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180067f44  jb      loc_18006817A
0x180067f4a  mov     edx, 12h
0x180067f4f  jmp     loc_18006815C
0x180067f54  lea     rcx, [rbp+var_38]
0x180067f58  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x180067f5d  mov     rdx, [rbp+ppByteStream]; struct IMFByteStream *
0x180067f61  lea     r8, [rbp+var_38]; struct IMFSourceReader **
0x180067f65  mov     rcx, rsi; this
0x180067f68  call    ?CreateSourceReaderFromDShowSource@CMFVideoThumbnail@@AEAAJPEAUIMFByteStream@@PEAPEAUIMFSourceReader@@@Z; CMFVideoThumbnail::CreateSourceReaderFromDShowSource(IMFByteStream *,IMFSourceReader * *)
0x180067f6d  mov     ebx, eax
0x180067f6f  test    eax, eax
0x180067f71  jns     loc_180068002
0x180067f77  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067f7e  test    rcx, rcx
0x180067f81  jnz     short loc_180067FC4
0x180067f83  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180067f89  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180067f90  mov     rcx, rax
0x180067f93  test    rax, rax
0x180067f96  jz      short loc_180067FB6
0x180067f98  mov     rax, [rax]
0x180067f9b  mov     edx, 7F0h
0x180067fa0  mov     rax, [rax+8]
0x180067fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067fa9  test    eax, eax
0x180067fab  jz      short loc_180067FB6
0x180067fad  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067fb4  jmp     short loc_180067FC4
0x180067fb6  lea     rcx, qword_1800D6F70; this
0x180067fbd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180067fc4  cmp     [rcx+8], r12b
0x180067fc8  jz      short loc_180067FEB
0x180067fca  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180067fcf  cmp     [rax+7CCh], ebx
0x180067fd5  jz      short loc_180067FEB
0x180067fd7  mov     r9d, ebx; int
0x180067fda  mov     r8d, 168h; int
0x180067fe0  mov     rdx, rdi; char *
0x180067fe3  mov     rcx, rax; this
0x180067fe6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180067feb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180067ff2  jb      loc_18006817A
0x180067ff8  mov     edx, 13h
0x180067ffd  jmp     loc_18006815C
0x180068002  lea     rcx, [rbp+var_30]
0x180068006  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006800b  lea     rcx, [rbp+var_28]
0x18006800f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180068014  mov     rdx, [rbp+var_38]; struct IMFSourceReader *
0x180068018  lea     r9, [rbp+var_30]; struct IMFMediaType **
0x18006801c  lea     r8, [rbp+var_28]; struct IMFSample **
0x180068020  mov     rcx, rsi; this
0x180068023  call    ?GetRepresentativeFrame@CMFVideoThumbnail@@AEAAJPEAUIMFSourceReader@@PEAPEAUIMFSample@@PEAPEAUIMFMediaType@@@Z; CMFVideoThumbnail::GetRepresentativeFrame(IMFSourceReader *,IMFSample * *,IMFMediaType * *)
0x180068028  mov     ebx, eax
0x18006802a  test    eax, eax
0x18006802c  jns     loc_1800680BD
0x180068032  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180068039  test    rcx, rcx
0x18006803c  jnz     short loc_18006807F
0x18006803e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180068044  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006804b  mov     rcx, rax
0x18006804e  test    rax, rax
0x180068051  jz      short loc_180068071
0x180068053  mov     rax, [rax]
0x180068056  mov     edx, 7F0h
0x18006805b  mov     rax, [rax+8]
0x18006805f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068064  test    eax, eax
0x180068066  jz      short loc_180068071
0x180068068  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006806f  jmp     short loc_18006807F
0x180068071  lea     rcx, qword_1800D6F70; this
0x180068078  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006807f  cmp     [rcx+8], r12b
0x180068083  jz      short loc_1800680A6
0x180068085  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006808a  cmp     [rax+7CCh], ebx
0x180068090  jz      short loc_1800680A6
0x180068092  mov     r9d, ebx; int
0x180068095  mov     r8d, 16Ah; int
0x18006809b  mov     rdx, rdi; char *
0x18006809e  mov     rcx, rax; this
0x1800680a1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800680a6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800680ad  jb      loc_18006817A
0x1800680b3  mov     edx, 14h
0x1800680b8  jmp     loc_18006815C
0x1800680bd  mov     r8, [rbp+var_28]; struct IMFSample *
0x1800680c1  mov     r9, r15; struct tagPROPVARIANT *
0x1800680c4  mov     rdx, [rbp+var_30]; struct IMFMediaType *
0x1800680c8  mov     rcx, rsi; this
0x1800680cb  call    ?MFSampleToThumbnailStream@CMFVideoThumbnail@@AEAAJPEAUIMFMediaType@@PEAUIMFSample@@PEAUtagPROPVARIANT@@@Z; CMFVideoThumbnail::MFSampleToThumbnailStream(IMFMediaType *,IMFSample *,tagPROPVARIANT *)
0x1800680d0  mov     ebx, eax
0x1800680d2  test    eax, eax
0x1800680d4  jns     loc_18006817A
0x1800680da  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800680e1  test    rcx, rcx
0x1800680e4  jnz     short loc_180068127
0x1800680e6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800680ec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800680f3  mov     rcx, rax
0x1800680f6  test    rax, rax
0x1800680f9  jz      short loc_180068119
0x1800680fb  mov     rax, [rax]
0x1800680fe  mov     edx, 7F0h
0x180068103  mov     rax, [rax+8]
0x180068107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006810c  test    eax, eax
0x18006810e  jz      short loc_180068119
0x180068110  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180068117  jmp     short loc_180068127
0x180068119  lea     rcx, qword_1800D6F70; this
0x180068120  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180068127  cmp     [rcx+8], r12b
  ... truncated ...
```
