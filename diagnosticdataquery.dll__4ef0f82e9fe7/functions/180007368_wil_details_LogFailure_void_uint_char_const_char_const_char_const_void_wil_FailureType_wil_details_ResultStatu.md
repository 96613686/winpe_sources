# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180007368`
- end: `0x180007661`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, WCHAR *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180005b30`

## callees

- `0x180005574`
- `0x180006a04`
- `0x1800071a4`
- `0x180007368`
- `0x1800078cc`
- `0x1800078f0`
- `0x180007904`
- `0x180007920`
- `0x18000893c`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000748b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000748b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000761c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000761c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800075aa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800075aa`

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
  _WORD *v21; // rax
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-48h]

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
    if ( !*lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
    OutputDebugStringW(lpOutputString);
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
0x180007368  mov     [rsp+arg_10], rbx
0x18000736d  mov     [rsp+arg_8], edx
0x180007371  mov     [rsp+arg_0], rcx
0x180007376  push    rbp
0x180007377  push    rsi
0x180007378  push    rdi
0x180007379  push    r12
0x18000737b  push    r13
0x18000737d  push    r14
0x18000737f  push    r15
0x180007381  sub     rsp, 40h
0x180007385  mov     r12, r9
0x180007388  mov     r13, r8
0x18000738b  mov     r10, rcx
0x18000738e  xor     eax, eax
0x180007390  mov     rsi, [rsp+78h+lpOutputString]
0x180007398  mov     [rsi], ax
0x18000739b  mov     rax, [rsp+78h+arg_60]
0x1800073a3  mov     byte ptr [rax], 0
0x1800073a6  mov     r14, [rsp+78h+arg_38]
0x1800073ae  mov     edi, [r14]
0x1800073b1  mov     rbx, [rsp+78h+arg_78]
0x1800073b9  mov     [rbx+8], edi
0x1800073bc  mov     eax, [r14+4]
0x1800073c0  mov     [rbx+0Ch], eax
0x1800073c3  xor     ebp, ebp
0x1800073c5  mov     r15d, [rsp+78h+arg_30]
0x1800073cd  mov     ecx, r15d
0x1800073d0  test    r15d, r15d
0x1800073d3  jz      short loc_18000743B
0x1800073d5  sub     ecx, 1
0x1800073d8  jz      short loc_180007432
0x1800073da  sub     ecx, 1
0x1800073dd  jz      short loc_1800073ED
0x1800073df  cmp     ecx, 1
0x1800073e2  jnz     short loc_180007444
0x1800073e4  mov     ecx, edi; this
0x1800073e6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800073eb  jmp     short loc_180007442
0x1800073ed  test    edi, edi
0x1800073ef  js      short loc_180007429
0x1800073f1  mov     edi, 8007029Ch
0x1800073f6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800073fa  mov     rax, [rsp+78h+arg_28]
0x180007402  mov     [rsp+78h+var_50], rax; __int64
0x180007407  mov     rax, [rsp+78h+arg_20]
0x18000740f  mov     [rsp+78h+var_58], rax; __int64
0x180007414  mov     rcx, r10; int
0x180007417  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000741c  mov     [rbx+8], edi
0x18000741f  mov     ecx, edi; this
0x180007421  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007426  mov     [rbx+0Ch], eax
0x180007429  mov     ecx, edi; this
0x18000742b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180007430  jmp     short loc_180007442
0x180007432  mov     ecx, edi; this
0x180007434  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007439  jmp     short loc_180007442
0x18000743b  mov     ecx, edi; this
0x18000743d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180007442  mov     ebp, eax
0x180007444  mov     [rbx], r15d
0x180007447  mov     eax, [rsp+78h+arg_70]
0x18000744e  mov     [rbx+4], eax
0x180007451  cmp     dword ptr [r14+8], 1
0x180007456  jnz     short loc_18000745E
0x180007458  or      eax, 8
0x18000745b  mov     [rbx+4], eax
0x18000745e  mov     eax, 1
0x180007463  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000746b  inc     eax
0x18000746d  mov     [rbx+10h], eax
0x180007470  mov     rax, [rsp+78h+arg_40]
0x180007478  xor     edi, edi
0x18000747a  test    rax, rax
0x18000747d  jz      short loc_180007484
0x18000747f  cmp     [rax], di
0x180007482  jnz     short loc_180007487
0x180007484  mov     rax, rdi
0x180007487  mov     [rbx+18h], rax
0x18000748b  call    cs:__imp_GetCurrentThreadId
0x180007491  mov     [rbx+20h], eax
0x180007494  mov     [rbx+38h], r13
0x180007498  mov     eax, [rsp+78h+arg_8]
0x18000749f  mov     [rbx+40h], eax
0x1800074a2  mov     [rbx+44h], ebp
0x1800074a5  mov     rax, [rsp+78h+arg_20]
0x1800074ad  mov     [rbx+28h], rax
0x1800074b1  mov     [rbx+30h], r12
0x1800074b5  mov     rax, [rsp+78h+arg_28]
0x1800074bd  mov     [rbx+88h], rax
0x1800074c4  mov     rax, [rsp+78h+arg_0]
0x1800074cc  mov     [rbx+90h], rax
0x1800074d3  mov     [rbx+48h], rdi
0x1800074d7  xorps   xmm0, xmm0
0x1800074da  xor     eax, eax
0x1800074dc  movups  xmmword ptr [rbx+68h], xmm0
0x1800074e0  mov     [rbx+78h], rax
0x1800074e4  movups  xmmword ptr [rbx+50h], xmm0
0x1800074e8  mov     [rbx+60h], rax
0x1800074ec  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800074f3  test    rax, rax
0x1800074f6  jz      short loc_1800074FF
0x1800074f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074fd  jmp     short loc_180007502
0x1800074ff  mov     rax, rdi
0x180007502  mov     [rbx+80h], rax
0x180007509  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007510  test    rax, rax
0x180007513  jz      short loc_18000751D
0x180007515  mov     rcx, rbx
0x180007518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000751d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007524  test    rax, rax
0x180007527  jz      short loc_18000753F
0x180007529  mov     r8d, 400h
0x18000752f  mov     rdx, [rsp+78h+arg_60]
0x180007537  mov     rcx, rbx
0x18000753a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000753f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007546  test    rax, rax
0x180007549  jz      short loc_180007553
0x18000754b  mov     rcx, rbx
0x18000754e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007553  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000755a  test    rax, rax
0x18000755d  jz      short loc_18000756D
0x18000755f  test    byte ptr [rbx+4], 2
0x180007563  jnz     short loc_18000756D
0x180007565  mov     rcx, rbx
0x180007568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000756d  cmp     [rbx+8], edi
0x180007570  jl      short loc_18000758C
0x180007572  cmp     r15d, 3
0x180007576  jnz     loc_18000765B
0x18000757c  mov     ecx, 8000FFFFh; this
0x180007581  mov     [rbx+8], ecx
0x180007584  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007589  mov     [rbx+0Ch], eax
0x18000758c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180007593  jnz     short loc_1800075B4
0x180007595  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000759c  test    rax, rax
0x18000759f  jz      short loc_1800075AA
0x1800075a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075a6  test    al, al
0x1800075a8  jmp     short loc_1800075B2
0x1800075aa  call    cs:__imp_IsDebuggerPresent
0x1800075b0  test    eax, eax
0x1800075b2  jz      short loc_1800075BA
0x1800075b4  test    byte ptr [rbx+4], 2
0x1800075b8  jz      short loc_1800075DE
0x1800075ba  mov     rax, cs:g_pfnResultLoggingCallback
0x1800075c1  test    rax, rax
0x1800075c4  jz      short loc_180007622
0x1800075c6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800075cd  jnz     short loc_180007622
0x1800075cf  xor     r8d, r8d
0x1800075d2  xor     edx, edx
0x1800075d4  mov     rcx, rbx
0x1800075d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075dc  jmp     short loc_180007622
0x1800075de  mov     ebp, 800h
0x1800075e3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800075ea  test    rax, rax
0x1800075ed  jz      short loc_180007606
0x1800075ef  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800075f6  jnz     short loc_180007606
0x1800075f8  mov     r8d, ebp
0x1800075fb  mov     rdx, rsi
0x1800075fe  mov     rcx, rbx
0x180007601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007606  cmp     [rsi], di
0x180007609  jnz     short loc_180007619
0x18000760b  mov     r8, rbx; unsigned __int64
0x18000760e  mov     rdx, rbp; unsigned __int16 *
0x180007611  mov     rcx, rsi; Buffer
0x180007614  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007619  mov     rcx, rsi; lpOutputString
0x18000761c  call    cs:__imp_OutputDebugStringW
0x180007622  test    byte ptr [rbx+4], 4
0x180007626  jnz     short loc_180007631
0x180007628  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000762f  jz      short loc_180007643
0x180007631  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007638  test    rax, rax
0x18000763b  jz      short loc_180007643
0x18000763d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007642  nop
0x180007643  mov     rbx, [rsp+78h+arg_10]
0x18000764b  add     rsp, 40h
0x18000764f  pop     r15
0x180007651  pop     r14
0x180007653  pop     r13
0x180007655  pop     r12
0x180007657  pop     rdi
0x180007658  pop     rsi
0x180007659  pop     rbp
0x18000765a  retn
0x18000765b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
