# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180021b20`
- end: `0x180021da9`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `649`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800218a0`

## callees

- `0x180021b20`
- `0x180024540`
- `0x180024d90`
- `0x1800265b0`
- `0x1800290f0`
- `0x18002f5f0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021be5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021be5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180021d76`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180021d76`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180021cec`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180021cec`

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
        __int64 a7)
{
  unsigned int v10; // edi
  int v11; // ecx
  const struct wil::FailureInfo *v12; // rdx
  __int64 v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  unsigned __int64 v16[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v17; // [rsp+30h] [rbp-D0h]
  __int128 v18; // [rsp+40h] [rbp-C0h]
  __int128 v19; // [rsp+50h] [rbp-B0h]
  __int128 v20; // [rsp+60h] [rbp-A0h]
  __int128 v21; // [rsp+70h] [rbp-90h]
  _OWORD v22[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v23; // [rsp+A0h] [rbp-60h]
  __int64 v24; // [rsp+B0h] [rbp-50h]
  _BYTE v25[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  *(_OWORD *)v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  memset(v22, 0, sizeof(v22));
  v23 = 0;
  v24 = 0;
  OutputString[0] = 0;
  v25[0] = 0;
  v16[1] = *(_QWORD *)a7;
  v10 = wil::details::RecordFailFast((wil::details *)LODWORD(v16[1]), a2);
  LODWORD(v16[0]) = 3;
  v11 = 0;
  if ( *(_DWORD *)(a7 + 8) == 1 )
    v11 = 8;
  HIDWORD(v16[0]) = v11;
  LODWORD(v17) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  *((_QWORD *)&v17 + 1) = 0;
  LODWORD(v18) = GetCurrentThreadId();
  *((_QWORD *)&v19 + 1) = a3;
  v20 = __PAIR64__(v10, a2);
  *((_QWORD *)&v18 + 1) = 0;
  *(_QWORD *)&v19 = 0;
  *((_QWORD *)&v23 + 1) = a6;
  v24 = a1;
  v21 = 0;
  memset(v22, 0, sizeof(v22));
  if ( wil::details::g_pfnGetModuleName )
    *(_QWORD *)&v23 = wil::details::g_pfnGetModuleName(v13);
  else
    *(_QWORD *)&v23 = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v16, v25, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v16);
  if ( wil::details::g_pfnOriginateCallback && (v16[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v16);
  if ( SLODWORD(v16[1]) >= 0 )
  {
    LODWORD(v16[1]) = -2147418113;
    HIDWORD(v16[1]) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v12);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v16[0] & 0x200000000LL) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( (v16[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v13);
  }
  wil::details::WilFailFast((wil::details *)v16, v12);
}

```

## disassembly

```asm
0x180021b20  mov     [rsp-8+arg_18], rbx
0x180021b25  push    rbp
0x180021b26  push    rsi
0x180021b27  push    rdi
0x180021b28  push    r12
0x180021b2a  push    r13
0x180021b2c  push    r14
0x180021b2e  push    r15
0x180021b30  lea     rbp, [rsp-13C0h]
0x180021b38  mov     eax, 14C0h
0x180021b3d  call    _alloca_probe
0x180021b42  sub     rsp, rax
0x180021b45  mov     r15, r8
0x180021b48  mov     r14d, edx
0x180021b4b  mov     r12, rcx
0x180021b4e  mov     rsi, [rbp+13F0h+arg_28]
0x180021b55  xorps   xmm0, xmm0
0x180021b58  xor     eax, eax
0x180021b5a  movups  xmmword ptr [rsp+14F0h+var_14D0], xmm0
0x180021b5f  movups  [rsp+14F0h+var_14C0], xmm0
0x180021b64  movups  [rsp+14F0h+var_14B0], xmm0
0x180021b69  movups  [rsp+14F0h+var_14A0], xmm0
0x180021b6e  movups  [rsp+14F0h+var_1490], xmm0
0x180021b73  movups  [rsp+14F0h+var_1480], xmm0
0x180021b78  movups  [rbp+13F0h+var_1470], xmm0
0x180021b7c  movups  [rbp+13F0h+var_1460], xmm0
0x180021b80  movups  [rbp+13F0h+var_1450], xmm0
0x180021b84  mov     [rbp+13F0h+var_1440], rax
0x180021b88  xor     r13d, r13d
0x180021b8b  mov     [rbp+13F0h+OutputString], r13w
0x180021b93  mov     [rbp+13F0h+var_1430], r13b
0x180021b97  mov     rbx, [rbp+13F0h+arg_30]
0x180021b9e  mov     ecx, [rbx]; this
0x180021ba0  mov     dword ptr [rsp+14F0h+var_14D0+8], ecx
0x180021ba4  mov     eax, [rbx+4]
0x180021ba7  mov     dword ptr [rsp+14F0h+var_14D0+0Ch], eax
0x180021bab  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180021bb0  mov     edi, eax
0x180021bb2  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180021bba  mov     ecx, r13d
0x180021bbd  mov     eax, 8
0x180021bc2  cmp     dword ptr [rbx+8], 1
0x180021bc6  cmovz   ecx, eax
0x180021bc9  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180021bcd  mov     ecx, 1
0x180021bd2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180021bda  inc     ecx
0x180021bdc  mov     dword ptr [rsp+14F0h+var_14C0], ecx
0x180021be0  mov     qword ptr [rsp+14F0h+var_14C0+8], r13
0x180021be5  call    cs:__imp_GetCurrentThreadId
0x180021beb  mov     dword ptr [rsp+14F0h+var_14B0], eax
0x180021bef  mov     qword ptr [rsp+14F0h+var_14A0+8], r15
0x180021bf4  mov     dword ptr [rsp+14F0h+var_1490], r14d
0x180021bf9  mov     dword ptr [rsp+14F0h+var_1490+4], edi
0x180021bfd  mov     qword ptr [rsp+14F0h+var_14B0+8], r13
0x180021c02  mov     qword ptr [rsp+14F0h+var_14A0], r13
0x180021c07  mov     qword ptr [rbp+13F0h+var_1450+8], rsi
0x180021c0b  mov     [rbp+13F0h+var_1440], r12
0x180021c0f  mov     qword ptr [rsp+14F0h+var_1490+8], r13
0x180021c14  xorps   xmm0, xmm0
0x180021c17  xor     eax, eax
0x180021c19  movups  [rbp+13F0h+var_1470+8], xmm0
0x180021c1d  mov     qword ptr [rbp+13F0h+var_1460+8], rax
0x180021c21  xorps   xmm1, xmm1
0x180021c24  movups  [rsp+14F0h+var_1480], xmm1
0x180021c29  mov     qword ptr [rbp+13F0h+var_1470], rax
0x180021c2d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180021c34  test    rax, rax
0x180021c37  jz      short loc_180021C44
0x180021c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c3e  mov     qword ptr [rbp+13F0h+var_1450], rax
0x180021c42  jmp     short loc_180021C48
0x180021c44  mov     qword ptr [rbp+13F0h+var_1450], r13
0x180021c48  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180021c4f  test    rax, rax
0x180021c52  jz      short loc_180021C5E
0x180021c54  lea     rcx, [rsp+14F0h+var_14D0]
0x180021c59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c5e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180021c65  test    rax, rax
0x180021c68  jz      short loc_180021C7E
0x180021c6a  mov     r8d, 400h
0x180021c70  lea     rdx, [rbp+13F0h+var_1430]
0x180021c74  lea     rcx, [rsp+14F0h+var_14D0]
0x180021c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c7e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180021c85  test    rax, rax
0x180021c88  jz      short loc_180021C94
0x180021c8a  lea     rcx, [rsp+14F0h+var_14D0]
0x180021c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c94  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180021c9b  test    rax, rax
0x180021c9e  jz      short loc_180021CB1
0x180021ca0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180021ca5  jnz     short loc_180021CB1
0x180021ca7  lea     rcx, [rsp+14F0h+var_14D0]
0x180021cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021cb1  cmp     dword ptr [rsp+14F0h+var_14D0+8], r13d
0x180021cb6  jl      short loc_180021CCE
0x180021cb8  mov     dword ptr [rsp+14F0h+var_14D0+8], 8000FFFFh
0x180021cc0  mov     ecx, 8000FFFFh; this
0x180021cc5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180021cca  mov     dword ptr [rsp+14F0h+var_14D0+0Ch], eax
0x180021cce  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180021cd5  jnz     short loc_180021CF6
0x180021cd7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180021cde  test    rax, rax
0x180021ce1  jz      short loc_180021CEC
0x180021ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ce8  test    al, al
0x180021cea  jmp     short loc_180021CF4
0x180021cec  call    cs:__imp_IsDebuggerPresent
0x180021cf2  test    eax, eax
0x180021cf4  jz      short loc_180021CFD
0x180021cf6  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180021cfb  jz      short loc_180021D23
0x180021cfd  mov     rax, cs:g_pfnResultLoggingCallback
0x180021d04  test    rax, rax
0x180021d07  jz      short loc_180021D7C
0x180021d09  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180021d10  jnz     short loc_180021D7C
0x180021d12  xor     r8d, r8d
0x180021d15  xor     edx, edx
0x180021d17  lea     rcx, [rsp+14F0h+var_14D0]
0x180021d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d21  jmp     short loc_180021D7C
0x180021d23  mov     rax, cs:g_pfnResultLoggingCallback
0x180021d2a  test    rax, rax
0x180021d2d  jz      short loc_180021D4F
0x180021d2f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180021d36  jnz     short loc_180021D4F
0x180021d38  mov     r8d, 800h
0x180021d3e  lea     rdx, [rbp+13F0h+OutputString]
0x180021d45  lea     rcx, [rsp+14F0h+var_14D0]
0x180021d4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d4f  cmp     [rbp+13F0h+OutputString], r13w
0x180021d57  jnz     short loc_180021D6F
0x180021d59  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180021d5e  mov     edx, 800h; unsigned __int16 *
0x180021d63  lea     rcx, [rbp+13F0h+OutputString]; this
0x180021d6a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180021d6f  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180021d76  call    cs:__imp_OutputDebugStringW
0x180021d7c  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180021d81  jnz     short loc_180021D8C
0x180021d83  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180021d8a  jz      short loc_180021D9E
0x180021d8c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180021d93  test    rax, rax
0x180021d96  jz      short loc_180021D9E
0x180021d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d9d  nop
0x180021d9e  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180021da3  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
