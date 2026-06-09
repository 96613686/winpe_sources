# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140002b6c`
- end: `0x140002de0`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `628`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140002908`

## callees

- `0x140002463`
- `0x140002b6c`
- `0x140004f04`
- `0x140005710`
- `0x140006750`
- `0x140008d5c`
- `0x14004ae40`
- `0x14004d010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140002d17`
- `KERNEL32!IsDebuggerPresent` at `0x140002d17`
- `KERNEL32!OutputDebugStringW` at `0x140002da7`
- `KERNEL32!OutputDebugStringW` at `0x140002da7`
- `KERNEL32!GetCurrentThreadId` at `0x140002c0e`
- `KERNEL32!GetCurrentThreadId` at `0x140002c0e`

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
0x140002b6c  mov     [rsp-8+arg_18], rbx
0x140002b71  push    rbp
0x140002b72  push    rsi
0x140002b73  push    rdi
0x140002b74  push    r12
0x140002b76  push    r13
0x140002b78  push    r14
0x140002b7a  push    r15
0x140002b7c  lea     rbp, [rsp-13C0h]
0x140002b84  mov     eax, 14C0h
0x140002b89  call    _alloca_probe
0x140002b8e  sub     rsp, rax
0x140002b91  mov     r15, r8
0x140002b94  mov     r14d, edx
0x140002b97  mov     r12, rcx
0x140002b9a  mov     rsi, [rbp+13F0h+arg_28]
0x140002ba1  xor     edx, edx; Val
0x140002ba3  mov     r8d, 98h; Size
0x140002ba9  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140002bae  call    memset_0
0x140002bb3  nop
0x140002bb4  xor     r13d, r13d
0x140002bb7  mov     [rbp+13F0h+OutputString], r13w
0x140002bbf  mov     [rbp+13F0h+var_1430], r13b
0x140002bc3  mov     rbx, [rbp+13F0h+arg_30]
0x140002bca  mov     ecx, [rbx]; this
0x140002bcc  mov     [rsp+14F0h+var_14C8], ecx
0x140002bd0  mov     eax, [rbx+4]
0x140002bd3  mov     [rsp+14F0h+var_14C4], eax
0x140002bd7  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140002bdc  mov     edi, eax
0x140002bde  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x140002be6  mov     ecx, r13d
0x140002be9  lea     eax, [r13+8]
0x140002bed  cmp     dword ptr [rbx+8], 1
0x140002bf1  cmovz   ecx, eax
0x140002bf4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140002bf8  lea     ecx, [rax-7]
0x140002bfb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002c03  inc     ecx
0x140002c05  mov     [rsp+14F0h+var_14C0], ecx
0x140002c09  mov     [rsp+14F0h+var_14B8], r13
0x140002c0e  call    cs:__imp_GetCurrentThreadId
0x140002c15  nop     dword ptr [rax+rax+00h]
0x140002c1a  mov     [rsp+14F0h+var_14B0], eax
0x140002c1e  mov     [rsp+14F0h+var_1498], r15
0x140002c23  mov     [rsp+14F0h+var_1490], r14d
0x140002c28  mov     [rsp+14F0h+var_148C], edi
0x140002c2c  mov     [rsp+14F0h+var_14A8], r13
0x140002c31  mov     [rsp+14F0h+var_14A0], r13
0x140002c36  mov     [rbp+13F0h+var_1448], rsi
0x140002c3a  mov     [rbp+13F0h+var_1440], r12
0x140002c3e  mov     [rsp+14F0h+var_1488], r13
0x140002c43  xorps   xmm0, xmm0
0x140002c46  xor     eax, eax
0x140002c48  movups  [rbp+13F0h+var_1468], xmm0
0x140002c4c  mov     [rbp+13F0h+var_1458], rax
0x140002c50  xorps   xmm1, xmm1
0x140002c53  movups  [rsp+14F0h+var_1480], xmm1
0x140002c58  mov     [rbp+13F0h+var_1470], rax
0x140002c5c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002c63  test    rax, rax
0x140002c66  jz      short loc_140002C73
0x140002c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c6d  mov     [rbp+13F0h+var_1450], rax
0x140002c71  jmp     short loc_140002C77
0x140002c73  mov     [rbp+13F0h+var_1450], r13
0x140002c77  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002c7e  test    rax, rax
0x140002c81  jz      short loc_140002C8D
0x140002c83  lea     rcx, [rsp+14F0h+var_14D0]
0x140002c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c8d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002c94  test    rax, rax
0x140002c97  jz      short loc_140002CAD
0x140002c99  mov     r8d, 400h
0x140002c9f  lea     rdx, [rbp+13F0h+var_1430]
0x140002ca3  lea     rcx, [rsp+14F0h+var_14D0]
0x140002ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002cad  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002cb4  test    rax, rax
0x140002cb7  jz      short loc_140002CC3
0x140002cb9  lea     rcx, [rsp+14F0h+var_14D0]
0x140002cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002cc3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002cca  test    rax, rax
0x140002ccd  jz      short loc_140002CE0
0x140002ccf  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002cd4  jnz     short loc_140002CE0
0x140002cd6  lea     rcx, [rsp+14F0h+var_14D0]
0x140002cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002ce0  cmp     [rsp+14F0h+var_14C8], r13d
0x140002ce5  jl      short loc_140002CF9
0x140002ce7  mov     ecx, 8000FFFFh; this
0x140002cec  mov     [rsp+14F0h+var_14C8], ecx
0x140002cf0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140002cf5  mov     [rsp+14F0h+var_14C4], eax
0x140002cf9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140002d00  jnz     short loc_140002D27
0x140002d02  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002d09  test    rax, rax
0x140002d0c  jz      short loc_140002D17
0x140002d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d13  test    al, al
0x140002d15  jmp     short loc_140002D25
0x140002d17  call    cs:__imp_IsDebuggerPresent
0x140002d1e  nop     dword ptr [rax+rax+00h]
0x140002d23  test    eax, eax
0x140002d25  jz      short loc_140002D2E
0x140002d27  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002d2c  jz      short loc_140002D54
0x140002d2e  mov     rax, cs:g_pfnResultLoggingCallback
0x140002d35  test    rax, rax
0x140002d38  jz      short loc_140002DB3
0x140002d3a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140002d41  jnz     short loc_140002DB3
0x140002d43  xor     r8d, r8d
0x140002d46  xor     edx, edx
0x140002d48  lea     rcx, [rsp+14F0h+var_14D0]
0x140002d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d52  jmp     short loc_140002DB3
0x140002d54  mov     ebx, 800h
0x140002d59  mov     rax, cs:g_pfnResultLoggingCallback
0x140002d60  test    rax, rax
0x140002d63  jz      short loc_140002D82
0x140002d65  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140002d6c  jnz     short loc_140002D82
0x140002d6e  mov     r8d, ebx
0x140002d71  lea     rdx, [rbp+13F0h+OutputString]
0x140002d78  lea     rcx, [rsp+14F0h+var_14D0]
0x140002d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d82  cmp     [rbp+13F0h+OutputString], r13w
0x140002d8a  jnz     short loc_140002DA0
0x140002d8c  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140002d91  mov     rdx, rbx; unsigned __int16 *
0x140002d94  lea     rcx, [rbp+13F0h+OutputString]; this
0x140002d9b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140002da0  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140002da7  call    cs:__imp_OutputDebugStringW
0x140002dae  nop     dword ptr [rax+rax+00h]
0x140002db3  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140002db8  jnz     short loc_140002DC3
0x140002dba  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140002dc1  jz      short loc_140002DD5
0x140002dc3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002dca  test    rax, rax
0x140002dcd  jz      short loc_140002DD5
0x140002dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002dd4  nop
0x140002dd5  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140002dda  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
