# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140003e8c`
- end: `0x140004151`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140003710`

## callees

- `0x140003168`
- `0x140003e8c`
- `0x1400070c4`
- `0x14000884c`
- `0x14000a634`
- `0x14000ace0`
- `0x14000af58`
- `0x1400130e0`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003f4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003f4d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004049`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004049`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400040e5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400040e5`

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
      g_pfnResultLoggingCallback(&v21, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v21, v17);
    if ( v19 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v21, 0, 0);
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
0x140003e8c  mov     [rsp-8+arg_18], rbx
0x140003e91  push    rbp
0x140003e92  push    rsi
0x140003e93  push    rdi
0x140003e94  push    r12
0x140003e96  push    r13
0x140003e98  push    r14
0x140003e9a  push    r15
0x140003e9c  lea     rbp, [rsp-13C0h]
0x140003ea4  mov     eax, 14C0h
0x140003ea9  call    _alloca_probe
0x140003eae  sub     rsp, rax
0x140003eb1  mov     r14, r8
0x140003eb4  mov     esi, edx
0x140003eb6  mov     rbx, rcx
0x140003eb9  mov     r15, [rbp+13F0h+arg_28]
0x140003ec0  xor     r13d, r13d
0x140003ec3  cmp     cs:g_pfnThrowPlatformException, r13
0x140003eca  setnz   dil
0x140003ece  xor     edx, edx; Val
0x140003ed0  mov     r8d, 98h; Size
0x140003ed6  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140003edb  call    memset_0
0x140003ee0  nop
0x140003ee1  mov     [rbp+13F0h+OutputString], r13w
0x140003ee9  mov     [rbp+13F0h+var_1430], r13b
0x140003eed  mov     rdx, [rbp+13F0h+arg_30]; int
0x140003ef4  mov     ecx, [rdx]; this
0x140003ef6  mov     [rsp+14F0h+var_14C8], ecx
0x140003efa  mov     eax, [rdx+4]
0x140003efd  mov     [rsp+14F0h+var_14C4], eax
0x140003f01  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140003f06  mov     r12d, eax
0x140003f09  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x140003f0e  mov     ecx, r13d
0x140003f11  lea     eax, [r13+8]
0x140003f15  cmp     dword ptr [rdx+8], 1
0x140003f19  cmovz   ecx, eax
0x140003f1c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140003f20  lea     ecx, [rax-7]
0x140003f23  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003f2b  inc     ecx
0x140003f2d  mov     [rsp+14F0h+var_14C0], ecx
0x140003f31  mov     rcx, [rbp+13F0h+arg_38]
0x140003f38  test    rcx, rcx
0x140003f3b  jz      short loc_140003F48
0x140003f3d  cmp     [rcx], r13w
0x140003f41  mov     [rsp+14F0h+var_14B8], rcx
0x140003f46  jnz     short loc_140003F4D
0x140003f48  mov     [rsp+14F0h+var_14B8], r13
0x140003f4d  call    cs:__imp_GetCurrentThreadId
0x140003f53  mov     [rsp+14F0h+var_14B0], eax
0x140003f57  mov     [rsp+14F0h+var_1498], r14
0x140003f5c  mov     [rsp+14F0h+var_1490], esi
0x140003f60  mov     [rsp+14F0h+var_148C], r12d
0x140003f65  mov     [rsp+14F0h+var_14A8], r13
0x140003f6a  mov     [rsp+14F0h+var_14A0], r13
0x140003f6f  mov     [rbp+13F0h+var_1448], r15
0x140003f73  mov     [rbp+13F0h+var_1440], rbx
0x140003f77  mov     [rsp+14F0h+var_1488], r13
0x140003f7c  xorps   xmm0, xmm0
0x140003f7f  xor     eax, eax
0x140003f81  movups  [rbp+13F0h+var_1468], xmm0
0x140003f85  mov     [rbp+13F0h+var_1458], rax
0x140003f89  xorps   xmm1, xmm1
0x140003f8c  movups  [rsp+14F0h+var_1480], xmm1
0x140003f91  mov     [rbp+13F0h+var_1470], rax
0x140003f95  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003f9c  test    rax, rax
0x140003f9f  jz      short loc_140003FAC
0x140003fa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003fa6  mov     [rbp+13F0h+var_1450], rax
0x140003faa  jmp     short loc_140003FB0
0x140003fac  mov     [rbp+13F0h+var_1450], r13
0x140003fb0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003fb7  test    rax, rax
0x140003fba  jz      short loc_140003FC6
0x140003fbc  lea     rcx, [rsp+14F0h+var_14D0]
0x140003fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003fc6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140003fcd  test    rax, rax
0x140003fd0  jz      short loc_140003FE6
0x140003fd2  mov     r8d, 400h
0x140003fd8  lea     rdx, [rbp+13F0h+var_1430]
0x140003fdc  lea     rcx, [rsp+14F0h+var_14D0]
0x140003fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003fe6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003fed  test    rax, rax
0x140003ff0  jz      short loc_140003FFC
0x140003ff2  lea     rcx, [rsp+14F0h+var_14D0]
0x140003ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003ffc  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004003  test    rax, rax
0x140004006  jz      short loc_14000401E
0x140004008  test    dil, dil
0x14000400b  jnz     short loc_14000401E
0x14000400d  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140004012  jnz     short loc_14000401E
0x140004014  lea     rcx, [rsp+14F0h+var_14D0]
0x140004019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000401e  cmp     [rsp+14F0h+var_14C8], r13d
0x140004023  jl      short loc_14000402B
0x140004025  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000402b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140004032  jnz     short loc_140004053
0x140004034  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000403b  test    rax, rax
0x14000403e  jz      short loc_140004049
0x140004040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004045  test    al, al
0x140004047  jmp     short loc_140004051
0x140004049  call    cs:__imp_IsDebuggerPresent
0x14000404f  test    eax, eax
0x140004051  jz      short loc_14000405C
0x140004053  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140004058  mov     bl, 1
0x14000405a  jz      short loc_14000405F
0x14000405c  mov     bl, r13b
0x14000405f  test    dil, dil
0x140004062  jnz     short loc_14000408E
0x140004064  test    bl, bl
0x140004066  jnz     short loc_14000408E
0x140004068  mov     rax, cs:g_pfnResultLoggingCallback
0x14000406f  test    rax, rax
0x140004072  jz      short loc_1400040EB
0x140004074  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x14000407b  jnz     short loc_1400040EB
0x14000407d  xor     r8d, r8d
0x140004080  xor     edx, edx
0x140004082  lea     rcx, [rsp+14F0h+var_14D0]
0x140004087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000408c  jmp     short loc_1400040EB
0x14000408e  mov     esi, 800h
0x140004093  mov     rax, cs:g_pfnResultLoggingCallback
0x14000409a  test    rax, rax
0x14000409d  jz      short loc_1400040BC
0x14000409f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1400040a6  jnz     short loc_1400040BC
0x1400040a8  mov     r8d, esi
0x1400040ab  lea     rdx, [rbp+13F0h+OutputString]
0x1400040b2  lea     rcx, [rsp+14F0h+var_14D0]
0x1400040b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400040bc  cmp     [rbp+13F0h+OutputString], r13w
0x1400040c4  jnz     short loc_1400040DA
0x1400040c6  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1400040cb  mov     rdx, rsi; unsigned __int16 *
0x1400040ce  lea     rcx, [rbp+13F0h+OutputString]; this
0x1400040d5  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400040da  test    bl, bl
0x1400040dc  jz      short loc_1400040EB
0x1400040de  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1400040e5  call    cs:__imp_OutputDebugStringW
0x1400040eb  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1400040f0  jnz     short loc_1400040FB
0x1400040f2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1400040f9  jz      short loc_14000410D
0x1400040fb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140004102  test    rax, rax
0x140004105  jz      short loc_14000410D
0x140004107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000410c  nop
0x14000410d  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140004112  jz      short loc_14000411F
0x140004114  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140004119  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000411f  test    dil, dil
0x140004122  jz      short loc_14000413C
0x140004124  lea     rdx, [rbp+13F0h+OutputString]
0x14000412b  lea     rcx, [rsp+14F0h+var_14D0]
0x140004130  mov     rax, cs:g_pfnThrowPlatformException
0x140004137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000413c  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140004141  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x140004146  lea     rcx, [rsp+14F0h+var_14D0]; this
0x14000414b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
