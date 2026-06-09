# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800080f8`
- end: `0x1800083f1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18000441c`
- `0x180004778`

## callees

- `0x180004354`
- `0x1800074e4`
- `0x180007cc4`
- `0x1800080f8`
- `0x18000883c`
- `0x180008860`
- `0x180008874`
- `0x180008890`
- `0x180009728`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000821b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000821b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000833a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000833a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800083ac`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800083ac`

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
0x1800080f8  mov     [rsp+arg_10], rbx
0x1800080fd  mov     [rsp+arg_8], edx
0x180008101  mov     [rsp+arg_0], rcx
0x180008106  push    rbp
0x180008107  push    rsi
0x180008108  push    rdi
0x180008109  push    r12
0x18000810b  push    r13
0x18000810d  push    r14
0x18000810f  push    r15
0x180008111  sub     rsp, 40h
0x180008115  mov     r12, r9
0x180008118  mov     r13, r8
0x18000811b  mov     r10, rcx
0x18000811e  xor     eax, eax
0x180008120  mov     rsi, [rsp+78h+lpOutputString]
0x180008128  mov     [rsi], ax
0x18000812b  mov     rax, [rsp+78h+arg_60]
0x180008133  mov     byte ptr [rax], 0
0x180008136  mov     r14, [rsp+78h+arg_38]
0x18000813e  mov     edi, [r14]
0x180008141  mov     rbx, [rsp+78h+arg_78]
0x180008149  mov     [rbx+8], edi
0x18000814c  mov     eax, [r14+4]
0x180008150  mov     [rbx+0Ch], eax
0x180008153  xor     ebp, ebp
0x180008155  mov     r15d, [rsp+78h+arg_30]
0x18000815d  mov     ecx, r15d
0x180008160  test    r15d, r15d
0x180008163  jz      short loc_1800081CB
0x180008165  sub     ecx, 1
0x180008168  jz      short loc_1800081C2
0x18000816a  sub     ecx, 1
0x18000816d  jz      short loc_18000817D
0x18000816f  cmp     ecx, 1
0x180008172  jnz     short loc_1800081D4
0x180008174  mov     ecx, edi; this
0x180008176  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000817b  jmp     short loc_1800081D2
0x18000817d  test    edi, edi
0x18000817f  js      short loc_1800081B9
0x180008181  mov     edi, 8007029Ch
0x180008186  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000818a  mov     rax, [rsp+78h+arg_28]
0x180008192  mov     [rsp+78h+var_50], rax; __int64
0x180008197  mov     rax, [rsp+78h+arg_20]
0x18000819f  mov     [rsp+78h+var_58], rax; __int64
0x1800081a4  mov     rcx, r10; int
0x1800081a7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800081ac  mov     [rbx+8], edi
0x1800081af  mov     ecx, edi; this
0x1800081b1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800081b6  mov     [rbx+0Ch], eax
0x1800081b9  mov     ecx, edi; this
0x1800081bb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800081c0  jmp     short loc_1800081D2
0x1800081c2  mov     ecx, edi; this
0x1800081c4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800081c9  jmp     short loc_1800081D2
0x1800081cb  mov     ecx, edi; this
0x1800081cd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800081d2  mov     ebp, eax
0x1800081d4  mov     [rbx], r15d
0x1800081d7  mov     eax, [rsp+78h+arg_70]
0x1800081de  mov     [rbx+4], eax
0x1800081e1  cmp     dword ptr [r14+8], 1
0x1800081e6  jnz     short loc_1800081EE
0x1800081e8  or      eax, 8
0x1800081eb  mov     [rbx+4], eax
0x1800081ee  mov     eax, 1
0x1800081f3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800081fb  inc     eax
0x1800081fd  mov     [rbx+10h], eax
0x180008200  mov     rax, [rsp+78h+arg_40]
0x180008208  xor     edi, edi
0x18000820a  test    rax, rax
0x18000820d  jz      short loc_180008214
0x18000820f  cmp     [rax], di
0x180008212  jnz     short loc_180008217
0x180008214  mov     rax, rdi
0x180008217  mov     [rbx+18h], rax
0x18000821b  call    cs:__imp_GetCurrentThreadId
0x180008221  mov     [rbx+20h], eax
0x180008224  mov     [rbx+38h], r13
0x180008228  mov     eax, [rsp+78h+arg_8]
0x18000822f  mov     [rbx+40h], eax
0x180008232  mov     [rbx+44h], ebp
0x180008235  mov     rax, [rsp+78h+arg_20]
0x18000823d  mov     [rbx+28h], rax
0x180008241  mov     [rbx+30h], r12
0x180008245  mov     rax, [rsp+78h+arg_28]
0x18000824d  mov     [rbx+88h], rax
0x180008254  mov     rax, [rsp+78h+arg_0]
0x18000825c  mov     [rbx+90h], rax
0x180008263  mov     [rbx+48h], rdi
0x180008267  xorps   xmm0, xmm0
0x18000826a  xor     eax, eax
0x18000826c  movups  xmmword ptr [rbx+68h], xmm0
0x180008270  mov     [rbx+78h], rax
0x180008274  movups  xmmword ptr [rbx+50h], xmm0
0x180008278  mov     [rbx+60h], rax
0x18000827c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008283  test    rax, rax
0x180008286  jz      short loc_18000828F
0x180008288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000828d  jmp     short loc_180008292
0x18000828f  mov     rax, rdi
0x180008292  mov     [rbx+80h], rax
0x180008299  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800082a0  test    rax, rax
0x1800082a3  jz      short loc_1800082AD
0x1800082a5  mov     rcx, rbx
0x1800082a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082ad  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800082b4  test    rax, rax
0x1800082b7  jz      short loc_1800082CF
0x1800082b9  mov     r8d, 400h
0x1800082bf  mov     rdx, [rsp+78h+arg_60]
0x1800082c7  mov     rcx, rbx
0x1800082ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082cf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800082d6  test    rax, rax
0x1800082d9  jz      short loc_1800082E3
0x1800082db  mov     rcx, rbx
0x1800082de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082e3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800082ea  test    rax, rax
0x1800082ed  jz      short loc_1800082FD
0x1800082ef  test    byte ptr [rbx+4], 2
0x1800082f3  jnz     short loc_1800082FD
0x1800082f5  mov     rcx, rbx
0x1800082f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082fd  cmp     [rbx+8], edi
0x180008300  jl      short loc_18000831C
0x180008302  cmp     r15d, 3
0x180008306  jnz     loc_1800083EB
0x18000830c  mov     ecx, 8000FFFFh; this
0x180008311  mov     [rbx+8], ecx
0x180008314  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008319  mov     [rbx+0Ch], eax
0x18000831c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180008323  jnz     short loc_180008344
0x180008325  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000832c  test    rax, rax
0x18000832f  jz      short loc_18000833A
0x180008331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008336  test    al, al
0x180008338  jmp     short loc_180008342
0x18000833a  call    cs:__imp_IsDebuggerPresent
0x180008340  test    eax, eax
0x180008342  jz      short loc_18000834A
0x180008344  test    byte ptr [rbx+4], 2
0x180008348  jz      short loc_18000836E
0x18000834a  mov     rax, cs:g_pfnResultLoggingCallback
0x180008351  test    rax, rax
0x180008354  jz      short loc_1800083B2
0x180008356  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000835d  jnz     short loc_1800083B2
0x18000835f  xor     r8d, r8d
0x180008362  xor     edx, edx
0x180008364  mov     rcx, rbx
0x180008367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000836c  jmp     short loc_1800083B2
0x18000836e  mov     ebp, 800h
0x180008373  mov     rax, cs:g_pfnResultLoggingCallback
0x18000837a  test    rax, rax
0x18000837d  jz      short loc_180008396
0x18000837f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008386  jnz     short loc_180008396
0x180008388  mov     r8d, ebp
0x18000838b  mov     rdx, rsi
0x18000838e  mov     rcx, rbx
0x180008391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008396  cmp     [rsi], di
0x180008399  jnz     short loc_1800083A9
0x18000839b  mov     r8, rbx; unsigned __int64
0x18000839e  mov     rdx, rbp; wchar_t *
0x1800083a1  mov     rcx, rsi; this
0x1800083a4  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800083a9  mov     rcx, rsi; lpOutputString
0x1800083ac  call    cs:__imp_OutputDebugStringW
0x1800083b2  test    byte ptr [rbx+4], 4
0x1800083b6  jnz     short loc_1800083C1
0x1800083b8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800083bf  jz      short loc_1800083D3
0x1800083c1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800083c8  test    rax, rax
0x1800083cb  jz      short loc_1800083D3
0x1800083cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083d2  nop
0x1800083d3  mov     rbx, [rsp+78h+arg_10]
0x1800083db  add     rsp, 40h
0x1800083df  pop     r15
0x1800083e1  pop     r14
0x1800083e3  pop     r13
0x1800083e5  pop     r12
0x1800083e7  pop     rdi
0x1800083e8  pop     rsi
0x1800083e9  pop     rbp
0x1800083ea  retn
0x1800083eb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
