# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180018fa0`
- end: `0x1800192ac`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180012b3c`
- `0x180012f40`

## callees

- `0x180005314`
- `0x18000c194`
- `0x18000c568`
- `0x180012a74`
- `0x180018944`
- `0x180018fa0`
- `0x180019b44`
- `0x180019b70`
- `0x18001b82c`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800190c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800190c3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800191e8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800191e8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180019260`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180019260`

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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
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
0x180018fa0  mov     [rsp+arg_10], rbx
0x180018fa5  mov     [rsp+arg_8], edx
0x180018fa9  mov     [rsp+arg_0], rcx
0x180018fae  push    rbp
0x180018faf  push    rsi
0x180018fb0  push    rdi
0x180018fb1  push    r12
0x180018fb3  push    r13
0x180018fb5  push    r14
0x180018fb7  push    r15
0x180018fb9  sub     rsp, 40h
0x180018fbd  mov     r12, r9
0x180018fc0  mov     r13, r8
0x180018fc3  mov     r10, rcx
0x180018fc6  xor     eax, eax
0x180018fc8  mov     rsi, [rsp+78h+lpOutputString]
0x180018fd0  mov     [rsi], ax
0x180018fd3  mov     rax, [rsp+78h+arg_60]
0x180018fdb  mov     byte ptr [rax], 0
0x180018fde  mov     r14, [rsp+78h+arg_38]
0x180018fe6  mov     edi, [r14]
0x180018fe9  mov     rbx, [rsp+78h+arg_78]
0x180018ff1  mov     [rbx+8], edi
0x180018ff4  mov     eax, [r14+4]
0x180018ff8  mov     [rbx+0Ch], eax
0x180018ffb  xor     ebp, ebp
0x180018ffd  mov     r15d, [rsp+78h+arg_30]
0x180019005  mov     ecx, r15d
0x180019008  test    r15d, r15d
0x18001900b  jz      short loc_180019073
0x18001900d  sub     ecx, 1
0x180019010  jz      short loc_18001906A
0x180019012  sub     ecx, 1
0x180019015  jz      short loc_180019025
0x180019017  cmp     ecx, 1
0x18001901a  jnz     short loc_18001907C
0x18001901c  mov     ecx, edi; this
0x18001901e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180019023  jmp     short loc_18001907A
0x180019025  test    edi, edi
0x180019027  js      short loc_180019061
0x180019029  mov     edi, 8007029Ch
0x18001902e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180019032  mov     rax, [rsp+78h+arg_28]
0x18001903a  mov     [rsp+78h+var_50], rax; __int64
0x18001903f  mov     rax, [rsp+78h+arg_20]
0x180019047  mov     [rsp+78h+var_58], rax; __int64
0x18001904c  mov     rcx, r10; int
0x18001904f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180019054  mov     [rbx+8], edi
0x180019057  mov     ecx, edi; this
0x180019059  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001905e  mov     [rbx+0Ch], eax
0x180019061  mov     ecx, edi; this
0x180019063  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180019068  jmp     short loc_18001907A
0x18001906a  mov     ecx, edi; this
0x18001906c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180019071  jmp     short loc_18001907A
0x180019073  mov     ecx, edi; this
0x180019075  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001907a  mov     ebp, eax
0x18001907c  mov     [rbx], r15d
0x18001907f  mov     eax, [rsp+78h+arg_70]
0x180019086  mov     [rbx+4], eax
0x180019089  cmp     dword ptr [r14+8], 1
0x18001908e  jnz     short loc_180019096
0x180019090  or      eax, 8
0x180019093  mov     [rbx+4], eax
0x180019096  mov     eax, 1
0x18001909b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800190a3  inc     eax
0x1800190a5  mov     [rbx+10h], eax
0x1800190a8  mov     rax, [rsp+78h+arg_40]
0x1800190b0  xor     edi, edi
0x1800190b2  test    rax, rax
0x1800190b5  jz      short loc_1800190BC
0x1800190b7  cmp     [rax], di
0x1800190ba  jnz     short loc_1800190BF
0x1800190bc  mov     rax, rdi
0x1800190bf  mov     [rbx+18h], rax
0x1800190c3  call    cs:__imp_GetCurrentThreadId
0x1800190ca  nop     dword ptr [rax+rax+00h]
0x1800190cf  mov     [rbx+20h], eax
0x1800190d2  mov     [rbx+38h], r13
0x1800190d6  mov     eax, [rsp+78h+arg_8]
0x1800190dd  mov     [rbx+40h], eax
0x1800190e0  mov     [rbx+44h], ebp
0x1800190e3  mov     rax, [rsp+78h+arg_20]
0x1800190eb  mov     [rbx+28h], rax
0x1800190ef  mov     [rbx+30h], r12
0x1800190f3  mov     rax, [rsp+78h+arg_28]
0x1800190fb  mov     [rbx+88h], rax
0x180019102  mov     rax, [rsp+78h+arg_0]
0x18001910a  mov     [rbx+90h], rax
0x180019111  mov     [rbx+48h], rdi
0x180019115  xorps   xmm0, xmm0
0x180019118  xor     eax, eax
0x18001911a  movups  xmmword ptr [rbx+68h], xmm0
0x18001911e  mov     [rbx+78h], rax
0x180019122  movups  xmmword ptr [rbx+50h], xmm0
0x180019126  mov     [rbx+60h], rax
0x18001912a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180019131  test    rax, rax
0x180019134  jz      short loc_18001913D
0x180019136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001913b  jmp     short loc_180019140
0x18001913d  mov     rax, rdi
0x180019140  mov     [rbx+80h], rax
0x180019147  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001914e  test    rax, rax
0x180019151  jz      short loc_18001915B
0x180019153  mov     rcx, rbx
0x180019156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001915b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180019162  test    rax, rax
0x180019165  jz      short loc_18001917D
0x180019167  mov     r8d, 400h
0x18001916d  mov     rdx, [rsp+78h+arg_60]
0x180019175  mov     rcx, rbx
0x180019178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001917d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180019184  test    rax, rax
0x180019187  jz      short loc_180019191
0x180019189  mov     rcx, rbx
0x18001918c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019191  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180019198  test    rax, rax
0x18001919b  jz      short loc_1800191AB
0x18001919d  test    byte ptr [rbx+4], 2
0x1800191a1  jnz     short loc_1800191AB
0x1800191a3  mov     rcx, rbx
0x1800191a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191ab  cmp     [rbx+8], edi
0x1800191ae  jl      short loc_1800191CA
0x1800191b0  cmp     r15d, 3
0x1800191b4  jnz     loc_1800192A6
0x1800191ba  mov     ecx, 8000FFFFh; this
0x1800191bf  mov     [rbx+8], ecx
0x1800191c2  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800191c7  mov     [rbx+0Ch], eax
0x1800191ca  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800191d1  jnz     short loc_1800191F8
0x1800191d3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800191da  test    rax, rax
0x1800191dd  jz      short loc_1800191E8
0x1800191df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191e4  test    al, al
0x1800191e6  jmp     short loc_1800191F6
0x1800191e8  call    cs:__imp_IsDebuggerPresent
0x1800191ef  nop     dword ptr [rax+rax+00h]
0x1800191f4  test    eax, eax
0x1800191f6  jz      short loc_1800191FE
0x1800191f8  test    byte ptr [rbx+4], 2
0x1800191fc  jz      short loc_180019222
0x1800191fe  mov     rax, cs:g_pfnResultLoggingCallback
0x180019205  test    rax, rax
0x180019208  jz      short loc_18001926C
0x18001920a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180019211  jnz     short loc_18001926C
0x180019213  xor     r8d, r8d
0x180019216  xor     edx, edx
0x180019218  mov     rcx, rbx
0x18001921b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019220  jmp     short loc_18001926C
0x180019222  mov     ebp, 800h
0x180019227  mov     rax, cs:g_pfnResultLoggingCallback
0x18001922e  test    rax, rax
0x180019231  jz      short loc_18001924A
0x180019233  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001923a  jnz     short loc_18001924A
0x18001923c  mov     r8d, ebp
0x18001923f  mov     rdx, rsi
0x180019242  mov     rcx, rbx
0x180019245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001924a  cmp     [rsi], di
0x18001924d  jnz     short loc_18001925D
0x18001924f  mov     r8, rbx; unsigned __int64
0x180019252  mov     rdx, rbp; unsigned __int16 *
0x180019255  mov     rcx, rsi; this
0x180019258  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001925d  mov     rcx, rsi; lpOutputString
0x180019260  call    cs:__imp_OutputDebugStringW
0x180019267  nop     dword ptr [rax+rax+00h]
0x18001926c  test    byte ptr [rbx+4], 4
0x180019270  jnz     short loc_18001927B
0x180019272  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180019279  jz      short loc_18001928D
0x18001927b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180019282  test    rax, rax
0x180019285  jz      short loc_18001928D
0x180019287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001928c  nop
0x18001928d  mov     rbx, [rsp+78h+arg_10]
0x180019295  add     rsp, 40h
0x180019299  pop     r15
0x18001929b  pop     r14
0x18001929d  pop     r13
0x18001929f  pop     r12
0x1800192a1  pop     rdi
0x1800192a2  pop     rsi
0x1800192a3  pop     rbp
0x1800192a4  retn
0x1800192a6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
