# CMFByteStreamMediaSource::BeginOpen(IMFAsyncCallback *,IUnknown *,IMFAsyncResult * *)

- ea: `0x180141a24`
- end: `0x180141f82`
- name: `?BeginOpen@CMFByteStreamMediaSource@@QEAAJPEAUIMFAsyncCallback@@PEAUIUnknown@@PEAPEAUIMFAsyncResult@@@Z`
- size: `1374`
- prototype: `int(CMFByteStreamMediaSource *__hidden this, struct IMFAsyncCallback *, struct IUnknown *, struct IMFAsyncResult **)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1801141d0`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180073b14`
- `0x180076bf8`
- `0x18009a264`
- `0x1801095a8`
- `0x180140fa8`
- `0x180141a24`
- `0x1801453b4`
- `0x180165230`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180141f55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180141f55`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180141a6a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180141a6a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180141a8e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180141b27`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180141bcf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180141c77`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180141d6a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180141e0c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180141ebe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180141a8e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180141b27`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180141bcf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180141c77`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180141d6a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180141e0c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180141ebe`
- `MFPlat!MFCreateAsyncResult` at `0x180141c5b`
- `MFPlat!MFCreateAsyncResult` at `0x180141c5b`

## string_xrefs

- `0x180141a37`: `CMFByteStreamMediaSource::BeginOpen`

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
        v8 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v17 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v21 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v37 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v34 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v29 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
      v13 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
0x180141a24  mov     [rsp+arg_8], rbx
0x180141a29  push    rbp
0x180141a2a  push    rsi
0x180141a2b  push    rdi
0x180141a2c  push    r12
0x180141a2e  push    r14
0x180141a30  sub     rsp, 30h
0x180141a34  mov     rbp, r8
0x180141a37  lea     r12, aCmfbytestreamm_34; "CMFByteStreamMediaSource::BeginOpen"
0x180141a3e  mov     rsi, rdx
0x180141a41  mov     rdi, rcx
0x180141a44  mov     rdx, r12; char *
0x180141a47  lea     rcx, [rsp+58h+arg_18]; this
0x180141a4c  mov     r8d, 25Ch; int
0x180141a52  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180141a57  lea     r14, [rdi+2C8h]
0x180141a5e  mov     [rsp+58h+ppAsyncResult], 0
0x180141a67  mov     rcx, r14; lpCriticalSection
0x180141a6a  call    cs:__imp_EnterCriticalSection
0x180141a70  cmp     dword ptr [rdi+454h], 0
0x180141a77  jz      loc_180141B0D
0x180141a7d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180141a84  mov     ebx, 0C00D36B2h
0x180141a89  test    rcx, rcx
0x180141a8c  jnz     short loc_180141ACF
0x180141a8e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180141a94  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180141a9b  mov     rcx, rax
0x180141a9e  test    rax, rax
0x180141aa1  jz      short loc_180141AC1
0x180141aa3  mov     rax, [rax]
0x180141aa6  mov     edx, 7F0h
0x180141aab  mov     rax, [rax+8]
0x180141aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180141ab4  test    eax, eax
0x180141ab6  jz      short loc_180141AC1
0x180141ab8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180141abf  jmp     short loc_180141ACF
0x180141ac1  lea     rcx, qword_1801B07E0; this
0x180141ac8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180141acf  cmp     byte ptr [rcx+8], 0
0x180141ad3  jz      short loc_180141AF6
0x180141ad5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180141ada  cmp     [rax+7CCh], ebx
0x180141ae0  jz      short loc_180141AF6
0x180141ae2  mov     r9d, ebx; int
0x180141ae5  mov     r8d, 265h; int
0x180141aeb  mov     rdx, r12; char *
0x180141aee  mov     rcx, rax; this
0x180141af1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180141af6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180141afd  jb      loc_180141F52
0x180141b03  mov     edx, 24h ; '$'
0x180141b08  jmp     loc_180141F34
0x180141b0d  test    rsi, rsi
0x180141b10  jnz     loc_180141BA6
0x180141b16  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180141b1d  mov     ebx, 80004003h
0x180141b22  test    rcx, rcx
0x180141b25  jnz     short loc_180141B68
0x180141b27  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180141b2d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180141b34  mov     rcx, rax
0x180141b37  test    rax, rax
0x180141b3a  jz      short loc_180141B5A
0x180141b3c  mov     rax, [rax]
0x180141b3f  mov     edx, 7F0h
0x180141b44  mov     rax, [rax+8]
0x180141b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180141b4d  test    eax, eax
0x180141b4f  jz      short loc_180141B5A
0x180141b51  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180141b58  jmp     short loc_180141B68
0x180141b5a  lea     rcx, qword_1801B07E0; this
0x180141b61  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180141b68  cmp     byte ptr [rcx+8], 0
0x180141b6c  jz      short loc_180141B8F
0x180141b6e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180141b73  cmp     [rax+7CCh], ebx
0x180141b79  jz      short loc_180141B8F
0x180141b7b  mov     r9d, ebx; int
0x180141b7e  mov     r8d, 268h; int
0x180141b84  mov     rdx, r12; char *
0x180141b87  mov     rcx, rax; this
0x180141b8a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180141b8f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180141b96  jb      loc_180141F52
0x180141b9c  mov     edx, 25h ; '%'
0x180141ba1  jmp     loc_180141F34
0x180141ba6  lea     rdx, [rdi+2A8h]; struct IMFAsyncCallback *
0x180141bad  lea     rcx, [rdi+460h]; this
0x180141bb4  call    ?BeginGetByteStreamEvent@CMFByteStreamSourceReader@@QEAAJPEAUIMFAsyncCallback@@@Z; CMFByteStreamSourceReader::BeginGetByteStreamEvent(IMFAsyncCallback *)
0x180141bb9  mov     ebx, eax
0x180141bbb  test    eax, eax
0x180141bbd  jns     loc_180141C4E
0x180141bc3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180141bca  test    rcx, rcx
0x180141bcd  jnz     short loc_180141C10
0x180141bcf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180141bd5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180141bdc  mov     rcx, rax
0x180141bdf  test    rax, rax
0x180141be2  jz      short loc_180141C02
0x180141be4  mov     rax, [rax]
0x180141be7  mov     edx, 7F0h
0x180141bec  mov     rax, [rax+8]
0x180141bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180141bf5  test    eax, eax
0x180141bf7  jz      short loc_180141C02
0x180141bf9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180141c00  jmp     short loc_180141C10
0x180141c02  lea     rcx, qword_1801B07E0; this
0x180141c09  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180141c10  cmp     byte ptr [rcx+8], 0
0x180141c14  jz      short loc_180141C37
0x180141c16  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180141c1b  cmp     [rax+7CCh], ebx
0x180141c21  jz      short loc_180141C37
0x180141c23  mov     r9d, ebx; int
0x180141c26  mov     r8d, 26Dh; int
0x180141c2c  mov     rdx, r12; char *
0x180141c2f  mov     rcx, rax; this
0x180141c32  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180141c37  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180141c3e  jb      loc_180141F52
0x180141c44  mov     edx, 26h ; '&'
0x180141c49  jmp     loc_180141F34
0x180141c4e  lea     r9, [rsp+58h+ppAsyncResult]; ppAsyncResult
0x180141c53  mov     r8, rbp; punkState
0x180141c56  mov     rdx, rsi; pCallback
0x180141c59  xor     ecx, ecx; punkObject
0x180141c5b  call    cs:__imp_MFCreateAsyncResult
0x180141c61  mov     ebx, eax
0x180141c63  test    eax, eax
0x180141c65  jns     loc_180141CF6
0x180141c6b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180141c72  test    rcx, rcx
0x180141c75  jnz     short loc_180141CB8
0x180141c77  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180141c7d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180141c84  mov     rcx, rax
0x180141c87  test    rax, rax
0x180141c8a  jz      short loc_180141CAA
0x180141c8c  mov     rax, [rax]
0x180141c8f  mov     edx, 7F0h
0x180141c94  mov     rax, [rax+8]
0x180141c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180141c9d  test    eax, eax
0x180141c9f  jz      short loc_180141CAA
0x180141ca1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180141ca8  jmp     short loc_180141CB8
0x180141caa  lea     rcx, qword_1801B07E0; this
0x180141cb1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180141cb8  cmp     byte ptr [rcx+8], 0
0x180141cbc  jz      short loc_180141CDF
0x180141cbe  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180141cc3  cmp     [rax+7CCh], ebx
0x180141cc9  jz      short loc_180141CDF
0x180141ccb  mov     r9d, ebx; int
0x180141cce  mov     r8d, 272h; int
0x180141cd4  mov     rdx, r12; char *
0x180141cd7  mov     rcx, rax; this
0x180141cda  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180141cdf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180141ce6  jb      loc_180141F52
0x180141cec  mov     edx, 27h ; '''
0x180141cf1  jmp     loc_180141F34
0x180141cf6  mov     ecx, 38h ; '8'; Size
0x180141cfb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180141d00  mov     rsi, rax
0x180141d03  test    rax, rax
0x180141d06  jz      loc_180141EAD
0x180141d0c  mov     rbx, [rsp+58h+ppAsyncResult]
0x180141d11  xor     r9d, r9d
0x180141d14  mov     r8, rdi
0x180141d17  mov     rcx, rax
0x180141d1a  lea     edx, [r9+1]
0x180141d1e  call    ??0CMediaSourceOp@@QEAA@W4MEDIA_SOURCE_OPERATION@0@PEAUIMFMediaEventGenerator@@K@Z; CMediaSourceOp::CMediaSourceOp(CMediaSourceOp::MEDIA_SOURCE_OPERATION,IMFMediaEventGenerator *,ulong)
0x180141d23  lea     rax, ??_7CMediaSourceOpOpen@@6B@; const CMediaSourceOpOpen::`vftable'
0x180141d2a  mov     [rsi], rax
0x180141d2d  mov     [rsi+30h], rbx
0x180141d31  test    rbx, rbx
0x180141d34  jz      short loc_180141D45
0x180141d36  mov     rax, [rbx]
0x180141d39  mov     rcx, rbx
0x180141d3c  mov     rax, [rax+8]
0x180141d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180141d45  lea     rcx, [rdi+58h]; this
0x180141d49  xor     r8d, r8d; int
0x180141d4c  mov     rdx, rsi; struct CBaseOperation *
0x180141d4f  call    ?QueueOperation@COpQueue@@QEAAJPEAVCBaseOperation@@H@Z; COpQueue::QueueOperation(CBaseOperation *,int)
0x180141d54  mov     ebx, eax
0x180141d56  test    eax, eax
0x180141d58  jns     loc_180141DE9
0x180141d5e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180141d65  test    rcx, rcx
0x180141d68  jnz     short loc_180141DAB
0x180141d6a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180141d70  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180141d77  mov     rcx, rax
0x180141d7a  test    rax, rax
0x180141d7d  jz      short loc_180141D9D
0x180141d7f  mov     rax, [rax]
0x180141d82  mov     edx, 7F0h
0x180141d87  mov     rax, [rax+8]
0x180141d8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180141d90  test    eax, eax
0x180141d92  jz      short loc_180141D9D
0x180141d94  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180141d9b  jmp     short loc_180141DAB
0x180141d9d  lea     rcx, qword_1801B07E0; this
0x180141da4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180141dab  cmp     byte ptr [rcx+8], 0
0x180141daf  jz      short loc_180141DD2
0x180141db1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180141db6  cmp     [rax+7CCh], ebx
0x180141dbc  jz      short loc_180141DD2
0x180141dbe  mov     r9d, ebx; int
0x180141dc1  mov     r8d, 277h; int
0x180141dc7  mov     rdx, r12; char *
0x180141dca  mov     rcx, rax; this
0x180141dcd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180141dd2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180141dd9  jb      loc_180141EA0
0x180141ddf  mov     edx, 29h ; ')'
0x180141de4  jmp     loc_180141E82
0x180141de9  mov     edx, 1
0x180141dee  mov     rcx, rdi
0x180141df1  call    ?SetState@CMFByteStreamMediaSource@@AEAAJW4MEDIA_SOURCE_STATE@1@@Z; CMFByteStreamMediaSource::SetState(CMFByteStreamMediaSource::MEDIA_SOURCE_STATE)
0x180141df6  mov     ebx, eax
0x180141df8  test    eax, eax
0x180141dfa  jns     loc_180141EA0
0x180141e00  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180141e07  test    rcx, rcx
0x180141e0a  jnz     short loc_180141E4D
0x180141e0c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180141e12  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180141e19  mov     rcx, rax
0x180141e1c  test    rax, rax
0x180141e1f  jz      short loc_180141E3F
0x180141e21  mov     rax, [rax]
0x180141e24  mov     edx, 7F0h
0x180141e29  mov     rax, [rax+8]
0x180141e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180141e32  test    eax, eax
0x180141e34  jz      short loc_180141E3F
0x180141e36  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180141e3d  jmp     short loc_180141E4D
0x180141e3f  lea     rcx, qword_1801B07E0; this
0x180141e46  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180141e4d  cmp     byte ptr [rcx+8], 0
0x180141e51  jz      short loc_180141E74
0x180141e53  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180141e58  cmp     [rax+7CCh], ebx
0x180141e5e  jz      short loc_180141E74
0x180141e60  mov     r9d, ebx; int
0x180141e63  mov     r8d, 27Eh; int
0x180141e69  mov     rdx, r12; char *
0x180141e6c  mov     rcx, rax; this
0x180141e6f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180141e74  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180141e7b  jb      short loc_180141EA0
0x180141e7d  mov     edx, 2Ah ; '*'
0x180141e82  mov     rcx, cs:WPP_GLOBAL_Control
0x180141e89  lea     r8, WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids
0x180141e90  mov     r9, rdi
0x180141e93  mov     [rsp+58h+var_38], ebx
0x180141e97  mov     rcx, [rcx+10h]
0x180141e9b  call    WPP_SF_qD
0x180141ea0  mov     rcx, rsi; this
0x180141ea3  call    ?Release@CBaseOperation@@QEAAKXZ; CBaseOperation::Release(void)
0x180141ea8  jmp     loc_180141F52
0x180141ead  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180141eb4  mov     ebx, 8007000Eh
0x180141eb9  test    rcx, rcx
0x180141ebc  jnz     short loc_180141EFF
0x180141ebe  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180141ec4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180141ecb  mov     rcx, rax
0x180141ece  test    rax, rax
0x180141ed1  jz      short loc_180141EF1
0x180141ed3  mov     rax, [rax]
0x180141ed6  mov     edx, 7F0h
0x180141edb  mov     rax, [rax+8]
0x180141edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180141ee4  test    eax, eax
0x180141ee6  jz      short loc_180141EF1
0x180141ee8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180141eef  jmp     short loc_180141EFF
0x180141ef1  lea     rcx, qword_1801B07E0; this
0x180141ef8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180141eff  cmp     byte ptr [rcx+8], 0
0x180141f03  jz      short loc_180141F26
0x180141f05  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180141f0a  cmp     [rax+7CCh], ebx
0x180141f10  jz      short loc_180141F26
0x180141f12  mov     r9d, ebx; int
0x180141f15  mov     r8d, 275h; int
0x180141f1b  mov     rdx, r12; char *
0x180141f1e  mov     rcx, rax; this
  ... truncated ...
```
