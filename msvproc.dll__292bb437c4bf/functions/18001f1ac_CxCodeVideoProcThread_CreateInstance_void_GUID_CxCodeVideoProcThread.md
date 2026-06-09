# CxCodeVideoProcThread::CreateInstance(void *,_GUID,CxCodeVideoProcThread * *)

- ea: `0x18001f1ac`
- end: `0x18001f2e5`
- name: `?CreateInstance@CxCodeVideoProcThread@@SAJPEAXU_GUID@@PEAPEAV1@@Z`
- size: `313`
- prototype: `__int64 __fastcall(void *, struct _GUID *__struct_ptr, struct CxCodeVideoProcThread **)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18004a1c4`

## callees

- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18001f1ac`
- `0x18001f2ec`
- `0x18003639c`
- `0x180053bfc`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001f242`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001f242`

## string_xrefs

- `0x18001f1ee`: `CxCodeVideoProcThread::CreateInstance`
- `0x18001f285`: `CxCodeVideoProcThread::CreateInstance`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcThread::CreateInstance(void *a1, struct _GUID *a2, struct CxCodeVideoProcThread **a3)
{
  CxCodeVideoProcThread *v6; // rax
  CxCodeVideoProcThread *v7; // rdi
  __int128 v8; // xmm0
  unsigned int v9; // ebx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v14; // [rsp+50h] [rbp+18h] BYREF

  *a3 = 0;
  v6 = (CxCodeVideoProcThread *)operator new(0x68u);
  if ( v6 )
    v7 = CxCodeVideoProcThread::CxCodeVideoProcThread(v6, a1);
  else
    v7 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v14, "CxCodeVideoProcThread::CreateInstance", 99);
  if ( v7 )
  {
    v8 = (__int128)*a2;
    v9 = 0;
    *(_OWORD *)((char *)v7 + 84) = v8;
    *a3 = v7;
  }
  else
  {
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    v9 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CxCodeVideoProcThread::CreateInstance", 99, -2147024882);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_cd0276237ea237e1200ead55a1fb02c7_Traceguids,
        0,
        -2147024882);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v14);
  return v9;
}

```

## disassembly

```asm
0x18001f1ac  mov     [rsp+arg_0], rbx
0x18001f1b1  mov     [rsp+arg_8], rsi
0x18001f1b6  push    rdi
0x18001f1b7  sub     rsp, 30h
0x18001f1bb  mov     rdi, rcx
0x18001f1be  mov     qword ptr [r8], 0
0x18001f1c5  mov     ecx, 68h ; 'h'; Size
0x18001f1ca  mov     rsi, r8
0x18001f1cd  mov     rbx, rdx
0x18001f1d0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f1d5  test    rax, rax
0x18001f1d8  jz      short loc_18001F22D
0x18001f1da  mov     rdx, rdi; void *
0x18001f1dd  mov     rcx, rax; this
0x18001f1e0  call    ??0CxCodeVideoProcThread@@AEAA@PEAX@Z; CxCodeVideoProcThread::CxCodeVideoProcThread(void *)
0x18001f1e5  mov     rdi, rax
0x18001f1e8  mov     r8d, 63h ; 'c'; int
0x18001f1ee  lea     rdx, aCxcodevideopro_13; "CxCodeVideoProcThread::CreateInstance"
0x18001f1f5  lea     rcx, [rsp+38h+arg_10]; this
0x18001f1fa  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001f1ff  test    rdi, rdi
0x18001f202  jz      short loc_18001F231
0x18001f204  movaps  xmm0, xmmword ptr [rbx]
0x18001f207  xor     ebx, ebx
0x18001f209  movdqu  xmmword ptr [rdi+54h], xmm0
0x18001f20e  mov     [rsi], rdi
0x18001f211  lea     rcx, [rsp+38h+arg_10]; this
0x18001f216  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001f21b  mov     rsi, [rsp+38h+arg_8]
0x18001f220  mov     eax, ebx
0x18001f222  mov     rbx, [rsp+38h+arg_0]
0x18001f227  add     rsp, 30h
0x18001f22b  pop     rdi
0x18001f22c  retn
0x18001f22d  xor     edi, edi
0x18001f22f  jmp     short loc_18001F1E8
0x18001f231  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001f238  mov     ebx, 8007000Eh
0x18001f23d  test    rcx, rcx
0x18001f240  jnz     short loc_18001F2AA
0x18001f242  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001f248  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001f24f  mov     rcx, rax
0x18001f252  test    rax, rax
0x18001f255  jz      short loc_18001F29C
0x18001f257  mov     rax, [rax]
0x18001f25a  mov     edx, 7F0h
0x18001f25f  mov     rax, [rax+8]
0x18001f263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f268  test    eax, eax
0x18001f26a  jz      short loc_18001F29C
0x18001f26c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001f273  jmp     short loc_18001F2AA
0x18001f275  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001f27a  cmp     [rax+7CCh], ebx
0x18001f280  jz      short loc_18001F2B0
0x18001f282  mov     r9d, ebx; int
0x18001f285  lea     rdx, aCxcodevideopro_13; "CxCodeVideoProcThread::CreateInstance"
0x18001f28c  mov     r8d, 63h ; 'c'; int
0x18001f292  mov     rcx, rax; this
0x18001f295  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001f29a  jmp     short loc_18001F2B0
0x18001f29c  lea     rcx, qword_180153440; this
0x18001f2a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001f2aa  cmp     byte ptr [rcx+8], 0
0x18001f2ae  jnz     short loc_18001F275
0x18001f2b0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001f2b7  jb      loc_18001F211
0x18001f2bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f2c4  lea     r8, WPP_cd0276237ea237e1200ead55a1fb02c7_Traceguids
0x18001f2cb  mov     edx, 0Ah
0x18001f2d0  mov     [rsp+38h+var_18], ebx
0x18001f2d4  xor     r9d, r9d
0x18001f2d7  mov     rcx, [rcx+10h]
0x18001f2db  call    WPP_SF_qD
0x18001f2e0  jmp     loc_18001F211
```
