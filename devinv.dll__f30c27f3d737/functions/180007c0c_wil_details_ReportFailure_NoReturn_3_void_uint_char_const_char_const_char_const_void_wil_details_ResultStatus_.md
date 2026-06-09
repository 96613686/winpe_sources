# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180007c0c`
- end: `0x180007e6e`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800079a8`

## callees

- `0x180006ec4`
- `0x180007c0c`
- `0x18000a734`
- `0x18000aedc`
- `0x18000bfb0`
- `0x18000e8e0`
- `0x18010d870`
- `0x180116010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007cae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007cae`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007e3b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007e3b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007db1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007db1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // edx
  int v11; // edi
  int v12; // ecx
  const struct wil::FailureInfo *v13; // rdx
  __int64 v14; // rcx
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
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v19, v10);
  v17 = 3;
  v12 = 0;
  if ( a7[2] == 1 )
    v12 = 8;
  v18 = v12;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v11;
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
  {
    v19 = -2147418113;
    v20 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v13);
  }
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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( (v18 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v14);
  }
  wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x180007c0c  mov     [rsp-8+arg_18], rbx
0x180007c11  push    rbp
0x180007c12  push    rsi
0x180007c13  push    rdi
0x180007c14  push    r12
0x180007c16  push    r13
0x180007c18  push    r14
0x180007c1a  push    r15
0x180007c1c  lea     rbp, [rsp-13C0h]
0x180007c24  mov     eax, 14C0h
0x180007c29  call    _alloca_probe
0x180007c2e  sub     rsp, rax
0x180007c31  mov     r15, r8
0x180007c34  mov     r14d, edx
0x180007c37  mov     r12, rcx
0x180007c3a  mov     rsi, [rbp+13F0h+arg_28]
0x180007c41  xor     edx, edx; Val
0x180007c43  mov     r8d, 98h; Size
0x180007c49  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180007c4e  call    memset_0
0x180007c53  nop
0x180007c54  xor     r13d, r13d
0x180007c57  mov     [rbp+13F0h+OutputString], r13w
0x180007c5f  mov     [rbp+13F0h+var_1430], r13b
0x180007c63  mov     rbx, [rbp+13F0h+arg_30]
0x180007c6a  mov     ecx, [rbx]; this
0x180007c6c  mov     [rsp+14F0h+var_14C8], ecx
0x180007c70  mov     eax, [rbx+4]
0x180007c73  mov     [rsp+14F0h+var_14C4], eax
0x180007c77  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180007c7c  mov     edi, eax
0x180007c7e  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180007c86  mov     ecx, r13d
0x180007c89  lea     eax, [r13+8]
0x180007c8d  cmp     dword ptr [rbx+8], 1
0x180007c91  cmovz   ecx, eax
0x180007c94  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180007c98  lea     ecx, [rax-7]
0x180007c9b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007ca3  inc     ecx
0x180007ca5  mov     [rsp+14F0h+var_14C0], ecx
0x180007ca9  mov     [rsp+14F0h+var_14B8], r13
0x180007cae  call    cs:__imp_GetCurrentThreadId
0x180007cb4  mov     [rsp+14F0h+var_14B0], eax
0x180007cb8  mov     [rsp+14F0h+var_1498], r15
0x180007cbd  mov     [rsp+14F0h+var_1490], r14d
0x180007cc2  mov     [rsp+14F0h+var_148C], edi
0x180007cc6  mov     [rsp+14F0h+var_14A8], r13
0x180007ccb  mov     [rsp+14F0h+var_14A0], r13
0x180007cd0  mov     [rbp+13F0h+var_1448], rsi
0x180007cd4  mov     [rbp+13F0h+var_1440], r12
0x180007cd8  mov     [rsp+14F0h+var_1488], r13
0x180007cdd  xorps   xmm0, xmm0
0x180007ce0  xor     eax, eax
0x180007ce2  movups  [rbp+13F0h+var_1468], xmm0
0x180007ce6  mov     [rbp+13F0h+var_1458], rax
0x180007cea  xorps   xmm1, xmm1
0x180007ced  movups  [rsp+14F0h+var_1480], xmm1
0x180007cf2  mov     [rbp+13F0h+var_1470], rax
0x180007cf6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007cfd  test    rax, rax
0x180007d00  jz      short loc_180007D0D
0x180007d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d07  mov     [rbp+13F0h+var_1450], rax
0x180007d0b  jmp     short loc_180007D11
0x180007d0d  mov     [rbp+13F0h+var_1450], r13
0x180007d11  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007d18  test    rax, rax
0x180007d1b  jz      short loc_180007D27
0x180007d1d  lea     rcx, [rsp+14F0h+var_14D0]
0x180007d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d27  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007d2e  test    rax, rax
0x180007d31  jz      short loc_180007D47
0x180007d33  mov     r8d, 400h
0x180007d39  lea     rdx, [rbp+13F0h+var_1430]
0x180007d3d  lea     rcx, [rsp+14F0h+var_14D0]
0x180007d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d47  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007d4e  test    rax, rax
0x180007d51  jz      short loc_180007D5D
0x180007d53  lea     rcx, [rsp+14F0h+var_14D0]
0x180007d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d5d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007d64  test    rax, rax
0x180007d67  jz      short loc_180007D7A
0x180007d69  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007d6e  jnz     short loc_180007D7A
0x180007d70  lea     rcx, [rsp+14F0h+var_14D0]
0x180007d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d7a  cmp     [rsp+14F0h+var_14C8], r13d
0x180007d7f  jl      short loc_180007D93
0x180007d81  mov     ecx, 8000FFFFh; this
0x180007d86  mov     [rsp+14F0h+var_14C8], ecx
0x180007d8a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007d8f  mov     [rsp+14F0h+var_14C4], eax
0x180007d93  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180007d9a  jnz     short loc_180007DBB
0x180007d9c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007da3  test    rax, rax
0x180007da6  jz      short loc_180007DB1
0x180007da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dad  test    al, al
0x180007daf  jmp     short loc_180007DB9
0x180007db1  call    cs:__imp_IsDebuggerPresent
0x180007db7  test    eax, eax
0x180007db9  jz      short loc_180007DC2
0x180007dbb  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007dc0  jz      short loc_180007DE8
0x180007dc2  mov     rax, cs:g_pfnResultLoggingCallback
0x180007dc9  test    rax, rax
0x180007dcc  jz      short loc_180007E41
0x180007dce  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180007dd5  jnz     short loc_180007E41
0x180007dd7  xor     r8d, r8d
0x180007dda  xor     edx, edx
0x180007ddc  lea     rcx, [rsp+14F0h+var_14D0]
0x180007de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007de6  jmp     short loc_180007E41
0x180007de8  mov     ebx, 800h
0x180007ded  mov     rax, cs:g_pfnResultLoggingCallback
0x180007df4  test    rax, rax
0x180007df7  jz      short loc_180007E16
0x180007df9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180007e00  jnz     short loc_180007E16
0x180007e02  mov     r8d, ebx
0x180007e05  lea     rdx, [rbp+13F0h+OutputString]
0x180007e0c  lea     rcx, [rsp+14F0h+var_14D0]
0x180007e11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e16  cmp     [rbp+13F0h+OutputString], r13w
0x180007e1e  jnz     short loc_180007E34
0x180007e20  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180007e25  mov     rdx, rbx; unsigned __int16 *
0x180007e28  lea     rcx, [rbp+13F0h+OutputString]; this
0x180007e2f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007e34  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180007e3b  call    cs:__imp_OutputDebugStringW
0x180007e41  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180007e46  jnz     short loc_180007E51
0x180007e48  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180007e4f  jz      short loc_180007E63
0x180007e51  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007e58  test    rax, rax
0x180007e5b  jz      short loc_180007E63
0x180007e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e62  nop
0x180007e63  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180007e68  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
