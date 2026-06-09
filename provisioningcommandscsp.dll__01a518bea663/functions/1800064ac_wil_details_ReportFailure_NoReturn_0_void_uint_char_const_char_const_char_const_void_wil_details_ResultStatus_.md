# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800064ac`
- end: `0x180006758`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800062e0`

## callees

- `0x180003a74`
- `0x1800049e8`
- `0x1800055fc`
- `0x180005930`
- `0x180005b00`
- `0x1800064ac`
- `0x18000c5ce`
- `0x18000c6c0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006555`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006555`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800066ec`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800066ec`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006650`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006650`

## pseudocode

```c
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
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v16);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0);
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
0x1800064ac  mov     [rsp-8+arg_18], rbx
0x1800064b1  push    rbp
0x1800064b2  push    rsi
0x1800064b3  push    rdi
0x1800064b4  push    r12
0x1800064b6  push    r13
0x1800064b8  push    r14
0x1800064ba  push    r15
0x1800064bc  lea     rbp, [rsp-13C0h]
0x1800064c4  mov     eax, 14C0h
0x1800064c9  call    _alloca_probe
0x1800064ce  sub     rsp, rax
0x1800064d1  mov     r14, r8
0x1800064d4  mov     esi, edx
0x1800064d6  mov     r15, rcx
0x1800064d9  mov     rdi, [rbp+13F0h+arg_28]
0x1800064e0  xor     r13d, r13d
0x1800064e3  cmp     cs:g_pfnThrowPlatformException, r13
0x1800064ea  setnz   r12b
0x1800064ee  xor     edx, edx; Val
0x1800064f0  mov     r8d, 98h; Size
0x1800064f6  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800064fb  call    memset_0
0x180006500  nop
0x180006501  mov     [rbp+13F0h+OutputString], r13w
0x180006509  mov     [rbp+13F0h+var_1430], r13b
0x18000650d  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180006514  mov     ecx, [rdx]; this
0x180006516  mov     [rsp+14F0h+var_14C8], ecx
0x18000651a  mov     eax, [rdx+4]
0x18000651d  mov     [rsp+14F0h+var_14C4], eax
0x180006521  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006526  mov     ebx, eax
0x180006528  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18000652d  mov     ecx, r13d
0x180006530  lea     eax, [r13+8]
0x180006534  cmp     dword ptr [rdx+8], 1
0x180006538  cmovz   ecx, eax
0x18000653b  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000653f  lea     ecx, [rax-7]
0x180006542  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000654a  inc     ecx
0x18000654c  mov     [rsp+14F0h+var_14C0], ecx
0x180006550  mov     [rsp+14F0h+var_14B8], r13
0x180006555  call    cs:__imp_GetCurrentThreadId
0x18000655b  mov     [rsp+14F0h+var_14B0], eax
0x18000655f  mov     [rsp+14F0h+var_1498], r14
0x180006564  mov     [rsp+14F0h+var_1490], esi
0x180006568  mov     [rsp+14F0h+var_148C], ebx
0x18000656c  mov     [rsp+14F0h+var_14A8], r13
0x180006571  mov     [rsp+14F0h+var_14A0], r13
0x180006576  mov     [rbp+13F0h+var_1448], rdi
0x18000657a  mov     [rbp+13F0h+var_1440], r15
0x18000657e  mov     [rsp+14F0h+var_1488], r13
0x180006583  xorps   xmm0, xmm0
0x180006586  xor     eax, eax
0x180006588  movups  [rbp+13F0h+var_1468], xmm0
0x18000658c  mov     [rbp+13F0h+var_1458], rax
0x180006590  xorps   xmm1, xmm1
0x180006593  movups  [rsp+14F0h+var_1480], xmm1
0x180006598  mov     [rbp+13F0h+var_1470], rax
0x18000659c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800065a3  test    rax, rax
0x1800065a6  jz      short loc_1800065B3
0x1800065a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065ad  mov     [rbp+13F0h+var_1450], rax
0x1800065b1  jmp     short loc_1800065B7
0x1800065b3  mov     [rbp+13F0h+var_1450], r13
0x1800065b7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800065be  test    rax, rax
0x1800065c1  jz      short loc_1800065CD
0x1800065c3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800065c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065cd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800065d4  test    rax, rax
0x1800065d7  jz      short loc_1800065ED
0x1800065d9  mov     r8d, 400h
0x1800065df  lea     rdx, [rbp+13F0h+var_1430]
0x1800065e3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800065e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065ed  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800065f4  test    rax, rax
0x1800065f7  jz      short loc_180006603
0x1800065f9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800065fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006603  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000660a  test    rax, rax
0x18000660d  jz      short loc_180006625
0x18000660f  test    r12b, r12b
0x180006612  jnz     short loc_180006625
0x180006614  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180006619  jnz     short loc_180006625
0x18000661b  lea     rcx, [rsp+14F0h+var_14D0]
0x180006620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006625  cmp     [rsp+14F0h+var_14C8], r13d
0x18000662a  jl      short loc_180006632
0x18000662c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006632  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180006639  jnz     short loc_18000665A
0x18000663b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006642  test    rax, rax
0x180006645  jz      short loc_180006650
0x180006647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000664c  test    al, al
0x18000664e  jmp     short loc_180006658
0x180006650  call    cs:__imp_IsDebuggerPresent
0x180006656  test    eax, eax
0x180006658  jz      short loc_180006663
0x18000665a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000665f  mov     bl, 1
0x180006661  jz      short loc_180006666
0x180006663  mov     bl, r13b
0x180006666  test    r12b, r12b
0x180006669  jnz     short loc_180006695
0x18000666b  test    bl, bl
0x18000666d  jnz     short loc_180006695
0x18000666f  mov     rax, cs:g_pfnResultLoggingCallback
0x180006676  test    rax, rax
0x180006679  jz      short loc_1800066F2
0x18000667b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180006682  jnz     short loc_1800066F2
0x180006684  xor     r8d, r8d
0x180006687  xor     edx, edx
0x180006689  lea     rcx, [rsp+14F0h+var_14D0]
0x18000668e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006693  jmp     short loc_1800066F2
0x180006695  mov     edi, 800h
0x18000669a  mov     rax, cs:g_pfnResultLoggingCallback
0x1800066a1  test    rax, rax
0x1800066a4  jz      short loc_1800066C3
0x1800066a6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800066ad  jnz     short loc_1800066C3
0x1800066af  mov     r8d, edi
0x1800066b2  lea     rdx, [rbp+13F0h+OutputString]
0x1800066b9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800066be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066c3  cmp     [rbp+13F0h+OutputString], r13w
0x1800066cb  jnz     short loc_1800066E1
0x1800066cd  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800066d2  mov     rdx, rdi; unsigned __int16 *
0x1800066d5  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800066dc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800066e1  test    bl, bl
0x1800066e3  jz      short loc_1800066F2
0x1800066e5  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800066ec  call    cs:__imp_OutputDebugStringW
0x1800066f2  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800066f7  jnz     short loc_180006702
0x1800066f9  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180006700  jz      short loc_180006714
0x180006702  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006709  test    rax, rax
0x18000670c  jz      short loc_180006714
0x18000670e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006713  nop
0x180006714  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180006719  jz      short loc_180006726
0x18000671b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180006720  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180006726  test    r12b, r12b
0x180006729  jz      short loc_180006743
0x18000672b  lea     rdx, [rbp+13F0h+OutputString]
0x180006732  lea     rcx, [rsp+14F0h+var_14D0]
0x180006737  mov     rax, cs:g_pfnThrowPlatformException
0x18000673e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006743  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180006748  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18000674d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180006752  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
