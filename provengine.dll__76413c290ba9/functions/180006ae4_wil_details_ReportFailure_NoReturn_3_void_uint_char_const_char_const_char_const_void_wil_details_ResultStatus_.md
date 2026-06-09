# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180006ae4`
- end: `0x180006d5d`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180006710`

## callees

- `0x180004494`
- `0x1800048d0`
- `0x180004e00`
- `0x1800057d0`
- `0x180006ae4`
- `0x18004371a`
- `0x180043810`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006b9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006b9d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006d2a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006d2a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006ca0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006ca0`

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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
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
0x180006ae4  mov     [rsp-8+arg_18], rbx
0x180006ae9  push    rbp
0x180006aea  push    rsi
0x180006aeb  push    rdi
0x180006aec  push    r12
0x180006aee  push    r13
0x180006af0  push    r14
0x180006af2  push    r15
0x180006af4  lea     rbp, [rsp-13C0h]
0x180006afc  mov     eax, 14C0h
0x180006b01  call    _alloca_probe
0x180006b06  sub     rsp, rax
0x180006b09  mov     r14, r8
0x180006b0c  mov     esi, edx
0x180006b0e  mov     rdi, rcx
0x180006b11  mov     r15, [rbp+13F0h+arg_28]
0x180006b18  xor     edx, edx; Val
0x180006b1a  mov     r8d, 98h; Size
0x180006b20  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180006b25  call    memset_0
0x180006b2a  nop
0x180006b2b  xor     r13d, r13d
0x180006b2e  mov     [rbp+13F0h+OutputString], r13w
0x180006b36  mov     [rbp+13F0h+var_1430], r13b
0x180006b3a  mov     rbx, [rbp+13F0h+arg_30]
0x180006b41  mov     ecx, [rbx]; this
0x180006b43  mov     [rsp+14F0h+var_14C8], ecx
0x180006b47  mov     eax, [rbx+4]
0x180006b4a  mov     [rsp+14F0h+var_14C4], eax
0x180006b4e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006b53  mov     r12d, eax
0x180006b56  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180006b5e  mov     ecx, r13d
0x180006b61  lea     eax, [r13+8]
0x180006b65  cmp     dword ptr [rbx+8], 1
0x180006b69  cmovz   ecx, eax
0x180006b6c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180006b70  lea     ecx, [rax-7]
0x180006b73  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006b7b  inc     ecx
0x180006b7d  mov     [rsp+14F0h+var_14C0], ecx
0x180006b81  mov     rcx, [rbp+13F0h+arg_38]
0x180006b88  test    rcx, rcx
0x180006b8b  jz      short loc_180006B98
0x180006b8d  cmp     [rcx], r13w
0x180006b91  mov     [rsp+14F0h+var_14B8], rcx
0x180006b96  jnz     short loc_180006B9D
0x180006b98  mov     [rsp+14F0h+var_14B8], r13
0x180006b9d  call    cs:__imp_GetCurrentThreadId
0x180006ba3  mov     [rsp+14F0h+var_14B0], eax
0x180006ba7  mov     [rsp+14F0h+var_1498], r14
0x180006bac  mov     [rsp+14F0h+var_1490], esi
0x180006bb0  mov     [rsp+14F0h+var_148C], r12d
0x180006bb5  mov     [rsp+14F0h+var_14A8], r13
0x180006bba  mov     [rsp+14F0h+var_14A0], r13
0x180006bbf  mov     [rbp+13F0h+var_1448], r15
0x180006bc3  mov     [rbp+13F0h+var_1440], rdi
0x180006bc7  mov     [rsp+14F0h+var_1488], r13
0x180006bcc  xorps   xmm0, xmm0
0x180006bcf  xor     eax, eax
0x180006bd1  movups  [rbp+13F0h+var_1468], xmm0
0x180006bd5  mov     [rbp+13F0h+var_1458], rax
0x180006bd9  xorps   xmm1, xmm1
0x180006bdc  movups  [rsp+14F0h+var_1480], xmm1
0x180006be1  mov     [rbp+13F0h+var_1470], rax
0x180006be5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006bec  test    rax, rax
0x180006bef  jz      short loc_180006BFC
0x180006bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bf6  mov     [rbp+13F0h+var_1450], rax
0x180006bfa  jmp     short loc_180006C00
0x180006bfc  mov     [rbp+13F0h+var_1450], r13
0x180006c00  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006c07  test    rax, rax
0x180006c0a  jz      short loc_180006C16
0x180006c0c  lea     rcx, [rsp+14F0h+var_14D0]
0x180006c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c16  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006c1d  test    rax, rax
0x180006c20  jz      short loc_180006C36
0x180006c22  mov     r8d, 400h
0x180006c28  lea     rdx, [rbp+13F0h+var_1430]
0x180006c2c  lea     rcx, [rsp+14F0h+var_14D0]
0x180006c31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c36  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006c3d  test    rax, rax
0x180006c40  jz      short loc_180006C4C
0x180006c42  lea     rcx, [rsp+14F0h+var_14D0]
0x180006c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c4c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006c53  test    rax, rax
0x180006c56  jz      short loc_180006C69
0x180006c58  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180006c5d  jnz     short loc_180006C69
0x180006c5f  lea     rcx, [rsp+14F0h+var_14D0]
0x180006c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c69  cmp     [rsp+14F0h+var_14C8], r13d
0x180006c6e  jl      short loc_180006C82
0x180006c70  mov     ecx, 8000FFFFh; this
0x180006c75  mov     [rsp+14F0h+var_14C8], ecx
0x180006c79  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006c7e  mov     [rsp+14F0h+var_14C4], eax
0x180006c82  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180006c89  jnz     short loc_180006CAA
0x180006c8b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006c92  test    rax, rax
0x180006c95  jz      short loc_180006CA0
0x180006c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c9c  test    al, al
0x180006c9e  jmp     short loc_180006CA8
0x180006ca0  call    cs:__imp_IsDebuggerPresent
0x180006ca6  test    eax, eax
0x180006ca8  jz      short loc_180006CB1
0x180006caa  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180006caf  jz      short loc_180006CD7
0x180006cb1  mov     rax, cs:g_pfnResultLoggingCallback
0x180006cb8  test    rax, rax
0x180006cbb  jz      short loc_180006D30
0x180006cbd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180006cc4  jnz     short loc_180006D30
0x180006cc6  xor     r8d, r8d
0x180006cc9  xor     edx, edx
0x180006ccb  lea     rcx, [rsp+14F0h+var_14D0]
0x180006cd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cd5  jmp     short loc_180006D30
0x180006cd7  mov     ebx, 800h
0x180006cdc  mov     rax, cs:g_pfnResultLoggingCallback
0x180006ce3  test    rax, rax
0x180006ce6  jz      short loc_180006D05
0x180006ce8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180006cef  jnz     short loc_180006D05
0x180006cf1  mov     r8d, ebx
0x180006cf4  lea     rdx, [rbp+13F0h+OutputString]
0x180006cfb  lea     rcx, [rsp+14F0h+var_14D0]
0x180006d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d05  cmp     [rbp+13F0h+OutputString], r13w
0x180006d0d  jnz     short loc_180006D23
0x180006d0f  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180006d14  mov     rdx, rbx; unsigned __int16 *
0x180006d17  lea     rcx, [rbp+13F0h+OutputString]; this
0x180006d1e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006d23  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180006d2a  call    cs:__imp_OutputDebugStringW
0x180006d30  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180006d35  jnz     short loc_180006D40
0x180006d37  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180006d3e  jz      short loc_180006D52
0x180006d40  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006d47  test    rax, rax
0x180006d4a  jz      short loc_180006D52
0x180006d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d51  nop
0x180006d52  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180006d57  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
