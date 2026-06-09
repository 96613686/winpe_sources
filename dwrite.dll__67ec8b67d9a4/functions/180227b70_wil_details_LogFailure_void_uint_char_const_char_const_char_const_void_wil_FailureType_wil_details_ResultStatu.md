# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180227b70`
- end: `0x180227e69`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180225c78`
- `0x180225fbc`

## callees

- `0x180210c38`
- `0x180225bb8`
- `0x1802272b4`
- `0x180227b70`
- `0x1802287a4`
- `0x1802287c0`
- `0x18022887c`
- `0x180228898`
- `0x18022a110`
- `0x180330010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180227c93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180227c93`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180227db2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180227db2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180227e24`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180227e24`

## pseudocode

```c
void __fastcall wil::details::LogFailure(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        unsigned int *a8,
        _WORD *a9,
        __int64 a10,
        WCHAR *lpOutputString,
        __int64 a12,
        _BYTE *a13,
        __int64 a14,
        int a15,
        unsigned __int64 a16)
{
  unsigned int v18; // edi
  int v19; // ebp
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  int v23; // edx
  wil::details::in1diag3 *v24; // rcx
  const struct wil::FailureInfo *v25; // r9
  __int64 ModuleName; // rax
  bool v27; // zf
  wil::details *v28; // [rsp+30h] [rbp-48h]

  *lpOutputString = 0;
  *a13 = 0;
  v18 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  v19 = 0;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v18, a2);
        break;
      case 2:
        if ( (v18 & 0x80000000) == 0 )
        {
          v18 = -2147024228;
          LODWORD(v28) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v28);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
        }
        v20 = wil::details::RecordLog((wil::details *)v18, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v18, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v18, a2);
  }
  v19 = v20;
LABEL_12:
  *(_DWORD *)a16 = a7;
  *(_DWORD *)(a16 + 4) = a15;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  *(_DWORD *)(a16 + 32) = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 64) = a2;
  *(_DWORD *)(a16 + 68) = v19;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  *(_QWORD *)(a16 + 128) = ModuleName;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(a16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(a16, a13, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(a16);
  if ( wil::details::g_pfnOriginateCallback && (*(_BYTE *)(a16 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(a16);
  if ( *(int *)(a16 + 8) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v27)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
    OutputDebugStringW(lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x180227b70  mov     [rsp+arg_10], rbx
0x180227b75  mov     [rsp+arg_8], edx
0x180227b79  mov     [rsp+arg_0], rcx
0x180227b7e  push    rbp
0x180227b7f  push    rsi
0x180227b80  push    rdi
0x180227b81  push    r12
0x180227b83  push    r13
0x180227b85  push    r14
0x180227b87  push    r15
0x180227b89  sub     rsp, 40h
0x180227b8d  mov     r12, r9
0x180227b90  mov     r13, r8
0x180227b93  mov     r10, rcx
0x180227b96  xor     eax, eax
0x180227b98  mov     rsi, [rsp+78h+lpOutputString]
0x180227ba0  mov     [rsi], ax
0x180227ba3  mov     rax, [rsp+78h+arg_60]
0x180227bab  mov     byte ptr [rax], 0
0x180227bae  mov     r14, [rsp+78h+arg_38]
0x180227bb6  mov     edi, [r14]
0x180227bb9  mov     rbx, [rsp+78h+arg_78]
0x180227bc1  mov     [rbx+8], edi
0x180227bc4  mov     eax, [r14+4]
0x180227bc8  mov     [rbx+0Ch], eax
0x180227bcb  xor     ebp, ebp
0x180227bcd  mov     r15d, [rsp+78h+arg_30]
0x180227bd5  mov     ecx, r15d
0x180227bd8  test    r15d, r15d
0x180227bdb  jz      short loc_180227C43
0x180227bdd  sub     ecx, 1
0x180227be0  jz      short loc_180227C3A
0x180227be2  sub     ecx, 1
0x180227be5  jz      short loc_180227BF5
0x180227be7  cmp     ecx, 1
0x180227bea  jnz     short loc_180227C4C
0x180227bec  mov     ecx, edi; this
0x180227bee  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180227bf3  jmp     short loc_180227C4A
0x180227bf5  test    edi, edi
0x180227bf7  js      short loc_180227C31
0x180227bf9  mov     edi, 8007029Ch
0x180227bfe  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180227c02  mov     rax, [rsp+78h+arg_28]
0x180227c0a  mov     [rsp+78h+var_50], rax; __int64
0x180227c0f  mov     rax, [rsp+78h+arg_20]
0x180227c17  mov     [rsp+78h+var_58], rax; __int64
0x180227c1c  mov     rcx, r10; int
0x180227c1f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180227c24  mov     [rbx+8], edi
0x180227c27  mov     ecx, edi; this
0x180227c29  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180227c2e  mov     [rbx+0Ch], eax
0x180227c31  mov     ecx, edi; this
0x180227c33  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180227c38  jmp     short loc_180227C4A
0x180227c3a  mov     ecx, edi; this
0x180227c3c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180227c41  jmp     short loc_180227C4A
0x180227c43  mov     ecx, edi; this
0x180227c45  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180227c4a  mov     ebp, eax
0x180227c4c  mov     [rbx], r15d
0x180227c4f  mov     eax, [rsp+78h+arg_70]
0x180227c56  mov     [rbx+4], eax
0x180227c59  cmp     dword ptr [r14+8], 1
0x180227c5e  jnz     short loc_180227C66
0x180227c60  or      eax, 8
0x180227c63  mov     [rbx+4], eax
0x180227c66  mov     eax, 1
0x180227c6b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180227c73  inc     eax
0x180227c75  mov     [rbx+10h], eax
0x180227c78  mov     rax, [rsp+78h+arg_40]
0x180227c80  xor     edi, edi
0x180227c82  test    rax, rax
0x180227c85  jz      short loc_180227C8C
0x180227c87  cmp     [rax], di
0x180227c8a  jnz     short loc_180227C8F
0x180227c8c  mov     rax, rdi
0x180227c8f  mov     [rbx+18h], rax
0x180227c93  call    cs:__imp_GetCurrentThreadId
0x180227c99  mov     [rbx+20h], eax
0x180227c9c  mov     [rbx+38h], r13
0x180227ca0  mov     eax, [rsp+78h+arg_8]
0x180227ca7  mov     [rbx+40h], eax
0x180227caa  mov     [rbx+44h], ebp
0x180227cad  mov     rax, [rsp+78h+arg_20]
0x180227cb5  mov     [rbx+28h], rax
0x180227cb9  mov     [rbx+30h], r12
0x180227cbd  mov     rax, [rsp+78h+arg_28]
0x180227cc5  mov     [rbx+88h], rax
0x180227ccc  mov     rax, [rsp+78h+arg_0]
0x180227cd4  mov     [rbx+90h], rax
0x180227cdb  mov     [rbx+48h], rdi
0x180227cdf  xorps   xmm0, xmm0
0x180227ce2  xor     eax, eax
0x180227ce4  movups  xmmword ptr [rbx+68h], xmm0
0x180227ce8  mov     [rbx+78h], rax
0x180227cec  movups  xmmword ptr [rbx+50h], xmm0
0x180227cf0  mov     [rbx+60h], rax
0x180227cf4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180227cfb  test    rax, rax
0x180227cfe  jz      short loc_180227D07
0x180227d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180227d05  jmp     short loc_180227D0A
0x180227d07  mov     rax, rdi
0x180227d0a  mov     [rbx+80h], rax
0x180227d11  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180227d18  test    rax, rax
0x180227d1b  jz      short loc_180227D25
0x180227d1d  mov     rcx, rbx
0x180227d20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180227d25  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180227d2c  test    rax, rax
0x180227d2f  jz      short loc_180227D47
0x180227d31  mov     r8d, 400h
0x180227d37  mov     rdx, [rsp+78h+arg_60]
0x180227d3f  mov     rcx, rbx
0x180227d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180227d47  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180227d4e  test    rax, rax
0x180227d51  jz      short loc_180227D5B
0x180227d53  mov     rcx, rbx
0x180227d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180227d5b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180227d62  test    rax, rax
0x180227d65  jz      short loc_180227D75
0x180227d67  test    byte ptr [rbx+4], 2
0x180227d6b  jnz     short loc_180227D75
0x180227d6d  mov     rcx, rbx
0x180227d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180227d75  cmp     [rbx+8], edi
0x180227d78  jl      short loc_180227D94
0x180227d7a  cmp     r15d, 3
0x180227d7e  jnz     loc_180227E63
0x180227d84  mov     ecx, 8000FFFFh; this
0x180227d89  mov     [rbx+8], ecx
0x180227d8c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180227d91  mov     [rbx+0Ch], eax
0x180227d94  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180227d9b  jnz     short loc_180227DBC
0x180227d9d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180227da4  test    rax, rax
0x180227da7  jz      short loc_180227DB2
0x180227da9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180227dae  test    al, al
0x180227db0  jmp     short loc_180227DBA
0x180227db2  call    cs:__imp_IsDebuggerPresent
0x180227db8  test    eax, eax
0x180227dba  jz      short loc_180227DC2
0x180227dbc  test    byte ptr [rbx+4], 2
0x180227dc0  jz      short loc_180227DE6
0x180227dc2  mov     rax, cs:g_pfnResultLoggingCallback
0x180227dc9  test    rax, rax
0x180227dcc  jz      short loc_180227E2A
0x180227dce  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180227dd5  jnz     short loc_180227E2A
0x180227dd7  xor     r8d, r8d
0x180227dda  xor     edx, edx
0x180227ddc  mov     rcx, rbx
0x180227ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180227de4  jmp     short loc_180227E2A
0x180227de6  mov     ebp, 800h
0x180227deb  mov     rax, cs:g_pfnResultLoggingCallback
0x180227df2  test    rax, rax
0x180227df5  jz      short loc_180227E0E
0x180227df7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180227dfe  jnz     short loc_180227E0E
0x180227e00  mov     r8d, ebp
0x180227e03  mov     rdx, rsi
0x180227e06  mov     rcx, rbx
0x180227e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180227e0e  cmp     [rsi], di
0x180227e11  jnz     short loc_180227E21
0x180227e13  mov     r8, rbx; unsigned __int64
0x180227e16  mov     rdx, rbp; wchar_t *
0x180227e19  mov     rcx, rsi; pszDest
0x180227e1c  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180227e21  mov     rcx, rsi; lpOutputString
0x180227e24  call    cs:__imp_OutputDebugStringW
0x180227e2a  test    byte ptr [rbx+4], 4
0x180227e2e  jnz     short loc_180227E39
0x180227e30  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180227e37  jz      short loc_180227E4B
0x180227e39  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180227e40  test    rax, rax
0x180227e43  jz      short loc_180227E4B
0x180227e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180227e4a  nop
0x180227e4b  mov     rbx, [rsp+78h+arg_10]
0x180227e53  add     rsp, 40h
0x180227e57  pop     r15
0x180227e59  pop     r14
0x180227e5b  pop     r13
0x180227e5d  pop     r12
0x180227e5f  pop     rdi
0x180227e60  pop     rsi
0x180227e61  pop     rbp
0x180227e62  retn
0x180227e63  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
