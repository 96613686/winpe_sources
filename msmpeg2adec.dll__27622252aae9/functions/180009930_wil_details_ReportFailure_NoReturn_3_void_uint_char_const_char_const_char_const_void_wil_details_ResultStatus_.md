# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180009930`
- end: `0x180009bda`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `682`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800096a0`

## callees

- `0x180009930`
- `0x18000eb60`
- `0x180010630`
- `0x1800133a0`
- `0x1800186c0`
- `0x180088690`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800099f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800099f4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009b0e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009b0e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009ba0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009ba0`

## string_xrefs

- `0x180009a04`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7)
{
  unsigned int v9; // edi
  int v10; // ecx
  const struct wil::FailureInfo *v11; // rdx
  __int64 v12; // rcx
  const struct wil::FailureInfo *v13; // r9
  bool v14; // zf
  unsigned __int64 v15[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v16; // [rsp+30h] [rbp-D0h]
  __int128 v17; // [rsp+40h] [rbp-C0h]
  __int128 v18; // [rsp+50h] [rbp-B0h]
  __int128 v19; // [rsp+60h] [rbp-A0h]
  __int128 v20; // [rsp+70h] [rbp-90h]
  _OWORD v21[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v22; // [rsp+A0h] [rbp-60h]
  __int64 v23; // [rsp+B0h] [rbp-50h]
  _BYTE v24[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  *(_OWORD *)v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  memset(v21, 0, sizeof(v21));
  v22 = 0;
  v23 = 0;
  OutputString[0] = 0;
  v24[0] = 0;
  v15[1] = *(_QWORD *)a7;
  v9 = wil::details::RecordFailFast((wil::details *)LODWORD(v15[1]), a2);
  LODWORD(v15[0]) = 3;
  v10 = 0;
  if ( *(_DWORD *)(a7 + 8) == 1 )
    v10 = 8;
  HIDWORD(v15[0]) = v10;
  LODWORD(v16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  *((_QWORD *)&v16 + 1) = 0;
  LODWORD(v17) = GetCurrentThreadId();
  *((_QWORD *)&v18 + 1) = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h";
  v19 = __PAIR64__(v9, a2);
  *((_QWORD *)&v17 + 1) = 0;
  *(_QWORD *)&v18 = 0;
  *((_QWORD *)&v22 + 1) = a6;
  v23 = a1;
  v20 = 0;
  memset(v21, 0, sizeof(v21));
  if ( wil::details::g_pfnGetModuleName )
    *(_QWORD *)&v22 = wil::details::g_pfnGetModuleName(v12);
  else
    *(_QWORD *)&v22 = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v15);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v15, v24, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v15);
  if ( wil::details::g_pfnOriginateCallback && (v15[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v15);
  if ( SLODWORD(v15[1]) >= 0 )
  {
    LODWORD(v15[1]) = -2147418113;
    HIDWORD(v15[1]) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v11);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v14 = !IsDebuggerPresent())
      : (v14 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v12) == 0),
        v14)
    || (v15[0] & 0x200000000LL) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v15, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v15, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)v15, v13);
    OutputDebugStringW(OutputString);
  }
  if ( (v15[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v12);
  }
  wil::details::WilFailFast((wil::details *)v15, v11);
}

```

## disassembly

```asm
0x180009930  mov     [rsp-8+arg_10], rbx
0x180009935  mov     [rsp-8+arg_18], rsi
0x18000993a  push    rbp
0x18000993b  push    rdi
0x18000993c  push    r12
0x18000993e  push    r14
0x180009940  push    r15
0x180009942  lea     rbp, [rsp-13C0h]
0x18000994a  mov     eax, 14C0h
0x18000994f  call    _alloca_probe
0x180009954  sub     rsp, rax
0x180009957  mov     r14d, edx
0x18000995a  mov     r15, rcx
0x18000995d  mov     rsi, [rbp+13E0h+arg_28]
0x180009964  xorps   xmm0, xmm0
0x180009967  xor     eax, eax
0x180009969  movups  xmmword ptr [rsp+14E0h+var_14C0], xmm0
0x18000996e  movups  [rsp+14E0h+var_14B0], xmm0
0x180009973  movups  [rsp+14E0h+var_14A0], xmm0
0x180009978  movups  [rsp+14E0h+var_1490], xmm0
0x18000997d  movups  [rsp+14E0h+var_1480], xmm0
0x180009982  movups  [rsp+14E0h+var_1470], xmm0
0x180009987  movups  [rbp+13E0h+var_1460], xmm0
0x18000998b  movups  [rbp+13E0h+var_1450], xmm0
0x18000998f  movups  [rbp+13E0h+var_1440], xmm0
0x180009993  mov     [rbp+13E0h+var_1430], rax
0x180009997  xor     r12d, r12d
0x18000999a  mov     [rbp+13E0h+OutputString], r12w
0x1800099a2  mov     [rbp+13E0h+var_1420], r12b
0x1800099a6  mov     rbx, [rbp+13E0h+arg_30]
0x1800099ad  mov     ecx, [rbx]; this
0x1800099af  mov     dword ptr [rsp+14E0h+var_14C0+8], ecx
0x1800099b3  mov     eax, [rbx+4]
0x1800099b6  mov     dword ptr [rsp+14E0h+var_14C0+0Ch], eax
0x1800099ba  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800099bf  mov     edi, eax
0x1800099c1  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x1800099c9  mov     ecx, r12d
0x1800099cc  mov     eax, 8
0x1800099d1  cmp     dword ptr [rbx+8], 1
0x1800099d5  cmovz   ecx, eax
0x1800099d8  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x1800099dc  mov     ecx, 1
0x1800099e1  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800099e9  inc     ecx
0x1800099eb  mov     dword ptr [rsp+14E0h+var_14B0], ecx
0x1800099ef  mov     qword ptr [rsp+14E0h+var_14B0+8], r12
0x1800099f4  call    cs:__imp_GetCurrentThreadId
0x1800099fb  nop     dword ptr [rax+rax+00h]
0x180009a00  mov     dword ptr [rsp+14E0h+var_14A0], eax
0x180009a04  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009a0b  mov     qword ptr [rsp+14E0h+var_1490+8], rax
0x180009a10  mov     dword ptr [rsp+14E0h+var_1480], r14d
0x180009a15  mov     dword ptr [rsp+14E0h+var_1480+4], edi
0x180009a19  mov     qword ptr [rsp+14E0h+var_14A0+8], r12
0x180009a1e  mov     qword ptr [rsp+14E0h+var_1490], r12
0x180009a23  mov     qword ptr [rbp+13E0h+var_1440+8], rsi
0x180009a27  mov     [rbp+13E0h+var_1430], r15
0x180009a2b  mov     qword ptr [rsp+14E0h+var_1480+8], r12
0x180009a30  xorps   xmm0, xmm0
0x180009a33  xor     eax, eax
0x180009a35  movups  [rbp+13E0h+var_1460+8], xmm0
0x180009a39  mov     qword ptr [rbp+13E0h+var_1450+8], rax
0x180009a3d  xorps   xmm1, xmm1
0x180009a40  movups  [rsp+14E0h+var_1470], xmm1
0x180009a45  mov     qword ptr [rbp+13E0h+var_1460], rax
0x180009a49  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180009a50  test    rax, rax
0x180009a53  jz      short loc_180009A61
0x180009a55  call    cs:__guard_dispatch_icall_fptr
0x180009a5b  mov     qword ptr [rbp+13E0h+var_1440], rax
0x180009a5f  jmp     short loc_180009A65
0x180009a61  mov     qword ptr [rbp+13E0h+var_1440], r12
0x180009a65  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009a6c  test    rax, rax
0x180009a6f  jz      short loc_180009A7C
0x180009a71  lea     rcx, [rsp+14E0h+var_14C0]
0x180009a76  call    cs:__guard_dispatch_icall_fptr
0x180009a7c  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009a83  test    rax, rax
0x180009a86  jz      short loc_180009A9D
0x180009a88  mov     r8d, 400h
0x180009a8e  lea     rdx, [rbp+13E0h+var_1420]
0x180009a92  lea     rcx, [rsp+14E0h+var_14C0]
0x180009a97  call    cs:__guard_dispatch_icall_fptr
0x180009a9d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009aa4  test    rax, rax
0x180009aa7  jz      short loc_180009AB4
0x180009aa9  lea     rcx, [rsp+14E0h+var_14C0]
0x180009aae  call    cs:__guard_dispatch_icall_fptr
0x180009ab4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009abb  test    rax, rax
0x180009abe  jz      short loc_180009AD2
0x180009ac0  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180009ac5  jnz     short loc_180009AD2
0x180009ac7  lea     rcx, [rsp+14E0h+var_14C0]
0x180009acc  call    cs:__guard_dispatch_icall_fptr
0x180009ad2  cmp     dword ptr [rsp+14E0h+var_14C0+8], r12d
0x180009ad7  jl      short loc_180009AEF
0x180009ad9  mov     dword ptr [rsp+14E0h+var_14C0+8], 8000FFFFh
0x180009ae1  mov     ecx, 8000FFFFh; this
0x180009ae6  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009aeb  mov     dword ptr [rsp+14E0h+var_14C0+0Ch], eax
0x180009aef  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180009af6  jnz     short loc_180009B1E
0x180009af8  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180009aff  test    rax, rax
0x180009b02  jz      short loc_180009B0E
0x180009b04  call    cs:__guard_dispatch_icall_fptr
0x180009b0a  test    al, al
0x180009b0c  jmp     short loc_180009B1C
0x180009b0e  call    cs:__imp_IsDebuggerPresent
0x180009b15  nop     dword ptr [rax+rax+00h]
0x180009b1a  test    eax, eax
0x180009b1c  jz      short loc_180009B25
0x180009b1e  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180009b23  jz      short loc_180009B4C
0x180009b25  mov     rax, cs:g_pfnResultLoggingCallback
0x180009b2c  test    rax, rax
0x180009b2f  jz      short loc_180009BAC
0x180009b31  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180009b38  jnz     short loc_180009BAC
0x180009b3a  xor     r8d, r8d
0x180009b3d  xor     edx, edx
0x180009b3f  lea     rcx, [rsp+14E0h+var_14C0]
0x180009b44  call    cs:__guard_dispatch_icall_fptr
0x180009b4a  jmp     short loc_180009BAC
0x180009b4c  mov     rax, cs:g_pfnResultLoggingCallback
0x180009b53  test    rax, rax
0x180009b56  jz      short loc_180009B79
0x180009b58  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180009b5f  jnz     short loc_180009B79
0x180009b61  mov     r8d, 800h
0x180009b67  lea     rdx, [rbp+13E0h+OutputString]
0x180009b6e  lea     rcx, [rsp+14E0h+var_14C0]
0x180009b73  call    cs:__guard_dispatch_icall_fptr
0x180009b79  cmp     [rbp+13E0h+OutputString], r12w
0x180009b81  jnz     short loc_180009B99
0x180009b83  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180009b88  mov     edx, 800h; unsigned __int16 *
0x180009b8d  lea     rcx, [rbp+13E0h+OutputString]; this
0x180009b94  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180009b99  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180009ba0  call    cs:__imp_OutputDebugStringW
0x180009ba7  nop     dword ptr [rax+rax+00h]
0x180009bac  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180009bb1  jnz     short loc_180009BBC
0x180009bb3  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180009bba  jz      short loc_180009BCF
0x180009bbc  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180009bc3  test    rax, rax
0x180009bc6  jz      short loc_180009BCF
0x180009bc8  call    cs:__guard_dispatch_icall_fptr
0x180009bce  nop
0x180009bcf  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180009bd4  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
