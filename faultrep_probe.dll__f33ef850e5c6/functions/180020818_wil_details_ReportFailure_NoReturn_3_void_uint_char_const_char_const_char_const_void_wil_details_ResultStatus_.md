# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180020818`
- end: `0x180020a7a`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180020668`

## callees

- `0x180003474`
- `0x180005804`
- `0x180005bec`
- `0x180005f50`
- `0x180006f90`
- `0x180020818`
- `0x180049280`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800208ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800208ba`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180020a47`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180020a47`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800209bd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800209bd`

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
        int *a7)
{
  int v10; // edx
  int v11; // edi
  int v12; // ecx
  const struct wil::FailureInfo *v13; // rdx
  __int64 v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v19, v10);
  v17 = 3;
  v12 = 0;
  if ( a7[2] == 1 )
    v12 = 8;
  v18 = v12;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v11;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
  {
    v19 = -2147418113;
    v20 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v13);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (__int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( (v18 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v14);
  }
  wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x180020818  mov     [rsp-8+arg_18], rbx
0x18002081d  push    rbp
0x18002081e  push    rsi
0x18002081f  push    rdi
0x180020820  push    r12
0x180020822  push    r13
0x180020824  push    r14
0x180020826  push    r15
0x180020828  lea     rbp, [rsp-13C0h]
0x180020830  mov     eax, 14C0h
0x180020835  call    _alloca_probe
0x18002083a  sub     rsp, rax
0x18002083d  mov     r15, r8
0x180020840  mov     r14d, edx
0x180020843  mov     r12, rcx
0x180020846  mov     rsi, [rbp+13F0h+arg_28]
0x18002084d  xor     edx, edx; Val
0x18002084f  mov     r8d, 98h; Size
0x180020855  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18002085a  call    memset_0
0x18002085f  nop
0x180020860  xor     r13d, r13d
0x180020863  mov     [rbp+13F0h+OutputString], r13w
0x18002086b  mov     [rbp+13F0h+var_1430], r13b
0x18002086f  mov     rbx, [rbp+13F0h+arg_30]
0x180020876  mov     ecx, [rbx]; this
0x180020878  mov     [rsp+14F0h+var_14C8], ecx
0x18002087c  mov     eax, [rbx+4]
0x18002087f  mov     [rsp+14F0h+var_14C4], eax
0x180020883  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180020888  mov     edi, eax
0x18002088a  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180020892  mov     ecx, r13d
0x180020895  lea     eax, [r13+8]
0x180020899  cmp     dword ptr [rbx+8], 1
0x18002089d  cmovz   ecx, eax
0x1800208a0  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800208a4  lea     ecx, [rax-7]
0x1800208a7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800208af  inc     ecx
0x1800208b1  mov     [rsp+14F0h+var_14C0], ecx
0x1800208b5  mov     [rsp+14F0h+var_14B8], r13
0x1800208ba  call    cs:__imp_GetCurrentThreadId
0x1800208c0  mov     [rsp+14F0h+var_14B0], eax
0x1800208c4  mov     [rsp+14F0h+var_1498], r15
0x1800208c9  mov     [rsp+14F0h+var_1490], r14d
0x1800208ce  mov     [rsp+14F0h+var_148C], edi
0x1800208d2  mov     [rsp+14F0h+var_14A8], r13
0x1800208d7  mov     [rsp+14F0h+var_14A0], r13
0x1800208dc  mov     [rbp+13F0h+var_1448], rsi
0x1800208e0  mov     [rbp+13F0h+var_1440], r12
0x1800208e4  mov     [rsp+14F0h+var_1488], r13
0x1800208e9  xorps   xmm0, xmm0
0x1800208ec  xor     eax, eax
0x1800208ee  movups  [rbp+13F0h+var_1468], xmm0
0x1800208f2  mov     [rbp+13F0h+var_1458], rax
0x1800208f6  xorps   xmm1, xmm1
0x1800208f9  movups  [rsp+14F0h+var_1480], xmm1
0x1800208fe  mov     [rbp+13F0h+var_1470], rax
0x180020902  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180020909  test    rax, rax
0x18002090c  jz      short loc_180020919
0x18002090e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020913  mov     [rbp+13F0h+var_1450], rax
0x180020917  jmp     short loc_18002091D
0x180020919  mov     [rbp+13F0h+var_1450], r13
0x18002091d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180020924  test    rax, rax
0x180020927  jz      short loc_180020933
0x180020929  lea     rcx, [rsp+14F0h+var_14D0]
0x18002092e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020933  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002093a  test    rax, rax
0x18002093d  jz      short loc_180020953
0x18002093f  mov     r8d, 400h
0x180020945  lea     rdx, [rbp+13F0h+var_1430]
0x180020949  lea     rcx, [rsp+14F0h+var_14D0]
0x18002094e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020953  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002095a  test    rax, rax
0x18002095d  jz      short loc_180020969
0x18002095f  lea     rcx, [rsp+14F0h+var_14D0]
0x180020964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020969  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180020970  test    rax, rax
0x180020973  jz      short loc_180020986
0x180020975  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18002097a  jnz     short loc_180020986
0x18002097c  lea     rcx, [rsp+14F0h+var_14D0]
0x180020981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020986  cmp     [rsp+14F0h+var_14C8], r13d
0x18002098b  jl      short loc_18002099F
0x18002098d  mov     ecx, 8000FFFFh; this
0x180020992  mov     [rsp+14F0h+var_14C8], ecx
0x180020996  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002099b  mov     [rsp+14F0h+var_14C4], eax
0x18002099f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800209a6  jnz     short loc_1800209C7
0x1800209a8  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800209af  test    rax, rax
0x1800209b2  jz      short loc_1800209BD
0x1800209b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209b9  test    al, al
0x1800209bb  jmp     short loc_1800209C5
0x1800209bd  call    cs:__imp_IsDebuggerPresent
0x1800209c3  test    eax, eax
0x1800209c5  jz      short loc_1800209CE
0x1800209c7  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800209cc  jz      short loc_1800209F4
0x1800209ce  mov     rax, cs:g_pfnResultLoggingCallback
0x1800209d5  test    rax, rax
0x1800209d8  jz      short loc_180020A4D
0x1800209da  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800209e1  jnz     short loc_180020A4D
0x1800209e3  xor     r8d, r8d
0x1800209e6  xor     edx, edx
0x1800209e8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800209ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209f2  jmp     short loc_180020A4D
0x1800209f4  mov     ebx, 800h
0x1800209f9  mov     rax, cs:g_pfnResultLoggingCallback
0x180020a00  test    rax, rax
0x180020a03  jz      short loc_180020A22
0x180020a05  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180020a0c  jnz     short loc_180020A22
0x180020a0e  mov     r8d, ebx
0x180020a11  lea     rdx, [rbp+13F0h+OutputString]
0x180020a18  lea     rcx, [rsp+14F0h+var_14D0]
0x180020a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a22  cmp     [rbp+13F0h+OutputString], r13w
0x180020a2a  jnz     short loc_180020A40
0x180020a2c  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180020a31  mov     rdx, rbx; wchar_t *
0x180020a34  lea     rcx, [rbp+13F0h+OutputString]; this
0x180020a3b  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180020a40  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180020a47  call    cs:__imp_OutputDebugStringW
0x180020a4d  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180020a52  jnz     short loc_180020A5D
0x180020a54  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180020a5b  jz      short loc_180020A6F
0x180020a5d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180020a64  test    rax, rax
0x180020a67  jz      short loc_180020A6F
0x180020a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a6e  nop
0x180020a6f  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180020a74  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
