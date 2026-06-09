# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140003c24`
- end: `0x140003e86`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400036e4`

## callees

- `0x140003168`
- `0x140003c24`
- `0x1400070c4`
- `0x140007908`
- `0x140008870`
- `0x14000ace0`
- `0x1400130e0`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003cc6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003cc6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003dc9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003dc9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003e53`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003e53`

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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v17, v15);
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
0x140003c24  mov     [rsp-8+arg_18], rbx
0x140003c29  push    rbp
0x140003c2a  push    rsi
0x140003c2b  push    rdi
0x140003c2c  push    r12
0x140003c2e  push    r13
0x140003c30  push    r14
0x140003c32  push    r15
0x140003c34  lea     rbp, [rsp-13C0h]
0x140003c3c  mov     eax, 14C0h
0x140003c41  call    _alloca_probe
0x140003c46  sub     rsp, rax
0x140003c49  mov     r15, r8
0x140003c4c  mov     r14d, edx
0x140003c4f  mov     r12, rcx
0x140003c52  mov     rsi, [rbp+13F0h+arg_28]
0x140003c59  xor     edx, edx; Val
0x140003c5b  mov     r8d, 98h; Size
0x140003c61  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140003c66  call    memset_0
0x140003c6b  nop
0x140003c6c  xor     r13d, r13d
0x140003c6f  mov     [rbp+13F0h+OutputString], r13w
0x140003c77  mov     [rbp+13F0h+var_1430], r13b
0x140003c7b  mov     rbx, [rbp+13F0h+arg_30]
0x140003c82  mov     ecx, [rbx]; this
0x140003c84  mov     [rsp+14F0h+var_14C8], ecx
0x140003c88  mov     eax, [rbx+4]
0x140003c8b  mov     [rsp+14F0h+var_14C4], eax
0x140003c8f  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140003c94  mov     edi, eax
0x140003c96  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x140003c9e  mov     ecx, r13d
0x140003ca1  lea     eax, [r13+8]
0x140003ca5  cmp     dword ptr [rbx+8], 1
0x140003ca9  cmovz   ecx, eax
0x140003cac  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140003cb0  lea     ecx, [rax-7]
0x140003cb3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003cbb  inc     ecx
0x140003cbd  mov     [rsp+14F0h+var_14C0], ecx
0x140003cc1  mov     [rsp+14F0h+var_14B8], r13
0x140003cc6  call    cs:__imp_GetCurrentThreadId
0x140003ccc  mov     [rsp+14F0h+var_14B0], eax
0x140003cd0  mov     [rsp+14F0h+var_1498], r15
0x140003cd5  mov     [rsp+14F0h+var_1490], r14d
0x140003cda  mov     [rsp+14F0h+var_148C], edi
0x140003cde  mov     [rsp+14F0h+var_14A8], r13
0x140003ce3  mov     [rsp+14F0h+var_14A0], r13
0x140003ce8  mov     [rbp+13F0h+var_1448], rsi
0x140003cec  mov     [rbp+13F0h+var_1440], r12
0x140003cf0  mov     [rsp+14F0h+var_1488], r13
0x140003cf5  xorps   xmm0, xmm0
0x140003cf8  xor     eax, eax
0x140003cfa  movups  [rbp+13F0h+var_1468], xmm0
0x140003cfe  mov     [rbp+13F0h+var_1458], rax
0x140003d02  xorps   xmm1, xmm1
0x140003d05  movups  [rsp+14F0h+var_1480], xmm1
0x140003d0a  mov     [rbp+13F0h+var_1470], rax
0x140003d0e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003d15  test    rax, rax
0x140003d18  jz      short loc_140003D25
0x140003d1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d1f  mov     [rbp+13F0h+var_1450], rax
0x140003d23  jmp     short loc_140003D29
0x140003d25  mov     [rbp+13F0h+var_1450], r13
0x140003d29  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003d30  test    rax, rax
0x140003d33  jz      short loc_140003D3F
0x140003d35  lea     rcx, [rsp+14F0h+var_14D0]
0x140003d3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d3f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140003d46  test    rax, rax
0x140003d49  jz      short loc_140003D5F
0x140003d4b  mov     r8d, 400h
0x140003d51  lea     rdx, [rbp+13F0h+var_1430]
0x140003d55  lea     rcx, [rsp+14F0h+var_14D0]
0x140003d5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d5f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003d66  test    rax, rax
0x140003d69  jz      short loc_140003D75
0x140003d6b  lea     rcx, [rsp+14F0h+var_14D0]
0x140003d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d75  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003d7c  test    rax, rax
0x140003d7f  jz      short loc_140003D92
0x140003d81  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140003d86  jnz     short loc_140003D92
0x140003d88  lea     rcx, [rsp+14F0h+var_14D0]
0x140003d8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d92  cmp     [rsp+14F0h+var_14C8], r13d
0x140003d97  jl      short loc_140003DAB
0x140003d99  mov     ecx, 8000FFFFh; this
0x140003d9e  mov     [rsp+14F0h+var_14C8], ecx
0x140003da2  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140003da7  mov     [rsp+14F0h+var_14C4], eax
0x140003dab  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140003db2  jnz     short loc_140003DD3
0x140003db4  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140003dbb  test    rax, rax
0x140003dbe  jz      short loc_140003DC9
0x140003dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003dc5  test    al, al
0x140003dc7  jmp     short loc_140003DD1
0x140003dc9  call    cs:__imp_IsDebuggerPresent
0x140003dcf  test    eax, eax
0x140003dd1  jz      short loc_140003DDA
0x140003dd3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140003dd8  jz      short loc_140003E00
0x140003dda  mov     rax, cs:g_pfnResultLoggingCallback
0x140003de1  test    rax, rax
0x140003de4  jz      short loc_140003E59
0x140003de6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140003ded  jnz     short loc_140003E59
0x140003def  xor     r8d, r8d
0x140003df2  xor     edx, edx
0x140003df4  lea     rcx, [rsp+14F0h+var_14D0]
0x140003df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003dfe  jmp     short loc_140003E59
0x140003e00  mov     ebx, 800h
0x140003e05  mov     rax, cs:g_pfnResultLoggingCallback
0x140003e0c  test    rax, rax
0x140003e0f  jz      short loc_140003E2E
0x140003e11  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140003e18  jnz     short loc_140003E2E
0x140003e1a  mov     r8d, ebx
0x140003e1d  lea     rdx, [rbp+13F0h+OutputString]
0x140003e24  lea     rcx, [rsp+14F0h+var_14D0]
0x140003e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003e2e  cmp     [rbp+13F0h+OutputString], r13w
0x140003e36  jnz     short loc_140003E4C
0x140003e38  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140003e3d  mov     rdx, rbx; unsigned __int16 *
0x140003e40  lea     rcx, [rbp+13F0h+OutputString]; this
0x140003e47  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140003e4c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140003e53  call    cs:__imp_OutputDebugStringW
0x140003e59  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140003e5e  jnz     short loc_140003E69
0x140003e60  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140003e67  jz      short loc_140003E7B
0x140003e69  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003e70  test    rax, rax
0x140003e73  jz      short loc_140003E7B
0x140003e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003e7a  nop
0x140003e7b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140003e80  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
