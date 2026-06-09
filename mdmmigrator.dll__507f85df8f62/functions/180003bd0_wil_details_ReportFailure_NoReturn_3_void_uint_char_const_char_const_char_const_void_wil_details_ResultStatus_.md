# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180003bd0`
- end: `0x180003e49`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003940`

## callees

- `0x180002cbc`
- `0x180003bd0`
- `0x1800050a4`
- `0x180005844`
- `0x180005fb0`
- `0x180007070`
- `0x18001ea10`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003c89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003c89`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003e16`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003e16`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003d8c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003d8c`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // edx
  int v12; // r12d
  int v13; // ecx
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, v11);
  v18 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v19 = v13;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v12;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
  {
    v20 = -2147418113;
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v14);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v15);
  }
  wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180003bd0  mov     [rsp-8+arg_18], rbx
0x180003bd5  push    rbp
0x180003bd6  push    rsi
0x180003bd7  push    rdi
0x180003bd8  push    r12
0x180003bda  push    r13
0x180003bdc  push    r14
0x180003bde  push    r15
0x180003be0  lea     rbp, [rsp-13C0h]
0x180003be8  mov     eax, 14C0h
0x180003bed  call    _alloca_probe
0x180003bf2  sub     rsp, rax
0x180003bf5  mov     r14, r8
0x180003bf8  mov     esi, edx
0x180003bfa  mov     rdi, rcx
0x180003bfd  mov     r15, [rbp+13F0h+arg_28]
0x180003c04  xor     edx, edx; Val
0x180003c06  mov     r8d, 98h; Size
0x180003c0c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003c11  call    memset_0
0x180003c16  nop
0x180003c17  xor     r13d, r13d
0x180003c1a  mov     [rbp+13F0h+OutputString], r13w
0x180003c22  mov     [rbp+13F0h+var_1430], r13b
0x180003c26  mov     rbx, [rbp+13F0h+arg_30]
0x180003c2d  mov     ecx, [rbx]; this
0x180003c2f  mov     [rsp+14F0h+var_14C8], ecx
0x180003c33  mov     eax, [rbx+4]
0x180003c36  mov     [rsp+14F0h+var_14C4], eax
0x180003c3a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180003c3f  mov     r12d, eax
0x180003c42  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180003c4a  mov     ecx, r13d
0x180003c4d  lea     eax, [r13+8]
0x180003c51  cmp     dword ptr [rbx+8], 1
0x180003c55  cmovz   ecx, eax
0x180003c58  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003c5c  lea     ecx, [rax-7]
0x180003c5f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003c67  inc     ecx
0x180003c69  mov     [rsp+14F0h+var_14C0], ecx
0x180003c6d  mov     rcx, [rbp+13F0h+arg_38]
0x180003c74  test    rcx, rcx
0x180003c77  jz      short loc_180003C84
0x180003c79  cmp     [rcx], r13w
0x180003c7d  mov     [rsp+14F0h+var_14B8], rcx
0x180003c82  jnz     short loc_180003C89
0x180003c84  mov     [rsp+14F0h+var_14B8], r13
0x180003c89  call    cs:__imp_GetCurrentThreadId
0x180003c8f  mov     [rsp+14F0h+var_14B0], eax
0x180003c93  mov     [rsp+14F0h+var_1498], r14
0x180003c98  mov     [rsp+14F0h+var_1490], esi
0x180003c9c  mov     [rsp+14F0h+var_148C], r12d
0x180003ca1  mov     [rsp+14F0h+var_14A8], r13
0x180003ca6  mov     [rsp+14F0h+var_14A0], r13
0x180003cab  mov     [rbp+13F0h+var_1448], r15
0x180003caf  mov     [rbp+13F0h+var_1440], rdi
0x180003cb3  mov     [rsp+14F0h+var_1488], r13
0x180003cb8  xorps   xmm0, xmm0
0x180003cbb  xor     eax, eax
0x180003cbd  movups  [rbp+13F0h+var_1468], xmm0
0x180003cc1  mov     [rbp+13F0h+var_1458], rax
0x180003cc5  xorps   xmm1, xmm1
0x180003cc8  movups  [rsp+14F0h+var_1480], xmm1
0x180003ccd  mov     [rbp+13F0h+var_1470], rax
0x180003cd1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003cd8  test    rax, rax
0x180003cdb  jz      short loc_180003CE8
0x180003cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ce2  mov     [rbp+13F0h+var_1450], rax
0x180003ce6  jmp     short loc_180003CEC
0x180003ce8  mov     [rbp+13F0h+var_1450], r13
0x180003cec  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003cf3  test    rax, rax
0x180003cf6  jz      short loc_180003D02
0x180003cf8  lea     rcx, [rsp+14F0h+var_14D0]
0x180003cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d02  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003d09  test    rax, rax
0x180003d0c  jz      short loc_180003D22
0x180003d0e  mov     r8d, 400h
0x180003d14  lea     rdx, [rbp+13F0h+var_1430]
0x180003d18  lea     rcx, [rsp+14F0h+var_14D0]
0x180003d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d22  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003d29  test    rax, rax
0x180003d2c  jz      short loc_180003D38
0x180003d2e  lea     rcx, [rsp+14F0h+var_14D0]
0x180003d33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d38  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003d3f  test    rax, rax
0x180003d42  jz      short loc_180003D55
0x180003d44  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003d49  jnz     short loc_180003D55
0x180003d4b  lea     rcx, [rsp+14F0h+var_14D0]
0x180003d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d55  cmp     [rsp+14F0h+var_14C8], r13d
0x180003d5a  jl      short loc_180003D6E
0x180003d5c  mov     ecx, 8000FFFFh; this
0x180003d61  mov     [rsp+14F0h+var_14C8], ecx
0x180003d65  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003d6a  mov     [rsp+14F0h+var_14C4], eax
0x180003d6e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180003d75  jnz     short loc_180003D96
0x180003d77  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003d7e  test    rax, rax
0x180003d81  jz      short loc_180003D8C
0x180003d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d88  test    al, al
0x180003d8a  jmp     short loc_180003D94
0x180003d8c  call    cs:__imp_IsDebuggerPresent
0x180003d92  test    eax, eax
0x180003d94  jz      short loc_180003D9D
0x180003d96  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003d9b  jz      short loc_180003DC3
0x180003d9d  mov     rax, cs:g_pfnResultLoggingCallback
0x180003da4  test    rax, rax
0x180003da7  jz      short loc_180003E1C
0x180003da9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003db0  jnz     short loc_180003E1C
0x180003db2  xor     r8d, r8d
0x180003db5  xor     edx, edx
0x180003db7  lea     rcx, [rsp+14F0h+var_14D0]
0x180003dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dc1  jmp     short loc_180003E1C
0x180003dc3  mov     ebx, 800h
0x180003dc8  mov     rax, cs:g_pfnResultLoggingCallback
0x180003dcf  test    rax, rax
0x180003dd2  jz      short loc_180003DF1
0x180003dd4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003ddb  jnz     short loc_180003DF1
0x180003ddd  mov     r8d, ebx
0x180003de0  lea     rdx, [rbp+13F0h+OutputString]
0x180003de7  lea     rcx, [rsp+14F0h+var_14D0]
0x180003dec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003df1  cmp     [rbp+13F0h+OutputString], r13w
0x180003df9  jnz     short loc_180003E0F
0x180003dfb  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003e00  mov     rdx, rbx; unsigned __int16 *
0x180003e03  lea     rcx, [rbp+13F0h+OutputString]; this
0x180003e0a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003e0f  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003e16  call    cs:__imp_OutputDebugStringW
0x180003e1c  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003e21  jnz     short loc_180003E2C
0x180003e23  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180003e2a  jz      short loc_180003E3E
0x180003e2c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003e33  test    rax, rax
0x180003e36  jz      short loc_180003E3E
0x180003e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e3d  nop
0x180003e3e  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003e43  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
