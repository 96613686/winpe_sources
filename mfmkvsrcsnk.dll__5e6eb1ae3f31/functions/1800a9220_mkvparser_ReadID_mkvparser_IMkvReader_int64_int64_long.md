# mkvparser::ReadID(mkvparser::IMkvReader *,__int64,__int64 &,long &)

- ea: `0x1800a9220`
- end: `0x1800a96c4`
- name: `?ReadID@mkvparser@@YAJPEAUIMkvReader@1@_JAEA_JAEAJ@Z`
- size: `1188`
- prototype: `__int64 __fastcall(mkvparser *__hidden this, struct mkvparser::IMkvReader *, __int64, __int64 *, int *)`
- caller_count: `25`
- callee_count: `7`
- tags: ``

## callers

- `0x180085edc`
- `0x1800867f0`
- `0x1800870cc`
- `0x180088614`
- `0x18008b0dc`
- `0x18008c718`
- `0x18008d628`
- `0x18008dbd4`
- `0x18008dfe0`
- `0x18008ef54`
- `0x18008fb48`
- `0x180090ff8`
- `0x180091950`
- `0x1800953f4`
- `0x180097920`
- `0x18009b3e4`
- `0x18009ba68`
- `0x18009dd9c`
- `0x1800a0978`
- `0x1800a1710`
- `0x1800a27b8`
- `0x1800a3018`
- `0x1800a43f4`
- `0x1800a4d84`
- `0x1800a5eb4`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x1800a9220`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9269`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9302`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a93cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9468`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9571`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9611`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9269`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9302`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a93cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9468`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9571`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9611`

## string_xrefs

- `0x1800a9231`: `mkvparser::ReadID`
- `0x1800a95c8`: `mkvparser::ReadID`

## pseudocode

```c
__int64 __fastcall mkvparser::ReadID(
        __int64 (__fastcall ***this)(mkvparser *, struct mkvparser::IMkvReader *, __int64, unsigned __int8 *),
        struct mkvparser::IMkvReader *a2,
        __int64 *a3,
        __int64 *a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  int v13; // ebx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 (__fastcall **v19)(mkvparser *, struct mkvparser::IMkvReader *, __int64, unsigned __int8 *); // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // r8
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  int i; // ecx
  __int64 v31; // rax
  int j; // esi
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  _BYTE v43[72]; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int8 v44; // [rsp+80h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v43, "mkvparser::ReadID", 278);
  if ( !this )
  {
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9, v10);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    v13 = -2147024809;
    if ( *((_BYTE *)v11 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "mkvparser::ReadID", 278, -2147024809);
    }
    if ( !g_wppLevels )
      goto LABEL_75;
    v15 = 15;
    goto LABEL_74;
  }
  if ( (__int64)a2 < 0 )
  {
    v16 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9, v10);
      CallStackTracing::s_wpInstance = v17;
      if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
      {
        v16 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v16 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    v13 = -2147024809;
    if ( *((_BYTE *)v16 + 8) )
    {
      v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
      if ( *((_DWORD *)v18 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v18, "mkvparser::ReadID", 282, -2147024809);
    }
    if ( !g_wppLevels )
      goto LABEL_75;
    v15 = 16;
    goto LABEL_74;
  }
  *(_DWORD *)a4 = 1;
  v19 = *this;
  v44 = 0;
  v13 = (*v19)((mkvparser *)this, a2, 1, &v44);
  if ( v13 < 0 )
  {
    v23 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v21, v22);
      CallStackTracing::s_wpInstance = v24;
      if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
      {
        v23 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v23 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v23 + 8) )
    {
      v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
      if ( *((_DWORD *)v25 + 499) != v13 )
        CallStackContext::TraceFailure(v25, "mkvparser::ReadID", 291, v13);
    }
    if ( !g_wppLevels )
      goto LABEL_75;
    v15 = 17;
    goto LABEL_74;
  }
  v26 = v44;
  if ( !v44 )
  {
    v27 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v44, v22);
      CallStackTracing::s_wpInstance = v28;
      if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
      {
        v27 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v27 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    v13 = -1072875842;
    if ( *((_BYTE *)v27 + 8) )
    {
      v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
      if ( *((_DWORD *)v29 + 499) != -1072875842 )
        CallStackContext::TraceFailure(v29, "mkvparser::ReadID", 295, -1072875842);
    }
    if ( !g_wppLevels )
      goto LABEL_75;
    v15 = 18;
LABEL_74:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids, 0, v13);
    goto LABEL_75;
  }
  for ( i = 0; i < 4; ++i )
  {
    v22 = (unsigned int)(i + 1);
    v20 = 128 >> i;
    if ( ((unsigned __int8)v20 & v44) != 0 )
    {
      v31 = v44;
      *(_DWORD *)a4 = v22;
      *a3 = v26;
      for ( j = 1; ; ++j )
      {
        if ( j >= *(_DWORD *)a4 )
        {
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v43);
          return 0;
        }
        *a3 = v31 << 8;
        v13 = (**this)((mkvparser *)this, (struct mkvparser::IMkvReader *)((char *)a2 + j), 1, &v44);
        if ( v13 < 0 )
          break;
        *a3 = v44 | (unsigned __int64)*a3;
        v31 = *a3;
      }
      v36 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34, v35);
        CallStackTracing::s_wpInstance = v37;
        if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
        {
          v36 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v36 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v36 + 8) )
      {
        v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
        if ( *((_DWORD *)v38 + 499) != v13 )
          CallStackContext::TraceFailure(v38, "mkvparser::ReadID", 321, v13);
      }
      if ( g_wppLevels )
      {
        v15 = 20;
        goto LABEL_74;
      }
      goto LABEL_75;
    }
  }
  v40 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v44, v22);
    CallStackTracing::s_wpInstance = v41;
    if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
    {
      v40 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v40 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
    }
  }
  v13 = -1072875842;
  if ( *((_BYTE *)v40 + 8) )
  {
    v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
    if ( *((_DWORD *)v42 + 499) != -1072875842 )
      CallStackContext::TraceFailure(v42, "mkvparser::ReadID", 313, -1072875842);
  }
  if ( g_wppLevels )
  {
    v15 = 19;
    goto LABEL_74;
  }
LABEL_75:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v43);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800a9220  push    rbx
0x1800a9222  push    rbp
0x1800a9223  push    rsi
0x1800a9224  push    r12
0x1800a9226  push    r14
0x1800a9228  push    r15
0x1800a922a  sub     rsp, 48h
0x1800a922e  mov     r14, r8
0x1800a9231  lea     rsi, aMkvparserReadi; "mkvparser::ReadID"
0x1800a9238  mov     r12, rdx
0x1800a923b  mov     rbp, rcx
0x1800a923e  mov     rdx, rsi; char *
0x1800a9241  lea     rcx, [rsp+78h+var_48]; this
0x1800a9246  mov     r8d, 116h; int
0x1800a924c  mov     r15, r9
0x1800a924f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a9254  test    rbp, rbp
0x1800a9257  jnz     loc_1800A92ED
0x1800a925d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9264  test    rcx, rcx
0x1800a9267  jnz     short loc_1800A92AA
0x1800a9269  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a926f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9276  mov     rcx, rax
0x1800a9279  test    rax, rax
0x1800a927c  jz      short loc_1800A929C
0x1800a927e  mov     rax, [rax]
0x1800a9281  mov     edx, 7F0h
0x1800a9286  mov     rax, [rax+8]
0x1800a928a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a928f  test    eax, eax
0x1800a9291  jz      short loc_1800A929C
0x1800a9293  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a929a  jmp     short loc_1800A92AA
0x1800a929c  lea     rcx, qword_1800D6F70; this
0x1800a92a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a92aa  cmp     byte ptr [rcx+8], 0
0x1800a92ae  mov     ebx, 80070057h
0x1800a92b3  jz      short loc_1800A92D6
0x1800a92b5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a92ba  cmp     [rax+7CCh], ebx
0x1800a92c0  jz      short loc_1800A92D6
0x1800a92c2  mov     r9d, ebx; int
0x1800a92c5  mov     r8d, 116h; int
0x1800a92cb  mov     rdx, rsi; char *
0x1800a92ce  mov     rcx, rax; this
0x1800a92d1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a92d6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a92dd  jb      loc_1800A96AA
0x1800a92e3  mov     edx, 0Fh
0x1800a92e8  jmp     loc_1800A968C
0x1800a92ed  test    r12, r12
0x1800a92f0  jns     loc_1800A9386
0x1800a92f6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a92fd  test    rcx, rcx
0x1800a9300  jnz     short loc_1800A9343
0x1800a9302  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a9308  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a930f  mov     rcx, rax
0x1800a9312  test    rax, rax
0x1800a9315  jz      short loc_1800A9335
0x1800a9317  mov     rax, [rax]
0x1800a931a  mov     edx, 7F0h
0x1800a931f  mov     rax, [rax+8]
0x1800a9323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9328  test    eax, eax
0x1800a932a  jz      short loc_1800A9335
0x1800a932c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9333  jmp     short loc_1800A9343
0x1800a9335  lea     rcx, qword_1800D6F70; this
0x1800a933c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9343  cmp     byte ptr [rcx+8], 0
0x1800a9347  mov     ebx, 80070057h
0x1800a934c  jz      short loc_1800A936F
0x1800a934e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a9353  cmp     [rax+7CCh], ebx
0x1800a9359  jz      short loc_1800A936F
0x1800a935b  mov     r9d, ebx; int
0x1800a935e  mov     r8d, 11Ah; int
0x1800a9364  mov     rdx, rsi; char *
0x1800a9367  mov     rcx, rax; this
0x1800a936a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a936f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a9376  jb      loc_1800A96AA
0x1800a937c  mov     edx, 10h
0x1800a9381  jmp     loc_1800A968C
0x1800a9386  mov     dword ptr [r15], 1
0x1800a938d  lea     r9, [rsp+78h+arg_0]
0x1800a9395  mov     rax, [rbp+0]
0x1800a9399  mov     r8d, 1
0x1800a939f  mov     rdx, r12
0x1800a93a2  mov     [rsp+78h+arg_0], 0
0x1800a93aa  mov     rcx, rbp
0x1800a93ad  mov     rax, [rax]
0x1800a93b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a93b5  mov     ebx, eax
0x1800a93b7  test    eax, eax
0x1800a93b9  jns     loc_1800A944A
0x1800a93bf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a93c6  test    rcx, rcx
0x1800a93c9  jnz     short loc_1800A940C
0x1800a93cb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a93d1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a93d8  mov     rcx, rax
0x1800a93db  test    rax, rax
0x1800a93de  jz      short loc_1800A93FE
0x1800a93e0  mov     rax, [rax]
0x1800a93e3  mov     edx, 7F0h
0x1800a93e8  mov     rax, [rax+8]
0x1800a93ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a93f1  test    eax, eax
0x1800a93f3  jz      short loc_1800A93FE
0x1800a93f5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a93fc  jmp     short loc_1800A940C
0x1800a93fe  lea     rcx, qword_1800D6F70; this
0x1800a9405  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a940c  cmp     byte ptr [rcx+8], 0
0x1800a9410  jz      short loc_1800A9433
0x1800a9412  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a9417  cmp     [rax+7CCh], ebx
0x1800a941d  jz      short loc_1800A9433
0x1800a941f  mov     r9d, ebx; int
0x1800a9422  mov     r8d, 123h; int
0x1800a9428  mov     rdx, rsi; char *
0x1800a942b  mov     rcx, rax; this
0x1800a942e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a9433  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a943a  jb      loc_1800A96AA
0x1800a9440  mov     edx, 11h
0x1800a9445  jmp     loc_1800A968C
0x1800a944a  movzx   r8d, [rsp+78h+arg_0]
0x1800a9453  test    r8b, r8b
0x1800a9456  jnz     loc_1800A94EC
0x1800a945c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9463  test    rcx, rcx
0x1800a9466  jnz     short loc_1800A94A9
0x1800a9468  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a946e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9475  mov     rcx, rax
0x1800a9478  test    rax, rax
0x1800a947b  jz      short loc_1800A949B
0x1800a947d  mov     rax, [rax]
0x1800a9480  mov     edx, 7F0h
0x1800a9485  mov     rax, [rax+8]
0x1800a9489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a948e  test    eax, eax
0x1800a9490  jz      short loc_1800A949B
0x1800a9492  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9499  jmp     short loc_1800A94A9
0x1800a949b  lea     rcx, qword_1800D6F70; this
0x1800a94a2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a94a9  cmp     byte ptr [rcx+8], 0
0x1800a94ad  mov     ebx, 0C00D36BEh
0x1800a94b2  jz      short loc_1800A94D5
0x1800a94b4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a94b9  cmp     [rax+7CCh], ebx
0x1800a94bf  jz      short loc_1800A94D5
0x1800a94c1  mov     r9d, ebx; int
0x1800a94c4  mov     r8d, 127h; int
0x1800a94ca  mov     rdx, rsi; char *
0x1800a94cd  mov     rcx, rax; this
0x1800a94d0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a94d5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a94dc  jb      loc_1800A96AA
0x1800a94e2  mov     edx, 12h
0x1800a94e7  jmp     loc_1800A968C
0x1800a94ec  xor     ecx, ecx
0x1800a94ee  cmp     ecx, 4
0x1800a94f1  jge     loc_1800A9605
0x1800a94f7  mov     edx, 80h
0x1800a94fc  lea     r9d, [rcx+1]
0x1800a9500  sar     edx, cl
0x1800a9502  test    r8b, dl
0x1800a9505  jnz     short loc_1800A950C
0x1800a9507  mov     ecx, r9d
0x1800a950a  jmp     short loc_1800A94EE
0x1800a950c  mov     rax, r8
0x1800a950f  mov     [r15], r9d
0x1800a9512  mov     [r14], rax
0x1800a9515  mov     esi, 1
0x1800a951a  cmp     esi, [r15]
0x1800a951d  jge     loc_1800A95F4
0x1800a9523  shl     rax, 8
0x1800a9527  lea     r9, [rsp+78h+arg_0]
0x1800a952f  mov     [r14], rax
0x1800a9532  mov     r8d, 1
0x1800a9538  mov     rax, [rbp+0]
0x1800a953c  mov     rcx, rbp
0x1800a953f  movsxd  rdx, esi
0x1800a9542  add     rdx, r12
0x1800a9545  mov     rax, [rax]
0x1800a9548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a954d  mov     ebx, eax
0x1800a954f  test    eax, eax
0x1800a9551  js      short loc_1800A9565
0x1800a9553  movzx   eax, [rsp+78h+arg_0]
0x1800a955b  or      [r14], rax
0x1800a955e  mov     rax, [r14]
0x1800a9561  inc     esi
0x1800a9563  jmp     short loc_1800A951A
0x1800a9565  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a956c  test    rcx, rcx
0x1800a956f  jnz     short loc_1800A95B2
0x1800a9571  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a9577  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a957e  mov     rcx, rax
0x1800a9581  test    rax, rax
0x1800a9584  jz      short loc_1800A95A4
0x1800a9586  mov     rax, [rax]
0x1800a9589  mov     edx, 7F0h
0x1800a958e  mov     rax, [rax+8]
0x1800a9592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9597  test    eax, eax
0x1800a9599  jz      short loc_1800A95A4
0x1800a959b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a95a2  jmp     short loc_1800A95B2
0x1800a95a4  lea     rcx, qword_1800D6F70; this
0x1800a95ab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a95b2  cmp     byte ptr [rcx+8], 0
0x1800a95b6  jz      short loc_1800A95DD
0x1800a95b8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a95bd  cmp     [rax+7CCh], ebx
0x1800a95c3  jz      short loc_1800A95DD
0x1800a95c5  mov     r9d, ebx; int
0x1800a95c8  lea     rdx, aMkvparserReadi; "mkvparser::ReadID"
0x1800a95cf  mov     r8d, 141h; int
0x1800a95d5  mov     rcx, rax; this
0x1800a95d8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a95dd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a95e4  jb      loc_1800A96AA
0x1800a95ea  mov     edx, 14h
0x1800a95ef  jmp     loc_1800A968C
0x1800a95f4  lea     rcx, [rsp+78h+var_48]; this
0x1800a95f9  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a95fe  xor     eax, eax
0x1800a9600  jmp     loc_1800A96B6
0x1800a9605  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a960c  test    rcx, rcx
0x1800a960f  jnz     short loc_1800A9652
0x1800a9611  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a9617  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a961e  mov     rcx, rax
0x1800a9621  test    rax, rax
0x1800a9624  jz      short loc_1800A9644
0x1800a9626  mov     rax, [rax]
0x1800a9629  mov     edx, 7F0h
0x1800a962e  mov     rax, [rax+8]
0x1800a9632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9637  test    eax, eax
0x1800a9639  jz      short loc_1800A9644
0x1800a963b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9642  jmp     short loc_1800A9652
0x1800a9644  lea     rcx, qword_1800D6F70; this
0x1800a964b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9652  cmp     byte ptr [rcx+8], 0
0x1800a9656  mov     ebx, 0C00D36BEh
0x1800a965b  jz      short loc_1800A967E
0x1800a965d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a9662  cmp     [rax+7CCh], ebx
0x1800a9668  jz      short loc_1800A967E
0x1800a966a  mov     r9d, ebx; int
0x1800a966d  mov     r8d, 139h; int
0x1800a9673  mov     rdx, rsi; char *
0x1800a9676  mov     rcx, rax; this
0x1800a9679  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a967e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a9685  jb      short loc_1800A96AA
0x1800a9687  mov     edx, 13h
0x1800a968c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9693  lea     r8, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids
0x1800a969a  xor     r9d, r9d
0x1800a969d  mov     [rsp+78h+var_58], ebx
0x1800a96a1  mov     rcx, [rcx+10h]
0x1800a96a5  call    WPP_SF_qD
0x1800a96aa  lea     rcx, [rsp+78h+var_48]; this
0x1800a96af  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a96b4  mov     eax, ebx
0x1800a96b6  add     rsp, 48h
0x1800a96ba  pop     r15
0x1800a96bc  pop     r14
0x1800a96be  pop     r12
0x1800a96c0  pop     rsi
0x1800a96c1  pop     rbp
0x1800a96c2  pop     rbx
0x1800a96c3  retn
```
