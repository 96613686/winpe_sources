# CByteStreamCacheReader2::BeginCacheRead(IMFAsyncCallback *,IUnknown *)

- ea: `0x18002f918`
- end: `0x18003005c`
- name: `?BeginCacheRead@CByteStreamCacheReader2@@QEAAJPEAUIMFAsyncCallback@@PEAUIUnknown@@@Z`
- size: `1860`
- prototype: `__int64 __fastcall(CByteStreamCacheReader2 *__hidden this, struct IMFAsyncCallback *, struct IUnknown *)`
- caller_count: `3`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002e708`
- `0x18005ca98`
- `0x18005fb60`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x18002f904`
- `0x18002f918`
- `0x180030064`
- `0x180030490`
- `0x180030604`
- `0x180071a44`
- `0x180073b14`
- `0x180074378`
- `0x1800b322c`
- `0x1801095a8`
- `0x18011b1e4`
- `0x1801688fc`
- `0x180168f2c`
- `0x180168fb4`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030033`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030033`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f9b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f9b6`
- `MFPlat!MFLockPlatform` at `0x18002fbbf`
- `MFPlat!MFLockPlatform` at `0x18002fbbf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002fa43`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002faf6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002fc4f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002fd5b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002fe12`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002ff0a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002fa43`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002faf6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002fc4f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002fd5b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002fe12`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002ff0a`

## string_xrefs

- `0x18002f952`: `CByteStreamCacheReader2::BeginCacheRead`
- `0x18002f9f9`: `CByteStreamCacheReader2::BeginCacheRead`
- `0x18002fa9a`: `CByteStreamCacheReader2::BeginCacheRead`
- `0x18002fb4d`: `CByteStreamCacheReader2::BeginCacheRead`
- `0x18002fca6`: `CByteStreamCacheReader2::BeginCacheRead`
- `0x18002fdb2`: `CByteStreamCacheReader2::BeginCacheRead`
- `0x18002fe69`: `CByteStreamCacheReader2::BeginCacheRead`
- `0x18002ff75`: `CByteStreamCacheReader2::BeginCacheRead`

## pseudocode

```c
__int64 __fastcall CByteStreamCacheReader2::BeginCacheRead(
        CByteStreamCacheReader2 *this,
        struct IMFAsyncCallback *a2,
        struct IUnknown *a3)
{
  CallStackTracing *v4; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v8; // rcx
  __int64 v9; // rcx
  CallStackTracing *v10; // rcx
  int Request; // ebx
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  unsigned __int64 v18; // rdx
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  tagMFASYNCRESULT *v22; // rax
  __int64 v23; // rdx
  tagMFASYNCRESULT *v24; // rbx
  __int64 v25; // rcx
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rdx
  wchar_t *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  wchar_t *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  int v38; // eax
  __int64 v39; // rdx
  wchar_t *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // rcx
  int v45; // [rsp+60h] [rbp+8h] BYREF

  v4 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v4 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v4 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v4);
    v8 = *((unsigned int *)ThreadRelativeContext + 497);
    if ( (unsigned int)v8 < *((_DWORD *)ThreadRelativeContext + 498) )
    {
      v9 = 2 * v8;
      *((_QWORD *)ThreadRelativeContext + v9) = "CByteStreamCacheReader2::BeginCacheRead";
      *((_DWORD *)ThreadRelativeContext + 2 * v9 + 2) = 372;
    }
    ++*((_DWORD *)ThreadRelativeContext + 497);
  }
  if ( g_wppLevels >= 0x20u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids, this);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v45 = 0;
  if ( !a2 )
  {
    v10 = CallStackTracing::s_wpInstance;
    Request = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v10 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext(v10);
      if ( *((_DWORD *)v12 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v12, "CByteStreamCacheReader2::BeginCacheRead", 379, -2147024809);
    }
    if ( !g_wppLevels )
      goto LABEL_107;
    v13 = 42;
    goto LABEL_106;
  }
  Request = CByteStreamCacheReader2::_ValidateReadRequest(this);
  if ( Request < 0 )
  {
    v15 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
      CallStackTracing::s_wpInstance = v16;
      if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
      {
        v15 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v15 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v15 + 8) )
    {
      v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
      if ( *((_DWORD *)v17 + 499) != Request )
        CallStackContext::TraceFailure(v17, "CByteStreamCacheReader2::BeginCacheRead", 388, Request);
    }
    if ( !g_wppLevels )
      goto LABEL_107;
    v13 = 43;
    goto LABEL_106;
  }
  v18 = *((_QWORD *)this + 10) % (unsigned __int64)*((unsigned int *)this + 16);
  if ( v18 && *((_DWORD *)this + 23) )
  {
    v19 = (wchar_t *)CallStackTracing::s_wpInstance;
    Request = -1072875803;
    if ( !CallStackTracing::s_wpInstance )
    {
      v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
      CallStackTracing::s_wpInstance = v20;
      if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
      {
        v19 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v19 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v19 + 8) )
    {
      v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
      if ( *((_DWORD *)v21 + 499) != -1072875803 )
        CallStackContext::TraceFailure(v21, "CByteStreamCacheReader2::BeginCacheRead", 395, -1072875803);
    }
    if ( !g_wppLevels )
      goto LABEL_107;
    v13 = 44;
    goto LABEL_106;
  }
  v22 = (tagMFASYNCRESULT *)operator new(0x80u);
  v24 = v22;
  if ( v22 )
  {
    tagMFASYNCRESULT::tagMFASYNCRESULT(v22);
    *(_QWORD *)(v25 + 64) = &CMFRefCounted::`vftable';
    *(_DWORD *)(v25 + 72) = 0;
    *(_QWORD *)v25 = &CMP3ByteStreamPluginResult::`vftable'{for `tagMFASYNCRESULT'};
    *(_QWORD *)(v25 + 64) = &CAsyncResult::`vftable'{for `CMFRefCounted'};
    *(_DWORD *)(v25 + 96) = 0;
    MFLockPlatform();
    HIDWORD(v24[1].overlapped.hEvent) = 0;
    v24->hrStatusResult = 0;
    v24->hEvent = 0;
    v24[1].overlapped.InternalHigh = 0;
    v24[1].overlapped.Pointer = a3;
    if ( a3 )
      ((void (__fastcall *)(struct IUnknown *))a3->lpVtbl->AddRef)(a3);
    v24->pCallback = a2;
    ((void (__fastcall *)(struct IMFAsyncCallback *))a2->lpVtbl->AddRef)(a2);
    *(_OWORD *)&v24->overlapped.Internal = 0;
    *(_OWORD *)&v24->overlapped.Offset = 0;
    v24->AsyncResult.lpVtbl = (struct IMFAsyncResultVtbl *)&CMP3ByteStreamPluginResult::`vftable'{for `tagMFASYNCRESULT'};
    v24[1].AsyncResult.lpVtbl = (struct IMFAsyncResultVtbl *)&CByteStreamCacheResult::`vftable'{for `CMFRefCounted'};
    v24->dwBytesTransferred = 0;
    v24[1].pCallback = 0;
    v24[1].hEvent = 0;
  }
  else
  {
    v24 = 0;
  }
  *((_QWORD *)this + 12) = v24;
  if ( !v24 )
  {
    v26 = (wchar_t *)CallStackTracing::s_wpInstance;
    Request = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
      CallStackTracing::s_wpInstance = v27;
      if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
      {
        v26 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v26 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v26 + 8) )
    {
      v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
      if ( *((_DWORD *)v28 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v28, "CByteStreamCacheReader2::BeginCacheRead", 402, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_107;
    v13 = 45;
    goto LABEL_106;
  }
  *(_QWORD *)&v24[1].hrStatusResult = *((_QWORD *)this + 10);
  *(_DWORD *)(*((_QWORD *)this + 12) + 124LL) = *((_DWORD *)this + 23);
  if ( (unsigned __int8)byte_1801B110B >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 46, &WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids, this);
  CByteStreamCacheReader2::_TracePendingCacheRead(this);
  v29 = *((_QWORD *)this + 12);
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
  if ( *((_DWORD *)this + 23) )
  {
    Request = CByteStreamCacheReader2::_TruncateCache(
                this,
                *((_QWORD *)this + 10),
                *((_QWORD *)this + 10) + *((unsigned int *)this + 17));
    if ( Request < 0 )
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
          v31 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v31 + 8) )
      {
        v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
        if ( *((_DWORD *)v33 + 499) != Request )
          CallStackContext::TraceFailure(v33, "CByteStreamCacheReader2::BeginCacheRead", 417, Request);
      }
      if ( !g_wppLevels )
        goto LABEL_107;
      v13 = 47;
      goto LABEL_106;
    }
    if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
      CByteStreamCacheReader2::_FireWMIEvent(this);
    Request = CByteStreamCacheReader2::_FillPendingCacheRead(this, &v45);
    if ( Request < 0 )
    {
      v35 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34);
        CallStackTracing::s_wpInstance = v36;
        if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
        {
          v35 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v35 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v35 + 8) )
      {
        v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
        if ( *((_DWORD *)v37 + 499) != Request )
          CallStackContext::TraceFailure(v37, "CByteStreamCacheReader2::BeginCacheRead", 432, Request);
      }
      if ( !g_wppLevels )
        goto LABEL_107;
      v13 = 48;
      goto LABEL_106;
    }
    v38 = CByteStreamCacheReader2::_BeginCacheEnabledRead(this);
  }
  else
  {
    v38 = CByteStreamCacheReader2::_BeginCacheDisabledRead(this);
  }
  Request = v38;
  if ( v38 == -2147483638 )
  {
    if ( (unsigned __int8)byte_1801B110B >= 4u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 49, &WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids, this);
    Request = 0;
LABEL_91:
    if ( *((_DWORD *)this + 29) )
      goto LABEL_111;
    Request = CByteStreamCacheReader2::_SetCurrentPosition(this, *((_QWORD *)this + 10) + *((unsigned int *)this + 16));
    if ( Request >= 0 )
      goto LABEL_111;
    v40 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39);
      CallStackTracing::s_wpInstance = v41;
      if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
      {
        v40 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v40 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v40 + 8) )
    {
      v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
      if ( *((_DWORD *)v42 + 499) != Request )
        CallStackContext::TraceFailure(v42, "CByteStreamCacheReader2::BeginCacheRead", 457, Request);
    }
    if ( g_wppLevels )
    {
      v13 = 51;
      goto LABEL_106;
    }
    goto LABEL_107;
  }
  if ( v38 >= 0 )
    goto LABEL_91;
  if ( g_wppLevels )
  {
    v13 = 50;
LABEL_106:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids, this, Request);
  }
LABEL_107:
  if ( (unsigned __int8)byte_1801B110B >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 52, &WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids, this);
  CByteStreamCacheReader2::_TracePendingCacheRead(this);
  v43 = *((_QWORD *)this + 12);
  if ( v43 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    *((_QWORD *)this + 12) = 0;
  }
LABEL_111:
  if ( v45 == 1 )
  {
    if ( (unsigned __int8)byte_1801B110B >= 8u )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 17),
        53,
        &WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids,
        this,
        Request);
    Request = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v45);
  return (unsigned int)Request;
}

```

## disassembly

```asm
0x18002f918  mov     [rsp+arg_8], rbx
0x18002f91d  mov     [rsp+arg_10], rbp
0x18002f922  push    rsi
0x18002f923  push    rdi
0x18002f924  push    r13
0x18002f926  push    r14
0x18002f928  push    r15
0x18002f92a  sub     rsp, 30h
0x18002f92e  mov     rdi, rcx
0x18002f931  xor     r15d, r15d
0x18002f934  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f93b  mov     rsi, r8
0x18002f93e  mov     r14, rdx
0x18002f941  test    rcx, rcx
0x18002f944  jnz     short loc_18002F952
0x18002f946  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002f94b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002f952  lea     rbx, aCbytestreamcac_19; "CByteStreamCacheReader2::BeginCacheRead"
0x18002f959  cmp     [rcx+8], r15b
0x18002f95d  jz      short loc_18002F987
0x18002f95f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002f964  mov     ecx, [rax+7C4h]
0x18002f96a  cmp     ecx, [rax+7C8h]
0x18002f970  jnb     short loc_18002F981
0x18002f972  add     rcx, rcx
0x18002f975  mov     [rax+rcx*8], rbx
0x18002f979  mov     dword ptr [rax+rcx*8+8], 174h
0x18002f981  inc     dword ptr [rax+7C4h]
0x18002f987  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x18002f98e  lea     r13, WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids
0x18002f995  jb      short loc_18002F9B2
0x18002f997  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f99e  mov     edx, 29h ; ')'
0x18002f9a3  mov     r9, rdi
0x18002f9a6  mov     r8, r13
0x18002f9a9  mov     rcx, [rcx+10h]
0x18002f9ad  call    WPP_SF_q
0x18002f9b2  lea     rcx, [rdi+10h]; lpCriticalSection
0x18002f9b6  call    cs:__imp_EnterCriticalSection
0x18002f9bc  mov     [rsp+58h+arg_0], r15d
0x18002f9c1  test    r14, r14
0x18002f9c4  jnz     short loc_18002FA25
0x18002f9c6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f9cd  mov     ebx, 80070057h
0x18002f9d2  test    rcx, rcx
0x18002f9d5  jnz     short loc_18002F9E3
0x18002f9d7  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002f9dc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002f9e3  cmp     [rcx+8], r15b
0x18002f9e7  jz      short loc_18002FA0E
0x18002f9e9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002f9ee  cmp     [rax+7CCh], ebx
0x18002f9f4  jz      short loc_18002FA0E
0x18002f9f6  mov     r9d, ebx; int
0x18002f9f9  lea     rdx, aCbytestreamcac_19; "CByteStreamCacheReader2::BeginCacheRead"
0x18002fa00  mov     r8d, 17Bh; int
0x18002fa06  mov     rcx, rax; this
0x18002fa09  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002fa0e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002fa15  jb      loc_18002FFB2
0x18002fa1b  mov     edx, 2Ah ; '*'
0x18002fa20  jmp     loc_18002FF98
0x18002fa25  mov     rcx, rdi; this
0x18002fa28  call    ?_ValidateReadRequest@CByteStreamCacheReader2@@IEAAJXZ; CByteStreamCacheReader2::_ValidateReadRequest(void)
0x18002fa2d  mov     ebx, eax
0x18002fa2f  test    eax, eax
0x18002fa31  jns     loc_18002FAC6
0x18002fa37  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002fa3e  test    rcx, rcx
0x18002fa41  jnz     short loc_18002FA84
0x18002fa43  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002fa49  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002fa50  mov     rcx, rax
0x18002fa53  test    rax, rax
0x18002fa56  jz      short loc_18002FA76
0x18002fa58  mov     rax, [rax]
0x18002fa5b  mov     edx, 7F0h
0x18002fa60  mov     rax, [rax+8]
0x18002fa64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa69  test    eax, eax
0x18002fa6b  jz      short loc_18002FA76
0x18002fa6d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002fa74  jmp     short loc_18002FA84
0x18002fa76  lea     rcx, qword_1801B07E0; this
0x18002fa7d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002fa84  cmp     [rcx+8], r15b
0x18002fa88  jz      short loc_18002FAAF
0x18002fa8a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002fa8f  cmp     [rax+7CCh], ebx
0x18002fa95  jz      short loc_18002FAAF
0x18002fa97  mov     r9d, ebx; int
0x18002fa9a  lea     rdx, aCbytestreamcac_19; "CByteStreamCacheReader2::BeginCacheRead"
0x18002faa1  mov     r8d, 184h; int
0x18002faa7  mov     rcx, rax; this
0x18002faaa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002faaf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002fab6  jb      loc_18002FFB2
0x18002fabc  mov     edx, 2Bh ; '+'
0x18002fac1  jmp     loc_18002FF98
0x18002fac6  mov     ecx, [rdi+40h]
0x18002fac9  xor     edx, edx
0x18002facb  mov     rax, [rdi+50h]
0x18002facf  div     rcx
0x18002fad2  test    rdx, rdx
0x18002fad5  jz      loc_18002FB79
0x18002fadb  cmp     [rdi+5Ch], r15d
0x18002fadf  jz      loc_18002FB79
0x18002fae5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002faec  mov     ebx, 0C00D36E5h
0x18002faf1  test    rcx, rcx
0x18002faf4  jnz     short loc_18002FB37
0x18002faf6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002fafc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002fb03  mov     rcx, rax
0x18002fb06  test    rax, rax
0x18002fb09  jz      short loc_18002FB29
0x18002fb0b  mov     rax, [rax]
0x18002fb0e  mov     edx, 7F0h
0x18002fb13  mov     rax, [rax+8]
0x18002fb17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb1c  test    eax, eax
0x18002fb1e  jz      short loc_18002FB29
0x18002fb20  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002fb27  jmp     short loc_18002FB37
0x18002fb29  lea     rcx, qword_1801B07E0; this
0x18002fb30  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002fb37  cmp     [rcx+8], r15b
0x18002fb3b  jz      short loc_18002FB62
0x18002fb3d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002fb42  cmp     [rax+7CCh], ebx
0x18002fb48  jz      short loc_18002FB62
0x18002fb4a  mov     r9d, ebx; int
0x18002fb4d  lea     rdx, aCbytestreamcac_19; "CByteStreamCacheReader2::BeginCacheRead"
0x18002fb54  mov     r8d, 18Bh; int
0x18002fb5a  mov     rcx, rax; this
0x18002fb5d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002fb62  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002fb69  jb      loc_18002FFB2
0x18002fb6f  mov     edx, 2Ch ; ','
0x18002fb74  jmp     loc_18002FF98
0x18002fb79  mov     ecx, 80h; Size
0x18002fb7e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002fb83  mov     rbx, rax
0x18002fb86  test    rax, rax
0x18002fb89  jz      loc_18002FC2E
0x18002fb8f  mov     rcx, rax; this
0x18002fb92  call    ??0tagMFASYNCRESULT@@QEAA@XZ; tagMFASYNCRESULT::tagMFASYNCRESULT(void)
0x18002fb97  lea     rax, ??_7CMFRefCounted@@6B@; const CMFRefCounted::`vftable'
0x18002fb9e  mov     [rcx+40h], rax
0x18002fba2  lea     rax, ??_7CMP3ByteStreamPluginResult@@6BtagMFASYNCRESULT@@@; const CMP3ByteStreamPluginResult::`vftable'{for `tagMFASYNCRESULT'}
0x18002fba9  mov     [rcx+48h], r15d
0x18002fbad  mov     [rcx], rax
0x18002fbb0  lea     rax, ??_7CAsyncResult@@6BCMFRefCounted@@@; const CAsyncResult::`vftable'{for `CMFRefCounted'}
0x18002fbb7  mov     [rcx+40h], rax
0x18002fbbb  mov     [rcx+60h], r15d
0x18002fbbf  call    cs:__imp_MFLockPlatform
0x18002fbc5  mov     [rbx+64h], r15d
0x18002fbc9  mov     [rbx+30h], r15d
0x18002fbcd  mov     [rbx+38h], r15
0x18002fbd1  mov     [rbx+50h], r15
0x18002fbd5  mov     [rbx+58h], rsi
0x18002fbd9  test    rsi, rsi
0x18002fbdc  jz      short loc_18002FBED
0x18002fbde  mov     rax, [rsi]
0x18002fbe1  mov     rcx, rsi
0x18002fbe4  mov     rax, [rax+8]
0x18002fbe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fbed  mov     [rbx+28h], r14
0x18002fbf1  mov     rcx, r14
0x18002fbf4  mov     rax, [r14]
0x18002fbf7  mov     rax, [rax+8]
0x18002fbfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc00  xorps   xmm0, xmm0
0x18002fc03  lea     rax, ??_7CMP3ByteStreamPluginResult@@6BtagMFASYNCRESULT@@@; const CMP3ByteStreamPluginResult::`vftable'{for `tagMFASYNCRESULT'}
0x18002fc0a  movups  xmmword ptr [rbx+8], xmm0
0x18002fc0e  movups  xmmword ptr [rbx+18h], xmm0
0x18002fc12  mov     [rbx], rax
0x18002fc15  lea     rax, ??_7CByteStreamCacheResult@@6BCMFRefCounted@@@; const CByteStreamCacheResult::`vftable'{for `CMFRefCounted'}
0x18002fc1c  mov     [rbx+40h], rax
0x18002fc20  mov     [rbx+34h], r15d
0x18002fc24  mov     [rbx+68h], r15
0x18002fc28  mov     [rbx+78h], r15
0x18002fc2c  jmp     short loc_18002FC31
0x18002fc2e  mov     rbx, r15
0x18002fc31  mov     [rdi+60h], rbx
0x18002fc35  test    rbx, rbx
0x18002fc38  jnz     loc_18002FCD2
0x18002fc3e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002fc45  mov     ebx, 8007000Eh
0x18002fc4a  test    rcx, rcx
0x18002fc4d  jnz     short loc_18002FC90
0x18002fc4f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002fc55  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002fc5c  mov     rcx, rax
0x18002fc5f  test    rax, rax
0x18002fc62  jz      short loc_18002FC82
0x18002fc64  mov     rax, [rax]
0x18002fc67  mov     edx, 7F0h
0x18002fc6c  mov     rax, [rax+8]
0x18002fc70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc75  test    eax, eax
0x18002fc77  jz      short loc_18002FC82
0x18002fc79  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002fc80  jmp     short loc_18002FC90
0x18002fc82  lea     rcx, qword_1801B07E0; this
0x18002fc89  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002fc90  cmp     [rcx+8], r15b
0x18002fc94  jz      short loc_18002FCBB
0x18002fc96  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002fc9b  cmp     [rax+7CCh], ebx
0x18002fca1  jz      short loc_18002FCBB
0x18002fca3  mov     r9d, ebx; int
0x18002fca6  lea     rdx, aCbytestreamcac_19; "CByteStreamCacheReader2::BeginCacheRead"
0x18002fcad  mov     r8d, 192h; int
0x18002fcb3  mov     rcx, rax; this
0x18002fcb6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002fcbb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002fcc2  jb      loc_18002FFB2
0x18002fcc8  mov     edx, 2Dh ; '-'
0x18002fccd  jmp     loc_18002FF98
0x18002fcd2  mov     rax, [rdi+50h]
0x18002fcd6  mov     [rbx+70h], rax
0x18002fcda  mov     rcx, [rdi+60h]
0x18002fcde  mov     eax, [rdi+5Ch]
0x18002fce1  mov     [rcx+7Ch], eax
0x18002fce4  cmp     cs:byte_1801B110B, 8
0x18002fceb  jb      short loc_18002FD0B
0x18002fced  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fcf4  mov     edx, 2Eh ; '.'
0x18002fcf9  mov     r9, rdi
0x18002fcfc  mov     r8, r13
0x18002fcff  mov     rcx, [rcx+88h]
0x18002fd06  call    WPP_SF_q
0x18002fd0b  mov     rcx, rdi; this
0x18002fd0e  call    ?_TracePendingCacheRead@CByteStreamCacheReader2@@IEAAXXZ; CByteStreamCacheReader2::_TracePendingCacheRead(void)
0x18002fd13  mov     rcx, [rdi+60h]
0x18002fd17  test    rcx, rcx
0x18002fd1a  jz      short loc_18002FD28
0x18002fd1c  mov     rax, [rcx]
0x18002fd1f  mov     rax, [rax+8]
0x18002fd23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd28  mov     rcx, rdi; this
0x18002fd2b  cmp     [rdi+5Ch], r15d
0x18002fd2f  jz      loc_18002FE9F
0x18002fd35  mov     rdx, [rdi+50h]; unsigned __int64
0x18002fd39  mov     r8d, [rdi+44h]
0x18002fd3d  add     r8, rdx; unsigned __int64
0x18002fd40  call    ?_TruncateCache@CByteStreamCacheReader2@@IEAAJ_K0@Z; CByteStreamCacheReader2::_TruncateCache(unsigned __int64,unsigned __int64)
0x18002fd45  mov     ebx, eax
0x18002fd47  test    eax, eax
0x18002fd49  jns     loc_18002FDDE
0x18002fd4f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002fd56  test    rcx, rcx
0x18002fd59  jnz     short loc_18002FD9C
0x18002fd5b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002fd61  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002fd68  mov     rcx, rax
0x18002fd6b  test    rax, rax
0x18002fd6e  jz      short loc_18002FD8E
0x18002fd70  mov     rax, [rax]
0x18002fd73  mov     edx, 7F0h
0x18002fd78  mov     rax, [rax+8]
0x18002fd7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd81  test    eax, eax
0x18002fd83  jz      short loc_18002FD8E
0x18002fd85  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002fd8c  jmp     short loc_18002FD9C
0x18002fd8e  lea     rcx, qword_1801B07E0; this
0x18002fd95  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002fd9c  cmp     [rcx+8], r15b
0x18002fda0  jz      short loc_18002FDC7
0x18002fda2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002fda7  cmp     [rax+7CCh], ebx
0x18002fdad  jz      short loc_18002FDC7
0x18002fdaf  mov     r9d, ebx; int
0x18002fdb2  lea     rdx, aCbytestreamcac_19; "CByteStreamCacheReader2::BeginCacheRead"
0x18002fdb9  mov     r8d, 1A1h; int
0x18002fdbf  mov     rcx, rax; this
0x18002fdc2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002fdc7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002fdce  jb      loc_18002FFB2
0x18002fdd4  mov     edx, 2Fh ; '/'
0x18002fdd9  jmp     loc_18002FF98
0x18002fdde  test    cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 1
0x18002fde5  jz      short loc_18002FDEF
0x18002fde7  mov     rcx, rdi; this
0x18002fdea  call    ?_FireWMIEvent@CByteStreamCacheReader2@@IEAAXXZ; CByteStreamCacheReader2::_FireWMIEvent(void)
0x18002fdef  lea     rdx, [rsp+58h+arg_0]; int *
0x18002fdf4  mov     rcx, rdi; this
0x18002fdf7  call    ?_FillPendingCacheRead@CByteStreamCacheReader2@@IEAAJPEAH@Z; CByteStreamCacheReader2::_FillPendingCacheRead(int *)
0x18002fdfc  mov     ebx, eax
0x18002fdfe  test    eax, eax
0x18002fe00  jns     loc_18002FE95
0x18002fe06  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002fe0d  test    rcx, rcx
0x18002fe10  jnz     short loc_18002FE53
0x18002fe12  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002fe18  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002fe1f  mov     rcx, rax
0x18002fe22  test    rax, rax
  ... truncated ...
```
