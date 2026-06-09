# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000420c`
- end: `0x180004518`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002ad0`

## callees

- `0x1800024e4`
- `0x1800037d4`
- `0x180003fd8`
- `0x18000420c`
- `0x1800049c4`
- `0x1800049f0`
- `0x180004a04`
- `0x180004a24`
- `0x180005d78`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000432f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000432f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800044cc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800044cc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004454`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004454`

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
    ModuleName = wil::details::g_pfnGetModuleName(v24);
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
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v24) == 0),
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
      wil::details::g_pfnDebugBreak(v24);
  }
}

```

## disassembly

```asm
0x18000420c  mov     [rsp+arg_10], rbx
0x180004211  mov     [rsp+arg_8], edx
0x180004215  mov     [rsp+arg_0], rcx
0x18000421a  push    rbp
0x18000421b  push    rsi
0x18000421c  push    rdi
0x18000421d  push    r12
0x18000421f  push    r13
0x180004221  push    r14
0x180004223  push    r15
0x180004225  sub     rsp, 40h
0x180004229  mov     r12, r9
0x18000422c  mov     r13, r8
0x18000422f  mov     r10, rcx
0x180004232  xor     eax, eax
0x180004234  mov     rsi, [rsp+78h+lpOutputString]
0x18000423c  mov     [rsi], ax
0x18000423f  mov     rax, [rsp+78h+arg_60]
0x180004247  mov     byte ptr [rax], 0
0x18000424a  mov     r14, [rsp+78h+arg_38]
0x180004252  mov     edi, [r14]
0x180004255  mov     rbx, [rsp+78h+arg_78]
0x18000425d  mov     [rbx+8], edi
0x180004260  mov     eax, [r14+4]
0x180004264  mov     [rbx+0Ch], eax
0x180004267  xor     ebp, ebp
0x180004269  mov     r15d, [rsp+78h+arg_30]
0x180004271  mov     ecx, r15d
0x180004274  test    r15d, r15d
0x180004277  jz      short loc_1800042DF
0x180004279  sub     ecx, 1
0x18000427c  jz      short loc_1800042D6
0x18000427e  sub     ecx, 1
0x180004281  jz      short loc_180004291
0x180004283  cmp     ecx, 1
0x180004286  jnz     short loc_1800042E8
0x180004288  mov     ecx, edi; this
0x18000428a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000428f  jmp     short loc_1800042E6
0x180004291  test    edi, edi
0x180004293  js      short loc_1800042CD
0x180004295  mov     edi, 8007029Ch
0x18000429a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000429e  mov     rax, [rsp+78h+arg_28]
0x1800042a6  mov     [rsp+78h+var_50], rax; __int64
0x1800042ab  mov     rax, [rsp+78h+arg_20]
0x1800042b3  mov     [rsp+78h+var_58], rax; __int64
0x1800042b8  mov     rcx, r10; int
0x1800042bb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800042c0  mov     [rbx+8], edi
0x1800042c3  mov     ecx, edi; this
0x1800042c5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800042ca  mov     [rbx+0Ch], eax
0x1800042cd  mov     ecx, edi; this
0x1800042cf  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800042d4  jmp     short loc_1800042E6
0x1800042d6  mov     ecx, edi; this
0x1800042d8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800042dd  jmp     short loc_1800042E6
0x1800042df  mov     ecx, edi; this
0x1800042e1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800042e6  mov     ebp, eax
0x1800042e8  mov     [rbx], r15d
0x1800042eb  mov     eax, [rsp+78h+arg_70]
0x1800042f2  mov     [rbx+4], eax
0x1800042f5  cmp     dword ptr [r14+8], 1
0x1800042fa  jnz     short loc_180004302
0x1800042fc  or      eax, 8
0x1800042ff  mov     [rbx+4], eax
0x180004302  mov     eax, 1
0x180004307  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000430f  inc     eax
0x180004311  mov     [rbx+10h], eax
0x180004314  mov     rax, [rsp+78h+arg_40]
0x18000431c  xor     edi, edi
0x18000431e  test    rax, rax
0x180004321  jz      short loc_180004328
0x180004323  cmp     [rax], di
0x180004326  jnz     short loc_18000432B
0x180004328  mov     rax, rdi
0x18000432b  mov     [rbx+18h], rax
0x18000432f  call    cs:__imp_GetCurrentThreadId
0x180004336  nop     dword ptr [rax+rax+00h]
0x18000433b  mov     [rbx+20h], eax
0x18000433e  mov     [rbx+38h], r13
0x180004342  mov     eax, [rsp+78h+arg_8]
0x180004349  mov     [rbx+40h], eax
0x18000434c  mov     [rbx+44h], ebp
0x18000434f  mov     rax, [rsp+78h+arg_20]
0x180004357  mov     [rbx+28h], rax
0x18000435b  mov     [rbx+30h], r12
0x18000435f  mov     rax, [rsp+78h+arg_28]
0x180004367  mov     [rbx+88h], rax
0x18000436e  mov     rax, [rsp+78h+arg_0]
0x180004376  mov     [rbx+90h], rax
0x18000437d  mov     [rbx+48h], rdi
0x180004381  xorps   xmm0, xmm0
0x180004384  xor     eax, eax
0x180004386  movups  xmmword ptr [rbx+68h], xmm0
0x18000438a  mov     [rbx+78h], rax
0x18000438e  movups  xmmword ptr [rbx+50h], xmm0
0x180004392  mov     [rbx+60h], rax
0x180004396  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000439d  test    rax, rax
0x1800043a0  jz      short loc_1800043A9
0x1800043a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043a7  jmp     short loc_1800043AC
0x1800043a9  mov     rax, rdi
0x1800043ac  mov     [rbx+80h], rax
0x1800043b3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800043ba  test    rax, rax
0x1800043bd  jz      short loc_1800043C7
0x1800043bf  mov     rcx, rbx
0x1800043c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043c7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800043ce  test    rax, rax
0x1800043d1  jz      short loc_1800043E9
0x1800043d3  mov     r8d, 400h
0x1800043d9  mov     rdx, [rsp+78h+arg_60]
0x1800043e1  mov     rcx, rbx
0x1800043e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043e9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800043f0  test    rax, rax
0x1800043f3  jz      short loc_1800043FD
0x1800043f5  mov     rcx, rbx
0x1800043f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043fd  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004404  test    rax, rax
0x180004407  jz      short loc_180004417
0x180004409  test    byte ptr [rbx+4], 2
0x18000440d  jnz     short loc_180004417
0x18000440f  mov     rcx, rbx
0x180004412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004417  cmp     [rbx+8], edi
0x18000441a  jl      short loc_180004436
0x18000441c  cmp     r15d, 3
0x180004420  jnz     loc_180004512
0x180004426  mov     ecx, 8000FFFFh; this
0x18000442b  mov     [rbx+8], ecx
0x18000442e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004433  mov     [rbx+0Ch], eax
0x180004436  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000443d  jnz     short loc_180004464
0x18000443f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004446  test    rax, rax
0x180004449  jz      short loc_180004454
0x18000444b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004450  test    al, al
0x180004452  jmp     short loc_180004462
0x180004454  call    cs:__imp_IsDebuggerPresent
0x18000445b  nop     dword ptr [rax+rax+00h]
0x180004460  test    eax, eax
0x180004462  jz      short loc_18000446A
0x180004464  test    byte ptr [rbx+4], 2
0x180004468  jz      short loc_18000448E
0x18000446a  mov     rax, cs:g_pfnResultLoggingCallback
0x180004471  test    rax, rax
0x180004474  jz      short loc_1800044D8
0x180004476  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000447d  jnz     short loc_1800044D8
0x18000447f  xor     r8d, r8d
0x180004482  xor     edx, edx
0x180004484  mov     rcx, rbx
0x180004487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000448c  jmp     short loc_1800044D8
0x18000448e  mov     ebp, 800h
0x180004493  mov     rax, cs:g_pfnResultLoggingCallback
0x18000449a  test    rax, rax
0x18000449d  jz      short loc_1800044B6
0x18000449f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800044a6  jnz     short loc_1800044B6
0x1800044a8  mov     r8d, ebp
0x1800044ab  mov     rdx, rsi
0x1800044ae  mov     rcx, rbx
0x1800044b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044b6  cmp     [rsi], di
0x1800044b9  jnz     short loc_1800044C9
0x1800044bb  mov     r8, rbx; unsigned __int64
0x1800044be  mov     rdx, rbp; wchar_t *
0x1800044c1  mov     rcx, rsi; this
0x1800044c4  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800044c9  mov     rcx, rsi; lpOutputString
0x1800044cc  call    cs:__imp_OutputDebugStringW
0x1800044d3  nop     dword ptr [rax+rax+00h]
0x1800044d8  test    byte ptr [rbx+4], 4
0x1800044dc  jnz     short loc_1800044E7
0x1800044de  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800044e5  jz      short loc_1800044F9
0x1800044e7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800044ee  test    rax, rax
0x1800044f1  jz      short loc_1800044F9
0x1800044f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044f8  nop
0x1800044f9  mov     rbx, [rsp+78h+arg_10]
0x180004501  add     rsp, 40h
0x180004505  pop     r15
0x180004507  pop     r14
0x180004509  pop     r13
0x18000450b  pop     r12
0x18000450d  pop     rdi
0x18000450e  pop     rsi
0x18000450f  pop     rbp
0x180004510  retn
0x180004512  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
