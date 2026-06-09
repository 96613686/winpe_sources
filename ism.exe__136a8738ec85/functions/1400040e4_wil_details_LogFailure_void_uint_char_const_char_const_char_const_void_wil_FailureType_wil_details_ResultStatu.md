# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1400040e4`
- end: `0x1400043dd`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140002804`

## callees

- `0x1400020a4`
- `0x140003784`
- `0x140003f20`
- `0x1400040e4`
- `0x1400046c8`
- `0x1400046f0`
- `0x140004704`
- `0x140004720`
- `0x14000579c`
- `0x140006010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004207`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004207`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004398`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004398`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004326`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004326`

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
0x1400040e4  mov     [rsp+arg_10], rbx
0x1400040e9  mov     [rsp+arg_8], edx
0x1400040ed  mov     [rsp+arg_0], rcx
0x1400040f2  push    rbp
0x1400040f3  push    rsi
0x1400040f4  push    rdi
0x1400040f5  push    r12
0x1400040f7  push    r13
0x1400040f9  push    r14
0x1400040fb  push    r15
0x1400040fd  sub     rsp, 40h
0x140004101  mov     r12, r9
0x140004104  mov     r13, r8
0x140004107  mov     r10, rcx
0x14000410a  xor     eax, eax
0x14000410c  mov     rsi, [rsp+78h+lpOutputString]
0x140004114  mov     [rsi], ax
0x140004117  mov     rax, [rsp+78h+arg_60]
0x14000411f  mov     byte ptr [rax], 0
0x140004122  mov     r14, [rsp+78h+arg_38]
0x14000412a  mov     edi, [r14]
0x14000412d  mov     rbx, [rsp+78h+arg_78]
0x140004135  mov     [rbx+8], edi
0x140004138  mov     eax, [r14+4]
0x14000413c  mov     [rbx+0Ch], eax
0x14000413f  xor     ebp, ebp
0x140004141  mov     r15d, [rsp+78h+arg_30]
0x140004149  mov     ecx, r15d
0x14000414c  test    r15d, r15d
0x14000414f  jz      short loc_1400041B7
0x140004151  sub     ecx, 1
0x140004154  jz      short loc_1400041AE
0x140004156  sub     ecx, 1
0x140004159  jz      short loc_140004169
0x14000415b  cmp     ecx, 1
0x14000415e  jnz     short loc_1400041C0
0x140004160  mov     ecx, edi; this
0x140004162  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140004167  jmp     short loc_1400041BE
0x140004169  test    edi, edi
0x14000416b  js      short loc_1400041A5
0x14000416d  mov     edi, 8007029Ch
0x140004172  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140004176  mov     rax, [rsp+78h+arg_28]
0x14000417e  mov     [rsp+78h+var_50], rax; __int64
0x140004183  mov     rax, [rsp+78h+arg_20]
0x14000418b  mov     [rsp+78h+var_58], rax; __int64
0x140004190  mov     rcx, r10; int
0x140004193  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140004198  mov     [rbx+8], edi
0x14000419b  mov     ecx, edi; this
0x14000419d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400041a2  mov     [rbx+0Ch], eax
0x1400041a5  mov     ecx, edi; this
0x1400041a7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1400041ac  jmp     short loc_1400041BE
0x1400041ae  mov     ecx, edi; this
0x1400041b0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400041b5  jmp     short loc_1400041BE
0x1400041b7  mov     ecx, edi; this
0x1400041b9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1400041be  mov     ebp, eax
0x1400041c0  mov     [rbx], r15d
0x1400041c3  mov     eax, [rsp+78h+arg_70]
0x1400041ca  mov     [rbx+4], eax
0x1400041cd  cmp     dword ptr [r14+8], 1
0x1400041d2  jnz     short loc_1400041DA
0x1400041d4  or      eax, 8
0x1400041d7  mov     [rbx+4], eax
0x1400041da  mov     eax, 1
0x1400041df  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400041e7  inc     eax
0x1400041e9  mov     [rbx+10h], eax
0x1400041ec  mov     rax, [rsp+78h+arg_40]
0x1400041f4  xor     edi, edi
0x1400041f6  test    rax, rax
0x1400041f9  jz      short loc_140004200
0x1400041fb  cmp     [rax], di
0x1400041fe  jnz     short loc_140004203
0x140004200  mov     rax, rdi
0x140004203  mov     [rbx+18h], rax
0x140004207  call    cs:__imp_GetCurrentThreadId
0x14000420d  mov     [rbx+20h], eax
0x140004210  mov     [rbx+38h], r13
0x140004214  mov     eax, [rsp+78h+arg_8]
0x14000421b  mov     [rbx+40h], eax
0x14000421e  mov     [rbx+44h], ebp
0x140004221  mov     rax, [rsp+78h+arg_20]
0x140004229  mov     [rbx+28h], rax
0x14000422d  mov     [rbx+30h], r12
0x140004231  mov     rax, [rsp+78h+arg_28]
0x140004239  mov     [rbx+88h], rax
0x140004240  mov     rax, [rsp+78h+arg_0]
0x140004248  mov     [rbx+90h], rax
0x14000424f  mov     [rbx+48h], rdi
0x140004253  xorps   xmm0, xmm0
0x140004256  xor     eax, eax
0x140004258  movups  xmmword ptr [rbx+68h], xmm0
0x14000425c  mov     [rbx+78h], rax
0x140004260  movups  xmmword ptr [rbx+50h], xmm0
0x140004264  mov     [rbx+60h], rax
0x140004268  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000426f  test    rax, rax
0x140004272  jz      short loc_14000427B
0x140004274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004279  jmp     short loc_14000427E
0x14000427b  mov     rax, rdi
0x14000427e  mov     [rbx+80h], rax
0x140004285  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000428c  test    rax, rax
0x14000428f  jz      short loc_140004299
0x140004291  mov     rcx, rbx
0x140004294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004299  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400042a0  test    rax, rax
0x1400042a3  jz      short loc_1400042BB
0x1400042a5  mov     r8d, 400h
0x1400042ab  mov     rdx, [rsp+78h+arg_60]
0x1400042b3  mov     rcx, rbx
0x1400042b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400042bb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400042c2  test    rax, rax
0x1400042c5  jz      short loc_1400042CF
0x1400042c7  mov     rcx, rbx
0x1400042ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400042cf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400042d6  test    rax, rax
0x1400042d9  jz      short loc_1400042E9
0x1400042db  test    byte ptr [rbx+4], 2
0x1400042df  jnz     short loc_1400042E9
0x1400042e1  mov     rcx, rbx
0x1400042e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400042e9  cmp     [rbx+8], edi
0x1400042ec  jl      short loc_140004308
0x1400042ee  cmp     r15d, 3
0x1400042f2  jnz     loc_1400043D7
0x1400042f8  mov     ecx, 8000FFFFh; this
0x1400042fd  mov     [rbx+8], ecx
0x140004300  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004305  mov     [rbx+0Ch], eax
0x140004308  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14000430f  jnz     short loc_140004330
0x140004311  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140004318  test    rax, rax
0x14000431b  jz      short loc_140004326
0x14000431d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004322  test    al, al
0x140004324  jmp     short loc_14000432E
0x140004326  call    cs:__imp_IsDebuggerPresent
0x14000432c  test    eax, eax
0x14000432e  jz      short loc_140004336
0x140004330  test    byte ptr [rbx+4], 2
0x140004334  jz      short loc_14000435A
0x140004336  mov     rax, cs:g_pfnResultLoggingCallback
0x14000433d  test    rax, rax
0x140004340  jz      short loc_14000439E
0x140004342  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140004349  jnz     short loc_14000439E
0x14000434b  xor     r8d, r8d
0x14000434e  xor     edx, edx
0x140004350  mov     rcx, rbx
0x140004353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004358  jmp     short loc_14000439E
0x14000435a  mov     ebp, 800h
0x14000435f  mov     rax, cs:g_pfnResultLoggingCallback
0x140004366  test    rax, rax
0x140004369  jz      short loc_140004382
0x14000436b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140004372  jnz     short loc_140004382
0x140004374  mov     r8d, ebp
0x140004377  mov     rdx, rsi
0x14000437a  mov     rcx, rbx
0x14000437d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004382  cmp     [rsi], di
0x140004385  jnz     short loc_140004395
0x140004387  mov     r8, rbx; unsigned __int64
0x14000438a  mov     rdx, rbp; unsigned __int16 *
0x14000438d  mov     rcx, rsi; this
0x140004390  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140004395  mov     rcx, rsi; lpOutputString
0x140004398  call    cs:__imp_OutputDebugStringW
0x14000439e  test    byte ptr [rbx+4], 4
0x1400043a2  jnz     short loc_1400043AD
0x1400043a4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1400043ab  jz      short loc_1400043BF
0x1400043ad  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400043b4  test    rax, rax
0x1400043b7  jz      short loc_1400043BF
0x1400043b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400043be  nop
0x1400043bf  mov     rbx, [rsp+78h+arg_10]
0x1400043c7  add     rsp, 40h
0x1400043cb  pop     r15
0x1400043cd  pop     r14
0x1400043cf  pop     r13
0x1400043d1  pop     r12
0x1400043d3  pop     rdi
0x1400043d4  pop     rsi
0x1400043d5  pop     rbp
0x1400043d6  retn
0x1400043d7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
