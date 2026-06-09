# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180006be8`
- end: `0x180006e61`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180006958`

## callees

- `0x1800043a8`
- `0x180006be8`
- `0x180009204`
- `0x180009a50`
- `0x18000aa60`
- `0x18000d1c0`
- `0x1800388e0`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006ca1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006ca1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006e2e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006e2e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006da4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006da4`

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
0x180006be8  mov     [rsp-8+arg_18], rbx
0x180006bed  push    rbp
0x180006bee  push    rsi
0x180006bef  push    rdi
0x180006bf0  push    r12
0x180006bf2  push    r13
0x180006bf4  push    r14
0x180006bf6  push    r15
0x180006bf8  lea     rbp, [rsp-13C0h]
0x180006c00  mov     eax, 14C0h
0x180006c05  call    _alloca_probe
0x180006c0a  sub     rsp, rax
0x180006c0d  mov     r14, r8
0x180006c10  mov     esi, edx
0x180006c12  mov     rdi, rcx
0x180006c15  mov     r15, [rbp+13F0h+arg_28]
0x180006c1c  xor     edx, edx; Val
0x180006c1e  mov     r8d, 98h; Size
0x180006c24  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180006c29  call    memset_0
0x180006c2e  nop
0x180006c2f  xor     r13d, r13d
0x180006c32  mov     [rbp+13F0h+OutputString], r13w
0x180006c3a  mov     [rbp+13F0h+var_1430], r13b
0x180006c3e  mov     rbx, [rbp+13F0h+arg_30]
0x180006c45  mov     ecx, [rbx]; this
0x180006c47  mov     [rsp+14F0h+var_14C8], ecx
0x180006c4b  mov     eax, [rbx+4]
0x180006c4e  mov     [rsp+14F0h+var_14C4], eax
0x180006c52  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006c57  mov     r12d, eax
0x180006c5a  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180006c62  mov     ecx, r13d
0x180006c65  lea     eax, [r13+8]
0x180006c69  cmp     dword ptr [rbx+8], 1
0x180006c6d  cmovz   ecx, eax
0x180006c70  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180006c74  lea     ecx, [rax-7]
0x180006c77  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006c7f  inc     ecx
0x180006c81  mov     [rsp+14F0h+var_14C0], ecx
0x180006c85  mov     rcx, [rbp+13F0h+arg_38]
0x180006c8c  test    rcx, rcx
0x180006c8f  jz      short loc_180006C9C
0x180006c91  cmp     [rcx], r13w
0x180006c95  mov     [rsp+14F0h+var_14B8], rcx
0x180006c9a  jnz     short loc_180006CA1
0x180006c9c  mov     [rsp+14F0h+var_14B8], r13
0x180006ca1  call    cs:__imp_GetCurrentThreadId
0x180006ca7  mov     [rsp+14F0h+var_14B0], eax
0x180006cab  mov     [rsp+14F0h+var_1498], r14
0x180006cb0  mov     [rsp+14F0h+var_1490], esi
0x180006cb4  mov     [rsp+14F0h+var_148C], r12d
0x180006cb9  mov     [rsp+14F0h+var_14A8], r13
0x180006cbe  mov     [rsp+14F0h+var_14A0], r13
0x180006cc3  mov     [rbp+13F0h+var_1448], r15
0x180006cc7  mov     [rbp+13F0h+var_1440], rdi
0x180006ccb  mov     [rsp+14F0h+var_1488], r13
0x180006cd0  xorps   xmm0, xmm0
0x180006cd3  xor     eax, eax
0x180006cd5  movups  [rbp+13F0h+var_1468], xmm0
0x180006cd9  mov     [rbp+13F0h+var_1458], rax
0x180006cdd  xorps   xmm1, xmm1
0x180006ce0  movups  [rsp+14F0h+var_1480], xmm1
0x180006ce5  mov     [rbp+13F0h+var_1470], rax
0x180006ce9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006cf0  test    rax, rax
0x180006cf3  jz      short loc_180006D00
0x180006cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cfa  mov     [rbp+13F0h+var_1450], rax
0x180006cfe  jmp     short loc_180006D04
0x180006d00  mov     [rbp+13F0h+var_1450], r13
0x180006d04  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006d0b  test    rax, rax
0x180006d0e  jz      short loc_180006D1A
0x180006d10  lea     rcx, [rsp+14F0h+var_14D0]
0x180006d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d1a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006d21  test    rax, rax
0x180006d24  jz      short loc_180006D3A
0x180006d26  mov     r8d, 400h
0x180006d2c  lea     rdx, [rbp+13F0h+var_1430]
0x180006d30  lea     rcx, [rsp+14F0h+var_14D0]
0x180006d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d3a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006d41  test    rax, rax
0x180006d44  jz      short loc_180006D50
0x180006d46  lea     rcx, [rsp+14F0h+var_14D0]
0x180006d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d50  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006d57  test    rax, rax
0x180006d5a  jz      short loc_180006D6D
0x180006d5c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180006d61  jnz     short loc_180006D6D
0x180006d63  lea     rcx, [rsp+14F0h+var_14D0]
0x180006d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d6d  cmp     [rsp+14F0h+var_14C8], r13d
0x180006d72  jl      short loc_180006D86
0x180006d74  mov     ecx, 8000FFFFh; this
0x180006d79  mov     [rsp+14F0h+var_14C8], ecx
0x180006d7d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006d82  mov     [rsp+14F0h+var_14C4], eax
0x180006d86  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180006d8d  jnz     short loc_180006DAE
0x180006d8f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006d96  test    rax, rax
0x180006d99  jz      short loc_180006DA4
0x180006d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006da0  test    al, al
0x180006da2  jmp     short loc_180006DAC
0x180006da4  call    cs:__imp_IsDebuggerPresent
0x180006daa  test    eax, eax
0x180006dac  jz      short loc_180006DB5
0x180006dae  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180006db3  jz      short loc_180006DDB
0x180006db5  mov     rax, cs:g_pfnResultLoggingCallback
0x180006dbc  test    rax, rax
0x180006dbf  jz      short loc_180006E34
0x180006dc1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180006dc8  jnz     short loc_180006E34
0x180006dca  xor     r8d, r8d
0x180006dcd  xor     edx, edx
0x180006dcf  lea     rcx, [rsp+14F0h+var_14D0]
0x180006dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dd9  jmp     short loc_180006E34
0x180006ddb  mov     ebx, 800h
0x180006de0  mov     rax, cs:g_pfnResultLoggingCallback
0x180006de7  test    rax, rax
0x180006dea  jz      short loc_180006E09
0x180006dec  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180006df3  jnz     short loc_180006E09
0x180006df5  mov     r8d, ebx
0x180006df8  lea     rdx, [rbp+13F0h+OutputString]
0x180006dff  lea     rcx, [rsp+14F0h+var_14D0]
0x180006e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e09  cmp     [rbp+13F0h+OutputString], r13w
0x180006e11  jnz     short loc_180006E27
0x180006e13  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180006e18  mov     rdx, rbx; unsigned __int16 *
0x180006e1b  lea     rcx, [rbp+13F0h+OutputString]; this
0x180006e22  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006e27  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180006e2e  call    cs:__imp_OutputDebugStringW
0x180006e34  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180006e39  jnz     short loc_180006E44
0x180006e3b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180006e42  jz      short loc_180006E56
0x180006e44  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006e4b  test    rax, rax
0x180006e4e  jz      short loc_180006E56
0x180006e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e55  nop
0x180006e56  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180006e5b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
