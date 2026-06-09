# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18002a39c`
- end: `0x18002a673`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `727`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002a218`

## callees

- `0x180003cf0`
- `0x180006d44`
- `0x1800087e4`
- `0x18000ab90`
- `0x18000b30c`
- `0x18000b59c`
- `0x18002a39c`
- `0x180057050`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a45d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a45d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002a601`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002a601`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002a55f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002a55f`

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
0x18002a39c  mov     [rsp-8+arg_18], rbx
0x18002a3a1  push    rbp
0x18002a3a2  push    rsi
0x18002a3a3  push    rdi
0x18002a3a4  push    r12
0x18002a3a6  push    r13
0x18002a3a8  push    r14
0x18002a3aa  push    r15
0x18002a3ac  lea     rbp, [rsp-13C0h]
0x18002a3b4  mov     eax, 14C0h
0x18002a3b9  call    _alloca_probe
0x18002a3be  sub     rsp, rax
0x18002a3c1  mov     r14, r8
0x18002a3c4  mov     esi, edx
0x18002a3c6  mov     rbx, rcx
0x18002a3c9  mov     r15, [rbp+13F0h+arg_28]
0x18002a3d0  xor     r13d, r13d
0x18002a3d3  cmp     cs:g_pfnThrowPlatformException, r13
0x18002a3da  setnz   dil
0x18002a3de  xor     edx, edx; Val
0x18002a3e0  mov     r8d, 98h; Size
0x18002a3e6  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18002a3eb  call    memset_0
0x18002a3f0  nop
0x18002a3f1  mov     [rbp+13F0h+OutputString], r13w
0x18002a3f9  mov     [rbp+13F0h+var_1430], r13b
0x18002a3fd  mov     rdx, [rbp+13F0h+arg_30]; int
0x18002a404  mov     ecx, [rdx]; this
0x18002a406  mov     [rsp+14F0h+var_14C8], ecx
0x18002a40a  mov     eax, [rdx+4]
0x18002a40d  mov     [rsp+14F0h+var_14C4], eax
0x18002a411  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18002a416  mov     r12d, eax
0x18002a419  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18002a41e  mov     ecx, r13d
0x18002a421  lea     eax, [r13+8]
0x18002a425  cmp     dword ptr [rdx+8], 1
0x18002a429  cmovz   ecx, eax
0x18002a42c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18002a430  lea     ecx, [rax-7]
0x18002a433  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002a43b  inc     ecx
0x18002a43d  mov     [rsp+14F0h+var_14C0], ecx
0x18002a441  mov     rcx, [rbp+13F0h+arg_38]
0x18002a448  test    rcx, rcx
0x18002a44b  jz      short loc_18002A458
0x18002a44d  cmp     [rcx], r13w
0x18002a451  mov     [rsp+14F0h+var_14B8], rcx
0x18002a456  jnz     short loc_18002A45D
0x18002a458  mov     [rsp+14F0h+var_14B8], r13
0x18002a45d  call    cs:__imp_GetCurrentThreadId
0x18002a464  nop     dword ptr [rax+rax+00h]
0x18002a469  mov     [rsp+14F0h+var_14B0], eax
0x18002a46d  mov     [rsp+14F0h+var_1498], r14
0x18002a472  mov     [rsp+14F0h+var_1490], esi
0x18002a476  mov     [rsp+14F0h+var_148C], r12d
0x18002a47b  mov     [rsp+14F0h+var_14A8], r13
0x18002a480  mov     [rsp+14F0h+var_14A0], r13
0x18002a485  mov     [rbp+13F0h+var_1448], r15
0x18002a489  mov     [rbp+13F0h+var_1440], rbx
0x18002a48d  mov     [rsp+14F0h+var_1488], r13
0x18002a492  xorps   xmm0, xmm0
0x18002a495  xor     eax, eax
0x18002a497  movups  [rbp+13F0h+var_1468], xmm0
0x18002a49b  mov     [rbp+13F0h+var_1458], rax
0x18002a49f  xorps   xmm1, xmm1
0x18002a4a2  movups  [rsp+14F0h+var_1480], xmm1
0x18002a4a7  mov     [rbp+13F0h+var_1470], rax
0x18002a4ab  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002a4b2  test    rax, rax
0x18002a4b5  jz      short loc_18002A4C2
0x18002a4b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a4bc  mov     [rbp+13F0h+var_1450], rax
0x18002a4c0  jmp     short loc_18002A4C6
0x18002a4c2  mov     [rbp+13F0h+var_1450], r13
0x18002a4c6  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002a4cd  test    rax, rax
0x18002a4d0  jz      short loc_18002A4DC
0x18002a4d2  lea     rcx, [rsp+14F0h+var_14D0]
0x18002a4d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a4dc  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002a4e3  test    rax, rax
0x18002a4e6  jz      short loc_18002A4FC
0x18002a4e8  mov     r8d, 400h
0x18002a4ee  lea     rdx, [rbp+13F0h+var_1430]
0x18002a4f2  lea     rcx, [rsp+14F0h+var_14D0]
0x18002a4f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a4fc  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002a503  test    rax, rax
0x18002a506  jz      short loc_18002A512
0x18002a508  lea     rcx, [rsp+14F0h+var_14D0]
0x18002a50d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a512  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002a519  test    rax, rax
0x18002a51c  jz      short loc_18002A534
0x18002a51e  test    dil, dil
0x18002a521  jnz     short loc_18002A534
0x18002a523  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18002a528  jnz     short loc_18002A534
0x18002a52a  lea     rcx, [rsp+14F0h+var_14D0]
0x18002a52f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a534  cmp     [rsp+14F0h+var_14C8], r13d
0x18002a539  jl      short loc_18002A541
0x18002a53b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18002a541  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18002a548  jnz     short loc_18002A56F
0x18002a54a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18002a551  test    rax, rax
0x18002a554  jz      short loc_18002A55F
0x18002a556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a55b  test    al, al
0x18002a55d  jmp     short loc_18002A56D
0x18002a55f  call    cs:__imp_IsDebuggerPresent
0x18002a566  nop     dword ptr [rax+rax+00h]
0x18002a56b  test    eax, eax
0x18002a56d  jz      short loc_18002A578
0x18002a56f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18002a574  mov     bl, 1
0x18002a576  jz      short loc_18002A57B
0x18002a578  mov     bl, r13b
0x18002a57b  test    dil, dil
0x18002a57e  jnz     short loc_18002A5AA
0x18002a580  test    bl, bl
0x18002a582  jnz     short loc_18002A5AA
0x18002a584  mov     rax, cs:g_pfnResultLoggingCallback
0x18002a58b  test    rax, rax
0x18002a58e  jz      short loc_18002A60D
0x18002a590  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18002a597  jnz     short loc_18002A60D
0x18002a599  xor     r8d, r8d
0x18002a59c  xor     edx, edx
0x18002a59e  lea     rcx, [rsp+14F0h+var_14D0]
0x18002a5a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a5a8  jmp     short loc_18002A60D
0x18002a5aa  mov     esi, 800h
0x18002a5af  mov     rax, cs:g_pfnResultLoggingCallback
0x18002a5b6  test    rax, rax
0x18002a5b9  jz      short loc_18002A5D8
0x18002a5bb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18002a5c2  jnz     short loc_18002A5D8
0x18002a5c4  mov     r8d, esi
0x18002a5c7  lea     rdx, [rbp+13F0h+OutputString]
0x18002a5ce  lea     rcx, [rsp+14F0h+var_14D0]
0x18002a5d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a5d8  cmp     [rbp+13F0h+OutputString], r13w
0x18002a5e0  jnz     short loc_18002A5F6
0x18002a5e2  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18002a5e7  mov     rdx, rsi; unsigned __int16 *
0x18002a5ea  lea     rcx, [rbp+13F0h+OutputString]; this
0x18002a5f1  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18002a5f6  test    bl, bl
0x18002a5f8  jz      short loc_18002A60D
0x18002a5fa  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18002a601  call    cs:__imp_OutputDebugStringW
0x18002a608  nop     dword ptr [rax+rax+00h]
0x18002a60d  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18002a612  jnz     short loc_18002A61D
0x18002a614  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18002a61b  jz      short loc_18002A62F
0x18002a61d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002a624  test    rax, rax
0x18002a627  jz      short loc_18002A62F
0x18002a629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a62e  nop
0x18002a62f  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18002a634  jz      short loc_18002A641
0x18002a636  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18002a63b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18002a641  test    dil, dil
0x18002a644  jz      short loc_18002A65E
0x18002a646  lea     rdx, [rbp+13F0h+OutputString]
0x18002a64d  lea     rcx, [rsp+14F0h+var_14D0]
0x18002a652  mov     rax, cs:g_pfnThrowPlatformException
0x18002a659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a65e  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18002a663  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18002a668  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18002a66d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
