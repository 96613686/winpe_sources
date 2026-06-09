# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000283c`
- end: `0x180002ac9`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000231c`

## callees

- `0x180001510`
- `0x180001e66`
- `0x18000283c`
- `0x1800039a4`
- `0x1800048a0`
- `0x180005860`
- `0x18000593c`
- `0x1800183e0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800028ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800028ea`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800029de`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800029de`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002a68`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002a68`

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
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
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
  v26 = a3;
  v27 = a2;
  v28 = v10;
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
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
0x18000283c  push    rbp
0x18000283e  push    rbx
0x18000283f  push    rsi
0x180002840  push    rdi
0x180002841  push    r12
0x180002843  push    r14
0x180002845  push    r15
0x180002847  lea     rbp, [rsp-13D0h]
0x18000284f  mov     eax, 14D0h
0x180002854  call    _alloca_probe
0x180002859  sub     rsp, rax
0x18000285c  mov     rax, cs:__security_cookie
0x180002863  xor     rax, rsp
0x180002866  mov     [rbp+1400h+var_40], rax
0x18000286d  mov     r14, r8
0x180002870  mov     esi, edx
0x180002872  mov     r15, rcx
0x180002875  mov     rdi, [rbp+1400h+arg_28]
0x18000287c  xor     edx, edx; Val
0x18000287e  mov     r8d, 98h; Size
0x180002884  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180002889  call    memset_0
0x18000288e  nop
0x18000288f  xor     r12d, r12d
0x180002892  mov     [rbp+1400h+OutputString], r12w
0x18000289a  mov     [rbp+1400h+var_1440], r12b
0x18000289e  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1800028a5  mov     ecx, [rdx]; this
0x1800028a7  mov     [rsp+1500h+var_14D8], ecx
0x1800028ab  mov     eax, [rdx+4]
0x1800028ae  mov     [rsp+1500h+var_14D4], eax
0x1800028b2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800028b7  mov     ebx, eax
0x1800028b9  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800028c1  mov     ecx, r12d
0x1800028c4  lea     eax, [r12+8]
0x1800028c9  cmp     dword ptr [rdx+8], 1
0x1800028cd  cmovz   ecx, eax
0x1800028d0  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800028d4  lea     ecx, [rax-7]
0x1800028d7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800028df  inc     ecx
0x1800028e1  mov     [rsp+1500h+var_14D0], ecx
0x1800028e5  mov     [rsp+1500h+var_14C8], r12
0x1800028ea  call    cs:__imp_GetCurrentThreadId
0x1800028f0  mov     [rsp+1500h+var_14C0], eax
0x1800028f4  mov     [rsp+1500h+var_14A8], r14
0x1800028f9  mov     [rsp+1500h+var_14A0], esi
0x1800028fd  mov     [rsp+1500h+var_149C], ebx
0x180002901  mov     [rsp+1500h+var_14B8], r12
0x180002906  mov     [rsp+1500h+var_14B0], r12
0x18000290b  mov     [rbp+1400h+var_1458], rdi
0x18000290f  mov     [rbp+1400h+var_1450], r15
0x180002913  mov     [rsp+1500h+var_1498], r12
0x180002918  xorps   xmm0, xmm0
0x18000291b  xor     eax, eax
0x18000291d  movups  [rbp+1400h+var_1478], xmm0
0x180002921  mov     [rbp+1400h+var_1468], rax
0x180002925  xorps   xmm1, xmm1
0x180002928  movups  [rsp+1500h+var_1490], xmm1
0x18000292d  mov     [rbp+1400h+var_1480], rax
0x180002931  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002938  test    rax, rax
0x18000293b  jz      short loc_180002948
0x18000293d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002942  mov     [rbp+1400h+var_1460], rax
0x180002946  jmp     short loc_18000294C
0x180002948  mov     [rbp+1400h+var_1460], r12
0x18000294c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002953  test    rax, rax
0x180002956  jz      short loc_180002962
0x180002958  lea     rcx, [rsp+1500h+var_14E0]
0x18000295d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002962  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002969  test    rax, rax
0x18000296c  jz      short loc_180002982
0x18000296e  mov     r8d, 400h
0x180002974  lea     rdx, [rbp+1400h+var_1440]
0x180002978  lea     rcx, [rsp+1500h+var_14E0]
0x18000297d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002982  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002989  test    rax, rax
0x18000298c  jz      short loc_180002998
0x18000298e  lea     rcx, [rsp+1500h+var_14E0]
0x180002993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002998  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000299f  test    rax, rax
0x1800029a2  jz      short loc_1800029B5
0x1800029a4  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800029a9  jnz     short loc_1800029B5
0x1800029ab  lea     rcx, [rsp+1500h+var_14E0]
0x1800029b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029b5  cmp     [rsp+1500h+var_14D8], r12d
0x1800029ba  jge     loc_180002AC3
0x1800029c0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800029c7  jnz     short loc_1800029E8
0x1800029c9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800029d0  test    rax, rax
0x1800029d3  jz      short loc_1800029DE
0x1800029d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029da  test    al, al
0x1800029dc  jmp     short loc_1800029E6
0x1800029de  call    cs:__imp_IsDebuggerPresent
0x1800029e4  test    eax, eax
0x1800029e6  jz      short loc_1800029EF
0x1800029e8  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800029ed  jz      short loc_180002A15
0x1800029ef  mov     rax, cs:g_pfnResultLoggingCallback
0x1800029f6  test    rax, rax
0x1800029f9  jz      short loc_180002A6E
0x1800029fb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002a02  jnz     short loc_180002A6E
0x180002a04  xor     r8d, r8d
0x180002a07  xor     edx, edx
0x180002a09  lea     rcx, [rsp+1500h+var_14E0]
0x180002a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a13  jmp     short loc_180002A6E
0x180002a15  mov     ebx, 800h
0x180002a1a  mov     rax, cs:g_pfnResultLoggingCallback
0x180002a21  test    rax, rax
0x180002a24  jz      short loc_180002A43
0x180002a26  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002a2d  jnz     short loc_180002A43
0x180002a2f  mov     r8d, ebx
0x180002a32  lea     rdx, [rbp+1400h+OutputString]
0x180002a39  lea     rcx, [rsp+1500h+var_14E0]
0x180002a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a43  cmp     [rbp+1400h+OutputString], r12w
0x180002a4b  jnz     short loc_180002A61
0x180002a4d  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180002a52  mov     rdx, rbx; unsigned __int16 *
0x180002a55  lea     rcx, [rbp+1400h+OutputString]; this
0x180002a5c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002a61  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180002a68  call    cs:__imp_OutputDebugStringW
0x180002a6e  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180002a73  jnz     short loc_180002A7E
0x180002a75  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002a7c  jz      short loc_180002A90
0x180002a7e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002a85  test    rax, rax
0x180002a88  jz      short loc_180002A90
0x180002a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a8f  nop
0x180002a90  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180002a95  jnz     short loc_180002AB8
0x180002a97  mov     rcx, [rbp+1400h+var_40]
0x180002a9e  xor     rcx, rsp; StackCookie
0x180002aa1  call    __security_check_cookie
0x180002aa6  add     rsp, 14D0h
0x180002aad  pop     r15
0x180002aaf  pop     r14
0x180002ab1  pop     r12
0x180002ab3  pop     rdi
0x180002ab4  pop     rsi
0x180002ab5  pop     rbx
0x180002ab6  pop     rbp
0x180002ab7  retn
0x180002ab8  lea     rcx, [rsp+1500h+var_14E0]; this
0x180002abd  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180002ac3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
