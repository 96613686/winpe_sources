# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180008aac`
- end: `0x180008d25`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000877c`

## callees

- `0x180007438`
- `0x180008aac`
- `0x18000c36c`
- `0x18000cea0`
- `0x18000de20`
- `0x180011320`
- `0x180099a90`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008b65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008b65`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008cf2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008cf2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008c68`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008c68`

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
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
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
0x180008aac  mov     [rsp-8+arg_18], rbx
0x180008ab1  push    rbp
0x180008ab2  push    rsi
0x180008ab3  push    rdi
0x180008ab4  push    r12
0x180008ab6  push    r13
0x180008ab8  push    r14
0x180008aba  push    r15
0x180008abc  lea     rbp, [rsp-13C0h]
0x180008ac4  mov     eax, 14C0h
0x180008ac9  call    _alloca_probe
0x180008ace  sub     rsp, rax
0x180008ad1  mov     r14, r8
0x180008ad4  mov     esi, edx
0x180008ad6  mov     rdi, rcx
0x180008ad9  mov     r15, [rbp+13F0h+arg_28]
0x180008ae0  xor     edx, edx; Val
0x180008ae2  mov     r8d, 98h; Size
0x180008ae8  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180008aed  call    memset_0
0x180008af2  nop
0x180008af3  xor     r13d, r13d
0x180008af6  mov     [rbp+13F0h+OutputString], r13w
0x180008afe  mov     [rbp+13F0h+var_1430], r13b
0x180008b02  mov     rbx, [rbp+13F0h+arg_30]
0x180008b09  mov     ecx, [rbx]; this
0x180008b0b  mov     [rsp+14F0h+var_14C8], ecx
0x180008b0f  mov     eax, [rbx+4]
0x180008b12  mov     [rsp+14F0h+var_14C4], eax
0x180008b16  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180008b1b  mov     r12d, eax
0x180008b1e  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180008b26  mov     ecx, r13d
0x180008b29  lea     eax, [r13+8]
0x180008b2d  cmp     dword ptr [rbx+8], 1
0x180008b31  cmovz   ecx, eax
0x180008b34  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180008b38  lea     ecx, [rax-7]
0x180008b3b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008b43  inc     ecx
0x180008b45  mov     [rsp+14F0h+var_14C0], ecx
0x180008b49  mov     rcx, [rbp+13F0h+arg_38]
0x180008b50  test    rcx, rcx
0x180008b53  jz      short loc_180008B60
0x180008b55  cmp     [rcx], r13w
0x180008b59  mov     [rsp+14F0h+var_14B8], rcx
0x180008b5e  jnz     short loc_180008B65
0x180008b60  mov     [rsp+14F0h+var_14B8], r13
0x180008b65  call    cs:__imp_GetCurrentThreadId
0x180008b6b  mov     [rsp+14F0h+var_14B0], eax
0x180008b6f  mov     [rsp+14F0h+var_1498], r14
0x180008b74  mov     [rsp+14F0h+var_1490], esi
0x180008b78  mov     [rsp+14F0h+var_148C], r12d
0x180008b7d  mov     [rsp+14F0h+var_14A8], r13
0x180008b82  mov     [rsp+14F0h+var_14A0], r13
0x180008b87  mov     [rbp+13F0h+var_1448], r15
0x180008b8b  mov     [rbp+13F0h+var_1440], rdi
0x180008b8f  mov     [rsp+14F0h+var_1488], r13
0x180008b94  xorps   xmm0, xmm0
0x180008b97  xor     eax, eax
0x180008b99  movups  [rbp+13F0h+var_1468], xmm0
0x180008b9d  mov     [rbp+13F0h+var_1458], rax
0x180008ba1  xorps   xmm1, xmm1
0x180008ba4  movups  [rsp+14F0h+var_1480], xmm1
0x180008ba9  mov     [rbp+13F0h+var_1470], rax
0x180008bad  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008bb4  test    rax, rax
0x180008bb7  jz      short loc_180008BC4
0x180008bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bbe  mov     [rbp+13F0h+var_1450], rax
0x180008bc2  jmp     short loc_180008BC8
0x180008bc4  mov     [rbp+13F0h+var_1450], r13
0x180008bc8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008bcf  test    rax, rax
0x180008bd2  jz      short loc_180008BDE
0x180008bd4  lea     rcx, [rsp+14F0h+var_14D0]
0x180008bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bde  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008be5  test    rax, rax
0x180008be8  jz      short loc_180008BFE
0x180008bea  mov     r8d, 400h
0x180008bf0  lea     rdx, [rbp+13F0h+var_1430]
0x180008bf4  lea     rcx, [rsp+14F0h+var_14D0]
0x180008bf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bfe  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008c05  test    rax, rax
0x180008c08  jz      short loc_180008C14
0x180008c0a  lea     rcx, [rsp+14F0h+var_14D0]
0x180008c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c14  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008c1b  test    rax, rax
0x180008c1e  jz      short loc_180008C31
0x180008c20  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180008c25  jnz     short loc_180008C31
0x180008c27  lea     rcx, [rsp+14F0h+var_14D0]
0x180008c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c31  cmp     [rsp+14F0h+var_14C8], r13d
0x180008c36  jl      short loc_180008C4A
0x180008c38  mov     ecx, 8000FFFFh; this
0x180008c3d  mov     [rsp+14F0h+var_14C8], ecx
0x180008c41  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008c46  mov     [rsp+14F0h+var_14C4], eax
0x180008c4a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180008c51  jnz     short loc_180008C72
0x180008c53  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008c5a  test    rax, rax
0x180008c5d  jz      short loc_180008C68
0x180008c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c64  test    al, al
0x180008c66  jmp     short loc_180008C70
0x180008c68  call    cs:__imp_IsDebuggerPresent
0x180008c6e  test    eax, eax
0x180008c70  jz      short loc_180008C79
0x180008c72  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180008c77  jz      short loc_180008C9F
0x180008c79  mov     rax, cs:g_pfnResultLoggingCallback
0x180008c80  test    rax, rax
0x180008c83  jz      short loc_180008CF8
0x180008c85  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180008c8c  jnz     short loc_180008CF8
0x180008c8e  xor     r8d, r8d
0x180008c91  xor     edx, edx
0x180008c93  lea     rcx, [rsp+14F0h+var_14D0]
0x180008c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c9d  jmp     short loc_180008CF8
0x180008c9f  mov     ebx, 800h
0x180008ca4  mov     rax, cs:g_pfnResultLoggingCallback
0x180008cab  test    rax, rax
0x180008cae  jz      short loc_180008CCD
0x180008cb0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180008cb7  jnz     short loc_180008CCD
0x180008cb9  mov     r8d, ebx
0x180008cbc  lea     rdx, [rbp+13F0h+OutputString]
0x180008cc3  lea     rcx, [rsp+14F0h+var_14D0]
0x180008cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ccd  cmp     [rbp+13F0h+OutputString], r13w
0x180008cd5  jnz     short loc_180008CEB
0x180008cd7  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180008cdc  mov     rdx, rbx; unsigned __int16 *
0x180008cdf  lea     rcx, [rbp+13F0h+OutputString]; this
0x180008ce6  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008ceb  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180008cf2  call    cs:__imp_OutputDebugStringW
0x180008cf8  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180008cfd  jnz     short loc_180008D08
0x180008cff  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180008d06  jz      short loc_180008D1A
0x180008d08  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008d0f  test    rax, rax
0x180008d12  jz      short loc_180008D1A
0x180008d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d19  nop
0x180008d1a  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180008d1f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
