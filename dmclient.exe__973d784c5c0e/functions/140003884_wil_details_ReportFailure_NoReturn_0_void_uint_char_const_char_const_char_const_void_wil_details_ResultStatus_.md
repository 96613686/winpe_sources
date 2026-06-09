# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140003884`
- end: `0x140003b41`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `701`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000334c`

## callees

- `0x140003884`
- `0x140006d84`
- `0x14000adbc`
- `0x14000b998`
- `0x14000bd4c`
- `0x14000bfc4`
- `0x1400195e2`
- `0x1400196d0`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003921`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003921`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003acf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003acf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003a2d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003a2d`

## string_xrefs

- `0x140003931`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

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
0x140003884  push    rbp
0x140003886  push    rbx
0x140003887  push    rsi
0x140003888  push    rdi
0x140003889  push    r14
0x14000388b  push    r15
0x14000388d  lea     rbp, [rsp-13C8h]
0x140003895  mov     eax, 14C8h
0x14000389a  call    _alloca_probe
0x14000389f  sub     rsp, rax
0x1400038a2  mov     rsi, rcx
0x1400038a5  mov     rdi, [rbp+13F0h+arg_28]
0x1400038ac  xor     r15d, r15d
0x1400038af  cmp     cs:g_pfnThrowPlatformException, r15
0x1400038b6  setnz   r14b
0x1400038ba  xor     edx, edx; Val
0x1400038bc  mov     r8d, 98h; Size
0x1400038c2  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1400038c7  call    memset_0
0x1400038cc  nop
0x1400038cd  mov     [rbp+13F0h+OutputString], r15w
0x1400038d5  mov     [rbp+13F0h+var_1430], r15b
0x1400038d9  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1400038e0  mov     ecx, [rdx]; this
0x1400038e2  mov     [rsp+14F0h+var_14C8], ecx
0x1400038e6  mov     eax, [rdx+4]
0x1400038e9  mov     [rsp+14F0h+var_14C4], eax
0x1400038ed  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1400038f2  mov     ebx, eax
0x1400038f4  mov     dword ptr [rsp+14F0h+var_14D0], r15d
0x1400038f9  mov     ecx, r15d
0x1400038fc  lea     eax, [r15+8]
0x140003900  cmp     dword ptr [rdx+8], 1
0x140003904  cmovz   ecx, eax
0x140003907  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x14000390b  lea     ecx, [rax-7]
0x14000390e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003916  inc     ecx
0x140003918  mov     [rsp+14F0h+var_14C0], ecx
0x14000391c  mov     [rsp+14F0h+var_14B8], r15
0x140003921  call    cs:__imp_GetCurrentThreadId
0x140003928  nop     dword ptr [rax+rax+00h]
0x14000392d  mov     [rsp+14F0h+var_14B0], eax
0x140003931  lea     rax, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140003938  mov     [rsp+14F0h+var_1498], rax
0x14000393d  mov     [rsp+14F0h+var_1490], 71Bh
0x140003945  mov     [rsp+14F0h+var_148C], ebx
0x140003949  mov     [rsp+14F0h+var_14A8], r15
0x14000394e  mov     [rsp+14F0h+var_14A0], r15
0x140003953  mov     [rbp+13F0h+var_1448], rdi
0x140003957  mov     [rbp+13F0h+var_1440], rsi
0x14000395b  mov     [rsp+14F0h+var_1488], r15
0x140003960  xorps   xmm0, xmm0
0x140003963  xor     eax, eax
0x140003965  movups  [rbp+13F0h+var_1468], xmm0
0x140003969  mov     [rbp+13F0h+var_1458], rax
0x14000396d  xorps   xmm1, xmm1
0x140003970  movups  [rsp+14F0h+var_1480], xmm1
0x140003975  mov     [rbp+13F0h+var_1470], rax
0x140003979  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003980  test    rax, rax
0x140003983  jz      short loc_140003990
0x140003985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000398a  mov     [rbp+13F0h+var_1450], rax
0x14000398e  jmp     short loc_140003994
0x140003990  mov     [rbp+13F0h+var_1450], r15
0x140003994  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000399b  test    rax, rax
0x14000399e  jz      short loc_1400039AA
0x1400039a0  lea     rcx, [rsp+14F0h+var_14D0]
0x1400039a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400039aa  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400039b1  test    rax, rax
0x1400039b4  jz      short loc_1400039CA
0x1400039b6  mov     r8d, 400h
0x1400039bc  lea     rdx, [rbp+13F0h+var_1430]
0x1400039c0  lea     rcx, [rsp+14F0h+var_14D0]
0x1400039c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400039ca  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400039d1  test    rax, rax
0x1400039d4  jz      short loc_1400039E0
0x1400039d6  lea     rcx, [rsp+14F0h+var_14D0]
0x1400039db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400039e0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400039e7  test    rax, rax
0x1400039ea  jz      short loc_140003A02
0x1400039ec  test    r14b, r14b
0x1400039ef  jnz     short loc_140003A02
0x1400039f1  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400039f6  jnz     short loc_140003A02
0x1400039f8  lea     rcx, [rsp+14F0h+var_14D0]
0x1400039fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003a02  cmp     [rsp+14F0h+var_14C8], r15d
0x140003a07  jl      short loc_140003A0F
0x140003a09  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140003a0f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x140003a16  jnz     short loc_140003A3D
0x140003a18  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140003a1f  test    rax, rax
0x140003a22  jz      short loc_140003A2D
0x140003a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003a29  test    al, al
0x140003a2b  jmp     short loc_140003A3B
0x140003a2d  call    cs:__imp_IsDebuggerPresent
0x140003a34  nop     dword ptr [rax+rax+00h]
0x140003a39  test    eax, eax
0x140003a3b  jz      short loc_140003A46
0x140003a3d  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140003a42  mov     bl, 1
0x140003a44  jz      short loc_140003A49
0x140003a46  mov     bl, r15b
0x140003a49  test    r14b, r14b
0x140003a4c  jnz     short loc_140003A78
0x140003a4e  test    bl, bl
0x140003a50  jnz     short loc_140003A78
0x140003a52  mov     rax, cs:g_pfnResultLoggingCallback
0x140003a59  test    rax, rax
0x140003a5c  jz      short loc_140003ADB
0x140003a5e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140003a65  jnz     short loc_140003ADB
0x140003a67  xor     r8d, r8d
0x140003a6a  xor     edx, edx
0x140003a6c  lea     rcx, [rsp+14F0h+var_14D0]
0x140003a71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003a76  jmp     short loc_140003ADB
0x140003a78  mov     edi, 800h
0x140003a7d  mov     rax, cs:g_pfnResultLoggingCallback
0x140003a84  test    rax, rax
0x140003a87  jz      short loc_140003AA6
0x140003a89  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140003a90  jnz     short loc_140003AA6
0x140003a92  mov     r8d, edi
0x140003a95  lea     rdx, [rbp+13F0h+OutputString]
0x140003a9c  lea     rcx, [rsp+14F0h+var_14D0]
0x140003aa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003aa6  cmp     [rbp+13F0h+OutputString], r15w
0x140003aae  jnz     short loc_140003AC4
0x140003ab0  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140003ab5  mov     rdx, rdi; unsigned __int16 *
0x140003ab8  lea     rcx, [rbp+13F0h+OutputString]; this
0x140003abf  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140003ac4  test    bl, bl
0x140003ac6  jz      short loc_140003ADB
0x140003ac8  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140003acf  call    cs:__imp_OutputDebugStringW
0x140003ad6  nop     dword ptr [rax+rax+00h]
0x140003adb  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140003ae0  jnz     short loc_140003AEB
0x140003ae2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x140003ae9  jz      short loc_140003AFD
0x140003aeb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003af2  test    rax, rax
0x140003af5  jz      short loc_140003AFD
0x140003af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003afc  nop
0x140003afd  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140003b02  jz      short loc_140003B0F
0x140003b04  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140003b09  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140003b0f  test    r14b, r14b
0x140003b12  jz      short loc_140003B2C
0x140003b14  lea     rdx, [rbp+13F0h+OutputString]
0x140003b1b  lea     rcx, [rsp+14F0h+var_14D0]
0x140003b20  mov     rax, cs:g_pfnThrowPlatformException
0x140003b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003b2c  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140003b31  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x140003b36  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140003b3b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
