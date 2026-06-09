# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1400073c8`
- end: `0x1400076c1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x140003bbc`
- `0x140003f00`

## callees

- `0x140003afc`
- `0x1400065b4`
- `0x140006ed4`
- `0x1400073c8`
- `0x140008d84`
- `0x140008da0`
- `0x140008ef0`
- `0x140008f0c`
- `0x14000b134`
- `0x140027010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400074eb`
- `KERNEL32!GetCurrentThreadId` at `0x1400074eb`
- `KERNEL32!OutputDebugStringW` at `0x14000767c`
- `KERNEL32!OutputDebugStringW` at `0x14000767c`
- `KERNEL32!IsDebuggerPresent` at `0x14000760a`
- `KERNEL32!IsDebuggerPresent` at `0x14000760a`

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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
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
0x1400073c8  mov     [rsp+arg_10], rbx
0x1400073cd  mov     [rsp+arg_8], edx
0x1400073d1  mov     [rsp+arg_0], rcx
0x1400073d6  push    rbp
0x1400073d7  push    rsi
0x1400073d8  push    rdi
0x1400073d9  push    r12
0x1400073db  push    r13
0x1400073dd  push    r14
0x1400073df  push    r15
0x1400073e1  sub     rsp, 40h
0x1400073e5  mov     r12, r9
0x1400073e8  mov     r13, r8
0x1400073eb  mov     r10, rcx
0x1400073ee  xor     eax, eax
0x1400073f0  mov     rsi, [rsp+78h+lpOutputString]
0x1400073f8  mov     [rsi], ax
0x1400073fb  mov     rax, [rsp+78h+arg_60]
0x140007403  mov     byte ptr [rax], 0
0x140007406  mov     r14, [rsp+78h+arg_38]
0x14000740e  mov     edi, [r14]
0x140007411  mov     rbx, [rsp+78h+arg_78]
0x140007419  mov     [rbx+8], edi
0x14000741c  mov     eax, [r14+4]
0x140007420  mov     [rbx+0Ch], eax
0x140007423  xor     ebp, ebp
0x140007425  mov     r15d, [rsp+78h+arg_30]
0x14000742d  mov     ecx, r15d
0x140007430  test    r15d, r15d
0x140007433  jz      short loc_14000749B
0x140007435  sub     ecx, 1
0x140007438  jz      short loc_140007492
0x14000743a  sub     ecx, 1
0x14000743d  jz      short loc_14000744D
0x14000743f  cmp     ecx, 1
0x140007442  jnz     short loc_1400074A4
0x140007444  mov     ecx, edi; this
0x140007446  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000744b  jmp     short loc_1400074A2
0x14000744d  test    edi, edi
0x14000744f  js      short loc_140007489
0x140007451  mov     edi, 8007029Ch
0x140007456  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14000745a  mov     rax, [rsp+78h+arg_28]
0x140007462  mov     [rsp+78h+var_50], rax; __int64
0x140007467  mov     rax, [rsp+78h+arg_20]
0x14000746f  mov     [rsp+78h+var_58], rax; __int64
0x140007474  mov     rcx, r10; int
0x140007477  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000747c  mov     [rbx+8], edi
0x14000747f  mov     ecx, edi; this
0x140007481  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140007486  mov     [rbx+0Ch], eax
0x140007489  mov     ecx, edi; this
0x14000748b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140007490  jmp     short loc_1400074A2
0x140007492  mov     ecx, edi; this
0x140007494  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140007499  jmp     short loc_1400074A2
0x14000749b  mov     ecx, edi; this
0x14000749d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1400074a2  mov     ebp, eax
0x1400074a4  mov     [rbx], r15d
0x1400074a7  mov     eax, [rsp+78h+arg_70]
0x1400074ae  mov     [rbx+4], eax
0x1400074b1  cmp     dword ptr [r14+8], 1
0x1400074b6  jnz     short loc_1400074BE
0x1400074b8  or      eax, 8
0x1400074bb  mov     [rbx+4], eax
0x1400074be  mov     eax, 1
0x1400074c3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400074cb  inc     eax
0x1400074cd  mov     [rbx+10h], eax
0x1400074d0  mov     rax, [rsp+78h+arg_40]
0x1400074d8  xor     edi, edi
0x1400074da  test    rax, rax
0x1400074dd  jz      short loc_1400074E4
0x1400074df  cmp     [rax], di
0x1400074e2  jnz     short loc_1400074E7
0x1400074e4  mov     rax, rdi
0x1400074e7  mov     [rbx+18h], rax
0x1400074eb  call    cs:__imp_GetCurrentThreadId
0x1400074f1  mov     [rbx+20h], eax
0x1400074f4  mov     [rbx+38h], r13
0x1400074f8  mov     eax, [rsp+78h+arg_8]
0x1400074ff  mov     [rbx+40h], eax
0x140007502  mov     [rbx+44h], ebp
0x140007505  mov     rax, [rsp+78h+arg_20]
0x14000750d  mov     [rbx+28h], rax
0x140007511  mov     [rbx+30h], r12
0x140007515  mov     rax, [rsp+78h+arg_28]
0x14000751d  mov     [rbx+88h], rax
0x140007524  mov     rax, [rsp+78h+arg_0]
0x14000752c  mov     [rbx+90h], rax
0x140007533  mov     [rbx+48h], rdi
0x140007537  xorps   xmm0, xmm0
0x14000753a  xor     eax, eax
0x14000753c  movups  xmmword ptr [rbx+68h], xmm0
0x140007540  mov     [rbx+78h], rax
0x140007544  movups  xmmword ptr [rbx+50h], xmm0
0x140007548  mov     [rbx+60h], rax
0x14000754c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140007553  test    rax, rax
0x140007556  jz      short loc_14000755F
0x140007558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000755d  jmp     short loc_140007562
0x14000755f  mov     rax, rdi
0x140007562  mov     [rbx+80h], rax
0x140007569  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140007570  test    rax, rax
0x140007573  jz      short loc_14000757D
0x140007575  mov     rcx, rbx
0x140007578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000757d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140007584  test    rax, rax
0x140007587  jz      short loc_14000759F
0x140007589  mov     r8d, 400h
0x14000758f  mov     rdx, [rsp+78h+arg_60]
0x140007597  mov     rcx, rbx
0x14000759a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000759f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400075a6  test    rax, rax
0x1400075a9  jz      short loc_1400075B3
0x1400075ab  mov     rcx, rbx
0x1400075ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400075b3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400075ba  test    rax, rax
0x1400075bd  jz      short loc_1400075CD
0x1400075bf  test    byte ptr [rbx+4], 2
0x1400075c3  jnz     short loc_1400075CD
0x1400075c5  mov     rcx, rbx
0x1400075c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400075cd  cmp     [rbx+8], edi
0x1400075d0  jl      short loc_1400075EC
0x1400075d2  cmp     r15d, 3
0x1400075d6  jnz     loc_1400076BB
0x1400075dc  mov     ecx, 8000FFFFh; this
0x1400075e1  mov     [rbx+8], ecx
0x1400075e4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400075e9  mov     [rbx+0Ch], eax
0x1400075ec  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1400075f3  jnz     short loc_140007614
0x1400075f5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400075fc  test    rax, rax
0x1400075ff  jz      short loc_14000760A
0x140007601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007606  test    al, al
0x140007608  jmp     short loc_140007612
0x14000760a  call    cs:__imp_IsDebuggerPresent
0x140007610  test    eax, eax
0x140007612  jz      short loc_14000761A
0x140007614  test    byte ptr [rbx+4], 2
0x140007618  jz      short loc_14000763E
0x14000761a  mov     rax, cs:g_pfnResultLoggingCallback
0x140007621  test    rax, rax
0x140007624  jz      short loc_140007682
0x140007626  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000762d  jnz     short loc_140007682
0x14000762f  xor     r8d, r8d
0x140007632  xor     edx, edx
0x140007634  mov     rcx, rbx
0x140007637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000763c  jmp     short loc_140007682
0x14000763e  mov     ebp, 800h
0x140007643  mov     rax, cs:g_pfnResultLoggingCallback
0x14000764a  test    rax, rax
0x14000764d  jz      short loc_140007666
0x14000764f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140007656  jnz     short loc_140007666
0x140007658  mov     r8d, ebp
0x14000765b  mov     rdx, rsi
0x14000765e  mov     rcx, rbx
0x140007661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007666  cmp     [rsi], di
0x140007669  jnz     short loc_140007679
0x14000766b  mov     r8, rbx; unsigned __int64
0x14000766e  mov     rdx, rbp; unsigned __int16 *
0x140007671  mov     rcx, rsi; pszDest
0x140007674  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140007679  mov     rcx, rsi; lpOutputString
0x14000767c  call    cs:__imp_OutputDebugStringW
0x140007682  test    byte ptr [rbx+4], 4
0x140007686  jnz     short loc_140007691
0x140007688  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14000768f  jz      short loc_1400076A3
0x140007691  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140007698  test    rax, rax
0x14000769b  jz      short loc_1400076A3
0x14000769d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400076a2  nop
0x1400076a3  mov     rbx, [rsp+78h+arg_10]
0x1400076ab  add     rsp, 40h
0x1400076af  pop     r15
0x1400076b1  pop     r14
0x1400076b3  pop     r13
0x1400076b5  pop     r12
0x1400076b7  pop     rdi
0x1400076b8  pop     rsi
0x1400076b9  pop     rbp
0x1400076ba  retn
0x1400076bb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
