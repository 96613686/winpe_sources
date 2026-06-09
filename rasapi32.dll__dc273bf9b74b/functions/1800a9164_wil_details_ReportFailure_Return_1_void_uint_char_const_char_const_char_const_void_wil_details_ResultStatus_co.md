# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800a9164`
- end: `0x1800a93f8`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800a8c6c`

## callees

- `0x1800a9164`
- `0x1800ab0e4`
- `0x1800acdb0`
- `0x1800ae630`
- `0x1800ae7ec`
- `0x1800ded06`
- `0x1800ded50`
- `0x1800dee10`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a920e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a920e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800a9309`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800a9309`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800a9393`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800a9393`

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
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v18 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  v19 = 1;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v20 = v13;
  v24 = 0;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v25 = CurrentThreadId;
  v30 = v12;
  v28 = "wil";
  v35 = 0;
  v33 = 0;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x1800a9164  mov     [rsp-8+arg_10], rbx
0x1800a9169  push    rbp
0x1800a916a  push    rsi
0x1800a916b  push    rdi
0x1800a916c  push    r14
0x1800a916e  push    r15
0x1800a9170  lea     rbp, [rsp-13D0h]
0x1800a9178  mov     eax, 14D0h
0x1800a917d  call    _alloca_probe
0x1800a9182  sub     rsp, rax
0x1800a9185  mov     rax, cs:__security_cookie
0x1800a918c  xor     rax, rsp
0x1800a918f  mov     [rbp+13F0h+var_30], rax
0x1800a9196  mov     rdi, [rbp+13F0h+arg_28]
0x1800a919d  mov     esi, edx
0x1800a919f  mov     r14, rcx
0x1800a91a2  xor     edx, edx; Val
0x1800a91a4  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800a91a9  mov     r8d, 98h; Size
0x1800a91af  call    memset_0
0x1800a91b4  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800a91bb  xor     r15d, r15d
0x1800a91be  mov     [rbp+13F0h+OutputString], r15w
0x1800a91c6  mov     [rbp+13F0h+var_1430], r15b
0x1800a91ca  mov     ecx, [rdx]; this
0x1800a91cc  mov     eax, [rdx+4]
0x1800a91cf  mov     [rsp+14F0h+var_14C8], ecx
0x1800a91d3  mov     [rsp+14F0h+var_14C4], eax
0x1800a91d7  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800a91dc  cmp     dword ptr [rdx+8], 1
0x1800a91e0  mov     ebx, eax
0x1800a91e2  lea     eax, [r15+8]
0x1800a91e6  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800a91ee  mov     ecx, r15d
0x1800a91f1  cmovz   ecx, eax
0x1800a91f4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800a91f8  lea     ecx, [rax-7]
0x1800a91fb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800a9203  inc     ecx
0x1800a9205  mov     [rsp+14F0h+var_14B8], r15
0x1800a920a  mov     [rsp+14F0h+var_14C0], ecx
0x1800a920e  call    cs:__imp_GetCurrentThreadId
0x1800a9214  xorps   xmm0, xmm0
0x1800a9217  mov     [rsp+14F0h+var_1490], esi
0x1800a921b  mov     [rsp+14F0h+var_14B0], eax
0x1800a921f  xorps   xmm1, xmm1
0x1800a9222  lea     rax, aWil; "wil"
0x1800a9229  mov     [rsp+14F0h+var_148C], ebx
0x1800a922d  mov     [rsp+14F0h+var_1498], rax
0x1800a9232  xor     eax, eax
0x1800a9234  mov     [rbp+13F0h+var_1458], rax
0x1800a9238  mov     [rbp+13F0h+var_1470], rax
0x1800a923c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800a9243  mov     [rsp+14F0h+var_14A8], r15
0x1800a9248  mov     [rsp+14F0h+var_14A0], r15
0x1800a924d  mov     [rbp+13F0h+var_1448], rdi
0x1800a9251  mov     [rbp+13F0h+var_1440], r14
0x1800a9255  mov     [rsp+14F0h+var_1488], r15
0x1800a925a  movups  [rbp+13F0h+var_1468], xmm0
0x1800a925e  movups  [rsp+14F0h+var_1480], xmm1
0x1800a9263  test    rax, rax
0x1800a9266  jz      short loc_1800A9273
0x1800a9268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a926d  mov     [rbp+13F0h+var_1450], rax
0x1800a9271  jmp     short loc_1800A9277
0x1800a9273  mov     [rbp+13F0h+var_1450], r15
0x1800a9277  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800a927e  test    rax, rax
0x1800a9281  jz      short loc_1800A928D
0x1800a9283  lea     rcx, [rsp+14F0h+var_14D0]
0x1800a9288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a928d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800a9294  test    rax, rax
0x1800a9297  jz      short loc_1800A92AD
0x1800a9299  mov     r8d, 400h
0x1800a929f  lea     rdx, [rbp+13F0h+var_1430]
0x1800a92a3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800a92a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a92ad  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800a92b4  test    rax, rax
0x1800a92b7  jz      short loc_1800A92C3
0x1800a92b9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800a92be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a92c3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800a92ca  test    rax, rax
0x1800a92cd  jz      short loc_1800A92E0
0x1800a92cf  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800a92d4  jnz     short loc_1800A92E0
0x1800a92d6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800a92db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a92e0  cmp     [rsp+14F0h+var_14C8], r15d
0x1800a92e5  jge     loc_1800A93E7
0x1800a92eb  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800a92f2  jnz     short loc_1800A9313
0x1800a92f4  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800a92fb  test    rax, rax
0x1800a92fe  jz      short loc_1800A9309
0x1800a9300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9305  test    al, al
0x1800a9307  jmp     short loc_1800A9311
0x1800a9309  call    cs:__imp_IsDebuggerPresent
0x1800a930f  test    eax, eax
0x1800a9311  jz      short loc_1800A931A
0x1800a9313  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800a9318  jz      short loc_1800A9340
0x1800a931a  mov     rax, cs:g_pfnResultLoggingCallback
0x1800a9321  test    rax, rax
0x1800a9324  jz      short loc_1800A9399
0x1800a9326  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800a932d  jnz     short loc_1800A9399
0x1800a932f  xor     r8d, r8d
0x1800a9332  lea     rcx, [rsp+14F0h+var_14D0]
0x1800a9337  xor     edx, edx
0x1800a9339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a933e  jmp     short loc_1800A9399
0x1800a9340  mov     rax, cs:g_pfnResultLoggingCallback
0x1800a9347  mov     ebx, 800h
0x1800a934c  test    rax, rax
0x1800a934f  jz      short loc_1800A936E
0x1800a9351  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800a9358  jnz     short loc_1800A936E
0x1800a935a  mov     r8d, ebx
0x1800a935d  lea     rdx, [rbp+13F0h+OutputString]
0x1800a9364  lea     rcx, [rsp+14F0h+var_14D0]
0x1800a9369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a936e  cmp     [rbp+13F0h+OutputString], r15w
0x1800a9376  jnz     short loc_1800A938C
0x1800a9378  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800a937d  mov     rdx, rbx; unsigned __int16 *
0x1800a9380  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800a9387  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800a938c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800a9393  call    cs:__imp_OutputDebugStringW
0x1800a9399  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800a939e  jnz     short loc_1800A93A9
0x1800a93a0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800a93a7  jz      short loc_1800A93BA
0x1800a93a9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800a93b0  test    rax, rax
0x1800a93b3  jz      short loc_1800A93BA
0x1800a93b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a93ba  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800a93bf  jnz     short loc_1800A93ED
0x1800a93c1  mov     rcx, [rbp+13F0h+var_30]
0x1800a93c8  xor     rcx, rsp; StackCookie
0x1800a93cb  call    __security_check_cookie
0x1800a93d0  mov     rbx, [rsp+14F0h+arg_10]
0x1800a93d8  add     rsp, 14D0h
0x1800a93df  pop     r15
0x1800a93e1  pop     r14
0x1800a93e3  pop     rdi
0x1800a93e4  pop     rsi
0x1800a93e5  pop     rbp
0x1800a93e6  retn
0x1800a93e7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800a93ed  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800a93f2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
