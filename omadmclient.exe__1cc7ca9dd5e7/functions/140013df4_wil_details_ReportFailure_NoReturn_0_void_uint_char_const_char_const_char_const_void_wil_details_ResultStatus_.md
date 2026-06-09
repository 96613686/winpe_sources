# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140013df4`
- end: `0x1400140b2`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `702`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140013d6c`

## callees

- `0x140003eb4`
- `0x14000866c`
- `0x140009ed4`
- `0x14000c46c`
- `0x14000cbdc`
- `0x14000ce6c`
- `0x140013df4`
- `0x140065e80`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140013e9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140013e9d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140013f9e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140013f9e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140014040`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140014040`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
      g_pfnResultLoggingCallback(&v20, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v20, v16);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0, v16);
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
0x140013df4  mov     [rsp-8+arg_18], rbx
0x140013df9  push    rbp
0x140013dfa  push    rsi
0x140013dfb  push    rdi
0x140013dfc  push    r12
0x140013dfe  push    r13
0x140013e00  push    r14
0x140013e02  push    r15
0x140013e04  lea     rbp, [rsp-13C0h]
0x140013e0c  mov     eax, 14C0h
0x140013e11  call    _alloca_probe
0x140013e16  sub     rsp, rax
0x140013e19  mov     r14, r8
0x140013e1c  mov     esi, edx
0x140013e1e  mov     r15, rcx
0x140013e21  mov     rdi, [rbp+13F0h+arg_28]
0x140013e28  xor     r13d, r13d
0x140013e2b  cmp     cs:g_pfnThrowPlatformException, r13
0x140013e32  setnz   r12b
0x140013e36  xor     edx, edx; Val
0x140013e38  mov     r8d, 98h; Size
0x140013e3e  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140013e43  call    memset_0
0x140013e48  nop
0x140013e49  mov     [rbp+13F0h+OutputString], r13w
0x140013e51  mov     [rbp+13F0h+var_1430], r13b
0x140013e55  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x140013e5c  mov     ecx, [rdx]; this
0x140013e5e  mov     [rsp+14F0h+var_14C8], ecx
0x140013e62  mov     eax, [rdx+4]
0x140013e65  mov     [rsp+14F0h+var_14C4], eax
0x140013e69  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140013e6e  mov     ebx, eax
0x140013e70  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x140013e75  mov     ecx, r13d
0x140013e78  lea     eax, [r13+8]
0x140013e7c  cmp     dword ptr [rdx+8], 1
0x140013e80  cmovz   ecx, eax
0x140013e83  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140013e87  lea     ecx, [rax-7]
0x140013e8a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140013e92  inc     ecx
0x140013e94  mov     [rsp+14F0h+var_14C0], ecx
0x140013e98  mov     [rsp+14F0h+var_14B8], r13
0x140013e9d  call    cs:__imp_GetCurrentThreadId
0x140013ea4  nop     dword ptr [rax+rax+00h]
0x140013ea9  mov     [rsp+14F0h+var_14B0], eax
0x140013ead  mov     [rsp+14F0h+var_1498], r14
0x140013eb2  mov     [rsp+14F0h+var_1490], esi
0x140013eb6  mov     [rsp+14F0h+var_148C], ebx
0x140013eba  mov     [rsp+14F0h+var_14A8], r13
0x140013ebf  mov     [rsp+14F0h+var_14A0], r13
0x140013ec4  mov     [rbp+13F0h+var_1448], rdi
0x140013ec8  mov     [rbp+13F0h+var_1440], r15
0x140013ecc  mov     [rsp+14F0h+var_1488], r13
0x140013ed1  xorps   xmm0, xmm0
0x140013ed4  xor     eax, eax
0x140013ed6  movups  [rbp+13F0h+var_1468], xmm0
0x140013eda  mov     [rbp+13F0h+var_1458], rax
0x140013ede  xorps   xmm1, xmm1
0x140013ee1  movups  [rsp+14F0h+var_1480], xmm1
0x140013ee6  mov     [rbp+13F0h+var_1470], rax
0x140013eea  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140013ef1  test    rax, rax
0x140013ef4  jz      short loc_140013F01
0x140013ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013efb  mov     [rbp+13F0h+var_1450], rax
0x140013eff  jmp     short loc_140013F05
0x140013f01  mov     [rbp+13F0h+var_1450], r13
0x140013f05  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140013f0c  test    rax, rax
0x140013f0f  jz      short loc_140013F1B
0x140013f11  lea     rcx, [rsp+14F0h+var_14D0]
0x140013f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013f1b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140013f22  test    rax, rax
0x140013f25  jz      short loc_140013F3B
0x140013f27  mov     r8d, 400h
0x140013f2d  lea     rdx, [rbp+13F0h+var_1430]
0x140013f31  lea     rcx, [rsp+14F0h+var_14D0]
0x140013f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013f3b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140013f42  test    rax, rax
0x140013f45  jz      short loc_140013F51
0x140013f47  lea     rcx, [rsp+14F0h+var_14D0]
0x140013f4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013f51  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140013f58  test    rax, rax
0x140013f5b  jz      short loc_140013F73
0x140013f5d  test    r12b, r12b
0x140013f60  jnz     short loc_140013F73
0x140013f62  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140013f67  jnz     short loc_140013F73
0x140013f69  lea     rcx, [rsp+14F0h+var_14D0]
0x140013f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013f73  cmp     [rsp+14F0h+var_14C8], r13d
0x140013f78  jl      short loc_140013F80
0x140013f7a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140013f80  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140013f87  jnz     short loc_140013FAE
0x140013f89  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140013f90  test    rax, rax
0x140013f93  jz      short loc_140013F9E
0x140013f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013f9a  test    al, al
0x140013f9c  jmp     short loc_140013FAC
0x140013f9e  call    cs:__imp_IsDebuggerPresent
0x140013fa5  nop     dword ptr [rax+rax+00h]
0x140013faa  test    eax, eax
0x140013fac  jz      short loc_140013FB7
0x140013fae  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140013fb3  mov     bl, 1
0x140013fb5  jz      short loc_140013FBA
0x140013fb7  mov     bl, r13b
0x140013fba  test    r12b, r12b
0x140013fbd  jnz     short loc_140013FE9
0x140013fbf  test    bl, bl
0x140013fc1  jnz     short loc_140013FE9
0x140013fc3  mov     rax, cs:g_pfnResultLoggingCallback
0x140013fca  test    rax, rax
0x140013fcd  jz      short loc_14001404C
0x140013fcf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140013fd6  jnz     short loc_14001404C
0x140013fd8  xor     r8d, r8d
0x140013fdb  xor     edx, edx
0x140013fdd  lea     rcx, [rsp+14F0h+var_14D0]
0x140013fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013fe7  jmp     short loc_14001404C
0x140013fe9  mov     edi, 800h
0x140013fee  mov     rax, cs:g_pfnResultLoggingCallback
0x140013ff5  test    rax, rax
0x140013ff8  jz      short loc_140014017
0x140013ffa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140014001  jnz     short loc_140014017
0x140014003  mov     r8d, edi
0x140014006  lea     rdx, [rbp+13F0h+OutputString]
0x14001400d  lea     rcx, [rsp+14F0h+var_14D0]
0x140014012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014017  cmp     [rbp+13F0h+OutputString], r13w
0x14001401f  jnz     short loc_140014035
0x140014021  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140014026  mov     rdx, rdi; unsigned __int16 *
0x140014029  lea     rcx, [rbp+13F0h+OutputString]; this
0x140014030  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140014035  test    bl, bl
0x140014037  jz      short loc_14001404C
0x140014039  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140014040  call    cs:__imp_OutputDebugStringW
0x140014047  nop     dword ptr [rax+rax+00h]
0x14001404c  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140014051  jnz     short loc_14001405C
0x140014053  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x14001405a  jz      short loc_14001406E
0x14001405c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140014063  test    rax, rax
0x140014066  jz      short loc_14001406E
0x140014068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001406d  nop
0x14001406e  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140014073  jz      short loc_140014080
0x140014075  lea     rcx, [rsp+14F0h+var_14D0]; this
0x14001407a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140014080  test    r12b, r12b
0x140014083  jz      short loc_14001409D
0x140014085  lea     rdx, [rbp+13F0h+OutputString]
0x14001408c  lea     rcx, [rsp+14F0h+var_14D0]
0x140014091  mov     rax, cs:g_pfnThrowPlatformException
0x140014098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001409d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1400140a2  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x1400140a7  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1400140ac  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
