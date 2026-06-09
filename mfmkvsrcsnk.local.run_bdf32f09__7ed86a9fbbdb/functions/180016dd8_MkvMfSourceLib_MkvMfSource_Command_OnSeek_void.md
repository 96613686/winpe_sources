# MkvMfSourceLib::MkvMfSource::Command::OnSeek(void)

- ea: `0x180016dd8`
- end: `0x1800170b3`
- name: `?OnSeek@Command@MkvMfSource@MkvMfSourceLib@@QEBAJXZ`
- size: `731`
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
- `0x180016dd8`
- `0x1800170bc`
- `0x180017e3c`
- `0x1800187d4`
- `0x180020d84`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016e9a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016f3d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016fde`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016e9a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016f3d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016fde`

## string_xrefs

- `0x180016dff`: `MkvMfSourceLib::MkvMfSource::Command::OnSeek`
- `0x180016ef7`: `MkvMfSourceLib::MkvMfSource::Command::OnSeek`
- `0x180016f9a`: `MkvMfSourceLib::MkvMfSource::Command::OnSeek`
- `0x18001703b`: `MkvMfSourceLib::MkvMfSource::Command::OnSeek`

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
          v15 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v8 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v21 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x180016dd8  mov     [rsp+arg_8], rbx
0x180016ddd  mov     [rsp+arg_10], rsi
0x180016de2  push    rdi
0x180016de3  sub     rsp, 50h
0x180016de7  mov     rax, cs:__security_cookie
0x180016dee  xor     rax, rsp
0x180016df1  mov     [rsp+58h+var_10], rax
0x180016df6  mov     rsi, rcx
0x180016df9  mov     r8d, 0DE7h; int
0x180016dff  lea     rdx, aMkvmfsourcelib_88; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180016e06  lea     rcx, [rsp+58h+var_28]; this
0x180016e0b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180016e10  nop
0x180016e11  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180016e18  cmp     byte ptr [rcx+8], 0
0x180016e1c  jz      short loc_180016E6B
0x180016e1e  cmp     qword ptr [rsi+10h], 0
0x180016e23  jz      short loc_180016E6B
0x180016e25  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180016e2a  mov     rdi, rax
0x180016e2d  mov     rcx, [rsi+10h]
0x180016e31  mov     rdx, [rcx]
0x180016e34  mov     rax, [rdx+128h]
0x180016e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e40  mov     ebx, eax
0x180016e42  mov     rcx, [rsi+10h]
0x180016e46  mov     rdx, [rcx]
0x180016e49  mov     rax, [rdx+118h]
0x180016e50  lea     rdx, [rsp+58h+var_20]
0x180016e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e5a  movups  xmm0, xmmword ptr [rax]
0x180016e5d  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180016e65  mov     [rdi+7E0h], ebx
0x180016e6b  mov     rax, [rsi+8]
0x180016e6f  mov     rcx, rsi; this
0x180016e72  cmp     byte ptr [rax+250h], 0
0x180016e79  jnz     loc_180016F1D
0x180016e7f  call    ?OnStartNoSeek@Command@MkvMfSource@MkvMfSourceLib@@AEBAJXZ; MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek(void)
0x180016e84  mov     ebx, eax
0x180016e86  test    eax, eax
0x180016e88  jns     loc_180016FC0
0x180016e8e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016e95  test    rcx, rcx
0x180016e98  jnz     short loc_180016EDB
0x180016e9a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180016ea0  mov     rcx, rax
0x180016ea3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180016eaa  test    rax, rax
0x180016ead  jz      short loc_180016ECD
0x180016eaf  mov     rax, [rax]
0x180016eb2  mov     edx, 7F0h
0x180016eb7  mov     rax, [rax+8]
0x180016ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ec0  test    eax, eax
0x180016ec2  jz      short loc_180016ECD
0x180016ec4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016ecb  jmp     short loc_180016EDB
0x180016ecd  lea     rcx, qword_1800D6F70; this
0x180016ed4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180016edb  cmp     byte ptr [rcx+8], 0
0x180016edf  jz      short loc_180016F06
0x180016ee1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180016ee6  cmp     [rax+7CCh], ebx
0x180016eec  jz      short loc_180016F06
0x180016eee  mov     r9d, ebx; int
0x180016ef1  mov     r8d, 0DF6h; int
0x180016ef7  lea     rdx, aMkvmfsourcelib_88; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180016efe  mov     rcx, rax; this
0x180016f01  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180016f06  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180016f0d  jb      loc_180017076
0x180016f13  mov     edx, 0E3h
0x180016f18  jmp     loc_180017058
0x180016f1d  imul    rdx, [rsi+28h], 64h ; 'd'; __int64
0x180016f22  call    ?OnStartInitStreams@Command@MkvMfSource@MkvMfSourceLib@@AEBAJ_J@Z; MkvMfSourceLib::MkvMfSource::Command::OnStartInitStreams(__int64)
0x180016f27  mov     ebx, eax
0x180016f29  test    eax, eax
0x180016f2b  jns     loc_180016FC0
0x180016f31  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016f38  test    rcx, rcx
0x180016f3b  jnz     short loc_180016F7E
0x180016f3d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180016f43  mov     rcx, rax
0x180016f46  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180016f4d  test    rax, rax
0x180016f50  jz      short loc_180016F70
0x180016f52  mov     rax, [rax]
0x180016f55  mov     edx, 7F0h
0x180016f5a  mov     rax, [rax+8]
0x180016f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f63  test    eax, eax
0x180016f65  jz      short loc_180016F70
0x180016f67  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016f6e  jmp     short loc_180016F7E
0x180016f70  lea     rcx, qword_1800D6F70; this
0x180016f77  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180016f7e  cmp     byte ptr [rcx+8], 0
0x180016f82  jz      short loc_180016FA9
0x180016f84  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180016f89  cmp     [rax+7CCh], ebx
0x180016f8f  jz      short loc_180016FA9
0x180016f91  mov     r9d, ebx; int
0x180016f94  mov     r8d, 0DFAh; int
0x180016f9a  lea     rdx, aMkvmfsourcelib_88; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180016fa1  mov     rcx, rax; this
0x180016fa4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180016fa9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180016fb0  jb      loc_180017076
0x180016fb6  mov     edx, 0E4h
0x180016fbb  jmp     loc_180017058
0x180016fc0  mov     rcx, rsi; this
0x180016fc3  call    ?OnSeekComplete@Command@MkvMfSource@MkvMfSourceLib@@AEBAJXZ; MkvMfSourceLib::MkvMfSource::Command::OnSeekComplete(void)
0x180016fc8  mov     ebx, eax
0x180016fca  test    eax, eax
0x180016fcc  jns     loc_18001708A
0x180016fd2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016fd9  test    rcx, rcx
0x180016fdc  jnz     short loc_18001701F
0x180016fde  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180016fe4  mov     rcx, rax
0x180016fe7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180016fee  test    rax, rax
0x180016ff1  jz      short loc_180017011
0x180016ff3  mov     rax, [rax]
0x180016ff6  mov     edx, 7F0h
0x180016ffb  mov     rax, [rax+8]
0x180016fff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017004  test    eax, eax
0x180017006  jz      short loc_180017011
0x180017008  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001700f  jmp     short loc_18001701F
0x180017011  lea     rcx, qword_1800D6F70; this
0x180017018  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001701f  cmp     byte ptr [rcx+8], 0
0x180017023  jz      short loc_18001704A
0x180017025  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001702a  cmp     [rax+7CCh], ebx
0x180017030  jz      short loc_18001704A
0x180017032  mov     r9d, ebx; int
0x180017035  mov     r8d, 0DFDh; int
0x18001703b  lea     rdx, aMkvmfsourcelib_88; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180017042  mov     rcx, rax; this
0x180017045  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001704a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180017051  jb      short loc_180017076
0x180017053  mov     edx, 0E5h
0x180017058  mov     rcx, cs:WPP_GLOBAL_Control
0x18001705f  mov     [rsp+58h+var_38], ebx
0x180017063  mov     r9, rsi
0x180017066  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18001706d  mov     rcx, [rcx+10h]
0x180017071  call    WPP_SF_qD
0x180017076  mov     r8d, ebx; int
0x180017079  lea     rdx, aSeekError; "Seek error."
0x180017080  mov     rcx, [rsi+8]; this
0x180017084  call    ?Error@MkvMfSource@MkvMfSourceLib@@AEAAJPEBGJ@Z; MkvMfSourceLib::MkvMfSource::Error(ushort const *,long)
0x180017089  nop
0x18001708a  lea     rcx, [rsp+58h+var_28]; this
0x18001708f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180017094  mov     eax, ebx
0x180017096  mov     rcx, [rsp+58h+var_10]
0x18001709b  xor     rcx, rsp; StackCookie
0x18001709e  call    __security_check_cookie
0x1800170a3  mov     rbx, [rsp+58h+arg_8]
0x1800170a8  mov     rsi, [rsp+58h+arg_10]
0x1800170ad  add     rsp, 50h
0x1800170b1  pop     rdi
0x1800170b2  retn
```
