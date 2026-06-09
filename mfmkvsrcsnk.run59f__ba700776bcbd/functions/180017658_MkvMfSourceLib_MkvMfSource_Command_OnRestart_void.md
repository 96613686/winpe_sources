# MkvMfSourceLib::MkvMfSource::Command::OnRestart(void)

- ea: `0x180017658`
- end: `0x180017894`
- name: `?OnRestart@Command@MkvMfSource@MkvMfSourceLib@@QEAAJXZ`
- size: `572`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource::Command *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180015b5c`

## callees

- `0x180002400`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180011720`
- `0x180017658`
- `0x180018260`
- `0x180019320`
- `0x180021b9c`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001770f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800177b8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001770f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800177b8`

## string_xrefs

- `0x18001767f`: `MkvMfSourceLib::MkvMfSource::Command::OnRestart`
- `0x180017772`: `MkvMfSourceLib::MkvMfSource::Command::OnRestart`
- `0x18001781b`: `MkvMfSourceLib::MkvMfSource::Command::OnRestart`

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
        v8 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v15 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x180017658  mov     [rsp+arg_8], rbx
0x18001765d  mov     [rsp+arg_10], rsi
0x180017662  push    rdi
0x180017663  sub     rsp, 50h
0x180017667  mov     rax, cs:__security_cookie
0x18001766e  xor     rax, rsp
0x180017671  mov     [rsp+58h+var_10], rax
0x180017676  mov     rsi, rcx
0x180017679  mov     r8d, 0E0Fh; int
0x18001767f  lea     rdx, aMkvmfsourcelib_46; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180017686  lea     rcx, [rsp+58h+var_28]; this
0x18001768b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180017690  nop
0x180017691  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180017698  cmp     byte ptr [rcx+8], 0
0x18001769c  jz      short loc_1800176F1
0x18001769e  cmp     qword ptr [rsi+10h], 0
0x1800176a3  jz      short loc_1800176F1
0x1800176a5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800176aa  mov     rdi, rax
0x1800176ad  mov     rdx, [rsi+10h]
0x1800176b1  mov     rcx, [rdx]
0x1800176b4  mov     rax, [rcx+128h]
0x1800176bb  mov     rcx, rdx
0x1800176be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176c3  mov     ebx, eax
0x1800176c5  mov     r8, [rsi+10h]
0x1800176c9  mov     rcx, [r8]
0x1800176cc  mov     rax, [rcx+118h]
0x1800176d3  lea     rdx, [rsp+58h+var_20]
0x1800176d8  mov     rcx, r8
0x1800176db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176e0  movups  xmm0, xmmword ptr [rax]
0x1800176e3  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800176eb  mov     [rdi+7E0h], ebx
0x1800176f1  mov     rcx, rsi; this
0x1800176f4  call    ?OnStartNoSeek@Command@MkvMfSource@MkvMfSourceLib@@AEBAJXZ; MkvMfSourceLib::MkvMfSource::Command::OnStartNoSeek(void)
0x1800176f9  mov     ebx, eax
0x1800176fb  test    eax, eax
0x1800176fd  jns     loc_180017798
0x180017703  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001770a  test    rcx, rcx
0x18001770d  jnz     short loc_180017756
0x18001770f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180017716  nop     dword ptr [rax+rax+00h]
0x18001771b  mov     rcx, rax
0x18001771e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180017725  test    rax, rax
0x180017728  jz      short loc_180017748
0x18001772a  mov     rax, [rax]
0x18001772d  mov     edx, 7F0h
0x180017732  mov     rax, [rax+8]
0x180017736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001773b  test    eax, eax
0x18001773d  jz      short loc_180017748
0x18001773f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017746  jmp     short loc_180017756
0x180017748  lea     rcx, qword_1800DBF70; this
0x18001774f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180017756  cmp     byte ptr [rcx+8], 0
0x18001775a  jz      short loc_180017781
0x18001775c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180017761  cmp     [rax+7CCh], ebx
0x180017767  jz      short loc_180017781
0x180017769  mov     r9d, ebx; int
0x18001776c  mov     r8d, 0E0Fh; int
0x180017772  lea     rdx, aMkvmfsourcelib_46; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180017779  mov     rcx, rax; this
0x18001777c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180017781  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180017788  jb      loc_180017856
0x18001778e  mov     edx, 0E6h
0x180017793  jmp     loc_180017838
0x180017798  mov     dl, 1; bool
0x18001779a  mov     rcx, rsi; this
0x18001779d  call    ?OnStartComplete@Command@MkvMfSource@MkvMfSourceLib@@AEBAJ_N@Z; MkvMfSourceLib::MkvMfSource::Command::OnStartComplete(bool)
0x1800177a2  mov     ebx, eax
0x1800177a4  test    eax, eax
0x1800177a6  jns     loc_18001786A
0x1800177ac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800177b3  test    rcx, rcx
0x1800177b6  jnz     short loc_1800177FF
0x1800177b8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800177bf  nop     dword ptr [rax+rax+00h]
0x1800177c4  mov     rcx, rax
0x1800177c7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800177ce  test    rax, rax
0x1800177d1  jz      short loc_1800177F1
0x1800177d3  mov     rax, [rax]
0x1800177d6  mov     edx, 7F0h
0x1800177db  mov     rax, [rax+8]
0x1800177df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800177e4  test    eax, eax
0x1800177e6  jz      short loc_1800177F1
0x1800177e8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800177ef  jmp     short loc_1800177FF
0x1800177f1  lea     rcx, qword_1800DBF70; this
0x1800177f8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800177ff  cmp     byte ptr [rcx+8], 0
0x180017803  jz      short loc_18001782A
0x180017805  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001780a  cmp     [rax+7CCh], ebx
0x180017810  jz      short loc_18001782A
0x180017812  mov     r9d, ebx; int
0x180017815  mov     r8d, 0E11h; int
0x18001781b  lea     rdx, aMkvmfsourcelib_46; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180017822  mov     rcx, rax; this
0x180017825  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001782a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180017831  jb      short loc_180017856
0x180017833  mov     edx, 0E7h
0x180017838  mov     rcx, cs:WPP_GLOBAL_Control
0x18001783f  mov     [rsp+58h+var_38], ebx
0x180017843  mov     r9, rsi
0x180017846  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18001784d  mov     rcx, [rcx+10h]
0x180017851  call    WPP_SF_qD
0x180017856  mov     r8d, ebx; int
0x180017859  lea     rdx, aErrorRestartin; "Error restarting source."
0x180017860  mov     rcx, [rsi+8]; this
0x180017864  call    ?Error@MkvMfSource@MkvMfSourceLib@@AEAAJPEBGJ@Z; MkvMfSourceLib::MkvMfSource::Error(ushort const *,long)
0x180017869  nop
0x18001786a  lea     rcx, [rsp+58h+var_28]; this
0x18001786f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180017874  mov     eax, ebx
0x180017876  mov     rcx, [rsp+58h+var_10]
0x18001787b  xor     rcx, rsp; StackCookie
0x18001787e  call    __security_check_cookie
0x180017883  mov     rbx, [rsp+58h+arg_8]
0x180017888  mov     rsi, [rsp+58h+arg_10]
0x18001788d  add     rsp, 50h
0x180017891  pop     rdi
0x180017892  retn
```
