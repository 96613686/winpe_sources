# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006218`
- end: `0x180006511`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800038dc`
- `0x180003c48`
- `0x18000899c`

## callees

- `0x180003814`
- `0x180005680`
- `0x180005f3c`
- `0x180006218`
- `0x180006940`
- `0x180006960`
- `0x180006974`
- `0x180006990`
- `0x180007fe4`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000633b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000633b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800064cc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800064cc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000645a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000645a`

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
0x180006218  mov     [rsp+arg_10], rbx
0x18000621d  mov     [rsp+arg_8], edx
0x180006221  mov     [rsp+arg_0], rcx
0x180006226  push    rbp
0x180006227  push    rsi
0x180006228  push    rdi
0x180006229  push    r12
0x18000622b  push    r13
0x18000622d  push    r14
0x18000622f  push    r15
0x180006231  sub     rsp, 40h
0x180006235  mov     r12, r9
0x180006238  mov     r13, r8
0x18000623b  mov     r10, rcx
0x18000623e  xor     eax, eax
0x180006240  mov     rsi, [rsp+78h+lpOutputString]
0x180006248  mov     [rsi], ax
0x18000624b  mov     rax, [rsp+78h+arg_60]
0x180006253  mov     byte ptr [rax], 0
0x180006256  mov     r14, [rsp+78h+arg_38]
0x18000625e  mov     edi, [r14]
0x180006261  mov     rbx, [rsp+78h+arg_78]
0x180006269  mov     [rbx+8], edi
0x18000626c  mov     eax, [r14+4]
0x180006270  mov     [rbx+0Ch], eax
0x180006273  xor     ebp, ebp
0x180006275  mov     r15d, [rsp+78h+arg_30]
0x18000627d  mov     ecx, r15d
0x180006280  test    r15d, r15d
0x180006283  jz      short loc_1800062EB
0x180006285  sub     ecx, 1
0x180006288  jz      short loc_1800062E2
0x18000628a  sub     ecx, 1
0x18000628d  jz      short loc_18000629D
0x18000628f  cmp     ecx, 1
0x180006292  jnz     short loc_1800062F4
0x180006294  mov     ecx, edi; this
0x180006296  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000629b  jmp     short loc_1800062F2
0x18000629d  test    edi, edi
0x18000629f  js      short loc_1800062D9
0x1800062a1  mov     edi, 8007029Ch
0x1800062a6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800062aa  mov     rax, [rsp+78h+arg_28]
0x1800062b2  mov     [rsp+78h+var_50], rax; __int64
0x1800062b7  mov     rax, [rsp+78h+arg_20]
0x1800062bf  mov     [rsp+78h+var_58], rax; __int64
0x1800062c4  mov     rcx, r10; int
0x1800062c7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800062cc  mov     [rbx+8], edi
0x1800062cf  mov     ecx, edi; this
0x1800062d1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800062d6  mov     [rbx+0Ch], eax
0x1800062d9  mov     ecx, edi; this
0x1800062db  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800062e0  jmp     short loc_1800062F2
0x1800062e2  mov     ecx, edi; this
0x1800062e4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800062e9  jmp     short loc_1800062F2
0x1800062eb  mov     ecx, edi; this
0x1800062ed  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800062f2  mov     ebp, eax
0x1800062f4  mov     [rbx], r15d
0x1800062f7  mov     eax, [rsp+78h+arg_70]
0x1800062fe  mov     [rbx+4], eax
0x180006301  cmp     dword ptr [r14+8], 1
0x180006306  jnz     short loc_18000630E
0x180006308  or      eax, 8
0x18000630b  mov     [rbx+4], eax
0x18000630e  mov     eax, 1
0x180006313  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000631b  inc     eax
0x18000631d  mov     [rbx+10h], eax
0x180006320  mov     rax, [rsp+78h+arg_40]
0x180006328  xor     edi, edi
0x18000632a  test    rax, rax
0x18000632d  jz      short loc_180006334
0x18000632f  cmp     [rax], di
0x180006332  jnz     short loc_180006337
0x180006334  mov     rax, rdi
0x180006337  mov     [rbx+18h], rax
0x18000633b  call    cs:__imp_GetCurrentThreadId
0x180006341  mov     [rbx+20h], eax
0x180006344  mov     [rbx+38h], r13
0x180006348  mov     eax, [rsp+78h+arg_8]
0x18000634f  mov     [rbx+40h], eax
0x180006352  mov     [rbx+44h], ebp
0x180006355  mov     rax, [rsp+78h+arg_20]
0x18000635d  mov     [rbx+28h], rax
0x180006361  mov     [rbx+30h], r12
0x180006365  mov     rax, [rsp+78h+arg_28]
0x18000636d  mov     [rbx+88h], rax
0x180006374  mov     rax, [rsp+78h+arg_0]
0x18000637c  mov     [rbx+90h], rax
0x180006383  mov     [rbx+48h], rdi
0x180006387  xorps   xmm0, xmm0
0x18000638a  xor     eax, eax
0x18000638c  movups  xmmword ptr [rbx+68h], xmm0
0x180006390  mov     [rbx+78h], rax
0x180006394  movups  xmmword ptr [rbx+50h], xmm0
0x180006398  mov     [rbx+60h], rax
0x18000639c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800063a3  test    rax, rax
0x1800063a6  jz      short loc_1800063AF
0x1800063a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063ad  jmp     short loc_1800063B2
0x1800063af  mov     rax, rdi
0x1800063b2  mov     [rbx+80h], rax
0x1800063b9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800063c0  test    rax, rax
0x1800063c3  jz      short loc_1800063CD
0x1800063c5  mov     rcx, rbx
0x1800063c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063cd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800063d4  test    rax, rax
0x1800063d7  jz      short loc_1800063EF
0x1800063d9  mov     r8d, 400h
0x1800063df  mov     rdx, [rsp+78h+arg_60]
0x1800063e7  mov     rcx, rbx
0x1800063ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063ef  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800063f6  test    rax, rax
0x1800063f9  jz      short loc_180006403
0x1800063fb  mov     rcx, rbx
0x1800063fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006403  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000640a  test    rax, rax
0x18000640d  jz      short loc_18000641D
0x18000640f  test    byte ptr [rbx+4], 2
0x180006413  jnz     short loc_18000641D
0x180006415  mov     rcx, rbx
0x180006418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000641d  cmp     [rbx+8], edi
0x180006420  jl      short loc_18000643C
0x180006422  cmp     r15d, 3
0x180006426  jnz     loc_18000650B
0x18000642c  mov     ecx, 8000FFFFh; this
0x180006431  mov     [rbx+8], ecx
0x180006434  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006439  mov     [rbx+0Ch], eax
0x18000643c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006443  jnz     short loc_180006464
0x180006445  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000644c  test    rax, rax
0x18000644f  jz      short loc_18000645A
0x180006451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006456  test    al, al
0x180006458  jmp     short loc_180006462
0x18000645a  call    cs:__imp_IsDebuggerPresent
0x180006460  test    eax, eax
0x180006462  jz      short loc_18000646A
0x180006464  test    byte ptr [rbx+4], 2
0x180006468  jz      short loc_18000648E
0x18000646a  mov     rax, cs:g_pfnResultLoggingCallback
0x180006471  test    rax, rax
0x180006474  jz      short loc_1800064D2
0x180006476  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000647d  jnz     short loc_1800064D2
0x18000647f  xor     r8d, r8d
0x180006482  xor     edx, edx
0x180006484  mov     rcx, rbx
0x180006487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000648c  jmp     short loc_1800064D2
0x18000648e  mov     ebp, 800h
0x180006493  mov     rax, cs:g_pfnResultLoggingCallback
0x18000649a  test    rax, rax
0x18000649d  jz      short loc_1800064B6
0x18000649f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800064a6  jnz     short loc_1800064B6
0x1800064a8  mov     r8d, ebp
0x1800064ab  mov     rdx, rsi
0x1800064ae  mov     rcx, rbx
0x1800064b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064b6  cmp     [rsi], di
0x1800064b9  jnz     short loc_1800064C9
0x1800064bb  mov     r8, rbx; unsigned __int64
0x1800064be  mov     rdx, rbp; unsigned __int16 *
0x1800064c1  mov     rcx, rsi; this
0x1800064c4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800064c9  mov     rcx, rsi; lpOutputString
0x1800064cc  call    cs:__imp_OutputDebugStringW
0x1800064d2  test    byte ptr [rbx+4], 4
0x1800064d6  jnz     short loc_1800064E1
0x1800064d8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800064df  jz      short loc_1800064F3
0x1800064e1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800064e8  test    rax, rax
0x1800064eb  jz      short loc_1800064F3
0x1800064ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064f2  nop
0x1800064f3  mov     rbx, [rsp+78h+arg_10]
0x1800064fb  add     rsp, 40h
0x1800064ff  pop     r15
0x180006501  pop     r14
0x180006503  pop     r13
0x180006505  pop     r12
0x180006507  pop     rdi
0x180006508  pop     rsi
0x180006509  pop     rbp
0x18000650a  retn
0x18000650b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
