# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140003cd4`
- end: `0x140003f4d`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, __int64, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140003718`

## callees

- `0x140002d4c`
- `0x140003cd4`
- `0x140009350`
- `0x140009b94`
- `0x14000b2f0`
- `0x14000fa00`
- `0x1400113b0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003d8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003d8d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003f1a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003f1a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003e90`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003e90`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
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
0x140003cd4  mov     [rsp-8+arg_18], rbx
0x140003cd9  push    rbp
0x140003cda  push    rsi
0x140003cdb  push    rdi
0x140003cdc  push    r12
0x140003cde  push    r13
0x140003ce0  push    r14
0x140003ce2  push    r15
0x140003ce4  lea     rbp, [rsp-13C0h]
0x140003cec  mov     eax, 14C0h
0x140003cf1  call    _alloca_probe
0x140003cf6  sub     rsp, rax
0x140003cf9  mov     r14, r8
0x140003cfc  mov     esi, edx
0x140003cfe  mov     rdi, rcx
0x140003d01  mov     r15, [rbp+13F0h+arg_28]
0x140003d08  xor     edx, edx; Val
0x140003d0a  mov     r8d, 98h; Size
0x140003d10  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140003d15  call    memset_0
0x140003d1a  nop
0x140003d1b  xor     r13d, r13d
0x140003d1e  mov     [rbp+13F0h+OutputString], r13w
0x140003d26  mov     [rbp+13F0h+var_1430], r13b
0x140003d2a  mov     rbx, [rbp+13F0h+arg_30]
0x140003d31  mov     ecx, [rbx]; this
0x140003d33  mov     [rsp+14F0h+var_14C8], ecx
0x140003d37  mov     eax, [rbx+4]
0x140003d3a  mov     [rsp+14F0h+var_14C4], eax
0x140003d3e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140003d43  mov     r12d, eax
0x140003d46  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x140003d4e  mov     ecx, r13d
0x140003d51  lea     eax, [r13+8]
0x140003d55  cmp     dword ptr [rbx+8], 1
0x140003d59  cmovz   ecx, eax
0x140003d5c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140003d60  lea     ecx, [rax-7]
0x140003d63  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003d6b  inc     ecx
0x140003d6d  mov     [rsp+14F0h+var_14C0], ecx
0x140003d71  mov     rcx, [rbp+13F0h+arg_38]
0x140003d78  test    rcx, rcx
0x140003d7b  jz      short loc_140003D88
0x140003d7d  cmp     [rcx], r13w
0x140003d81  mov     [rsp+14F0h+var_14B8], rcx
0x140003d86  jnz     short loc_140003D8D
0x140003d88  mov     [rsp+14F0h+var_14B8], r13
0x140003d8d  call    cs:__imp_GetCurrentThreadId
0x140003d93  mov     [rsp+14F0h+var_14B0], eax
0x140003d97  mov     [rsp+14F0h+var_1498], r14
0x140003d9c  mov     [rsp+14F0h+var_1490], esi
0x140003da0  mov     [rsp+14F0h+var_148C], r12d
0x140003da5  mov     [rsp+14F0h+var_14A8], r13
0x140003daa  mov     [rsp+14F0h+var_14A0], r13
0x140003daf  mov     [rbp+13F0h+var_1448], r15
0x140003db3  mov     [rbp+13F0h+var_1440], rdi
0x140003db7  mov     [rsp+14F0h+var_1488], r13
0x140003dbc  xorps   xmm0, xmm0
0x140003dbf  xor     eax, eax
0x140003dc1  movups  [rbp+13F0h+var_1468], xmm0
0x140003dc5  mov     [rbp+13F0h+var_1458], rax
0x140003dc9  xorps   xmm1, xmm1
0x140003dcc  movups  [rsp+14F0h+var_1480], xmm1
0x140003dd1  mov     [rbp+13F0h+var_1470], rax
0x140003dd5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003ddc  test    rax, rax
0x140003ddf  jz      short loc_140003DEC
0x140003de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003de6  mov     [rbp+13F0h+var_1450], rax
0x140003dea  jmp     short loc_140003DF0
0x140003dec  mov     [rbp+13F0h+var_1450], r13
0x140003df0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003df7  test    rax, rax
0x140003dfa  jz      short loc_140003E06
0x140003dfc  lea     rcx, [rsp+14F0h+var_14D0]
0x140003e01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003e06  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140003e0d  test    rax, rax
0x140003e10  jz      short loc_140003E26
0x140003e12  mov     r8d, 400h
0x140003e18  lea     rdx, [rbp+13F0h+var_1430]
0x140003e1c  lea     rcx, [rsp+14F0h+var_14D0]
0x140003e21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003e26  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003e2d  test    rax, rax
0x140003e30  jz      short loc_140003E3C
0x140003e32  lea     rcx, [rsp+14F0h+var_14D0]
0x140003e37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003e3c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003e43  test    rax, rax
0x140003e46  jz      short loc_140003E59
0x140003e48  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140003e4d  jnz     short loc_140003E59
0x140003e4f  lea     rcx, [rsp+14F0h+var_14D0]
0x140003e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003e59  cmp     [rsp+14F0h+var_14C8], r13d
0x140003e5e  jl      short loc_140003E72
0x140003e60  mov     ecx, 8000FFFFh; this
0x140003e65  mov     [rsp+14F0h+var_14C8], ecx
0x140003e69  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140003e6e  mov     [rsp+14F0h+var_14C4], eax
0x140003e72  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140003e79  jnz     short loc_140003E9A
0x140003e7b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140003e82  test    rax, rax
0x140003e85  jz      short loc_140003E90
0x140003e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003e8c  test    al, al
0x140003e8e  jmp     short loc_140003E98
0x140003e90  call    cs:__imp_IsDebuggerPresent
0x140003e96  test    eax, eax
0x140003e98  jz      short loc_140003EA1
0x140003e9a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140003e9f  jz      short loc_140003EC7
0x140003ea1  mov     rax, cs:g_pfnResultLoggingCallback
0x140003ea8  test    rax, rax
0x140003eab  jz      short loc_140003F20
0x140003ead  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140003eb4  jnz     short loc_140003F20
0x140003eb6  xor     r8d, r8d
0x140003eb9  xor     edx, edx
0x140003ebb  lea     rcx, [rsp+14F0h+var_14D0]
0x140003ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003ec5  jmp     short loc_140003F20
0x140003ec7  mov     ebx, 800h
0x140003ecc  mov     rax, cs:g_pfnResultLoggingCallback
0x140003ed3  test    rax, rax
0x140003ed6  jz      short loc_140003EF5
0x140003ed8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140003edf  jnz     short loc_140003EF5
0x140003ee1  mov     r8d, ebx
0x140003ee4  lea     rdx, [rbp+13F0h+OutputString]
0x140003eeb  lea     rcx, [rsp+14F0h+var_14D0]
0x140003ef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003ef5  cmp     [rbp+13F0h+OutputString], r13w
0x140003efd  jnz     short loc_140003F13
0x140003eff  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140003f04  mov     rdx, rbx; unsigned __int16 *
0x140003f07  lea     rcx, [rbp+13F0h+OutputString]; this
0x140003f0e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140003f13  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140003f1a  call    cs:__imp_OutputDebugStringW
0x140003f20  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140003f25  jnz     short loc_140003F30
0x140003f27  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140003f2e  jz      short loc_140003F42
0x140003f30  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003f37  test    rax, rax
0x140003f3a  jz      short loc_140003F42
0x140003f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f41  nop
0x140003f42  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140003f47  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
