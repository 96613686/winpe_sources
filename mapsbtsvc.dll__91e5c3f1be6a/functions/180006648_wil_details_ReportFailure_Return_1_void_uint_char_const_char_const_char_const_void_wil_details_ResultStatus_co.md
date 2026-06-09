# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180006648`
- end: `0x1800068de`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180006310`

## callees

- `0x180001e70`
- `0x1800028e8`
- `0x180006648`
- `0x180007404`
- `0x1800084b0`
- `0x1800090a8`
- `0x180009210`
- `0x180013980`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800066f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800066f3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006878`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006878`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800067ee`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800067ee`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x180006648  mov     [rsp-8+arg_10], rbx
0x18000664d  push    rbp
0x18000664e  push    rsi
0x18000664f  push    rdi
0x180006650  push    r14
0x180006652  push    r15
0x180006654  lea     rbp, [rsp-13D0h]
0x18000665c  mov     eax, 14D0h
0x180006661  call    _alloca_probe
0x180006666  sub     rsp, rax
0x180006669  mov     rax, cs:__security_cookie
0x180006670  xor     rax, rsp
0x180006673  mov     [rbp+13F0h+var_30], rax
0x18000667a  mov     esi, edx
0x18000667c  mov     r14, rcx
0x18000667f  mov     rdi, [rbp+13F0h+arg_28]
0x180006686  xor     edx, edx; Val
0x180006688  mov     r8d, 98h; Size
0x18000668e  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180006693  call    memset_0
0x180006698  nop
0x180006699  xor     r15d, r15d
0x18000669c  mov     [rbp+13F0h+OutputString], r15w
0x1800066a4  mov     [rbp+13F0h+var_1430], r15b
0x1800066a8  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800066af  mov     ecx, [rdx]; this
0x1800066b1  mov     [rsp+14F0h+var_14C8], ecx
0x1800066b5  mov     eax, [rdx+4]
0x1800066b8  mov     [rsp+14F0h+var_14C4], eax
0x1800066bc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800066c1  mov     ebx, eax
0x1800066c3  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800066cb  mov     ecx, r15d
0x1800066ce  lea     eax, [r15+8]
0x1800066d2  cmp     dword ptr [rdx+8], 1
0x1800066d6  cmovz   ecx, eax
0x1800066d9  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800066dd  lea     ecx, [rax-7]
0x1800066e0  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800066e8  inc     ecx
0x1800066ea  mov     [rsp+14F0h+var_14C0], ecx
0x1800066ee  mov     [rsp+14F0h+var_14B8], r15
0x1800066f3  call    cs:__imp_GetCurrentThreadId
0x1800066f9  mov     [rsp+14F0h+var_14B0], eax
0x1800066fd  lea     rax, aWil; "wil"
0x180006704  mov     [rsp+14F0h+var_1498], rax
0x180006709  mov     [rsp+14F0h+var_1490], esi
0x18000670d  mov     [rsp+14F0h+var_148C], ebx
0x180006711  mov     [rsp+14F0h+var_14A8], r15
0x180006716  mov     [rsp+14F0h+var_14A0], r15
0x18000671b  mov     [rbp+13F0h+var_1448], rdi
0x18000671f  mov     [rbp+13F0h+var_1440], r14
0x180006723  mov     [rsp+14F0h+var_1488], r15
0x180006728  xorps   xmm0, xmm0
0x18000672b  xor     eax, eax
0x18000672d  movups  [rbp+13F0h+var_1468], xmm0
0x180006731  mov     [rbp+13F0h+var_1458], rax
0x180006735  xorps   xmm1, xmm1
0x180006738  movups  [rsp+14F0h+var_1480], xmm1
0x18000673d  mov     [rbp+13F0h+var_1470], rax
0x180006741  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006748  test    rax, rax
0x18000674b  jz      short loc_180006758
0x18000674d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006752  mov     [rbp+13F0h+var_1450], rax
0x180006756  jmp     short loc_18000675C
0x180006758  mov     [rbp+13F0h+var_1450], r15
0x18000675c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006763  test    rax, rax
0x180006766  jz      short loc_180006772
0x180006768  lea     rcx, [rsp+14F0h+var_14D0]
0x18000676d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006772  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006779  test    rax, rax
0x18000677c  jz      short loc_180006792
0x18000677e  mov     r8d, 400h
0x180006784  lea     rdx, [rbp+13F0h+var_1430]
0x180006788  lea     rcx, [rsp+14F0h+var_14D0]
0x18000678d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006792  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006799  test    rax, rax
0x18000679c  jz      short loc_1800067A8
0x18000679e  lea     rcx, [rsp+14F0h+var_14D0]
0x1800067a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067a8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800067af  test    rax, rax
0x1800067b2  jz      short loc_1800067C5
0x1800067b4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800067b9  jnz     short loc_1800067C5
0x1800067bb  lea     rcx, [rsp+14F0h+var_14D0]
0x1800067c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067c5  cmp     [rsp+14F0h+var_14C8], r15d
0x1800067ca  jge     loc_1800068D8
0x1800067d0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800067d7  jnz     short loc_1800067F8
0x1800067d9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800067e0  test    rax, rax
0x1800067e3  jz      short loc_1800067EE
0x1800067e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067ea  test    al, al
0x1800067ec  jmp     short loc_1800067F6
0x1800067ee  call    cs:__imp_IsDebuggerPresent
0x1800067f4  test    eax, eax
0x1800067f6  jz      short loc_1800067FF
0x1800067f8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800067fd  jz      short loc_180006825
0x1800067ff  mov     rax, cs:g_pfnResultLoggingCallback
0x180006806  test    rax, rax
0x180006809  jz      short loc_18000687E
0x18000680b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006812  jnz     short loc_18000687E
0x180006814  xor     r8d, r8d
0x180006817  xor     edx, edx
0x180006819  lea     rcx, [rsp+14F0h+var_14D0]
0x18000681e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006823  jmp     short loc_18000687E
0x180006825  mov     ebx, 800h
0x18000682a  mov     rax, cs:g_pfnResultLoggingCallback
0x180006831  test    rax, rax
0x180006834  jz      short loc_180006853
0x180006836  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000683d  jnz     short loc_180006853
0x18000683f  mov     r8d, ebx
0x180006842  lea     rdx, [rbp+13F0h+OutputString]
0x180006849  lea     rcx, [rsp+14F0h+var_14D0]
0x18000684e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006853  cmp     [rbp+13F0h+OutputString], r15w
0x18000685b  jnz     short loc_180006871
0x18000685d  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180006862  mov     rdx, rbx; unsigned __int16 *
0x180006865  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000686c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006871  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180006878  call    cs:__imp_OutputDebugStringW
0x18000687e  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180006883  jnz     short loc_18000688E
0x180006885  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000688c  jz      short loc_1800068A0
0x18000688e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006895  test    rax, rax
0x180006898  jz      short loc_1800068A0
0x18000689a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000689f  nop
0x1800068a0  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800068a5  jnz     short loc_1800068CD
0x1800068a7  mov     rcx, [rbp+13F0h+var_30]
0x1800068ae  xor     rcx, rsp; StackCookie
0x1800068b1  call    __security_check_cookie
0x1800068b6  mov     rbx, [rsp+14F0h+arg_10]
0x1800068be  add     rsp, 14D0h
0x1800068c5  pop     r15
0x1800068c7  pop     r14
0x1800068c9  pop     rdi
0x1800068ca  pop     rsi
0x1800068cb  pop     rbp
0x1800068cc  retn
0x1800068cd  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800068d2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800068d8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
