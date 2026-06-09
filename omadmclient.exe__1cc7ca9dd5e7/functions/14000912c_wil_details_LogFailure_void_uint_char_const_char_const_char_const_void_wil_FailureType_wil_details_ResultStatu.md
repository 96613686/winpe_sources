# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x14000912c`
- end: `0x140009438`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140006384`

## callees

- `0x140005d68`
- `0x14000866c`
- `0x140008e7c`
- `0x14000912c`
- `0x140009ed4`
- `0x140009f00`
- `0x14000a048`
- `0x14000a068`
- `0x14000ce6c`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000924f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000924f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140009374`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140009374`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400093ec`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400093ec`

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
0x14000912c  mov     [rsp+arg_10], rbx
0x140009131  mov     [rsp+arg_8], edx
0x140009135  mov     [rsp+arg_0], rcx
0x14000913a  push    rbp
0x14000913b  push    rsi
0x14000913c  push    rdi
0x14000913d  push    r12
0x14000913f  push    r13
0x140009141  push    r14
0x140009143  push    r15
0x140009145  sub     rsp, 40h
0x140009149  mov     r12, r9
0x14000914c  mov     r13, r8
0x14000914f  mov     r10, rcx
0x140009152  xor     eax, eax
0x140009154  mov     rsi, [rsp+78h+lpOutputString]
0x14000915c  mov     [rsi], ax
0x14000915f  mov     rax, [rsp+78h+arg_60]
0x140009167  mov     byte ptr [rax], 0
0x14000916a  mov     r14, [rsp+78h+arg_38]
0x140009172  mov     edi, [r14]
0x140009175  mov     rbx, [rsp+78h+arg_78]
0x14000917d  mov     [rbx+8], edi
0x140009180  mov     eax, [r14+4]
0x140009184  mov     [rbx+0Ch], eax
0x140009187  xor     ebp, ebp
0x140009189  mov     r15d, [rsp+78h+arg_30]
0x140009191  mov     ecx, r15d
0x140009194  test    r15d, r15d
0x140009197  jz      short loc_1400091FF
0x140009199  sub     ecx, 1
0x14000919c  jz      short loc_1400091F6
0x14000919e  sub     ecx, 1
0x1400091a1  jz      short loc_1400091B1
0x1400091a3  cmp     ecx, 1
0x1400091a6  jnz     short loc_140009208
0x1400091a8  mov     ecx, edi; this
0x1400091aa  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400091af  jmp     short loc_140009206
0x1400091b1  test    edi, edi
0x1400091b3  js      short loc_1400091ED
0x1400091b5  mov     edi, 8007029Ch
0x1400091ba  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1400091be  mov     rax, [rsp+78h+arg_28]
0x1400091c6  mov     [rsp+78h+var_50], rax; __int64
0x1400091cb  mov     rax, [rsp+78h+arg_20]
0x1400091d3  mov     [rsp+78h+var_58], rax; __int64
0x1400091d8  mov     rcx, r10; int
0x1400091db  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400091e0  mov     [rbx+8], edi
0x1400091e3  mov     ecx, edi; this
0x1400091e5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400091ea  mov     [rbx+0Ch], eax
0x1400091ed  mov     ecx, edi; this
0x1400091ef  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1400091f4  jmp     short loc_140009206
0x1400091f6  mov     ecx, edi; this
0x1400091f8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400091fd  jmp     short loc_140009206
0x1400091ff  mov     ecx, edi; this
0x140009201  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140009206  mov     ebp, eax
0x140009208  mov     [rbx], r15d
0x14000920b  mov     eax, [rsp+78h+arg_70]
0x140009212  mov     [rbx+4], eax
0x140009215  cmp     dword ptr [r14+8], 1
0x14000921a  jnz     short loc_140009222
0x14000921c  or      eax, 8
0x14000921f  mov     [rbx+4], eax
0x140009222  mov     eax, 1
0x140009227  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000922f  inc     eax
0x140009231  mov     [rbx+10h], eax
0x140009234  mov     rax, [rsp+78h+arg_40]
0x14000923c  xor     edi, edi
0x14000923e  test    rax, rax
0x140009241  jz      short loc_140009248
0x140009243  cmp     [rax], di
0x140009246  jnz     short loc_14000924B
0x140009248  mov     rax, rdi
0x14000924b  mov     [rbx+18h], rax
0x14000924f  call    cs:__imp_GetCurrentThreadId
0x140009256  nop     dword ptr [rax+rax+00h]
0x14000925b  mov     [rbx+20h], eax
0x14000925e  mov     [rbx+38h], r13
0x140009262  mov     eax, [rsp+78h+arg_8]
0x140009269  mov     [rbx+40h], eax
0x14000926c  mov     [rbx+44h], ebp
0x14000926f  mov     rax, [rsp+78h+arg_20]
0x140009277  mov     [rbx+28h], rax
0x14000927b  mov     [rbx+30h], r12
0x14000927f  mov     rax, [rsp+78h+arg_28]
0x140009287  mov     [rbx+88h], rax
0x14000928e  mov     rax, [rsp+78h+arg_0]
0x140009296  mov     [rbx+90h], rax
0x14000929d  mov     [rbx+48h], rdi
0x1400092a1  xorps   xmm0, xmm0
0x1400092a4  xor     eax, eax
0x1400092a6  movups  xmmword ptr [rbx+68h], xmm0
0x1400092aa  mov     [rbx+78h], rax
0x1400092ae  movups  xmmword ptr [rbx+50h], xmm0
0x1400092b2  mov     [rbx+60h], rax
0x1400092b6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400092bd  test    rax, rax
0x1400092c0  jz      short loc_1400092C9
0x1400092c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400092c7  jmp     short loc_1400092CC
0x1400092c9  mov     rax, rdi
0x1400092cc  mov     [rbx+80h], rax
0x1400092d3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400092da  test    rax, rax
0x1400092dd  jz      short loc_1400092E7
0x1400092df  mov     rcx, rbx
0x1400092e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400092e7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400092ee  test    rax, rax
0x1400092f1  jz      short loc_140009309
0x1400092f3  mov     r8d, 400h
0x1400092f9  mov     rdx, [rsp+78h+arg_60]
0x140009301  mov     rcx, rbx
0x140009304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009309  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140009310  test    rax, rax
0x140009313  jz      short loc_14000931D
0x140009315  mov     rcx, rbx
0x140009318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000931d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140009324  test    rax, rax
0x140009327  jz      short loc_140009337
0x140009329  test    byte ptr [rbx+4], 2
0x14000932d  jnz     short loc_140009337
0x14000932f  mov     rcx, rbx
0x140009332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009337  cmp     [rbx+8], edi
0x14000933a  jl      short loc_140009356
0x14000933c  cmp     r15d, 3
0x140009340  jnz     loc_140009432
0x140009346  mov     ecx, 8000FFFFh; this
0x14000934b  mov     [rbx+8], ecx
0x14000934e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140009353  mov     [rbx+0Ch], eax
0x140009356  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14000935d  jnz     short loc_140009384
0x14000935f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140009366  test    rax, rax
0x140009369  jz      short loc_140009374
0x14000936b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009370  test    al, al
0x140009372  jmp     short loc_140009382
0x140009374  call    cs:__imp_IsDebuggerPresent
0x14000937b  nop     dword ptr [rax+rax+00h]
0x140009380  test    eax, eax
0x140009382  jz      short loc_14000938A
0x140009384  test    byte ptr [rbx+4], 2
0x140009388  jz      short loc_1400093AE
0x14000938a  mov     rax, cs:g_pfnResultLoggingCallback
0x140009391  test    rax, rax
0x140009394  jz      short loc_1400093F8
0x140009396  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000939d  jnz     short loc_1400093F8
0x14000939f  xor     r8d, r8d
0x1400093a2  xor     edx, edx
0x1400093a4  mov     rcx, rbx
0x1400093a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400093ac  jmp     short loc_1400093F8
0x1400093ae  mov     ebp, 800h
0x1400093b3  mov     rax, cs:g_pfnResultLoggingCallback
0x1400093ba  test    rax, rax
0x1400093bd  jz      short loc_1400093D6
0x1400093bf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400093c6  jnz     short loc_1400093D6
0x1400093c8  mov     r8d, ebp
0x1400093cb  mov     rdx, rsi
0x1400093ce  mov     rcx, rbx
0x1400093d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400093d6  cmp     [rsi], di
0x1400093d9  jnz     short loc_1400093E9
0x1400093db  mov     r8, rbx; unsigned __int64
0x1400093de  mov     rdx, rbp; unsigned __int16 *
0x1400093e1  mov     rcx, rsi; this
0x1400093e4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400093e9  mov     rcx, rsi; lpOutputString
0x1400093ec  call    cs:__imp_OutputDebugStringW
0x1400093f3  nop     dword ptr [rax+rax+00h]
0x1400093f8  test    byte ptr [rbx+4], 4
0x1400093fc  jnz     short loc_140009407
0x1400093fe  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140009405  jz      short loc_140009419
0x140009407  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000940e  test    rax, rax
0x140009411  jz      short loc_140009419
0x140009413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009418  nop
0x140009419  mov     rbx, [rsp+78h+arg_10]
0x140009421  add     rsp, 40h
0x140009425  pop     r15
0x140009427  pop     r14
0x140009429  pop     r13
0x14000942b  pop     r12
0x14000942d  pop     rdi
0x14000942e  pop     rsi
0x14000942f  pop     rbp
0x140009430  retn
0x140009432  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
