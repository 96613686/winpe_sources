# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180004edc`
- end: `0x18000513e`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180004ca8`

## callees

- `0x180004edc`
- `0x180006b34`
- `0x1800077e8`
- `0x180008f00`
- `0x18000aa30`
- `0x18002f0ba`
- `0x18002f1a0`
- `0x180031010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180005081`
- `KERNEL32!IsDebuggerPresent` at `0x180005081`
- `KERNEL32!OutputDebugStringW` at `0x18000510b`
- `KERNEL32!OutputDebugStringW` at `0x18000510b`
- `KERNEL32!GetCurrentThreadId` at `0x180004f7e`
- `KERNEL32!GetCurrentThreadId` at `0x180004f7e`

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
      wil::GetFailureLogString(OutputString, (wchar_t *)0x800, (__int64)&v17, v15);
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
0x180004edc  mov     [rsp-8+arg_18], rbx
0x180004ee1  push    rbp
0x180004ee2  push    rsi
0x180004ee3  push    rdi
0x180004ee4  push    r12
0x180004ee6  push    r13
0x180004ee8  push    r14
0x180004eea  push    r15
0x180004eec  lea     rbp, [rsp-13C0h]
0x180004ef4  mov     eax, 14C0h
0x180004ef9  call    _alloca_probe
0x180004efe  sub     rsp, rax
0x180004f01  mov     r15, r8
0x180004f04  mov     r14d, edx
0x180004f07  mov     r12, rcx
0x180004f0a  mov     rsi, [rbp+13F0h+arg_28]
0x180004f11  xor     edx, edx; Val
0x180004f13  mov     r8d, 98h; Size
0x180004f19  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180004f1e  call    memset_0
0x180004f23  nop
0x180004f24  xor     r13d, r13d
0x180004f27  mov     [rbp+13F0h+OutputString], r13w
0x180004f2f  mov     [rbp+13F0h+var_1430], r13b
0x180004f33  mov     rbx, [rbp+13F0h+arg_30]
0x180004f3a  mov     ecx, [rbx]; this
0x180004f3c  mov     [rsp+14F0h+var_14C8], ecx
0x180004f40  mov     eax, [rbx+4]
0x180004f43  mov     [rsp+14F0h+var_14C4], eax
0x180004f47  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004f4c  mov     edi, eax
0x180004f4e  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180004f56  mov     ecx, r13d
0x180004f59  lea     eax, [r13+8]
0x180004f5d  cmp     dword ptr [rbx+8], 1
0x180004f61  cmovz   ecx, eax
0x180004f64  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180004f68  lea     ecx, [rax-7]
0x180004f6b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004f73  inc     ecx
0x180004f75  mov     [rsp+14F0h+var_14C0], ecx
0x180004f79  mov     [rsp+14F0h+var_14B8], r13
0x180004f7e  call    cs:__imp_GetCurrentThreadId
0x180004f84  mov     [rsp+14F0h+var_14B0], eax
0x180004f88  mov     [rsp+14F0h+var_1498], r15
0x180004f8d  mov     [rsp+14F0h+var_1490], r14d
0x180004f92  mov     [rsp+14F0h+var_148C], edi
0x180004f96  mov     [rsp+14F0h+var_14A8], r13
0x180004f9b  mov     [rsp+14F0h+var_14A0], r13
0x180004fa0  mov     [rbp+13F0h+var_1448], rsi
0x180004fa4  mov     [rbp+13F0h+var_1440], r12
0x180004fa8  mov     [rsp+14F0h+var_1488], r13
0x180004fad  xorps   xmm0, xmm0
0x180004fb0  xor     eax, eax
0x180004fb2  movups  [rbp+13F0h+var_1468], xmm0
0x180004fb6  mov     [rbp+13F0h+var_1458], rax
0x180004fba  xorps   xmm1, xmm1
0x180004fbd  movups  [rsp+14F0h+var_1480], xmm1
0x180004fc2  mov     [rbp+13F0h+var_1470], rax
0x180004fc6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004fcd  test    rax, rax
0x180004fd0  jz      short loc_180004FDD
0x180004fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fd7  mov     [rbp+13F0h+var_1450], rax
0x180004fdb  jmp     short loc_180004FE1
0x180004fdd  mov     [rbp+13F0h+var_1450], r13
0x180004fe1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004fe8  test    rax, rax
0x180004feb  jz      short loc_180004FF7
0x180004fed  lea     rcx, [rsp+14F0h+var_14D0]
0x180004ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ff7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004ffe  test    rax, rax
0x180005001  jz      short loc_180005017
0x180005003  mov     r8d, 400h
0x180005009  lea     rdx, [rbp+13F0h+var_1430]
0x18000500d  lea     rcx, [rsp+14F0h+var_14D0]
0x180005012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005017  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000501e  test    rax, rax
0x180005021  jz      short loc_18000502D
0x180005023  lea     rcx, [rsp+14F0h+var_14D0]
0x180005028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000502d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005034  test    rax, rax
0x180005037  jz      short loc_18000504A
0x180005039  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000503e  jnz     short loc_18000504A
0x180005040  lea     rcx, [rsp+14F0h+var_14D0]
0x180005045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000504a  cmp     [rsp+14F0h+var_14C8], r13d
0x18000504f  jl      short loc_180005063
0x180005051  mov     ecx, 8000FFFFh; this
0x180005056  mov     [rsp+14F0h+var_14C8], ecx
0x18000505a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000505f  mov     [rsp+14F0h+var_14C4], eax
0x180005063  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000506a  jnz     short loc_18000508B
0x18000506c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005073  test    rax, rax
0x180005076  jz      short loc_180005081
0x180005078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000507d  test    al, al
0x18000507f  jmp     short loc_180005089
0x180005081  call    cs:__imp_IsDebuggerPresent
0x180005087  test    eax, eax
0x180005089  jz      short loc_180005092
0x18000508b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005090  jz      short loc_1800050B8
0x180005092  mov     rax, cs:g_pfnResultLoggingCallback
0x180005099  test    rax, rax
0x18000509c  jz      short loc_180005111
0x18000509e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800050a5  jnz     short loc_180005111
0x1800050a7  xor     r8d, r8d
0x1800050aa  xor     edx, edx
0x1800050ac  lea     rcx, [rsp+14F0h+var_14D0]
0x1800050b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050b6  jmp     short loc_180005111
0x1800050b8  mov     ebx, 800h
0x1800050bd  mov     rax, cs:g_pfnResultLoggingCallback
0x1800050c4  test    rax, rax
0x1800050c7  jz      short loc_1800050E6
0x1800050c9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800050d0  jnz     short loc_1800050E6
0x1800050d2  mov     r8d, ebx
0x1800050d5  lea     rdx, [rbp+13F0h+OutputString]
0x1800050dc  lea     rcx, [rsp+14F0h+var_14D0]
0x1800050e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050e6  cmp     [rbp+13F0h+OutputString], r13w
0x1800050ee  jnz     short loc_180005104
0x1800050f0  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800050f5  mov     rdx, rbx; wchar_t *
0x1800050f8  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800050ff  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180005104  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000510b  call    cs:__imp_OutputDebugStringW
0x180005111  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180005116  jnz     short loc_180005121
0x180005118  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000511f  jz      short loc_180005133
0x180005121  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005128  test    rax, rax
0x18000512b  jz      short loc_180005133
0x18000512d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005132  nop
0x180005133  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005138  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
