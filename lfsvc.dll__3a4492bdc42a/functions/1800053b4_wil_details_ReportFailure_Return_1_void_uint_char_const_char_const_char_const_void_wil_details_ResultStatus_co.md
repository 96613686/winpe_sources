# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800053b4`
- end: `0x180005669`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `693`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003bb4`

## callees

- `0x180004310`
- `0x180004d48`
- `0x1800053b4`
- `0x180006d54`
- `0x180008590`
- `0x180009c58`
- `0x180009e10`
- `0x18000b360`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005470`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005470`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000556c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000556c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800055d9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800055d9`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7)
{
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag5 *v14; // rcx
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
  const char *v26; // [rsp+58h] [rbp-A8h]
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v19, (int)a7);
  v17 = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v18 = v11;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = "wil";
  v27 = a2;
  v28 = v10;
  v24 = a5;
  v25 = a4;
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
    wil::details::in1diag5::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || !wil::g_fResultOutputDebugString
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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( ((v18 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v18 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x1800053b4  mov     [rsp-8+arg_10], rbx
0x1800053b9  push    rbp
0x1800053ba  push    rsi
0x1800053bb  push    rdi
0x1800053bc  push    r12
0x1800053be  push    r13
0x1800053c0  push    r14
0x1800053c2  push    r15
0x1800053c4  lea     rbp, [rsp-13D0h]
0x1800053cc  mov     eax, 14D0h
0x1800053d1  call    _alloca_probe
0x1800053d6  sub     rsp, rax
0x1800053d9  mov     rax, cs:__security_cookie
0x1800053e0  xor     rax, rsp
0x1800053e3  mov     [rbp+1400h+var_40], rax
0x1800053ea  mov     r12, r9
0x1800053ed  mov     r14d, edx
0x1800053f0  mov     r15, rcx
0x1800053f3  mov     rdi, [rbp+1400h+arg_20]
0x1800053fa  mov     rsi, [rbp+1400h+arg_28]
0x180005401  xor     edx, edx; Val
0x180005403  mov     r8d, 98h; Size
0x180005409  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000540e  call    memset_0
0x180005413  nop
0x180005414  xor     r13d, r13d
0x180005417  mov     [rbp+1400h+OutputString], r13w
0x18000541f  mov     [rbp+1400h+var_1440], r13b
0x180005423  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18000542a  mov     ecx, [rdx]; this
0x18000542c  mov     [rsp+1500h+var_14D8], ecx
0x180005430  mov     eax, [rdx+4]
0x180005433  mov     [rsp+1500h+var_14D4], eax
0x180005437  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000543c  mov     ebx, eax
0x18000543e  lea     r8d, [r13+1]
0x180005442  mov     dword ptr [rsp+1500h+var_14E0], r8d
0x180005447  mov     ecx, r13d
0x18000544a  lea     eax, [r13+8]
0x18000544e  cmp     [rdx+8], r8d
0x180005452  cmovz   ecx, eax
0x180005455  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180005459  mov     ecx, r8d
0x18000545c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005464  add     ecx, r8d
0x180005467  mov     [rsp+1500h+var_14D0], ecx
0x18000546b  mov     [rsp+1500h+var_14C8], r13
0x180005470  call    cs:__imp_GetCurrentThreadId
0x180005476  mov     [rsp+1500h+var_14C0], eax
0x18000547a  lea     rax, aWil; "wil"
0x180005481  mov     [rsp+1500h+var_14A8], rax
0x180005486  mov     [rsp+1500h+var_14A0], r14d
0x18000548b  mov     [rsp+1500h+var_149C], ebx
0x18000548f  mov     [rsp+1500h+var_14B8], rdi
0x180005494  mov     [rsp+1500h+var_14B0], r12
0x180005499  mov     [rbp+1400h+var_1458], rsi
0x18000549d  mov     [rbp+1400h+var_1450], r15
0x1800054a1  mov     [rsp+1500h+var_1498], r13
0x1800054a6  xorps   xmm0, xmm0
0x1800054a9  xor     eax, eax
0x1800054ab  movups  [rbp+1400h+var_1478], xmm0
0x1800054af  mov     [rbp+1400h+var_1468], rax
0x1800054b3  xorps   xmm1, xmm1
0x1800054b6  movups  [rsp+1500h+var_1490], xmm1
0x1800054bb  mov     [rbp+1400h+var_1480], rax
0x1800054bf  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800054c6  test    rax, rax
0x1800054c9  jz      short loc_1800054D6
0x1800054cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054d0  mov     [rbp+1400h+var_1460], rax
0x1800054d4  jmp     short loc_1800054DA
0x1800054d6  mov     [rbp+1400h+var_1460], r13
0x1800054da  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800054e1  test    rax, rax
0x1800054e4  jz      short loc_1800054F0
0x1800054e6  lea     rcx, [rsp+1500h+var_14E0]
0x1800054eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054f0  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800054f7  test    rax, rax
0x1800054fa  jz      short loc_180005510
0x1800054fc  mov     r8d, 400h
0x180005502  lea     rdx, [rbp+1400h+var_1440]
0x180005506  lea     rcx, [rsp+1500h+var_14E0]
0x18000550b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005510  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005517  test    rax, rax
0x18000551a  jz      short loc_180005526
0x18000551c  lea     rcx, [rsp+1500h+var_14E0]
0x180005521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005526  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000552d  test    rax, rax
0x180005530  jz      short loc_180005543
0x180005532  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005537  jnz     short loc_180005543
0x180005539  lea     rcx, [rsp+1500h+var_14E0]
0x18000553e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005543  cmp     [rsp+1500h+var_14D8], r13d
0x180005548  jge     loc_180005663
0x18000554e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180005555  jnz     short loc_180005576
0x180005557  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000555e  test    rax, rax
0x180005561  jz      short loc_18000556C
0x180005563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005568  test    al, al
0x18000556a  jmp     short loc_180005574
0x18000556c  call    cs:__imp_IsDebuggerPresent
0x180005572  test    eax, eax
0x180005574  jz      short loc_1800055E1
0x180005576  cmp     cs:?g_fResultOutputDebugString@wil@@3_NA, r13b; bool wil::g_fResultOutputDebugString
0x18000557d  jz      short loc_1800055E1
0x18000557f  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005584  jnz     short loc_1800055E1
0x180005586  mov     ebx, 800h
0x18000558b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005592  test    rax, rax
0x180005595  jz      short loc_1800055B4
0x180005597  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000559e  jnz     short loc_1800055B4
0x1800055a0  mov     r8d, ebx
0x1800055a3  lea     rdx, [rbp+1400h+OutputString]
0x1800055aa  lea     rcx, [rsp+1500h+var_14E0]
0x1800055af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055b4  cmp     [rbp+1400h+OutputString], r13w
0x1800055bc  jnz     short loc_1800055D2
0x1800055be  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800055c3  mov     rdx, rbx; unsigned __int16 *
0x1800055c6  lea     rcx, [rbp+1400h+OutputString]; this
0x1800055cd  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800055d2  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800055d9  call    cs:__imp_OutputDebugStringW
0x1800055df  jmp     short loc_180005605
0x1800055e1  mov     rax, cs:g_pfnResultLoggingCallback
0x1800055e8  test    rax, rax
0x1800055eb  jz      short loc_180005605
0x1800055ed  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800055f4  jnz     short loc_180005605
0x1800055f6  xor     r8d, r8d
0x1800055f9  xor     edx, edx
0x1800055fb  lea     rcx, [rsp+1500h+var_14E0]
0x180005600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005605  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000560a  jnz     short loc_180005615
0x18000560c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180005613  jz      short loc_180005627
0x180005615  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000561c  test    rax, rax
0x18000561f  jz      short loc_180005627
0x180005621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005626  nop
0x180005627  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000562c  jnz     short loc_180005658
0x18000562e  mov     rcx, [rbp+1400h+var_40]
0x180005635  xor     rcx, rsp; StackCookie
0x180005638  call    __security_check_cookie
0x18000563d  mov     rbx, [rsp+1500h+arg_10]
0x180005645  add     rsp, 14D0h
0x18000564c  pop     r15
0x18000564e  pop     r14
0x180005650  pop     r13
0x180005652  pop     r12
0x180005654  pop     rdi
0x180005655  pop     rsi
0x180005656  pop     rbp
0x180005657  retn
0x180005658  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000565d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005663  call    ?_FailFastImmediate_Unexpected@in1diag5@details@wil@@YAXXZ; wil::details::in1diag5::_FailFastImmediate_Unexpected(void)
```
