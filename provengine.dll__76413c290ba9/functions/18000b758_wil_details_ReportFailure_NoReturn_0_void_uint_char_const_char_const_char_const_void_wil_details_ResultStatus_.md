# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000b758`
- end: `0x18000ba04`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000b660`

## callees

- `0x180004494`
- `0x1800057d0`
- `0x18000965c`
- `0x18000a16c`
- `0x18000ad08`
- `0x18000b758`
- `0x18004371a`
- `0x180043810`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b801`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b801`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000b998`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000b998`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b8fc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b8fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v10; // r12
  int v11; // ebx
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  char v18; // bl
  const struct wil::FailureInfo *v19; // rdx
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
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

  v10 = g_pfnThrowPlatformException != 0;
  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v22 = *a7;
  v23 = a7[1];
  v11 = wil::details::RecordException((wil::details *)(unsigned int)v22, (int)a7);
  v20 = 0;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v21 = v12;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v25 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v30 = a2;
  v31 = v11;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && !v10 && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v18 = 1, (v21 & 2) != 0) )
  {
    v18 = 0;
  }
  if ( v10 || v18 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v16);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v14);
  if ( v10 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v20, OutputString);
  wil::ThrowResultException((wil *)&v20, v14);
  wil::details::WilFailFast((wil::details *)&v20, v19);
}

```

## disassembly

```asm
0x18000b758  mov     [rsp-8+arg_18], rbx
0x18000b75d  push    rbp
0x18000b75e  push    rsi
0x18000b75f  push    rdi
0x18000b760  push    r12
0x18000b762  push    r13
0x18000b764  push    r14
0x18000b766  push    r15
0x18000b768  lea     rbp, [rsp-13C0h]
0x18000b770  mov     eax, 14C0h
0x18000b775  call    _alloca_probe
0x18000b77a  sub     rsp, rax
0x18000b77d  mov     r14, r8
0x18000b780  mov     esi, edx
0x18000b782  mov     r15, rcx
0x18000b785  mov     rdi, [rbp+13F0h+arg_28]
0x18000b78c  xor     r13d, r13d
0x18000b78f  cmp     cs:g_pfnThrowPlatformException, r13
0x18000b796  setnz   r12b
0x18000b79a  xor     edx, edx; Val
0x18000b79c  mov     r8d, 98h; Size
0x18000b7a2  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000b7a7  call    memset_0
0x18000b7ac  nop
0x18000b7ad  mov     [rbp+13F0h+OutputString], r13w
0x18000b7b5  mov     [rbp+13F0h+var_1430], r13b
0x18000b7b9  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000b7c0  mov     ecx, [rdx]; this
0x18000b7c2  mov     [rsp+14F0h+var_14C8], ecx
0x18000b7c6  mov     eax, [rdx+4]
0x18000b7c9  mov     [rsp+14F0h+var_14C4], eax
0x18000b7cd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000b7d2  mov     ebx, eax
0x18000b7d4  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18000b7d9  mov     ecx, r13d
0x18000b7dc  lea     eax, [r13+8]
0x18000b7e0  cmp     dword ptr [rdx+8], 1
0x18000b7e4  cmovz   ecx, eax
0x18000b7e7  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000b7eb  lea     ecx, [rax-7]
0x18000b7ee  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000b7f6  inc     ecx
0x18000b7f8  mov     [rsp+14F0h+var_14C0], ecx
0x18000b7fc  mov     [rsp+14F0h+var_14B8], r13
0x18000b801  call    cs:__imp_GetCurrentThreadId
0x18000b807  mov     [rsp+14F0h+var_14B0], eax
0x18000b80b  mov     [rsp+14F0h+var_1498], r14
0x18000b810  mov     [rsp+14F0h+var_1490], esi
0x18000b814  mov     [rsp+14F0h+var_148C], ebx
0x18000b818  mov     [rsp+14F0h+var_14A8], r13
0x18000b81d  mov     [rsp+14F0h+var_14A0], r13
0x18000b822  mov     [rbp+13F0h+var_1448], rdi
0x18000b826  mov     [rbp+13F0h+var_1440], r15
0x18000b82a  mov     [rsp+14F0h+var_1488], r13
0x18000b82f  xorps   xmm0, xmm0
0x18000b832  xor     eax, eax
0x18000b834  movups  [rbp+13F0h+var_1468], xmm0
0x18000b838  mov     [rbp+13F0h+var_1458], rax
0x18000b83c  xorps   xmm1, xmm1
0x18000b83f  movups  [rsp+14F0h+var_1480], xmm1
0x18000b844  mov     [rbp+13F0h+var_1470], rax
0x18000b848  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000b84f  test    rax, rax
0x18000b852  jz      short loc_18000B85F
0x18000b854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b859  mov     [rbp+13F0h+var_1450], rax
0x18000b85d  jmp     short loc_18000B863
0x18000b85f  mov     [rbp+13F0h+var_1450], r13
0x18000b863  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000b86a  test    rax, rax
0x18000b86d  jz      short loc_18000B879
0x18000b86f  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b879  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000b880  test    rax, rax
0x18000b883  jz      short loc_18000B899
0x18000b885  mov     r8d, 400h
0x18000b88b  lea     rdx, [rbp+13F0h+var_1430]
0x18000b88f  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b899  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000b8a0  test    rax, rax
0x18000b8a3  jz      short loc_18000B8AF
0x18000b8a5  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b8aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8af  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000b8b6  test    rax, rax
0x18000b8b9  jz      short loc_18000B8D1
0x18000b8bb  test    r12b, r12b
0x18000b8be  jnz     short loc_18000B8D1
0x18000b8c0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000b8c5  jnz     short loc_18000B8D1
0x18000b8c7  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b8cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8d1  cmp     [rsp+14F0h+var_14C8], r13d
0x18000b8d6  jl      short loc_18000B8DE
0x18000b8d8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000b8de  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000b8e5  jnz     short loc_18000B906
0x18000b8e7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000b8ee  test    rax, rax
0x18000b8f1  jz      short loc_18000B8FC
0x18000b8f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8f8  test    al, al
0x18000b8fa  jmp     short loc_18000B904
0x18000b8fc  call    cs:__imp_IsDebuggerPresent
0x18000b902  test    eax, eax
0x18000b904  jz      short loc_18000B90F
0x18000b906  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000b90b  mov     bl, 1
0x18000b90d  jz      short loc_18000B912
0x18000b90f  mov     bl, r13b
0x18000b912  test    r12b, r12b
0x18000b915  jnz     short loc_18000B941
0x18000b917  test    bl, bl
0x18000b919  jnz     short loc_18000B941
0x18000b91b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b922  test    rax, rax
0x18000b925  jz      short loc_18000B99E
0x18000b927  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000b92e  jnz     short loc_18000B99E
0x18000b930  xor     r8d, r8d
0x18000b933  xor     edx, edx
0x18000b935  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b93a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b93f  jmp     short loc_18000B99E
0x18000b941  mov     edi, 800h
0x18000b946  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b94d  test    rax, rax
0x18000b950  jz      short loc_18000B96F
0x18000b952  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000b959  jnz     short loc_18000B96F
0x18000b95b  mov     r8d, edi
0x18000b95e  lea     rdx, [rbp+13F0h+OutputString]
0x18000b965  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b96a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b96f  cmp     [rbp+13F0h+OutputString], r13w
0x18000b977  jnz     short loc_18000B98D
0x18000b979  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000b97e  mov     rdx, rdi; unsigned __int16 *
0x18000b981  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000b988  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000b98d  test    bl, bl
0x18000b98f  jz      short loc_18000B99E
0x18000b991  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000b998  call    cs:__imp_OutputDebugStringW
0x18000b99e  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000b9a3  jnz     short loc_18000B9AE
0x18000b9a5  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000b9ac  jz      short loc_18000B9C0
0x18000b9ae  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000b9b5  test    rax, rax
0x18000b9b8  jz      short loc_18000B9C0
0x18000b9ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9bf  nop
0x18000b9c0  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000b9c5  jz      short loc_18000B9D2
0x18000b9c7  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000b9cc  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000b9d2  test    r12b, r12b
0x18000b9d5  jz      short loc_18000B9EF
0x18000b9d7  lea     rdx, [rbp+13F0h+OutputString]
0x18000b9de  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b9e3  mov     rax, cs:g_pfnThrowPlatformException
0x18000b9ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9ef  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000b9f4  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18000b9f9  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000b9fe  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
