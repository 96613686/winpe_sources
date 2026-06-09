# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180025724`
- end: `0x1800259d0`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800253e8`

## callees

- `0x1800043a8`
- `0x180009204`
- `0x18000aa3c`
- `0x18000ca70`
- `0x18000d1c0`
- `0x18000d438`
- `0x180025724`
- `0x1800388e0`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800257cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800257cd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025964`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025964`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800258c8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800258c8`

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
0x180025724  mov     [rsp-8+arg_18], rbx
0x180025729  push    rbp
0x18002572a  push    rsi
0x18002572b  push    rdi
0x18002572c  push    r12
0x18002572e  push    r13
0x180025730  push    r14
0x180025732  push    r15
0x180025734  lea     rbp, [rsp-13C0h]
0x18002573c  mov     eax, 14C0h
0x180025741  call    _alloca_probe
0x180025746  sub     rsp, rax
0x180025749  mov     r14, r8
0x18002574c  mov     esi, edx
0x18002574e  mov     r15, rcx
0x180025751  mov     rdi, [rbp+13F0h+arg_28]
0x180025758  xor     r13d, r13d
0x18002575b  cmp     cs:g_pfnThrowPlatformException, r13
0x180025762  setnz   r12b
0x180025766  xor     edx, edx; Val
0x180025768  mov     r8d, 98h; Size
0x18002576e  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180025773  call    memset_0
0x180025778  nop
0x180025779  mov     [rbp+13F0h+OutputString], r13w
0x180025781  mov     [rbp+13F0h+var_1430], r13b
0x180025785  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18002578c  mov     ecx, [rdx]; this
0x18002578e  mov     [rsp+14F0h+var_14C8], ecx
0x180025792  mov     eax, [rdx+4]
0x180025795  mov     [rsp+14F0h+var_14C4], eax
0x180025799  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18002579e  mov     ebx, eax
0x1800257a0  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x1800257a5  mov     ecx, r13d
0x1800257a8  lea     eax, [r13+8]
0x1800257ac  cmp     dword ptr [rdx+8], 1
0x1800257b0  cmovz   ecx, eax
0x1800257b3  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800257b7  lea     ecx, [rax-7]
0x1800257ba  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800257c2  inc     ecx
0x1800257c4  mov     [rsp+14F0h+var_14C0], ecx
0x1800257c8  mov     [rsp+14F0h+var_14B8], r13
0x1800257cd  call    cs:__imp_GetCurrentThreadId
0x1800257d3  mov     [rsp+14F0h+var_14B0], eax
0x1800257d7  mov     [rsp+14F0h+var_1498], r14
0x1800257dc  mov     [rsp+14F0h+var_1490], esi
0x1800257e0  mov     [rsp+14F0h+var_148C], ebx
0x1800257e4  mov     [rsp+14F0h+var_14A8], r13
0x1800257e9  mov     [rsp+14F0h+var_14A0], r13
0x1800257ee  mov     [rbp+13F0h+var_1448], rdi
0x1800257f2  mov     [rbp+13F0h+var_1440], r15
0x1800257f6  mov     [rsp+14F0h+var_1488], r13
0x1800257fb  xorps   xmm0, xmm0
0x1800257fe  xor     eax, eax
0x180025800  movups  [rbp+13F0h+var_1468], xmm0
0x180025804  mov     [rbp+13F0h+var_1458], rax
0x180025808  xorps   xmm1, xmm1
0x18002580b  movups  [rsp+14F0h+var_1480], xmm1
0x180025810  mov     [rbp+13F0h+var_1470], rax
0x180025814  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002581b  test    rax, rax
0x18002581e  jz      short loc_18002582B
0x180025820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025825  mov     [rbp+13F0h+var_1450], rax
0x180025829  jmp     short loc_18002582F
0x18002582b  mov     [rbp+13F0h+var_1450], r13
0x18002582f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180025836  test    rax, rax
0x180025839  jz      short loc_180025845
0x18002583b  lea     rcx, [rsp+14F0h+var_14D0]
0x180025840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025845  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002584c  test    rax, rax
0x18002584f  jz      short loc_180025865
0x180025851  mov     r8d, 400h
0x180025857  lea     rdx, [rbp+13F0h+var_1430]
0x18002585b  lea     rcx, [rsp+14F0h+var_14D0]
0x180025860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025865  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002586c  test    rax, rax
0x18002586f  jz      short loc_18002587B
0x180025871  lea     rcx, [rsp+14F0h+var_14D0]
0x180025876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002587b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180025882  test    rax, rax
0x180025885  jz      short loc_18002589D
0x180025887  test    r12b, r12b
0x18002588a  jnz     short loc_18002589D
0x18002588c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180025891  jnz     short loc_18002589D
0x180025893  lea     rcx, [rsp+14F0h+var_14D0]
0x180025898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002589d  cmp     [rsp+14F0h+var_14C8], r13d
0x1800258a2  jl      short loc_1800258AA
0x1800258a4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800258aa  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800258b1  jnz     short loc_1800258D2
0x1800258b3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800258ba  test    rax, rax
0x1800258bd  jz      short loc_1800258C8
0x1800258bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258c4  test    al, al
0x1800258c6  jmp     short loc_1800258D0
0x1800258c8  call    cs:__imp_IsDebuggerPresent
0x1800258ce  test    eax, eax
0x1800258d0  jz      short loc_1800258DB
0x1800258d2  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800258d7  mov     bl, 1
0x1800258d9  jz      short loc_1800258DE
0x1800258db  mov     bl, r13b
0x1800258de  test    r12b, r12b
0x1800258e1  jnz     short loc_18002590D
0x1800258e3  test    bl, bl
0x1800258e5  jnz     short loc_18002590D
0x1800258e7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800258ee  test    rax, rax
0x1800258f1  jz      short loc_18002596A
0x1800258f3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800258fa  jnz     short loc_18002596A
0x1800258fc  xor     r8d, r8d
0x1800258ff  xor     edx, edx
0x180025901  lea     rcx, [rsp+14F0h+var_14D0]
0x180025906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002590b  jmp     short loc_18002596A
0x18002590d  mov     edi, 800h
0x180025912  mov     rax, cs:g_pfnResultLoggingCallback
0x180025919  test    rax, rax
0x18002591c  jz      short loc_18002593B
0x18002591e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180025925  jnz     short loc_18002593B
0x180025927  mov     r8d, edi
0x18002592a  lea     rdx, [rbp+13F0h+OutputString]
0x180025931  lea     rcx, [rsp+14F0h+var_14D0]
0x180025936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002593b  cmp     [rbp+13F0h+OutputString], r13w
0x180025943  jnz     short loc_180025959
0x180025945  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18002594a  mov     rdx, rdi; unsigned __int16 *
0x18002594d  lea     rcx, [rbp+13F0h+OutputString]; this
0x180025954  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180025959  test    bl, bl
0x18002595b  jz      short loc_18002596A
0x18002595d  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180025964  call    cs:__imp_OutputDebugStringW
0x18002596a  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18002596f  jnz     short loc_18002597A
0x180025971  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180025978  jz      short loc_18002598C
0x18002597a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180025981  test    rax, rax
0x180025984  jz      short loc_18002598C
0x180025986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002598b  nop
0x18002598c  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180025991  jz      short loc_18002599E
0x180025993  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180025998  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18002599e  test    r12b, r12b
0x1800259a1  jz      short loc_1800259BB
0x1800259a3  lea     rdx, [rbp+13F0h+OutputString]
0x1800259aa  lea     rcx, [rsp+14F0h+var_14D0]
0x1800259af  mov     rax, cs:g_pfnThrowPlatformException
0x1800259b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259bb  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800259c0  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x1800259c5  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800259ca  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
