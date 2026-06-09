# MkvMfSourceLib::MkvMfSource::Command::OnSeek(void)

- ea: `0x18001789c`
- end: `0x180017b8a`
- name: `?OnSeek@Command@MkvMfSource@MkvMfSourceLib@@QEBAJXZ`
- size: `750`
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
- `0x18001789c`
- `0x180017b90`
- `0x18001895c`
- `0x180019320`
- `0x180021b9c`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001795e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017a07`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017aae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001795e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017a07`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017aae`

## string_xrefs

- `0x1800178c3`: `MkvMfSourceLib::MkvMfSource::Command::OnSeek`
- `0x1800179c1`: `MkvMfSourceLib::MkvMfSource::Command::OnSeek`
- `0x180017a6a`: `MkvMfSourceLib::MkvMfSource::Command::OnSeek`
- `0x180017b11`: `MkvMfSourceLib::MkvMfSource::Command::OnSeek`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MkvMfSourceLib::MkvMfSource::Command::OnSeek(MkvMfSourceLib::MkvMfSource::Command *this)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v3; // ebx
  __int64 v4; // rdx
  int started; // ebx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  _BYTE v25[8]; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v26[16]; // [rsp+38h] [rbp-20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v25,
    "MkvMfSourceLib::MkvMfSource::Command::OnSeek",
    3559);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 2) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 296LL))(*((_QWORD *)this + 2));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 2) + 280LL))(
                                                            *((_QWORD *)this + 2),
                                                            v26);
    *((_DWORD *)ThreadRelativeContext + 504) = v3;
  }
  if ( *(_BYTE *)(*((_QWORD *)this + 1) + 592LL) )
  {
    started = MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams(this, 100LL * *((_QWORD *)this + 5));
    if ( started < 0 )
    {
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
        CallStackTracing::s_wpInstance = v16;
        if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
        {
          v15 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
        if ( *((_DWORD *)v17 + 499) != started )
          CallStackContext::TraceFailure(v17, "MkvMfSourceLib::MkvMfSource::Command::OnSeek", 3578, started);
      }
      if ( !g_wppLevels )
        goto LABEL_39;
      v11 = 228;
      goto LABEL_38;
    }
  }
  else
  {
    started = MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek(this);
    if ( started < 0 )
    {
      v8 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v6, v7);
        CallStackTracing::s_wpInstance = v9;
        if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
        {
          v8 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v8 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v8 + 8) )
      {
        v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
        if ( *((_DWORD *)v10 + 499) != started )
          CallStackContext::TraceFailure(v10, "MkvMfSourceLib::MkvMfSource::Command::OnSeek", 3574, started);
      }
      if ( !g_wppLevels )
        goto LABEL_39;
      v11 = 227;
LABEL_38:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
        this,
        started);
LABEL_39:
      MkvMfSourceLib::MkvMfSource::Error(*((MkvMfSourceLib::MkvMfSource **)this + 1), L"Seek error.", started);
      goto LABEL_40;
    }
  }
  started = MkvMfSourceLib::MkvMfSource::Command::OnSeekComplete(this);
  if ( started < 0 )
  {
    v21 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
      CallStackTracing::s_wpInstance = v22;
      if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
      {
        v21 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v21 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v21 + 8) )
    {
      v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
      if ( *((_DWORD *)v23 + 499) != started )
        CallStackContext::TraceFailure(v23, "MkvMfSourceLib::MkvMfSource::Command::OnSeek", 3581, started);
    }
    if ( !g_wppLevels )
      goto LABEL_39;
    v11 = 229;
    goto LABEL_38;
  }
LABEL_40:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v25);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18001789c  mov     [rsp+arg_8], rbx
0x1800178a1  mov     [rsp+arg_10], rsi
0x1800178a6  push    rdi
0x1800178a7  sub     rsp, 50h
0x1800178ab  mov     rax, cs:__security_cookie
0x1800178b2  xor     rax, rsp
0x1800178b5  mov     [rsp+58h+var_10], rax
0x1800178ba  mov     rsi, rcx
0x1800178bd  mov     r8d, 0DE7h; int
0x1800178c3  lea     rdx, aMkvmfsourcelib_88; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x1800178ca  lea     rcx, [rsp+58h+var_28]; this
0x1800178cf  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800178d4  nop
0x1800178d5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800178dc  cmp     byte ptr [rcx+8], 0
0x1800178e0  jz      short loc_18001792F
0x1800178e2  cmp     qword ptr [rsi+10h], 0
0x1800178e7  jz      short loc_18001792F
0x1800178e9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800178ee  mov     rdi, rax
0x1800178f1  mov     rcx, [rsi+10h]
0x1800178f5  mov     rdx, [rcx]
0x1800178f8  mov     rax, [rdx+128h]
0x1800178ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017904  mov     ebx, eax
0x180017906  mov     rcx, [rsi+10h]
0x18001790a  mov     rdx, [rcx]
0x18001790d  mov     rax, [rdx+118h]
0x180017914  lea     rdx, [rsp+58h+var_20]
0x180017919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001791e  movups  xmm0, xmmword ptr [rax]
0x180017921  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180017929  mov     [rdi+7E0h], ebx
0x18001792f  mov     rax, [rsi+8]
0x180017933  mov     rcx, rsi; this
0x180017936  cmp     byte ptr [rax+250h], 0
0x18001793d  jnz     loc_1800179E7
0x180017943  call    ?OnStartNoSeek@Command@MkvMfSource@MkvMfSourceLib@@AEBAJXZ; MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek(void)
0x180017948  mov     ebx, eax
0x18001794a  test    eax, eax
0x18001794c  jns     loc_180017A90
0x180017952  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017959  test    rcx, rcx
0x18001795c  jnz     short loc_1800179A5
0x18001795e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180017965  nop     dword ptr [rax+rax+00h]
0x18001796a  mov     rcx, rax
0x18001796d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180017974  test    rax, rax
0x180017977  jz      short loc_180017997
0x180017979  mov     rax, [rax]
0x18001797c  mov     edx, 7F0h
0x180017981  mov     rax, [rax+8]
0x180017985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001798a  test    eax, eax
0x18001798c  jz      short loc_180017997
0x18001798e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017995  jmp     short loc_1800179A5
0x180017997  lea     rcx, qword_1800DBF70; this
0x18001799e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800179a5  cmp     byte ptr [rcx+8], 0
0x1800179a9  jz      short loc_1800179D0
0x1800179ab  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800179b0  cmp     [rax+7CCh], ebx
0x1800179b6  jz      short loc_1800179D0
0x1800179b8  mov     r9d, ebx; int
0x1800179bb  mov     r8d, 0DF6h; int
0x1800179c1  lea     rdx, aMkvmfsourcelib_88; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x1800179c8  mov     rcx, rax; this
0x1800179cb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800179d0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800179d7  jb      loc_180017B4C
0x1800179dd  mov     edx, 0E3h
0x1800179e2  jmp     loc_180017B2E
0x1800179e7  imul    rdx, [rsi+28h], 64h ; 'd'; __int64
0x1800179ec  call    ?OnStartInitStreams@Command@MkvMfSource@MkvMfSourceLib@@AEBAJ_J@Z; MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams(__int64)
0x1800179f1  mov     ebx, eax
0x1800179f3  test    eax, eax
0x1800179f5  jns     loc_180017A90
0x1800179fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017a02  test    rcx, rcx
0x180017a05  jnz     short loc_180017A4E
0x180017a07  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180017a0e  nop     dword ptr [rax+rax+00h]
0x180017a13  mov     rcx, rax
0x180017a16  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180017a1d  test    rax, rax
0x180017a20  jz      short loc_180017A40
0x180017a22  mov     rax, [rax]
0x180017a25  mov     edx, 7F0h
0x180017a2a  mov     rax, [rax+8]
0x180017a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a33  test    eax, eax
0x180017a35  jz      short loc_180017A40
0x180017a37  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017a3e  jmp     short loc_180017A4E
0x180017a40  lea     rcx, qword_1800DBF70; this
0x180017a47  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180017a4e  cmp     byte ptr [rcx+8], 0
0x180017a52  jz      short loc_180017A79
0x180017a54  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180017a59  cmp     [rax+7CCh], ebx
0x180017a5f  jz      short loc_180017A79
0x180017a61  mov     r9d, ebx; int
0x180017a64  mov     r8d, 0DFAh; int
0x180017a6a  lea     rdx, aMkvmfsourcelib_88; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180017a71  mov     rcx, rax; this
0x180017a74  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180017a79  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180017a80  jb      loc_180017B4C
0x180017a86  mov     edx, 0E4h
0x180017a8b  jmp     loc_180017B2E
0x180017a90  mov     rcx, rsi; this
0x180017a93  call    ?OnSeekComplete@Command@MkvMfSource@MkvMfSourceLib@@AEBAJXZ; MkvMfSourceLib::MkvMfSource::Command::OnSeekComplete(void)
0x180017a98  mov     ebx, eax
0x180017a9a  test    eax, eax
0x180017a9c  jns     loc_180017B60
0x180017aa2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017aa9  test    rcx, rcx
0x180017aac  jnz     short loc_180017AF5
0x180017aae  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180017ab5  nop     dword ptr [rax+rax+00h]
0x180017aba  mov     rcx, rax
0x180017abd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180017ac4  test    rax, rax
0x180017ac7  jz      short loc_180017AE7
0x180017ac9  mov     rax, [rax]
0x180017acc  mov     edx, 7F0h
0x180017ad1  mov     rax, [rax+8]
0x180017ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ada  test    eax, eax
0x180017adc  jz      short loc_180017AE7
0x180017ade  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017ae5  jmp     short loc_180017AF5
0x180017ae7  lea     rcx, qword_1800DBF70; this
0x180017aee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180017af5  cmp     byte ptr [rcx+8], 0
0x180017af9  jz      short loc_180017B20
0x180017afb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180017b00  cmp     [rax+7CCh], ebx
0x180017b06  jz      short loc_180017B20
0x180017b08  mov     r9d, ebx; int
0x180017b0b  mov     r8d, 0DFDh; int
0x180017b11  lea     rdx, aMkvmfsourcelib_88; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180017b18  mov     rcx, rax; this
0x180017b1b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180017b20  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180017b27  jb      short loc_180017B4C
0x180017b29  mov     edx, 0E5h
0x180017b2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b35  mov     [rsp+58h+var_38], ebx
0x180017b39  mov     r9, rsi
0x180017b3c  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180017b43  mov     rcx, [rcx+10h]
0x180017b47  call    WPP_SF_qD
0x180017b4c  mov     r8d, ebx; int
0x180017b4f  lea     rdx, aSeekError; "Seek error."
0x180017b56  mov     rcx, [rsi+8]; this
0x180017b5a  call    ?Error@MkvMfSource@MkvMfSourceLib@@AEAAJPEBGJ@Z; MkvMfSourceLib::MkvMfSource::Error(ushort const *,long)
0x180017b5f  nop
0x180017b60  lea     rcx, [rsp+58h+var_28]; this
0x180017b65  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180017b6a  mov     eax, ebx
0x180017b6c  mov     rcx, [rsp+58h+var_10]
0x180017b71  xor     rcx, rsp; StackCookie
0x180017b74  call    __security_check_cookie
0x180017b79  mov     rbx, [rsp+58h+arg_8]
0x180017b7e  mov     rsi, [rsp+58h+arg_10]
0x180017b83  add     rsp, 50h
0x180017b87  pop     rdi
0x180017b88  retn
```
