# CByteStreamCacheReader2::EndCacheRead(IMFAsyncResult *,IMFMediaBuffer * *,CByteStreamCacheItem * *)

- ea: `0x180039ca8`
- end: `0x18003a167`
- name: `?EndCacheRead@CByteStreamCacheReader2@@QEAAJPEAUIMFAsyncResult@@PEAPEAUIMFMediaBuffer@@PEAPEAVCByteStreamCacheItem@@@Z`
- size: `1215`
- prototype: `__int64 __fastcall(CByteStreamCacheReader2 *__hidden this, struct IMFAsyncResult *, struct IMFMediaBuffer **, struct CByteStreamCacheItem **)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x180037dec`
- `0x18003a170`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180039ca8`
- `0x180075e94`
- `0x180077708`
- `0x180079680`
- `0x180121750`
- `0x180172320`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a135`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a135`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039d0d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039d0d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039d3c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039e19`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039ebd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039f66`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039d3c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039e19`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039ebd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039f66`

## string_xrefs

- `0x180039cc7`: `CByteStreamCacheReader2::EndCacheRead`
- `0x180039d99`: `CByteStreamCacheReader2::EndCacheRead`
- `0x180039e76`: `CByteStreamCacheReader2::EndCacheRead`
- `0x180039f1a`: `CByteStreamCacheReader2::EndCacheRead`
- `0x180039fc3`: `CByteStreamCacheReader2::EndCacheRead`
- `0x18003a0a2`: `CByteStreamCacheReader2::EndCacheRead`

## pseudocode

```c
__int64 __fastcall CByteStreamCacheReader2::EndCacheRead(
        CByteStreamCacheReader2 *this,
        struct IMFAsyncResult *a2,
        struct IMFMediaBuffer **a3,
        struct CByteStreamCacheItem **a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  wchar_t *v10; // rcx
  int lpVtbl; // edi
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _QWORD *v14; // rbx
  __int64 v15; // rax
  wchar_t *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  struct IMFAsyncResultVtbl *v24; // rcx
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  ULONG (__stdcall *Release)(IMFAsyncResult *); // rcx
  struct CByteStreamCacheItem *v29; // rcx
  CallStackTracing *v30; // rcx
  struct CallStackContext *v31; // rax
  char v33; // [rsp+70h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v33, "CByteStreamCacheReader2::EndCacheRead", 486);
  if ( g_wppLevels >= 0x20u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids, this);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( !a3 && !a4 )
  {
    v10 = (wchar_t *)CallStackTracing::s_wpInstance;
    lpVtbl = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v10 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CByteStreamCacheReader2::EndCacheRead", 497, -2147024809);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        55,
        &WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids,
        this,
        -2147024809);
    v14 = (_QWORD *)((char *)this + 96);
    goto LABEL_68;
  }
  v14 = (_QWORD *)((char *)this + 96);
  v15 = *((_QWORD *)this + 12);
  if ( !v15 || !*(_DWORD *)(v15 + 120) )
  {
    v30 = CallStackTracing::s_wpInstance;
    lpVtbl = -1072875845;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v30 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v30 + 8) )
    {
      v31 = CallStackTracing::GetThreadRelativeContext(v30);
      if ( *((_DWORD *)v31 + 499) != -1072875845 )
        CallStackContext::TraceFailure(v31, "CByteStreamCacheReader2::EndCacheRead", 505, -1072875845);
    }
    if ( !g_wppLevels )
      goto LABEL_68;
    v23 = 56;
LABEL_67:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, &WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids, this, lpVtbl);
    goto LABEL_68;
  }
  if ( !a2 )
  {
    v16 = (wchar_t *)CallStackTracing::s_wpInstance;
    lpVtbl = -2147467259;
    if ( !CallStackTracing::s_wpInstance )
    {
      v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
      CallStackTracing::s_wpInstance = v17;
      if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
      {
        v16 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v16 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v16 + 8) )
    {
      v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
      if ( *((_DWORD *)v18 + 499) != -2147467259 )
        CallStackContext::TraceFailure(v18, "CByteStreamCacheReader2::EndCacheRead", 510, -2147467259);
    }
    if ( g_wppLevels )
    {
      v19 = 57;
LABEL_29:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v19,
        &WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids,
        this,
        -2147467259);
      goto LABEL_68;
    }
    goto LABEL_68;
  }
  lpVtbl = (int)a2[6].lpVtbl;
  if ( lpVtbl < 0 )
  {
    v20 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
      CallStackTracing::s_wpInstance = v21;
      if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
      {
        v20 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v20 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v20 + 8) )
    {
      v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
      if ( *((_DWORD *)v22 + 499) != lpVtbl )
        CallStackContext::TraceFailure(v22, "CByteStreamCacheReader2::EndCacheRead", 512, lpVtbl);
    }
    if ( !g_wppLevels )
      goto LABEL_68;
    v23 = 58;
    goto LABEL_67;
  }
  v24 = a2[13].lpVtbl;
  if ( v24 )
  {
    if ( (unsigned __int8)byte_1801BA10B >= 8u )
      WPP_SF_qqId(*((_QWORD *)WPP_GLOBAL_Control + 17), v8, v9, this, v24->Release, v24->GetState, v24->GetStatus);
    if ( a3 )
    {
      Release = a2[13].lpVtbl->Release;
      *a3 = (struct IMFMediaBuffer *)Release;
      if ( Release )
        (*(void (__fastcall **)(ULONG (__stdcall *)(IMFAsyncResult *)))(*(_QWORD *)Release + 8LL))(Release);
    }
    if ( a4 )
    {
      v29 = (struct CByteStreamCacheItem *)a2[13].lpVtbl;
      *a4 = v29;
      if ( v29 )
        (*(void (__fastcall **)(struct CByteStreamCacheItem *))(*(_QWORD *)v29 + 8LL))(v29);
    }
  }
  else
  {
    v25 = (wchar_t *)CallStackTracing::s_wpInstance;
    lpVtbl = -2147467259;
    if ( !CallStackTracing::s_wpInstance )
    {
      v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
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
      if ( *((_DWORD *)v27 + 499) != -2147467259 )
        CallStackContext::TraceFailure(v27, "CByteStreamCacheReader2::EndCacheRead", 514, -2147467259);
    }
    if ( g_wppLevels )
    {
      v19 = 59;
      goto LABEL_29;
    }
  }
LABEL_68:
  if ( (unsigned __int8)byte_1801BA10B >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 61, &WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids, this);
  CByteStreamCacheReader2::_TracePendingCacheRead(this);
  if ( *v14 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 16LL))(*v14);
    *v14 = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v33);
  return (unsigned int)lpVtbl;
}

```

## disassembly

```asm
0x180039ca8  mov     [rsp+arg_8], rbx
0x180039cad  mov     [rsp+arg_10], rbp
0x180039cb2  push    rsi
0x180039cb3  push    rdi
0x180039cb4  push    r12
0x180039cb6  push    r14
0x180039cb8  push    r15
0x180039cba  sub     rsp, 40h
0x180039cbe  mov     r14, r8
0x180039cc1  mov     rsi, rdx
0x180039cc4  mov     rbp, rcx
0x180039cc7  lea     rdx, aCbytestreamcac_22; "CByteStreamCacheReader2::EndCacheRead"
0x180039cce  mov     r8d, 1E6h; int
0x180039cd4  lea     rcx, [rsp+68h+arg_0]; this
0x180039cd9  mov     r15, r9
0x180039cdc  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180039ce1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x180039ce8  jb      short loc_180039D09
0x180039cea  mov     rcx, cs:WPP_GLOBAL_Control
0x180039cf1  lea     r8, WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids
0x180039cf8  mov     edx, 36h ; '6'
0x180039cfd  mov     r9, rbp
0x180039d00  mov     rcx, [rcx+10h]
0x180039d04  call    WPP_SF_q
0x180039d09  lea     rcx, [rbp+10h]; lpCriticalSection
0x180039d0d  call    cs:__imp_EnterCriticalSection
0x180039d14  nop     dword ptr [rax+rax+00h]
0x180039d19  test    r14, r14
0x180039d1c  jnz     loc_180039DE3
0x180039d22  test    r15, r15
0x180039d25  jnz     loc_180039DE3
0x180039d2b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039d32  mov     edi, 80070057h
0x180039d37  test    rcx, rcx
0x180039d3a  jnz     short loc_180039D83
0x180039d3c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180039d43  nop     dword ptr [rax+rax+00h]
0x180039d48  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180039d4f  mov     rcx, rax
0x180039d52  test    rax, rax
0x180039d55  jz      short loc_180039D75
0x180039d57  mov     rax, [rax]
0x180039d5a  mov     edx, 7F0h
0x180039d5f  mov     rax, [rax+8]
0x180039d63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039d68  test    eax, eax
0x180039d6a  jz      short loc_180039D75
0x180039d6c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039d73  jmp     short loc_180039D83
0x180039d75  lea     rcx, qword_1801B97E0; this
0x180039d7c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180039d83  cmp     byte ptr [rcx+8], 0
0x180039d87  jz      short loc_180039DAE
0x180039d89  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180039d8e  cmp     [rax+7CCh], edi
0x180039d94  jz      short loc_180039DAE
0x180039d96  mov     r9d, edi; int
0x180039d99  lea     rdx, aCbytestreamcac_22; "CByteStreamCacheReader2::EndCacheRead"
0x180039da0  mov     r8d, 1F1h; int
0x180039da6  mov     rcx, rax; this
0x180039da9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180039dae  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180039db5  jb      short loc_180039DDA
0x180039db7  mov     rcx, cs:WPP_GLOBAL_Control
0x180039dbe  lea     r8, WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids
0x180039dc5  mov     edx, 37h ; '7'
0x180039dca  mov     dword ptr [rsp+68h+var_48], edi
0x180039dce  mov     r9, rbp
0x180039dd1  mov     rcx, [rcx+10h]
0x180039dd5  call    WPP_SF_qD
0x180039dda  lea     rbx, [rbp+60h]
0x180039dde  jmp     loc_18003A0E3
0x180039de3  lea     rbx, [rbp+60h]
0x180039de7  mov     rax, [rbx]
0x180039dea  test    rax, rax
0x180039ded  jz      loc_18003A06F
0x180039df3  cmp     dword ptr [rax+78h], 0
0x180039df7  jz      loc_18003A06F
0x180039dfd  test    rsi, rsi
0x180039e00  jnz     loc_180039EA6
0x180039e06  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039e0d  mov     esi, 80004005h
0x180039e12  mov     edi, esi
0x180039e14  test    rcx, rcx
0x180039e17  jnz     short loc_180039E60
0x180039e19  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180039e20  nop     dword ptr [rax+rax+00h]
0x180039e25  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180039e2c  mov     rcx, rax
0x180039e2f  test    rax, rax
0x180039e32  jz      short loc_180039E52
0x180039e34  mov     rax, [rax]
0x180039e37  mov     edx, 7F0h
0x180039e3c  mov     rax, [rax+8]
0x180039e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e45  test    eax, eax
0x180039e47  jz      short loc_180039E52
0x180039e49  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039e50  jmp     short loc_180039E60
0x180039e52  lea     rcx, qword_1801B97E0; this
0x180039e59  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180039e60  cmp     byte ptr [rcx+8], 0
0x180039e64  jz      short loc_180039E8B
0x180039e66  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180039e6b  cmp     [rax+7CCh], esi
0x180039e71  jz      short loc_180039E8B
0x180039e73  mov     r9d, esi; int
0x180039e76  lea     rdx, aCbytestreamcac_22; "CByteStreamCacheReader2::EndCacheRead"
0x180039e7d  mov     r8d, 1FEh; int
0x180039e83  mov     rcx, rax; this
0x180039e86  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180039e8b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180039e92  jb      loc_18003A0E3
0x180039e98  mov     edx, 39h ; '9'
0x180039e9d  mov     dword ptr [rsp+68h+var_48], esi
0x180039ea1  jmp     loc_18003A0C9
0x180039ea6  mov     edi, [rsi+30h]
0x180039ea9  test    edi, edi
0x180039eab  jns     loc_180039F46
0x180039eb1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039eb8  test    rcx, rcx
0x180039ebb  jnz     short loc_180039F04
0x180039ebd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180039ec4  nop     dword ptr [rax+rax+00h]
0x180039ec9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180039ed0  mov     rcx, rax
0x180039ed3  test    rax, rax
0x180039ed6  jz      short loc_180039EF6
0x180039ed8  mov     rax, [rax]
0x180039edb  mov     edx, 7F0h
0x180039ee0  mov     rax, [rax+8]
0x180039ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039ee9  test    eax, eax
0x180039eeb  jz      short loc_180039EF6
0x180039eed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039ef4  jmp     short loc_180039F04
0x180039ef6  lea     rcx, qword_1801B97E0; this
0x180039efd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180039f04  cmp     byte ptr [rcx+8], 0
0x180039f08  jz      short loc_180039F2F
0x180039f0a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180039f0f  cmp     [rax+7CCh], edi
0x180039f15  jz      short loc_180039F2F
0x180039f17  mov     r9d, edi; int
0x180039f1a  lea     rdx, aCbytestreamcac_22; "CByteStreamCacheReader2::EndCacheRead"
0x180039f21  mov     r8d, 200h; int
0x180039f27  mov     rcx, rax; this
0x180039f2a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180039f2f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180039f36  jb      loc_18003A0E3
0x180039f3c  mov     edx, 3Ah ; ':'
0x180039f41  jmp     loc_18003A0C5
0x180039f46  mov     rcx, [rsi+68h]
0x180039f4a  test    rcx, rcx
0x180039f4d  jnz     loc_180039FEF
0x180039f53  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039f5a  mov     esi, 80004005h
0x180039f5f  mov     edi, esi
0x180039f61  test    rcx, rcx
0x180039f64  jnz     short loc_180039FAD
0x180039f66  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180039f6d  nop     dword ptr [rax+rax+00h]
0x180039f72  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180039f79  mov     rcx, rax
0x180039f7c  test    rax, rax
0x180039f7f  jz      short loc_180039F9F
0x180039f81  mov     rax, [rax]
0x180039f84  mov     edx, 7F0h
0x180039f89  mov     rax, [rax+8]
0x180039f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039f92  test    eax, eax
0x180039f94  jz      short loc_180039F9F
0x180039f96  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039f9d  jmp     short loc_180039FAD
0x180039f9f  lea     rcx, qword_1801B97E0; this
0x180039fa6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180039fad  cmp     byte ptr [rcx+8], 0
0x180039fb1  jz      short loc_180039FD8
0x180039fb3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180039fb8  cmp     [rax+7CCh], esi
0x180039fbe  jz      short loc_180039FD8
0x180039fc0  mov     r9d, esi; int
0x180039fc3  lea     rdx, aCbytestreamcac_22; "CByteStreamCacheReader2::EndCacheRead"
0x180039fca  mov     r8d, 202h; int
0x180039fd0  mov     rcx, rax; this
0x180039fd3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180039fd8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180039fdf  jb      loc_18003A0E3
0x180039fe5  mov     edx, 3Bh ; ';'
0x180039fea  jmp     loc_180039E9D
0x180039fef  cmp     cs:byte_1801BA10B, 8
0x180039ff6  jb      short loc_18003A027
0x180039ff8  mov     eax, [rcx+20h]
0x180039ffb  mov     r9, rbp
0x180039ffe  mov     [rsp+68h+var_38], eax
0x18003a002  mov     rax, [rcx+18h]
0x18003a006  mov     [rsp+68h+var_40], rax
0x18003a00b  mov     rax, [rcx+10h]
0x18003a00f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a016  mov     [rsp+68h+var_48], rax
0x18003a01b  mov     rcx, [rcx+88h]
0x18003a022  call    WPP_SF_qqId
0x18003a027  test    r14, r14
0x18003a02a  jz      short loc_18003A048
0x18003a02c  mov     rax, [rsi+68h]
0x18003a030  mov     rcx, [rax+10h]
0x18003a034  mov     [r14], rcx
0x18003a037  test    rcx, rcx
0x18003a03a  jz      short loc_18003A048
0x18003a03c  mov     rax, [rcx]
0x18003a03f  mov     rax, [rax+8]
0x18003a043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a048  test    r15, r15
0x18003a04b  jz      loc_18003A0E3
0x18003a051  mov     rcx, [rsi+68h]
0x18003a055  mov     [r15], rcx
0x18003a058  test    rcx, rcx
0x18003a05b  jz      loc_18003A0E3
0x18003a061  mov     rax, [rcx]
0x18003a064  mov     rax, [rax+8]
0x18003a068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a06d  jmp     short loc_18003A0E3
0x18003a06f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003a076  mov     edi, 0C00D36BBh
0x18003a07b  test    rcx, rcx
0x18003a07e  jnz     short loc_18003A08C
0x18003a080  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18003a085  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003a08c  cmp     byte ptr [rcx+8], 0
0x18003a090  jz      short loc_18003A0B7
0x18003a092  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003a097  cmp     [rax+7CCh], edi
0x18003a09d  jz      short loc_18003A0B7
0x18003a09f  mov     r9d, edi; int
0x18003a0a2  lea     rdx, aCbytestreamcac_22; "CByteStreamCacheReader2::EndCacheRead"
0x18003a0a9  mov     r8d, 1F9h; int
0x18003a0af  mov     rcx, rax; this
0x18003a0b2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003a0b7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003a0be  jb      short loc_18003A0E3
0x18003a0c0  mov     edx, 38h ; '8'
0x18003a0c5  mov     dword ptr [rsp+68h+var_48], edi
0x18003a0c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a0d0  lea     r8, WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids
0x18003a0d7  mov     r9, rbp
0x18003a0da  mov     rcx, [rcx+10h]
0x18003a0de  call    WPP_SF_qD
0x18003a0e3  cmp     cs:byte_1801BA10B, 8
0x18003a0ea  jb      short loc_18003A10E
0x18003a0ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a0f3  lea     r8, WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids
0x18003a0fa  mov     edx, 3Dh ; '='
0x18003a0ff  mov     r9, rbp
0x18003a102  mov     rcx, [rcx+88h]
0x18003a109  call    WPP_SF_q
0x18003a10e  mov     rcx, rbp; this
0x18003a111  call    ?_TracePendingCacheRead@CByteStreamCacheReader2@@IEAAXXZ; CByteStreamCacheReader2::_TracePendingCacheRead(void)
0x18003a116  mov     rcx, [rbx]
0x18003a119  test    rcx, rcx
0x18003a11c  jz      short loc_18003A131
0x18003a11e  mov     rdx, [rcx]
0x18003a121  mov     rax, [rdx+10h]
0x18003a125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a12a  mov     qword ptr [rbx], 0
0x18003a131  lea     rcx, [rbp+10h]; lpCriticalSection
0x18003a135  call    cs:__imp_LeaveCriticalSection
0x18003a13c  nop     dword ptr [rax+rax+00h]
0x18003a141  lea     rcx, [rsp+68h+arg_0]; this
0x18003a146  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003a14b  lea     r11, [rsp+68h+var_28]
0x18003a150  mov     eax, edi
0x18003a152  mov     rbx, [r11+38h]
0x18003a156  mov     rbp, [r11+40h]
0x18003a15a  mov     rsp, r11
0x18003a15d  pop     r15
0x18003a15f  pop     r14
0x18003a161  pop     r12
0x18003a163  pop     rdi
0x18003a164  pop     rsi
0x18003a165  retn
```
