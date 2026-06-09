# mkvparser::ReadID(mkvparser::IMkvReader *,__int64,__int64 &,long &)

- ea: `0x1800adea8`
- end: `0x1800ae371`
- name: `?ReadID@mkvparser@@YAJPEAUIMkvReader@1@_JAEA_JAEAJ@Z`
- size: `1225`
- prototype: `__int64 __fastcall(mkvparser *__hidden this, struct mkvparser::IMkvReader *, __int64, __int64 *, int *)`
- caller_count: `25`
- callee_count: `7`
- tags: ``

## callers

- `0x180089abc`
- `0x18008a410`
- `0x18008ad30`
- `0x18008c320`
- `0x18008eef8`
- `0x1800905dc`
- `0x180091564`
- `0x180091b3c`
- `0x180091f68`
- `0x180092f5c`
- `0x180093bb4`
- `0x1800950f0`
- `0x180095a94`
- `0x18009970c`
- `0x18009bd54`
- `0x18009f9d4`
- `0x1800a0088`
- `0x1800a24c8`
- `0x1800a51ec`
- `0x1800a5fec`
- `0x1800a7120`
- `0x1800a79c4`
- `0x1800a8e30`
- `0x1800a9808`
- `0x1800aa9c0`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x1800adea8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800adef1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800adf90`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ae05f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ae102`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ae211`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ae2b7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800adef1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800adf90`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ae05f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ae102`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ae211`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ae2b7`

## string_xrefs

- `0x1800adeb9`: `mkvparser::ReadID`
- `0x1800ae26e`: `mkvparser::ReadID`

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
        v11 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v16 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v23 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v27 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids, 0, v13);
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
          v36 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      v40 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x1800adea8  push    rbx
0x1800adeaa  push    rbp
0x1800adeab  push    rsi
0x1800adeac  push    r12
0x1800adeae  push    r14
0x1800adeb0  push    r15
0x1800adeb2  sub     rsp, 48h
0x1800adeb6  mov     r14, r8
0x1800adeb9  lea     rsi, aMkvparserReadi; "mkvparser::ReadID"
0x1800adec0  mov     r12, rdx
0x1800adec3  mov     rbp, rcx
0x1800adec6  mov     rdx, rsi; char *
0x1800adec9  lea     rcx, [rsp+78h+var_48]; this
0x1800adece  mov     r8d, 116h; int
0x1800aded4  mov     r15, r9
0x1800aded7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800adedc  test    rbp, rbp
0x1800adedf  jnz     loc_1800ADF7B
0x1800adee5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adeec  test    rcx, rcx
0x1800adeef  jnz     short loc_1800ADF38
0x1800adef1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800adef8  nop     dword ptr [rax+rax+00h]
0x1800adefd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adf04  mov     rcx, rax
0x1800adf07  test    rax, rax
0x1800adf0a  jz      short loc_1800ADF2A
0x1800adf0c  mov     rax, [rax]
0x1800adf0f  mov     edx, 7F0h
0x1800adf14  mov     rax, [rax+8]
0x1800adf18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adf1d  test    eax, eax
0x1800adf1f  jz      short loc_1800ADF2A
0x1800adf21  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adf28  jmp     short loc_1800ADF38
0x1800adf2a  lea     rcx, qword_1800DBF70; this
0x1800adf31  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adf38  cmp     byte ptr [rcx+8], 0
0x1800adf3c  mov     ebx, 80070057h
0x1800adf41  jz      short loc_1800ADF64
0x1800adf43  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800adf48  cmp     [rax+7CCh], ebx
0x1800adf4e  jz      short loc_1800ADF64
0x1800adf50  mov     r9d, ebx; int
0x1800adf53  mov     r8d, 116h; int
0x1800adf59  mov     rdx, rsi; char *
0x1800adf5c  mov     rcx, rax; this
0x1800adf5f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800adf64  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800adf6b  jb      loc_1800AE356
0x1800adf71  mov     edx, 0Fh
0x1800adf76  jmp     loc_1800AE338
0x1800adf7b  test    r12, r12
0x1800adf7e  jns     loc_1800AE01A
0x1800adf84  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adf8b  test    rcx, rcx
0x1800adf8e  jnz     short loc_1800ADFD7
0x1800adf90  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800adf97  nop     dword ptr [rax+rax+00h]
0x1800adf9c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adfa3  mov     rcx, rax
0x1800adfa6  test    rax, rax
0x1800adfa9  jz      short loc_1800ADFC9
0x1800adfab  mov     rax, [rax]
0x1800adfae  mov     edx, 7F0h
0x1800adfb3  mov     rax, [rax+8]
0x1800adfb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adfbc  test    eax, eax
0x1800adfbe  jz      short loc_1800ADFC9
0x1800adfc0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adfc7  jmp     short loc_1800ADFD7
0x1800adfc9  lea     rcx, qword_1800DBF70; this
0x1800adfd0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800adfd7  cmp     byte ptr [rcx+8], 0
0x1800adfdb  mov     ebx, 80070057h
0x1800adfe0  jz      short loc_1800AE003
0x1800adfe2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800adfe7  cmp     [rax+7CCh], ebx
0x1800adfed  jz      short loc_1800AE003
0x1800adfef  mov     r9d, ebx; int
0x1800adff2  mov     r8d, 11Ah; int
0x1800adff8  mov     rdx, rsi; char *
0x1800adffb  mov     rcx, rax; this
0x1800adffe  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ae003  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ae00a  jb      loc_1800AE356
0x1800ae010  mov     edx, 10h
0x1800ae015  jmp     loc_1800AE338
0x1800ae01a  mov     dword ptr [r15], 1
0x1800ae021  lea     r9, [rsp+78h+arg_0]
0x1800ae029  mov     rax, [rbp+0]
0x1800ae02d  mov     r8d, 1
0x1800ae033  mov     rdx, r12
0x1800ae036  mov     [rsp+78h+arg_0], 0
0x1800ae03e  mov     rcx, rbp
0x1800ae041  mov     rax, [rax]
0x1800ae044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae049  mov     ebx, eax
0x1800ae04b  test    eax, eax
0x1800ae04d  jns     loc_1800AE0E4
0x1800ae053  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae05a  test    rcx, rcx
0x1800ae05d  jnz     short loc_1800AE0A6
0x1800ae05f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ae066  nop     dword ptr [rax+rax+00h]
0x1800ae06b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae072  mov     rcx, rax
0x1800ae075  test    rax, rax
0x1800ae078  jz      short loc_1800AE098
0x1800ae07a  mov     rax, [rax]
0x1800ae07d  mov     edx, 7F0h
0x1800ae082  mov     rax, [rax+8]
0x1800ae086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae08b  test    eax, eax
0x1800ae08d  jz      short loc_1800AE098
0x1800ae08f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae096  jmp     short loc_1800AE0A6
0x1800ae098  lea     rcx, qword_1800DBF70; this
0x1800ae09f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae0a6  cmp     byte ptr [rcx+8], 0
0x1800ae0aa  jz      short loc_1800AE0CD
0x1800ae0ac  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ae0b1  cmp     [rax+7CCh], ebx
0x1800ae0b7  jz      short loc_1800AE0CD
0x1800ae0b9  mov     r9d, ebx; int
0x1800ae0bc  mov     r8d, 123h; int
0x1800ae0c2  mov     rdx, rsi; char *
0x1800ae0c5  mov     rcx, rax; this
0x1800ae0c8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ae0cd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ae0d4  jb      loc_1800AE356
0x1800ae0da  mov     edx, 11h
0x1800ae0df  jmp     loc_1800AE338
0x1800ae0e4  movzx   r8d, [rsp+78h+arg_0]
0x1800ae0ed  test    r8b, r8b
0x1800ae0f0  jnz     loc_1800AE18C
0x1800ae0f6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae0fd  test    rcx, rcx
0x1800ae100  jnz     short loc_1800AE149
0x1800ae102  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ae109  nop     dword ptr [rax+rax+00h]
0x1800ae10e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae115  mov     rcx, rax
0x1800ae118  test    rax, rax
0x1800ae11b  jz      short loc_1800AE13B
0x1800ae11d  mov     rax, [rax]
0x1800ae120  mov     edx, 7F0h
0x1800ae125  mov     rax, [rax+8]
0x1800ae129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae12e  test    eax, eax
0x1800ae130  jz      short loc_1800AE13B
0x1800ae132  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae139  jmp     short loc_1800AE149
0x1800ae13b  lea     rcx, qword_1800DBF70; this
0x1800ae142  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae149  cmp     byte ptr [rcx+8], 0
0x1800ae14d  mov     ebx, 0C00D36BEh
0x1800ae152  jz      short loc_1800AE175
0x1800ae154  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ae159  cmp     [rax+7CCh], ebx
0x1800ae15f  jz      short loc_1800AE175
0x1800ae161  mov     r9d, ebx; int
0x1800ae164  mov     r8d, 127h; int
0x1800ae16a  mov     rdx, rsi; char *
0x1800ae16d  mov     rcx, rax; this
0x1800ae170  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ae175  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ae17c  jb      loc_1800AE356
0x1800ae182  mov     edx, 12h
0x1800ae187  jmp     loc_1800AE338
0x1800ae18c  xor     ecx, ecx
0x1800ae18e  cmp     ecx, 4
0x1800ae191  jge     loc_1800AE2AB
0x1800ae197  mov     edx, 80h
0x1800ae19c  lea     r9d, [rcx+1]
0x1800ae1a0  sar     edx, cl
0x1800ae1a2  test    r8b, dl
0x1800ae1a5  jnz     short loc_1800AE1AC
0x1800ae1a7  mov     ecx, r9d
0x1800ae1aa  jmp     short loc_1800AE18E
0x1800ae1ac  mov     rax, r8
0x1800ae1af  mov     [r15], r9d
0x1800ae1b2  mov     [r14], rax
0x1800ae1b5  mov     esi, 1
0x1800ae1ba  cmp     esi, [r15]
0x1800ae1bd  jge     loc_1800AE29A
0x1800ae1c3  shl     rax, 8
0x1800ae1c7  lea     r9, [rsp+78h+arg_0]
0x1800ae1cf  mov     [r14], rax
0x1800ae1d2  mov     r8d, 1
0x1800ae1d8  mov     rax, [rbp+0]
0x1800ae1dc  mov     rcx, rbp
0x1800ae1df  movsxd  rdx, esi
0x1800ae1e2  add     rdx, r12
0x1800ae1e5  mov     rax, [rax]
0x1800ae1e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae1ed  mov     ebx, eax
0x1800ae1ef  test    eax, eax
0x1800ae1f1  js      short loc_1800AE205
0x1800ae1f3  movzx   eax, [rsp+78h+arg_0]
0x1800ae1fb  or      [r14], rax
0x1800ae1fe  mov     rax, [r14]
0x1800ae201  inc     esi
0x1800ae203  jmp     short loc_1800AE1BA
0x1800ae205  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae20c  test    rcx, rcx
0x1800ae20f  jnz     short loc_1800AE258
0x1800ae211  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ae218  nop     dword ptr [rax+rax+00h]
0x1800ae21d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae224  mov     rcx, rax
0x1800ae227  test    rax, rax
0x1800ae22a  jz      short loc_1800AE24A
0x1800ae22c  mov     rax, [rax]
0x1800ae22f  mov     edx, 7F0h
0x1800ae234  mov     rax, [rax+8]
0x1800ae238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae23d  test    eax, eax
0x1800ae23f  jz      short loc_1800AE24A
0x1800ae241  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae248  jmp     short loc_1800AE258
0x1800ae24a  lea     rcx, qword_1800DBF70; this
0x1800ae251  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae258  cmp     byte ptr [rcx+8], 0
0x1800ae25c  jz      short loc_1800AE283
0x1800ae25e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ae263  cmp     [rax+7CCh], ebx
0x1800ae269  jz      short loc_1800AE283
0x1800ae26b  mov     r9d, ebx; int
0x1800ae26e  lea     rdx, aMkvparserReadi; "mkvparser::ReadID"
0x1800ae275  mov     r8d, 141h; int
0x1800ae27b  mov     rcx, rax; this
0x1800ae27e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ae283  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ae28a  jb      loc_1800AE356
0x1800ae290  mov     edx, 14h
0x1800ae295  jmp     loc_1800AE338
0x1800ae29a  lea     rcx, [rsp+78h+var_48]; this
0x1800ae29f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800ae2a4  xor     eax, eax
0x1800ae2a6  jmp     loc_1800AE362
0x1800ae2ab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae2b2  test    rcx, rcx
0x1800ae2b5  jnz     short loc_1800AE2FE
0x1800ae2b7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ae2be  nop     dword ptr [rax+rax+00h]
0x1800ae2c3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae2ca  mov     rcx, rax
0x1800ae2cd  test    rax, rax
0x1800ae2d0  jz      short loc_1800AE2F0
0x1800ae2d2  mov     rax, [rax]
0x1800ae2d5  mov     edx, 7F0h
0x1800ae2da  mov     rax, [rax+8]
0x1800ae2de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae2e3  test    eax, eax
0x1800ae2e5  jz      short loc_1800AE2F0
0x1800ae2e7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae2ee  jmp     short loc_1800AE2FE
0x1800ae2f0  lea     rcx, qword_1800DBF70; this
0x1800ae2f7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae2fe  cmp     byte ptr [rcx+8], 0
0x1800ae302  mov     ebx, 0C00D36BEh
0x1800ae307  jz      short loc_1800AE32A
0x1800ae309  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ae30e  cmp     [rax+7CCh], ebx
0x1800ae314  jz      short loc_1800AE32A
0x1800ae316  mov     r9d, ebx; int
0x1800ae319  mov     r8d, 139h; int
0x1800ae31f  mov     rdx, rsi; char *
0x1800ae322  mov     rcx, rax; this
0x1800ae325  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ae32a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ae331  jb      short loc_1800AE356
0x1800ae333  mov     edx, 13h
0x1800ae338  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae33f  lea     r8, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids
0x1800ae346  xor     r9d, r9d
0x1800ae349  mov     [rsp+78h+var_58], ebx
0x1800ae34d  mov     rcx, [rcx+10h]
0x1800ae351  call    WPP_SF_qD
0x1800ae356  lea     rcx, [rsp+78h+var_48]; this
0x1800ae35b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800ae360  mov     eax, ebx
0x1800ae362  add     rsp, 48h
0x1800ae366  pop     r15
0x1800ae368  pop     r14
0x1800ae36a  pop     r12
0x1800ae36c  pop     rsi
0x1800ae36d  pop     rbp
0x1800ae36e  pop     rbx
0x1800ae36f  retn
```
