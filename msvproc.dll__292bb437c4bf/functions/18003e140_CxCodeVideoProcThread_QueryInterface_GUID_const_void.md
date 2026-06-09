# CxCodeVideoProcThread::QueryInterface(_GUID const &,void * *)

- ea: `0x18003e140`
- end: `0x18003e305`
- name: `?QueryInterface@CxCodeVideoProcThread@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `453`
- prototype: `int(CxCodeVideoProcThread *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x18003e140`
- `0x18003e30c`
- `0x1800cfec0`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003e18b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003e251`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003e18b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003e251`

## string_xrefs

- `0x18003e158`: `CxCodeVideoProcThread::QueryInterface`
- `0x18003e1e6`: `CxCodeVideoProcThread::QueryInterface`
- `0x18003e2a8`: `CxCodeVideoProcThread::QueryInterface`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcThread::QueryInterface(
        CxCodeVideoProcThread *this,
        const struct _GUID *a2,
        void **a3)
{
  int v6; // eax
  __int64 *v7; // rcx
  int v8; // ebx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v16; // [rsp+50h] [rbp+18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v16, "CxCodeVideoProcThread::QueryInterface", 126);
  if ( a3 )
  {
    *a3 = 0;
    if ( !memcmp_0(a2, &IID_IUnknown, 0x10u) )
    {
      v8 = 0;
      *a3 = this;
      _InterlockedIncrement((volatile signed __int32 *)this + 13);
    }
    else
    {
      v12 = (__int64 *)CallStackTracing::s_wpInstance;
      v8 = -2147467262;
      if ( !CallStackTracing::s_wpInstance )
      {
        v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v13;
        if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
        {
          v12 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467262 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CxCodeVideoProcThread::QueryInterface",
            136,
            -2147467262);
      }
      if ( g_wppLevels )
      {
        v11 = 13;
        goto LABEL_25;
      }
    }
  }
  else
  {
    v6 = XvpOriginateError<38>();
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    v8 = v6;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( v8 < 0 && *((_DWORD *)v10 + 499) != v8 )
        CallStackContext::TraceFailure(v10, "CxCodeVideoProcThread::QueryInterface", 126, v8);
    }
    if ( g_wppLevels )
    {
      v11 = 12;
LABEL_25:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_cd0276237ea237e1200ead55a1fb02c7_Traceguids, this, v8);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v16);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003e140  mov     [rsp+arg_0], rbx
0x18003e145  mov     [rsp+arg_8], rsi
0x18003e14a  push    rdi
0x18003e14b  sub     rsp, 30h
0x18003e14f  mov     rsi, r8
0x18003e152  mov     rbx, rdx
0x18003e155  mov     rdi, rcx
0x18003e158  lea     rdx, aCxcodevideopro_44; "CxCodeVideoProcThread::QueryInterface"
0x18003e15f  mov     r8d, 7Eh ; '~'; int
0x18003e165  lea     rcx, [rsp+38h+arg_10]; this
0x18003e16a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003e16f  test    rsi, rsi
0x18003e172  jnz     loc_18003E212
0x18003e178  call    ??$XvpOriginateError@$0CG@@@YAJQEADJAEAY0CG@$$CBG@Z; XvpOriginateError<38>(char * const,long,ushort const (&)[38])
0x18003e17d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e184  mov     ebx, eax
0x18003e186  test    rcx, rcx
0x18003e189  jnz     short loc_18003E1CC
0x18003e18b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003e191  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e198  mov     rcx, rax
0x18003e19b  test    rax, rax
0x18003e19e  jz      short loc_18003E1BE
0x18003e1a0  mov     rdx, [rax]
0x18003e1a3  mov     rax, [rdx+8]
0x18003e1a7  mov     edx, 7F0h
0x18003e1ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e1b1  test    eax, eax
0x18003e1b3  jz      short loc_18003E1BE
0x18003e1b5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e1bc  jmp     short loc_18003E1CC
0x18003e1be  lea     rcx, qword_180153440; this
0x18003e1c5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e1cc  cmp     byte ptr [rcx+8], 0
0x18003e1d0  jz      short loc_18003E1FB
0x18003e1d2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003e1d7  test    ebx, ebx
0x18003e1d9  jns     short loc_18003E1FB
0x18003e1db  cmp     [rax+7CCh], ebx
0x18003e1e1  jz      short loc_18003E1FB
0x18003e1e3  mov     r9d, ebx; int
0x18003e1e6  lea     rdx, aCxcodevideopro_44; "CxCodeVideoProcThread::QueryInterface"
0x18003e1ed  mov     r8d, 7Eh ; '~'; int
0x18003e1f3  mov     rcx, rax; this
0x18003e1f6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003e1fb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003e202  jb      loc_18003E2E9
0x18003e208  mov     edx, 0Ch
0x18003e20d  jmp     loc_18003E2CB
0x18003e212  mov     r8d, 10h; Size
0x18003e218  mov     qword ptr [rsi], 0
0x18003e21f  lea     rdx, IID_IUnknown; Buf2
0x18003e226  mov     rcx, rbx; Buf1
0x18003e229  call    memcmp_0
0x18003e22e  test    eax, eax
0x18003e230  jnz     short loc_18003E240
0x18003e232  xor     ebx, ebx
0x18003e234  mov     [rsi], rdi
0x18003e237  lock inc dword ptr [rdi+34h]
0x18003e23b  jmp     loc_18003E2E9
0x18003e240  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e247  mov     ebx, 80004002h
0x18003e24c  test    rcx, rcx
0x18003e24f  jnz     short loc_18003E292
0x18003e251  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003e257  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e25e  mov     rcx, rax
0x18003e261  test    rax, rax
0x18003e264  jz      short loc_18003E284
0x18003e266  mov     rax, [rax]
0x18003e269  mov     edx, 7F0h
0x18003e26e  mov     rax, [rax+8]
0x18003e272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e277  test    eax, eax
0x18003e279  jz      short loc_18003E284
0x18003e27b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e282  jmp     short loc_18003E292
0x18003e284  lea     rcx, qword_180153440; this
0x18003e28b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e292  cmp     byte ptr [rcx+8], 0
0x18003e296  jz      short loc_18003E2BD
0x18003e298  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003e29d  cmp     [rax+7CCh], ebx
0x18003e2a3  jz      short loc_18003E2BD
0x18003e2a5  mov     r9d, ebx; int
0x18003e2a8  lea     rdx, aCxcodevideopro_44; "CxCodeVideoProcThread::QueryInterface"
0x18003e2af  mov     r8d, 88h; int
0x18003e2b5  mov     rcx, rax; this
0x18003e2b8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003e2bd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003e2c4  jb      short loc_18003E2E9
0x18003e2c6  mov     edx, 0Dh
0x18003e2cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e2d2  lea     r8, WPP_cd0276237ea237e1200ead55a1fb02c7_Traceguids
0x18003e2d9  mov     r9, rdi
0x18003e2dc  mov     [rsp+38h+var_18], ebx
0x18003e2e0  mov     rcx, [rcx+10h]
0x18003e2e4  call    WPP_SF_qD
0x18003e2e9  lea     rcx, [rsp+38h+arg_10]; this
0x18003e2ee  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003e2f3  mov     rsi, [rsp+38h+arg_8]
0x18003e2f8  mov     eax, ebx
0x18003e2fa  mov     rbx, [rsp+38h+arg_0]
0x18003e2ff  add     rsp, 30h
0x18003e303  pop     rdi
0x18003e304  retn
```
