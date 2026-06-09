# CMFVideoThumbnail::Generate(IStream *,tagPROPVARIANT *)

- ea: `0x18006a8cc`
- end: `0x18006aea3`
- name: `?Generate@CMFVideoThumbnail@@QEAAJPEAUIStream@@PEAUtagPROPVARIANT@@@Z`
- size: `1495`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, IStream *pStream, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180055990`

## callees

- `0x180002400`
- `0x180005c68`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180054a9c`
- `0x18006a2ac`
- `0x18006a524`
- `0x18006a8cc`
- `0x18006b2cc`
- `0x18006c764`
- `0x18006c8f0`
- `0x18006e958`
- `0x18006eccc`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a9c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006aa80`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ab6f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ac23`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ace4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ad92`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a9c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006aa80`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ab6f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ac23`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ace4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ad92`
- `MFPlat!MFCreateMFByteStreamOnStream` at `0x18006aa5e`
- `MFPlat!MFCreateMFByteStreamOnStream` at `0x18006aa5e`

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
      &Property_Handler_ThumbnailGeneration_Start,
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
              v26 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
              v32 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
              v38 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v44 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v20 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v13 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
    McTemplateU0pq_EventWriteTransfer(v47, &Property_Handler_ThumbnailGeneration_End, this, *((unsigned int *)this + 7));
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
0x18006a8cc  push    rbp
0x18006a8ce  push    rbx
0x18006a8cf  push    rsi
0x18006a8d0  push    rdi
0x18006a8d1  push    r12
0x18006a8d3  push    r14
0x18006a8d5  push    r15
0x18006a8d7  mov     rbp, rsp
0x18006a8da  sub     rsp, 70h
0x18006a8de  mov     rax, cs:__security_cookie
0x18006a8e5  xor     rax, rsp
0x18006a8e8  mov     [rbp+var_8], rax
0x18006a8ec  test    cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 1
0x18006a8f3  mov     r15, r8
0x18006a8f6  mov     r14, rdx
0x18006a8f9  mov     rsi, rcx
0x18006a8fc  jz      short loc_18006A911
0x18006a8fe  mov     r9d, [rcx+1Ch]
0x18006a902  lea     rdx, Property_Handler_ThumbnailGeneration_Start
0x18006a909  mov     r8, rcx
0x18006a90c  call    McTemplateU0pq_EventWriteTransfer
0x18006a911  xor     r12d, r12d
0x18006a914  lea     rdi, aCmfvideothumbn_6; "CMFVideoThumbnail::Generate"
0x18006a91b  mov     rdx, rdi; char *
0x18006a91e  mov     [rbp+ppByteStream], r12
0x18006a922  mov     r8d, 13Dh; int
0x18006a928  mov     [rbp+var_38], r12
0x18006a92c  lea     rcx, [rbp+var_40]; this
0x18006a930  mov     [rbp+var_28], r12
0x18006a934  mov     [rbp+var_30], r12
0x18006a938  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006a93d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18006a944  cmp     [rcx+8], r12b
0x18006a948  jz      short loc_18006A9AB
0x18006a94a  cmp     [rsi+190h], r12
0x18006a951  jz      short loc_18006A9AB
0x18006a953  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006a958  mov     rdx, [rsi+190h]
0x18006a95f  mov     rdi, rax
0x18006a962  mov     rcx, [rdx]
0x18006a965  mov     rax, [rcx+128h]
0x18006a96c  mov     rcx, rdx
0x18006a96f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a974  mov     r8, [rsi+190h]
0x18006a97b  lea     rdx, [rbp+var_18]
0x18006a97f  mov     ebx, eax
0x18006a981  mov     rcx, [r8]
0x18006a984  mov     rax, [rcx+118h]
0x18006a98b  mov     rcx, r8
0x18006a98e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a993  movups  xmm0, xmmword ptr [rax]
0x18006a996  mov     [rdi+7E0h], ebx
0x18006a99c  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18006a9a4  lea     rdi, aCmfvideothumbn_6; "CMFVideoThumbnail::Generate"
0x18006a9ab  mov     rcx, rsi; this
0x18006a9ae  call    ?StartTiming@CMFVideoThumbnail@@AEAAJXZ; CMFVideoThumbnail::StartTiming(void)
0x18006a9b3  mov     ebx, eax
0x18006a9b5  test    eax, eax
0x18006a9b7  jns     loc_18006AA4E
0x18006a9bd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a9c4  test    rcx, rcx
0x18006a9c7  jnz     short loc_18006AA10
0x18006a9c9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006a9d0  nop     dword ptr [rax+rax+00h]
0x18006a9d5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a9dc  mov     rcx, rax
0x18006a9df  test    rax, rax
0x18006a9e2  jz      short loc_18006AA02
0x18006a9e4  mov     rax, [rax]
0x18006a9e7  mov     edx, 7F0h
0x18006a9ec  mov     rax, [rax+8]
0x18006a9f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a9f5  test    eax, eax
0x18006a9f7  jz      short loc_18006AA02
0x18006a9f9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006aa00  jmp     short loc_18006AA10
0x18006aa02  lea     rcx, qword_1800DBF70; this
0x18006aa09  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006aa10  cmp     [rcx+8], r12b
0x18006aa14  jz      short loc_18006AA37
0x18006aa16  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006aa1b  cmp     [rax+7CCh], ebx
0x18006aa21  jz      short loc_18006AA37
0x18006aa23  mov     r9d, ebx; int
0x18006aa26  mov     r8d, 13Fh; int
0x18006aa2c  mov     rdx, rdi; char *
0x18006aa2f  mov     rcx, rax; this
0x18006aa32  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006aa37  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006aa3e  jb      loc_18006AE2C
0x18006aa44  mov     edx, 10h
0x18006aa49  jmp     loc_18006AE0E
0x18006aa4e  lea     rcx, [rbp+ppByteStream]
0x18006aa52  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006aa57  lea     rdx, [rbp+ppByteStream]; ppByteStream
0x18006aa5b  mov     rcx, r14; pStream
0x18006aa5e  call    cs:__imp_MFCreateMFByteStreamOnStream
0x18006aa65  nop     dword ptr [rax+rax+00h]
0x18006aa6a  mov     ebx, eax
0x18006aa6c  test    eax, eax
0x18006aa6e  jns     loc_18006AB05
0x18006aa74  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006aa7b  test    rcx, rcx
0x18006aa7e  jnz     short loc_18006AAC7
0x18006aa80  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006aa87  nop     dword ptr [rax+rax+00h]
0x18006aa8c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006aa93  mov     rcx, rax
0x18006aa96  test    rax, rax
0x18006aa99  jz      short loc_18006AAB9
0x18006aa9b  mov     rax, [rax]
0x18006aa9e  mov     edx, 7F0h
0x18006aaa3  mov     rax, [rax+8]
0x18006aaa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aaac  test    eax, eax
0x18006aaae  jz      short loc_18006AAB9
0x18006aab0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006aab7  jmp     short loc_18006AAC7
0x18006aab9  lea     rcx, qword_1800DBF70; this
0x18006aac0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006aac7  cmp     [rcx+8], r12b
0x18006aacb  jz      short loc_18006AAEE
0x18006aacd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006aad2  cmp     [rax+7CCh], ebx
0x18006aad8  jz      short loc_18006AAEE
0x18006aada  mov     r9d, ebx; int
0x18006aadd  mov     r8d, 14Ch; int
0x18006aae3  mov     rdx, rdi; char *
0x18006aae6  mov     rcx, rax; this
0x18006aae9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006aaee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006aaf5  jb      loc_18006AE2C
0x18006aafb  mov     edx, 11h
0x18006ab00  jmp     loc_18006AE0E
0x18006ab05  lea     rcx, [rbp+var_38]
0x18006ab09  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x18006ab0e  mov     rdx, [rbp+ppByteStream]; struct IMFByteStream *
0x18006ab12  lea     r8, [rbp+var_38]; struct IMFSourceReader **
0x18006ab16  mov     rcx, rsi; this
0x18006ab19  call    ?CreateSourceReaderFromMFSource@CMFVideoThumbnail@@AEAAJPEAUIMFByteStream@@PEAPEAUIMFSourceReader@@@Z; CMFVideoThumbnail::CreateSourceReaderFromMFSource(IMFByteStream *,IMFSourceReader * *)
0x18006ab1e  mov     ebx, eax
0x18006ab20  test    eax, eax
0x18006ab22  jnz     short loc_18006AB4C
0x18006ab24  lea     rcx, [rbp+var_30]
0x18006ab28  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006ab2d  lea     rcx, [rbp+var_28]
0x18006ab31  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006ab36  mov     rdx, [rbp+var_38]; struct IMFSourceReader *
0x18006ab3a  lea     r9, [rbp+var_30]; struct IMFMediaType **
0x18006ab3e  lea     r8, [rbp+var_28]; struct IMFSample **
0x18006ab42  mov     rcx, rsi; this
0x18006ab45  call    ?GetRepresentativeFrame@CMFVideoThumbnail@@AEAAJPEAUIMFSourceReader@@PEAPEAUIMFSample@@PEAPEAUIMFMediaType@@@Z; CMFVideoThumbnail::GetRepresentativeFrame(IMFSourceReader *,IMFSample * *,IMFMediaType * *)
0x18006ab4a  mov     ebx, eax
0x18006ab4c  test    ebx, ebx
0x18006ab4e  jns     loc_18006AD69
0x18006ab54  mov     eax, [rsi+1Ch]
0x18006ab57  sub     eax, 4
0x18006ab5a  cmp     eax, 1
0x18006ab5d  jbe     loc_18006ABF4
0x18006ab63  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ab6a  test    rcx, rcx
0x18006ab6d  jnz     short loc_18006ABB6
0x18006ab6f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006ab76  nop     dword ptr [rax+rax+00h]
0x18006ab7b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ab82  mov     rcx, rax
0x18006ab85  test    rax, rax
0x18006ab88  jz      short loc_18006ABA8
0x18006ab8a  mov     rax, [rax]
0x18006ab8d  mov     edx, 7F0h
0x18006ab92  mov     rax, [rax+8]
0x18006ab96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ab9b  test    eax, eax
0x18006ab9d  jz      short loc_18006ABA8
0x18006ab9f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006aba6  jmp     short loc_18006ABB6
0x18006aba8  lea     rcx, qword_1800DBF70; this
0x18006abaf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006abb6  cmp     [rcx+8], r12b
0x18006abba  jz      short loc_18006ABDD
0x18006abbc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006abc1  cmp     [rax+7CCh], ebx
0x18006abc7  jz      short loc_18006ABDD
0x18006abc9  mov     r9d, ebx; int
0x18006abcc  mov     r8d, 161h; int
0x18006abd2  mov     rdx, rdi; char *
0x18006abd5  mov     rcx, rax; this
0x18006abd8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006abdd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006abe4  jb      loc_18006AE2C
0x18006abea  mov     edx, 12h
0x18006abef  jmp     loc_18006AE0E
0x18006abf4  lea     rcx, [rbp+var_38]
0x18006abf8  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x18006abfd  mov     rdx, [rbp+ppByteStream]; struct IMFByteStream *
0x18006ac01  lea     r8, [rbp+var_38]; struct IMFSourceReader **
0x18006ac05  mov     rcx, rsi; this
0x18006ac08  call    ?CreateSourceReaderFromDShowSource@CMFVideoThumbnail@@AEAAJPEAUIMFByteStream@@PEAPEAUIMFSourceReader@@@Z; CMFVideoThumbnail::CreateSourceReaderFromDShowSource(IMFByteStream *,IMFSourceReader * *)
0x18006ac0d  mov     ebx, eax
0x18006ac0f  test    eax, eax
0x18006ac11  jns     loc_18006ACA8
0x18006ac17  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ac1e  test    rcx, rcx
0x18006ac21  jnz     short loc_18006AC6A
0x18006ac23  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006ac2a  nop     dword ptr [rax+rax+00h]
0x18006ac2f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ac36  mov     rcx, rax
0x18006ac39  test    rax, rax
0x18006ac3c  jz      short loc_18006AC5C
0x18006ac3e  mov     rax, [rax]
0x18006ac41  mov     edx, 7F0h
0x18006ac46  mov     rax, [rax+8]
0x18006ac4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ac4f  test    eax, eax
0x18006ac51  jz      short loc_18006AC5C
0x18006ac53  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ac5a  jmp     short loc_18006AC6A
0x18006ac5c  lea     rcx, qword_1800DBF70; this
0x18006ac63  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ac6a  cmp     [rcx+8], r12b
0x18006ac6e  jz      short loc_18006AC91
0x18006ac70  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006ac75  cmp     [rax+7CCh], ebx
0x18006ac7b  jz      short loc_18006AC91
0x18006ac7d  mov     r9d, ebx; int
0x18006ac80  mov     r8d, 168h; int
0x18006ac86  mov     rdx, rdi; char *
0x18006ac89  mov     rcx, rax; this
0x18006ac8c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006ac91  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006ac98  jb      loc_18006AE2C
0x18006ac9e  mov     edx, 13h
0x18006aca3  jmp     loc_18006AE0E
0x18006aca8  lea     rcx, [rbp+var_30]
0x18006acac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006acb1  lea     rcx, [rbp+var_28]
0x18006acb5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006acba  mov     rdx, [rbp+var_38]; struct IMFSourceReader *
0x18006acbe  lea     r9, [rbp+var_30]; struct IMFMediaType **
0x18006acc2  lea     r8, [rbp+var_28]; struct IMFSample **
0x18006acc6  mov     rcx, rsi; this
0x18006acc9  call    ?GetRepresentativeFrame@CMFVideoThumbnail@@AEAAJPEAUIMFSourceReader@@PEAPEAUIMFSample@@PEAPEAUIMFMediaType@@@Z; CMFVideoThumbnail::GetRepresentativeFrame(IMFSourceReader *,IMFSample * *,IMFMediaType * *)
0x18006acce  mov     ebx, eax
0x18006acd0  test    eax, eax
0x18006acd2  jns     loc_18006AD69
0x18006acd8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006acdf  test    rcx, rcx
0x18006ace2  jnz     short loc_18006AD2B
0x18006ace4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006aceb  nop     dword ptr [rax+rax+00h]
0x18006acf0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006acf7  mov     rcx, rax
0x18006acfa  test    rax, rax
0x18006acfd  jz      short loc_18006AD1D
0x18006acff  mov     rax, [rax]
0x18006ad02  mov     edx, 7F0h
0x18006ad07  mov     rax, [rax+8]
0x18006ad0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ad10  test    eax, eax
0x18006ad12  jz      short loc_18006AD1D
0x18006ad14  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ad1b  jmp     short loc_18006AD2B
0x18006ad1d  lea     rcx, qword_1800DBF70; this
0x18006ad24  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ad2b  cmp     [rcx+8], r12b
0x18006ad2f  jz      short loc_18006AD52
0x18006ad31  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006ad36  cmp     [rax+7CCh], ebx
0x18006ad3c  jz      short loc_18006AD52
0x18006ad3e  mov     r9d, ebx; int
0x18006ad41  mov     r8d, 16Ah; int
0x18006ad47  mov     rdx, rdi; char *
0x18006ad4a  mov     rcx, rax; this
0x18006ad4d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006ad52  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006ad59  jb      loc_18006AE2C
0x18006ad5f  mov     edx, 14h
0x18006ad64  jmp     loc_18006AE0E
0x18006ad69  mov     r8, [rbp+var_28]; struct IMFSample *
0x18006ad6d  mov     r9, r15; struct tagPROPVARIANT *
0x18006ad70  mov     rdx, [rbp+var_30]; struct IMFMediaType *
0x18006ad74  mov     rcx, rsi; this
0x18006ad77  call    ?MFSampleToThumbnailStream@CMFVideoThumbnail@@AEAAJPEAUIMFMediaType@@PEAUIMFSample@@PEAUtagPROPVARIANT@@@Z; CMFVideoThumbnail::MFSampleToThumbnailStream(IMFMediaType *,IMFSample *,tagPROPVARIANT *)
0x18006ad7c  mov     ebx, eax
0x18006ad7e  test    eax, eax
0x18006ad80  jns     loc_18006AE2C
0x18006ad86  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ad8d  test    rcx, rcx
0x18006ad90  jnz     short loc_18006ADD9
0x18006ad92  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006ad99  nop     dword ptr [rax+rax+00h]
0x18006ad9e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ada5  mov     rcx, rax
0x18006ada8  test    rax, rax
0x18006adab  jz      short loc_18006ADCB
0x18006adad  mov     rax, [rax]
0x18006adb0  mov     edx, 7F0h
0x18006adb5  mov     rax, [rax+8]
0x18006adb9  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
