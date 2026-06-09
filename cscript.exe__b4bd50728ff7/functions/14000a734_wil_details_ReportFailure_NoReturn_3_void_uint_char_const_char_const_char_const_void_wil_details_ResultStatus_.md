# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x14000a734`
- end: `0x14000a994`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14000a500`

## callees

- `0x14000a734`
- `0x14000b49c`
- `0x14000b9cc`
- `0x14000c170`
- `0x14000c8b4`
- `0x14001619a`
- `0x140016200`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000a7d5`
- `KERNEL32!GetCurrentThreadId` at `0x14000a7d5`
- `KERNEL32!OutputDebugStringW` at `0x14000a962`
- `KERNEL32!OutputDebugStringW` at `0x14000a962`
- `KERNEL32!IsDebuggerPresent` at `0x14000a8d8`
- `KERNEL32!IsDebuggerPresent` at `0x14000a8d8`

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
0x14000a734  mov     [rsp-8+arg_18], rbx
0x14000a739  push    rbp
0x14000a73a  push    rsi
0x14000a73b  push    rdi
0x14000a73c  push    r12
0x14000a73e  push    r13
0x14000a740  push    r14
0x14000a742  push    r15
0x14000a744  lea     rbp, [rsp-13C0h]
0x14000a74c  mov     eax, 14C0h
0x14000a751  call    _alloca_probe
0x14000a756  sub     rsp, rax
0x14000a759  mov     rsi, [rbp+13F0h+arg_28]
0x14000a760  mov     r15, r8
0x14000a763  mov     r14d, edx
0x14000a766  mov     r12, rcx
0x14000a769  xor     edx, edx; Val
0x14000a76b  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x14000a770  mov     r8d, 98h; Size
0x14000a776  call    memset_0
0x14000a77b  mov     rbx, [rbp+13F0h+arg_30]
0x14000a782  xor     r13d, r13d
0x14000a785  mov     [rbp+13F0h+OutputString], r13w
0x14000a78d  mov     [rbp+13F0h+var_1430], r13b
0x14000a791  mov     ecx, [rbx]; this
0x14000a793  mov     eax, [rbx+4]
0x14000a796  mov     [rsp+14F0h+var_14C8], ecx
0x14000a79a  mov     [rsp+14F0h+var_14C4], eax
0x14000a79e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000a7a3  cmp     dword ptr [rbx+8], 1
0x14000a7a7  mov     edi, eax
0x14000a7a9  lea     eax, [r13+8]
0x14000a7ad  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x14000a7b5  mov     ecx, r13d
0x14000a7b8  cmovz   ecx, eax
0x14000a7bb  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x14000a7bf  lea     ecx, [rax-7]
0x14000a7c2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000a7ca  inc     ecx
0x14000a7cc  mov     [rsp+14F0h+var_14B8], r13
0x14000a7d1  mov     [rsp+14F0h+var_14C0], ecx
0x14000a7d5  call    cs:__imp_GetCurrentThreadId
0x14000a7db  xorps   xmm0, xmm0
0x14000a7de  mov     [rsp+14F0h+var_1498], r15
0x14000a7e3  mov     [rsp+14F0h+var_14B0], eax
0x14000a7e7  xorps   xmm1, xmm1
0x14000a7ea  xor     eax, eax
0x14000a7ec  mov     [rsp+14F0h+var_1490], r14d
0x14000a7f1  mov     [rbp+13F0h+var_1458], rax
0x14000a7f5  mov     [rbp+13F0h+var_1470], rax
0x14000a7f9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000a800  mov     [rsp+14F0h+var_148C], edi
0x14000a804  mov     [rsp+14F0h+var_14A8], r13
0x14000a809  mov     [rsp+14F0h+var_14A0], r13
0x14000a80e  mov     [rbp+13F0h+var_1448], rsi
0x14000a812  mov     [rbp+13F0h+var_1440], r12
0x14000a816  mov     [rsp+14F0h+var_1488], r13
0x14000a81b  movups  [rbp+13F0h+var_1468], xmm0
0x14000a81f  movups  [rsp+14F0h+var_1480], xmm1
0x14000a824  test    rax, rax
0x14000a827  jz      short loc_14000A834
0x14000a829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a82e  mov     [rbp+13F0h+var_1450], rax
0x14000a832  jmp     short loc_14000A838
0x14000a834  mov     [rbp+13F0h+var_1450], r13
0x14000a838  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000a83f  test    rax, rax
0x14000a842  jz      short loc_14000A84E
0x14000a844  lea     rcx, [rsp+14F0h+var_14D0]
0x14000a849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a84e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000a855  test    rax, rax
0x14000a858  jz      short loc_14000A86E
0x14000a85a  mov     r8d, 400h
0x14000a860  lea     rdx, [rbp+13F0h+var_1430]
0x14000a864  lea     rcx, [rsp+14F0h+var_14D0]
0x14000a869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a86e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000a875  test    rax, rax
0x14000a878  jz      short loc_14000A884
0x14000a87a  lea     rcx, [rsp+14F0h+var_14D0]
0x14000a87f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a884  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000a88b  test    rax, rax
0x14000a88e  jz      short loc_14000A8A1
0x14000a890  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000a895  jnz     short loc_14000A8A1
0x14000a897  lea     rcx, [rsp+14F0h+var_14D0]
0x14000a89c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a8a1  cmp     [rsp+14F0h+var_14C8], r13d
0x14000a8a6  jl      short loc_14000A8BA
0x14000a8a8  mov     ecx, 8000FFFFh; this
0x14000a8ad  mov     [rsp+14F0h+var_14C8], ecx
0x14000a8b1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000a8b6  mov     [rsp+14F0h+var_14C4], eax
0x14000a8ba  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x14000a8c1  jnz     short loc_14000A8E2
0x14000a8c3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000a8ca  test    rax, rax
0x14000a8cd  jz      short loc_14000A8D8
0x14000a8cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a8d4  test    al, al
0x14000a8d6  jmp     short loc_14000A8E0
0x14000a8d8  call    cs:__imp_IsDebuggerPresent
0x14000a8de  test    eax, eax
0x14000a8e0  jz      short loc_14000A8E9
0x14000a8e2  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000a8e7  jz      short loc_14000A90F
0x14000a8e9  mov     rax, cs:g_pfnResultLoggingCallback
0x14000a8f0  test    rax, rax
0x14000a8f3  jz      short loc_14000A968
0x14000a8f5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x14000a8fc  jnz     short loc_14000A968
0x14000a8fe  xor     r8d, r8d
0x14000a901  lea     rcx, [rsp+14F0h+var_14D0]
0x14000a906  xor     edx, edx
0x14000a908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a90d  jmp     short loc_14000A968
0x14000a90f  mov     rax, cs:g_pfnResultLoggingCallback
0x14000a916  mov     ebx, 800h
0x14000a91b  test    rax, rax
0x14000a91e  jz      short loc_14000A93D
0x14000a920  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x14000a927  jnz     short loc_14000A93D
0x14000a929  mov     r8d, ebx
0x14000a92c  lea     rdx, [rbp+13F0h+OutputString]
0x14000a933  lea     rcx, [rsp+14F0h+var_14D0]
0x14000a938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a93d  cmp     [rbp+13F0h+OutputString], r13w
0x14000a945  jnz     short loc_14000A95B
0x14000a947  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x14000a94c  mov     rdx, rbx; unsigned __int16 *
0x14000a94f  lea     rcx, [rbp+13F0h+OutputString]; this
0x14000a956  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000a95b  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x14000a962  call    cs:__imp_OutputDebugStringW
0x14000a968  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x14000a96d  jnz     short loc_14000A978
0x14000a96f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x14000a976  jz      short loc_14000A989
0x14000a978  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000a97f  test    rax, rax
0x14000a982  jz      short loc_14000A989
0x14000a984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a989  lea     rcx, [rsp+14F0h+var_14D0]; this
0x14000a98e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
