# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180020794`
- end: `0x180020a28`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002045c`

## callees

- `0x180020794`
- `0x1800219f4`
- `0x1800230ac`
- `0x180024098`
- `0x1800242a8`
- `0x18002656a`
- `0x1800265b0`
- `0x180026640`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002083e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002083e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800209c3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800209c3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180020939`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180020939`

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
0x180020794  mov     [rsp-8+arg_10], rbx
0x180020799  push    rbp
0x18002079a  push    rsi
0x18002079b  push    rdi
0x18002079c  push    r14
0x18002079e  push    r15
0x1800207a0  lea     rbp, [rsp-13D0h]
0x1800207a8  mov     eax, 14D0h
0x1800207ad  call    _alloca_probe
0x1800207b2  sub     rsp, rax
0x1800207b5  mov     rax, cs:__security_cookie
0x1800207bc  xor     rax, rsp
0x1800207bf  mov     [rbp+13F0h+var_30], rax
0x1800207c6  mov     rdi, [rbp+13F0h+arg_28]
0x1800207cd  mov     esi, edx
0x1800207cf  mov     r14, rcx
0x1800207d2  xor     edx, edx; Val
0x1800207d4  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800207d9  mov     r8d, 98h; Size
0x1800207df  call    memset_0
0x1800207e4  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800207eb  xor     r15d, r15d
0x1800207ee  mov     [rbp+13F0h+OutputString], r15w
0x1800207f6  mov     [rbp+13F0h+var_1430], r15b
0x1800207fa  mov     ecx, [rdx]; this
0x1800207fc  mov     eax, [rdx+4]
0x1800207ff  mov     [rsp+14F0h+var_14C8], ecx
0x180020803  mov     [rsp+14F0h+var_14C4], eax
0x180020807  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18002080c  cmp     dword ptr [rdx+8], 1
0x180020810  mov     ebx, eax
0x180020812  lea     eax, [r15+8]
0x180020816  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18002081e  mov     ecx, r15d
0x180020821  cmovz   ecx, eax
0x180020824  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180020828  lea     ecx, [rax-7]
0x18002082b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180020833  inc     ecx
0x180020835  mov     [rsp+14F0h+var_14B8], r15
0x18002083a  mov     [rsp+14F0h+var_14C0], ecx
0x18002083e  call    cs:__imp_GetCurrentThreadId
0x180020844  xorps   xmm0, xmm0
0x180020847  mov     [rsp+14F0h+var_1490], esi
0x18002084b  mov     [rsp+14F0h+var_14B0], eax
0x18002084f  xorps   xmm1, xmm1
0x180020852  lea     rax, aWil; "wil"
0x180020859  mov     [rsp+14F0h+var_148C], ebx
0x18002085d  mov     [rsp+14F0h+var_1498], rax
0x180020862  xor     eax, eax
0x180020864  mov     [rbp+13F0h+var_1458], rax
0x180020868  mov     [rbp+13F0h+var_1470], rax
0x18002086c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180020873  mov     [rsp+14F0h+var_14A8], r15
0x180020878  mov     [rsp+14F0h+var_14A0], r15
0x18002087d  mov     [rbp+13F0h+var_1448], rdi
0x180020881  mov     [rbp+13F0h+var_1440], r14
0x180020885  mov     [rsp+14F0h+var_1488], r15
0x18002088a  movups  [rbp+13F0h+var_1468], xmm0
0x18002088e  movups  [rsp+14F0h+var_1480], xmm1
0x180020893  test    rax, rax
0x180020896  jz      short loc_1800208A3
0x180020898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002089d  mov     [rbp+13F0h+var_1450], rax
0x1800208a1  jmp     short loc_1800208A7
0x1800208a3  mov     [rbp+13F0h+var_1450], r15
0x1800208a7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800208ae  test    rax, rax
0x1800208b1  jz      short loc_1800208BD
0x1800208b3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800208b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208bd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800208c4  test    rax, rax
0x1800208c7  jz      short loc_1800208DD
0x1800208c9  mov     r8d, 400h
0x1800208cf  lea     rdx, [rbp+13F0h+var_1430]
0x1800208d3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800208d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208dd  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800208e4  test    rax, rax
0x1800208e7  jz      short loc_1800208F3
0x1800208e9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800208ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208f3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800208fa  test    rax, rax
0x1800208fd  jz      short loc_180020910
0x1800208ff  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180020904  jnz     short loc_180020910
0x180020906  lea     rcx, [rsp+14F0h+var_14D0]
0x18002090b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020910  cmp     [rsp+14F0h+var_14C8], r15d
0x180020915  jge     loc_180020A17
0x18002091b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180020922  jnz     short loc_180020943
0x180020924  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18002092b  test    rax, rax
0x18002092e  jz      short loc_180020939
0x180020930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020935  test    al, al
0x180020937  jmp     short loc_180020941
0x180020939  call    cs:__imp_IsDebuggerPresent
0x18002093f  test    eax, eax
0x180020941  jz      short loc_18002094A
0x180020943  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180020948  jz      short loc_180020970
0x18002094a  mov     rax, cs:g_pfnResultLoggingCallback
0x180020951  test    rax, rax
0x180020954  jz      short loc_1800209C9
0x180020956  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002095d  jnz     short loc_1800209C9
0x18002095f  xor     r8d, r8d
0x180020962  lea     rcx, [rsp+14F0h+var_14D0]
0x180020967  xor     edx, edx
0x180020969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002096e  jmp     short loc_1800209C9
0x180020970  mov     rax, cs:g_pfnResultLoggingCallback
0x180020977  mov     ebx, 800h
0x18002097c  test    rax, rax
0x18002097f  jz      short loc_18002099E
0x180020981  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180020988  jnz     short loc_18002099E
0x18002098a  mov     r8d, ebx
0x18002098d  lea     rdx, [rbp+13F0h+OutputString]
0x180020994  lea     rcx, [rsp+14F0h+var_14D0]
0x180020999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002099e  cmp     [rbp+13F0h+OutputString], r15w
0x1800209a6  jnz     short loc_1800209BC
0x1800209a8  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800209ad  mov     rdx, rbx; unsigned __int16 *
0x1800209b0  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800209b7  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800209bc  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800209c3  call    cs:__imp_OutputDebugStringW
0x1800209c9  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800209ce  jnz     short loc_1800209D9
0x1800209d0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800209d7  jz      short loc_1800209EA
0x1800209d9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800209e0  test    rax, rax
0x1800209e3  jz      short loc_1800209EA
0x1800209e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209ea  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800209ef  jnz     short loc_180020A1D
0x1800209f1  mov     rcx, [rbp+13F0h+var_30]
0x1800209f8  xor     rcx, rsp; StackCookie
0x1800209fb  call    __security_check_cookie
0x180020a00  mov     rbx, [rsp+14F0h+arg_10]
0x180020a08  add     rsp, 14D0h
0x180020a0f  pop     r15
0x180020a11  pop     r14
0x180020a13  pop     rdi
0x180020a14  pop     rsi
0x180020a15  pop     rbp
0x180020a16  retn
0x180020a17  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180020a1d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180020a22  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
