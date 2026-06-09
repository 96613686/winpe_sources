# CMFVideoThumbnail::Generate(IStream *,tagPROPVARIANT *)

- ea: `0x18004c254`
- end: `0x18004c800`
- name: `?Generate@CMFVideoThumbnail@@QEAAJPEAUIStream@@PEAUtagPROPVARIANT@@@Z`
- size: `1452`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, IStream *pStream, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003bfb0`

## callees

- `0x180001e80`
- `0x180017e64`
- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x180048710`
- `0x18004bc64`
- `0x18004bec8`
- `0x18004c254`
- `0x18004cc48`
- `0x18004e1fc`
- `0x18005018c`
- `0x1800504d4`
- `0x180056010`

## import_xrefs

- `MFPlat!MFCreateMFByteStreamOnStream` at `0x18004c3e0`
- `MFPlat!MFCreateMFByteStreamOnStream` at `0x18004c3e0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c351`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c3fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c4e5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c593`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c64e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c6f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c351`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c3fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c4e5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c593`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c64e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c6f6`

## pseudocode

```c
__int64 __fastcall CMFVideoThumbnail::Generate(CMFVideoThumbnail *this, IStream *pStream, struct tagPROPVARIANT *a3)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v7; // ebx
  __int128 v8; // xmm0
  __int64 v9; // rdx
  HRESULT started; // ebx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  struct IUnknown **v35; // rcx
  _BYTE v37[8]; // [rsp+30h] [rbp-40h] BYREF
  struct IMFSourceReader *v38; // [rsp+38h] [rbp-38h] BYREF
  struct IMFMediaType *v39; // [rsp+40h] [rbp-30h] BYREF
  struct IMFSample *v40; // [rsp+48h] [rbp-28h] BYREF
  IMFByteStream *ppByteStream; // [rsp+50h] [rbp-20h] BYREF
  _BYTE v42[16]; // [rsp+58h] [rbp-18h] BYREF

  if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
    McTemplateU0pq_EventWriteTransfer(
      this,
      &Property_Handler_ThumbnailGeneration_Start,
      this,
      *((unsigned int *)this + 7));
  ppByteStream = 0;
  v38 = 0;
  v40 = 0;
  v39 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v37, "CMFVideoThumbnail::Generate", 317);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 50) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 296LL))(*((_QWORD *)this + 50));
    v8 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 50) + 280LL))(
                      *((_QWORD *)this + 50),
                      v42);
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
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
      started = CMFVideoThumbnail::CreateSourceReaderFromMFSource(this, ppByteStream, &v38);
      if ( !started )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
        started = CMFVideoThumbnail::GetRepresentativeFrame(this, v38, &v40, &v39);
      }
      if ( started < 0 )
      {
        if ( (unsigned int)(*((_DWORD *)this + 7) - 4) > 1 )
        {
          v20 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
            CallStackTracing::s_wpInstance = v21;
            if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
            {
              v20 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v20 = &qword_18006EB20;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
            }
          }
          if ( *((_BYTE *)v20 + 8) )
          {
            v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
            if ( *((_DWORD *)v22 + 499) != started )
              CallStackContext::TraceFailure(v22, "CMFVideoThumbnail::Generate", 353, started);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v14 = 18;
            goto LABEL_75;
          }
          goto LABEL_76;
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        started = CMFVideoThumbnail::CreateSourceReaderFromDShowSource(this, ppByteStream, &v38);
        if ( started < 0 )
        {
          v24 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
            CallStackTracing::s_wpInstance = v25;
            if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
            {
              v24 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v24 = &qword_18006EB20;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
            }
          }
          if ( *((_BYTE *)v24 + 8) )
          {
            v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
            if ( *((_DWORD *)v26 + 499) != started )
              CallStackContext::TraceFailure(v26, "CMFVideoThumbnail::Generate", 360, started);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v14 = 19;
            goto LABEL_75;
          }
          goto LABEL_76;
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
        started = CMFVideoThumbnail::GetRepresentativeFrame(this, v38, &v40, &v39);
        if ( started < 0 )
        {
          v28 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
            CallStackTracing::s_wpInstance = v29;
            if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
            {
              v28 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v28 = &qword_18006EB20;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
            }
          }
          if ( *((_BYTE *)v28 + 8) )
          {
            v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
            if ( *((_DWORD *)v30 + 499) != started )
              CallStackContext::TraceFailure(v30, "CMFVideoThumbnail::Generate", 362, started);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v14 = 20;
            goto LABEL_75;
          }
          goto LABEL_76;
        }
      }
      started = CMFVideoThumbnail::MFSampleToThumbnailStream(this, v39, v40, a3);
      if ( started < 0 )
      {
        v32 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
          CallStackTracing::s_wpInstance = v33;
          if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
          {
            v32 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v32 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v32 + 8) )
        {
          v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
          if ( *((_DWORD *)v34 + 499) != started )
            CallStackContext::TraceFailure(v34, "CMFVideoThumbnail::Generate", 365, started);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v14 = 21;
          goto LABEL_75;
        }
      }
      goto LABEL_76;
    }
    v16 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
      CallStackTracing::s_wpInstance = v17;
      if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
      {
        v16 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v16 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v16 + 8) )
    {
      v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
      if ( *((_DWORD *)v18 + 499) != started )
        CallStackContext::TraceFailure(v18, "CMFVideoThumbnail::Generate", 332, started);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v14 = 17;
      goto LABEL_75;
    }
  }
  else
  {
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)v13 + 499) != started )
        CallStackContext::TraceFailure(v13, "CMFVideoThumbnail::Generate", 319, started);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v14 = 16;
LABEL_75:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids,
        this,
        started);
    }
  }
LABEL_76:
  v35 = (struct IUnknown **)((char *)this + 32);
  if ( *((_QWORD *)this + 4) )
    ATL::AtlComPtrAssign(v35, 0);
  if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
    McTemplateU0pq_EventWriteTransfer(v35, &Property_Handler_ThumbnailGeneration_End, this, *((unsigned int *)this + 7));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v37);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppByteStream);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18004c254  push    rbp
0x18004c256  push    rbx
0x18004c257  push    rsi
0x18004c258  push    rdi
0x18004c259  push    r12
0x18004c25b  push    r14
0x18004c25d  push    r15
0x18004c25f  mov     rbp, rsp
0x18004c262  sub     rsp, 70h
0x18004c266  mov     rax, cs:__security_cookie
0x18004c26d  xor     rax, rsp
0x18004c270  mov     [rbp+var_8], rax
0x18004c274  test    cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 1
0x18004c27b  mov     r15, r8
0x18004c27e  mov     r14, rdx
0x18004c281  mov     rsi, rcx
0x18004c284  jz      short loc_18004C299
0x18004c286  mov     r9d, [rcx+1Ch]
0x18004c28a  lea     rdx, Property_Handler_ThumbnailGeneration_Start
0x18004c291  mov     r8, rcx
0x18004c294  call    McTemplateU0pq_EventWriteTransfer
0x18004c299  xor     r12d, r12d
0x18004c29c  lea     rdi, aCmfvideothumbn_6; "CMFVideoThumbnail::Generate"
0x18004c2a3  mov     rdx, rdi; char *
0x18004c2a6  mov     [rbp+ppByteStream], r12
0x18004c2aa  mov     r8d, 13Dh; int
0x18004c2b0  mov     [rbp+var_38], r12
0x18004c2b4  lea     rcx, [rbp+var_40]; this
0x18004c2b8  mov     [rbp+var_28], r12
0x18004c2bc  mov     [rbp+var_30], r12
0x18004c2c0  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004c2c5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004c2cc  cmp     [rcx+8], r12b
0x18004c2d0  jz      short loc_18004C333
0x18004c2d2  cmp     [rsi+190h], r12
0x18004c2d9  jz      short loc_18004C333
0x18004c2db  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004c2e0  mov     rdx, [rsi+190h]
0x18004c2e7  mov     rdi, rax
0x18004c2ea  mov     rcx, [rdx]
0x18004c2ed  mov     rax, [rcx+128h]
0x18004c2f4  mov     rcx, rdx
0x18004c2f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c2fc  mov     r8, [rsi+190h]
0x18004c303  lea     rdx, [rbp+var_18]
0x18004c307  mov     ebx, eax
0x18004c309  mov     rcx, [r8]
0x18004c30c  mov     rax, [rcx+118h]
0x18004c313  mov     rcx, r8
0x18004c316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c31b  movups  xmm0, xmmword ptr [rax]
0x18004c31e  mov     [rdi+7E0h], ebx
0x18004c324  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18004c32c  lea     rdi, aCmfvideothumbn_6; "CMFVideoThumbnail::Generate"
0x18004c333  mov     rcx, rsi; this
0x18004c336  call    ?StartTiming@CMFVideoThumbnail@@AEAAJXZ; CMFVideoThumbnail::StartTiming(void)
0x18004c33b  mov     ebx, eax
0x18004c33d  test    eax, eax
0x18004c33f  jns     loc_18004C3D0
0x18004c345  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c34c  test    rcx, rcx
0x18004c34f  jnz     short loc_18004C392
0x18004c351  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004c357  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c35e  mov     rcx, rax
0x18004c361  test    rax, rax
0x18004c364  jz      short loc_18004C384
0x18004c366  mov     rax, [rax]
0x18004c369  mov     edx, 7F0h
0x18004c36e  mov     rax, [rax+8]
0x18004c372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c377  test    eax, eax
0x18004c379  jz      short loc_18004C384
0x18004c37b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c382  jmp     short loc_18004C392
0x18004c384  lea     rcx, qword_18006EB20; this
0x18004c38b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c392  cmp     [rcx+8], r12b
0x18004c396  jz      short loc_18004C3B9
0x18004c398  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004c39d  cmp     [rax+7CCh], ebx
0x18004c3a3  jz      short loc_18004C3B9
0x18004c3a5  mov     r9d, ebx; int
0x18004c3a8  mov     r8d, 13Fh; int
0x18004c3ae  mov     rdx, rdi; char *
0x18004c3b1  mov     rcx, rax; this
0x18004c3b4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004c3b9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004c3be  cmp     al, 1
0x18004c3c0  jb      loc_18004C78A
0x18004c3c6  mov     edx, 10h
0x18004c3cb  jmp     loc_18004C76C
0x18004c3d0  lea     rcx, [rbp+ppByteStream]
0x18004c3d4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c3d9  lea     rdx, [rbp+ppByteStream]; ppByteStream
0x18004c3dd  mov     rcx, r14; pStream
0x18004c3e0  call    cs:__imp_MFCreateMFByteStreamOnStream
0x18004c3e6  mov     ebx, eax
0x18004c3e8  test    eax, eax
0x18004c3ea  jns     loc_18004C47B
0x18004c3f0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c3f7  test    rcx, rcx
0x18004c3fa  jnz     short loc_18004C43D
0x18004c3fc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004c402  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c409  mov     rcx, rax
0x18004c40c  test    rax, rax
0x18004c40f  jz      short loc_18004C42F
0x18004c411  mov     rax, [rax]
0x18004c414  mov     edx, 7F0h
0x18004c419  mov     rax, [rax+8]
0x18004c41d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c422  test    eax, eax
0x18004c424  jz      short loc_18004C42F
0x18004c426  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c42d  jmp     short loc_18004C43D
0x18004c42f  lea     rcx, qword_18006EB20; this
0x18004c436  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c43d  cmp     [rcx+8], r12b
0x18004c441  jz      short loc_18004C464
0x18004c443  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004c448  cmp     [rax+7CCh], ebx
0x18004c44e  jz      short loc_18004C464
0x18004c450  mov     r9d, ebx; int
0x18004c453  mov     r8d, 14Ch; int
0x18004c459  mov     rdx, rdi; char *
0x18004c45c  mov     rcx, rax; this
0x18004c45f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004c464  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004c469  cmp     al, 1
0x18004c46b  jb      loc_18004C78A
0x18004c471  mov     edx, 11h
0x18004c476  jmp     loc_18004C76C
0x18004c47b  lea     rcx, [rbp+var_38]
0x18004c47f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c484  mov     rdx, [rbp+ppByteStream]; struct IMFByteStream *
0x18004c488  lea     r8, [rbp+var_38]; struct IMFSourceReader **
0x18004c48c  mov     rcx, rsi; this
0x18004c48f  call    ?CreateSourceReaderFromMFSource@CMFVideoThumbnail@@AEAAJPEAUIMFByteStream@@PEAPEAUIMFSourceReader@@@Z; CMFVideoThumbnail::CreateSourceReaderFromMFSource(IMFByteStream *,IMFSourceReader * *)
0x18004c494  mov     ebx, eax
0x18004c496  test    eax, eax
0x18004c498  jnz     short loc_18004C4C2
0x18004c49a  lea     rcx, [rbp+var_30]
0x18004c49e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c4a3  lea     rcx, [rbp+var_28]
0x18004c4a7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c4ac  mov     rdx, [rbp+var_38]; struct IMFSourceReader *
0x18004c4b0  lea     r9, [rbp+var_30]; struct IMFMediaType **
0x18004c4b4  lea     r8, [rbp+var_28]; struct IMFSample **
0x18004c4b8  mov     rcx, rsi; this
0x18004c4bb  call    ?GetRepresentativeFrame@CMFVideoThumbnail@@AEAAJPEAUIMFSourceReader@@PEAPEAUIMFSample@@PEAPEAUIMFMediaType@@@Z; CMFVideoThumbnail::GetRepresentativeFrame(IMFSourceReader *,IMFSample * *,IMFMediaType * *)
0x18004c4c0  mov     ebx, eax
0x18004c4c2  test    ebx, ebx
0x18004c4c4  jns     loc_18004C6CD
0x18004c4ca  mov     eax, [rsi+1Ch]
0x18004c4cd  sub     eax, 4
0x18004c4d0  cmp     eax, 1
0x18004c4d3  jbe     loc_18004C564
0x18004c4d9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c4e0  test    rcx, rcx
0x18004c4e3  jnz     short loc_18004C526
0x18004c4e5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004c4eb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c4f2  mov     rcx, rax
0x18004c4f5  test    rax, rax
0x18004c4f8  jz      short loc_18004C518
0x18004c4fa  mov     rax, [rax]
0x18004c4fd  mov     edx, 7F0h
0x18004c502  mov     rax, [rax+8]
0x18004c506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c50b  test    eax, eax
0x18004c50d  jz      short loc_18004C518
0x18004c50f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c516  jmp     short loc_18004C526
0x18004c518  lea     rcx, qword_18006EB20; this
0x18004c51f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c526  cmp     [rcx+8], r12b
0x18004c52a  jz      short loc_18004C54D
0x18004c52c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004c531  cmp     [rax+7CCh], ebx
0x18004c537  jz      short loc_18004C54D
0x18004c539  mov     r9d, ebx; int
0x18004c53c  mov     r8d, 161h; int
0x18004c542  mov     rdx, rdi; char *
0x18004c545  mov     rcx, rax; this
0x18004c548  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004c54d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004c552  cmp     al, 1
0x18004c554  jb      loc_18004C78A
0x18004c55a  mov     edx, 12h
0x18004c55f  jmp     loc_18004C76C
0x18004c564  lea     rcx, [rbp+var_38]
0x18004c568  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c56d  mov     rdx, [rbp+ppByteStream]; struct IMFByteStream *
0x18004c571  lea     r8, [rbp+var_38]; struct IMFSourceReader **
0x18004c575  mov     rcx, rsi; this
0x18004c578  call    ?CreateSourceReaderFromDShowSource@CMFVideoThumbnail@@AEAAJPEAUIMFByteStream@@PEAPEAUIMFSourceReader@@@Z; CMFVideoThumbnail::CreateSourceReaderFromDShowSource(IMFByteStream *,IMFSourceReader * *)
0x18004c57d  mov     ebx, eax
0x18004c57f  test    eax, eax
0x18004c581  jns     loc_18004C612
0x18004c587  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c58e  test    rcx, rcx
0x18004c591  jnz     short loc_18004C5D4
0x18004c593  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004c599  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c5a0  mov     rcx, rax
0x18004c5a3  test    rax, rax
0x18004c5a6  jz      short loc_18004C5C6
0x18004c5a8  mov     rax, [rax]
0x18004c5ab  mov     edx, 7F0h
0x18004c5b0  mov     rax, [rax+8]
0x18004c5b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c5b9  test    eax, eax
0x18004c5bb  jz      short loc_18004C5C6
0x18004c5bd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c5c4  jmp     short loc_18004C5D4
0x18004c5c6  lea     rcx, qword_18006EB20; this
0x18004c5cd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c5d4  cmp     [rcx+8], r12b
0x18004c5d8  jz      short loc_18004C5FB
0x18004c5da  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004c5df  cmp     [rax+7CCh], ebx
0x18004c5e5  jz      short loc_18004C5FB
0x18004c5e7  mov     r9d, ebx; int
0x18004c5ea  mov     r8d, 168h; int
0x18004c5f0  mov     rdx, rdi; char *
0x18004c5f3  mov     rcx, rax; this
0x18004c5f6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004c5fb  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004c600  cmp     al, 1
0x18004c602  jb      loc_18004C78A
0x18004c608  mov     edx, 13h
0x18004c60d  jmp     loc_18004C76C
0x18004c612  lea     rcx, [rbp+var_30]
0x18004c616  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c61b  lea     rcx, [rbp+var_28]
0x18004c61f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c624  mov     rdx, [rbp+var_38]; struct IMFSourceReader *
0x18004c628  lea     r9, [rbp+var_30]; struct IMFMediaType **
0x18004c62c  lea     r8, [rbp+var_28]; struct IMFSample **
0x18004c630  mov     rcx, rsi; this
0x18004c633  call    ?GetRepresentativeFrame@CMFVideoThumbnail@@AEAAJPEAUIMFSourceReader@@PEAPEAUIMFSample@@PEAPEAUIMFMediaType@@@Z; CMFVideoThumbnail::GetRepresentativeFrame(IMFSourceReader *,IMFSample * *,IMFMediaType * *)
0x18004c638  mov     ebx, eax
0x18004c63a  test    eax, eax
0x18004c63c  jns     loc_18004C6CD
0x18004c642  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c649  test    rcx, rcx
0x18004c64c  jnz     short loc_18004C68F
0x18004c64e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004c654  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c65b  mov     rcx, rax
0x18004c65e  test    rax, rax
0x18004c661  jz      short loc_18004C681
0x18004c663  mov     rax, [rax]
0x18004c666  mov     edx, 7F0h
0x18004c66b  mov     rax, [rax+8]
0x18004c66f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c674  test    eax, eax
0x18004c676  jz      short loc_18004C681
0x18004c678  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c67f  jmp     short loc_18004C68F
0x18004c681  lea     rcx, qword_18006EB20; this
0x18004c688  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c68f  cmp     [rcx+8], r12b
0x18004c693  jz      short loc_18004C6B6
0x18004c695  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004c69a  cmp     [rax+7CCh], ebx
0x18004c6a0  jz      short loc_18004C6B6
0x18004c6a2  mov     r9d, ebx; int
0x18004c6a5  mov     r8d, 16Ah; int
0x18004c6ab  mov     rdx, rdi; char *
0x18004c6ae  mov     rcx, rax; this
0x18004c6b1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004c6b6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004c6bb  cmp     al, 1
0x18004c6bd  jb      loc_18004C78A
0x18004c6c3  mov     edx, 14h
0x18004c6c8  jmp     loc_18004C76C
0x18004c6cd  mov     r8, [rbp+var_28]; struct IMFSample *
0x18004c6d1  mov     r9, r15; struct tagPROPVARIANT *
0x18004c6d4  mov     rdx, [rbp+var_30]; struct IMFMediaType *
0x18004c6d8  mov     rcx, rsi; this
0x18004c6db  call    ?MFSampleToThumbnailStream@CMFVideoThumbnail@@AEAAJPEAUIMFMediaType@@PEAUIMFSample@@PEAUtagPROPVARIANT@@@Z; CMFVideoThumbnail::MFSampleToThumbnailStream(IMFMediaType *,IMFSample *,tagPROPVARIANT *)
0x18004c6e0  mov     ebx, eax
0x18004c6e2  test    eax, eax
0x18004c6e4  jns     loc_18004C78A
0x18004c6ea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c6f1  test    rcx, rcx
0x18004c6f4  jnz     short loc_18004C737
0x18004c6f6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004c6fc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c703  mov     rcx, rax
0x18004c706  test    rax, rax
0x18004c709  jz      short loc_18004C729
0x18004c70b  mov     rax, [rax]
0x18004c70e  mov     edx, 7F0h
0x18004c713  mov     rax, [rax+8]
0x18004c717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c71c  test    eax, eax
0x18004c71e  jz      short loc_18004C729
  ... truncated ...
```
