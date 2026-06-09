# CxCodeVideoProcMFT::ProcessIdleTasks(void)

- ea: `0x18000c0f0`
- end: `0x18000c223`
- name: `?ProcessIdleTasks@CxCodeVideoProcMFT@@UEAAJXZ`
- size: `307`
- prototype: `__int64 __fastcall(CxCodeVideoProcMFT *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task`

## callees

- `0x18000a954`
- `0x18000c0f0`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c10a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c10a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c157`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c157`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000c180`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000c180`

## string_xrefs

- `0x18000c116`: `CxCodeVideoProcMFT::ProcessIdleTasks`
- `0x18000c1c3`: `CxCodeVideoProcMFT::ProcessIdleTasks`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcMFT::ProcessIdleTasks(CxCodeVideoProcMFT *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  char *v2; // rsi
  __int64 v3; // rcx
  __int64 v4; // rcx
  unsigned int v5; // ebx
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v10; // [rsp+40h] [rbp+8h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this - 48);
  v2 = (char *)this - 88;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this - 48));
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v10, "CxCodeVideoProcMFT::ProcessIdleTasks", 797);
  v3 = *((_QWORD *)v2 + 4);
  if ( v3 )
  {
    v4 = *(_QWORD *)(v3 + 168);
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 120LL))(v4);
    v5 = 0;
  }
  else
  {
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    v5 = -1072875845;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875845 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CxCodeVideoProcMFT::ProcessIdleTasks", 797, -1072875845);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        50,
        &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
        v2,
        -1072875845);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v10);
  LeaveCriticalSection(v1);
  return v5;
}

```

## disassembly

```asm
0x18000c0f0  mov     [rsp+arg_8], rbx
0x18000c0f5  mov     [rsp+arg_10], rsi
0x18000c0fa  push    rdi
0x18000c0fb  sub     rsp, 30h
0x18000c0ff  lea     rdi, [rcx-30h]
0x18000c103  lea     rsi, [rcx-58h]
0x18000c107  mov     rcx, rdi; lpCriticalSection
0x18000c10a  call    cs:__imp_EnterCriticalSection
0x18000c110  mov     r8d, 31Dh; int
0x18000c116  lea     rdx, aCxcodevideopro_23; "CxCodeVideoProcMFT::ProcessIdleTasks"
0x18000c11d  lea     rcx, [rsp+38h+arg_0]; this
0x18000c122  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18000c127  mov     rcx, [rsi+20h]
0x18000c12b  test    rcx, rcx
0x18000c12e  jz      short loc_18000C16F
0x18000c130  mov     rcx, [rcx+0A8h]
0x18000c137  test    rcx, rcx
0x18000c13a  jz      short loc_18000C148
0x18000c13c  mov     rax, [rcx]
0x18000c13f  mov     rax, [rax+78h]
0x18000c143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c148  xor     ebx, ebx
0x18000c14a  lea     rcx, [rsp+38h+arg_0]; this
0x18000c14f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18000c154  mov     rcx, rdi; lpCriticalSection
0x18000c157  call    cs:__imp_LeaveCriticalSection
0x18000c15d  mov     rsi, [rsp+38h+arg_10]
0x18000c162  mov     eax, ebx
0x18000c164  mov     rbx, [rsp+38h+arg_8]
0x18000c169  add     rsp, 30h
0x18000c16d  pop     rdi
0x18000c16e  retn
0x18000c16f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000c176  mov     ebx, 0C00D36BBh
0x18000c17b  test    rcx, rcx
0x18000c17e  jnz     short loc_18000C1E8
0x18000c180  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000c186  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000c18d  mov     rcx, rax
0x18000c190  test    rax, rax
0x18000c193  jz      short loc_18000C1DA
0x18000c195  mov     rax, [rax]
0x18000c198  mov     edx, 7F0h
0x18000c19d  mov     rax, [rax+8]
0x18000c1a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1a6  test    eax, eax
0x18000c1a8  jz      short loc_18000C1DA
0x18000c1aa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000c1b1  jmp     short loc_18000C1E8
0x18000c1b3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000c1b8  cmp     [rax+7CCh], ebx
0x18000c1be  jz      short loc_18000C1EE
0x18000c1c0  mov     r9d, ebx; int
0x18000c1c3  lea     rdx, aCxcodevideopro_23; "CxCodeVideoProcMFT::ProcessIdleTasks"
0x18000c1ca  mov     r8d, 31Dh; int
0x18000c1d0  mov     rcx, rax; this
0x18000c1d3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000c1d8  jmp     short loc_18000C1EE
0x18000c1da  lea     rcx, qword_180153440; this
0x18000c1e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000c1e8  cmp     byte ptr [rcx+8], 0
0x18000c1ec  jnz     short loc_18000C1B3
0x18000c1ee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000c1f5  jb      loc_18000C14A
0x18000c1fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c202  lea     r8, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x18000c209  mov     edx, 32h ; '2'
0x18000c20e  mov     [rsp+38h+var_18], ebx
0x18000c212  mov     r9, rsi
0x18000c215  mov     rcx, [rcx+10h]
0x18000c219  call    WPP_SF_qD
0x18000c21e  jmp     loc_18000C14A
```
