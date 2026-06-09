# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180008424`
- end: `0x180008730`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180004578`
- `0x1800048e8`

## callees

- `0x1800044b0`
- `0x180007794`
- `0x180007fdc`
- `0x180008424`
- `0x180008ba8`
- `0x180008bd0`
- `0x180008be4`
- `0x180008c04`
- `0x180009b10`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008547`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008547`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000866c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000866c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800086e4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800086e4`

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
  int v21; // edx
  _WORD *v22; // rax
  int v23; // edx
  wil::details::in1diag3 *v24; // rcx
  const struct wil::FailureInfo *v25; // r9
  __int64 ModuleName; // rax
  bool v27; // zf
  wil::details *v28; // [rsp+30h] [rbp-48h]

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
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
    OutputDebugStringW((LPCWSTR)lpOutputString);
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
0x180008424  mov     [rsp+arg_10], rbx
0x180008429  mov     [rsp+arg_8], edx
0x18000842d  mov     [rsp+arg_0], rcx
0x180008432  push    rbp
0x180008433  push    rsi
0x180008434  push    rdi
0x180008435  push    r12
0x180008437  push    r13
0x180008439  push    r14
0x18000843b  push    r15
0x18000843d  sub     rsp, 40h
0x180008441  mov     r12, r9
0x180008444  mov     r13, r8
0x180008447  mov     r10, rcx
0x18000844a  xor     eax, eax
0x18000844c  mov     rsi, [rsp+78h+lpOutputString]
0x180008454  mov     [rsi], ax
0x180008457  mov     rax, [rsp+78h+arg_60]
0x18000845f  mov     byte ptr [rax], 0
0x180008462  mov     r14, [rsp+78h+arg_38]
0x18000846a  mov     edi, [r14]
0x18000846d  mov     rbx, [rsp+78h+arg_78]
0x180008475  mov     [rbx+8], edi
0x180008478  mov     eax, [r14+4]
0x18000847c  mov     [rbx+0Ch], eax
0x18000847f  xor     ebp, ebp
0x180008481  mov     r15d, [rsp+78h+arg_30]
0x180008489  mov     ecx, r15d
0x18000848c  test    r15d, r15d
0x18000848f  jz      short loc_1800084F7
0x180008491  sub     ecx, 1
0x180008494  jz      short loc_1800084EE
0x180008496  sub     ecx, 1
0x180008499  jz      short loc_1800084A9
0x18000849b  cmp     ecx, 1
0x18000849e  jnz     short loc_180008500
0x1800084a0  mov     ecx, edi; this
0x1800084a2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800084a7  jmp     short loc_1800084FE
0x1800084a9  test    edi, edi
0x1800084ab  js      short loc_1800084E5
0x1800084ad  mov     edi, 8007029Ch
0x1800084b2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800084b6  mov     rax, [rsp+78h+arg_28]
0x1800084be  mov     [rsp+78h+var_50], rax; __int64
0x1800084c3  mov     rax, [rsp+78h+arg_20]
0x1800084cb  mov     [rsp+78h+var_58], rax; __int64
0x1800084d0  mov     rcx, r10; int
0x1800084d3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800084d8  mov     [rbx+8], edi
0x1800084db  mov     ecx, edi; this
0x1800084dd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800084e2  mov     [rbx+0Ch], eax
0x1800084e5  mov     ecx, edi; this
0x1800084e7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800084ec  jmp     short loc_1800084FE
0x1800084ee  mov     ecx, edi; this
0x1800084f0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800084f5  jmp     short loc_1800084FE
0x1800084f7  mov     ecx, edi; this
0x1800084f9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800084fe  mov     ebp, eax
0x180008500  mov     [rbx], r15d
0x180008503  mov     eax, [rsp+78h+arg_70]
0x18000850a  mov     [rbx+4], eax
0x18000850d  cmp     dword ptr [r14+8], 1
0x180008512  jnz     short loc_18000851A
0x180008514  or      eax, 8
0x180008517  mov     [rbx+4], eax
0x18000851a  mov     eax, 1
0x18000851f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008527  inc     eax
0x180008529  mov     [rbx+10h], eax
0x18000852c  mov     rax, [rsp+78h+arg_40]
0x180008534  xor     edi, edi
0x180008536  test    rax, rax
0x180008539  jz      short loc_180008540
0x18000853b  cmp     [rax], di
0x18000853e  jnz     short loc_180008543
0x180008540  mov     rax, rdi
0x180008543  mov     [rbx+18h], rax
0x180008547  call    cs:__imp_GetCurrentThreadId
0x18000854e  nop     dword ptr [rax+rax+00h]
0x180008553  mov     [rbx+20h], eax
0x180008556  mov     [rbx+38h], r13
0x18000855a  mov     eax, [rsp+78h+arg_8]
0x180008561  mov     [rbx+40h], eax
0x180008564  mov     [rbx+44h], ebp
0x180008567  mov     rax, [rsp+78h+arg_20]
0x18000856f  mov     [rbx+28h], rax
0x180008573  mov     [rbx+30h], r12
0x180008577  mov     rax, [rsp+78h+arg_28]
0x18000857f  mov     [rbx+88h], rax
0x180008586  mov     rax, [rsp+78h+arg_0]
0x18000858e  mov     [rbx+90h], rax
0x180008595  mov     [rbx+48h], rdi
0x180008599  xorps   xmm0, xmm0
0x18000859c  xor     eax, eax
0x18000859e  movups  xmmword ptr [rbx+68h], xmm0
0x1800085a2  mov     [rbx+78h], rax
0x1800085a6  movups  xmmword ptr [rbx+50h], xmm0
0x1800085aa  mov     [rbx+60h], rax
0x1800085ae  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800085b5  test    rax, rax
0x1800085b8  jz      short loc_1800085C1
0x1800085ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085bf  jmp     short loc_1800085C4
0x1800085c1  mov     rax, rdi
0x1800085c4  mov     [rbx+80h], rax
0x1800085cb  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800085d2  test    rax, rax
0x1800085d5  jz      short loc_1800085DF
0x1800085d7  mov     rcx, rbx
0x1800085da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085df  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800085e6  test    rax, rax
0x1800085e9  jz      short loc_180008601
0x1800085eb  mov     r8d, 400h
0x1800085f1  mov     rdx, [rsp+78h+arg_60]
0x1800085f9  mov     rcx, rbx
0x1800085fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008601  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008608  test    rax, rax
0x18000860b  jz      short loc_180008615
0x18000860d  mov     rcx, rbx
0x180008610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008615  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000861c  test    rax, rax
0x18000861f  jz      short loc_18000862F
0x180008621  test    byte ptr [rbx+4], 2
0x180008625  jnz     short loc_18000862F
0x180008627  mov     rcx, rbx
0x18000862a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000862f  cmp     [rbx+8], edi
0x180008632  jl      short loc_18000864E
0x180008634  cmp     r15d, 3
0x180008638  jnz     loc_18000872A
0x18000863e  mov     ecx, 8000FFFFh; this
0x180008643  mov     [rbx+8], ecx
0x180008646  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000864b  mov     [rbx+0Ch], eax
0x18000864e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180008655  jnz     short loc_18000867C
0x180008657  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000865e  test    rax, rax
0x180008661  jz      short loc_18000866C
0x180008663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008668  test    al, al
0x18000866a  jmp     short loc_18000867A
0x18000866c  call    cs:__imp_IsDebuggerPresent
0x180008673  nop     dword ptr [rax+rax+00h]
0x180008678  test    eax, eax
0x18000867a  jz      short loc_180008682
0x18000867c  test    byte ptr [rbx+4], 2
0x180008680  jz      short loc_1800086A6
0x180008682  mov     rax, cs:g_pfnResultLoggingCallback
0x180008689  test    rax, rax
0x18000868c  jz      short loc_1800086F0
0x18000868e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008695  jnz     short loc_1800086F0
0x180008697  xor     r8d, r8d
0x18000869a  xor     edx, edx
0x18000869c  mov     rcx, rbx
0x18000869f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086a4  jmp     short loc_1800086F0
0x1800086a6  mov     ebp, 800h
0x1800086ab  mov     rax, cs:g_pfnResultLoggingCallback
0x1800086b2  test    rax, rax
0x1800086b5  jz      short loc_1800086CE
0x1800086b7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800086be  jnz     short loc_1800086CE
0x1800086c0  mov     r8d, ebp
0x1800086c3  mov     rdx, rsi
0x1800086c6  mov     rcx, rbx
0x1800086c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086ce  cmp     [rsi], di
0x1800086d1  jnz     short loc_1800086E1
0x1800086d3  mov     r8, rbx; unsigned __int64
0x1800086d6  mov     rdx, rbp; wchar_t *
0x1800086d9  mov     rcx, rsi; this
0x1800086dc  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800086e1  mov     rcx, rsi; lpOutputString
0x1800086e4  call    cs:__imp_OutputDebugStringW
0x1800086eb  nop     dword ptr [rax+rax+00h]
0x1800086f0  test    byte ptr [rbx+4], 4
0x1800086f4  jnz     short loc_1800086FF
0x1800086f6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800086fd  jz      short loc_180008711
0x1800086ff  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008706  test    rax, rax
0x180008709  jz      short loc_180008711
0x18000870b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008710  nop
0x180008711  mov     rbx, [rsp+78h+arg_10]
0x180008719  add     rsp, 40h
0x18000871d  pop     r15
0x18000871f  pop     r14
0x180008721  pop     r13
0x180008723  pop     r12
0x180008725  pop     rdi
0x180008726  pop     rsi
0x180008727  pop     rbp
0x180008728  retn
0x18000872a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
