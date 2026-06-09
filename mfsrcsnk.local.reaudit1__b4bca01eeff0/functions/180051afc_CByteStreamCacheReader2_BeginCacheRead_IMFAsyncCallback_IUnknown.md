# CByteStreamCacheReader2::BeginCacheRead(IMFAsyncCallback *,IUnknown *)

- ea: `0x180051afc`
- end: `0x1800521fd`
- name: `?BeginCacheRead@CByteStreamCacheReader2@@QEAAJPEAUIMFAsyncCallback@@PEAUIUnknown@@@Z`
- size: `1793`
- prototype: `__int64 __fastcall(CByteStreamCacheReader2 *__hidden this, struct IMFAsyncCallback *, struct IUnknown *)`
- caller_count: `3`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800177b4`
- `0x18003a170`
- `0x180060378`

## callees

- `0x180005cf4`
- `0x180018880`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180051afc`
- `0x180052204`
- `0x180052650`
- `0x1800527cc`
- `0x180075e94`
- `0x180077708`
- `0x180079680`
- `0x1800b8958`
- `0x180110a94`
- `0x180121750`
- `0x18017188c`
- `0x180171ee0`
- `0x180171f68`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800521cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800521cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051b9a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051b9a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051c2d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051ce6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051dd1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051ee3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051fa0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005209e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051c2d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051ce6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051dd1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051ee3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051fa0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005209e`

## string_xrefs

- `0x180051b36`: `CByteStreamCacheReader2::BeginCacheRead`
- `0x180051be3`: `CByteStreamCacheReader2::BeginCacheRead`
- `0x180051c8a`: `CByteStreamCacheReader2::BeginCacheRead`
- `0x180051d43`: `CByteStreamCacheReader2::BeginCacheRead`
- `0x180051e2e`: `CByteStreamCacheReader2::BeginCacheRead`
- `0x180051f40`: `CByteStreamCacheReader2::BeginCacheRead`
- `0x180051ffd`: `CByteStreamCacheReader2::BeginCacheRead`
- `0x18005210f`: `CByteStreamCacheReader2::BeginCacheRead`

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
  CAsyncResult *v22; // rax
  __int64 v23; // rdx
  CAsyncResult *v24; // rbx
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rdx
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  int v37; // eax
  __int64 v38; // rdx
  wchar_t *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  __int64 v42; // rcx
  int v44; // [rsp+60h] [rbp+8h] BYREF

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
  v44 = 0;
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
      goto LABEL_105;
    v13 = 42;
    goto LABEL_104;
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
        v15 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v15 + 8) )
    {
      v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
      if ( *((_DWORD *)v17 + 499) != Request )
        CallStackContext::TraceFailure(v17, "CByteStreamCacheReader2::BeginCacheRead", 388, Request);
    }
    if ( !g_wppLevels )
      goto LABEL_105;
    v13 = 43;
    goto LABEL_104;
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
        v19 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v19 + 8) )
    {
      v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
      if ( *((_DWORD *)v21 + 499) != -1072875803 )
        CallStackContext::TraceFailure(v21, "CByteStreamCacheReader2::BeginCacheRead", 395, -1072875803);
    }
    if ( !g_wppLevels )
      goto LABEL_105;
    v13 = 44;
    goto LABEL_104;
  }
  v22 = (CAsyncResult *)operator new(0x80u);
  v24 = v22;
  if ( v22 )
  {
    CAsyncResult::CAsyncResult(v22, 0, a2, a3);
    *((_QWORD *)v24 + 13) = 0;
    *(_QWORD *)v24 = &CMP3ByteStreamPluginResult::`vftable'{for `tagMFASYNCRESULT'};
    *((_QWORD *)v24 + 8) = &CByteStreamCacheResult::`vftable'{for `CMFRefCounted'};
    *((_QWORD *)v24 + 15) = 0;
  }
  else
  {
    v24 = 0;
  }
  *((_QWORD *)this + 12) = v24;
  if ( !v24 )
  {
    v25 = (wchar_t *)CallStackTracing::s_wpInstance;
    Request = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
      CallStackTracing::s_wpInstance = v26;
      if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
      {
        v25 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v25 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v25 + 8) )
    {
      v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
      if ( *((_DWORD *)v27 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v27, "CByteStreamCacheReader2::BeginCacheRead", 402, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_105;
    v13 = 45;
    goto LABEL_104;
  }
  *((_QWORD *)v24 + 14) = *((_QWORD *)this + 10);
  *(_DWORD *)(*((_QWORD *)this + 12) + 124LL) = *((_DWORD *)this + 23);
  if ( (unsigned __int8)byte_1801BA10B >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 46, &WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids, this);
  CByteStreamCacheReader2::_TracePendingCacheRead(this);
  v28 = *((_QWORD *)this + 12);
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 8LL))(v28);
  if ( *((_DWORD *)this + 23) )
  {
    Request = CByteStreamCacheReader2::_TruncateCache(
                this,
                *((_QWORD *)this + 10),
                *((_QWORD *)this + 10) + *((unsigned int *)this + 17));
    if ( Request < 0 )
    {
      v30 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
        CallStackTracing::s_wpInstance = v31;
        if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
        {
          v30 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v30 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v30 + 8) )
      {
        v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
        if ( *((_DWORD *)v32 + 499) != Request )
          CallStackContext::TraceFailure(v32, "CByteStreamCacheReader2::BeginCacheRead", 417, Request);
      }
      if ( !g_wppLevels )
        goto LABEL_105;
      v13 = 47;
      goto LABEL_104;
    }
    if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
      CByteStreamCacheReader2::_FireWMIEvent(this);
    Request = CByteStreamCacheReader2::_FillPendingCacheRead(this, &v44);
    if ( Request < 0 )
    {
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
        if ( *((_DWORD *)v36 + 499) != Request )
          CallStackContext::TraceFailure(v36, "CByteStreamCacheReader2::BeginCacheRead", 432, Request);
      }
      if ( !g_wppLevels )
        goto LABEL_105;
      v13 = 48;
      goto LABEL_104;
    }
    v37 = CByteStreamCacheReader2::_BeginCacheEnabledRead(this);
  }
  else
  {
    v37 = CByteStreamCacheReader2::_BeginCacheDisabledRead(this);
  }
  Request = v37;
  if ( v37 == -2147483638 )
  {
    if ( (unsigned __int8)byte_1801BA10B >= 4u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 49, &WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids, this);
    Request = 0;
LABEL_89:
    if ( *((_DWORD *)this + 29) )
      goto LABEL_109;
    Request = CByteStreamCacheReader2::_SetCurrentPosition(this, *((_QWORD *)this + 10) + *((unsigned int *)this + 16));
    if ( Request >= 0 )
      goto LABEL_109;
    v39 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38);
      CallStackTracing::s_wpInstance = v40;
      if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
      {
        v39 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v39 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v39 + 8) )
    {
      v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
      if ( *((_DWORD *)v41 + 499) != Request )
        CallStackContext::TraceFailure(v41, "CByteStreamCacheReader2::BeginCacheRead", 457, Request);
    }
    if ( g_wppLevels )
    {
      v13 = 51;
      goto LABEL_104;
    }
    goto LABEL_105;
  }
  if ( v37 >= 0 )
    goto LABEL_89;
  if ( g_wppLevels )
  {
    v13 = 50;
LABEL_104:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids, this, Request);
  }
LABEL_105:
  if ( (unsigned __int8)byte_1801BA10B >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 52, &WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids, this);
  CByteStreamCacheReader2::_TracePendingCacheRead(this);
  v42 = *((_QWORD *)this + 12);
  if ( v42 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    *((_QWORD *)this + 12) = 0;
  }
LABEL_109:
  if ( v44 == 1 )
  {
    if ( (unsigned __int8)byte_1801BA10B >= 8u )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 17),
        53,
        &WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids,
        this,
        Request);
    Request = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v44);
  return (unsigned int)Request;
}

```

## disassembly

```asm
0x180051afc  mov     [rsp+arg_8], rbx
0x180051b01  mov     [rsp+arg_10], rbp
0x180051b06  push    rsi
0x180051b07  push    rdi
0x180051b08  push    r13
0x180051b0a  push    r14
0x180051b0c  push    r15
0x180051b0e  sub     rsp, 30h
0x180051b12  mov     rdi, rcx
0x180051b15  xor     r15d, r15d
0x180051b18  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051b1f  mov     rbp, r8
0x180051b22  mov     rsi, rdx
0x180051b25  test    rcx, rcx
0x180051b28  jnz     short loc_180051B36
0x180051b2a  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180051b2f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180051b36  lea     rbx, aCbytestreamcac_19; "CByteStreamCacheReader2::BeginCacheRead"
0x180051b3d  cmp     [rcx+8], r15b
0x180051b41  jz      short loc_180051B6B
0x180051b43  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180051b48  mov     ecx, [rax+7C4h]
0x180051b4e  cmp     ecx, [rax+7C8h]
0x180051b54  jnb     short loc_180051B65
0x180051b56  add     rcx, rcx
0x180051b59  mov     [rax+rcx*8], rbx
0x180051b5d  mov     dword ptr [rax+rcx*8+8], 174h
0x180051b65  inc     dword ptr [rax+7C4h]
0x180051b6b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x180051b72  lea     r13, WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids
0x180051b79  jb      short loc_180051B96
0x180051b7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180051b82  mov     edx, 29h ; ')'
0x180051b87  mov     r9, rdi
0x180051b8a  mov     r8, r13
0x180051b8d  mov     rcx, [rcx+10h]
0x180051b91  call    WPP_SF_q
0x180051b96  lea     rcx, [rdi+10h]; lpCriticalSection
0x180051b9a  call    cs:__imp_EnterCriticalSection
0x180051ba1  nop     dword ptr [rax+rax+00h]
0x180051ba6  mov     [rsp+58h+arg_0], r15d
0x180051bab  test    rsi, rsi
0x180051bae  jnz     short loc_180051C0F
0x180051bb0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051bb7  mov     ebx, 80070057h
0x180051bbc  test    rcx, rcx
0x180051bbf  jnz     short loc_180051BCD
0x180051bc1  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180051bc6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180051bcd  cmp     [rcx+8], r15b
0x180051bd1  jz      short loc_180051BF8
0x180051bd3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180051bd8  cmp     [rax+7CCh], ebx
0x180051bde  jz      short loc_180051BF8
0x180051be0  mov     r9d, ebx; int
0x180051be3  lea     rdx, aCbytestreamcac_19; "CByteStreamCacheReader2::BeginCacheRead"
0x180051bea  mov     r8d, 17Bh; int
0x180051bf0  mov     rcx, rax; this
0x180051bf3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180051bf8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180051bff  jb      loc_18005214C
0x180051c05  mov     edx, 2Ah ; '*'
0x180051c0a  jmp     loc_180052132
0x180051c0f  mov     rcx, rdi; this
0x180051c12  call    ?_ValidateReadRequest@CByteStreamCacheReader2@@IEAAJXZ; CByteStreamCacheReader2::_ValidateReadRequest(void)
0x180051c17  mov     ebx, eax
0x180051c19  test    eax, eax
0x180051c1b  jns     loc_180051CB6
0x180051c21  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051c28  test    rcx, rcx
0x180051c2b  jnz     short loc_180051C74
0x180051c2d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180051c34  nop     dword ptr [rax+rax+00h]
0x180051c39  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180051c40  mov     rcx, rax
0x180051c43  test    rax, rax
0x180051c46  jz      short loc_180051C66
0x180051c48  mov     rax, [rax]
0x180051c4b  mov     edx, 7F0h
0x180051c50  mov     rax, [rax+8]
0x180051c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051c59  test    eax, eax
0x180051c5b  jz      short loc_180051C66
0x180051c5d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051c64  jmp     short loc_180051C74
0x180051c66  lea     rcx, qword_1801B97E0; this
0x180051c6d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180051c74  cmp     [rcx+8], r15b
0x180051c78  jz      short loc_180051C9F
0x180051c7a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180051c7f  cmp     [rax+7CCh], ebx
0x180051c85  jz      short loc_180051C9F
0x180051c87  mov     r9d, ebx; int
0x180051c8a  lea     rdx, aCbytestreamcac_19; "CByteStreamCacheReader2::BeginCacheRead"
0x180051c91  mov     r8d, 184h; int
0x180051c97  mov     rcx, rax; this
0x180051c9a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180051c9f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180051ca6  jb      loc_18005214C
0x180051cac  mov     edx, 2Bh ; '+'
0x180051cb1  jmp     loc_180052132
0x180051cb6  mov     ecx, [rdi+40h]
0x180051cb9  xor     edx, edx
0x180051cbb  mov     rax, [rdi+50h]
0x180051cbf  div     rcx
0x180051cc2  test    rdx, rdx
0x180051cc5  jz      loc_180051D6F
0x180051ccb  cmp     [rdi+5Ch], r15d
0x180051ccf  jz      loc_180051D6F
0x180051cd5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051cdc  mov     ebx, 0C00D36E5h
0x180051ce1  test    rcx, rcx
0x180051ce4  jnz     short loc_180051D2D
0x180051ce6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180051ced  nop     dword ptr [rax+rax+00h]
0x180051cf2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180051cf9  mov     rcx, rax
0x180051cfc  test    rax, rax
0x180051cff  jz      short loc_180051D1F
0x180051d01  mov     rax, [rax]
0x180051d04  mov     edx, 7F0h
0x180051d09  mov     rax, [rax+8]
0x180051d0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051d12  test    eax, eax
0x180051d14  jz      short loc_180051D1F
0x180051d16  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051d1d  jmp     short loc_180051D2D
0x180051d1f  lea     rcx, qword_1801B97E0; this
0x180051d26  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180051d2d  cmp     [rcx+8], r15b
0x180051d31  jz      short loc_180051D58
0x180051d33  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180051d38  cmp     [rax+7CCh], ebx
0x180051d3e  jz      short loc_180051D58
0x180051d40  mov     r9d, ebx; int
0x180051d43  lea     rdx, aCbytestreamcac_19; "CByteStreamCacheReader2::BeginCacheRead"
0x180051d4a  mov     r8d, 18Bh; int
0x180051d50  mov     rcx, rax; this
0x180051d53  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180051d58  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180051d5f  jb      loc_18005214C
0x180051d65  mov     edx, 2Ch ; ','
0x180051d6a  jmp     loc_180052132
0x180051d6f  mov     ecx, 80h; Size
0x180051d74  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180051d79  mov     rbx, rax
0x180051d7c  test    rax, rax
0x180051d7f  jz      short loc_180051DB0
0x180051d81  mov     r9, rbp; struct IUnknown *
0x180051d84  mov     r8, rsi; struct IMFAsyncCallback *
0x180051d87  xor     edx, edx; struct IUnknown *
0x180051d89  mov     rcx, rax; this
0x180051d8c  call    ??0CAsyncResult@@QEAA@PEAUIUnknown@@PEAUIMFAsyncCallback@@0@Z; CAsyncResult::CAsyncResult(IUnknown *,IMFAsyncCallback *,IUnknown *)
0x180051d91  lea     rax, ??_7CMP3ByteStreamPluginResult@@6BtagMFASYNCRESULT@@@; const CMP3ByteStreamPluginResult::`vftable'{for `tagMFASYNCRESULT'}
0x180051d98  mov     [rbx+68h], r15
0x180051d9c  mov     [rbx], rax
0x180051d9f  lea     rax, ??_7CByteStreamCacheResult@@6BCMFRefCounted@@@; const CByteStreamCacheResult::`vftable'{for `CMFRefCounted'}
0x180051da6  mov     [rbx+40h], rax
0x180051daa  mov     [rbx+78h], r15
0x180051dae  jmp     short loc_180051DB3
0x180051db0  mov     rbx, r15
0x180051db3  mov     [rdi+60h], rbx
0x180051db7  test    rbx, rbx
0x180051dba  jnz     loc_180051E5A
0x180051dc0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051dc7  mov     ebx, 8007000Eh
0x180051dcc  test    rcx, rcx
0x180051dcf  jnz     short loc_180051E18
0x180051dd1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180051dd8  nop     dword ptr [rax+rax+00h]
0x180051ddd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180051de4  mov     rcx, rax
0x180051de7  test    rax, rax
0x180051dea  jz      short loc_180051E0A
0x180051dec  mov     rax, [rax]
0x180051def  mov     edx, 7F0h
0x180051df4  mov     rax, [rax+8]
0x180051df8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051dfd  test    eax, eax
0x180051dff  jz      short loc_180051E0A
0x180051e01  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051e08  jmp     short loc_180051E18
0x180051e0a  lea     rcx, qword_1801B97E0; this
0x180051e11  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180051e18  cmp     [rcx+8], r15b
0x180051e1c  jz      short loc_180051E43
0x180051e1e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180051e23  cmp     [rax+7CCh], ebx
0x180051e29  jz      short loc_180051E43
0x180051e2b  mov     r9d, ebx; int
0x180051e2e  lea     rdx, aCbytestreamcac_19; "CByteStreamCacheReader2::BeginCacheRead"
0x180051e35  mov     r8d, 192h; int
0x180051e3b  mov     rcx, rax; this
0x180051e3e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180051e43  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180051e4a  jb      loc_18005214C
0x180051e50  mov     edx, 2Dh ; '-'
0x180051e55  jmp     loc_180052132
0x180051e5a  mov     rax, [rdi+50h]
0x180051e5e  mov     [rbx+70h], rax
0x180051e62  mov     rcx, [rdi+60h]
0x180051e66  mov     eax, [rdi+5Ch]
0x180051e69  mov     [rcx+7Ch], eax
0x180051e6c  cmp     cs:byte_1801BA10B, 8
0x180051e73  jb      short loc_180051E93
0x180051e75  mov     rcx, cs:WPP_GLOBAL_Control
0x180051e7c  mov     edx, 2Eh ; '.'
0x180051e81  mov     r9, rdi
0x180051e84  mov     r8, r13
0x180051e87  mov     rcx, [rcx+88h]
0x180051e8e  call    WPP_SF_q
0x180051e93  mov     rcx, rdi; this
0x180051e96  call    ?_TracePendingCacheRead@CByteStreamCacheReader2@@IEAAXXZ; CByteStreamCacheReader2::_TracePendingCacheRead(void)
0x180051e9b  mov     rcx, [rdi+60h]
0x180051e9f  test    rcx, rcx
0x180051ea2  jz      short loc_180051EB0
0x180051ea4  mov     rax, [rcx]
0x180051ea7  mov     rax, [rax+8]
0x180051eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051eb0  mov     rcx, rdi; this
0x180051eb3  cmp     [rdi+5Ch], r15d
0x180051eb7  jz      loc_180052033
0x180051ebd  mov     rdx, [rdi+50h]; unsigned __int64
0x180051ec1  mov     r8d, [rdi+44h]
0x180051ec5  add     r8, rdx; unsigned __int64
0x180051ec8  call    ?_TruncateCache@CByteStreamCacheReader2@@IEAAJ_K0@Z; CByteStreamCacheReader2::_TruncateCache(unsigned __int64,unsigned __int64)
0x180051ecd  mov     ebx, eax
0x180051ecf  test    eax, eax
0x180051ed1  jns     loc_180051F6C
0x180051ed7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051ede  test    rcx, rcx
0x180051ee1  jnz     short loc_180051F2A
0x180051ee3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180051eea  nop     dword ptr [rax+rax+00h]
0x180051eef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180051ef6  mov     rcx, rax
0x180051ef9  test    rax, rax
0x180051efc  jz      short loc_180051F1C
0x180051efe  mov     rax, [rax]
0x180051f01  mov     edx, 7F0h
0x180051f06  mov     rax, [rax+8]
0x180051f0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051f0f  test    eax, eax
0x180051f11  jz      short loc_180051F1C
0x180051f13  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051f1a  jmp     short loc_180051F2A
0x180051f1c  lea     rcx, qword_1801B97E0; this
0x180051f23  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180051f2a  cmp     [rcx+8], r15b
0x180051f2e  jz      short loc_180051F55
0x180051f30  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180051f35  cmp     [rax+7CCh], ebx
0x180051f3b  jz      short loc_180051F55
0x180051f3d  mov     r9d, ebx; int
0x180051f40  lea     rdx, aCbytestreamcac_19; "CByteStreamCacheReader2::BeginCacheRead"
0x180051f47  mov     r8d, 1A1h; int
0x180051f4d  mov     rcx, rax; this
0x180051f50  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180051f55  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180051f5c  jb      loc_18005214C
0x180051f62  mov     edx, 2Fh ; '/'
0x180051f67  jmp     loc_180052132
0x180051f6c  test    cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 1
0x180051f73  jz      short loc_180051F7D
0x180051f75  mov     rcx, rdi; this
0x180051f78  call    ?_FireWMIEvent@CByteStreamCacheReader2@@IEAAXXZ; CByteStreamCacheReader2::_FireWMIEvent(void)
0x180051f7d  lea     rdx, [rsp+58h+arg_0]; int *
0x180051f82  mov     rcx, rdi; this
0x180051f85  call    ?_FillPendingCacheRead@CByteStreamCacheReader2@@IEAAJPEAH@Z; CByteStreamCacheReader2::_FillPendingCacheRead(int *)
0x180051f8a  mov     ebx, eax
0x180051f8c  test    eax, eax
0x180051f8e  jns     loc_180052029
0x180051f94  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051f9b  test    rcx, rcx
0x180051f9e  jnz     short loc_180051FE7
0x180051fa0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180051fa7  nop     dword ptr [rax+rax+00h]
0x180051fac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180051fb3  mov     rcx, rax
0x180051fb6  test    rax, rax
0x180051fb9  jz      short loc_180051FD9
0x180051fbb  mov     rax, [rax]
0x180051fbe  mov     edx, 7F0h
0x180051fc3  mov     rax, [rax+8]
0x180051fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051fcc  test    eax, eax
0x180051fce  jz      short loc_180051FD9
0x180051fd0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051fd7  jmp     short loc_180051FE7
0x180051fd9  lea     rcx, qword_1801B97E0; this
0x180051fe0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180051fe7  cmp     [rcx+8], r15b
0x180051feb  jz      short loc_180052012
0x180051fed  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180051ff2  cmp     [rax+7CCh], ebx
0x180051ff8  jz      short loc_180052012
0x180051ffa  mov     r9d, ebx; int
0x180051ffd  lea     rdx, aCbytestreamcac_19; "CByteStreamCacheReader2::BeginCacheRead"
0x180052004  mov     r8d, 1B0h; int
0x18005200a  mov     rcx, rax; this
  ... truncated ...
```
