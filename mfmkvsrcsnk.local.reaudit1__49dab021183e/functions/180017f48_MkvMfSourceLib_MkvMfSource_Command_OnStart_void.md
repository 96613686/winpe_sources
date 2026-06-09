# MkvMfSourceLib::MkvMfSource::Command::OnStart(void)

- ea: `0x180017f48`
- end: `0x180018259`
- name: `?OnStart@Command@MkvMfSource@MkvMfSourceLib@@QEAAJXZ`
- size: `785`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource::Command *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180015b5c`

## callees

- `0x180002400`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180011720`
- `0x180017f48`
- `0x180018260`
- `0x18001895c`
- `0x180019320`
- `0x180021b9c`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001802c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800180db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018184`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001802c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800180db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018184`

## string_xrefs

- `0x180017f69`: `MkvMfSourceLib::MkvMfSource::Command::OnStart`
- `0x18001808f`: `MkvMfSourceLib::MkvMfSource::Command::OnStart`
- `0x18001813e`: `MkvMfSourceLib::MkvMfSource::Command::OnStart`
- `0x1800181e7`: `MkvMfSourceLib::MkvMfSource::Command::OnStart`

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
          v9 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v16 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v22 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x180017f48  push    rbx
0x180017f4a  push    rbp
0x180017f4b  push    rsi
0x180017f4c  push    rdi
0x180017f4d  sub     rsp, 58h
0x180017f51  mov     rax, cs:__security_cookie
0x180017f58  xor     rax, rsp
0x180017f5b  mov     [rsp+78h+var_30], rax
0x180017f60  mov     rsi, rcx
0x180017f63  mov     r8d, 0DC0h; int
0x180017f69  lea     rdx, aMkvmfsourcelib_150; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180017f70  lea     rcx, [rsp+78h+var_48]; this
0x180017f75  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180017f7a  nop
0x180017f7b  xor     ebp, ebp
0x180017f7d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180017f84  cmp     [rcx+8], bpl
0x180017f88  jz      short loc_180017FDC
0x180017f8a  cmp     [rsi+10h], rbp
0x180017f8e  jz      short loc_180017FDC
0x180017f90  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180017f95  mov     rdi, rax
0x180017f98  mov     rdx, [rsi+10h]
0x180017f9c  mov     rcx, [rdx]
0x180017f9f  mov     rax, [rcx+128h]
0x180017fa6  mov     rcx, rdx
0x180017fa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fae  mov     ebx, eax
0x180017fb0  mov     r8, [rsi+10h]
0x180017fb4  mov     rcx, [r8]
0x180017fb7  mov     rax, [rcx+118h]
0x180017fbe  lea     rdx, [rsp+78h+var_40]
0x180017fc3  mov     rcx, r8
0x180017fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fcb  movups  xmm0, xmmword ptr [rax]
0x180017fce  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180017fd6  mov     [rdi+7E0h], ebx
0x180017fdc  mov     ecx, 14h
0x180017fe1  cmp     [rsi+20h], bp
0x180017fe5  jnz     short loc_180017FEF
0x180017fe7  mov     [rsi+20h], cx
0x180017feb  mov     [rsi+28h], rbp
0x180017fef  imul    rdx, [rsi+28h], 64h ; 'd'; __int64
0x180017ff4  test    rdx, rdx
0x180017ff7  jz      loc_1800180B5
0x180017ffd  mov     rax, [rsi+8]
0x180018001  cmp     [rax+250h], bpl
0x180018008  jz      loc_1800180B5
0x18001800e  mov     rcx, rsi; this
0x180018011  call    ?OnStartInitStreams@Command@MkvMfSource@MkvMfSourceLib@@AEBAJ_J@Z; MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams(__int64)
0x180018016  mov     ebx, eax
0x180018018  test    eax, eax
0x18001801a  jns     loc_180018164
0x180018020  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018027  test    rcx, rcx
0x18001802a  jnz     short loc_180018073
0x18001802c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180018033  nop     dword ptr [rax+rax+00h]
0x180018038  mov     rcx, rax
0x18001803b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180018042  test    rax, rax
0x180018045  jz      short loc_180018065
0x180018047  mov     rax, [rax]
0x18001804a  mov     edx, 7F0h
0x18001804f  mov     rax, [rax+8]
0x180018053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018058  test    eax, eax
0x18001805a  jz      short loc_180018065
0x18001805c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018063  jmp     short loc_180018073
0x180018065  lea     rcx, qword_1800DBF70; this
0x18001806c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180018073  cmp     [rcx+8], bpl
0x180018077  jz      short loc_18001809E
0x180018079  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001807e  cmp     [rax+7CCh], ebx
0x180018084  jz      short loc_18001809E
0x180018086  mov     r9d, ebx; int
0x180018089  mov     r8d, 0DD7h; int
0x18001808f  lea     rdx, aMkvmfsourcelib_150; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180018096  mov     rcx, rax; this
0x180018099  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001809e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800180a5  jb      loc_180018222
0x1800180ab  mov     edx, 0E1h
0x1800180b0  jmp     loc_180018204
0x1800180b5  mov     [rsi+20h], cx
0x1800180b9  mov     [rsi+28h], rbp
0x1800180bd  mov     rcx, rsi; this
0x1800180c0  call    ?OnStartNoSeek@Command@MkvMfSource@MkvMfSourceLib@@AEBAJXZ; MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek(void)
0x1800180c5  mov     ebx, eax
0x1800180c7  test    eax, eax
0x1800180c9  jns     loc_180018164
0x1800180cf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800180d6  test    rcx, rcx
0x1800180d9  jnz     short loc_180018122
0x1800180db  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800180e2  nop     dword ptr [rax+rax+00h]
0x1800180e7  mov     rcx, rax
0x1800180ea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800180f1  test    rax, rax
0x1800180f4  jz      short loc_180018114
0x1800180f6  mov     rax, [rax]
0x1800180f9  mov     edx, 7F0h
0x1800180fe  mov     rax, [rax+8]
0x180018102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018107  test    eax, eax
0x180018109  jz      short loc_180018114
0x18001810b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018112  jmp     short loc_180018122
0x180018114  lea     rcx, qword_1800DBF70; this
0x18001811b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180018122  cmp     [rcx+8], bpl
0x180018126  jz      short loc_18001814D
0x180018128  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001812d  cmp     [rax+7CCh], ebx
0x180018133  jz      short loc_18001814D
0x180018135  mov     r9d, ebx; int
0x180018138  mov     r8d, 0DD3h; int
0x18001813e  lea     rdx, aMkvmfsourcelib_150; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180018145  mov     rcx, rax; this
0x180018148  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001814d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180018154  jb      loc_180018222
0x18001815a  mov     edx, 0E0h
0x18001815f  jmp     loc_180018204
0x180018164  xor     edx, edx; bool
0x180018166  mov     rcx, rsi; this
0x180018169  call    ?OnStartComplete@Command@MkvMfSource@MkvMfSourceLib@@AEBAJ_N@Z; MkvMfSourceLib::MkvMfSource::Command::OnStartComplete(bool)
0x18001816e  mov     ebx, eax
0x180018170  test    eax, eax
0x180018172  jns     loc_180018236
0x180018178  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001817f  test    rcx, rcx
0x180018182  jnz     short loc_1800181CB
0x180018184  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001818b  nop     dword ptr [rax+rax+00h]
0x180018190  mov     rcx, rax
0x180018193  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001819a  test    rax, rax
0x18001819d  jz      short loc_1800181BD
0x18001819f  mov     rax, [rax]
0x1800181a2  mov     edx, 7F0h
0x1800181a7  mov     rax, [rax+8]
0x1800181ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181b0  test    eax, eax
0x1800181b2  jz      short loc_1800181BD
0x1800181b4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800181bb  jmp     short loc_1800181CB
0x1800181bd  lea     rcx, qword_1800DBF70; this
0x1800181c4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800181cb  cmp     [rcx+8], bpl
0x1800181cf  jz      short loc_1800181F6
0x1800181d1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800181d6  cmp     [rax+7CCh], ebx
0x1800181dc  jz      short loc_1800181F6
0x1800181de  mov     r9d, ebx; int
0x1800181e1  mov     r8d, 0DDAh; int
0x1800181e7  lea     rdx, aMkvmfsourcelib_150; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x1800181ee  mov     rcx, rax; this
0x1800181f1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800181f6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800181fd  jb      short loc_180018222
0x1800181ff  mov     edx, 0E2h
0x180018204  mov     rcx, cs:WPP_GLOBAL_Control
0x18001820b  mov     [rsp+78h+var_58], ebx
0x18001820f  mov     r9, rsi
0x180018212  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180018219  mov     rcx, [rcx+10h]
0x18001821d  call    WPP_SF_qD
0x180018222  mov     r8d, ebx; int
0x180018225  lea     rdx, aErrorStartingS; "Error starting source."
0x18001822c  mov     rcx, [rsi+8]; this
0x180018230  call    ?Error@MkvMfSource@MkvMfSourceLib@@AEAAJPEBGJ@Z; MkvMfSourceLib::MkvMfSource::Error(ushort const *,long)
0x180018235  nop
0x180018236  lea     rcx, [rsp+78h+var_48]; this
0x18001823b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180018240  mov     eax, ebx
0x180018242  mov     rcx, [rsp+78h+var_30]
0x180018247  xor     rcx, rsp; StackCookie
0x18001824a  call    __security_check_cookie
0x18001824f  add     rsp, 58h
0x180018253  pop     rdi
0x180018254  pop     rsi
0x180018255  pop     rbp
0x180018256  pop     rbx
0x180018257  retn
```
