# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004d6c`
- end: `0x18000506d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `769`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002cb4`

## callees

- `0x1800026e4`
- `0x1800043c4`
- `0x180004ba8`
- `0x180004d6c`
- `0x1800052fc`
- `0x180005320`
- `0x180005334`
- `0x180005350`
- `0x180006730`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e97`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005028`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005028`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004fb6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004fb6`

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
        wil *lpOutputString,
        __int64 a12,
        _BYTE *a13,
        __int64 a14,
        int a15,
        unsigned __int64 a16)
{
  unsigned int v18; // edi
  int v19; // ebp
  int v20; // eax
  _WORD *v21; // rax
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-58h]

  *(_WORD *)lpOutputString = 0;
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
          LODWORD(v26) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v26);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v22);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v22) == 0),
        v25)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v23);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v22);
  }
}

```

## disassembly

```asm
0x180004d6c  mov     rax, rsp
0x180004d6f  mov     [rax+10h], edx
0x180004d72  mov     [rax+8], rcx
0x180004d76  push    rbp
0x180004d77  push    rsi
0x180004d78  push    rdi
0x180004d79  push    r12
0x180004d7b  push    r13
0x180004d7d  push    r14
0x180004d7f  push    r15
0x180004d81  sub     rsp, 50h
0x180004d85  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x180004d8d  mov     [rax+18h], rbx
0x180004d91  mov     r12, r9
0x180004d94  mov     r13, r8
0x180004d97  mov     r10, rcx
0x180004d9a  xor     eax, eax
0x180004d9c  mov     rsi, [rsp+88h+lpOutputString]
0x180004da4  mov     [rsi], ax
0x180004da7  mov     rax, [rsp+88h+arg_60]
0x180004daf  mov     byte ptr [rax], 0
0x180004db2  mov     r14, [rsp+88h+arg_38]
0x180004dba  mov     edi, [r14]
0x180004dbd  mov     rbx, [rsp+88h+arg_78]
0x180004dc5  mov     [rbx+8], edi
0x180004dc8  mov     eax, [r14+4]
0x180004dcc  mov     [rbx+0Ch], eax
0x180004dcf  xor     ebp, ebp
0x180004dd1  mov     r15d, [rsp+88h+arg_30]
0x180004dd9  mov     ecx, r15d
0x180004ddc  test    r15d, r15d
0x180004ddf  jz      short loc_180004E47
0x180004de1  sub     ecx, 1
0x180004de4  jz      short loc_180004E3E
0x180004de6  sub     ecx, 1
0x180004de9  jz      short loc_180004DF9
0x180004deb  cmp     ecx, 1
0x180004dee  jnz     short loc_180004E50
0x180004df0  mov     ecx, edi; this
0x180004df2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004df7  jmp     short loc_180004E4E
0x180004df9  test    edi, edi
0x180004dfb  js      short loc_180004E35
0x180004dfd  mov     edi, 8007029Ch
0x180004e02  mov     dword ptr [rsp+88h+var_58], edi; wil::details *
0x180004e06  mov     rax, [rsp+88h+arg_28]
0x180004e0e  mov     [rsp+88h+var_60], rax; __int64
0x180004e13  mov     rax, [rsp+88h+arg_20]
0x180004e1b  mov     [rsp+88h+var_68], rax; __int64
0x180004e20  mov     rcx, r10; int
0x180004e23  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004e28  mov     [rbx+8], edi
0x180004e2b  mov     ecx, edi; this
0x180004e2d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004e32  mov     [rbx+0Ch], eax
0x180004e35  mov     ecx, edi; this
0x180004e37  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004e3c  jmp     short loc_180004E4E
0x180004e3e  mov     ecx, edi; this
0x180004e40  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004e45  jmp     short loc_180004E4E
0x180004e47  mov     ecx, edi; this
0x180004e49  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004e4e  mov     ebp, eax
0x180004e50  mov     [rbx], r15d
0x180004e53  mov     eax, [rsp+88h+arg_70]
0x180004e5a  mov     [rbx+4], eax
0x180004e5d  cmp     dword ptr [r14+8], 1
0x180004e62  jnz     short loc_180004E6A
0x180004e64  or      eax, 8
0x180004e67  mov     [rbx+4], eax
0x180004e6a  mov     eax, 1
0x180004e6f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004e77  inc     eax
0x180004e79  mov     [rbx+10h], eax
0x180004e7c  mov     rax, [rsp+88h+arg_40]
0x180004e84  xor     edi, edi
0x180004e86  test    rax, rax
0x180004e89  jz      short loc_180004E90
0x180004e8b  cmp     [rax], di
0x180004e8e  jnz     short loc_180004E93
0x180004e90  mov     rax, rdi
0x180004e93  mov     [rbx+18h], rax
0x180004e97  call    cs:__imp_GetCurrentThreadId
0x180004e9d  mov     [rbx+20h], eax
0x180004ea0  mov     [rbx+38h], r13
0x180004ea4  mov     eax, [rsp+88h+arg_8]
0x180004eab  mov     [rbx+40h], eax
0x180004eae  mov     [rbx+44h], ebp
0x180004eb1  mov     rax, [rsp+88h+arg_20]
0x180004eb9  mov     [rbx+28h], rax
0x180004ebd  mov     [rbx+30h], r12
0x180004ec1  mov     rax, [rsp+88h+arg_28]
0x180004ec9  mov     [rbx+88h], rax
0x180004ed0  mov     rax, [rsp+88h+arg_0]
0x180004ed8  mov     [rbx+90h], rax
0x180004edf  mov     [rbx+48h], rdi
0x180004ee3  xorps   xmm0, xmm0
0x180004ee6  xor     eax, eax
0x180004ee8  movups  xmmword ptr [rbx+68h], xmm0
0x180004eec  mov     [rbx+78h], rax
0x180004ef0  movups  xmmword ptr [rbx+50h], xmm0
0x180004ef4  mov     [rbx+60h], rax
0x180004ef8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004eff  test    rax, rax
0x180004f02  jz      short loc_180004F0B
0x180004f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f09  jmp     short loc_180004F0E
0x180004f0b  mov     rax, rdi
0x180004f0e  mov     [rbx+80h], rax
0x180004f15  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004f1c  test    rax, rax
0x180004f1f  jz      short loc_180004F29
0x180004f21  mov     rcx, rbx
0x180004f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f29  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004f30  test    rax, rax
0x180004f33  jz      short loc_180004F4B
0x180004f35  mov     r8d, 400h
0x180004f3b  mov     rdx, [rsp+88h+arg_60]
0x180004f43  mov     rcx, rbx
0x180004f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f4b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004f52  test    rax, rax
0x180004f55  jz      short loc_180004F5F
0x180004f57  mov     rcx, rbx
0x180004f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f5f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004f66  test    rax, rax
0x180004f69  jz      short loc_180004F79
0x180004f6b  test    byte ptr [rbx+4], 2
0x180004f6f  jnz     short loc_180004F79
0x180004f71  mov     rcx, rbx
0x180004f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f79  cmp     [rbx+8], edi
0x180004f7c  jl      short loc_180004F98
0x180004f7e  cmp     r15d, 3
0x180004f82  jnz     loc_180005067
0x180004f88  mov     ecx, 8000FFFFh; this
0x180004f8d  mov     [rbx+8], ecx
0x180004f90  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004f95  mov     [rbx+0Ch], eax
0x180004f98  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180004f9f  jnz     short loc_180004FC0
0x180004fa1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004fa8  test    rax, rax
0x180004fab  jz      short loc_180004FB6
0x180004fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fb2  test    al, al
0x180004fb4  jmp     short loc_180004FBE
0x180004fb6  call    cs:__imp_IsDebuggerPresent
0x180004fbc  test    eax, eax
0x180004fbe  jz      short loc_180004FC6
0x180004fc0  test    byte ptr [rbx+4], 2
0x180004fc4  jz      short loc_180004FEA
0x180004fc6  mov     rax, cs:g_pfnResultLoggingCallback
0x180004fcd  test    rax, rax
0x180004fd0  jz      short loc_18000502E
0x180004fd2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004fd9  jnz     short loc_18000502E
0x180004fdb  xor     r8d, r8d
0x180004fde  xor     edx, edx
0x180004fe0  mov     rcx, rbx
0x180004fe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fe8  jmp     short loc_18000502E
0x180004fea  mov     ebp, 800h
0x180004fef  mov     rax, cs:g_pfnResultLoggingCallback
0x180004ff6  test    rax, rax
0x180004ff9  jz      short loc_180005012
0x180004ffb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005002  jnz     short loc_180005012
0x180005004  mov     r8d, ebp
0x180005007  mov     rdx, rsi
0x18000500a  mov     rcx, rbx
0x18000500d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005012  cmp     [rsi], di
0x180005015  jnz     short loc_180005025
0x180005017  mov     r8, rbx; unsigned __int64
0x18000501a  mov     rdx, rbp; wchar_t *
0x18000501d  mov     rcx, rsi; this
0x180005020  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180005025  mov     rcx, rsi; lpOutputString
0x180005028  call    cs:__imp_OutputDebugStringW
0x18000502e  test    byte ptr [rbx+4], 4
0x180005032  jnz     short loc_18000503D
0x180005034  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000503b  jz      short loc_18000504F
0x18000503d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005044  test    rax, rax
0x180005047  jz      short loc_18000504F
0x180005049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000504e  nop
0x18000504f  mov     rbx, [rsp+88h+arg_10]
0x180005057  add     rsp, 50h
0x18000505b  pop     r15
0x18000505d  pop     r14
0x18000505f  pop     r13
0x180005061  pop     r12
0x180005063  pop     rdi
0x180005064  pop     rsi
0x180005065  pop     rbp
0x180005066  retn
0x180005067  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
