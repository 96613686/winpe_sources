# mkvparser::Track::Info::CopyStr(char * mkvparser::Track::Info::*,mkvparser::Track::Info &)

- ea: `0x1800851a4`
- end: `0x1800854b8`
- name: `?CopyStr@Info@Track@mkvparser@@AEBAJPEQ123@PEADAEAV123@@Z`
- size: `788`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180084bd0`

## callees

- `0x180001fd0`
- `0x180006bbc`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x18008385c`
- `0x1800851a4`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800851fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800852a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085369`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085422`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800851fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800852a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085369`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085422`

## string_xrefs

- `0x1800851ba`: `mkvparser::Track::Info::CopyStr`

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
        v12 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids, a1, v14);
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
          v26 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v32 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      v18 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x1800851a4  push    rbx
0x1800851a6  push    rbp
0x1800851a7  push    rsi
0x1800851a8  push    rdi
0x1800851a9  push    r12
0x1800851ab  push    r14
0x1800851ad  sub     rsp, 38h
0x1800851b1  mov     rsi, r8
0x1800851b4  movsxd  rbx, edx
0x1800851b7  mov     r14, rcx
0x1800851ba  lea     r12, aMkvparserTrack_5; "mkvparser::Track::Info::CopyStr"
0x1800851c1  mov     rdx, r12; char *
0x1800851c4  lea     rcx, [rsp+68h+arg_8]; this
0x1800851c9  mov     r8d, 1505h; int
0x1800851cf  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800851d4  mov     rbp, [rbx+r14]
0x1800851d8  mov     rdi, rbx
0x1800851db  test    rbp, rbp
0x1800851de  jz      loc_18008549D
0x1800851e4  cmp     qword ptr [rbx+rsi], 0
0x1800851e9  jz      loc_18008527F
0x1800851ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800851f6  test    rcx, rcx
0x1800851f9  jnz     short loc_18008523C
0x1800851fb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180085201  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180085208  mov     rcx, rax
0x18008520b  test    rax, rax
0x18008520e  jz      short loc_18008522E
0x180085210  mov     rax, [rax]
0x180085213  mov     edx, 7F0h
0x180085218  mov     rax, [rax+8]
0x18008521c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085221  test    eax, eax
0x180085223  jz      short loc_18008522E
0x180085225  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008522c  jmp     short loc_18008523C
0x18008522e  lea     rcx, qword_1800D6F70; this
0x180085235  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008523c  cmp     byte ptr [rcx+8], 0
0x180085240  mov     ebx, 80070057h
0x180085245  jz      short loc_180085268
0x180085247  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008524c  cmp     [rax+7CCh], ebx
0x180085252  jz      short loc_180085268
0x180085254  mov     r9d, ebx; int
0x180085257  mov     r8d, 150Eh; int
0x18008525d  mov     rdx, r12; char *
0x180085260  mov     rcx, rax; this
0x180085263  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180085268  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008526f  jb      loc_18008549F
0x180085275  mov     edx, 1D0h
0x18008527a  jmp     loc_180085321
0x18008527f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180085283  inc     rax
0x180085286  cmp     byte ptr [rax+rbp], 0
0x18008528a  jnz     short loc_180085283
0x18008528c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180085290  jnz     loc_180085344
0x180085296  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008529d  test    rcx, rcx
0x1800852a0  jnz     short loc_1800852E3
0x1800852a2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800852a8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800852af  mov     rcx, rax
0x1800852b2  test    rax, rax
0x1800852b5  jz      short loc_1800852D5
0x1800852b7  mov     rax, [rax]
0x1800852ba  mov     edx, 7F0h
0x1800852bf  mov     rax, [rax+8]
0x1800852c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800852c8  test    eax, eax
0x1800852ca  jz      short loc_1800852D5
0x1800852cc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800852d3  jmp     short loc_1800852E3
0x1800852d5  lea     rcx, qword_1800D6F70; this
0x1800852dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800852e3  cmp     byte ptr [rcx+8], 0
0x1800852e7  mov     ebx, 80004005h
0x1800852ec  jz      short loc_18008530F
0x1800852ee  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800852f3  cmp     [rax+7CCh], ebx
0x1800852f9  jz      short loc_18008530F
0x1800852fb  mov     r9d, ebx; int
0x1800852fe  mov     r8d, 1515h; int
0x180085304  mov     rdx, r12; char *
0x180085307  mov     rcx, rax; this
0x18008530a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008530f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180085316  jb      loc_18008549F
0x18008531c  mov     edx, 1D1h
0x180085321  mov     rcx, cs:WPP_GLOBAL_Control
0x180085328  lea     r8, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids
0x18008532f  mov     r9, r14
0x180085332  mov     [rsp+68h+var_48], ebx
0x180085336  mov     rcx, [rcx+10h]
0x18008533a  call    WPP_SF_qD
0x18008533f  jmp     loc_18008549F
0x180085344  lea     rbx, [rax+1]
0x180085348  mov     rdx, rbx
0x18008534b  call    ??$SafeArrayAlloc@D@mkvparser@@YAPEAD_K0@Z; mkvparser::SafeArrayAlloc<char>(unsigned __int64,unsigned __int64)
0x180085350  mov     [rdi+rsi], rax
0x180085354  test    rax, rax
0x180085357  jnz     loc_1800853ED
0x18008535d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180085364  test    rcx, rcx
0x180085367  jnz     short loc_1800853AA
0x180085369  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008536f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180085376  mov     rcx, rax
0x180085379  test    rax, rax
0x18008537c  jz      short loc_18008539C
0x18008537e  mov     rax, [rax]
0x180085381  mov     edx, 7F0h
0x180085386  mov     rax, [rax+8]
0x18008538a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008538f  test    eax, eax
0x180085391  jz      short loc_18008539C
0x180085393  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008539a  jmp     short loc_1800853AA
0x18008539c  lea     rcx, qword_1800D6F70; this
0x1800853a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800853aa  cmp     byte ptr [rcx+8], 0
0x1800853ae  mov     ebx, 8007000Eh
0x1800853b3  jz      short loc_1800853D6
0x1800853b5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800853ba  cmp     [rax+7CCh], ebx
0x1800853c0  jz      short loc_1800853D6
0x1800853c2  mov     r9d, ebx; int
0x1800853c5  mov     r8d, 1519h; int
0x1800853cb  mov     rdx, r12; char *
0x1800853ce  mov     rcx, rax; this
0x1800853d1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800853d6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800853dd  jb      loc_18008549F
0x1800853e3  mov     edx, 1D2h
0x1800853e8  jmp     loc_180085321
0x1800853ed  mov     r8, rbp; char *
0x1800853f0  mov     rdx, rbx; unsigned __int64
0x1800853f3  mov     rcx, rax; char *
0x1800853f6  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x1800853fb  mov     ebx, eax
0x1800853fd  test    eax, eax
0x1800853ff  jns     loc_18008549D
0x180085405  mov     rcx, [rdi+rsi]; Block
0x180085409  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008540e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180085415  mov     qword ptr [rdi+rsi], 0
0x18008541d  test    rcx, rcx
0x180085420  jnz     short loc_180085463
0x180085422  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180085428  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008542f  mov     rcx, rax
0x180085432  test    rax, rax
0x180085435  jz      short loc_180085455
0x180085437  mov     rax, [rax]
0x18008543a  mov     edx, 7F0h
0x18008543f  mov     rax, [rax+8]
0x180085443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085448  test    eax, eax
0x18008544a  jz      short loc_180085455
0x18008544c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180085453  jmp     short loc_180085463
0x180085455  lea     rcx, qword_1800D6F70; this
0x18008545c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180085463  cmp     byte ptr [rcx+8], 0
0x180085467  jz      short loc_18008548A
0x180085469  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008546e  cmp     [rax+7CCh], ebx
0x180085474  jz      short loc_18008548A
0x180085476  mov     r9d, ebx; int
0x180085479  mov     r8d, 151Fh; int
0x18008547f  mov     rdx, r12; char *
0x180085482  mov     rcx, rax; this
0x180085485  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008548a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180085491  jb      short loc_18008549F
0x180085493  mov     edx, 1D3h
0x180085498  jmp     loc_180085321
0x18008549d  xor     ebx, ebx
0x18008549f  lea     rcx, [rsp+68h+arg_8]; this
0x1800854a4  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800854a9  mov     eax, ebx
0x1800854ab  add     rsp, 38h
0x1800854af  pop     r14
0x1800854b1  pop     r12
0x1800854b3  pop     rdi
0x1800854b4  pop     rsi
0x1800854b5  pop     rbp
0x1800854b6  pop     rbx
0x1800854b7  retn
```
