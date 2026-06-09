# CByteStreamCacheReader2::EndCacheRead(IMFAsyncResult *,IMFMediaBuffer * *,CByteStreamCacheItem * *)

- ea: `0x18005feac`
- end: `0x180060346`
- name: `?EndCacheRead@CByteStreamCacheReader2@@QEAAJPEAUIMFAsyncResult@@PEAPEAUIMFMediaBuffer@@PEAPEAVCByteStreamCacheItem@@@Z`
- size: `1178`
- prototype: `__int64 __fastcall(CByteStreamCacheReader2 *__hidden this, struct IMFAsyncResult *, struct IMFMediaBuffer **, struct CByteStreamCacheItem **)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x18005de70`
- `0x18005fb60`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x18005feac`
- `0x180071a44`
- `0x180073b14`
- `0x180074378`
- `0x18011b1e4`
- `0x18016935c`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006031b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006031b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005ff11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005ff11`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005ff3a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060011`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800600af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060152`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005ff3a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060011`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800600af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060152`

## string_xrefs

- `0x18005fecb`: `CByteStreamCacheReader2::EndCacheRead`
- `0x18005ff91`: `CByteStreamCacheReader2::EndCacheRead`
- `0x180060068`: `CByteStreamCacheReader2::EndCacheRead`
- `0x180060106`: `CByteStreamCacheReader2::EndCacheRead`
- `0x1800601a9`: `CByteStreamCacheReader2::EndCacheRead`
- `0x180060288`: `CByteStreamCacheReader2::EndCacheRead`

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
  __int64 v10; // r9
  wchar_t *v11; // rcx
  int lpVtbl; // edi
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _QWORD *v15; // rbx
  __int64 v16; // rax
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  struct IMFAsyncResultVtbl *v25; // rcx
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  ULONG (__stdcall *Release)(IMFAsyncResult *); // rcx
  struct CByteStreamCacheItem *v30; // rcx
  CallStackTracing *v31; // rcx
  struct CallStackContext *v32; // rax
  char v34; // [rsp+70h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v34, "CByteStreamCacheReader2::EndCacheRead", 486);
  if ( g_wppLevels >= 0x20u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids, this);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( !a3 && !a4 )
  {
    v11 = (wchar_t *)CallStackTracing::s_wpInstance;
    lpVtbl = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9, v10);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v11 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
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
    v15 = (_QWORD *)((char *)this + 96);
    goto LABEL_68;
  }
  v15 = (_QWORD *)((char *)this + 96);
  v16 = *((_QWORD *)this + 12);
  if ( !v16 || !*(_DWORD *)(v16 + 120) )
  {
    v31 = CallStackTracing::s_wpInstance;
    lpVtbl = -1072875845;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v31 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v31 + 8) )
    {
      v32 = CallStackTracing::GetThreadRelativeContext(v31);
      if ( *((_DWORD *)v32 + 499) != -1072875845 )
        CallStackContext::TraceFailure(v32, "CByteStreamCacheReader2::EndCacheRead", 505, -1072875845);
    }
    if ( !g_wppLevels )
      goto LABEL_68;
    v24 = 56;
LABEL_67:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, &WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids, this, lpVtbl);
    goto LABEL_68;
  }
  if ( !a2 )
  {
    v17 = (wchar_t *)CallStackTracing::s_wpInstance;
    lpVtbl = -2147467259;
    if ( !CallStackTracing::s_wpInstance )
    {
      v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9, v10);
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
      if ( *((_DWORD *)v19 + 499) != -2147467259 )
        CallStackContext::TraceFailure(v19, "CByteStreamCacheReader2::EndCacheRead", 510, -2147467259);
    }
    if ( g_wppLevels )
    {
      v20 = 57;
LABEL_29:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v20,
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
    v21 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9, v10);
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
      if ( *((_DWORD *)v23 + 499) != lpVtbl )
        CallStackContext::TraceFailure(v23, "CByteStreamCacheReader2::EndCacheRead", 512, lpVtbl);
    }
    if ( !g_wppLevels )
      goto LABEL_68;
    v24 = 58;
    goto LABEL_67;
  }
  v25 = a2[13].lpVtbl;
  if ( v25 )
  {
    if ( (unsigned __int8)byte_1801B110B >= 8u )
      WPP_SF_qqId(*((_QWORD *)WPP_GLOBAL_Control + 17), v8, v9, this, v25->Release, v25->GetState, v25->GetStatus);
    if ( a3 )
    {
      Release = a2[13].lpVtbl->Release;
      *a3 = (struct IMFMediaBuffer *)Release;
      if ( Release )
        (*(void (__fastcall **)(ULONG (__stdcall *)(IMFAsyncResult *)))(*(_QWORD *)Release + 8LL))(Release);
    }
    if ( a4 )
    {
      v30 = (struct CByteStreamCacheItem *)a2[13].lpVtbl;
      *a4 = v30;
      if ( v30 )
        (*(void (__fastcall **)(struct CByteStreamCacheItem *))(*(_QWORD *)v30 + 8LL))(v30);
    }
  }
  else
  {
    v26 = (wchar_t *)CallStackTracing::s_wpInstance;
    lpVtbl = -2147467259;
    if ( !CallStackTracing::s_wpInstance )
    {
      v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9, v10);
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
      if ( *((_DWORD *)v28 + 499) != -2147467259 )
        CallStackContext::TraceFailure(v28, "CByteStreamCacheReader2::EndCacheRead", 514, -2147467259);
    }
    if ( g_wppLevels )
    {
      v20 = 59;
      goto LABEL_29;
    }
  }
LABEL_68:
  if ( (unsigned __int8)byte_1801B110B >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 61, &WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids, this);
  CByteStreamCacheReader2::_TracePendingCacheRead(this);
  if ( *v15 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v15 + 16LL))(*v15);
    *v15 = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v34);
  return (unsigned int)lpVtbl;
}

```

## disassembly

```asm
0x18005feac  mov     [rsp+arg_8], rbx
0x18005feb1  mov     [rsp+arg_10], rbp
0x18005feb6  push    rsi
0x18005feb7  push    rdi
0x18005feb8  push    r12
0x18005feba  push    r14
0x18005febc  push    r15
0x18005febe  sub     rsp, 40h
0x18005fec2  mov     r14, r8
0x18005fec5  mov     rsi, rdx
0x18005fec8  mov     rbp, rcx
0x18005fecb  lea     rdx, aCbytestreamcac_22; "CByteStreamCacheReader2::EndCacheRead"
0x18005fed2  mov     r8d, 1E6h; int
0x18005fed8  lea     rcx, [rsp+68h+arg_0]; this
0x18005fedd  mov     r15, r9
0x18005fee0  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005fee5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x18005feec  jb      short loc_18005FF0D
0x18005feee  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fef5  lea     r8, WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids
0x18005fefc  mov     edx, 36h ; '6'
0x18005ff01  mov     r9, rbp
0x18005ff04  mov     rcx, [rcx+10h]
0x18005ff08  call    WPP_SF_q
0x18005ff0d  lea     rcx, [rbp+10h]; lpCriticalSection
0x18005ff11  call    cs:__imp_EnterCriticalSection
0x18005ff17  test    r14, r14
0x18005ff1a  jnz     loc_18005FFDB
0x18005ff20  test    r15, r15
0x18005ff23  jnz     loc_18005FFDB
0x18005ff29  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ff30  mov     edi, 80070057h
0x18005ff35  test    rcx, rcx
0x18005ff38  jnz     short loc_18005FF7B
0x18005ff3a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005ff40  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ff47  mov     rcx, rax
0x18005ff4a  test    rax, rax
0x18005ff4d  jz      short loc_18005FF6D
0x18005ff4f  mov     rax, [rax]
0x18005ff52  mov     edx, 7F0h
0x18005ff57  mov     rax, [rax+8]
0x18005ff5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ff60  test    eax, eax
0x18005ff62  jz      short loc_18005FF6D
0x18005ff64  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ff6b  jmp     short loc_18005FF7B
0x18005ff6d  lea     rcx, qword_1801B07E0; this
0x18005ff74  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ff7b  cmp     byte ptr [rcx+8], 0
0x18005ff7f  jz      short loc_18005FFA6
0x18005ff81  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005ff86  cmp     [rax+7CCh], edi
0x18005ff8c  jz      short loc_18005FFA6
0x18005ff8e  mov     r9d, edi; int
0x18005ff91  lea     rdx, aCbytestreamcac_22; "CByteStreamCacheReader2::EndCacheRead"
0x18005ff98  mov     r8d, 1F1h; int
0x18005ff9e  mov     rcx, rax; this
0x18005ffa1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005ffa6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005ffad  jb      short loc_18005FFD2
0x18005ffaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ffb6  lea     r8, WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids
0x18005ffbd  mov     edx, 37h ; '7'
0x18005ffc2  mov     dword ptr [rsp+68h+var_48], edi
0x18005ffc6  mov     r9, rbp
0x18005ffc9  mov     rcx, [rcx+10h]
0x18005ffcd  call    WPP_SF_qD
0x18005ffd2  lea     rbx, [rbp+60h]
0x18005ffd6  jmp     loc_1800602C9
0x18005ffdb  lea     rbx, [rbp+60h]
0x18005ffdf  mov     rax, [rbx]
0x18005ffe2  test    rax, rax
0x18005ffe5  jz      loc_180060255
0x18005ffeb  cmp     dword ptr [rax+78h], 0
0x18005ffef  jz      loc_180060255
0x18005fff5  test    rsi, rsi
0x18005fff8  jnz     loc_180060098
0x18005fffe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060005  mov     esi, 80004005h
0x18006000a  mov     edi, esi
0x18006000c  test    rcx, rcx
0x18006000f  jnz     short loc_180060052
0x180060011  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180060017  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006001e  mov     rcx, rax
0x180060021  test    rax, rax
0x180060024  jz      short loc_180060044
0x180060026  mov     rax, [rax]
0x180060029  mov     edx, 7F0h
0x18006002e  mov     rax, [rax+8]
0x180060032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060037  test    eax, eax
0x180060039  jz      short loc_180060044
0x18006003b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060042  jmp     short loc_180060052
0x180060044  lea     rcx, qword_1801B07E0; this
0x18006004b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180060052  cmp     byte ptr [rcx+8], 0
0x180060056  jz      short loc_18006007D
0x180060058  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006005d  cmp     [rax+7CCh], esi
0x180060063  jz      short loc_18006007D
0x180060065  mov     r9d, esi; int
0x180060068  lea     rdx, aCbytestreamcac_22; "CByteStreamCacheReader2::EndCacheRead"
0x18006006f  mov     r8d, 1FEh; int
0x180060075  mov     rcx, rax; this
0x180060078  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006007d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180060084  jb      loc_1800602C9
0x18006008a  mov     edx, 39h ; '9'
0x18006008f  mov     dword ptr [rsp+68h+var_48], esi
0x180060093  jmp     loc_1800602AF
0x180060098  mov     edi, [rsi+30h]
0x18006009b  test    edi, edi
0x18006009d  jns     loc_180060132
0x1800600a3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800600aa  test    rcx, rcx
0x1800600ad  jnz     short loc_1800600F0
0x1800600af  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800600b5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800600bc  mov     rcx, rax
0x1800600bf  test    rax, rax
0x1800600c2  jz      short loc_1800600E2
0x1800600c4  mov     rax, [rax]
0x1800600c7  mov     edx, 7F0h
0x1800600cc  mov     rax, [rax+8]
0x1800600d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800600d5  test    eax, eax
0x1800600d7  jz      short loc_1800600E2
0x1800600d9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800600e0  jmp     short loc_1800600F0
0x1800600e2  lea     rcx, qword_1801B07E0; this
0x1800600e9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800600f0  cmp     byte ptr [rcx+8], 0
0x1800600f4  jz      short loc_18006011B
0x1800600f6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800600fb  cmp     [rax+7CCh], edi
0x180060101  jz      short loc_18006011B
0x180060103  mov     r9d, edi; int
0x180060106  lea     rdx, aCbytestreamcac_22; "CByteStreamCacheReader2::EndCacheRead"
0x18006010d  mov     r8d, 200h; int
0x180060113  mov     rcx, rax; this
0x180060116  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006011b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180060122  jb      loc_1800602C9
0x180060128  mov     edx, 3Ah ; ':'
0x18006012d  jmp     loc_1800602AB
0x180060132  mov     rcx, [rsi+68h]
0x180060136  test    rcx, rcx
0x180060139  jnz     loc_1800601D5
0x18006013f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060146  mov     esi, 80004005h
0x18006014b  mov     edi, esi
0x18006014d  test    rcx, rcx
0x180060150  jnz     short loc_180060193
0x180060152  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180060158  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006015f  mov     rcx, rax
0x180060162  test    rax, rax
0x180060165  jz      short loc_180060185
0x180060167  mov     rax, [rax]
0x18006016a  mov     edx, 7F0h
0x18006016f  mov     rax, [rax+8]
0x180060173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060178  test    eax, eax
0x18006017a  jz      short loc_180060185
0x18006017c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060183  jmp     short loc_180060193
0x180060185  lea     rcx, qword_1801B07E0; this
0x18006018c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180060193  cmp     byte ptr [rcx+8], 0
0x180060197  jz      short loc_1800601BE
0x180060199  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006019e  cmp     [rax+7CCh], esi
0x1800601a4  jz      short loc_1800601BE
0x1800601a6  mov     r9d, esi; int
0x1800601a9  lea     rdx, aCbytestreamcac_22; "CByteStreamCacheReader2::EndCacheRead"
0x1800601b0  mov     r8d, 202h; int
0x1800601b6  mov     rcx, rax; this
0x1800601b9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800601be  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800601c5  jb      loc_1800602C9
0x1800601cb  mov     edx, 3Bh ; ';'
0x1800601d0  jmp     loc_18006008F
0x1800601d5  cmp     cs:byte_1801B110B, 8
0x1800601dc  jb      short loc_18006020D
0x1800601de  mov     eax, [rcx+20h]
0x1800601e1  mov     r9, rbp
0x1800601e4  mov     [rsp+68h+var_38], eax
0x1800601e8  mov     rax, [rcx+18h]
0x1800601ec  mov     [rsp+68h+var_40], rax
0x1800601f1  mov     rax, [rcx+10h]
0x1800601f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800601fc  mov     [rsp+68h+var_48], rax
0x180060201  mov     rcx, [rcx+88h]
0x180060208  call    WPP_SF_qqId
0x18006020d  test    r14, r14
0x180060210  jz      short loc_18006022E
0x180060212  mov     rax, [rsi+68h]
0x180060216  mov     rcx, [rax+10h]
0x18006021a  mov     [r14], rcx
0x18006021d  test    rcx, rcx
0x180060220  jz      short loc_18006022E
0x180060222  mov     rax, [rcx]
0x180060225  mov     rax, [rax+8]
0x180060229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006022e  test    r15, r15
0x180060231  jz      loc_1800602C9
0x180060237  mov     rcx, [rsi+68h]
0x18006023b  mov     [r15], rcx
0x18006023e  test    rcx, rcx
0x180060241  jz      loc_1800602C9
0x180060247  mov     rax, [rcx]
0x18006024a  mov     rax, [rax+8]
0x18006024e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060253  jmp     short loc_1800602C9
0x180060255  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006025c  mov     edi, 0C00D36BBh
0x180060261  test    rcx, rcx
0x180060264  jnz     short loc_180060272
0x180060266  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18006026b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180060272  cmp     byte ptr [rcx+8], 0
0x180060276  jz      short loc_18006029D
0x180060278  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006027d  cmp     [rax+7CCh], edi
0x180060283  jz      short loc_18006029D
0x180060285  mov     r9d, edi; int
0x180060288  lea     rdx, aCbytestreamcac_22; "CByteStreamCacheReader2::EndCacheRead"
0x18006028f  mov     r8d, 1F9h; int
0x180060295  mov     rcx, rax; this
0x180060298  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006029d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800602a4  jb      short loc_1800602C9
0x1800602a6  mov     edx, 38h ; '8'
0x1800602ab  mov     dword ptr [rsp+68h+var_48], edi
0x1800602af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800602b6  lea     r8, WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids
0x1800602bd  mov     r9, rbp
0x1800602c0  mov     rcx, [rcx+10h]
0x1800602c4  call    WPP_SF_qD
0x1800602c9  cmp     cs:byte_1801B110B, 8
0x1800602d0  jb      short loc_1800602F4
0x1800602d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800602d9  lea     r8, WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids
0x1800602e0  mov     edx, 3Dh ; '='
0x1800602e5  mov     r9, rbp
0x1800602e8  mov     rcx, [rcx+88h]
0x1800602ef  call    WPP_SF_q
0x1800602f4  mov     rcx, rbp; this
0x1800602f7  call    ?_TracePendingCacheRead@CByteStreamCacheReader2@@IEAAXXZ; CByteStreamCacheReader2::_TracePendingCacheRead(void)
0x1800602fc  mov     rcx, [rbx]
0x1800602ff  test    rcx, rcx
0x180060302  jz      short loc_180060317
0x180060304  mov     rdx, [rcx]
0x180060307  mov     rax, [rdx+10h]
0x18006030b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060310  mov     qword ptr [rbx], 0
0x180060317  lea     rcx, [rbp+10h]; lpCriticalSection
0x18006031b  call    cs:__imp_LeaveCriticalSection
0x180060321  lea     rcx, [rsp+68h+arg_0]; this
0x180060326  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18006032b  lea     r11, [rsp+68h+var_28]
0x180060330  mov     eax, edi
0x180060332  mov     rbx, [r11+38h]
0x180060336  mov     rbp, [r11+40h]
0x18006033a  mov     rsp, r11
0x18006033d  pop     r15
0x18006033f  pop     r14
0x180060341  pop     r12
0x180060343  pop     rdi
0x180060344  pop     rsi
0x180060345  retn
```
