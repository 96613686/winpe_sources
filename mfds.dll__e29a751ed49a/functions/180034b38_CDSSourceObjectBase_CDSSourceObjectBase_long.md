# CDSSourceObjectBase::CDSSourceObjectBase(long *)

- ea: `0x180034b38`
- end: `0x180034d15`
- name: `??0CDSSourceObjectBase@@QEAA@PEAJ@Z`
- size: `477`
- prototype: `CDSSourceObjectBase *__fastcall(CDSSourceObjectBase *__hidden this, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180034274`
- `0x18004ce6c`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x180032a50`
- `0x180034b38`
- `0x180051ce4`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180034b5d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180034b5d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180034bad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180034c5c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180034bad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180034c5c`
- `MFPlat!MFCreateEventQueue` at `0x180034c3a`
- `MFPlat!MFCreateEventQueue` at `0x180034c3a`

## pseudocode

```c
CDSSourceObjectBase *__fastcall CDSSourceObjectBase::CDSSourceObjectBase(CDSSourceObjectBase *this, int *a2)
{
  HRESULT v4; // ebx
  CallStackTracing *v5; // rcx
  CallStackTracing *v6; // rax
  struct CallStackContext *v7; // rax
  __int64 v8; // rdx
  CallStackTracing *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v13; // [rsp+60h] [rbp+8h] BYREF

  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &CDSSourceObjectBase::`vftable';
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v4 = *a2;
  *((_DWORD *)this + 14) = 0;
  *((_QWORD *)this + 8) = 0;
  _InterlockedIncrement((_DWORD *)&qword_1800EAFE8 + 1);
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v13,
    "CDSSourceObjectBase::CDSSourceObjectBase",
    2252);
  if ( v4 >= 0 )
  {
    v4 = MFCreateEventQueue((IMFMediaEventQueue **)this + 8);
    if ( v4 < 0 )
    {
      v9 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v10;
        if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
        {
          v9 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v9 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v9 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v9);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v4 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CDSSourceObjectBase::CDSSourceObjectBase", 2254, v4);
      }
      if ( g_wppLevels )
      {
        v8 = 213;
        goto LABEL_23;
      }
    }
  }
  else
  {
    v5 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v6;
      if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
      {
        v5 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      v7 = CallStackTracing::GetThreadRelativeContext(v5);
      if ( *((_DWORD *)v7 + 499) != v4 )
        CallStackContext::TraceFailure(v7, "CDSSourceObjectBase::CDSSourceObjectBase", 2252, v4);
    }
    if ( g_wppLevels )
    {
      v8 = 212;
LABEL_23:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids, this, v4);
    }
  }
  *a2 = v4;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v13);
  return this;
}

```

## disassembly

```asm
0x180034b38  push    rbx
0x180034b3a  push    rsi
0x180034b3b  push    rdi
0x180034b3c  push    r14
0x180034b3e  sub     rsp, 38h
0x180034b42  lea     rax, ??_7CDSSourceObjectBase@@6B@; const CDSSourceObjectBase::`vftable'
0x180034b49  mov     dword ptr [rcx+8], 1
0x180034b50  mov     [rcx], rax
0x180034b53  mov     rdi, rcx
0x180034b56  add     rcx, 10h; lpCriticalSection
0x180034b5a  mov     r14, rdx
0x180034b5d  call    cs:__imp_InitializeCriticalSection
0x180034b64  nop     dword ptr [rax+rax+00h]
0x180034b69  mov     ebx, [r14]
0x180034b6c  mov     dword ptr [rdi+38h], 0
0x180034b73  mov     qword ptr [rdi+40h], 0
0x180034b7b  lock inc dword ptr cs:qword_1800EAFE8+4
0x180034b82  mov     r8d, 8CCh; int
0x180034b88  lea     rdx, aCdssourceobjec; "CDSSourceObjectBase::CDSSourceObjectBas"...
0x180034b8f  lea     rcx, [rsp+58h+arg_0]; this
0x180034b94  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180034b99  test    ebx, ebx
0x180034b9b  jns     loc_180034C36
0x180034ba1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180034ba8  test    rcx, rcx
0x180034bab  jnz     short loc_180034BF4
0x180034bad  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180034bb4  nop     dword ptr [rax+rax+00h]
0x180034bb9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180034bc0  mov     rcx, rax
0x180034bc3  test    rax, rax
0x180034bc6  jz      short loc_180034BE6
0x180034bc8  mov     rax, [rax]
0x180034bcb  mov     edx, 7F0h
0x180034bd0  mov     rax, [rax+8]
0x180034bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034bd9  test    eax, eax
0x180034bdb  jz      short loc_180034BE6
0x180034bdd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180034be4  jmp     short loc_180034BF4
0x180034be6  lea     rcx, qword_1800EB130; this
0x180034bed  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180034bf4  cmp     byte ptr [rcx+8], 0
0x180034bf8  jz      short loc_180034C1F
0x180034bfa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180034bff  cmp     [rax+7CCh], ebx
0x180034c05  jz      short loc_180034C1F
0x180034c07  mov     r9d, ebx; int
0x180034c0a  lea     rdx, aCdssourceobjec; "CDSSourceObjectBase::CDSSourceObjectBas"...
0x180034c11  mov     r8d, 8CCh; int
0x180034c17  mov     rcx, rax; this
0x180034c1a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180034c1f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180034c26  jb      loc_180034CFA
0x180034c2c  mov     edx, 0D4h
0x180034c31  jmp     loc_180034CDC
0x180034c36  lea     rcx, [rdi+40h]; ppMediaEventQueue
0x180034c3a  call    cs:__imp_MFCreateEventQueue
0x180034c41  nop     dword ptr [rax+rax+00h]
0x180034c46  mov     ebx, eax
0x180034c48  test    eax, eax
0x180034c4a  jns     loc_180034CFA
0x180034c50  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180034c57  test    rcx, rcx
0x180034c5a  jnz     short loc_180034CA3
0x180034c5c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180034c63  nop     dword ptr [rax+rax+00h]
0x180034c68  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180034c6f  mov     rcx, rax
0x180034c72  test    rax, rax
0x180034c75  jz      short loc_180034C95
0x180034c77  mov     rax, [rax]
0x180034c7a  mov     edx, 7F0h
0x180034c7f  mov     rax, [rax+8]
0x180034c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034c88  test    eax, eax
0x180034c8a  jz      short loc_180034C95
0x180034c8c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180034c93  jmp     short loc_180034CA3
0x180034c95  lea     rcx, qword_1800EB130; this
0x180034c9c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180034ca3  cmp     byte ptr [rcx+8], 0
0x180034ca7  jz      short loc_180034CCE
0x180034ca9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180034cae  cmp     [rax+7CCh], ebx
0x180034cb4  jz      short loc_180034CCE
0x180034cb6  mov     r9d, ebx; int
0x180034cb9  lea     rdx, aCdssourceobjec; "CDSSourceObjectBase::CDSSourceObjectBas"...
0x180034cc0  mov     r8d, 8CEh; int
0x180034cc6  mov     rcx, rax; this
0x180034cc9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180034cce  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180034cd5  jb      short loc_180034CFA
0x180034cd7  mov     edx, 0D5h
0x180034cdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180034ce3  lea     r8, WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids
0x180034cea  mov     r9, rdi
0x180034ced  mov     [rsp+58h+var_38], ebx
0x180034cf1  mov     rcx, [rcx+10h]
0x180034cf5  call    WPP_SF_qD
0x180034cfa  lea     rcx, [rsp+58h+arg_0]; this
0x180034cff  mov     [r14], ebx
0x180034d02  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180034d07  mov     rax, rdi
0x180034d0a  add     rsp, 38h
0x180034d0e  pop     r14
0x180034d10  pop     rdi
0x180034d11  pop     rsi
0x180034d12  pop     rbx
0x180034d13  retn
```
