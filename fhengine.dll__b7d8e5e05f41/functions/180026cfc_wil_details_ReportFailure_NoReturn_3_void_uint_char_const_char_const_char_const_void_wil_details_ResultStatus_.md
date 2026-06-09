# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180026cfc`
- end: `0x180026f5e`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180026ac8`

## callees

- `0x180026cfc`
- `0x18002a094`
- `0x18002aa30`
- `0x18002be50`
- `0x18002e070`
- `0x180031642`
- `0x180031740`
- `0x180034010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180026f2b`
- `KERNEL32!OutputDebugStringW` at `0x180026f2b`
- `KERNEL32!IsDebuggerPresent` at `0x180026ea1`
- `KERNEL32!IsDebuggerPresent` at `0x180026ea1`
- `KERNEL32!GetCurrentThreadId` at `0x180026d9e`
- `KERNEL32!GetCurrentThreadId` at `0x180026d9e`

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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
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
0x180026cfc  mov     [rsp-8+arg_18], rbx
0x180026d01  push    rbp
0x180026d02  push    rsi
0x180026d03  push    rdi
0x180026d04  push    r12
0x180026d06  push    r13
0x180026d08  push    r14
0x180026d0a  push    r15
0x180026d0c  lea     rbp, [rsp-13C0h]
0x180026d14  mov     eax, 14C0h
0x180026d19  call    _alloca_probe
0x180026d1e  sub     rsp, rax
0x180026d21  mov     r15, r8
0x180026d24  mov     r14d, edx
0x180026d27  mov     r12, rcx
0x180026d2a  mov     rsi, [rbp+13F0h+arg_28]
0x180026d31  xor     edx, edx; Val
0x180026d33  mov     r8d, 98h; Size
0x180026d39  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180026d3e  call    memset_0
0x180026d43  nop
0x180026d44  xor     r13d, r13d
0x180026d47  mov     [rbp+13F0h+OutputString], r13w
0x180026d4f  mov     [rbp+13F0h+var_1430], r13b
0x180026d53  mov     rbx, [rbp+13F0h+arg_30]
0x180026d5a  mov     ecx, [rbx]; this
0x180026d5c  mov     [rsp+14F0h+var_14C8], ecx
0x180026d60  mov     eax, [rbx+4]
0x180026d63  mov     [rsp+14F0h+var_14C4], eax
0x180026d67  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180026d6c  mov     edi, eax
0x180026d6e  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180026d76  mov     ecx, r13d
0x180026d79  lea     eax, [r13+8]
0x180026d7d  cmp     dword ptr [rbx+8], 1
0x180026d81  cmovz   ecx, eax
0x180026d84  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180026d88  lea     ecx, [rax-7]
0x180026d8b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180026d93  inc     ecx
0x180026d95  mov     [rsp+14F0h+var_14C0], ecx
0x180026d99  mov     [rsp+14F0h+var_14B8], r13
0x180026d9e  call    cs:__imp_GetCurrentThreadId
0x180026da4  mov     [rsp+14F0h+var_14B0], eax
0x180026da8  mov     [rsp+14F0h+var_1498], r15
0x180026dad  mov     [rsp+14F0h+var_1490], r14d
0x180026db2  mov     [rsp+14F0h+var_148C], edi
0x180026db6  mov     [rsp+14F0h+var_14A8], r13
0x180026dbb  mov     [rsp+14F0h+var_14A0], r13
0x180026dc0  mov     [rbp+13F0h+var_1448], rsi
0x180026dc4  mov     [rbp+13F0h+var_1440], r12
0x180026dc8  mov     [rsp+14F0h+var_1488], r13
0x180026dcd  xorps   xmm0, xmm0
0x180026dd0  xor     eax, eax
0x180026dd2  movups  [rbp+13F0h+var_1468], xmm0
0x180026dd6  mov     [rbp+13F0h+var_1458], rax
0x180026dda  xorps   xmm1, xmm1
0x180026ddd  movups  [rsp+14F0h+var_1480], xmm1
0x180026de2  mov     [rbp+13F0h+var_1470], rax
0x180026de6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180026ded  test    rax, rax
0x180026df0  jz      short loc_180026DFD
0x180026df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026df7  mov     [rbp+13F0h+var_1450], rax
0x180026dfb  jmp     short loc_180026E01
0x180026dfd  mov     [rbp+13F0h+var_1450], r13
0x180026e01  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180026e08  test    rax, rax
0x180026e0b  jz      short loc_180026E17
0x180026e0d  lea     rcx, [rsp+14F0h+var_14D0]
0x180026e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e17  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180026e1e  test    rax, rax
0x180026e21  jz      short loc_180026E37
0x180026e23  mov     r8d, 400h
0x180026e29  lea     rdx, [rbp+13F0h+var_1430]
0x180026e2d  lea     rcx, [rsp+14F0h+var_14D0]
0x180026e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e37  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180026e3e  test    rax, rax
0x180026e41  jz      short loc_180026E4D
0x180026e43  lea     rcx, [rsp+14F0h+var_14D0]
0x180026e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e4d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180026e54  test    rax, rax
0x180026e57  jz      short loc_180026E6A
0x180026e59  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180026e5e  jnz     short loc_180026E6A
0x180026e60  lea     rcx, [rsp+14F0h+var_14D0]
0x180026e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e6a  cmp     [rsp+14F0h+var_14C8], r13d
0x180026e6f  jl      short loc_180026E83
0x180026e71  mov     ecx, 8000FFFFh; this
0x180026e76  mov     [rsp+14F0h+var_14C8], ecx
0x180026e7a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180026e7f  mov     [rsp+14F0h+var_14C4], eax
0x180026e83  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180026e8a  jnz     short loc_180026EAB
0x180026e8c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180026e93  test    rax, rax
0x180026e96  jz      short loc_180026EA1
0x180026e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e9d  test    al, al
0x180026e9f  jmp     short loc_180026EA9
0x180026ea1  call    cs:__imp_IsDebuggerPresent
0x180026ea7  test    eax, eax
0x180026ea9  jz      short loc_180026EB2
0x180026eab  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180026eb0  jz      short loc_180026ED8
0x180026eb2  mov     rax, cs:g_pfnResultLoggingCallback
0x180026eb9  test    rax, rax
0x180026ebc  jz      short loc_180026F31
0x180026ebe  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180026ec5  jnz     short loc_180026F31
0x180026ec7  xor     r8d, r8d
0x180026eca  xor     edx, edx
0x180026ecc  lea     rcx, [rsp+14F0h+var_14D0]
0x180026ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ed6  jmp     short loc_180026F31
0x180026ed8  mov     ebx, 800h
0x180026edd  mov     rax, cs:g_pfnResultLoggingCallback
0x180026ee4  test    rax, rax
0x180026ee7  jz      short loc_180026F06
0x180026ee9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180026ef0  jnz     short loc_180026F06
0x180026ef2  mov     r8d, ebx
0x180026ef5  lea     rdx, [rbp+13F0h+OutputString]
0x180026efc  lea     rcx, [rsp+14F0h+var_14D0]
0x180026f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f06  cmp     [rbp+13F0h+OutputString], r13w
0x180026f0e  jnz     short loc_180026F24
0x180026f10  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180026f15  mov     rdx, rbx; unsigned __int16 *
0x180026f18  lea     rcx, [rbp+13F0h+OutputString]; this
0x180026f1f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180026f24  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180026f2b  call    cs:__imp_OutputDebugStringW
0x180026f31  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180026f36  jnz     short loc_180026F41
0x180026f38  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180026f3f  jz      short loc_180026F53
0x180026f41  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180026f48  test    rax, rax
0x180026f4b  jz      short loc_180026F53
0x180026f4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f52  nop
0x180026f53  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180026f58  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
