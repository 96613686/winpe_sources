# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002ab4`
- end: `0x180002d1d`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `617`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002868`

## callees

- `0x180002612`
- `0x180002ab4`
- `0x180004534`
- `0x180004cd0`
- `0x180005770`
- `0x180007210`
- `0x180007e70`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002b56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002b56`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002cea`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002cea`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002c60`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002c60`

## string_xrefs

- `0x180002b60`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7)
{
  int v9; // edx
  int v10; // edi
  int v11; // ecx
  const struct wil::FailureInfo *v12; // rdx
  __int64 v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v10 = wil::details::RecordFailFast((wil::details *)(unsigned int)v18, v9);
  v16 = 3;
  v11 = 0;
  if ( a7[2] == 1 )
    v11 = 8;
  v17 = v11;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h";
  v26 = a2;
  v27 = v10;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
  {
    v18 = -2147418113;
    v19 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v12);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( (v17 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v13);
  }
  wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x180002ab4  mov     [rsp-8+arg_10], rbx
0x180002ab9  mov     [rsp-8+arg_18], rsi
0x180002abe  push    rbp
0x180002abf  push    rdi
0x180002ac0  push    r12
0x180002ac2  push    r14
0x180002ac4  push    r15
0x180002ac6  lea     rbp, [rsp-13C0h]
0x180002ace  mov     eax, 14C0h
0x180002ad3  call    _alloca_probe
0x180002ad8  sub     rsp, rax
0x180002adb  mov     r14d, edx
0x180002ade  mov     r15, rcx
0x180002ae1  mov     rsi, [rbp+13E0h+arg_28]
0x180002ae8  xor     edx, edx; Val
0x180002aea  mov     r8d, 98h; Size
0x180002af0  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x180002af5  call    memset_0
0x180002afa  nop
0x180002afb  xor     r12d, r12d
0x180002afe  mov     [rbp+13E0h+OutputString], r12w
0x180002b06  mov     [rbp+13E0h+var_1420], r12b
0x180002b0a  mov     rbx, [rbp+13E0h+arg_30]
0x180002b11  mov     ecx, [rbx]; this
0x180002b13  mov     [rsp+14E0h+var_14B8], ecx
0x180002b17  mov     eax, [rbx+4]
0x180002b1a  mov     [rsp+14E0h+var_14B4], eax
0x180002b1e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002b23  mov     edi, eax
0x180002b25  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180002b2d  mov     ecx, r12d
0x180002b30  lea     eax, [r12+8]
0x180002b35  cmp     dword ptr [rbx+8], 1
0x180002b39  cmovz   ecx, eax
0x180002b3c  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x180002b40  lea     ecx, [rax-7]
0x180002b43  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002b4b  inc     ecx
0x180002b4d  mov     [rsp+14E0h+var_14B0], ecx
0x180002b51  mov     [rsp+14E0h+var_14A8], r12
0x180002b56  call    cs:__imp_GetCurrentThreadId
0x180002b5c  mov     [rsp+14E0h+var_14A0], eax
0x180002b60  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180002b67  mov     [rsp+14E0h+var_1488], rax
0x180002b6c  mov     [rsp+14E0h+var_1480], r14d
0x180002b71  mov     [rsp+14E0h+var_147C], edi
0x180002b75  mov     [rsp+14E0h+var_1498], r12
0x180002b7a  mov     [rsp+14E0h+var_1490], r12
0x180002b7f  mov     [rbp+13E0h+var_1438], rsi
0x180002b83  mov     [rbp+13E0h+var_1430], r15
0x180002b87  mov     [rsp+14E0h+var_1478], r12
0x180002b8c  xorps   xmm0, xmm0
0x180002b8f  xor     eax, eax
0x180002b91  movups  [rbp+13E0h+var_1458], xmm0
0x180002b95  mov     [rbp+13E0h+var_1448], rax
0x180002b99  xorps   xmm1, xmm1
0x180002b9c  movups  [rsp+14E0h+var_1470], xmm1
0x180002ba1  mov     [rbp+13E0h+var_1460], rax
0x180002ba5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002bac  test    rax, rax
0x180002baf  jz      short loc_180002BBC
0x180002bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bb6  mov     [rbp+13E0h+var_1440], rax
0x180002bba  jmp     short loc_180002BC0
0x180002bbc  mov     [rbp+13E0h+var_1440], r12
0x180002bc0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002bc7  test    rax, rax
0x180002bca  jz      short loc_180002BD6
0x180002bcc  lea     rcx, [rsp+14E0h+var_14C0]
0x180002bd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bd6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002bdd  test    rax, rax
0x180002be0  jz      short loc_180002BF6
0x180002be2  mov     r8d, 400h
0x180002be8  lea     rdx, [rbp+13E0h+var_1420]
0x180002bec  lea     rcx, [rsp+14E0h+var_14C0]
0x180002bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bf6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002bfd  test    rax, rax
0x180002c00  jz      short loc_180002C0C
0x180002c02  lea     rcx, [rsp+14E0h+var_14C0]
0x180002c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c0c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002c13  test    rax, rax
0x180002c16  jz      short loc_180002C29
0x180002c18  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180002c1d  jnz     short loc_180002C29
0x180002c1f  lea     rcx, [rsp+14E0h+var_14C0]
0x180002c24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c29  cmp     [rsp+14E0h+var_14B8], r12d
0x180002c2e  jl      short loc_180002C42
0x180002c30  mov     ecx, 8000FFFFh; this
0x180002c35  mov     [rsp+14E0h+var_14B8], ecx
0x180002c39  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002c3e  mov     [rsp+14E0h+var_14B4], eax
0x180002c42  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002c49  jnz     short loc_180002C6A
0x180002c4b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002c52  test    rax, rax
0x180002c55  jz      short loc_180002C60
0x180002c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c5c  test    al, al
0x180002c5e  jmp     short loc_180002C68
0x180002c60  call    cs:__imp_IsDebuggerPresent
0x180002c66  test    eax, eax
0x180002c68  jz      short loc_180002C71
0x180002c6a  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180002c6f  jz      short loc_180002C97
0x180002c71  mov     rax, cs:g_pfnResultLoggingCallback
0x180002c78  test    rax, rax
0x180002c7b  jz      short loc_180002CF0
0x180002c7d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002c84  jnz     short loc_180002CF0
0x180002c86  xor     r8d, r8d
0x180002c89  xor     edx, edx
0x180002c8b  lea     rcx, [rsp+14E0h+var_14C0]
0x180002c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c95  jmp     short loc_180002CF0
0x180002c97  mov     ebx, 800h
0x180002c9c  mov     rax, cs:g_pfnResultLoggingCallback
0x180002ca3  test    rax, rax
0x180002ca6  jz      short loc_180002CC5
0x180002ca8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002caf  jnz     short loc_180002CC5
0x180002cb1  mov     r8d, ebx
0x180002cb4  lea     rdx, [rbp+13E0h+OutputString]
0x180002cbb  lea     rcx, [rsp+14E0h+var_14C0]
0x180002cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cc5  cmp     [rbp+13E0h+OutputString], r12w
0x180002ccd  jnz     short loc_180002CE3
0x180002ccf  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180002cd4  mov     rdx, rbx; unsigned __int16 *
0x180002cd7  lea     rcx, [rbp+13E0h+OutputString]; this
0x180002cde  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002ce3  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180002cea  call    cs:__imp_OutputDebugStringW
0x180002cf0  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180002cf5  jnz     short loc_180002D00
0x180002cf7  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002cfe  jz      short loc_180002D12
0x180002d00  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002d07  test    rax, rax
0x180002d0a  jz      short loc_180002D12
0x180002d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d11  nop
0x180002d12  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180002d17  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
