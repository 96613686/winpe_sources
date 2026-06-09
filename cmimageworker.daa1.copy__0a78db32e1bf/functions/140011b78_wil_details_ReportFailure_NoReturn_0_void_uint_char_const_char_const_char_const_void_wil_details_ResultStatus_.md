# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140011b78`
- end: `0x140011e36`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `702`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400119a0`

## callees

- `0x140002b2c`
- `0x140004b34`
- `0x1400069a0`
- `0x140008a18`
- `0x140008dcc`
- `0x140008f64`
- `0x140011b78`
- `0x14002e860`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140011c21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140011c21`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140011dc4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140011dc4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140011d22`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140011d22`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v10; // r12
  int v11; // ebx
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  char v18; // bl
  const struct wil::FailureInfo *v19; // rdx
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
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

  v10 = g_pfnThrowPlatformException != 0;
  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v22 = *a7;
  v23 = a7[1];
  v11 = wil::details::RecordException((wil::details *)(unsigned int)v22, (int)a7);
  v20 = 0;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v21 = v12;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v25 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v30 = a2;
  v31 = v11;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && !v10 && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v18 = 1, (v21 & 2) != 0) )
  {
    v18 = 0;
  }
  if ( v10 || v18 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v20, v16);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0, v16);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v14);
  if ( v10 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v20, OutputString);
  wil::ThrowResultException((wil *)&v20, v14);
  wil::details::WilFailFast((wil::details *)&v20, v19);
}

```

## disassembly

```asm
0x140011b78  mov     [rsp-8+arg_18], rbx
0x140011b7d  push    rbp
0x140011b7e  push    rsi
0x140011b7f  push    rdi
0x140011b80  push    r12
0x140011b82  push    r13
0x140011b84  push    r14
0x140011b86  push    r15
0x140011b88  lea     rbp, [rsp-13C0h]
0x140011b90  mov     eax, 14C0h
0x140011b95  call    _alloca_probe
0x140011b9a  sub     rsp, rax
0x140011b9d  mov     r14, r8
0x140011ba0  mov     esi, edx
0x140011ba2  mov     r15, rcx
0x140011ba5  mov     rdi, [rbp+13F0h+arg_28]
0x140011bac  xor     r13d, r13d
0x140011baf  cmp     cs:g_pfnThrowPlatformException, r13
0x140011bb6  setnz   r12b
0x140011bba  xor     edx, edx; Val
0x140011bbc  mov     r8d, 98h; Size
0x140011bc2  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140011bc7  call    memset_0
0x140011bcc  nop
0x140011bcd  mov     [rbp+13F0h+OutputString], r13w
0x140011bd5  mov     [rbp+13F0h+var_1430], r13b
0x140011bd9  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x140011be0  mov     ecx, [rdx]; this
0x140011be2  mov     [rsp+14F0h+var_14C8], ecx
0x140011be6  mov     eax, [rdx+4]
0x140011be9  mov     [rsp+14F0h+var_14C4], eax
0x140011bed  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140011bf2  mov     ebx, eax
0x140011bf4  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x140011bf9  mov     ecx, r13d
0x140011bfc  lea     eax, [r13+8]
0x140011c00  cmp     dword ptr [rdx+8], 1
0x140011c04  cmovz   ecx, eax
0x140011c07  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140011c0b  lea     ecx, [rax-7]
0x140011c0e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140011c16  inc     ecx
0x140011c18  mov     [rsp+14F0h+var_14C0], ecx
0x140011c1c  mov     [rsp+14F0h+var_14B8], r13
0x140011c21  call    cs:__imp_GetCurrentThreadId
0x140011c28  nop     dword ptr [rax+rax+00h]
0x140011c2d  mov     [rsp+14F0h+var_14B0], eax
0x140011c31  mov     [rsp+14F0h+var_1498], r14
0x140011c36  mov     [rsp+14F0h+var_1490], esi
0x140011c3a  mov     [rsp+14F0h+var_148C], ebx
0x140011c3e  mov     [rsp+14F0h+var_14A8], r13
0x140011c43  mov     [rsp+14F0h+var_14A0], r13
0x140011c48  mov     [rbp+13F0h+var_1448], rdi
0x140011c4c  mov     [rbp+13F0h+var_1440], r15
0x140011c50  mov     [rsp+14F0h+var_1488], r13
0x140011c55  xorps   xmm0, xmm0
0x140011c58  xor     eax, eax
0x140011c5a  movups  [rbp+13F0h+var_1468], xmm0
0x140011c5e  mov     [rbp+13F0h+var_1458], rax
0x140011c62  xorps   xmm1, xmm1
0x140011c65  movups  [rsp+14F0h+var_1480], xmm1
0x140011c6a  mov     [rbp+13F0h+var_1470], rax
0x140011c6e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140011c75  test    rax, rax
0x140011c78  jz      short loc_140011C85
0x140011c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011c7f  mov     [rbp+13F0h+var_1450], rax
0x140011c83  jmp     short loc_140011C89
0x140011c85  mov     [rbp+13F0h+var_1450], r13
0x140011c89  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140011c90  test    rax, rax
0x140011c93  jz      short loc_140011C9F
0x140011c95  lea     rcx, [rsp+14F0h+var_14D0]
0x140011c9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011c9f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140011ca6  test    rax, rax
0x140011ca9  jz      short loc_140011CBF
0x140011cab  mov     r8d, 400h
0x140011cb1  lea     rdx, [rbp+13F0h+var_1430]
0x140011cb5  lea     rcx, [rsp+14F0h+var_14D0]
0x140011cba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011cbf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140011cc6  test    rax, rax
0x140011cc9  jz      short loc_140011CD5
0x140011ccb  lea     rcx, [rsp+14F0h+var_14D0]
0x140011cd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011cd5  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140011cdc  test    rax, rax
0x140011cdf  jz      short loc_140011CF7
0x140011ce1  test    r12b, r12b
0x140011ce4  jnz     short loc_140011CF7
0x140011ce6  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140011ceb  jnz     short loc_140011CF7
0x140011ced  lea     rcx, [rsp+14F0h+var_14D0]
0x140011cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011cf7  cmp     [rsp+14F0h+var_14C8], r13d
0x140011cfc  jl      short loc_140011D04
0x140011cfe  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140011d04  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140011d0b  jnz     short loc_140011D32
0x140011d0d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140011d14  test    rax, rax
0x140011d17  jz      short loc_140011D22
0x140011d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011d1e  test    al, al
0x140011d20  jmp     short loc_140011D30
0x140011d22  call    cs:__imp_IsDebuggerPresent
0x140011d29  nop     dword ptr [rax+rax+00h]
0x140011d2e  test    eax, eax
0x140011d30  jz      short loc_140011D3B
0x140011d32  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140011d37  mov     bl, 1
0x140011d39  jz      short loc_140011D3E
0x140011d3b  mov     bl, r13b
0x140011d3e  test    r12b, r12b
0x140011d41  jnz     short loc_140011D6D
0x140011d43  test    bl, bl
0x140011d45  jnz     short loc_140011D6D
0x140011d47  mov     rax, cs:g_pfnResultLoggingCallback
0x140011d4e  test    rax, rax
0x140011d51  jz      short loc_140011DD0
0x140011d53  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140011d5a  jnz     short loc_140011DD0
0x140011d5c  xor     r8d, r8d
0x140011d5f  xor     edx, edx
0x140011d61  lea     rcx, [rsp+14F0h+var_14D0]
0x140011d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011d6b  jmp     short loc_140011DD0
0x140011d6d  mov     edi, 800h
0x140011d72  mov     rax, cs:g_pfnResultLoggingCallback
0x140011d79  test    rax, rax
0x140011d7c  jz      short loc_140011D9B
0x140011d7e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140011d85  jnz     short loc_140011D9B
0x140011d87  mov     r8d, edi
0x140011d8a  lea     rdx, [rbp+13F0h+OutputString]
0x140011d91  lea     rcx, [rsp+14F0h+var_14D0]
0x140011d96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011d9b  cmp     [rbp+13F0h+OutputString], r13w
0x140011da3  jnz     short loc_140011DB9
0x140011da5  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140011daa  mov     rdx, rdi; unsigned __int16 *
0x140011dad  lea     rcx, [rbp+13F0h+OutputString]; this
0x140011db4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140011db9  test    bl, bl
0x140011dbb  jz      short loc_140011DD0
0x140011dbd  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140011dc4  call    cs:__imp_OutputDebugStringW
0x140011dcb  nop     dword ptr [rax+rax+00h]
0x140011dd0  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140011dd5  jnz     short loc_140011DE0
0x140011dd7  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140011dde  jz      short loc_140011DF2
0x140011de0  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140011de7  test    rax, rax
0x140011dea  jz      short loc_140011DF2
0x140011dec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011df1  nop
0x140011df2  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140011df7  jz      short loc_140011E04
0x140011df9  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140011dfe  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140011e04  test    r12b, r12b
0x140011e07  jz      short loc_140011E21
0x140011e09  lea     rdx, [rbp+13F0h+OutputString]
0x140011e10  lea     rcx, [rsp+14F0h+var_14D0]
0x140011e15  mov     rax, cs:g_pfnThrowPlatformException
0x140011e1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011e21  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140011e26  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x140011e2b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140011e30  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
