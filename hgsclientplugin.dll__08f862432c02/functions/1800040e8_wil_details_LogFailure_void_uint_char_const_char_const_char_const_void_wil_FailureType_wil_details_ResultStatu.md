# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800040e8`
- end: `0x1800043e1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800028a0`

## callees

- `0x1800022ac`
- `0x180003784`
- `0x180003f24`
- `0x1800040e8`
- `0x180004674`
- `0x180004690`
- `0x1800046a4`
- `0x1800046c0`
- `0x18000581c`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000420b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000420b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000439c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000439c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000432a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000432a`

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
0x1800040e8  mov     [rsp+arg_10], rbx
0x1800040ed  mov     [rsp+arg_8], edx
0x1800040f1  mov     [rsp+arg_0], rcx
0x1800040f6  push    rbp
0x1800040f7  push    rsi
0x1800040f8  push    rdi
0x1800040f9  push    r12
0x1800040fb  push    r13
0x1800040fd  push    r14
0x1800040ff  push    r15
0x180004101  sub     rsp, 40h
0x180004105  mov     r12, r9
0x180004108  mov     r13, r8
0x18000410b  mov     r10, rcx
0x18000410e  xor     eax, eax
0x180004110  mov     rsi, [rsp+78h+lpOutputString]
0x180004118  mov     [rsi], ax
0x18000411b  mov     rax, [rsp+78h+arg_60]
0x180004123  mov     byte ptr [rax], 0
0x180004126  mov     r14, [rsp+78h+arg_38]
0x18000412e  mov     edi, [r14]
0x180004131  mov     rbx, [rsp+78h+arg_78]
0x180004139  mov     [rbx+8], edi
0x18000413c  mov     eax, [r14+4]
0x180004140  mov     [rbx+0Ch], eax
0x180004143  xor     ebp, ebp
0x180004145  mov     r15d, [rsp+78h+arg_30]
0x18000414d  mov     ecx, r15d
0x180004150  test    r15d, r15d
0x180004153  jz      short loc_1800041BB
0x180004155  sub     ecx, 1
0x180004158  jz      short loc_1800041B2
0x18000415a  sub     ecx, 1
0x18000415d  jz      short loc_18000416D
0x18000415f  cmp     ecx, 1
0x180004162  jnz     short loc_1800041C4
0x180004164  mov     ecx, edi; this
0x180004166  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000416b  jmp     short loc_1800041C2
0x18000416d  test    edi, edi
0x18000416f  js      short loc_1800041A9
0x180004171  mov     edi, 8007029Ch
0x180004176  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000417a  mov     rax, [rsp+78h+arg_28]
0x180004182  mov     [rsp+78h+var_50], rax; __int64
0x180004187  mov     rax, [rsp+78h+arg_20]
0x18000418f  mov     [rsp+78h+var_58], rax; __int64
0x180004194  mov     rcx, r10; int
0x180004197  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000419c  mov     [rbx+8], edi
0x18000419f  mov     ecx, edi; this
0x1800041a1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800041a6  mov     [rbx+0Ch], eax
0x1800041a9  mov     ecx, edi; this
0x1800041ab  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800041b0  jmp     short loc_1800041C2
0x1800041b2  mov     ecx, edi; this
0x1800041b4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800041b9  jmp     short loc_1800041C2
0x1800041bb  mov     ecx, edi; this
0x1800041bd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800041c2  mov     ebp, eax
0x1800041c4  mov     [rbx], r15d
0x1800041c7  mov     eax, [rsp+78h+arg_70]
0x1800041ce  mov     [rbx+4], eax
0x1800041d1  cmp     dword ptr [r14+8], 1
0x1800041d6  jnz     short loc_1800041DE
0x1800041d8  or      eax, 8
0x1800041db  mov     [rbx+4], eax
0x1800041de  mov     eax, 1
0x1800041e3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800041eb  inc     eax
0x1800041ed  mov     [rbx+10h], eax
0x1800041f0  mov     rax, [rsp+78h+arg_40]
0x1800041f8  xor     edi, edi
0x1800041fa  test    rax, rax
0x1800041fd  jz      short loc_180004204
0x1800041ff  cmp     [rax], di
0x180004202  jnz     short loc_180004207
0x180004204  mov     rax, rdi
0x180004207  mov     [rbx+18h], rax
0x18000420b  call    cs:__imp_GetCurrentThreadId
0x180004211  mov     [rbx+20h], eax
0x180004214  mov     [rbx+38h], r13
0x180004218  mov     eax, [rsp+78h+arg_8]
0x18000421f  mov     [rbx+40h], eax
0x180004222  mov     [rbx+44h], ebp
0x180004225  mov     rax, [rsp+78h+arg_20]
0x18000422d  mov     [rbx+28h], rax
0x180004231  mov     [rbx+30h], r12
0x180004235  mov     rax, [rsp+78h+arg_28]
0x18000423d  mov     [rbx+88h], rax
0x180004244  mov     rax, [rsp+78h+arg_0]
0x18000424c  mov     [rbx+90h], rax
0x180004253  mov     [rbx+48h], rdi
0x180004257  xorps   xmm0, xmm0
0x18000425a  xor     eax, eax
0x18000425c  movups  xmmword ptr [rbx+68h], xmm0
0x180004260  mov     [rbx+78h], rax
0x180004264  movups  xmmword ptr [rbx+50h], xmm0
0x180004268  mov     [rbx+60h], rax
0x18000426c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004273  test    rax, rax
0x180004276  jz      short loc_18000427F
0x180004278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000427d  jmp     short loc_180004282
0x18000427f  mov     rax, rdi
0x180004282  mov     [rbx+80h], rax
0x180004289  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004290  test    rax, rax
0x180004293  jz      short loc_18000429D
0x180004295  mov     rcx, rbx
0x180004298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000429d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800042a4  test    rax, rax
0x1800042a7  jz      short loc_1800042BF
0x1800042a9  mov     r8d, 400h
0x1800042af  mov     rdx, [rsp+78h+arg_60]
0x1800042b7  mov     rcx, rbx
0x1800042ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042bf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800042c6  test    rax, rax
0x1800042c9  jz      short loc_1800042D3
0x1800042cb  mov     rcx, rbx
0x1800042ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042d3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800042da  test    rax, rax
0x1800042dd  jz      short loc_1800042ED
0x1800042df  test    byte ptr [rbx+4], 2
0x1800042e3  jnz     short loc_1800042ED
0x1800042e5  mov     rcx, rbx
0x1800042e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042ed  cmp     [rbx+8], edi
0x1800042f0  jl      short loc_18000430C
0x1800042f2  cmp     r15d, 3
0x1800042f6  jnz     loc_1800043DB
0x1800042fc  mov     ecx, 8000FFFFh; this
0x180004301  mov     [rbx+8], ecx
0x180004304  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004309  mov     [rbx+0Ch], eax
0x18000430c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180004313  jnz     short loc_180004334
0x180004315  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000431c  test    rax, rax
0x18000431f  jz      short loc_18000432A
0x180004321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004326  test    al, al
0x180004328  jmp     short loc_180004332
0x18000432a  call    cs:__imp_IsDebuggerPresent
0x180004330  test    eax, eax
0x180004332  jz      short loc_18000433A
0x180004334  test    byte ptr [rbx+4], 2
0x180004338  jz      short loc_18000435E
0x18000433a  mov     rax, cs:g_pfnResultLoggingCallback
0x180004341  test    rax, rax
0x180004344  jz      short loc_1800043A2
0x180004346  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000434d  jnz     short loc_1800043A2
0x18000434f  xor     r8d, r8d
0x180004352  xor     edx, edx
0x180004354  mov     rcx, rbx
0x180004357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000435c  jmp     short loc_1800043A2
0x18000435e  mov     ebp, 800h
0x180004363  mov     rax, cs:g_pfnResultLoggingCallback
0x18000436a  test    rax, rax
0x18000436d  jz      short loc_180004386
0x18000436f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004376  jnz     short loc_180004386
0x180004378  mov     r8d, ebp
0x18000437b  mov     rdx, rsi
0x18000437e  mov     rcx, rbx
0x180004381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004386  cmp     [rsi], di
0x180004389  jnz     short loc_180004399
0x18000438b  mov     r8, rbx; unsigned __int64
0x18000438e  mov     rdx, rbp; wchar_t *
0x180004391  mov     rcx, rsi; this
0x180004394  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180004399  mov     rcx, rsi; lpOutputString
0x18000439c  call    cs:__imp_OutputDebugStringW
0x1800043a2  test    byte ptr [rbx+4], 4
0x1800043a6  jnz     short loc_1800043B1
0x1800043a8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800043af  jz      short loc_1800043C3
0x1800043b1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800043b8  test    rax, rax
0x1800043bb  jz      short loc_1800043C3
0x1800043bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043c2  nop
0x1800043c3  mov     rbx, [rsp+78h+arg_10]
0x1800043cb  add     rsp, 40h
0x1800043cf  pop     r15
0x1800043d1  pop     r14
0x1800043d3  pop     r13
0x1800043d5  pop     r12
0x1800043d7  pop     rdi
0x1800043d8  pop     rsi
0x1800043d9  pop     rbp
0x1800043da  retn
0x1800043db  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
