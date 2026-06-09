# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180003e94`
- end: `0x1800040f4`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003c38`

## callees

- `0x180003e94`
- `0x180006444`
- `0x180006eb8`
- `0x1800086e0`
- `0x18000a3b0`
- `0x18000ccde`
- `0x18000cda0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800040c2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800040c2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004038`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004038`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003f35`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003f35`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // eax
  int v11; // edx
  int v12; // eax
  int v13; // edi
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  __int64 v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v22, v11);
  v19 = a7[2] == 1;
  v13 = v12;
  v20 = 3;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
  {
    v22 = -2147418113;
    v23 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v16);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( (v21 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v17);
  }
  wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x180003e94  mov     [rsp-8+arg_18], rbx
0x180003e99  push    rbp
0x180003e9a  push    rsi
0x180003e9b  push    rdi
0x180003e9c  push    r12
0x180003e9e  push    r13
0x180003ea0  push    r14
0x180003ea2  push    r15
0x180003ea4  lea     rbp, [rsp-13C0h]
0x180003eac  mov     eax, 14C0h
0x180003eb1  call    _alloca_probe
0x180003eb6  sub     rsp, rax
0x180003eb9  mov     rsi, [rbp+13F0h+arg_28]
0x180003ec0  mov     r15, r8
0x180003ec3  mov     r14d, edx
0x180003ec6  mov     r12, rcx
0x180003ec9  xor     edx, edx; Val
0x180003ecb  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003ed0  mov     r8d, 98h; Size
0x180003ed6  call    memset_0
0x180003edb  mov     rbx, [rbp+13F0h+arg_30]
0x180003ee2  xor     r13d, r13d
0x180003ee5  mov     [rbp+13F0h+OutputString], r13w
0x180003eed  mov     [rbp+13F0h+var_1430], r13b
0x180003ef1  mov     ecx, [rbx]; this
0x180003ef3  mov     eax, [rbx+4]
0x180003ef6  mov     [rsp+14F0h+var_14C8], ecx
0x180003efa  mov     [rsp+14F0h+var_14C4], eax
0x180003efe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180003f03  cmp     dword ptr [rbx+8], 1
0x180003f07  mov     edi, eax
0x180003f09  lea     eax, [r13+8]
0x180003f0d  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180003f15  mov     ecx, r13d
0x180003f18  cmovz   ecx, eax
0x180003f1b  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003f1f  lea     ecx, [rax-7]
0x180003f22  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003f2a  inc     ecx
0x180003f2c  mov     [rsp+14F0h+var_14B8], r13
0x180003f31  mov     [rsp+14F0h+var_14C0], ecx
0x180003f35  call    cs:__imp_GetCurrentThreadId
0x180003f3b  xorps   xmm0, xmm0
0x180003f3e  mov     [rsp+14F0h+var_1498], r15
0x180003f43  mov     [rsp+14F0h+var_14B0], eax
0x180003f47  xorps   xmm1, xmm1
0x180003f4a  xor     eax, eax
0x180003f4c  mov     [rsp+14F0h+var_1490], r14d
0x180003f51  mov     [rbp+13F0h+var_1458], rax
0x180003f55  mov     [rbp+13F0h+var_1470], rax
0x180003f59  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003f60  mov     [rsp+14F0h+var_148C], edi
0x180003f64  mov     [rsp+14F0h+var_14A8], r13
0x180003f69  mov     [rsp+14F0h+var_14A0], r13
0x180003f6e  mov     [rbp+13F0h+var_1448], rsi
0x180003f72  mov     [rbp+13F0h+var_1440], r12
0x180003f76  mov     [rsp+14F0h+var_1488], r13
0x180003f7b  movups  [rbp+13F0h+var_1468], xmm0
0x180003f7f  movups  [rsp+14F0h+var_1480], xmm1
0x180003f84  test    rax, rax
0x180003f87  jz      short loc_180003F94
0x180003f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f8e  mov     [rbp+13F0h+var_1450], rax
0x180003f92  jmp     short loc_180003F98
0x180003f94  mov     [rbp+13F0h+var_1450], r13
0x180003f98  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003f9f  test    rax, rax
0x180003fa2  jz      short loc_180003FAE
0x180003fa4  lea     rcx, [rsp+14F0h+var_14D0]
0x180003fa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fae  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003fb5  test    rax, rax
0x180003fb8  jz      short loc_180003FCE
0x180003fba  mov     r8d, 400h
0x180003fc0  lea     rdx, [rbp+13F0h+var_1430]
0x180003fc4  lea     rcx, [rsp+14F0h+var_14D0]
0x180003fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fce  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003fd5  test    rax, rax
0x180003fd8  jz      short loc_180003FE4
0x180003fda  lea     rcx, [rsp+14F0h+var_14D0]
0x180003fdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fe4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003feb  test    rax, rax
0x180003fee  jz      short loc_180004001
0x180003ff0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003ff5  jnz     short loc_180004001
0x180003ff7  lea     rcx, [rsp+14F0h+var_14D0]
0x180003ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004001  cmp     [rsp+14F0h+var_14C8], r13d
0x180004006  jl      short loc_18000401A
0x180004008  mov     ecx, 8000FFFFh; this
0x18000400d  mov     [rsp+14F0h+var_14C8], ecx
0x180004011  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004016  mov     [rsp+14F0h+var_14C4], eax
0x18000401a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180004021  jnz     short loc_180004042
0x180004023  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000402a  test    rax, rax
0x18000402d  jz      short loc_180004038
0x18000402f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004034  test    al, al
0x180004036  jmp     short loc_180004040
0x180004038  call    cs:__imp_IsDebuggerPresent
0x18000403e  test    eax, eax
0x180004040  jz      short loc_180004049
0x180004042  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004047  jz      short loc_18000406F
0x180004049  mov     rax, cs:g_pfnResultLoggingCallback
0x180004050  test    rax, rax
0x180004053  jz      short loc_1800040C8
0x180004055  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000405c  jnz     short loc_1800040C8
0x18000405e  xor     r8d, r8d
0x180004061  lea     rcx, [rsp+14F0h+var_14D0]
0x180004066  xor     edx, edx
0x180004068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000406d  jmp     short loc_1800040C8
0x18000406f  mov     rax, cs:g_pfnResultLoggingCallback
0x180004076  mov     ebx, 800h
0x18000407b  test    rax, rax
0x18000407e  jz      short loc_18000409D
0x180004080  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180004087  jnz     short loc_18000409D
0x180004089  mov     r8d, ebx
0x18000408c  lea     rdx, [rbp+13F0h+OutputString]
0x180004093  lea     rcx, [rsp+14F0h+var_14D0]
0x180004098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000409d  cmp     [rbp+13F0h+OutputString], r13w
0x1800040a5  jnz     short loc_1800040BB
0x1800040a7  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800040ac  mov     rdx, rbx; unsigned __int16 *
0x1800040af  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800040b6  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800040bb  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800040c2  call    cs:__imp_OutputDebugStringW
0x1800040c8  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800040cd  jnz     short loc_1800040D8
0x1800040cf  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800040d6  jz      short loc_1800040E9
0x1800040d8  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800040df  test    rax, rax
0x1800040e2  jz      short loc_1800040E9
0x1800040e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040e9  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800040ee  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
