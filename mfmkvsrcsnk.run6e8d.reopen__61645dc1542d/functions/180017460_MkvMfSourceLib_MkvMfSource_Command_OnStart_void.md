# MkvMfSourceLib::MkvMfSource::Command::OnStart(void)

- ea: `0x180017460`
- end: `0x18001775e`
- name: `?OnStart@Command@MkvMfSource@MkvMfSourceLib@@QEAAJXZ`
- size: `766`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource::Command *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180015154`

## callees

- `0x1800023e0`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180010fd0`
- `0x180017460`
- `0x180017764`
- `0x180017e3c`
- `0x1800187d4`
- `0x180020d84`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017544`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800175ed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017690`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017544`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800175ed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017690`

## string_xrefs

- `0x180017481`: `MkvMfSourceLib::MkvMfSource::Command::OnStart`
- `0x1800175a1`: `MkvMfSourceLib::MkvMfSource::Command::OnStart`
- `0x18001764a`: `MkvMfSourceLib::MkvMfSource::Command::OnStart`
- `0x1800176ed`: `MkvMfSourceLib::MkvMfSource::Command::OnStart`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MkvMfSourceLib::MkvMfSource::Command::OnStart(MkvMfSourceLib::MkvMfSource::Command *this)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // rdx
  int started; // ebx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  _BYTE v26[8]; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v27[16]; // [rsp+38h] [rbp-40h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v26,
    "MkvMfSourceLib::MkvMfSource::Command::OnStart",
    3520);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 2) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 296LL))(*((_QWORD *)this + 2));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 2) + 280LL))(
                                                            *((_QWORD *)this + 2),
                                                            v27);
    *((_DWORD *)ThreadRelativeContext + 504) = v3;
  }
  if ( !*((_WORD *)this + 16) )
  {
    *((_WORD *)this + 16) = 20;
    *((_QWORD *)this + 5) = 0;
  }
  v4 = 100LL * *((_QWORD *)this + 5);
  if ( v4 && *(_BYTE *)(*((_QWORD *)this + 1) + 592LL) )
  {
    started = MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams(this, v4);
    if ( started < 0 )
    {
      v9 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5, v7, v8);
        CallStackTracing::s_wpInstance = v10;
        if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
        {
          v9 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v9 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v9 + 8) )
      {
        v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
        if ( *((_DWORD *)v11 + 499) != started )
          CallStackContext::TraceFailure(v11, "MkvMfSourceLib::MkvMfSource::Command::OnStart", 3543, started);
      }
      if ( !g_wppLevels )
        goto LABEL_42;
      v12 = 225;
LABEL_41:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
        this,
        started);
LABEL_42:
      MkvMfSourceLib::MkvMfSource::Error(
        *((MkvMfSourceLib::MkvMfSource **)this + 1),
        L"Error starting source.",
        started);
      goto LABEL_43;
    }
  }
  else
  {
    *((_WORD *)this + 16) = 20;
    *((_QWORD *)this + 5) = 0;
    started = MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek(this);
    if ( started < 0 )
    {
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14, v15);
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
      if ( *((_BYTE *)v16 + 8) )
      {
        v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
        if ( *((_DWORD *)v18 + 499) != started )
          CallStackContext::TraceFailure(v18, "MkvMfSourceLib::MkvMfSource::Command::OnStart", 3539, started);
      }
      if ( !g_wppLevels )
        goto LABEL_42;
      v12 = 224;
      goto LABEL_41;
    }
  }
  started = MkvMfSourceLib::MkvMfSource::Command::OnStartComplete(this, 0);
  if ( started < 0 )
  {
    v22 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20, v21);
      CallStackTracing::s_wpInstance = v23;
      if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
      {
        v22 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v22 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v22 + 8) )
    {
      v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
      if ( *((_DWORD *)v24 + 499) != started )
        CallStackContext::TraceFailure(v24, "MkvMfSourceLib::MkvMfSource::Command::OnStart", 3546, started);
    }
    if ( !g_wppLevels )
      goto LABEL_42;
    v12 = 226;
    goto LABEL_41;
  }
LABEL_43:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v26);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x180017460  push    rbx
0x180017462  push    rbp
0x180017463  push    rsi
0x180017464  push    rdi
0x180017465  sub     rsp, 58h
0x180017469  mov     rax, cs:__security_cookie
0x180017470  xor     rax, rsp
0x180017473  mov     [rsp+78h+var_30], rax
0x180017478  mov     rsi, rcx
0x18001747b  mov     r8d, 0DC0h; int
0x180017481  lea     rdx, aMkvmfsourcelib_150; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180017488  lea     rcx, [rsp+78h+var_48]; this
0x18001748d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180017492  nop
0x180017493  xor     ebp, ebp
0x180017495  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001749c  cmp     [rcx+8], bpl
0x1800174a0  jz      short loc_1800174F4
0x1800174a2  cmp     [rsi+10h], rbp
0x1800174a6  jz      short loc_1800174F4
0x1800174a8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800174ad  mov     rdi, rax
0x1800174b0  mov     rdx, [rsi+10h]
0x1800174b4  mov     rcx, [rdx]
0x1800174b7  mov     rax, [rcx+128h]
0x1800174be  mov     rcx, rdx
0x1800174c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174c6  mov     ebx, eax
0x1800174c8  mov     r8, [rsi+10h]
0x1800174cc  mov     rcx, [r8]
0x1800174cf  mov     rax, [rcx+118h]
0x1800174d6  lea     rdx, [rsp+78h+var_40]
0x1800174db  mov     rcx, r8
0x1800174de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174e3  movups  xmm0, xmmword ptr [rax]
0x1800174e6  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800174ee  mov     [rdi+7E0h], ebx
0x1800174f4  mov     ecx, 14h
0x1800174f9  cmp     [rsi+20h], bp
0x1800174fd  jnz     short loc_180017507
0x1800174ff  mov     [rsi+20h], cx
0x180017503  mov     [rsi+28h], rbp
0x180017507  imul    rdx, [rsi+28h], 64h ; 'd'; __int64
0x18001750c  test    rdx, rdx
0x18001750f  jz      loc_1800175C7
0x180017515  mov     rax, [rsi+8]
0x180017519  cmp     [rax+250h], bpl
0x180017520  jz      loc_1800175C7
0x180017526  mov     rcx, rsi; this
0x180017529  call    ?OnStartInitStreams@Command@MkvMfSource@MkvMfSourceLib@@AEBAJ_J@Z; MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams(__int64)
0x18001752e  mov     ebx, eax
0x180017530  test    eax, eax
0x180017532  jns     loc_180017670
0x180017538  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001753f  test    rcx, rcx
0x180017542  jnz     short loc_180017585
0x180017544  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001754a  mov     rcx, rax
0x18001754d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180017554  test    rax, rax
0x180017557  jz      short loc_180017577
0x180017559  mov     rax, [rax]
0x18001755c  mov     edx, 7F0h
0x180017561  mov     rax, [rax+8]
0x180017565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001756a  test    eax, eax
0x18001756c  jz      short loc_180017577
0x18001756e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017575  jmp     short loc_180017585
0x180017577  lea     rcx, qword_1800D6F70; this
0x18001757e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180017585  cmp     [rcx+8], bpl
0x180017589  jz      short loc_1800175B0
0x18001758b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180017590  cmp     [rax+7CCh], ebx
0x180017596  jz      short loc_1800175B0
0x180017598  mov     r9d, ebx; int
0x18001759b  mov     r8d, 0DD7h; int
0x1800175a1  lea     rdx, aMkvmfsourcelib_150; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x1800175a8  mov     rcx, rax; this
0x1800175ab  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800175b0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800175b7  jb      loc_180017728
0x1800175bd  mov     edx, 0E1h
0x1800175c2  jmp     loc_18001770A
0x1800175c7  mov     [rsi+20h], cx
0x1800175cb  mov     [rsi+28h], rbp
0x1800175cf  mov     rcx, rsi; this
0x1800175d2  call    ?OnStartNoSeek@Command@MkvMfSource@MkvMfSourceLib@@AEBAJXZ; MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek(void)
0x1800175d7  mov     ebx, eax
0x1800175d9  test    eax, eax
0x1800175db  jns     loc_180017670
0x1800175e1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800175e8  test    rcx, rcx
0x1800175eb  jnz     short loc_18001762E
0x1800175ed  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800175f3  mov     rcx, rax
0x1800175f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800175fd  test    rax, rax
0x180017600  jz      short loc_180017620
0x180017602  mov     rax, [rax]
0x180017605  mov     edx, 7F0h
0x18001760a  mov     rax, [rax+8]
0x18001760e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017613  test    eax, eax
0x180017615  jz      short loc_180017620
0x180017617  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001761e  jmp     short loc_18001762E
0x180017620  lea     rcx, qword_1800D6F70; this
0x180017627  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001762e  cmp     [rcx+8], bpl
0x180017632  jz      short loc_180017659
0x180017634  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180017639  cmp     [rax+7CCh], ebx
0x18001763f  jz      short loc_180017659
0x180017641  mov     r9d, ebx; int
0x180017644  mov     r8d, 0DD3h; int
0x18001764a  lea     rdx, aMkvmfsourcelib_150; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180017651  mov     rcx, rax; this
0x180017654  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180017659  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180017660  jb      loc_180017728
0x180017666  mov     edx, 0E0h
0x18001766b  jmp     loc_18001770A
0x180017670  xor     edx, edx; bool
0x180017672  mov     rcx, rsi; this
0x180017675  call    ?OnStartComplete@Command@MkvMfSource@MkvMfSourceLib@@AEBAJ_N@Z; MkvMfSourceLib::MkvMfSource::Command::OnStartComplete(bool)
0x18001767a  mov     ebx, eax
0x18001767c  test    eax, eax
0x18001767e  jns     loc_18001773C
0x180017684  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001768b  test    rcx, rcx
0x18001768e  jnz     short loc_1800176D1
0x180017690  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180017696  mov     rcx, rax
0x180017699  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800176a0  test    rax, rax
0x1800176a3  jz      short loc_1800176C3
0x1800176a5  mov     rax, [rax]
0x1800176a8  mov     edx, 7F0h
0x1800176ad  mov     rax, [rax+8]
0x1800176b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176b6  test    eax, eax
0x1800176b8  jz      short loc_1800176C3
0x1800176ba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800176c1  jmp     short loc_1800176D1
0x1800176c3  lea     rcx, qword_1800D6F70; this
0x1800176ca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800176d1  cmp     [rcx+8], bpl
0x1800176d5  jz      short loc_1800176FC
0x1800176d7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800176dc  cmp     [rax+7CCh], ebx
0x1800176e2  jz      short loc_1800176FC
0x1800176e4  mov     r9d, ebx; int
0x1800176e7  mov     r8d, 0DDAh; int
0x1800176ed  lea     rdx, aMkvmfsourcelib_150; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x1800176f4  mov     rcx, rax; this
0x1800176f7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800176fc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180017703  jb      short loc_180017728
0x180017705  mov     edx, 0E2h
0x18001770a  mov     rcx, cs:WPP_GLOBAL_Control
0x180017711  mov     [rsp+78h+var_58], ebx
0x180017715  mov     r9, rsi
0x180017718  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18001771f  mov     rcx, [rcx+10h]
0x180017723  call    WPP_SF_qD
0x180017728  mov     r8d, ebx; int
0x18001772b  lea     rdx, aErrorStartingS; "Error starting source."
0x180017732  mov     rcx, [rsi+8]; this
0x180017736  call    ?Error@MkvMfSource@MkvMfSourceLib@@AEAAJPEBGJ@Z; MkvMfSourceLib::MkvMfSource::Error(ushort const *,long)
0x18001773b  nop
0x18001773c  lea     rcx, [rsp+78h+var_48]; this
0x180017741  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180017746  mov     eax, ebx
0x180017748  mov     rcx, [rsp+78h+var_30]
0x18001774d  xor     rcx, rsp; StackCookie
0x180017750  call    __security_check_cookie
0x180017755  add     rsp, 58h
0x180017759  pop     rdi
0x18001775a  pop     rsi
0x18001775b  pop     rbp
0x18001775c  pop     rbx
0x18001775d  retn
```
