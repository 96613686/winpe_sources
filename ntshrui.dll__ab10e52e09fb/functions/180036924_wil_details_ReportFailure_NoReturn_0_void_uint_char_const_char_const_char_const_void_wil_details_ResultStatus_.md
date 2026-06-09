# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180036924`
- end: `0x180036bcf`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `683`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180036710`

## callees

- `0x180026394`
- `0x1800292ec`
- `0x180029b3c`
- `0x18002a308`
- `0x18002a3d8`
- `0x18002a544`
- `0x180036924`
- `0x180074b70`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800369c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800369c1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180036ac7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180036ac7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180036b63`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180036b63`

## string_xrefs

- `0x1800369cb`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  v27 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h";
  v28 = 7358;
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
0x180036924  push    rbp
0x180036926  push    rbx
0x180036927  push    rsi
0x180036928  push    rdi
0x180036929  push    r14
0x18003692b  push    r15
0x18003692d  lea     rbp, [rsp-13C8h]
0x180036935  mov     eax, 14C8h
0x18003693a  call    _alloca_probe
0x18003693f  sub     rsp, rax
0x180036942  mov     rsi, rcx
0x180036945  mov     rdi, [rbp+13F0h+arg_28]
0x18003694c  xor     r15d, r15d
0x18003694f  cmp     cs:g_pfnThrowPlatformException, r15
0x180036956  setnz   r14b
0x18003695a  xor     edx, edx; Val
0x18003695c  mov     r8d, 98h; Size
0x180036962  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180036967  call    memset_0
0x18003696c  nop
0x18003696d  mov     [rbp+13F0h+OutputString], r15w
0x180036975  mov     [rbp+13F0h+var_1430], r15b
0x180036979  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180036980  mov     ecx, [rdx]; this
0x180036982  mov     [rsp+14F0h+var_14C8], ecx
0x180036986  mov     eax, [rdx+4]
0x180036989  mov     [rsp+14F0h+var_14C4], eax
0x18003698d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180036992  mov     ebx, eax
0x180036994  mov     dword ptr [rsp+14F0h+var_14D0], r15d
0x180036999  mov     ecx, r15d
0x18003699c  lea     eax, [r15+8]
0x1800369a0  cmp     dword ptr [rdx+8], 1
0x1800369a4  cmovz   ecx, eax
0x1800369a7  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800369ab  lea     ecx, [rax-7]
0x1800369ae  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800369b6  inc     ecx
0x1800369b8  mov     [rsp+14F0h+var_14C0], ecx
0x1800369bc  mov     [rsp+14F0h+var_14B8], r15
0x1800369c1  call    cs:__imp_GetCurrentThreadId
0x1800369c7  mov     [rsp+14F0h+var_14B0], eax
0x1800369cb  lea     rax, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800369d2  mov     [rsp+14F0h+var_1498], rax
0x1800369d7  mov     [rsp+14F0h+var_1490], 1CBEh
0x1800369df  mov     [rsp+14F0h+var_148C], ebx
0x1800369e3  mov     [rsp+14F0h+var_14A8], r15
0x1800369e8  mov     [rsp+14F0h+var_14A0], r15
0x1800369ed  mov     [rbp+13F0h+var_1448], rdi
0x1800369f1  mov     [rbp+13F0h+var_1440], rsi
0x1800369f5  mov     [rsp+14F0h+var_1488], r15
0x1800369fa  xorps   xmm0, xmm0
0x1800369fd  xor     eax, eax
0x1800369ff  movups  [rbp+13F0h+var_1468], xmm0
0x180036a03  mov     [rbp+13F0h+var_1458], rax
0x180036a07  xorps   xmm1, xmm1
0x180036a0a  movups  [rsp+14F0h+var_1480], xmm1
0x180036a0f  mov     [rbp+13F0h+var_1470], rax
0x180036a13  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180036a1a  test    rax, rax
0x180036a1d  jz      short loc_180036A2A
0x180036a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a24  mov     [rbp+13F0h+var_1450], rax
0x180036a28  jmp     short loc_180036A2E
0x180036a2a  mov     [rbp+13F0h+var_1450], r15
0x180036a2e  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180036a35  test    rax, rax
0x180036a38  jz      short loc_180036A44
0x180036a3a  lea     rcx, [rsp+14F0h+var_14D0]
0x180036a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a44  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180036a4b  test    rax, rax
0x180036a4e  jz      short loc_180036A64
0x180036a50  mov     r8d, 400h
0x180036a56  lea     rdx, [rbp+13F0h+var_1430]
0x180036a5a  lea     rcx, [rsp+14F0h+var_14D0]
0x180036a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a64  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180036a6b  test    rax, rax
0x180036a6e  jz      short loc_180036A7A
0x180036a70  lea     rcx, [rsp+14F0h+var_14D0]
0x180036a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a7a  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180036a81  test    rax, rax
0x180036a84  jz      short loc_180036A9C
0x180036a86  test    r14b, r14b
0x180036a89  jnz     short loc_180036A9C
0x180036a8b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180036a90  jnz     short loc_180036A9C
0x180036a92  lea     rcx, [rsp+14F0h+var_14D0]
0x180036a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a9c  cmp     [rsp+14F0h+var_14C8], r15d
0x180036aa1  jl      short loc_180036AA9
0x180036aa3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180036aa9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180036ab0  jnz     short loc_180036AD1
0x180036ab2  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180036ab9  test    rax, rax
0x180036abc  jz      short loc_180036AC7
0x180036abe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ac3  test    al, al
0x180036ac5  jmp     short loc_180036ACF
0x180036ac7  call    cs:__imp_IsDebuggerPresent
0x180036acd  test    eax, eax
0x180036acf  jz      short loc_180036ADA
0x180036ad1  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180036ad6  mov     bl, 1
0x180036ad8  jz      short loc_180036ADD
0x180036ada  mov     bl, r15b
0x180036add  test    r14b, r14b
0x180036ae0  jnz     short loc_180036B0C
0x180036ae2  test    bl, bl
0x180036ae4  jnz     short loc_180036B0C
0x180036ae6  mov     rax, cs:g_pfnResultLoggingCallback
0x180036aed  test    rax, rax
0x180036af0  jz      short loc_180036B69
0x180036af2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180036af9  jnz     short loc_180036B69
0x180036afb  xor     r8d, r8d
0x180036afe  xor     edx, edx
0x180036b00  lea     rcx, [rsp+14F0h+var_14D0]
0x180036b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b0a  jmp     short loc_180036B69
0x180036b0c  mov     edi, 800h
0x180036b11  mov     rax, cs:g_pfnResultLoggingCallback
0x180036b18  test    rax, rax
0x180036b1b  jz      short loc_180036B3A
0x180036b1d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180036b24  jnz     short loc_180036B3A
0x180036b26  mov     r8d, edi
0x180036b29  lea     rdx, [rbp+13F0h+OutputString]
0x180036b30  lea     rcx, [rsp+14F0h+var_14D0]
0x180036b35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b3a  cmp     [rbp+13F0h+OutputString], r15w
0x180036b42  jnz     short loc_180036B58
0x180036b44  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180036b49  mov     rdx, rdi; unsigned __int16 *
0x180036b4c  lea     rcx, [rbp+13F0h+OutputString]; this
0x180036b53  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180036b58  test    bl, bl
0x180036b5a  jz      short loc_180036B69
0x180036b5c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180036b63  call    cs:__imp_OutputDebugStringW
0x180036b69  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180036b6e  jnz     short loc_180036B79
0x180036b70  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180036b77  jz      short loc_180036B8B
0x180036b79  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180036b80  test    rax, rax
0x180036b83  jz      short loc_180036B8B
0x180036b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b8a  nop
0x180036b8b  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180036b90  jz      short loc_180036B9D
0x180036b92  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180036b97  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180036b9d  test    r14b, r14b
0x180036ba0  jz      short loc_180036BBA
0x180036ba2  lea     rdx, [rbp+13F0h+OutputString]
0x180036ba9  lea     rcx, [rsp+14F0h+var_14D0]
0x180036bae  mov     rax, cs:g_pfnThrowPlatformException
0x180036bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036bba  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180036bbf  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180036bc4  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180036bc9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
