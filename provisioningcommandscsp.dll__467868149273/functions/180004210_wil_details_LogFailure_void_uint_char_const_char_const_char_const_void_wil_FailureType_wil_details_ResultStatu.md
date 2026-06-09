# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004210`
- end: `0x18000451c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002b04`

## callees

- `0x1800024e8`
- `0x180003814`
- `0x180004028`
- `0x180004210`
- `0x180004aa0`
- `0x180004ac0`
- `0x180004ad4`
- `0x180004af4`
- `0x180005ce8`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004333`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004333`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800044d0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800044d0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004458`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004458`

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
0x180004210  mov     [rsp+arg_10], rbx
0x180004215  mov     [rsp+arg_8], edx
0x180004219  mov     [rsp+arg_0], rcx
0x18000421e  push    rbp
0x18000421f  push    rsi
0x180004220  push    rdi
0x180004221  push    r12
0x180004223  push    r13
0x180004225  push    r14
0x180004227  push    r15
0x180004229  sub     rsp, 40h
0x18000422d  mov     r12, r9
0x180004230  mov     r13, r8
0x180004233  mov     r10, rcx
0x180004236  xor     eax, eax
0x180004238  mov     rsi, [rsp+78h+lpOutputString]
0x180004240  mov     [rsi], ax
0x180004243  mov     rax, [rsp+78h+arg_60]
0x18000424b  mov     byte ptr [rax], 0
0x18000424e  mov     r14, [rsp+78h+arg_38]
0x180004256  mov     edi, [r14]
0x180004259  mov     rbx, [rsp+78h+arg_78]
0x180004261  mov     [rbx+8], edi
0x180004264  mov     eax, [r14+4]
0x180004268  mov     [rbx+0Ch], eax
0x18000426b  xor     ebp, ebp
0x18000426d  mov     r15d, [rsp+78h+arg_30]
0x180004275  mov     ecx, r15d
0x180004278  test    r15d, r15d
0x18000427b  jz      short loc_1800042E3
0x18000427d  sub     ecx, 1
0x180004280  jz      short loc_1800042DA
0x180004282  sub     ecx, 1
0x180004285  jz      short loc_180004295
0x180004287  cmp     ecx, 1
0x18000428a  jnz     short loc_1800042EC
0x18000428c  mov     ecx, edi; this
0x18000428e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004293  jmp     short loc_1800042EA
0x180004295  test    edi, edi
0x180004297  js      short loc_1800042D1
0x180004299  mov     edi, 8007029Ch
0x18000429e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800042a2  mov     rax, [rsp+78h+arg_28]
0x1800042aa  mov     [rsp+78h+var_50], rax; __int64
0x1800042af  mov     rax, [rsp+78h+arg_20]
0x1800042b7  mov     [rsp+78h+var_58], rax; __int64
0x1800042bc  mov     rcx, r10; int
0x1800042bf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800042c4  mov     [rbx+8], edi
0x1800042c7  mov     ecx, edi; this
0x1800042c9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800042ce  mov     [rbx+0Ch], eax
0x1800042d1  mov     ecx, edi; this
0x1800042d3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800042d8  jmp     short loc_1800042EA
0x1800042da  mov     ecx, edi; this
0x1800042dc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800042e1  jmp     short loc_1800042EA
0x1800042e3  mov     ecx, edi; this
0x1800042e5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800042ea  mov     ebp, eax
0x1800042ec  mov     [rbx], r15d
0x1800042ef  mov     eax, [rsp+78h+arg_70]
0x1800042f6  mov     [rbx+4], eax
0x1800042f9  cmp     dword ptr [r14+8], 1
0x1800042fe  jnz     short loc_180004306
0x180004300  or      eax, 8
0x180004303  mov     [rbx+4], eax
0x180004306  mov     eax, 1
0x18000430b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004313  inc     eax
0x180004315  mov     [rbx+10h], eax
0x180004318  mov     rax, [rsp+78h+arg_40]
0x180004320  xor     edi, edi
0x180004322  test    rax, rax
0x180004325  jz      short loc_18000432C
0x180004327  cmp     [rax], di
0x18000432a  jnz     short loc_18000432F
0x18000432c  mov     rax, rdi
0x18000432f  mov     [rbx+18h], rax
0x180004333  call    cs:__imp_GetCurrentThreadId
0x18000433a  nop     dword ptr [rax+rax+00h]
0x18000433f  mov     [rbx+20h], eax
0x180004342  mov     [rbx+38h], r13
0x180004346  mov     eax, [rsp+78h+arg_8]
0x18000434d  mov     [rbx+40h], eax
0x180004350  mov     [rbx+44h], ebp
0x180004353  mov     rax, [rsp+78h+arg_20]
0x18000435b  mov     [rbx+28h], rax
0x18000435f  mov     [rbx+30h], r12
0x180004363  mov     rax, [rsp+78h+arg_28]
0x18000436b  mov     [rbx+88h], rax
0x180004372  mov     rax, [rsp+78h+arg_0]
0x18000437a  mov     [rbx+90h], rax
0x180004381  mov     [rbx+48h], rdi
0x180004385  xorps   xmm0, xmm0
0x180004388  xor     eax, eax
0x18000438a  movups  xmmword ptr [rbx+68h], xmm0
0x18000438e  mov     [rbx+78h], rax
0x180004392  movups  xmmword ptr [rbx+50h], xmm0
0x180004396  mov     [rbx+60h], rax
0x18000439a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800043a1  test    rax, rax
0x1800043a4  jz      short loc_1800043AD
0x1800043a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043ab  jmp     short loc_1800043B0
0x1800043ad  mov     rax, rdi
0x1800043b0  mov     [rbx+80h], rax
0x1800043b7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800043be  test    rax, rax
0x1800043c1  jz      short loc_1800043CB
0x1800043c3  mov     rcx, rbx
0x1800043c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043cb  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800043d2  test    rax, rax
0x1800043d5  jz      short loc_1800043ED
0x1800043d7  mov     r8d, 400h
0x1800043dd  mov     rdx, [rsp+78h+arg_60]
0x1800043e5  mov     rcx, rbx
0x1800043e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043ed  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800043f4  test    rax, rax
0x1800043f7  jz      short loc_180004401
0x1800043f9  mov     rcx, rbx
0x1800043fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004401  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004408  test    rax, rax
0x18000440b  jz      short loc_18000441B
0x18000440d  test    byte ptr [rbx+4], 2
0x180004411  jnz     short loc_18000441B
0x180004413  mov     rcx, rbx
0x180004416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000441b  cmp     [rbx+8], edi
0x18000441e  jl      short loc_18000443A
0x180004420  cmp     r15d, 3
0x180004424  jnz     loc_180004516
0x18000442a  mov     ecx, 8000FFFFh; this
0x18000442f  mov     [rbx+8], ecx
0x180004432  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004437  mov     [rbx+0Ch], eax
0x18000443a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180004441  jnz     short loc_180004468
0x180004443  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000444a  test    rax, rax
0x18000444d  jz      short loc_180004458
0x18000444f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004454  test    al, al
0x180004456  jmp     short loc_180004466
0x180004458  call    cs:__imp_IsDebuggerPresent
0x18000445f  nop     dword ptr [rax+rax+00h]
0x180004464  test    eax, eax
0x180004466  jz      short loc_18000446E
0x180004468  test    byte ptr [rbx+4], 2
0x18000446c  jz      short loc_180004492
0x18000446e  mov     rax, cs:g_pfnResultLoggingCallback
0x180004475  test    rax, rax
0x180004478  jz      short loc_1800044DC
0x18000447a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004481  jnz     short loc_1800044DC
0x180004483  xor     r8d, r8d
0x180004486  xor     edx, edx
0x180004488  mov     rcx, rbx
0x18000448b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004490  jmp     short loc_1800044DC
0x180004492  mov     ebp, 800h
0x180004497  mov     rax, cs:g_pfnResultLoggingCallback
0x18000449e  test    rax, rax
0x1800044a1  jz      short loc_1800044BA
0x1800044a3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800044aa  jnz     short loc_1800044BA
0x1800044ac  mov     r8d, ebp
0x1800044af  mov     rdx, rsi
0x1800044b2  mov     rcx, rbx
0x1800044b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044ba  cmp     [rsi], di
0x1800044bd  jnz     short loc_1800044CD
0x1800044bf  mov     r8, rbx; unsigned __int64
0x1800044c2  mov     rdx, rbp; unsigned __int16 *
0x1800044c5  mov     rcx, rsi; this
0x1800044c8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800044cd  mov     rcx, rsi; lpOutputString
0x1800044d0  call    cs:__imp_OutputDebugStringW
0x1800044d7  nop     dword ptr [rax+rax+00h]
0x1800044dc  test    byte ptr [rbx+4], 4
0x1800044e0  jnz     short loc_1800044EB
0x1800044e2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800044e9  jz      short loc_1800044FD
0x1800044eb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800044f2  test    rax, rax
0x1800044f5  jz      short loc_1800044FD
0x1800044f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044fc  nop
0x1800044fd  mov     rbx, [rsp+78h+arg_10]
0x180004505  add     rsp, 40h
0x180004509  pop     r15
0x18000450b  pop     r14
0x18000450d  pop     r13
0x18000450f  pop     r12
0x180004511  pop     rdi
0x180004512  pop     rsi
0x180004513  pop     rbp
0x180004514  retn
0x180004516  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
