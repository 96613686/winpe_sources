# MkvMfSourceLib::MkvMfSource::Command::OnRestart(void)

- ea: `0x180016ba0`
- end: `0x180016dcf`
- name: `?OnRestart@Command@MkvMfSource@MkvMfSourceLib@@QEAAJXZ`
- size: `559`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource::Command *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180015154`

## callees

- `0x1800023e0`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180010fd0`
- `0x180016ba0`
- `0x180017764`
- `0x1800187d4`
- `0x180020d84`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016c57`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016cfa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016c57`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016cfa`

## string_xrefs

- `0x180016bc7`: `MkvMfSourceLib::MkvMfSource::Command::OnRestart`
- `0x180016cb4`: `MkvMfSourceLib::MkvMfSource::Command::OnRestart`
- `0x180016d57`: `MkvMfSourceLib::MkvMfSource::Command::OnRestart`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MkvMfSourceLib::MkvMfSource::Command::OnRestart(MkvMfSourceLib::MkvMfSource::Command *this)
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
  _BYTE v19[8]; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v20[16]; // [rsp+38h] [rbp-20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v19,
    "MkvMfSourceLib::MkvMfSource::Command::OnRestart",
    3599);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 2) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 296LL))(*((_QWORD *)this + 2));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 2) + 280LL))(
                                                            *((_QWORD *)this + 2),
                                                            v20);
    *((_DWORD *)ThreadRelativeContext + 504) = v3;
  }
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
        CallStackContext::TraceFailure(v10, "MkvMfSourceLib::MkvMfSource::Command::OnRestart", 3599, started);
    }
    if ( !g_wppLevels )
      goto LABEL_27;
    v11 = 230;
LABEL_26:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, started);
LABEL_27:
    MkvMfSourceLib::MkvMfSource::Error(
      *((MkvMfSourceLib::MkvMfSource **)this + 1),
      L"Error restarting source.",
      started);
    goto LABEL_28;
  }
  started = MkvMfSourceLib::MkvMfSource::Command::OnStartComplete(this, 1);
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
        CallStackContext::TraceFailure(v17, "MkvMfSourceLib::MkvMfSource::Command::OnRestart", 3601, started);
    }
    if ( !g_wppLevels )
      goto LABEL_27;
    v11 = 231;
    goto LABEL_26;
  }
LABEL_28:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v19);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x180016ba0  mov     [rsp+arg_8], rbx
0x180016ba5  mov     [rsp+arg_10], rsi
0x180016baa  push    rdi
0x180016bab  sub     rsp, 50h
0x180016baf  mov     rax, cs:__security_cookie
0x180016bb6  xor     rax, rsp
0x180016bb9  mov     [rsp+58h+var_10], rax
0x180016bbe  mov     rsi, rcx
0x180016bc1  mov     r8d, 0E0Fh; int
0x180016bc7  lea     rdx, aMkvmfsourcelib_46; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180016bce  lea     rcx, [rsp+58h+var_28]; this
0x180016bd3  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180016bd8  nop
0x180016bd9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180016be0  cmp     byte ptr [rcx+8], 0
0x180016be4  jz      short loc_180016C39
0x180016be6  cmp     qword ptr [rsi+10h], 0
0x180016beb  jz      short loc_180016C39
0x180016bed  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180016bf2  mov     rdi, rax
0x180016bf5  mov     rdx, [rsi+10h]
0x180016bf9  mov     rcx, [rdx]
0x180016bfc  mov     rax, [rcx+128h]
0x180016c03  mov     rcx, rdx
0x180016c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c0b  mov     ebx, eax
0x180016c0d  mov     r8, [rsi+10h]
0x180016c11  mov     rcx, [r8]
0x180016c14  mov     rax, [rcx+118h]
0x180016c1b  lea     rdx, [rsp+58h+var_20]
0x180016c20  mov     rcx, r8
0x180016c23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c28  movups  xmm0, xmmword ptr [rax]
0x180016c2b  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180016c33  mov     [rdi+7E0h], ebx
0x180016c39  mov     rcx, rsi; this
0x180016c3c  call    ?OnStartNoSeek@Command@MkvMfSource@MkvMfSourceLib@@AEBAJXZ; MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek(void)
0x180016c41  mov     ebx, eax
0x180016c43  test    eax, eax
0x180016c45  jns     loc_180016CDA
0x180016c4b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016c52  test    rcx, rcx
0x180016c55  jnz     short loc_180016C98
0x180016c57  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180016c5d  mov     rcx, rax
0x180016c60  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180016c67  test    rax, rax
0x180016c6a  jz      short loc_180016C8A
0x180016c6c  mov     rax, [rax]
0x180016c6f  mov     edx, 7F0h
0x180016c74  mov     rax, [rax+8]
0x180016c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c7d  test    eax, eax
0x180016c7f  jz      short loc_180016C8A
0x180016c81  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016c88  jmp     short loc_180016C98
0x180016c8a  lea     rcx, qword_1800D6F70; this
0x180016c91  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180016c98  cmp     byte ptr [rcx+8], 0
0x180016c9c  jz      short loc_180016CC3
0x180016c9e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180016ca3  cmp     [rax+7CCh], ebx
0x180016ca9  jz      short loc_180016CC3
0x180016cab  mov     r9d, ebx; int
0x180016cae  mov     r8d, 0E0Fh; int
0x180016cb4  lea     rdx, aMkvmfsourcelib_46; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180016cbb  mov     rcx, rax; this
0x180016cbe  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180016cc3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180016cca  jb      loc_180016D92
0x180016cd0  mov     edx, 0E6h
0x180016cd5  jmp     loc_180016D74
0x180016cda  mov     dl, 1; bool
0x180016cdc  mov     rcx, rsi; this
0x180016cdf  call    ?OnStartComplete@Command@MkvMfSource@MkvMfSourceLib@@AEBAJ_N@Z; MkvMfSourceLib::MkvMfSource::Command::OnStartComplete(bool)
0x180016ce4  mov     ebx, eax
0x180016ce6  test    eax, eax
0x180016ce8  jns     loc_180016DA6
0x180016cee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016cf5  test    rcx, rcx
0x180016cf8  jnz     short loc_180016D3B
0x180016cfa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180016d00  mov     rcx, rax
0x180016d03  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180016d0a  test    rax, rax
0x180016d0d  jz      short loc_180016D2D
0x180016d0f  mov     rax, [rax]
0x180016d12  mov     edx, 7F0h
0x180016d17  mov     rax, [rax+8]
0x180016d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d20  test    eax, eax
0x180016d22  jz      short loc_180016D2D
0x180016d24  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016d2b  jmp     short loc_180016D3B
0x180016d2d  lea     rcx, qword_1800D6F70; this
0x180016d34  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180016d3b  cmp     byte ptr [rcx+8], 0
0x180016d3f  jz      short loc_180016D66
0x180016d41  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180016d46  cmp     [rax+7CCh], ebx
0x180016d4c  jz      short loc_180016D66
0x180016d4e  mov     r9d, ebx; int
0x180016d51  mov     r8d, 0E11h; int
0x180016d57  lea     rdx, aMkvmfsourcelib_46; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180016d5e  mov     rcx, rax; this
0x180016d61  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180016d66  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180016d6d  jb      short loc_180016D92
0x180016d6f  mov     edx, 0E7h
0x180016d74  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d7b  mov     [rsp+58h+var_38], ebx
0x180016d7f  mov     r9, rsi
0x180016d82  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180016d89  mov     rcx, [rcx+10h]
0x180016d8d  call    WPP_SF_qD
0x180016d92  mov     r8d, ebx; int
0x180016d95  lea     rdx, aErrorRestartin; "Error restarting source."
0x180016d9c  mov     rcx, [rsi+8]; this
0x180016da0  call    ?Error@MkvMfSource@MkvMfSourceLib@@AEAAJPEBGJ@Z; MkvMfSourceLib::MkvMfSource::Error(ushort const *,long)
0x180016da5  nop
0x180016da6  lea     rcx, [rsp+58h+var_28]; this
0x180016dab  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180016db0  mov     eax, ebx
0x180016db2  mov     rcx, [rsp+58h+var_10]
0x180016db7  xor     rcx, rsp; StackCookie
0x180016dba  call    __security_check_cookie
0x180016dbf  mov     rbx, [rsp+58h+arg_8]
0x180016dc4  mov     rsi, [rsp+58h+arg_10]
0x180016dc9  add     rsp, 50h
0x180016dcd  pop     rdi
0x180016dce  retn
```
