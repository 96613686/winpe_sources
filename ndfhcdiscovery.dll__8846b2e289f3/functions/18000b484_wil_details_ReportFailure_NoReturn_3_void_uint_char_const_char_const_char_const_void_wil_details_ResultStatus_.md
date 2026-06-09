# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000b484`
- end: `0x18000b6f5`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `625`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000b408`

## callees

- `0x180002844`
- `0x180002c48`
- `0x180002fc0`
- `0x18000b484`
- `0x1800108a8`
- `0x180013686`
- `0x180013770`
- `0x180015010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x18000b6bc`
- `KERNEL32!OutputDebugStringW` at `0x18000b6bc`
- `KERNEL32!GetCurrentThreadId` at `0x18000b519`
- `KERNEL32!GetCurrentThreadId` at `0x18000b519`
- `KERNEL32!IsDebuggerPresent` at `0x18000b62c`
- `KERNEL32!IsDebuggerPresent` at `0x18000b62c`

## string_xrefs

- `0x18000b529`: `onecore\internal\sdk\inc\wil\opensource/wil/safecast.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v8; // edx
  int v9; // edi
  int v10; // ecx
  const struct wil::FailureInfo *v11; // rdx
  __int64 v12; // rcx
  const struct wil::FailureInfo *v13; // r9
  bool v14; // zf
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh]
  int v17; // [rsp+28h] [rbp-D8h]
  int v18; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v19; // [rsp+30h] [rbp-D0h]
  __int64 v20; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v22; // [rsp+48h] [rbp-B8h]
  __int64 v23; // [rsp+50h] [rbp-B0h]
  const char *v24; // [rsp+58h] [rbp-A8h]
  int v25; // [rsp+60h] [rbp-A0h]
  int v26; // [rsp+64h] [rbp-9Ch]
  __int64 v27; // [rsp+68h] [rbp-98h]
  __int128 v28; // [rsp+70h] [rbp-90h]
  __int64 v29; // [rsp+80h] [rbp-80h]
  __int128 v30; // [rsp+88h] [rbp-78h]
  __int64 v31; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v33; // [rsp+A8h] [rbp-58h]
  __int64 v34; // [rsp+B0h] [rbp-50h]
  char v35[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v15, 0, 0x98u);
  OutputString[0] = 0;
  v35[0] = 0;
  v17 = *a7;
  v18 = a7[1];
  v9 = wil::details::RecordFailFast((wil::details *)(unsigned int)v17, v8);
  v15 = 3;
  v10 = 0;
  if ( a7[2] == 1 )
    v10 = 8;
  v16 = v10;
  v19 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v20 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v24 = "onecore\\internal\\sdk\\inc\\wil\\opensource/wil/safecast.h";
  v25 = 271;
  v26 = v9;
  v22 = 0;
  v23 = 0;
  v33 = a6;
  v34 = a1;
  v27 = 0;
  v30 = 0;
  v31 = 0;
  v28 = 0;
  v29 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v12);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v15);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v15, v35, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v15);
  if ( wil::details::g_pfnOriginateCallback && (v16 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v15);
  if ( v17 >= 0 )
  {
    v17 = -2147418113;
    v18 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v11);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v14 = !IsDebuggerPresent())
      : (v14 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v12) == 0),
        v14)
    || (v16 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v15, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v15, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v15, v13);
    OutputDebugStringW(OutputString);
  }
  if ( (v16 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v12);
  }
  wil::details::WilFailFast((wil::details *)&v15, v11);
}

```

## disassembly

```asm
0x18000b484  push    rbp
0x18000b486  push    rbx
0x18000b487  push    rsi
0x18000b488  push    rdi
0x18000b489  push    r14
0x18000b48b  push    r15
0x18000b48d  lea     rbp, [rsp-13C8h]
0x18000b495  mov     eax, 14C8h
0x18000b49a  call    _alloca_probe
0x18000b49f  sub     rsp, rax
0x18000b4a2  mov     r14, rcx
0x18000b4a5  mov     rsi, [rbp+13F0h+arg_28]
0x18000b4ac  xor     edx, edx; Val
0x18000b4ae  mov     r8d, 98h; Size
0x18000b4b4  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000b4b9  call    memset_0
0x18000b4be  nop
0x18000b4bf  xor     r15d, r15d
0x18000b4c2  mov     [rbp+13F0h+OutputString], r15w
0x18000b4ca  mov     [rbp+13F0h+var_1430], r15b
0x18000b4ce  mov     rbx, [rbp+13F0h+arg_30]
0x18000b4d5  mov     ecx, [rbx]; this
0x18000b4d7  mov     [rsp+14F0h+var_14C8], ecx
0x18000b4db  mov     eax, [rbx+4]
0x18000b4de  mov     [rsp+14F0h+var_14C4], eax
0x18000b4e2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000b4e7  mov     edi, eax
0x18000b4e9  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000b4f1  mov     ecx, r15d
0x18000b4f4  lea     eax, [r15+8]
0x18000b4f8  cmp     dword ptr [rbx+8], 1
0x18000b4fc  cmovz   ecx, eax
0x18000b4ff  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000b503  lea     ecx, [rax-7]
0x18000b506  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000b50e  inc     ecx
0x18000b510  mov     [rsp+14F0h+var_14C0], ecx
0x18000b514  mov     [rsp+14F0h+var_14B8], r15
0x18000b519  call    cs:__imp_GetCurrentThreadId
0x18000b520  nop     dword ptr [rax+rax+00h]
0x18000b525  mov     [rsp+14F0h+var_14B0], eax
0x18000b529  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b530  mov     [rsp+14F0h+var_1498], rax
0x18000b535  mov     [rsp+14F0h+var_1490], 10Fh
0x18000b53d  mov     [rsp+14F0h+var_148C], edi
0x18000b541  mov     [rsp+14F0h+var_14A8], r15
0x18000b546  mov     [rsp+14F0h+var_14A0], r15
0x18000b54b  mov     [rbp+13F0h+var_1448], rsi
0x18000b54f  mov     [rbp+13F0h+var_1440], r14
0x18000b553  mov     [rsp+14F0h+var_1488], r15
0x18000b558  xorps   xmm0, xmm0
0x18000b55b  xor     eax, eax
0x18000b55d  movups  [rbp+13F0h+var_1468], xmm0
0x18000b561  mov     [rbp+13F0h+var_1458], rax
0x18000b565  xorps   xmm1, xmm1
0x18000b568  movups  [rsp+14F0h+var_1480], xmm1
0x18000b56d  mov     [rbp+13F0h+var_1470], rax
0x18000b571  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000b578  test    rax, rax
0x18000b57b  jz      short loc_18000B588
0x18000b57d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b582  mov     [rbp+13F0h+var_1450], rax
0x18000b586  jmp     short loc_18000B58C
0x18000b588  mov     [rbp+13F0h+var_1450], r15
0x18000b58c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000b593  test    rax, rax
0x18000b596  jz      short loc_18000B5A2
0x18000b598  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b59d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5a2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000b5a9  test    rax, rax
0x18000b5ac  jz      short loc_18000B5C2
0x18000b5ae  mov     r8d, 400h
0x18000b5b4  lea     rdx, [rbp+13F0h+var_1430]
0x18000b5b8  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b5bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5c2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000b5c9  test    rax, rax
0x18000b5cc  jz      short loc_18000B5D8
0x18000b5ce  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b5d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5d8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000b5df  test    rax, rax
0x18000b5e2  jz      short loc_18000B5F5
0x18000b5e4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000b5e9  jnz     short loc_18000B5F5
0x18000b5eb  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b5f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5f5  cmp     [rsp+14F0h+var_14C8], r15d
0x18000b5fa  jl      short loc_18000B60E
0x18000b5fc  mov     ecx, 8000FFFFh; this
0x18000b601  mov     [rsp+14F0h+var_14C8], ecx
0x18000b605  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000b60a  mov     [rsp+14F0h+var_14C4], eax
0x18000b60e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000b615  jnz     short loc_18000B63C
0x18000b617  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000b61e  test    rax, rax
0x18000b621  jz      short loc_18000B62C
0x18000b623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b628  test    al, al
0x18000b62a  jmp     short loc_18000B63A
0x18000b62c  call    cs:__imp_IsDebuggerPresent
0x18000b633  nop     dword ptr [rax+rax+00h]
0x18000b638  test    eax, eax
0x18000b63a  jz      short loc_18000B643
0x18000b63c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000b641  jz      short loc_18000B669
0x18000b643  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b64a  test    rax, rax
0x18000b64d  jz      short loc_18000B6C8
0x18000b64f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000b656  jnz     short loc_18000B6C8
0x18000b658  xor     r8d, r8d
0x18000b65b  xor     edx, edx
0x18000b65d  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b667  jmp     short loc_18000B6C8
0x18000b669  mov     ebx, 800h
0x18000b66e  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b675  test    rax, rax
0x18000b678  jz      short loc_18000B697
0x18000b67a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000b681  jnz     short loc_18000B697
0x18000b683  mov     r8d, ebx
0x18000b686  lea     rdx, [rbp+13F0h+OutputString]
0x18000b68d  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b697  cmp     [rbp+13F0h+OutputString], r15w
0x18000b69f  jnz     short loc_18000B6B5
0x18000b6a1  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000b6a6  mov     rdx, rbx; unsigned __int16 *
0x18000b6a9  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000b6b0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000b6b5  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000b6bc  call    cs:__imp_OutputDebugStringW
0x18000b6c3  nop     dword ptr [rax+rax+00h]
0x18000b6c8  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000b6cd  jnz     short loc_18000B6D8
0x18000b6cf  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000b6d6  jz      short loc_18000B6EA
0x18000b6d8  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000b6df  test    rax, rax
0x18000b6e2  jz      short loc_18000B6EA
0x18000b6e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6e9  nop
0x18000b6ea  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000b6ef  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
