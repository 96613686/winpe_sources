# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180003770`
- end: `0x180003a35`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800030ac`

## callees

- `0x180002062`
- `0x180003770`
- `0x180004e44`
- `0x180006674`
- `0x18000746c`
- `0x1800077d0`
- `0x1800078ac`
- `0x18000ce90`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003831`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003831`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800039c9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800039c9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000392d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000392d`

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
        int *a7,
        _WORD *a8)
{
  bool v11; // di
  int v12; // r12d
  int v13; // ecx
  __int64 v14; // rdx
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  char v19; // bl
  const struct wil::FailureInfo *v20; // rdx
  int v21; // [rsp+20h] [rbp-E0h] BYREF
  int v22; // [rsp+24h] [rbp-DCh]
  int v23; // [rsp+28h] [rbp-D8h]
  int v24; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v25; // [rsp+30h] [rbp-D0h]
  _WORD *v26; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v28; // [rsp+48h] [rbp-B8h]
  __int64 v29; // [rsp+50h] [rbp-B0h]
  __int64 v30; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+60h] [rbp-A0h]
  int v32; // [rsp+64h] [rbp-9Ch]
  __int64 v33; // [rsp+68h] [rbp-98h]
  __int128 v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+80h] [rbp-80h]
  __int128 v36; // [rsp+88h] [rbp-78h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v39; // [rsp+A8h] [rbp-58h]
  __int64 v40; // [rsp+B0h] [rbp-50h]
  char v41[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v11 = g_pfnThrowPlatformException != 0;
  memset_0(&v21, 0, 0x98u);
  OutputString[0] = 0;
  v41[0] = 0;
  v23 = *a7;
  v24 = a7[1];
  v12 = wil::details::RecordException((wil::details *)(unsigned int)v23, (int)a7);
  v21 = 0;
  v13 = 0;
  if ( *(_DWORD *)(v14 + 8) == 1 )
    v13 = 8;
  v22 = v13;
  v25 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v18 = *a8 == 0, v26 = a8, v18) )
    v26 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v30 = a3;
  v31 = a2;
  v32 = v12;
  v28 = 0;
  v29 = 0;
  v39 = a6;
  v40 = a1;
  v33 = 0;
  v36 = 0;
  v37 = 0;
  v34 = 0;
  v35 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v21);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v21, v41, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v21);
  if ( wil::details::g_pfnOriginateCallback && !v11 && (v22 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v21);
  if ( v23 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v19 = 1, (v22 & 2) != 0) )
  {
    v19 = 0;
  }
  if ( v11 || v19 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v21, OutputString, 2048, v17);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v21, v17);
    if ( v19 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v21, 0, 0, v17);
  }
  if ( ((v22 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v22 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v21, v15);
  if ( v11 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v21, OutputString);
  wil::ThrowResultException((wil *)&v21, v15);
  wil::details::WilFailFast((wil::details *)&v21, v20);
}

```

## disassembly

```asm
0x180003770  mov     [rsp-8+arg_18], rbx
0x180003775  push    rbp
0x180003776  push    rsi
0x180003777  push    rdi
0x180003778  push    r12
0x18000377a  push    r13
0x18000377c  push    r14
0x18000377e  push    r15
0x180003780  lea     rbp, [rsp-13C0h]
0x180003788  mov     eax, 14C0h
0x18000378d  call    _alloca_probe
0x180003792  sub     rsp, rax
0x180003795  mov     r14, r8
0x180003798  mov     esi, edx
0x18000379a  mov     rbx, rcx
0x18000379d  mov     r15, [rbp+13F0h+arg_28]
0x1800037a4  xor     r13d, r13d
0x1800037a7  cmp     cs:g_pfnThrowPlatformException, r13
0x1800037ae  setnz   dil
0x1800037b2  xor     edx, edx; Val
0x1800037b4  mov     r8d, 98h; Size
0x1800037ba  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800037bf  call    memset_0
0x1800037c4  nop
0x1800037c5  mov     [rbp+13F0h+OutputString], r13w
0x1800037cd  mov     [rbp+13F0h+var_1430], r13b
0x1800037d1  mov     rdx, [rbp+13F0h+arg_30]; int
0x1800037d8  mov     ecx, [rdx]; this
0x1800037da  mov     [rsp+14F0h+var_14C8], ecx
0x1800037de  mov     eax, [rdx+4]
0x1800037e1  mov     [rsp+14F0h+var_14C4], eax
0x1800037e5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800037ea  mov     r12d, eax
0x1800037ed  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x1800037f2  mov     ecx, r13d
0x1800037f5  lea     eax, [r13+8]
0x1800037f9  cmp     dword ptr [rdx+8], 1
0x1800037fd  cmovz   ecx, eax
0x180003800  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003804  lea     ecx, [rax-7]
0x180003807  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000380f  inc     ecx
0x180003811  mov     [rsp+14F0h+var_14C0], ecx
0x180003815  mov     rcx, [rbp+13F0h+arg_38]
0x18000381c  test    rcx, rcx
0x18000381f  jz      short loc_18000382C
0x180003821  cmp     [rcx], r13w
0x180003825  mov     [rsp+14F0h+var_14B8], rcx
0x18000382a  jnz     short loc_180003831
0x18000382c  mov     [rsp+14F0h+var_14B8], r13
0x180003831  call    cs:__imp_GetCurrentThreadId
0x180003837  mov     [rsp+14F0h+var_14B0], eax
0x18000383b  mov     [rsp+14F0h+var_1498], r14
0x180003840  mov     [rsp+14F0h+var_1490], esi
0x180003844  mov     [rsp+14F0h+var_148C], r12d
0x180003849  mov     [rsp+14F0h+var_14A8], r13
0x18000384e  mov     [rsp+14F0h+var_14A0], r13
0x180003853  mov     [rbp+13F0h+var_1448], r15
0x180003857  mov     [rbp+13F0h+var_1440], rbx
0x18000385b  mov     [rsp+14F0h+var_1488], r13
0x180003860  xorps   xmm0, xmm0
0x180003863  xor     eax, eax
0x180003865  movups  [rbp+13F0h+var_1468], xmm0
0x180003869  mov     [rbp+13F0h+var_1458], rax
0x18000386d  xorps   xmm1, xmm1
0x180003870  movups  [rsp+14F0h+var_1480], xmm1
0x180003875  mov     [rbp+13F0h+var_1470], rax
0x180003879  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003880  test    rax, rax
0x180003883  jz      short loc_180003890
0x180003885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000388a  mov     [rbp+13F0h+var_1450], rax
0x18000388e  jmp     short loc_180003894
0x180003890  mov     [rbp+13F0h+var_1450], r13
0x180003894  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000389b  test    rax, rax
0x18000389e  jz      short loc_1800038AA
0x1800038a0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800038a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038aa  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800038b1  test    rax, rax
0x1800038b4  jz      short loc_1800038CA
0x1800038b6  mov     r8d, 400h
0x1800038bc  lea     rdx, [rbp+13F0h+var_1430]
0x1800038c0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800038c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038ca  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800038d1  test    rax, rax
0x1800038d4  jz      short loc_1800038E0
0x1800038d6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800038db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038e0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800038e7  test    rax, rax
0x1800038ea  jz      short loc_180003902
0x1800038ec  test    dil, dil
0x1800038ef  jnz     short loc_180003902
0x1800038f1  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800038f6  jnz     short loc_180003902
0x1800038f8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800038fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003902  cmp     [rsp+14F0h+var_14C8], r13d
0x180003907  jl      short loc_18000390F
0x180003909  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000390f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180003916  jnz     short loc_180003937
0x180003918  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000391f  test    rax, rax
0x180003922  jz      short loc_18000392D
0x180003924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003929  test    al, al
0x18000392b  jmp     short loc_180003935
0x18000392d  call    cs:__imp_IsDebuggerPresent
0x180003933  test    eax, eax
0x180003935  jz      short loc_180003940
0x180003937  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000393c  mov     bl, 1
0x18000393e  jz      short loc_180003943
0x180003940  mov     bl, r13b
0x180003943  test    dil, dil
0x180003946  jnz     short loc_180003972
0x180003948  test    bl, bl
0x18000394a  jnz     short loc_180003972
0x18000394c  mov     rax, cs:g_pfnResultLoggingCallback
0x180003953  test    rax, rax
0x180003956  jz      short loc_1800039CF
0x180003958  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000395f  jnz     short loc_1800039CF
0x180003961  xor     r8d, r8d
0x180003964  xor     edx, edx
0x180003966  lea     rcx, [rsp+14F0h+var_14D0]
0x18000396b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003970  jmp     short loc_1800039CF
0x180003972  mov     esi, 800h
0x180003977  mov     rax, cs:g_pfnResultLoggingCallback
0x18000397e  test    rax, rax
0x180003981  jz      short loc_1800039A0
0x180003983  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000398a  jnz     short loc_1800039A0
0x18000398c  mov     r8d, esi
0x18000398f  lea     rdx, [rbp+13F0h+OutputString]
0x180003996  lea     rcx, [rsp+14F0h+var_14D0]
0x18000399b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039a0  cmp     [rbp+13F0h+OutputString], r13w
0x1800039a8  jnz     short loc_1800039BE
0x1800039aa  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800039af  mov     rdx, rsi; unsigned __int16 *
0x1800039b2  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800039b9  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800039be  test    bl, bl
0x1800039c0  jz      short loc_1800039CF
0x1800039c2  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800039c9  call    cs:__imp_OutputDebugStringW
0x1800039cf  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800039d4  jnz     short loc_1800039DF
0x1800039d6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800039dd  jz      short loc_1800039F1
0x1800039df  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800039e6  test    rax, rax
0x1800039e9  jz      short loc_1800039F1
0x1800039eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039f0  nop
0x1800039f1  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800039f6  jz      short loc_180003A03
0x1800039f8  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800039fd  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003a03  test    dil, dil
0x180003a06  jz      short loc_180003A20
0x180003a08  lea     rdx, [rbp+13F0h+OutputString]
0x180003a0f  lea     rcx, [rsp+14F0h+var_14D0]
0x180003a14  mov     rax, cs:g_pfnThrowPlatformException
0x180003a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a20  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003a25  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180003a2a  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003a2f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
