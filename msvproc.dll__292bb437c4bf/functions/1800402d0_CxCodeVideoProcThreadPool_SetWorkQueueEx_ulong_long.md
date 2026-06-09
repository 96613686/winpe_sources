# CxCodeVideoProcThreadPool::SetWorkQueueEx(ulong,long)

- ea: `0x1800402d0`
- end: `0x180040411`
- name: `?SetWorkQueueEx@CxCodeVideoProcThreadPool@@QEAAJKJ@Z`
- size: `321`
- prototype: `int(CxCodeVideoProcThreadPool *__hidden this, unsigned int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180038eb0`

## callees

- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x1800402d0`
- `0x1800a422c`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040360`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040360`

## string_xrefs

- `0x18004031d`: `CxCodeVideoProcThreadPool::SetWorkQueueEx`
- `0x1800403b7`: `CxCodeVideoProcThreadPool::SetWorkQueueEx`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcThreadPool::SetWorkQueueEx(CxCodeVideoProcThreadPool *this, unsigned int a2, int a3)
{
  int v3; // edi
  bool v4; // zf
  __int64 i; // rsi
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v13; // [rsp+78h] [rbp+10h] BYREF

  v3 = 0;
  *((_DWORD *)this + 10) = a2;
  v4 = *((_DWORD *)this + 4) == 1;
  *((_DWORD *)this + 11) = a3;
  if ( !v4 && *(_QWORD *)this )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 4); i = (unsigned int)(i + 1) )
    {
      if ( *(_QWORD *)(*(_QWORD *)this + 8 * i) )
      {
        CallStackScopeTrace::CallStackScopeTrace(
          (CallStackScopeTrace *)&v13,
          "CxCodeVideoProcThreadPool::SetWorkQueueEx",
          337);
        v3 = CxCodeVideoProcThread::SetWorkQueueEx(*(CxCodeVideoProcThread **)(*(_QWORD *)this + 8 * i), a2, a3);
        if ( v3 < 0 )
        {
          v9 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v10;
            if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
            {
              v9 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v9 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v9 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v3 )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "CxCodeVideoProcThreadPool::SetWorkQueueEx",
                337,
                v3);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              23,
              WPP_31017d59e5fa36e4c5717ad5ebbdb595_Traceguids,
              this,
              v3);
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v13);
          return (unsigned int)v3;
        }
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v13);
      }
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800402d0  push    rbx
0x1800402d2  push    rbp
0x1800402d3  push    rsi
0x1800402d4  push    rdi
0x1800402d5  push    r14
0x1800402d7  push    r15
0x1800402d9  sub     rsp, 38h
0x1800402dd  xor     edi, edi
0x1800402df  mov     [rcx+28h], edx
0x1800402e2  cmp     dword ptr [rcx+10h], 1
0x1800402e6  mov     r14d, r8d
0x1800402e9  mov     r15d, edx
0x1800402ec  mov     [rcx+2Ch], r8d
0x1800402f0  mov     rbx, rcx
0x1800402f3  jz      loc_180040402
0x1800402f9  cmp     [rcx], rdi
0x1800402fc  jz      loc_180040402
0x180040302  xor     esi, esi
0x180040304  cmp     esi, [rbx+10h]
0x180040307  jnb     loc_180040402
0x18004030d  mov     rax, [rbx]
0x180040310  cmp     qword ptr [rax+rsi*8], 0
0x180040315  jz      short loc_180040350
0x180040317  mov     r8d, 151h; int
0x18004031d  lea     rdx, aCxcodevideopro_122; "CxCodeVideoProcThreadPool::SetWorkQueue"...
0x180040324  lea     rcx, [rsp+68h+arg_8]; this
0x180040329  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004032e  mov     rcx, [rbx]
0x180040331  mov     r8d, r14d; int
0x180040334  mov     edx, r15d; unsigned int
0x180040337  mov     rcx, [rcx+rsi*8]; this
0x18004033b  call    ?SetWorkQueueEx@CxCodeVideoProcThread@@QEAAJKJ@Z; CxCodeVideoProcThread::SetWorkQueueEx(ulong,long)
0x180040340  mov     edi, eax
0x180040342  test    eax, eax
0x180040344  js      short loc_180040354
0x180040346  lea     rcx, [rsp+68h+arg_8]; this
0x18004034b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180040350  inc     esi
0x180040352  jmp     short loc_180040304
0x180040354  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004035b  test    rcx, rcx
0x18004035e  jnz     short loc_1800403A1
0x180040360  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180040366  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004036d  mov     rcx, rax
0x180040370  test    rax, rax
0x180040373  jz      short loc_180040393
0x180040375  mov     rax, [rax]
0x180040378  mov     edx, 7F0h
0x18004037d  mov     rax, [rax+8]
0x180040381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040386  test    eax, eax
0x180040388  jz      short loc_180040393
0x18004038a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180040391  jmp     short loc_1800403A1
0x180040393  lea     rcx, qword_180153440; this
0x18004039a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800403a1  cmp     byte ptr [rcx+8], 0
0x1800403a5  jz      short loc_1800403CC
0x1800403a7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800403ac  cmp     [rax+7CCh], edi
0x1800403b2  jz      short loc_1800403CC
0x1800403b4  mov     r9d, edi; int
0x1800403b7  lea     rdx, aCxcodevideopro_122; "CxCodeVideoProcThreadPool::SetWorkQueue"...
0x1800403be  mov     r8d, 151h; int
0x1800403c4  mov     rcx, rax; this
0x1800403c7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800403cc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800403d3  jb      short loc_1800403F8
0x1800403d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800403dc  lea     r8, WPP_31017d59e5fa36e4c5717ad5ebbdb595_Traceguids
0x1800403e3  mov     edx, 17h
0x1800403e8  mov     [rsp+68h+var_48], edi
0x1800403ec  mov     r9, rbx
0x1800403ef  mov     rcx, [rcx+10h]
0x1800403f3  call    WPP_SF_qD
0x1800403f8  lea     rcx, [rsp+68h+arg_8]; this
0x1800403fd  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180040402  mov     eax, edi
0x180040404  add     rsp, 38h
0x180040408  pop     r15
0x18004040a  pop     r14
0x18004040c  pop     rdi
0x18004040d  pop     rsi
0x18004040e  pop     rbp
0x18004040f  pop     rbx
0x180040410  retn
```
