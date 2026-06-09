# mkvparser::Track::Info::CopyStr(char * mkvparser::Track::Info::*,mkvparser::Track::Info &)

- ea: `0x180088d28`
- end: `0x180089055`
- name: `?CopyStr@Info@Track@mkvparser@@AEBAJPEQ123@PEADAEAV123@@Z`
- size: `813`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180088724`

## callees

- `0x180001ff0`
- `0x180006e04`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x180087364`
- `0x180088d28`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088d7f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088e2c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088ef9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088fb8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088d7f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088e2c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088ef9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088fb8`

## string_xrefs

- `0x180088d3e`: `mkvparser::Track::Info::CopyStr`

## pseudocode

```c
__int64 __fastcall mkvparser::Track::Info::CopyStr(__int64 a1, int a2, __int64 a3)
{
  __int64 v4; // rbx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  const char *v10; // rbp
  __int64 v11; // rdi
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  int v14; // ebx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  unsigned __int64 v21; // rbx
  char *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  char v36; // [rsp+78h] [rbp+10h] BYREF

  v4 = a2;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v36, "mkvparser::Track::Info::CopyStr", 5381);
  v10 = *(const char **)(v4 + a1);
  v11 = v4;
  if ( !v10 )
    goto LABEL_49;
  if ( *(_QWORD *)(v4 + a3) )
  {
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v8, v9);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    v14 = -2147024809;
    if ( *((_BYTE *)v12 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "mkvparser::Track::Info::CopyStr", 5390, -2147024809);
    }
    if ( g_wppLevels )
    {
      v16 = 464;
LABEL_26:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids, a1, v14);
      goto LABEL_50;
    }
    goto LABEL_50;
  }
  v17 = -1;
  do
    ++v17;
  while ( v10[v17] );
  if ( v17 != -1 )
  {
    v21 = v17 + 1;
    v22 = (char *)mkvparser::SafeArrayAlloc<char>(v7, v17 + 1);
    *(_QWORD *)(v11 + a3) = v22;
    if ( !v22 )
    {
      v26 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24, v25);
        CallStackTracing::s_wpInstance = v27;
        if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
        {
          v26 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v26 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      v14 = -2147024882;
      if ( *((_BYTE *)v26 + 8) )
      {
        v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
        if ( *((_DWORD *)v28 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v28, "mkvparser::Track::Info::CopyStr", 5401, -2147024882);
      }
      if ( g_wppLevels )
      {
        v16 = 466;
        goto LABEL_26;
      }
      goto LABEL_50;
    }
    v14 = StringCbCopyA(v22, v21, v10);
    if ( v14 < 0 )
    {
      operator delete(*(void **)(v11 + a3));
      v32 = (__int64 *)CallStackTracing::s_wpInstance;
      *(_QWORD *)(v11 + a3) = 0;
      if ( !v32 )
      {
        v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30, v31);
        CallStackTracing::s_wpInstance = v33;
        if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
        {
          v32 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v32 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v32 + 8) )
      {
        v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
        if ( *((_DWORD *)v34 + 499) != v14 )
          CallStackContext::TraceFailure(v34, "mkvparser::Track::Info::CopyStr", 5407, v14);
      }
      if ( g_wppLevels )
      {
        v16 = 467;
        goto LABEL_26;
      }
      goto LABEL_50;
    }
LABEL_49:
    v14 = 0;
    goto LABEL_50;
  }
  v18 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v8, v9);
    CallStackTracing::s_wpInstance = v19;
    if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
    {
      v18 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v18 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
    }
  }
  v14 = -2147467259;
  if ( *((_BYTE *)v18 + 8) )
  {
    v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
    if ( *((_DWORD *)v20 + 499) != -2147467259 )
      CallStackContext::TraceFailure(v20, "mkvparser::Track::Info::CopyStr", 5397, -2147467259);
  }
  if ( g_wppLevels )
  {
    v16 = 465;
    goto LABEL_26;
  }
LABEL_50:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v36);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180088d28  push    rbx
0x180088d2a  push    rbp
0x180088d2b  push    rsi
0x180088d2c  push    rdi
0x180088d2d  push    r12
0x180088d2f  push    r14
0x180088d31  sub     rsp, 38h
0x180088d35  mov     rsi, r8
0x180088d38  movsxd  rbx, edx
0x180088d3b  mov     r14, rcx
0x180088d3e  lea     r12, aMkvparserTrack_5; "mkvparser::Track::Info::CopyStr"
0x180088d45  mov     rdx, r12; char *
0x180088d48  lea     rcx, [rsp+68h+arg_8]; this
0x180088d4d  mov     r8d, 1505h; int
0x180088d53  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180088d58  mov     rbp, [rbx+r14]
0x180088d5c  mov     rdi, rbx
0x180088d5f  test    rbp, rbp
0x180088d62  jz      loc_180089039
0x180088d68  cmp     qword ptr [rbx+rsi], 0
0x180088d6d  jz      loc_180088E09
0x180088d73  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088d7a  test    rcx, rcx
0x180088d7d  jnz     short loc_180088DC6
0x180088d7f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180088d86  nop     dword ptr [rax+rax+00h]
0x180088d8b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180088d92  mov     rcx, rax
0x180088d95  test    rax, rax
0x180088d98  jz      short loc_180088DB8
0x180088d9a  mov     rax, [rax]
0x180088d9d  mov     edx, 7F0h
0x180088da2  mov     rax, [rax+8]
0x180088da6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088dab  test    eax, eax
0x180088dad  jz      short loc_180088DB8
0x180088daf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088db6  jmp     short loc_180088DC6
0x180088db8  lea     rcx, qword_1800DBF70; this
0x180088dbf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180088dc6  cmp     byte ptr [rcx+8], 0
0x180088dca  mov     ebx, 80070057h
0x180088dcf  jz      short loc_180088DF2
0x180088dd1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180088dd6  cmp     [rax+7CCh], ebx
0x180088ddc  jz      short loc_180088DF2
0x180088dde  mov     r9d, ebx; int
0x180088de1  mov     r8d, 150Eh; int
0x180088de7  mov     rdx, r12; char *
0x180088dea  mov     rcx, rax; this
0x180088ded  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180088df2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180088df9  jb      loc_18008903B
0x180088dff  mov     edx, 1D0h
0x180088e04  jmp     loc_180088EB1
0x180088e09  or      rax, 0FFFFFFFFFFFFFFFFh
0x180088e0d  inc     rax
0x180088e10  cmp     byte ptr [rax+rbp], 0
0x180088e14  jnz     short loc_180088E0D
0x180088e16  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180088e1a  jnz     loc_180088ED4
0x180088e20  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088e27  test    rcx, rcx
0x180088e2a  jnz     short loc_180088E73
0x180088e2c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180088e33  nop     dword ptr [rax+rax+00h]
0x180088e38  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180088e3f  mov     rcx, rax
0x180088e42  test    rax, rax
0x180088e45  jz      short loc_180088E65
0x180088e47  mov     rax, [rax]
0x180088e4a  mov     edx, 7F0h
0x180088e4f  mov     rax, [rax+8]
0x180088e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088e58  test    eax, eax
0x180088e5a  jz      short loc_180088E65
0x180088e5c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088e63  jmp     short loc_180088E73
0x180088e65  lea     rcx, qword_1800DBF70; this
0x180088e6c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180088e73  cmp     byte ptr [rcx+8], 0
0x180088e77  mov     ebx, 80004005h
0x180088e7c  jz      short loc_180088E9F
0x180088e7e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180088e83  cmp     [rax+7CCh], ebx
0x180088e89  jz      short loc_180088E9F
0x180088e8b  mov     r9d, ebx; int
0x180088e8e  mov     r8d, 1515h; int
0x180088e94  mov     rdx, r12; char *
0x180088e97  mov     rcx, rax; this
0x180088e9a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180088e9f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180088ea6  jb      loc_18008903B
0x180088eac  mov     edx, 1D1h
0x180088eb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180088eb8  lea     r8, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids
0x180088ebf  mov     r9, r14
0x180088ec2  mov     [rsp+68h+var_48], ebx
0x180088ec6  mov     rcx, [rcx+10h]
0x180088eca  call    WPP_SF_qD
0x180088ecf  jmp     loc_18008903B
0x180088ed4  lea     rbx, [rax+1]
0x180088ed8  mov     rdx, rbx
0x180088edb  call    ??$SafeArrayAlloc@D@mkvparser@@YAPEAD_K0@Z; mkvparser::SafeArrayAlloc<char>(unsigned __int64,unsigned __int64)
0x180088ee0  mov     [rdi+rsi], rax
0x180088ee4  test    rax, rax
0x180088ee7  jnz     loc_180088F83
0x180088eed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088ef4  test    rcx, rcx
0x180088ef7  jnz     short loc_180088F40
0x180088ef9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180088f00  nop     dword ptr [rax+rax+00h]
0x180088f05  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180088f0c  mov     rcx, rax
0x180088f0f  test    rax, rax
0x180088f12  jz      short loc_180088F32
0x180088f14  mov     rax, [rax]
0x180088f17  mov     edx, 7F0h
0x180088f1c  mov     rax, [rax+8]
0x180088f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088f25  test    eax, eax
0x180088f27  jz      short loc_180088F32
0x180088f29  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088f30  jmp     short loc_180088F40
0x180088f32  lea     rcx, qword_1800DBF70; this
0x180088f39  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180088f40  cmp     byte ptr [rcx+8], 0
0x180088f44  mov     ebx, 8007000Eh
0x180088f49  jz      short loc_180088F6C
0x180088f4b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180088f50  cmp     [rax+7CCh], ebx
0x180088f56  jz      short loc_180088F6C
0x180088f58  mov     r9d, ebx; int
0x180088f5b  mov     r8d, 1519h; int
0x180088f61  mov     rdx, r12; char *
0x180088f64  mov     rcx, rax; this
0x180088f67  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180088f6c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180088f73  jb      loc_18008903B
0x180088f79  mov     edx, 1D2h
0x180088f7e  jmp     loc_180088EB1
0x180088f83  mov     r8, rbp; char *
0x180088f86  mov     rdx, rbx; unsigned __int64
0x180088f89  mov     rcx, rax; char *
0x180088f8c  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x180088f91  mov     ebx, eax
0x180088f93  test    eax, eax
0x180088f95  jns     loc_180089039
0x180088f9b  mov     rcx, [rdi+rsi]; Block
0x180088f9f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180088fa4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088fab  mov     qword ptr [rdi+rsi], 0
0x180088fb3  test    rcx, rcx
0x180088fb6  jnz     short loc_180088FFF
0x180088fb8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180088fbf  nop     dword ptr [rax+rax+00h]
0x180088fc4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180088fcb  mov     rcx, rax
0x180088fce  test    rax, rax
0x180088fd1  jz      short loc_180088FF1
0x180088fd3  mov     rax, [rax]
0x180088fd6  mov     edx, 7F0h
0x180088fdb  mov     rax, [rax+8]
0x180088fdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088fe4  test    eax, eax
0x180088fe6  jz      short loc_180088FF1
0x180088fe8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088fef  jmp     short loc_180088FFF
0x180088ff1  lea     rcx, qword_1800DBF70; this
0x180088ff8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180088fff  cmp     byte ptr [rcx+8], 0
0x180089003  jz      short loc_180089026
0x180089005  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008900a  cmp     [rax+7CCh], ebx
0x180089010  jz      short loc_180089026
0x180089012  mov     r9d, ebx; int
0x180089015  mov     r8d, 151Fh; int
0x18008901b  mov     rdx, r12; char *
0x18008901e  mov     rcx, rax; this
0x180089021  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180089026  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008902d  jb      short loc_18008903B
0x18008902f  mov     edx, 1D3h
0x180089034  jmp     loc_180088EB1
0x180089039  xor     ebx, ebx
0x18008903b  lea     rcx, [rsp+68h+arg_8]; this
0x180089040  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180089045  mov     eax, ebx
0x180089047  add     rsp, 38h
0x18008904b  pop     r14
0x18008904d  pop     r12
0x18008904f  pop     rdi
0x180089050  pop     rsi
0x180089051  pop     rbp
0x180089052  pop     rbx
0x180089053  retn
```
