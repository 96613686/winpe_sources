# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140003828`
- end: `0x140003ad3`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `683`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000330c`

## callees

- `0x140003828`
- `0x140006c94`
- `0x14000ab34`
- `0x14000b650`
- `0x14000b9b0`
- `0x14000bc1c`
- `0x1400187b2`
- `0x1400188a0`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400038c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400038c5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003a67`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003a67`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400039cb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400039cb`

## string_xrefs

- `0x1400038cf`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v8; // r14
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  char v16; // bl
  const struct wil::FailureInfo *v17; // rdx
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  __int64 v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  const char *v27; // [rsp+58h] [rbp-A8h]
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

  v8 = g_pfnThrowPlatformException != 0;
  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v9 = wil::details::RecordException((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 0;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v19 = v10;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h";
  v28 = 1819;
  v29 = v9;
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
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && !v8 && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v16 = 1, (v19 & 2) != 0) )
  {
    v16 = 0;
  }
  if ( v8 || v16 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v14);
    if ( v16 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v12);
  if ( v8 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v18, OutputString);
  wil::ThrowResultException((wil *)&v18, v12);
  wil::details::WilFailFast((wil::details *)&v18, v17);
}

```

## disassembly

```asm
0x140003828  push    rbp
0x14000382a  push    rbx
0x14000382b  push    rsi
0x14000382c  push    rdi
0x14000382d  push    r14
0x14000382f  push    r15
0x140003831  lea     rbp, [rsp-13C8h]
0x140003839  mov     eax, 14C8h
0x14000383e  call    _alloca_probe
0x140003843  sub     rsp, rax
0x140003846  mov     rsi, rcx
0x140003849  mov     rdi, [rbp+13F0h+arg_28]
0x140003850  xor     r15d, r15d
0x140003853  cmp     cs:g_pfnThrowPlatformException, r15
0x14000385a  setnz   r14b
0x14000385e  xor     edx, edx; Val
0x140003860  mov     r8d, 98h; Size
0x140003866  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x14000386b  call    memset_0
0x140003870  nop
0x140003871  mov     [rbp+13F0h+OutputString], r15w
0x140003879  mov     [rbp+13F0h+var_1430], r15b
0x14000387d  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x140003884  mov     ecx, [rdx]; this
0x140003886  mov     [rsp+14F0h+var_14C8], ecx
0x14000388a  mov     eax, [rdx+4]
0x14000388d  mov     [rsp+14F0h+var_14C4], eax
0x140003891  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140003896  mov     ebx, eax
0x140003898  mov     dword ptr [rsp+14F0h+var_14D0], r15d
0x14000389d  mov     ecx, r15d
0x1400038a0  lea     eax, [r15+8]
0x1400038a4  cmp     dword ptr [rdx+8], 1
0x1400038a8  cmovz   ecx, eax
0x1400038ab  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1400038af  lea     ecx, [rax-7]
0x1400038b2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400038ba  inc     ecx
0x1400038bc  mov     [rsp+14F0h+var_14C0], ecx
0x1400038c0  mov     [rsp+14F0h+var_14B8], r15
0x1400038c5  call    cs:__imp_GetCurrentThreadId
0x1400038cb  mov     [rsp+14F0h+var_14B0], eax
0x1400038cf  lea     rax, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400038d6  mov     [rsp+14F0h+var_1498], rax
0x1400038db  mov     [rsp+14F0h+var_1490], 71Bh
0x1400038e3  mov     [rsp+14F0h+var_148C], ebx
0x1400038e7  mov     [rsp+14F0h+var_14A8], r15
0x1400038ec  mov     [rsp+14F0h+var_14A0], r15
0x1400038f1  mov     [rbp+13F0h+var_1448], rdi
0x1400038f5  mov     [rbp+13F0h+var_1440], rsi
0x1400038f9  mov     [rsp+14F0h+var_1488], r15
0x1400038fe  xorps   xmm0, xmm0
0x140003901  xor     eax, eax
0x140003903  movups  [rbp+13F0h+var_1468], xmm0
0x140003907  mov     [rbp+13F0h+var_1458], rax
0x14000390b  xorps   xmm1, xmm1
0x14000390e  movups  [rsp+14F0h+var_1480], xmm1
0x140003913  mov     [rbp+13F0h+var_1470], rax
0x140003917  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000391e  test    rax, rax
0x140003921  jz      short loc_14000392E
0x140003923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003928  mov     [rbp+13F0h+var_1450], rax
0x14000392c  jmp     short loc_140003932
0x14000392e  mov     [rbp+13F0h+var_1450], r15
0x140003932  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003939  test    rax, rax
0x14000393c  jz      short loc_140003948
0x14000393e  lea     rcx, [rsp+14F0h+var_14D0]
0x140003943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003948  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000394f  test    rax, rax
0x140003952  jz      short loc_140003968
0x140003954  mov     r8d, 400h
0x14000395a  lea     rdx, [rbp+13F0h+var_1430]
0x14000395e  lea     rcx, [rsp+14F0h+var_14D0]
0x140003963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003968  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000396f  test    rax, rax
0x140003972  jz      short loc_14000397E
0x140003974  lea     rcx, [rsp+14F0h+var_14D0]
0x140003979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000397e  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003985  test    rax, rax
0x140003988  jz      short loc_1400039A0
0x14000398a  test    r14b, r14b
0x14000398d  jnz     short loc_1400039A0
0x14000398f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140003994  jnz     short loc_1400039A0
0x140003996  lea     rcx, [rsp+14F0h+var_14D0]
0x14000399b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400039a0  cmp     [rsp+14F0h+var_14C8], r15d
0x1400039a5  jl      short loc_1400039AD
0x1400039a7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400039ad  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1400039b4  jnz     short loc_1400039D5
0x1400039b6  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400039bd  test    rax, rax
0x1400039c0  jz      short loc_1400039CB
0x1400039c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400039c7  test    al, al
0x1400039c9  jmp     short loc_1400039D3
0x1400039cb  call    cs:__imp_IsDebuggerPresent
0x1400039d1  test    eax, eax
0x1400039d3  jz      short loc_1400039DE
0x1400039d5  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400039da  mov     bl, 1
0x1400039dc  jz      short loc_1400039E1
0x1400039de  mov     bl, r15b
0x1400039e1  test    r14b, r14b
0x1400039e4  jnz     short loc_140003A10
0x1400039e6  test    bl, bl
0x1400039e8  jnz     short loc_140003A10
0x1400039ea  mov     rax, cs:g_pfnResultLoggingCallback
0x1400039f1  test    rax, rax
0x1400039f4  jz      short loc_140003A6D
0x1400039f6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400039fd  jnz     short loc_140003A6D
0x1400039ff  xor     r8d, r8d
0x140003a02  xor     edx, edx
0x140003a04  lea     rcx, [rsp+14F0h+var_14D0]
0x140003a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003a0e  jmp     short loc_140003A6D
0x140003a10  mov     edi, 800h
0x140003a15  mov     rax, cs:g_pfnResultLoggingCallback
0x140003a1c  test    rax, rax
0x140003a1f  jz      short loc_140003A3E
0x140003a21  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140003a28  jnz     short loc_140003A3E
0x140003a2a  mov     r8d, edi
0x140003a2d  lea     rdx, [rbp+13F0h+OutputString]
0x140003a34  lea     rcx, [rsp+14F0h+var_14D0]
0x140003a39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003a3e  cmp     [rbp+13F0h+OutputString], r15w
0x140003a46  jnz     short loc_140003A5C
0x140003a48  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140003a4d  mov     rdx, rdi; unsigned __int16 *
0x140003a50  lea     rcx, [rbp+13F0h+OutputString]; this
0x140003a57  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140003a5c  test    bl, bl
0x140003a5e  jz      short loc_140003A6D
0x140003a60  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140003a67  call    cs:__imp_OutputDebugStringW
0x140003a6d  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140003a72  jnz     short loc_140003A7D
0x140003a74  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x140003a7b  jz      short loc_140003A8F
0x140003a7d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003a84  test    rax, rax
0x140003a87  jz      short loc_140003A8F
0x140003a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003a8e  nop
0x140003a8f  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140003a94  jz      short loc_140003AA1
0x140003a96  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140003a9b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140003aa1  test    r14b, r14b
0x140003aa4  jz      short loc_140003ABE
0x140003aa6  lea     rdx, [rbp+13F0h+OutputString]
0x140003aad  lea     rcx, [rsp+14F0h+var_14D0]
0x140003ab2  mov     rax, cs:g_pfnThrowPlatformException
0x140003ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003abe  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140003ac3  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x140003ac8  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140003acd  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
