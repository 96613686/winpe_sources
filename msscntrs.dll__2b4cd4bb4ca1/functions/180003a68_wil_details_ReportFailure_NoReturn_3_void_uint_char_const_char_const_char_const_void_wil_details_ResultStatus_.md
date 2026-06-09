# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180003a68`
- end: `0x180003ce1`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800037d8`

## callees

- `0x180003320`
- `0x180003a68`
- `0x1800063c4`
- `0x180006b64`
- `0x180007ae0`
- `0x18000a1f0`
- `0x180015650`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003b21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003b21`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003cae`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003cae`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003c24`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003c24`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // edx
  int v12; // r12d
  int v13; // ecx
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, v11);
  v18 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v19 = v13;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v12;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
  {
    v20 = -2147418113;
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v14);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v15);
  }
  wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180003a68  mov     [rsp-8+arg_18], rbx
0x180003a6d  push    rbp
0x180003a6e  push    rsi
0x180003a6f  push    rdi
0x180003a70  push    r12
0x180003a72  push    r13
0x180003a74  push    r14
0x180003a76  push    r15
0x180003a78  lea     rbp, [rsp-13C0h]
0x180003a80  mov     eax, 14C0h
0x180003a85  call    _alloca_probe
0x180003a8a  sub     rsp, rax
0x180003a8d  mov     r14, r8
0x180003a90  mov     esi, edx
0x180003a92  mov     rdi, rcx
0x180003a95  mov     r15, [rbp+13F0h+arg_28]
0x180003a9c  xor     edx, edx; Val
0x180003a9e  mov     r8d, 98h; Size
0x180003aa4  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003aa9  call    memset_0
0x180003aae  nop
0x180003aaf  xor     r13d, r13d
0x180003ab2  mov     [rbp+13F0h+OutputString], r13w
0x180003aba  mov     [rbp+13F0h+var_1430], r13b
0x180003abe  mov     rbx, [rbp+13F0h+arg_30]
0x180003ac5  mov     ecx, [rbx]; this
0x180003ac7  mov     [rsp+14F0h+var_14C8], ecx
0x180003acb  mov     eax, [rbx+4]
0x180003ace  mov     [rsp+14F0h+var_14C4], eax
0x180003ad2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180003ad7  mov     r12d, eax
0x180003ada  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180003ae2  mov     ecx, r13d
0x180003ae5  lea     eax, [r13+8]
0x180003ae9  cmp     dword ptr [rbx+8], 1
0x180003aed  cmovz   ecx, eax
0x180003af0  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003af4  lea     ecx, [rax-7]
0x180003af7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003aff  inc     ecx
0x180003b01  mov     [rsp+14F0h+var_14C0], ecx
0x180003b05  mov     rcx, [rbp+13F0h+arg_38]
0x180003b0c  test    rcx, rcx
0x180003b0f  jz      short loc_180003B1C
0x180003b11  cmp     [rcx], r13w
0x180003b15  mov     [rsp+14F0h+var_14B8], rcx
0x180003b1a  jnz     short loc_180003B21
0x180003b1c  mov     [rsp+14F0h+var_14B8], r13
0x180003b21  call    cs:__imp_GetCurrentThreadId
0x180003b27  mov     [rsp+14F0h+var_14B0], eax
0x180003b2b  mov     [rsp+14F0h+var_1498], r14
0x180003b30  mov     [rsp+14F0h+var_1490], esi
0x180003b34  mov     [rsp+14F0h+var_148C], r12d
0x180003b39  mov     [rsp+14F0h+var_14A8], r13
0x180003b3e  mov     [rsp+14F0h+var_14A0], r13
0x180003b43  mov     [rbp+13F0h+var_1448], r15
0x180003b47  mov     [rbp+13F0h+var_1440], rdi
0x180003b4b  mov     [rsp+14F0h+var_1488], r13
0x180003b50  xorps   xmm0, xmm0
0x180003b53  xor     eax, eax
0x180003b55  movups  [rbp+13F0h+var_1468], xmm0
0x180003b59  mov     [rbp+13F0h+var_1458], rax
0x180003b5d  xorps   xmm1, xmm1
0x180003b60  movups  [rsp+14F0h+var_1480], xmm1
0x180003b65  mov     [rbp+13F0h+var_1470], rax
0x180003b69  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003b70  test    rax, rax
0x180003b73  jz      short loc_180003B80
0x180003b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b7a  mov     [rbp+13F0h+var_1450], rax
0x180003b7e  jmp     short loc_180003B84
0x180003b80  mov     [rbp+13F0h+var_1450], r13
0x180003b84  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003b8b  test    rax, rax
0x180003b8e  jz      short loc_180003B9A
0x180003b90  lea     rcx, [rsp+14F0h+var_14D0]
0x180003b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b9a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003ba1  test    rax, rax
0x180003ba4  jz      short loc_180003BBA
0x180003ba6  mov     r8d, 400h
0x180003bac  lea     rdx, [rbp+13F0h+var_1430]
0x180003bb0  lea     rcx, [rsp+14F0h+var_14D0]
0x180003bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bba  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003bc1  test    rax, rax
0x180003bc4  jz      short loc_180003BD0
0x180003bc6  lea     rcx, [rsp+14F0h+var_14D0]
0x180003bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bd0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003bd7  test    rax, rax
0x180003bda  jz      short loc_180003BED
0x180003bdc  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003be1  jnz     short loc_180003BED
0x180003be3  lea     rcx, [rsp+14F0h+var_14D0]
0x180003be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bed  cmp     [rsp+14F0h+var_14C8], r13d
0x180003bf2  jl      short loc_180003C06
0x180003bf4  mov     ecx, 8000FFFFh; this
0x180003bf9  mov     [rsp+14F0h+var_14C8], ecx
0x180003bfd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003c02  mov     [rsp+14F0h+var_14C4], eax
0x180003c06  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180003c0d  jnz     short loc_180003C2E
0x180003c0f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003c16  test    rax, rax
0x180003c19  jz      short loc_180003C24
0x180003c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c20  test    al, al
0x180003c22  jmp     short loc_180003C2C
0x180003c24  call    cs:__imp_IsDebuggerPresent
0x180003c2a  test    eax, eax
0x180003c2c  jz      short loc_180003C35
0x180003c2e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003c33  jz      short loc_180003C5B
0x180003c35  mov     rax, cs:g_pfnResultLoggingCallback
0x180003c3c  test    rax, rax
0x180003c3f  jz      short loc_180003CB4
0x180003c41  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003c48  jnz     short loc_180003CB4
0x180003c4a  xor     r8d, r8d
0x180003c4d  xor     edx, edx
0x180003c4f  lea     rcx, [rsp+14F0h+var_14D0]
0x180003c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c59  jmp     short loc_180003CB4
0x180003c5b  mov     ebx, 800h
0x180003c60  mov     rax, cs:g_pfnResultLoggingCallback
0x180003c67  test    rax, rax
0x180003c6a  jz      short loc_180003C89
0x180003c6c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003c73  jnz     short loc_180003C89
0x180003c75  mov     r8d, ebx
0x180003c78  lea     rdx, [rbp+13F0h+OutputString]
0x180003c7f  lea     rcx, [rsp+14F0h+var_14D0]
0x180003c84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c89  cmp     [rbp+13F0h+OutputString], r13w
0x180003c91  jnz     short loc_180003CA7
0x180003c93  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003c98  mov     rdx, rbx; wchar_t *
0x180003c9b  lea     rcx, [rbp+13F0h+OutputString]; this
0x180003ca2  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180003ca7  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003cae  call    cs:__imp_OutputDebugStringW
0x180003cb4  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003cb9  jnz     short loc_180003CC4
0x180003cbb  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180003cc2  jz      short loc_180003CD6
0x180003cc4  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003ccb  test    rax, rax
0x180003cce  jz      short loc_180003CD6
0x180003cd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cd5  nop
0x180003cd6  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003cdb  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
