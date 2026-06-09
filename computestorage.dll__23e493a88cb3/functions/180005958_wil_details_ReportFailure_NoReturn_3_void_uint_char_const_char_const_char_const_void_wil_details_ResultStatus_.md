# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180005958`
- end: `0x180005be3`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `651`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180005214`

## callees

- `0x1800032b8`
- `0x180005958`
- `0x18000b004`
- `0x18000b7f0`
- `0x18000dc90`
- `0x180012f2c`
- `0x180042f60`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a11`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005baa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005baa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005b1a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005b1a`

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
0x180005958  mov     [rsp-8+arg_18], rbx
0x18000595d  push    rbp
0x18000595e  push    rsi
0x18000595f  push    rdi
0x180005960  push    r12
0x180005962  push    r13
0x180005964  push    r14
0x180005966  push    r15
0x180005968  lea     rbp, [rsp-13C0h]
0x180005970  mov     eax, 14C0h
0x180005975  call    _alloca_probe
0x18000597a  sub     rsp, rax
0x18000597d  mov     r14, r8
0x180005980  mov     esi, edx
0x180005982  mov     rdi, rcx
0x180005985  mov     r15, [rbp+13F0h+arg_28]
0x18000598c  xor     edx, edx; Val
0x18000598e  mov     r8d, 98h; Size
0x180005994  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180005999  call    memset_0
0x18000599e  nop
0x18000599f  xor     r13d, r13d
0x1800059a2  mov     [rbp+13F0h+OutputString], r13w
0x1800059aa  mov     [rbp+13F0h+var_1430], r13b
0x1800059ae  mov     rbx, [rbp+13F0h+arg_30]
0x1800059b5  mov     ecx, [rbx]; this
0x1800059b7  mov     [rsp+14F0h+var_14C8], ecx
0x1800059bb  mov     eax, [rbx+4]
0x1800059be  mov     [rsp+14F0h+var_14C4], eax
0x1800059c2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800059c7  mov     r12d, eax
0x1800059ca  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800059d2  mov     ecx, r13d
0x1800059d5  lea     eax, [r13+8]
0x1800059d9  cmp     dword ptr [rbx+8], 1
0x1800059dd  cmovz   ecx, eax
0x1800059e0  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800059e4  lea     ecx, [rax-7]
0x1800059e7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800059ef  inc     ecx
0x1800059f1  mov     [rsp+14F0h+var_14C0], ecx
0x1800059f5  mov     rcx, [rbp+13F0h+arg_38]
0x1800059fc  test    rcx, rcx
0x1800059ff  jz      short loc_180005A0C
0x180005a01  cmp     [rcx], r13w
0x180005a05  mov     [rsp+14F0h+var_14B8], rcx
0x180005a0a  jnz     short loc_180005A11
0x180005a0c  mov     [rsp+14F0h+var_14B8], r13
0x180005a11  call    cs:__imp_GetCurrentThreadId
0x180005a18  nop     dword ptr [rax+rax+00h]
0x180005a1d  mov     [rsp+14F0h+var_14B0], eax
0x180005a21  mov     [rsp+14F0h+var_1498], r14
0x180005a26  mov     [rsp+14F0h+var_1490], esi
0x180005a2a  mov     [rsp+14F0h+var_148C], r12d
0x180005a2f  mov     [rsp+14F0h+var_14A8], r13
0x180005a34  mov     [rsp+14F0h+var_14A0], r13
0x180005a39  mov     [rbp+13F0h+var_1448], r15
0x180005a3d  mov     [rbp+13F0h+var_1440], rdi
0x180005a41  mov     [rsp+14F0h+var_1488], r13
0x180005a46  xorps   xmm0, xmm0
0x180005a49  xor     eax, eax
0x180005a4b  movups  [rbp+13F0h+var_1468], xmm0
0x180005a4f  mov     [rbp+13F0h+var_1458], rax
0x180005a53  xorps   xmm1, xmm1
0x180005a56  movups  [rsp+14F0h+var_1480], xmm1
0x180005a5b  mov     [rbp+13F0h+var_1470], rax
0x180005a5f  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005a66  test    rax, rax
0x180005a69  jz      short loc_180005A76
0x180005a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a70  mov     [rbp+13F0h+var_1450], rax
0x180005a74  jmp     short loc_180005A7A
0x180005a76  mov     [rbp+13F0h+var_1450], r13
0x180005a7a  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005a81  test    rax, rax
0x180005a84  jz      short loc_180005A90
0x180005a86  lea     rcx, [rsp+14F0h+var_14D0]
0x180005a8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a90  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005a97  test    rax, rax
0x180005a9a  jz      short loc_180005AB0
0x180005a9c  mov     r8d, 400h
0x180005aa2  lea     rdx, [rbp+13F0h+var_1430]
0x180005aa6  lea     rcx, [rsp+14F0h+var_14D0]
0x180005aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ab0  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005ab7  test    rax, rax
0x180005aba  jz      short loc_180005AC6
0x180005abc  lea     rcx, [rsp+14F0h+var_14D0]
0x180005ac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ac6  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005acd  test    rax, rax
0x180005ad0  jz      short loc_180005AE3
0x180005ad2  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005ad7  jnz     short loc_180005AE3
0x180005ad9  lea     rcx, [rsp+14F0h+var_14D0]
0x180005ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ae3  cmp     [rsp+14F0h+var_14C8], r13d
0x180005ae8  jl      short loc_180005AFC
0x180005aea  mov     ecx, 8000FFFFh; this
0x180005aef  mov     [rsp+14F0h+var_14C8], ecx
0x180005af3  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005af8  mov     [rsp+14F0h+var_14C4], eax
0x180005afc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180005b03  jnz     short loc_180005B2A
0x180005b05  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005b0c  test    rax, rax
0x180005b0f  jz      short loc_180005B1A
0x180005b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b16  test    al, al
0x180005b18  jmp     short loc_180005B28
0x180005b1a  call    cs:__imp_IsDebuggerPresent
0x180005b21  nop     dword ptr [rax+rax+00h]
0x180005b26  test    eax, eax
0x180005b28  jz      short loc_180005B31
0x180005b2a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005b2f  jz      short loc_180005B57
0x180005b31  mov     rax, cs:g_pfnResultLoggingCallback
0x180005b38  test    rax, rax
0x180005b3b  jz      short loc_180005BB6
0x180005b3d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180005b44  jnz     short loc_180005BB6
0x180005b46  xor     r8d, r8d
0x180005b49  xor     edx, edx
0x180005b4b  lea     rcx, [rsp+14F0h+var_14D0]
0x180005b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b55  jmp     short loc_180005BB6
0x180005b57  mov     ebx, 800h
0x180005b5c  mov     rax, cs:g_pfnResultLoggingCallback
0x180005b63  test    rax, rax
0x180005b66  jz      short loc_180005B85
0x180005b68  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180005b6f  jnz     short loc_180005B85
0x180005b71  mov     r8d, ebx
0x180005b74  lea     rdx, [rbp+13F0h+OutputString]
0x180005b7b  lea     rcx, [rsp+14F0h+var_14D0]
0x180005b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b85  cmp     [rbp+13F0h+OutputString], r13w
0x180005b8d  jnz     short loc_180005BA3
0x180005b8f  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180005b94  mov     rdx, rbx; unsigned __int16 *
0x180005b97  lea     rcx, [rbp+13F0h+OutputString]; this
0x180005b9e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005ba3  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180005baa  call    cs:__imp_OutputDebugStringW
0x180005bb1  nop     dword ptr [rax+rax+00h]
0x180005bb6  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180005bbb  jnz     short loc_180005BC6
0x180005bbd  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180005bc4  jz      short loc_180005BD8
0x180005bc6  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005bcd  test    rax, rax
0x180005bd0  jz      short loc_180005BD8
0x180005bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bd7  nop
0x180005bd8  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005bdd  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
