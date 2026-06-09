# CMFByteStreamMediaSource::BeginOpen(IMFAsyncCallback *,IUnknown *,IMFAsyncResult * *)

- ea: `0x1801497d0`
- end: `0x180149d6b`
- name: `?BeginOpen@CMFByteStreamMediaSource@@QEAAJPEAUIMFAsyncCallback@@PEAUIUnknown@@PEAPEAUIMFAsyncResult@@@Z`
- size: `1435`
- prototype: `int(CMFByteStreamMediaSource *__hidden this, struct IMFAsyncCallback *, struct IUnknown *, struct IMFAsyncResult **)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18011bd40`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x180079680`
- `0x18007c76c`
- `0x18009f8ac`
- `0x180110a94`
- `0x180148d0c`
- `0x1801497d0`
- `0x18014d3c4`
- `0x18016e1f0`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180149d37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180149d37`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180149816`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180149816`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180149840`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801498df`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014998d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180149a41`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180149b3a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180149be2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180149c9a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180149840`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801498df`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014998d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180149a41`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180149b3a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180149be2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180149c9a`
- `MFPlat!MFCreateAsyncResult` at `0x180149a1f`
- `MFPlat!MFCreateAsyncResult` at `0x180149a1f`

## string_xrefs

- `0x1801497e3`: `CMFByteStreamMediaSource::BeginOpen`

## pseudocode

```c
__int64 __fastcall CMFByteStreamMediaSource::BeginOpen(
        CMFByteStreamMediaSource *this,
        struct IMFAsyncCallback *a2,
        struct IUnknown *a3,
        struct IMFAsyncResult **a4)
{
  __int64 v7; // rdx
  wchar_t *v8; // rcx
  HRESULT ByteStreamEvent; // ebx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  wchar_t *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  struct CBaseOperation *v24; // rax
  __int64 v25; // rdx
  struct CBaseOperation *v26; // rsi
  IMFAsyncResult *v27; // rbx
  __int64 v28; // rdx
  wchar_t *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rdx
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  wchar_t *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  IMFAsyncResult *ppAsyncResult; // [rsp+60h] [rbp+8h] BYREF
  char v42; // [rsp+78h] [rbp+20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v42, "CMFByteStreamMediaSource::BeginOpen", 604);
  ppAsyncResult = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 712));
  if ( *((_DWORD *)this + 277) )
  {
    v8 = (wchar_t *)CallStackTracing::s_wpInstance;
    ByteStreamEvent = -1072875854;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v8 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875854 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFByteStreamMediaSource::BeginOpen", 613, -1072875854);
    }
    if ( g_wppLevels )
    {
      v12 = 36;
LABEL_82:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
        this,
        ByteStreamEvent);
      goto LABEL_83;
    }
    goto LABEL_83;
  }
  if ( a2 )
  {
    ByteStreamEvent = CMFByteStreamSourceReader::BeginGetByteStreamEvent(
                        (CMFByteStreamMediaSource *)((char *)this + 1120),
                        (struct IMFAsyncCallback *)this + 85);
    if ( ByteStreamEvent < 0 )
    {
      v17 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
        CallStackTracing::s_wpInstance = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v17 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
        if ( *((_DWORD *)v19 + 499) != ByteStreamEvent )
          CallStackContext::TraceFailure(v19, "CMFByteStreamMediaSource::BeginOpen", 621, ByteStreamEvent);
      }
      if ( g_wppLevels )
      {
        v12 = 38;
        goto LABEL_82;
      }
      goto LABEL_83;
    }
    ByteStreamEvent = MFCreateAsyncResult(0, a2, a3, &ppAsyncResult);
    if ( ByteStreamEvent < 0 )
    {
      v21 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
        CallStackTracing::s_wpInstance = v22;
        if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
        {
          v21 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v21 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v21 + 8) )
      {
        v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
        if ( *((_DWORD *)v23 + 499) != ByteStreamEvent )
          CallStackContext::TraceFailure(v23, "CMFByteStreamMediaSource::BeginOpen", 626, ByteStreamEvent);
      }
      if ( g_wppLevels )
      {
        v12 = 39;
        goto LABEL_82;
      }
      goto LABEL_83;
    }
    v24 = (struct CBaseOperation *)operator new(0x38u);
    v26 = v24;
    if ( !v24 )
    {
      v37 = (wchar_t *)CallStackTracing::s_wpInstance;
      ByteStreamEvent = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
        CallStackTracing::s_wpInstance = v38;
        if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
        {
          v37 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v37 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v37 + 8) )
      {
        v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
        if ( *((_DWORD *)v39 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v39, "CMFByteStreamMediaSource::BeginOpen", 629, -2147024882);
      }
      if ( g_wppLevels )
      {
        v12 = 40;
        goto LABEL_82;
      }
      goto LABEL_83;
    }
    v27 = ppAsyncResult;
    CMediaSourceOp::CMediaSourceOp(v24, 1, this);
    *(_QWORD *)v26 = &CMediaSourceOpOpen::`vftable';
    *((_QWORD *)v26 + 6) = v27;
    if ( v27 )
      ((void (__fastcall *)(IMFAsyncResult *))v27->lpVtbl->AddRef)(v27);
    ByteStreamEvent = COpQueue::QueueOperation((CMFByteStreamMediaSource *)((char *)this + 88), v26, 0);
    if ( ByteStreamEvent >= 0 )
    {
      ByteStreamEvent = CMFByteStreamMediaSource::SetState(this, 1);
      if ( ByteStreamEvent >= 0 )
        goto LABEL_71;
      v34 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
        CallStackTracing::s_wpInstance = v35;
        if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
        {
          v34 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v34 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v34 + 8) )
      {
        v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
        if ( *((_DWORD *)v36 + 499) != ByteStreamEvent )
          CallStackContext::TraceFailure(v36, "CMFByteStreamMediaSource::BeginOpen", 638, ByteStreamEvent);
      }
      if ( !g_wppLevels )
        goto LABEL_71;
      v32 = 42;
    }
    else
    {
      v29 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28);
        CallStackTracing::s_wpInstance = v30;
        if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
        {
          v29 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v29 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v29 + 8) )
      {
        v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
        if ( *((_DWORD *)v31 + 499) != ByteStreamEvent )
          CallStackContext::TraceFailure(v31, "CMFByteStreamMediaSource::BeginOpen", 631, ByteStreamEvent);
      }
      if ( !g_wppLevels )
        goto LABEL_71;
      v32 = 41;
    }
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v32,
      &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
      this,
      ByteStreamEvent);
LABEL_71:
    CBaseOperation::Release(v26);
    goto LABEL_83;
  }
  v13 = (wchar_t *)CallStackTracing::s_wpInstance;
  ByteStreamEvent = -2147467261;
  if ( !CallStackTracing::s_wpInstance )
  {
    v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7);
    CallStackTracing::s_wpInstance = v14;
    if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
    {
      v13 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v13 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v13 + 8) )
  {
    v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
    if ( *((_DWORD *)v15 + 499) != -2147467261 )
      CallStackContext::TraceFailure(v15, "CMFByteStreamMediaSource::BeginOpen", 616, -2147467261);
  }
  if ( g_wppLevels )
  {
    v12 = 37;
    goto LABEL_82;
  }
LABEL_83:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 712));
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppAsyncResult);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v42);
  return (unsigned int)ByteStreamEvent;
}

```

## disassembly

```asm
0x1801497d0  mov     [rsp+arg_8], rbx
0x1801497d5  push    rbp
0x1801497d6  push    rsi
0x1801497d7  push    rdi
0x1801497d8  push    r12
0x1801497da  push    r14
0x1801497dc  sub     rsp, 30h
0x1801497e0  mov     rbp, r8
0x1801497e3  lea     r12, aCmfbytestreamm_34; "CMFByteStreamMediaSource::BeginOpen"
0x1801497ea  mov     rsi, rdx
0x1801497ed  mov     rdi, rcx
0x1801497f0  mov     rdx, r12; char *
0x1801497f3  lea     rcx, [rsp+58h+arg_18]; this
0x1801497f8  mov     r8d, 25Ch; int
0x1801497fe  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180149803  lea     r14, [rdi+2C8h]
0x18014980a  mov     [rsp+58h+ppAsyncResult], 0
0x180149813  mov     rcx, r14; lpCriticalSection
0x180149816  call    cs:__imp_EnterCriticalSection
0x18014981d  nop     dword ptr [rax+rax+00h]
0x180149822  cmp     dword ptr [rdi+454h], 0
0x180149829  jz      loc_1801498C5
0x18014982f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180149836  mov     ebx, 0C00D36B2h
0x18014983b  test    rcx, rcx
0x18014983e  jnz     short loc_180149887
0x180149840  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180149847  nop     dword ptr [rax+rax+00h]
0x18014984c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180149853  mov     rcx, rax
0x180149856  test    rax, rax
0x180149859  jz      short loc_180149879
0x18014985b  mov     rax, [rax]
0x18014985e  mov     edx, 7F0h
0x180149863  mov     rax, [rax+8]
0x180149867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014986c  test    eax, eax
0x18014986e  jz      short loc_180149879
0x180149870  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180149877  jmp     short loc_180149887
0x180149879  lea     rcx, qword_1801B97E0; this
0x180149880  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180149887  cmp     byte ptr [rcx+8], 0
0x18014988b  jz      short loc_1801498AE
0x18014988d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180149892  cmp     [rax+7CCh], ebx
0x180149898  jz      short loc_1801498AE
0x18014989a  mov     r9d, ebx; int
0x18014989d  mov     r8d, 265h; int
0x1801498a3  mov     rdx, r12; char *
0x1801498a6  mov     rcx, rax; this
0x1801498a9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801498ae  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801498b5  jb      loc_180149D34
0x1801498bb  mov     edx, 24h ; '$'
0x1801498c0  jmp     loc_180149D16
0x1801498c5  test    rsi, rsi
0x1801498c8  jnz     loc_180149964
0x1801498ce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801498d5  mov     ebx, 80004003h
0x1801498da  test    rcx, rcx
0x1801498dd  jnz     short loc_180149926
0x1801498df  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801498e6  nop     dword ptr [rax+rax+00h]
0x1801498eb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801498f2  mov     rcx, rax
0x1801498f5  test    rax, rax
0x1801498f8  jz      short loc_180149918
0x1801498fa  mov     rax, [rax]
0x1801498fd  mov     edx, 7F0h
0x180149902  mov     rax, [rax+8]
0x180149906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014990b  test    eax, eax
0x18014990d  jz      short loc_180149918
0x18014990f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180149916  jmp     short loc_180149926
0x180149918  lea     rcx, qword_1801B97E0; this
0x18014991f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180149926  cmp     byte ptr [rcx+8], 0
0x18014992a  jz      short loc_18014994D
0x18014992c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180149931  cmp     [rax+7CCh], ebx
0x180149937  jz      short loc_18014994D
0x180149939  mov     r9d, ebx; int
0x18014993c  mov     r8d, 268h; int
0x180149942  mov     rdx, r12; char *
0x180149945  mov     rcx, rax; this
0x180149948  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18014994d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180149954  jb      loc_180149D34
0x18014995a  mov     edx, 25h ; '%'
0x18014995f  jmp     loc_180149D16
0x180149964  lea     rdx, [rdi+2A8h]; struct IMFAsyncCallback *
0x18014996b  lea     rcx, [rdi+460h]; this
0x180149972  call    ?BeginGetByteStreamEvent@CMFByteStreamSourceReader@@QEAAJPEAUIMFAsyncCallback@@@Z; CMFByteStreamSourceReader::BeginGetByteStreamEvent(IMFAsyncCallback *)
0x180149977  mov     ebx, eax
0x180149979  test    eax, eax
0x18014997b  jns     loc_180149A12
0x180149981  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180149988  test    rcx, rcx
0x18014998b  jnz     short loc_1801499D4
0x18014998d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180149994  nop     dword ptr [rax+rax+00h]
0x180149999  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801499a0  mov     rcx, rax
0x1801499a3  test    rax, rax
0x1801499a6  jz      short loc_1801499C6
0x1801499a8  mov     rax, [rax]
0x1801499ab  mov     edx, 7F0h
0x1801499b0  mov     rax, [rax+8]
0x1801499b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801499b9  test    eax, eax
0x1801499bb  jz      short loc_1801499C6
0x1801499bd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801499c4  jmp     short loc_1801499D4
0x1801499c6  lea     rcx, qword_1801B97E0; this
0x1801499cd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801499d4  cmp     byte ptr [rcx+8], 0
0x1801499d8  jz      short loc_1801499FB
0x1801499da  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801499df  cmp     [rax+7CCh], ebx
0x1801499e5  jz      short loc_1801499FB
0x1801499e7  mov     r9d, ebx; int
0x1801499ea  mov     r8d, 26Dh; int
0x1801499f0  mov     rdx, r12; char *
0x1801499f3  mov     rcx, rax; this
0x1801499f6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801499fb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180149a02  jb      loc_180149D34
0x180149a08  mov     edx, 26h ; '&'
0x180149a0d  jmp     loc_180149D16
0x180149a12  lea     r9, [rsp+58h+ppAsyncResult]; ppAsyncResult
0x180149a17  mov     r8, rbp; punkState
0x180149a1a  mov     rdx, rsi; pCallback
0x180149a1d  xor     ecx, ecx; punkObject
0x180149a1f  call    cs:__imp_MFCreateAsyncResult
0x180149a26  nop     dword ptr [rax+rax+00h]
0x180149a2b  mov     ebx, eax
0x180149a2d  test    eax, eax
0x180149a2f  jns     loc_180149AC6
0x180149a35  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180149a3c  test    rcx, rcx
0x180149a3f  jnz     short loc_180149A88
0x180149a41  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180149a48  nop     dword ptr [rax+rax+00h]
0x180149a4d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180149a54  mov     rcx, rax
0x180149a57  test    rax, rax
0x180149a5a  jz      short loc_180149A7A
0x180149a5c  mov     rax, [rax]
0x180149a5f  mov     edx, 7F0h
0x180149a64  mov     rax, [rax+8]
0x180149a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180149a6d  test    eax, eax
0x180149a6f  jz      short loc_180149A7A
0x180149a71  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180149a78  jmp     short loc_180149A88
0x180149a7a  lea     rcx, qword_1801B97E0; this
0x180149a81  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180149a88  cmp     byte ptr [rcx+8], 0
0x180149a8c  jz      short loc_180149AAF
0x180149a8e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180149a93  cmp     [rax+7CCh], ebx
0x180149a99  jz      short loc_180149AAF
0x180149a9b  mov     r9d, ebx; int
0x180149a9e  mov     r8d, 272h; int
0x180149aa4  mov     rdx, r12; char *
0x180149aa7  mov     rcx, rax; this
0x180149aaa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180149aaf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180149ab6  jb      loc_180149D34
0x180149abc  mov     edx, 27h ; '''
0x180149ac1  jmp     loc_180149D16
0x180149ac6  mov     ecx, 38h ; '8'; Size
0x180149acb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180149ad0  mov     rsi, rax
0x180149ad3  test    rax, rax
0x180149ad6  jz      loc_180149C89
0x180149adc  mov     rbx, [rsp+58h+ppAsyncResult]
0x180149ae1  xor     r9d, r9d
0x180149ae4  mov     r8, rdi
0x180149ae7  mov     rcx, rax
0x180149aea  lea     edx, [r9+1]
0x180149aee  call    ??0CMediaSourceOp@@QEAA@W4MEDIA_SOURCE_OPERATION@0@PEAUIMFMediaEventGenerator@@K@Z; CMediaSourceOp::CMediaSourceOp(CMediaSourceOp::MEDIA_SOURCE_OPERATION,IMFMediaEventGenerator *,ulong)
0x180149af3  lea     rax, ??_7CMediaSourceOpOpen@@6B@; const CMediaSourceOpOpen::`vftable'
0x180149afa  mov     [rsi], rax
0x180149afd  mov     [rsi+30h], rbx
0x180149b01  test    rbx, rbx
0x180149b04  jz      short loc_180149B15
0x180149b06  mov     rax, [rbx]
0x180149b09  mov     rcx, rbx
0x180149b0c  mov     rax, [rax+8]
0x180149b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180149b15  lea     rcx, [rdi+58h]; this
0x180149b19  xor     r8d, r8d; int
0x180149b1c  mov     rdx, rsi; struct CBaseOperation *
0x180149b1f  call    ?QueueOperation@COpQueue@@QEAAJPEAVCBaseOperation@@H@Z; COpQueue::QueueOperation(CBaseOperation *,int)
0x180149b24  mov     ebx, eax
0x180149b26  test    eax, eax
0x180149b28  jns     loc_180149BBF
0x180149b2e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180149b35  test    rcx, rcx
0x180149b38  jnz     short loc_180149B81
0x180149b3a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180149b41  nop     dword ptr [rax+rax+00h]
0x180149b46  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180149b4d  mov     rcx, rax
0x180149b50  test    rax, rax
0x180149b53  jz      short loc_180149B73
0x180149b55  mov     rax, [rax]
0x180149b58  mov     edx, 7F0h
0x180149b5d  mov     rax, [rax+8]
0x180149b61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180149b66  test    eax, eax
0x180149b68  jz      short loc_180149B73
0x180149b6a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180149b71  jmp     short loc_180149B81
0x180149b73  lea     rcx, qword_1801B97E0; this
0x180149b7a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180149b81  cmp     byte ptr [rcx+8], 0
0x180149b85  jz      short loc_180149BA8
0x180149b87  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180149b8c  cmp     [rax+7CCh], ebx
0x180149b92  jz      short loc_180149BA8
0x180149b94  mov     r9d, ebx; int
0x180149b97  mov     r8d, 277h; int
0x180149b9d  mov     rdx, r12; char *
0x180149ba0  mov     rcx, rax; this
0x180149ba3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180149ba8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180149baf  jb      loc_180149C7C
0x180149bb5  mov     edx, 29h ; ')'
0x180149bba  jmp     loc_180149C5E
0x180149bbf  mov     edx, 1
0x180149bc4  mov     rcx, rdi
0x180149bc7  call    ?SetState@CMFByteStreamMediaSource@@AEAAJW4MEDIA_SOURCE_STATE@1@@Z; CMFByteStreamMediaSource::SetState(CMFByteStreamMediaSource::MEDIA_SOURCE_STATE)
0x180149bcc  mov     ebx, eax
0x180149bce  test    eax, eax
0x180149bd0  jns     loc_180149C7C
0x180149bd6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180149bdd  test    rcx, rcx
0x180149be0  jnz     short loc_180149C29
0x180149be2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180149be9  nop     dword ptr [rax+rax+00h]
0x180149bee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180149bf5  mov     rcx, rax
0x180149bf8  test    rax, rax
0x180149bfb  jz      short loc_180149C1B
0x180149bfd  mov     rax, [rax]
0x180149c00  mov     edx, 7F0h
0x180149c05  mov     rax, [rax+8]
0x180149c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180149c0e  test    eax, eax
0x180149c10  jz      short loc_180149C1B
0x180149c12  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180149c19  jmp     short loc_180149C29
0x180149c1b  lea     rcx, qword_1801B97E0; this
0x180149c22  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180149c29  cmp     byte ptr [rcx+8], 0
0x180149c2d  jz      short loc_180149C50
0x180149c2f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180149c34  cmp     [rax+7CCh], ebx
0x180149c3a  jz      short loc_180149C50
0x180149c3c  mov     r9d, ebx; int
0x180149c3f  mov     r8d, 27Eh; int
0x180149c45  mov     rdx, r12; char *
0x180149c48  mov     rcx, rax; this
0x180149c4b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180149c50  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180149c57  jb      short loc_180149C7C
0x180149c59  mov     edx, 2Ah ; '*'
0x180149c5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180149c65  lea     r8, WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids
0x180149c6c  mov     r9, rdi
0x180149c6f  mov     [rsp+58h+var_38], ebx
0x180149c73  mov     rcx, [rcx+10h]
0x180149c77  call    WPP_SF_qD
0x180149c7c  mov     rcx, rsi; this
0x180149c7f  call    ?Release@CBaseOperation@@QEAAKXZ; CBaseOperation::Release(void)
0x180149c84  jmp     loc_180149D34
0x180149c89  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180149c90  mov     ebx, 8007000Eh
0x180149c95  test    rcx, rcx
0x180149c98  jnz     short loc_180149CE1
0x180149c9a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180149ca1  nop     dword ptr [rax+rax+00h]
0x180149ca6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180149cad  mov     rcx, rax
0x180149cb0  test    rax, rax
0x180149cb3  jz      short loc_180149CD3
0x180149cb5  mov     rax, [rax]
0x180149cb8  mov     edx, 7F0h
0x180149cbd  mov     rax, [rax+8]
0x180149cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180149cc6  test    eax, eax
0x180149cc8  jz      short loc_180149CD3
0x180149cca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180149cd1  jmp     short loc_180149CE1
0x180149cd3  lea     rcx, qword_1801B97E0; this
0x180149cda  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
