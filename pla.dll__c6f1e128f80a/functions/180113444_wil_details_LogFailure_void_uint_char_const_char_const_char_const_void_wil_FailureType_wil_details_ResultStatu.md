# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180113444`
- end: `0x18011373c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18010ff80`

## callees

- `0x18010c0f0`
- `0x18010f9bc`
- `0x1801128dc`
- `0x180113060`
- `0x180113444`
- `0x1801150a4`
- `0x180115230`
- `0x18011524c`
- `0x180116ebc`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1801136f8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1801136f8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180113686`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180113686`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180113567`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180113567`

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
  int v16; // ebp
  unsigned int v19; // edi
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  DWORD CurrentThreadId; // eax
  int v24; // edx
  wil::details::in1diag3 *v25; // rcx
  const struct wil::FailureInfo *v26; // r9
  __int64 ModuleName; // rax
  bool v28; // zf
  wil::details *v29; // [rsp+30h] [rbp-48h]

  v16 = 0;
  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v19 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v19, a2);
        break;
      case 2:
        if ( (v19 & 0x80000000) == 0 )
        {
          v19 = -2147024228;
          LODWORD(v29) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v29);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
        }
        v20 = wil::details::RecordLog((wil::details *)v19, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v19, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v19, a2);
  }
  v16 = v20;
LABEL_12:
  *(_DWORD *)(a16 + 4) = a15;
  *(_DWORD *)a16 = a7;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 32) = CurrentThreadId;
  *(_DWORD *)(a16 + 64) = a2;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_DWORD *)(a16 + 68) = v16;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v25);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v25) == 0),
        v28)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v26);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v25);
  }
}

```

## disassembly

```asm
0x180113444  mov     [rsp+arg_10], rbx
0x180113449  mov     [rsp+arg_8], edx
0x18011344d  mov     [rsp+arg_0], rcx
0x180113452  push    rbp
0x180113453  push    rsi
0x180113454  push    rdi
0x180113455  push    r12
0x180113457  push    r13
0x180113459  push    r14
0x18011345b  push    r15
0x18011345d  sub     rsp, 40h
0x180113461  mov     r14, [rsp+78h+arg_38]
0x180113469  xor     eax, eax
0x18011346b  mov     rbx, [rsp+78h+arg_78]
0x180113473  xor     ebp, ebp
0x180113475  mov     r15d, [rsp+78h+arg_30]
0x18011347d  mov     r10, rcx
0x180113480  mov     rsi, [rsp+78h+lpOutputString]
0x180113488  mov     r12, r9
0x18011348b  mov     r13, r8
0x18011348e  mov     ecx, r15d
0x180113491  mov     [rsi], ax
0x180113494  mov     rax, [rsp+78h+arg_60]
0x18011349c  mov     byte ptr [rax], 0
0x18011349f  mov     edi, [r14]
0x1801134a2  mov     [rbx+8], edi
0x1801134a5  mov     eax, [r14+4]
0x1801134a9  mov     [rbx+0Ch], eax
0x1801134ac  test    r15d, r15d
0x1801134af  jz      short loc_180113517
0x1801134b1  sub     ecx, 1
0x1801134b4  jz      short loc_18011350E
0x1801134b6  sub     ecx, 1
0x1801134b9  jz      short loc_1801134C9
0x1801134bb  cmp     ecx, 1
0x1801134be  jnz     short loc_180113520
0x1801134c0  mov     ecx, edi; this
0x1801134c2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1801134c7  jmp     short loc_18011351E
0x1801134c9  test    edi, edi
0x1801134cb  js      short loc_180113505
0x1801134cd  mov     rax, [rsp+78h+arg_28]
0x1801134d5  mov     edi, 8007029Ch
0x1801134da  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1801134de  mov     rcx, r10; int
0x1801134e1  mov     [rsp+78h+var_50], rax; __int64
0x1801134e6  mov     rax, [rsp+78h+arg_20]
0x1801134ee  mov     [rsp+78h+var_58], rax; __int64
0x1801134f3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1801134f8  mov     ecx, edi; this
0x1801134fa  mov     [rbx+8], edi
0x1801134fd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180113502  mov     [rbx+0Ch], eax
0x180113505  mov     ecx, edi; this
0x180113507  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18011350c  jmp     short loc_18011351E
0x18011350e  mov     ecx, edi; this
0x180113510  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180113515  jmp     short loc_18011351E
0x180113517  mov     ecx, edi; this
0x180113519  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18011351e  mov     ebp, eax
0x180113520  mov     eax, [rsp+78h+arg_70]
0x180113527  mov     [rbx+4], eax
0x18011352a  mov     [rbx], r15d
0x18011352d  cmp     dword ptr [r14+8], 1
0x180113532  jnz     short loc_18011353A
0x180113534  or      eax, 8
0x180113537  mov     [rbx+4], eax
0x18011353a  mov     eax, 1
0x18011353f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180113547  inc     eax
0x180113549  xor     edi, edi
0x18011354b  mov     [rbx+10h], eax
0x18011354e  mov     rax, [rsp+78h+arg_40]
0x180113556  test    rax, rax
0x180113559  jz      short loc_180113560
0x18011355b  cmp     [rax], di
0x18011355e  jnz     short loc_180113563
0x180113560  mov     rax, rdi
0x180113563  mov     [rbx+18h], rax
0x180113567  call    cs:__imp_GetCurrentThreadId
0x18011356d  mov     [rbx+38h], r13
0x180113571  xorps   xmm0, xmm0
0x180113574  mov     [rbx+20h], eax
0x180113577  mov     eax, [rsp+78h+arg_8]
0x18011357e  mov     [rbx+40h], eax
0x180113581  mov     rax, [rsp+78h+arg_20]
0x180113589  mov     [rbx+28h], rax
0x18011358d  mov     rax, [rsp+78h+arg_28]
0x180113595  mov     [rbx+88h], rax
0x18011359c  mov     rax, [rsp+78h+arg_0]
0x1801135a4  mov     [rbx+90h], rax
0x1801135ab  xor     eax, eax
0x1801135ad  mov     [rbx+44h], ebp
0x1801135b0  mov     [rbx+30h], r12
0x1801135b4  mov     [rbx+48h], rdi
0x1801135b8  movups  xmmword ptr [rbx+68h], xmm0
0x1801135bc  mov     [rbx+78h], rax
0x1801135c0  movups  xmmword ptr [rbx+50h], xmm0
0x1801135c4  mov     [rbx+60h], rax
0x1801135c8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1801135cf  test    rax, rax
0x1801135d2  jz      short loc_1801135DB
0x1801135d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801135d9  jmp     short loc_1801135DE
0x1801135db  mov     rax, rdi
0x1801135de  mov     [rbx+80h], rax
0x1801135e5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1801135ec  test    rax, rax
0x1801135ef  jz      short loc_1801135F9
0x1801135f1  mov     rcx, rbx
0x1801135f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801135f9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180113600  test    rax, rax
0x180113603  jz      short loc_18011361B
0x180113605  mov     rdx, [rsp+78h+arg_60]
0x18011360d  mov     r8d, 400h
0x180113613  mov     rcx, rbx
0x180113616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011361b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180113622  test    rax, rax
0x180113625  jz      short loc_18011362F
0x180113627  mov     rcx, rbx
0x18011362a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011362f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180113636  test    rax, rax
0x180113639  jz      short loc_180113649
0x18011363b  test    byte ptr [rbx+4], 2
0x18011363f  jnz     short loc_180113649
0x180113641  mov     rcx, rbx
0x180113644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113649  cmp     [rbx+8], edi
0x18011364c  jl      short loc_180113668
0x18011364e  cmp     r15d, 3
0x180113652  jnz     loc_180113736
0x180113658  mov     ecx, 8000FFFFh; this
0x18011365d  mov     [rbx+8], ecx
0x180113660  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180113665  mov     [rbx+0Ch], eax
0x180113668  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18011366f  jnz     short loc_180113690
0x180113671  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180113678  test    rax, rax
0x18011367b  jz      short loc_180113686
0x18011367d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113682  test    al, al
0x180113684  jmp     short loc_18011368E
0x180113686  call    cs:__imp_IsDebuggerPresent
0x18011368c  test    eax, eax
0x18011368e  jz      short loc_180113696
0x180113690  test    byte ptr [rbx+4], 2
0x180113694  jz      short loc_1801136BA
0x180113696  mov     rax, cs:g_pfnResultLoggingCallback
0x18011369d  test    rax, rax
0x1801136a0  jz      short loc_1801136FE
0x1801136a2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1801136a9  jnz     short loc_1801136FE
0x1801136ab  xor     r8d, r8d
0x1801136ae  xor     edx, edx
0x1801136b0  mov     rcx, rbx
0x1801136b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801136b8  jmp     short loc_1801136FE
0x1801136ba  mov     rax, cs:g_pfnResultLoggingCallback
0x1801136c1  mov     ebp, 800h
0x1801136c6  test    rax, rax
0x1801136c9  jz      short loc_1801136E2
0x1801136cb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1801136d2  jnz     short loc_1801136E2
0x1801136d4  mov     r8d, ebp
0x1801136d7  mov     rdx, rsi
0x1801136da  mov     rcx, rbx
0x1801136dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801136e2  cmp     [rsi], di
0x1801136e5  jnz     short loc_1801136F5
0x1801136e7  mov     r8, rbx; unsigned __int64
0x1801136ea  mov     rdx, rbp; unsigned __int16 *
0x1801136ed  mov     rcx, rsi; this
0x1801136f0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1801136f5  mov     rcx, rsi; lpOutputString
0x1801136f8  call    cs:__imp_OutputDebugStringW
0x1801136fe  test    byte ptr [rbx+4], 4
0x180113702  jnz     short loc_18011370D
0x180113704  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18011370b  jz      short loc_18011371E
0x18011370d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180113714  test    rax, rax
0x180113717  jz      short loc_18011371E
0x180113719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011371e  mov     rbx, [rsp+78h+arg_10]
0x180113726  add     rsp, 40h
0x18011372a  pop     r15
0x18011372c  pop     r14
0x18011372e  pop     r13
0x180113730  pop     r12
0x180113732  pop     rdi
0x180113733  pop     rsi
0x180113734  pop     rbp
0x180113735  retn
0x180113736  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
