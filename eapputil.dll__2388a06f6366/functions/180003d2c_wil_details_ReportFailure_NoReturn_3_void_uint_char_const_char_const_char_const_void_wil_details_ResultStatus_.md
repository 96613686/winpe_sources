# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180003d2c`
- end: `0x180003fa5`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003a9c`

## callees

- `0x180002b78`
- `0x180003d2c`
- `0x180005584`
- `0x180005d24`
- `0x1800065e0`
- `0x180007950`
- `0x180030510`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003de5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003de5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003ee8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003ee8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003f72`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003f72`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180003d2c  mov     [rsp-8+arg_18], rbx
0x180003d31  push    rbp
0x180003d32  push    rsi
0x180003d33  push    rdi
0x180003d34  push    r12
0x180003d36  push    r13
0x180003d38  push    r14
0x180003d3a  push    r15
0x180003d3c  lea     rbp, [rsp-13C0h]
0x180003d44  mov     eax, 14C0h
0x180003d49  call    _alloca_probe
0x180003d4e  sub     rsp, rax
0x180003d51  mov     r14, r8
0x180003d54  mov     esi, edx
0x180003d56  mov     rdi, rcx
0x180003d59  mov     r15, [rbp+13F0h+arg_28]
0x180003d60  xor     edx, edx; Val
0x180003d62  mov     r8d, 98h; Size
0x180003d68  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003d6d  call    memset_0
0x180003d72  nop
0x180003d73  xor     r13d, r13d
0x180003d76  mov     [rbp+13F0h+OutputString], r13w
0x180003d7e  mov     [rbp+13F0h+var_1430], r13b
0x180003d82  mov     rbx, [rbp+13F0h+arg_30]
0x180003d89  mov     ecx, [rbx]; this
0x180003d8b  mov     [rsp+14F0h+var_14C8], ecx
0x180003d8f  mov     eax, [rbx+4]
0x180003d92  mov     [rsp+14F0h+var_14C4], eax
0x180003d96  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180003d9b  mov     r12d, eax
0x180003d9e  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180003da6  mov     ecx, r13d
0x180003da9  lea     eax, [r13+8]
0x180003dad  cmp     dword ptr [rbx+8], 1
0x180003db1  cmovz   ecx, eax
0x180003db4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003db8  lea     ecx, [rax-7]
0x180003dbb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003dc3  inc     ecx
0x180003dc5  mov     [rsp+14F0h+var_14C0], ecx
0x180003dc9  mov     rcx, [rbp+13F0h+arg_38]
0x180003dd0  test    rcx, rcx
0x180003dd3  jz      short loc_180003DE0
0x180003dd5  cmp     [rcx], r13w
0x180003dd9  mov     [rsp+14F0h+var_14B8], rcx
0x180003dde  jnz     short loc_180003DE5
0x180003de0  mov     [rsp+14F0h+var_14B8], r13
0x180003de5  call    cs:__imp_GetCurrentThreadId
0x180003deb  mov     [rsp+14F0h+var_14B0], eax
0x180003def  mov     [rsp+14F0h+var_1498], r14
0x180003df4  mov     [rsp+14F0h+var_1490], esi
0x180003df8  mov     [rsp+14F0h+var_148C], r12d
0x180003dfd  mov     [rsp+14F0h+var_14A8], r13
0x180003e02  mov     [rsp+14F0h+var_14A0], r13
0x180003e07  mov     [rbp+13F0h+var_1448], r15
0x180003e0b  mov     [rbp+13F0h+var_1440], rdi
0x180003e0f  mov     [rsp+14F0h+var_1488], r13
0x180003e14  xorps   xmm0, xmm0
0x180003e17  xor     eax, eax
0x180003e19  movups  [rbp+13F0h+var_1468], xmm0
0x180003e1d  mov     [rbp+13F0h+var_1458], rax
0x180003e21  xorps   xmm1, xmm1
0x180003e24  movups  [rsp+14F0h+var_1480], xmm1
0x180003e29  mov     [rbp+13F0h+var_1470], rax
0x180003e2d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003e34  test    rax, rax
0x180003e37  jz      short loc_180003E44
0x180003e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e3e  mov     [rbp+13F0h+var_1450], rax
0x180003e42  jmp     short loc_180003E48
0x180003e44  mov     [rbp+13F0h+var_1450], r13
0x180003e48  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003e4f  test    rax, rax
0x180003e52  jz      short loc_180003E5E
0x180003e54  lea     rcx, [rsp+14F0h+var_14D0]
0x180003e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e5e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003e65  test    rax, rax
0x180003e68  jz      short loc_180003E7E
0x180003e6a  mov     r8d, 400h
0x180003e70  lea     rdx, [rbp+13F0h+var_1430]
0x180003e74  lea     rcx, [rsp+14F0h+var_14D0]
0x180003e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e7e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003e85  test    rax, rax
0x180003e88  jz      short loc_180003E94
0x180003e8a  lea     rcx, [rsp+14F0h+var_14D0]
0x180003e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e94  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003e9b  test    rax, rax
0x180003e9e  jz      short loc_180003EB1
0x180003ea0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003ea5  jnz     short loc_180003EB1
0x180003ea7  lea     rcx, [rsp+14F0h+var_14D0]
0x180003eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003eb1  cmp     [rsp+14F0h+var_14C8], r13d
0x180003eb6  jl      short loc_180003ECA
0x180003eb8  mov     ecx, 8000FFFFh; this
0x180003ebd  mov     [rsp+14F0h+var_14C8], ecx
0x180003ec1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003ec6  mov     [rsp+14F0h+var_14C4], eax
0x180003eca  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180003ed1  jnz     short loc_180003EF2
0x180003ed3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003eda  test    rax, rax
0x180003edd  jz      short loc_180003EE8
0x180003edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ee4  test    al, al
0x180003ee6  jmp     short loc_180003EF0
0x180003ee8  call    cs:__imp_IsDebuggerPresent
0x180003eee  test    eax, eax
0x180003ef0  jz      short loc_180003EF9
0x180003ef2  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003ef7  jz      short loc_180003F1F
0x180003ef9  mov     rax, cs:g_pfnResultLoggingCallback
0x180003f00  test    rax, rax
0x180003f03  jz      short loc_180003F78
0x180003f05  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003f0c  jnz     short loc_180003F78
0x180003f0e  xor     r8d, r8d
0x180003f11  xor     edx, edx
0x180003f13  lea     rcx, [rsp+14F0h+var_14D0]
0x180003f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f1d  jmp     short loc_180003F78
0x180003f1f  mov     ebx, 800h
0x180003f24  mov     rax, cs:g_pfnResultLoggingCallback
0x180003f2b  test    rax, rax
0x180003f2e  jz      short loc_180003F4D
0x180003f30  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003f37  jnz     short loc_180003F4D
0x180003f39  mov     r8d, ebx
0x180003f3c  lea     rdx, [rbp+13F0h+OutputString]
0x180003f43  lea     rcx, [rsp+14F0h+var_14D0]
0x180003f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f4d  cmp     [rbp+13F0h+OutputString], r13w
0x180003f55  jnz     short loc_180003F6B
0x180003f57  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003f5c  mov     rdx, rbx; unsigned __int16 *
0x180003f5f  lea     rcx, [rbp+13F0h+OutputString]; this
0x180003f66  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003f6b  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003f72  call    cs:__imp_OutputDebugStringW
0x180003f78  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003f7d  jnz     short loc_180003F88
0x180003f7f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180003f86  jz      short loc_180003F9A
0x180003f88  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003f8f  test    rax, rax
0x180003f92  jz      short loc_180003F9A
0x180003f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f99  nop
0x180003f9a  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003f9f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
