# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800140e4`
- end: `0x1800143ca`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `742`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180014020`

## callees

- `0x180003bc8`
- `0x180008064`
- `0x1800094fc`
- `0x18000a574`
- `0x18000b4fc`
- `0x18000bc50`
- `0x18000be1c`
- `0x1800140e4`
- `0x180057f50`
- `0x180061010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800141b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800141b8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800142b8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800142b8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180014355`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180014355`

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
        _WORD *a8,
        char a9)
{
  bool v12; // di
  _WORD *v13; // r8
  int v14; // r13d
  int v15; // ecx
  __int64 v16; // rdx
  const struct wil::FailureInfo *v17; // rdx
  wil::details::in1diag3 *v18; // rcx
  const struct wil::FailureInfo *v19; // r9
  bool v20; // zf
  char v21; // bl
  const struct wil::FailureInfo *v22; // rdx
  int v23; // [rsp+20h] [rbp-E0h] BYREF
  int v24; // [rsp+24h] [rbp-DCh]
  int v25; // [rsp+28h] [rbp-D8h]
  int v26; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v27; // [rsp+30h] [rbp-D0h]
  _WORD *v28; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v30; // [rsp+48h] [rbp-B8h]
  __int64 v31; // [rsp+50h] [rbp-B0h]
  __int64 v32; // [rsp+58h] [rbp-A8h]
  int v33; // [rsp+60h] [rbp-A0h]
  int v34; // [rsp+64h] [rbp-9Ch]
  __int64 v35; // [rsp+68h] [rbp-98h]
  __int128 v36; // [rsp+70h] [rbp-90h]
  __int64 v37; // [rsp+80h] [rbp-80h]
  __int128 v38; // [rsp+88h] [rbp-78h]
  __int64 v39; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v41; // [rsp+A8h] [rbp-58h]
  __int64 v42; // [rsp+B0h] [rbp-50h]
  char v43[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v12 = (a9 & 2) == 0 && g_pfnThrowPlatformException;
  memset_0(&v23, 0, 0x98u);
  OutputString[0] = 0;
  v43[0] = 0;
  v25 = *a7;
  v26 = a7[1];
  v14 = wil::details::RecordException((wil::details *)(unsigned int)v25, (int)a7);
  v23 = (int)v13;
  v15 = (int)v13;
  if ( *(_DWORD *)(v16 + 8) == 1 )
    v15 = (_DWORD)v13 + 8;
  v24 = v15;
  v27 = _InterlockedExchangeAdd(&`wil::details::LogFailure'::`2'::s_failureId, (_DWORD)v13 + 1) + 1;
  if ( !a8 || (v20 = *a8 == (unsigned __int16)v13, v28 = a8, v20) )
    v28 = v13;
  CurrentThreadId = GetCurrentThreadId();
  v32 = a3;
  v33 = a2;
  v34 = v14;
  v30 = 0;
  v31 = 0;
  v41 = a6;
  v42 = a1;
  v35 = 0;
  v38 = 0;
  v39 = 0;
  v36 = 0;
  v37 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v18);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v23);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v23, v43, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v23);
  if ( wil::details::g_pfnOriginateCallback && !v12 && (v24 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v23);
  if ( v25 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v18);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v20 = !IsDebuggerPresent())
      : (v20 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v18) == 0),
        v20)
    || (v21 = 1, (v24 & 2) != 0) )
  {
    v21 = 0;
  }
  if ( v12 || v21 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, OutputString, 2048, v19);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v23, v19);
    if ( v21 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v23, 0, 0, v19);
  }
  if ( ((v24 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v18);
  if ( (v24 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v23, v17);
  if ( v12 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v23, OutputString);
  if ( (a9 & 2) != 0 )
    wil::RethrowCaughtException(v18);
  wil::ThrowResultException((wil *)&v23, v17);
  wil::details::WilFailFast((wil::details *)&v23, v22);
}

```

## disassembly

```asm
0x1800140e4  mov     [rsp-8+arg_18], rbx
0x1800140e9  push    rbp
0x1800140ea  push    rsi
0x1800140eb  push    rdi
0x1800140ec  push    r12
0x1800140ee  push    r13
0x1800140f0  push    r14
0x1800140f2  push    r15
0x1800140f4  lea     rbp, [rsp-13C0h]
0x1800140fc  mov     eax, 14C0h
0x180014101  call    _alloca_probe
0x180014106  sub     rsp, rax
0x180014109  mov     r15, r8
0x18001410c  mov     r14d, edx
0x18001410f  mov     rbx, rcx
0x180014112  mov     r12, [rbp+13F0h+arg_28]
0x180014119  mov     esi, [rbp+13F0h+arg_40]
0x18001411f  and     esi, 2
0x180014122  jnz     short loc_180014133
0x180014124  cmp     cs:g_pfnThrowPlatformException, 0
0x18001412c  jz      short loc_180014133
0x18001412e  mov     dil, 1
0x180014131  jmp     short loc_180014136
0x180014133  xor     dil, dil
0x180014136  xor     edx, edx; Val
0x180014138  mov     r8d, 98h; Size
0x18001413e  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180014143  call    memset_0
0x180014148  nop
0x180014149  xor     r8d, r8d
0x18001414c  mov     [rbp+13F0h+OutputString], r8w
0x180014154  mov     [rbp+13F0h+var_1430], r8b
0x180014158  mov     rdx, [rbp+13F0h+arg_30]; int
0x18001415f  mov     ecx, [rdx]; this
0x180014161  mov     [rsp+14F0h+var_14C8], ecx
0x180014165  mov     eax, [rdx+4]
0x180014168  mov     [rsp+14F0h+var_14C4], eax
0x18001416c  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180014171  mov     r13d, eax
0x180014174  mov     dword ptr [rsp+14F0h+var_14D0], r8d
0x180014179  mov     ecx, r8d
0x18001417c  lea     eax, [r8+8]
0x180014180  cmp     dword ptr [rdx+8], 1
0x180014184  cmovz   ecx, eax
0x180014187  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18001418b  lea     ecx, [rax-7]
0x18001418e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180014196  inc     ecx
0x180014198  mov     [rsp+14F0h+var_14C0], ecx
0x18001419c  mov     rcx, [rbp+13F0h+arg_38]
0x1800141a3  test    rcx, rcx
0x1800141a6  jz      short loc_1800141B3
0x1800141a8  cmp     [rcx], r8w
0x1800141ac  mov     [rsp+14F0h+var_14B8], rcx
0x1800141b1  jnz     short loc_1800141B8
0x1800141b3  mov     [rsp+14F0h+var_14B8], r8
0x1800141b8  call    cs:__imp_GetCurrentThreadId
0x1800141be  mov     [rsp+14F0h+var_14B0], eax
0x1800141c2  mov     [rsp+14F0h+var_1498], r15
0x1800141c7  mov     [rsp+14F0h+var_1490], r14d
0x1800141cc  mov     [rsp+14F0h+var_148C], r13d
0x1800141d1  xor     r14d, r14d
0x1800141d4  mov     [rsp+14F0h+var_14A8], r14
0x1800141d9  mov     [rsp+14F0h+var_14A0], r14
0x1800141de  mov     [rbp+13F0h+var_1448], r12
0x1800141e2  mov     [rbp+13F0h+var_1440], rbx
0x1800141e6  mov     [rsp+14F0h+var_1488], r14
0x1800141eb  xorps   xmm0, xmm0
0x1800141ee  xor     eax, eax
0x1800141f0  movups  [rbp+13F0h+var_1468], xmm0
0x1800141f4  mov     [rbp+13F0h+var_1458], rax
0x1800141f8  xorps   xmm1, xmm1
0x1800141fb  movups  [rsp+14F0h+var_1480], xmm1
0x180014200  mov     [rbp+13F0h+var_1470], rax
0x180014204  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001420b  test    rax, rax
0x18001420e  jz      short loc_18001421B
0x180014210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014215  mov     [rbp+13F0h+var_1450], rax
0x180014219  jmp     short loc_18001421F
0x18001421b  mov     [rbp+13F0h+var_1450], r14
0x18001421f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180014226  test    rax, rax
0x180014229  jz      short loc_180014235
0x18001422b  lea     rcx, [rsp+14F0h+var_14D0]
0x180014230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014235  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001423c  test    rax, rax
0x18001423f  jz      short loc_180014255
0x180014241  mov     r8d, 400h
0x180014247  lea     rdx, [rbp+13F0h+var_1430]
0x18001424b  lea     rcx, [rsp+14F0h+var_14D0]
0x180014250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014255  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001425c  test    rax, rax
0x18001425f  jz      short loc_18001426B
0x180014261  lea     rcx, [rsp+14F0h+var_14D0]
0x180014266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001426b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180014272  test    rax, rax
0x180014275  jz      short loc_18001428D
0x180014277  test    dil, dil
0x18001427a  jnz     short loc_18001428D
0x18001427c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180014281  jnz     short loc_18001428D
0x180014283  lea     rcx, [rsp+14F0h+var_14D0]
0x180014288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001428d  cmp     [rsp+14F0h+var_14C8], r14d
0x180014292  jl      short loc_18001429A
0x180014294  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001429a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r14b; bool wil::g_fIsDebuggerPresent
0x1800142a1  jnz     short loc_1800142C2
0x1800142a3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800142aa  test    rax, rax
0x1800142ad  jz      short loc_1800142B8
0x1800142af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142b4  test    al, al
0x1800142b6  jmp     short loc_1800142C0
0x1800142b8  call    cs:__imp_IsDebuggerPresent
0x1800142be  test    eax, eax
0x1800142c0  jz      short loc_1800142CB
0x1800142c2  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800142c7  mov     bl, 1
0x1800142c9  jz      short loc_1800142CE
0x1800142cb  mov     bl, r14b
0x1800142ce  test    dil, dil
0x1800142d1  jnz     short loc_1800142FD
0x1800142d3  test    bl, bl
0x1800142d5  jnz     short loc_1800142FD
0x1800142d7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800142de  test    rax, rax
0x1800142e1  jz      short loc_18001435B
0x1800142e3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r14b; bool wil::details::g_resultMessageCallbackSet
0x1800142ea  jnz     short loc_18001435B
0x1800142ec  xor     r8d, r8d
0x1800142ef  xor     edx, edx
0x1800142f1  lea     rcx, [rsp+14F0h+var_14D0]
0x1800142f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142fb  jmp     short loc_18001435B
0x1800142fd  mov     r15d, 800h
0x180014303  mov     rax, cs:g_pfnResultLoggingCallback
0x18001430a  test    rax, rax
0x18001430d  jz      short loc_18001432C
0x18001430f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r14b; bool wil::details::g_resultMessageCallbackSet
0x180014316  jnz     short loc_18001432C
0x180014318  mov     r8d, r15d
0x18001431b  lea     rdx, [rbp+13F0h+OutputString]
0x180014322  lea     rcx, [rsp+14F0h+var_14D0]
0x180014327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001432c  cmp     [rbp+13F0h+OutputString], r14w
0x180014334  jnz     short loc_18001434A
0x180014336  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18001433b  mov     rdx, r15; unsigned __int16 *
0x18001433e  lea     rcx, [rbp+13F0h+OutputString]; this
0x180014345  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001434a  test    bl, bl
0x18001434c  jz      short loc_18001435B
0x18001434e  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180014355  call    cs:__imp_OutputDebugStringW
0x18001435b  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180014360  jnz     short loc_18001436B
0x180014362  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r14b; bool wil::g_fBreakOnFailure
0x180014369  jz      short loc_18001437D
0x18001436b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180014372  test    rax, rax
0x180014375  jz      short loc_18001437D
0x180014377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001437c  nop
0x18001437d  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180014382  jz      short loc_18001438F
0x180014384  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180014389  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18001438f  test    dil, dil
0x180014392  jz      short loc_1800143AC
0x180014394  lea     rdx, [rbp+13F0h+OutputString]
0x18001439b  lea     rcx, [rsp+14F0h+var_14D0]
0x1800143a0  mov     rax, cs:g_pfnThrowPlatformException
0x1800143a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143ac  test    esi, esi
0x1800143ae  jz      short loc_1800143B5
0x1800143b0  call    ?RethrowCaughtException@wil@@YAXXZ; wil::RethrowCaughtException(void)
0x1800143b5  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800143ba  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x1800143bf  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800143c4  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
