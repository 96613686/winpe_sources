# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800a8efc`
- end: `0x1800a915c`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800a8cc8`

## callees

- `0x1800a8efc`
- `0x1800ab0e4`
- `0x1800ab950`
- `0x1800acc10`
- `0x1800ae630`
- `0x1800ded06`
- `0x1800dee10`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a8f9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a8f9d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800a90a0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800a90a0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800a912a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800a912a`

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
0x1800a8efc  mov     [rsp-8+arg_18], rbx
0x1800a8f01  push    rbp
0x1800a8f02  push    rsi
0x1800a8f03  push    rdi
0x1800a8f04  push    r12
0x1800a8f06  push    r13
0x1800a8f08  push    r14
0x1800a8f0a  push    r15
0x1800a8f0c  lea     rbp, [rsp-13C0h]
0x1800a8f14  mov     eax, 14C0h
0x1800a8f19  call    _alloca_probe
0x1800a8f1e  sub     rsp, rax
0x1800a8f21  mov     rsi, [rbp+13F0h+arg_28]
0x1800a8f28  mov     r15, r8
0x1800a8f2b  mov     r14d, edx
0x1800a8f2e  mov     r12, rcx
0x1800a8f31  xor     edx, edx; Val
0x1800a8f33  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800a8f38  mov     r8d, 98h; Size
0x1800a8f3e  call    memset_0
0x1800a8f43  mov     rbx, [rbp+13F0h+arg_30]
0x1800a8f4a  xor     r13d, r13d
0x1800a8f4d  mov     [rbp+13F0h+OutputString], r13w
0x1800a8f55  mov     [rbp+13F0h+var_1430], r13b
0x1800a8f59  mov     ecx, [rbx]; this
0x1800a8f5b  mov     eax, [rbx+4]
0x1800a8f5e  mov     [rsp+14F0h+var_14C8], ecx
0x1800a8f62  mov     [rsp+14F0h+var_14C4], eax
0x1800a8f66  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800a8f6b  cmp     dword ptr [rbx+8], 1
0x1800a8f6f  mov     edi, eax
0x1800a8f71  lea     eax, [r13+8]
0x1800a8f75  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800a8f7d  mov     ecx, r13d
0x1800a8f80  cmovz   ecx, eax
0x1800a8f83  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800a8f87  lea     ecx, [rax-7]
0x1800a8f8a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800a8f92  inc     ecx
0x1800a8f94  mov     [rsp+14F0h+var_14B8], r13
0x1800a8f99  mov     [rsp+14F0h+var_14C0], ecx
0x1800a8f9d  call    cs:__imp_GetCurrentThreadId
0x1800a8fa3  xorps   xmm0, xmm0
0x1800a8fa6  mov     [rsp+14F0h+var_1498], r15
0x1800a8fab  mov     [rsp+14F0h+var_14B0], eax
0x1800a8faf  xorps   xmm1, xmm1
0x1800a8fb2  xor     eax, eax
0x1800a8fb4  mov     [rsp+14F0h+var_1490], r14d
0x1800a8fb9  mov     [rbp+13F0h+var_1458], rax
0x1800a8fbd  mov     [rbp+13F0h+var_1470], rax
0x1800a8fc1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800a8fc8  mov     [rsp+14F0h+var_148C], edi
0x1800a8fcc  mov     [rsp+14F0h+var_14A8], r13
0x1800a8fd1  mov     [rsp+14F0h+var_14A0], r13
0x1800a8fd6  mov     [rbp+13F0h+var_1448], rsi
0x1800a8fda  mov     [rbp+13F0h+var_1440], r12
0x1800a8fde  mov     [rsp+14F0h+var_1488], r13
0x1800a8fe3  movups  [rbp+13F0h+var_1468], xmm0
0x1800a8fe7  movups  [rsp+14F0h+var_1480], xmm1
0x1800a8fec  test    rax, rax
0x1800a8fef  jz      short loc_1800A8FFC
0x1800a8ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8ff6  mov     [rbp+13F0h+var_1450], rax
0x1800a8ffa  jmp     short loc_1800A9000
0x1800a8ffc  mov     [rbp+13F0h+var_1450], r13
0x1800a9000  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800a9007  test    rax, rax
0x1800a900a  jz      short loc_1800A9016
0x1800a900c  lea     rcx, [rsp+14F0h+var_14D0]
0x1800a9011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9016  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800a901d  test    rax, rax
0x1800a9020  jz      short loc_1800A9036
0x1800a9022  mov     r8d, 400h
0x1800a9028  lea     rdx, [rbp+13F0h+var_1430]
0x1800a902c  lea     rcx, [rsp+14F0h+var_14D0]
0x1800a9031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9036  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800a903d  test    rax, rax
0x1800a9040  jz      short loc_1800A904C
0x1800a9042  lea     rcx, [rsp+14F0h+var_14D0]
0x1800a9047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a904c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800a9053  test    rax, rax
0x1800a9056  jz      short loc_1800A9069
0x1800a9058  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800a905d  jnz     short loc_1800A9069
0x1800a905f  lea     rcx, [rsp+14F0h+var_14D0]
0x1800a9064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9069  cmp     [rsp+14F0h+var_14C8], r13d
0x1800a906e  jl      short loc_1800A9082
0x1800a9070  mov     ecx, 8000FFFFh; this
0x1800a9075  mov     [rsp+14F0h+var_14C8], ecx
0x1800a9079  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800a907e  mov     [rsp+14F0h+var_14C4], eax
0x1800a9082  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800a9089  jnz     short loc_1800A90AA
0x1800a908b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800a9092  test    rax, rax
0x1800a9095  jz      short loc_1800A90A0
0x1800a9097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a909c  test    al, al
0x1800a909e  jmp     short loc_1800A90A8
0x1800a90a0  call    cs:__imp_IsDebuggerPresent
0x1800a90a6  test    eax, eax
0x1800a90a8  jz      short loc_1800A90B1
0x1800a90aa  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800a90af  jz      short loc_1800A90D7
0x1800a90b1  mov     rax, cs:g_pfnResultLoggingCallback
0x1800a90b8  test    rax, rax
0x1800a90bb  jz      short loc_1800A9130
0x1800a90bd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800a90c4  jnz     short loc_1800A9130
0x1800a90c6  xor     r8d, r8d
0x1800a90c9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800a90ce  xor     edx, edx
0x1800a90d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a90d5  jmp     short loc_1800A9130
0x1800a90d7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800a90de  mov     ebx, 800h
0x1800a90e3  test    rax, rax
0x1800a90e6  jz      short loc_1800A9105
0x1800a90e8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800a90ef  jnz     short loc_1800A9105
0x1800a90f1  mov     r8d, ebx
0x1800a90f4  lea     rdx, [rbp+13F0h+OutputString]
0x1800a90fb  lea     rcx, [rsp+14F0h+var_14D0]
0x1800a9100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9105  cmp     [rbp+13F0h+OutputString], r13w
0x1800a910d  jnz     short loc_1800A9123
0x1800a910f  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800a9114  mov     rdx, rbx; unsigned __int16 *
0x1800a9117  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800a911e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800a9123  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800a912a  call    cs:__imp_OutputDebugStringW
0x1800a9130  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800a9135  jnz     short loc_1800A9140
0x1800a9137  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800a913e  jz      short loc_1800A9151
0x1800a9140  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800a9147  test    rax, rax
0x1800a914a  jz      short loc_1800A9151
0x1800a914c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9151  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800a9156  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
