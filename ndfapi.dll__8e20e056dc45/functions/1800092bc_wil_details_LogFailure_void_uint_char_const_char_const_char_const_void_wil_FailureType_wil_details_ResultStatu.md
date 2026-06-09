# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800092bc`
- end: `0x1800095b5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180007dbc`

## callees

- `0x180002f94`
- `0x18000337c`
- `0x1800036e0`
- `0x180007aa0`
- `0x1800092bc`
- `0x18000985c`
- `0x180009878`
- `0x180009894`
- `0x180009efc`
- `0x180021010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800093df`
- `KERNEL32!GetCurrentThreadId` at `0x1800093df`
- `KERNEL32!OutputDebugStringW` at `0x180009570`
- `KERNEL32!OutputDebugStringW` at `0x180009570`
- `KERNEL32!IsDebuggerPresent` at `0x1800094fe`
- `KERNEL32!IsDebuggerPresent` at `0x1800094fe`

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
  wil::details *v26; // [rsp+30h] [rbp-48h]

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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
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
0x1800092bc  mov     [rsp+arg_10], rbx
0x1800092c1  mov     [rsp+arg_8], edx
0x1800092c5  mov     [rsp+arg_0], rcx
0x1800092ca  push    rbp
0x1800092cb  push    rsi
0x1800092cc  push    rdi
0x1800092cd  push    r12
0x1800092cf  push    r13
0x1800092d1  push    r14
0x1800092d3  push    r15
0x1800092d5  sub     rsp, 40h
0x1800092d9  mov     r12, r9
0x1800092dc  mov     r13, r8
0x1800092df  mov     r10, rcx
0x1800092e2  xor     eax, eax
0x1800092e4  mov     rsi, [rsp+78h+lpOutputString]
0x1800092ec  mov     [rsi], ax
0x1800092ef  mov     rax, [rsp+78h+arg_60]
0x1800092f7  mov     byte ptr [rax], 0
0x1800092fa  mov     r14, [rsp+78h+arg_38]
0x180009302  mov     edi, [r14]
0x180009305  mov     rbx, [rsp+78h+arg_78]
0x18000930d  mov     [rbx+8], edi
0x180009310  mov     eax, [r14+4]
0x180009314  mov     [rbx+0Ch], eax
0x180009317  xor     ebp, ebp
0x180009319  mov     r15d, [rsp+78h+arg_30]
0x180009321  mov     ecx, r15d
0x180009324  test    r15d, r15d
0x180009327  jz      short loc_18000938F
0x180009329  sub     ecx, 1
0x18000932c  jz      short loc_180009386
0x18000932e  sub     ecx, 1
0x180009331  jz      short loc_180009341
0x180009333  cmp     ecx, 1
0x180009336  jnz     short loc_180009398
0x180009338  mov     ecx, edi; this
0x18000933a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000933f  jmp     short loc_180009396
0x180009341  test    edi, edi
0x180009343  js      short loc_18000937D
0x180009345  mov     edi, 8007029Ch
0x18000934a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000934e  mov     rax, [rsp+78h+arg_28]
0x180009356  mov     [rsp+78h+var_50], rax; __int64
0x18000935b  mov     rax, [rsp+78h+arg_20]
0x180009363  mov     [rsp+78h+var_58], rax; __int64
0x180009368  mov     rcx, r10; int
0x18000936b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180009370  mov     [rbx+8], edi
0x180009373  mov     ecx, edi; this
0x180009375  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000937a  mov     [rbx+0Ch], eax
0x18000937d  mov     ecx, edi; this
0x18000937f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180009384  jmp     short loc_180009396
0x180009386  mov     ecx, edi; this
0x180009388  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000938d  jmp     short loc_180009396
0x18000938f  mov     ecx, edi; this
0x180009391  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180009396  mov     ebp, eax
0x180009398  mov     [rbx], r15d
0x18000939b  mov     eax, [rsp+78h+arg_70]
0x1800093a2  mov     [rbx+4], eax
0x1800093a5  cmp     dword ptr [r14+8], 1
0x1800093aa  jnz     short loc_1800093B2
0x1800093ac  or      eax, 8
0x1800093af  mov     [rbx+4], eax
0x1800093b2  mov     eax, 1
0x1800093b7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800093bf  inc     eax
0x1800093c1  mov     [rbx+10h], eax
0x1800093c4  mov     rax, [rsp+78h+arg_40]
0x1800093cc  xor     edi, edi
0x1800093ce  test    rax, rax
0x1800093d1  jz      short loc_1800093D8
0x1800093d3  cmp     [rax], di
0x1800093d6  jnz     short loc_1800093DB
0x1800093d8  mov     rax, rdi
0x1800093db  mov     [rbx+18h], rax
0x1800093df  call    cs:__imp_GetCurrentThreadId
0x1800093e5  mov     [rbx+20h], eax
0x1800093e8  mov     [rbx+38h], r13
0x1800093ec  mov     eax, [rsp+78h+arg_8]
0x1800093f3  mov     [rbx+40h], eax
0x1800093f6  mov     [rbx+44h], ebp
0x1800093f9  mov     rax, [rsp+78h+arg_20]
0x180009401  mov     [rbx+28h], rax
0x180009405  mov     [rbx+30h], r12
0x180009409  mov     rax, [rsp+78h+arg_28]
0x180009411  mov     [rbx+88h], rax
0x180009418  mov     rax, [rsp+78h+arg_0]
0x180009420  mov     [rbx+90h], rax
0x180009427  mov     [rbx+48h], rdi
0x18000942b  xorps   xmm0, xmm0
0x18000942e  xor     eax, eax
0x180009430  movups  xmmword ptr [rbx+68h], xmm0
0x180009434  mov     [rbx+78h], rax
0x180009438  movups  xmmword ptr [rbx+50h], xmm0
0x18000943c  mov     [rbx+60h], rax
0x180009440  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180009447  test    rax, rax
0x18000944a  jz      short loc_180009453
0x18000944c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009451  jmp     short loc_180009456
0x180009453  mov     rax, rdi
0x180009456  mov     [rbx+80h], rax
0x18000945d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009464  test    rax, rax
0x180009467  jz      short loc_180009471
0x180009469  mov     rcx, rbx
0x18000946c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009471  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009478  test    rax, rax
0x18000947b  jz      short loc_180009493
0x18000947d  mov     r8d, 400h
0x180009483  mov     rdx, [rsp+78h+arg_60]
0x18000948b  mov     rcx, rbx
0x18000948e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009493  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000949a  test    rax, rax
0x18000949d  jz      short loc_1800094A7
0x18000949f  mov     rcx, rbx
0x1800094a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094a7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800094ae  test    rax, rax
0x1800094b1  jz      short loc_1800094C1
0x1800094b3  test    byte ptr [rbx+4], 2
0x1800094b7  jnz     short loc_1800094C1
0x1800094b9  mov     rcx, rbx
0x1800094bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094c1  cmp     [rbx+8], edi
0x1800094c4  jl      short loc_1800094E0
0x1800094c6  cmp     r15d, 3
0x1800094ca  jnz     loc_1800095AF
0x1800094d0  mov     ecx, 8000FFFFh; this
0x1800094d5  mov     [rbx+8], ecx
0x1800094d8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800094dd  mov     [rbx+0Ch], eax
0x1800094e0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800094e7  jnz     short loc_180009508
0x1800094e9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800094f0  test    rax, rax
0x1800094f3  jz      short loc_1800094FE
0x1800094f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094fa  test    al, al
0x1800094fc  jmp     short loc_180009506
0x1800094fe  call    cs:__imp_IsDebuggerPresent
0x180009504  test    eax, eax
0x180009506  jz      short loc_18000950E
0x180009508  test    byte ptr [rbx+4], 2
0x18000950c  jz      short loc_180009532
0x18000950e  mov     rax, cs:g_pfnResultLoggingCallback
0x180009515  test    rax, rax
0x180009518  jz      short loc_180009576
0x18000951a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180009521  jnz     short loc_180009576
0x180009523  xor     r8d, r8d
0x180009526  xor     edx, edx
0x180009528  mov     rcx, rbx
0x18000952b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009530  jmp     short loc_180009576
0x180009532  mov     ebp, 800h
0x180009537  mov     rax, cs:g_pfnResultLoggingCallback
0x18000953e  test    rax, rax
0x180009541  jz      short loc_18000955A
0x180009543  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000954a  jnz     short loc_18000955A
0x18000954c  mov     r8d, ebp
0x18000954f  mov     rdx, rsi
0x180009552  mov     rcx, rbx
0x180009555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000955a  cmp     [rsi], di
0x18000955d  jnz     short loc_18000956D
0x18000955f  mov     r8, rbx; unsigned __int64
0x180009562  mov     rdx, rbp; unsigned __int16 *
0x180009565  mov     rcx, rsi; this
0x180009568  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000956d  mov     rcx, rsi; lpOutputString
0x180009570  call    cs:__imp_OutputDebugStringW
0x180009576  test    byte ptr [rbx+4], 4
0x18000957a  jnz     short loc_180009585
0x18000957c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180009583  jz      short loc_180009597
0x180009585  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000958c  test    rax, rax
0x18000958f  jz      short loc_180009597
0x180009591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009596  nop
0x180009597  mov     rbx, [rsp+78h+arg_10]
0x18000959f  add     rsp, 40h
0x1800095a3  pop     r15
0x1800095a5  pop     r14
0x1800095a7  pop     r13
0x1800095a9  pop     r12
0x1800095ab  pop     rdi
0x1800095ac  pop     rsi
0x1800095ad  pop     rbp
0x1800095ae  retn
0x1800095af  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
