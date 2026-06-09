# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180007b54`
- end: `0x180007db3`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `607`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180007a74`

## callees

- `0x180002f94`
- `0x18000337c`
- `0x1800036e0`
- `0x180007b54`
- `0x180009c50`
- `0x18001f652`
- `0x18001f750`
- `0x180021010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180007be9`
- `KERNEL32!GetCurrentThreadId` at `0x180007be9`
- `KERNEL32!OutputDebugStringW` at `0x180007d80`
- `KERNEL32!OutputDebugStringW` at `0x180007d80`
- `KERNEL32!IsDebuggerPresent` at `0x180007cf6`
- `KERNEL32!IsDebuggerPresent` at `0x180007cf6`

## string_xrefs

- `0x180007bf3`: `onecore\internal\sdk\inc\wil\opensource/wil/safecast.h`

## pseudocode

```c
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
0x180007b54  push    rbp
0x180007b56  push    rbx
0x180007b57  push    rsi
0x180007b58  push    rdi
0x180007b59  push    r14
0x180007b5b  push    r15
0x180007b5d  lea     rbp, [rsp-13C8h]
0x180007b65  mov     eax, 14C8h
0x180007b6a  call    _alloca_probe
0x180007b6f  sub     rsp, rax
0x180007b72  mov     r14, rcx
0x180007b75  mov     rsi, [rbp+13F0h+arg_28]
0x180007b7c  xor     edx, edx; Val
0x180007b7e  mov     r8d, 98h; Size
0x180007b84  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180007b89  call    memset_0
0x180007b8e  nop
0x180007b8f  xor     r15d, r15d
0x180007b92  mov     [rbp+13F0h+OutputString], r15w
0x180007b9a  mov     [rbp+13F0h+var_1430], r15b
0x180007b9e  mov     rbx, [rbp+13F0h+arg_30]
0x180007ba5  mov     ecx, [rbx]; this
0x180007ba7  mov     [rsp+14F0h+var_14C8], ecx
0x180007bab  mov     eax, [rbx+4]
0x180007bae  mov     [rsp+14F0h+var_14C4], eax
0x180007bb2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180007bb7  mov     edi, eax
0x180007bb9  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180007bc1  mov     ecx, r15d
0x180007bc4  lea     eax, [r15+8]
0x180007bc8  cmp     dword ptr [rbx+8], 1
0x180007bcc  cmovz   ecx, eax
0x180007bcf  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180007bd3  lea     ecx, [rax-7]
0x180007bd6  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007bde  inc     ecx
0x180007be0  mov     [rsp+14F0h+var_14C0], ecx
0x180007be4  mov     [rsp+14F0h+var_14B8], r15
0x180007be9  call    cs:__imp_GetCurrentThreadId
0x180007bef  mov     [rsp+14F0h+var_14B0], eax
0x180007bf3  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007bfa  mov     [rsp+14F0h+var_1498], rax
0x180007bff  mov     [rsp+14F0h+var_1490], 10Fh
0x180007c07  mov     [rsp+14F0h+var_148C], edi
0x180007c0b  mov     [rsp+14F0h+var_14A8], r15
0x180007c10  mov     [rsp+14F0h+var_14A0], r15
0x180007c15  mov     [rbp+13F0h+var_1448], rsi
0x180007c19  mov     [rbp+13F0h+var_1440], r14
0x180007c1d  mov     [rsp+14F0h+var_1488], r15
0x180007c22  xorps   xmm0, xmm0
0x180007c25  xor     eax, eax
0x180007c27  movups  [rbp+13F0h+var_1468], xmm0
0x180007c2b  mov     [rbp+13F0h+var_1458], rax
0x180007c2f  xorps   xmm1, xmm1
0x180007c32  movups  [rsp+14F0h+var_1480], xmm1
0x180007c37  mov     [rbp+13F0h+var_1470], rax
0x180007c3b  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007c42  test    rax, rax
0x180007c45  jz      short loc_180007C52
0x180007c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c4c  mov     [rbp+13F0h+var_1450], rax
0x180007c50  jmp     short loc_180007C56
0x180007c52  mov     [rbp+13F0h+var_1450], r15
0x180007c56  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007c5d  test    rax, rax
0x180007c60  jz      short loc_180007C6C
0x180007c62  lea     rcx, [rsp+14F0h+var_14D0]
0x180007c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c6c  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007c73  test    rax, rax
0x180007c76  jz      short loc_180007C8C
0x180007c78  mov     r8d, 400h
0x180007c7e  lea     rdx, [rbp+13F0h+var_1430]
0x180007c82  lea     rcx, [rsp+14F0h+var_14D0]
0x180007c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c8c  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007c93  test    rax, rax
0x180007c96  jz      short loc_180007CA2
0x180007c98  lea     rcx, [rsp+14F0h+var_14D0]
0x180007c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ca2  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007ca9  test    rax, rax
0x180007cac  jz      short loc_180007CBF
0x180007cae  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007cb3  jnz     short loc_180007CBF
0x180007cb5  lea     rcx, [rsp+14F0h+var_14D0]
0x180007cba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cbf  cmp     [rsp+14F0h+var_14C8], r15d
0x180007cc4  jl      short loc_180007CD8
0x180007cc6  mov     ecx, 8000FFFFh; this
0x180007ccb  mov     [rsp+14F0h+var_14C8], ecx
0x180007ccf  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007cd4  mov     [rsp+14F0h+var_14C4], eax
0x180007cd8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180007cdf  jnz     short loc_180007D00
0x180007ce1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007ce8  test    rax, rax
0x180007ceb  jz      short loc_180007CF6
0x180007ced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cf2  test    al, al
0x180007cf4  jmp     short loc_180007CFE
0x180007cf6  call    cs:__imp_IsDebuggerPresent
0x180007cfc  test    eax, eax
0x180007cfe  jz      short loc_180007D07
0x180007d00  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007d05  jz      short loc_180007D2D
0x180007d07  mov     rax, cs:g_pfnResultLoggingCallback
0x180007d0e  test    rax, rax
0x180007d11  jz      short loc_180007D86
0x180007d13  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180007d1a  jnz     short loc_180007D86
0x180007d1c  xor     r8d, r8d
0x180007d1f  xor     edx, edx
0x180007d21  lea     rcx, [rsp+14F0h+var_14D0]
0x180007d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d2b  jmp     short loc_180007D86
0x180007d2d  mov     ebx, 800h
0x180007d32  mov     rax, cs:g_pfnResultLoggingCallback
0x180007d39  test    rax, rax
0x180007d3c  jz      short loc_180007D5B
0x180007d3e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180007d45  jnz     short loc_180007D5B
0x180007d47  mov     r8d, ebx
0x180007d4a  lea     rdx, [rbp+13F0h+OutputString]
0x180007d51  lea     rcx, [rsp+14F0h+var_14D0]
0x180007d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d5b  cmp     [rbp+13F0h+OutputString], r15w
0x180007d63  jnz     short loc_180007D79
0x180007d65  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180007d6a  mov     rdx, rbx; unsigned __int16 *
0x180007d6d  lea     rcx, [rbp+13F0h+OutputString]; this
0x180007d74  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007d79  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180007d80  call    cs:__imp_OutputDebugStringW
0x180007d86  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180007d8b  jnz     short loc_180007D96
0x180007d8d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180007d94  jz      short loc_180007DA8
0x180007d96  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007d9d  test    rax, rax
0x180007da0  jz      short loc_180007DA8
0x180007da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007da7  nop
0x180007da8  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180007dad  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
