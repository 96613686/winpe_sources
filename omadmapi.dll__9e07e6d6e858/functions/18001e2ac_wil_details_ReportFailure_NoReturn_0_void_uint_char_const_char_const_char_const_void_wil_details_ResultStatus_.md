# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18001e2ac`
- end: `0x18001e569`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `701`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001e230`

## callees

- `0x180003db8`
- `0x180005304`
- `0x1800108e0`
- `0x180013444`
- `0x180013b14`
- `0x180013ce8`
- `0x18001e2ac`
- `0x1800229a0`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e349`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e349`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001e4f7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001e4f7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001e455`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001e455`

## string_xrefs

- `0x18001e359`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
  v27 = "onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h";
  v28 = 5331;
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
0x18001e2ac  push    rbp
0x18001e2ae  push    rbx
0x18001e2af  push    rsi
0x18001e2b0  push    rdi
0x18001e2b1  push    r14
0x18001e2b3  push    r15
0x18001e2b5  lea     rbp, [rsp-13C8h]
0x18001e2bd  mov     eax, 14C8h
0x18001e2c2  call    _alloca_probe
0x18001e2c7  sub     rsp, rax
0x18001e2ca  mov     rsi, rcx
0x18001e2cd  mov     rdi, [rbp+13F0h+arg_28]
0x18001e2d4  xor     r15d, r15d
0x18001e2d7  cmp     cs:g_pfnThrowPlatformException, r15
0x18001e2de  setnz   r14b
0x18001e2e2  xor     edx, edx; Val
0x18001e2e4  mov     r8d, 98h; Size
0x18001e2ea  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18001e2ef  call    memset_0
0x18001e2f4  nop
0x18001e2f5  mov     [rbp+13F0h+OutputString], r15w
0x18001e2fd  mov     [rbp+13F0h+var_1430], r15b
0x18001e301  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18001e308  mov     ecx, [rdx]; this
0x18001e30a  mov     [rsp+14F0h+var_14C8], ecx
0x18001e30e  mov     eax, [rdx+4]
0x18001e311  mov     [rsp+14F0h+var_14C4], eax
0x18001e315  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001e31a  mov     ebx, eax
0x18001e31c  mov     dword ptr [rsp+14F0h+var_14D0], r15d
0x18001e321  mov     ecx, r15d
0x18001e324  lea     eax, [r15+8]
0x18001e328  cmp     dword ptr [rdx+8], 1
0x18001e32c  cmovz   ecx, eax
0x18001e32f  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18001e333  lea     ecx, [rax-7]
0x18001e336  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001e33e  inc     ecx
0x18001e340  mov     [rsp+14F0h+var_14C0], ecx
0x18001e344  mov     [rsp+14F0h+var_14B8], r15
0x18001e349  call    cs:__imp_GetCurrentThreadId
0x18001e350  nop     dword ptr [rax+rax+00h]
0x18001e355  mov     [rsp+14F0h+var_14B0], eax
0x18001e359  lea     rax, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001e360  mov     [rsp+14F0h+var_1498], rax
0x18001e365  mov     [rsp+14F0h+var_1490], 14D3h
0x18001e36d  mov     [rsp+14F0h+var_148C], ebx
0x18001e371  mov     [rsp+14F0h+var_14A8], r15
0x18001e376  mov     [rsp+14F0h+var_14A0], r15
0x18001e37b  mov     [rbp+13F0h+var_1448], rdi
0x18001e37f  mov     [rbp+13F0h+var_1440], rsi
0x18001e383  mov     [rsp+14F0h+var_1488], r15
0x18001e388  xorps   xmm0, xmm0
0x18001e38b  xor     eax, eax
0x18001e38d  movups  [rbp+13F0h+var_1468], xmm0
0x18001e391  mov     [rbp+13F0h+var_1458], rax
0x18001e395  xorps   xmm1, xmm1
0x18001e398  movups  [rsp+14F0h+var_1480], xmm1
0x18001e39d  mov     [rbp+13F0h+var_1470], rax
0x18001e3a1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001e3a8  test    rax, rax
0x18001e3ab  jz      short loc_18001E3B8
0x18001e3ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3b2  mov     [rbp+13F0h+var_1450], rax
0x18001e3b6  jmp     short loc_18001E3BC
0x18001e3b8  mov     [rbp+13F0h+var_1450], r15
0x18001e3bc  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001e3c3  test    rax, rax
0x18001e3c6  jz      short loc_18001E3D2
0x18001e3c8  lea     rcx, [rsp+14F0h+var_14D0]
0x18001e3cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3d2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001e3d9  test    rax, rax
0x18001e3dc  jz      short loc_18001E3F2
0x18001e3de  mov     r8d, 400h
0x18001e3e4  lea     rdx, [rbp+13F0h+var_1430]
0x18001e3e8  lea     rcx, [rsp+14F0h+var_14D0]
0x18001e3ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3f2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001e3f9  test    rax, rax
0x18001e3fc  jz      short loc_18001E408
0x18001e3fe  lea     rcx, [rsp+14F0h+var_14D0]
0x18001e403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e408  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001e40f  test    rax, rax
0x18001e412  jz      short loc_18001E42A
0x18001e414  test    r14b, r14b
0x18001e417  jnz     short loc_18001E42A
0x18001e419  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001e41e  jnz     short loc_18001E42A
0x18001e420  lea     rcx, [rsp+14F0h+var_14D0]
0x18001e425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e42a  cmp     [rsp+14F0h+var_14C8], r15d
0x18001e42f  jl      short loc_18001E437
0x18001e431  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001e437  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18001e43e  jnz     short loc_18001E465
0x18001e440  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001e447  test    rax, rax
0x18001e44a  jz      short loc_18001E455
0x18001e44c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e451  test    al, al
0x18001e453  jmp     short loc_18001E463
0x18001e455  call    cs:__imp_IsDebuggerPresent
0x18001e45c  nop     dword ptr [rax+rax+00h]
0x18001e461  test    eax, eax
0x18001e463  jz      short loc_18001E46E
0x18001e465  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001e46a  mov     bl, 1
0x18001e46c  jz      short loc_18001E471
0x18001e46e  mov     bl, r15b
0x18001e471  test    r14b, r14b
0x18001e474  jnz     short loc_18001E4A0
0x18001e476  test    bl, bl
0x18001e478  jnz     short loc_18001E4A0
0x18001e47a  mov     rax, cs:g_pfnResultLoggingCallback
0x18001e481  test    rax, rax
0x18001e484  jz      short loc_18001E503
0x18001e486  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001e48d  jnz     short loc_18001E503
0x18001e48f  xor     r8d, r8d
0x18001e492  xor     edx, edx
0x18001e494  lea     rcx, [rsp+14F0h+var_14D0]
0x18001e499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e49e  jmp     short loc_18001E503
0x18001e4a0  mov     edi, 800h
0x18001e4a5  mov     rax, cs:g_pfnResultLoggingCallback
0x18001e4ac  test    rax, rax
0x18001e4af  jz      short loc_18001E4CE
0x18001e4b1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001e4b8  jnz     short loc_18001E4CE
0x18001e4ba  mov     r8d, edi
0x18001e4bd  lea     rdx, [rbp+13F0h+OutputString]
0x18001e4c4  lea     rcx, [rsp+14F0h+var_14D0]
0x18001e4c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4ce  cmp     [rbp+13F0h+OutputString], r15w
0x18001e4d6  jnz     short loc_18001E4EC
0x18001e4d8  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18001e4dd  mov     rdx, rdi; unsigned __int16 *
0x18001e4e0  lea     rcx, [rbp+13F0h+OutputString]; this
0x18001e4e7  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001e4ec  test    bl, bl
0x18001e4ee  jz      short loc_18001E503
0x18001e4f0  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18001e4f7  call    cs:__imp_OutputDebugStringW
0x18001e4fe  nop     dword ptr [rax+rax+00h]
0x18001e503  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18001e508  jnz     short loc_18001E513
0x18001e50a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18001e511  jz      short loc_18001E525
0x18001e513  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001e51a  test    rax, rax
0x18001e51d  jz      short loc_18001E525
0x18001e51f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e524  nop
0x18001e525  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18001e52a  jz      short loc_18001E537
0x18001e52c  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001e531  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18001e537  test    r14b, r14b
0x18001e53a  jz      short loc_18001E554
0x18001e53c  lea     rdx, [rbp+13F0h+OutputString]
0x18001e543  lea     rcx, [rsp+14F0h+var_14D0]
0x18001e548  mov     rax, cs:g_pfnThrowPlatformException
0x18001e54f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e554  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001e559  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18001e55e  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001e563  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
