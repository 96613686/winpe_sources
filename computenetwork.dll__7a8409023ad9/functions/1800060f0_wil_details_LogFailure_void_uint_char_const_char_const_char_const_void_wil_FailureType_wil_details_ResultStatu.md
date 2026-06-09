# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800060f0`
- end: `0x1800063e9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003ce8`

## callees

- `0x1800033c4`
- `0x180004e44`
- `0x180005f2c`
- `0x1800060f0`
- `0x180006674`
- `0x180006690`
- `0x1800066a4`
- `0x1800066c0`
- `0x1800078ac`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006213`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006213`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800063a4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800063a4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006332`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006332`

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
      g_pfnResultLoggingCallback(a16, 0, 0, v25);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v25);
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
0x1800060f0  mov     [rsp+arg_10], rbx
0x1800060f5  mov     [rsp+arg_8], edx
0x1800060f9  mov     [rsp+arg_0], rcx
0x1800060fe  push    rbp
0x1800060ff  push    rsi
0x180006100  push    rdi
0x180006101  push    r12
0x180006103  push    r13
0x180006105  push    r14
0x180006107  push    r15
0x180006109  sub     rsp, 40h
0x18000610d  mov     r12, r9
0x180006110  mov     r13, r8
0x180006113  mov     r10, rcx
0x180006116  xor     eax, eax
0x180006118  mov     rsi, [rsp+78h+lpOutputString]
0x180006120  mov     [rsi], ax
0x180006123  mov     rax, [rsp+78h+arg_60]
0x18000612b  mov     byte ptr [rax], 0
0x18000612e  mov     r14, [rsp+78h+arg_38]
0x180006136  mov     edi, [r14]
0x180006139  mov     rbx, [rsp+78h+arg_78]
0x180006141  mov     [rbx+8], edi
0x180006144  mov     eax, [r14+4]
0x180006148  mov     [rbx+0Ch], eax
0x18000614b  xor     ebp, ebp
0x18000614d  mov     r15d, [rsp+78h+arg_30]
0x180006155  mov     ecx, r15d
0x180006158  test    r15d, r15d
0x18000615b  jz      short loc_1800061C3
0x18000615d  sub     ecx, 1
0x180006160  jz      short loc_1800061BA
0x180006162  sub     ecx, 1
0x180006165  jz      short loc_180006175
0x180006167  cmp     ecx, 1
0x18000616a  jnz     short loc_1800061CC
0x18000616c  mov     ecx, edi; this
0x18000616e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006173  jmp     short loc_1800061CA
0x180006175  test    edi, edi
0x180006177  js      short loc_1800061B1
0x180006179  mov     edi, 8007029Ch
0x18000617e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180006182  mov     rax, [rsp+78h+arg_28]
0x18000618a  mov     [rsp+78h+var_50], rax; __int64
0x18000618f  mov     rax, [rsp+78h+arg_20]
0x180006197  mov     [rsp+78h+var_58], rax; __int64
0x18000619c  mov     rcx, r10; int
0x18000619f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800061a4  mov     [rbx+8], edi
0x1800061a7  mov     ecx, edi; this
0x1800061a9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800061ae  mov     [rbx+0Ch], eax
0x1800061b1  mov     ecx, edi; this
0x1800061b3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800061b8  jmp     short loc_1800061CA
0x1800061ba  mov     ecx, edi; this
0x1800061bc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800061c1  jmp     short loc_1800061CA
0x1800061c3  mov     ecx, edi; this
0x1800061c5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800061ca  mov     ebp, eax
0x1800061cc  mov     [rbx], r15d
0x1800061cf  mov     eax, [rsp+78h+arg_70]
0x1800061d6  mov     [rbx+4], eax
0x1800061d9  cmp     dword ptr [r14+8], 1
0x1800061de  jnz     short loc_1800061E6
0x1800061e0  or      eax, 8
0x1800061e3  mov     [rbx+4], eax
0x1800061e6  mov     eax, 1
0x1800061eb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800061f3  inc     eax
0x1800061f5  mov     [rbx+10h], eax
0x1800061f8  mov     rax, [rsp+78h+arg_40]
0x180006200  xor     edi, edi
0x180006202  test    rax, rax
0x180006205  jz      short loc_18000620C
0x180006207  cmp     [rax], di
0x18000620a  jnz     short loc_18000620F
0x18000620c  mov     rax, rdi
0x18000620f  mov     [rbx+18h], rax
0x180006213  call    cs:__imp_GetCurrentThreadId
0x180006219  mov     [rbx+20h], eax
0x18000621c  mov     [rbx+38h], r13
0x180006220  mov     eax, [rsp+78h+arg_8]
0x180006227  mov     [rbx+40h], eax
0x18000622a  mov     [rbx+44h], ebp
0x18000622d  mov     rax, [rsp+78h+arg_20]
0x180006235  mov     [rbx+28h], rax
0x180006239  mov     [rbx+30h], r12
0x18000623d  mov     rax, [rsp+78h+arg_28]
0x180006245  mov     [rbx+88h], rax
0x18000624c  mov     rax, [rsp+78h+arg_0]
0x180006254  mov     [rbx+90h], rax
0x18000625b  mov     [rbx+48h], rdi
0x18000625f  xorps   xmm0, xmm0
0x180006262  xor     eax, eax
0x180006264  movups  xmmword ptr [rbx+68h], xmm0
0x180006268  mov     [rbx+78h], rax
0x18000626c  movups  xmmword ptr [rbx+50h], xmm0
0x180006270  mov     [rbx+60h], rax
0x180006274  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000627b  test    rax, rax
0x18000627e  jz      short loc_180006287
0x180006280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006285  jmp     short loc_18000628A
0x180006287  mov     rax, rdi
0x18000628a  mov     [rbx+80h], rax
0x180006291  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006298  test    rax, rax
0x18000629b  jz      short loc_1800062A5
0x18000629d  mov     rcx, rbx
0x1800062a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062a5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800062ac  test    rax, rax
0x1800062af  jz      short loc_1800062C7
0x1800062b1  mov     r8d, 400h
0x1800062b7  mov     rdx, [rsp+78h+arg_60]
0x1800062bf  mov     rcx, rbx
0x1800062c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062c7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800062ce  test    rax, rax
0x1800062d1  jz      short loc_1800062DB
0x1800062d3  mov     rcx, rbx
0x1800062d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062db  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800062e2  test    rax, rax
0x1800062e5  jz      short loc_1800062F5
0x1800062e7  test    byte ptr [rbx+4], 2
0x1800062eb  jnz     short loc_1800062F5
0x1800062ed  mov     rcx, rbx
0x1800062f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062f5  cmp     [rbx+8], edi
0x1800062f8  jl      short loc_180006314
0x1800062fa  cmp     r15d, 3
0x1800062fe  jnz     loc_1800063E3
0x180006304  mov     ecx, 8000FFFFh; this
0x180006309  mov     [rbx+8], ecx
0x18000630c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006311  mov     [rbx+0Ch], eax
0x180006314  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000631b  jnz     short loc_18000633C
0x18000631d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006324  test    rax, rax
0x180006327  jz      short loc_180006332
0x180006329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000632e  test    al, al
0x180006330  jmp     short loc_18000633A
0x180006332  call    cs:__imp_IsDebuggerPresent
0x180006338  test    eax, eax
0x18000633a  jz      short loc_180006342
0x18000633c  test    byte ptr [rbx+4], 2
0x180006340  jz      short loc_180006366
0x180006342  mov     rax, cs:g_pfnResultLoggingCallback
0x180006349  test    rax, rax
0x18000634c  jz      short loc_1800063AA
0x18000634e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006355  jnz     short loc_1800063AA
0x180006357  xor     r8d, r8d
0x18000635a  xor     edx, edx
0x18000635c  mov     rcx, rbx
0x18000635f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006364  jmp     short loc_1800063AA
0x180006366  mov     ebp, 800h
0x18000636b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006372  test    rax, rax
0x180006375  jz      short loc_18000638E
0x180006377  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000637e  jnz     short loc_18000638E
0x180006380  mov     r8d, ebp
0x180006383  mov     rdx, rsi
0x180006386  mov     rcx, rbx
0x180006389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000638e  cmp     [rsi], di
0x180006391  jnz     short loc_1800063A1
0x180006393  mov     r8, rbx; unsigned __int64
0x180006396  mov     rdx, rbp; unsigned __int16 *
0x180006399  mov     rcx, rsi; this
0x18000639c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800063a1  mov     rcx, rsi; lpOutputString
0x1800063a4  call    cs:__imp_OutputDebugStringW
0x1800063aa  test    byte ptr [rbx+4], 4
0x1800063ae  jnz     short loc_1800063B9
0x1800063b0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800063b7  jz      short loc_1800063CB
0x1800063b9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800063c0  test    rax, rax
0x1800063c3  jz      short loc_1800063CB
0x1800063c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063ca  nop
0x1800063cb  mov     rbx, [rsp+78h+arg_10]
0x1800063d3  add     rsp, 40h
0x1800063d7  pop     r15
0x1800063d9  pop     r14
0x1800063db  pop     r13
0x1800063dd  pop     r12
0x1800063df  pop     rdi
0x1800063e0  pop     rsi
0x1800063e1  pop     rbp
0x1800063e2  retn
0x1800063e3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
