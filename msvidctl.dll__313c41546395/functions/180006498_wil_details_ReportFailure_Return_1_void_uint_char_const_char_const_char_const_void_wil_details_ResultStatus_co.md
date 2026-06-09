# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180006498`
- end: `0x18000672e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180005fa8`

## callees

- `0x180004640`
- `0x1800054bc`
- `0x180006498`
- `0x180009a34`
- `0x18000ac50`
- `0x18000c3f0`
- `0x18000c4cc`
- `0x1800eeda0`
- `0x1800f8010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x1800066c8`
- `KERNEL32!OutputDebugStringW` at `0x1800066c8`
- `KERNEL32!IsDebuggerPresent` at `0x18000663e`
- `KERNEL32!IsDebuggerPresent` at `0x18000663e`
- `KERNEL32!GetCurrentThreadId` at `0x180006543`
- `KERNEL32!GetCurrentThreadId` at `0x180006543`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x180006498  mov     [rsp-8+arg_10], rbx
0x18000649d  push    rbp
0x18000649e  push    rsi
0x18000649f  push    rdi
0x1800064a0  push    r14
0x1800064a2  push    r15
0x1800064a4  lea     rbp, [rsp-13D0h]
0x1800064ac  mov     eax, 14D0h
0x1800064b1  call    _alloca_probe
0x1800064b6  sub     rsp, rax
0x1800064b9  mov     rax, cs:__security_cookie
0x1800064c0  xor     rax, rsp
0x1800064c3  mov     [rbp+13F0h+var_30], rax
0x1800064ca  mov     esi, edx
0x1800064cc  mov     r14, rcx
0x1800064cf  mov     rdi, [rbp+13F0h+arg_28]
0x1800064d6  xor     edx, edx; Val
0x1800064d8  mov     r8d, 98h; Size
0x1800064de  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800064e3  call    memset_0
0x1800064e8  nop
0x1800064e9  xor     r15d, r15d
0x1800064ec  mov     [rbp+13F0h+OutputString], r15w
0x1800064f4  mov     [rbp+13F0h+var_1430], r15b
0x1800064f8  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800064ff  mov     ecx, [rdx]; this
0x180006501  mov     [rsp+14F0h+var_14C8], ecx
0x180006505  mov     eax, [rdx+4]
0x180006508  mov     [rsp+14F0h+var_14C4], eax
0x18000650c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006511  mov     ebx, eax
0x180006513  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000651b  mov     ecx, r15d
0x18000651e  lea     eax, [r15+8]
0x180006522  cmp     dword ptr [rdx+8], 1
0x180006526  cmovz   ecx, eax
0x180006529  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000652d  lea     ecx, [rax-7]
0x180006530  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006538  inc     ecx
0x18000653a  mov     [rsp+14F0h+var_14C0], ecx
0x18000653e  mov     [rsp+14F0h+var_14B8], r15
0x180006543  call    cs:__imp_GetCurrentThreadId
0x180006549  mov     [rsp+14F0h+var_14B0], eax
0x18000654d  lea     rax, aWil; "wil"
0x180006554  mov     [rsp+14F0h+var_1498], rax
0x180006559  mov     [rsp+14F0h+var_1490], esi
0x18000655d  mov     [rsp+14F0h+var_148C], ebx
0x180006561  mov     [rsp+14F0h+var_14A8], r15
0x180006566  mov     [rsp+14F0h+var_14A0], r15
0x18000656b  mov     [rbp+13F0h+var_1448], rdi
0x18000656f  mov     [rbp+13F0h+var_1440], r14
0x180006573  mov     [rsp+14F0h+var_1488], r15
0x180006578  xorps   xmm0, xmm0
0x18000657b  xor     eax, eax
0x18000657d  movups  [rbp+13F0h+var_1468], xmm0
0x180006581  mov     [rbp+13F0h+var_1458], rax
0x180006585  xorps   xmm1, xmm1
0x180006588  movups  [rsp+14F0h+var_1480], xmm1
0x18000658d  mov     [rbp+13F0h+var_1470], rax
0x180006591  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006598  test    rax, rax
0x18000659b  jz      short loc_1800065A8
0x18000659d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065a2  mov     [rbp+13F0h+var_1450], rax
0x1800065a6  jmp     short loc_1800065AC
0x1800065a8  mov     [rbp+13F0h+var_1450], r15
0x1800065ac  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800065b3  test    rax, rax
0x1800065b6  jz      short loc_1800065C2
0x1800065b8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800065bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065c2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800065c9  test    rax, rax
0x1800065cc  jz      short loc_1800065E2
0x1800065ce  mov     r8d, 400h
0x1800065d4  lea     rdx, [rbp+13F0h+var_1430]
0x1800065d8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800065dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065e2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800065e9  test    rax, rax
0x1800065ec  jz      short loc_1800065F8
0x1800065ee  lea     rcx, [rsp+14F0h+var_14D0]
0x1800065f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065f8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800065ff  test    rax, rax
0x180006602  jz      short loc_180006615
0x180006604  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180006609  jnz     short loc_180006615
0x18000660b  lea     rcx, [rsp+14F0h+var_14D0]
0x180006610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006615  cmp     [rsp+14F0h+var_14C8], r15d
0x18000661a  jge     loc_180006728
0x180006620  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180006627  jnz     short loc_180006648
0x180006629  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006630  test    rax, rax
0x180006633  jz      short loc_18000663E
0x180006635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000663a  test    al, al
0x18000663c  jmp     short loc_180006646
0x18000663e  call    cs:__imp_IsDebuggerPresent
0x180006644  test    eax, eax
0x180006646  jz      short loc_18000664F
0x180006648  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000664d  jz      short loc_180006675
0x18000664f  mov     rax, cs:g_pfnResultLoggingCallback
0x180006656  test    rax, rax
0x180006659  jz      short loc_1800066CE
0x18000665b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006662  jnz     short loc_1800066CE
0x180006664  xor     r8d, r8d
0x180006667  xor     edx, edx
0x180006669  lea     rcx, [rsp+14F0h+var_14D0]
0x18000666e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006673  jmp     short loc_1800066CE
0x180006675  mov     ebx, 800h
0x18000667a  mov     rax, cs:g_pfnResultLoggingCallback
0x180006681  test    rax, rax
0x180006684  jz      short loc_1800066A3
0x180006686  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000668d  jnz     short loc_1800066A3
0x18000668f  mov     r8d, ebx
0x180006692  lea     rdx, [rbp+13F0h+OutputString]
0x180006699  lea     rcx, [rsp+14F0h+var_14D0]
0x18000669e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066a3  cmp     [rbp+13F0h+OutputString], r15w
0x1800066ab  jnz     short loc_1800066C1
0x1800066ad  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800066b2  mov     rdx, rbx; unsigned __int16 *
0x1800066b5  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800066bc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800066c1  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800066c8  call    cs:__imp_OutputDebugStringW
0x1800066ce  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800066d3  jnz     short loc_1800066DE
0x1800066d5  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800066dc  jz      short loc_1800066F0
0x1800066de  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800066e5  test    rax, rax
0x1800066e8  jz      short loc_1800066F0
0x1800066ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066ef  nop
0x1800066f0  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800066f5  jnz     short loc_18000671D
0x1800066f7  mov     rcx, [rbp+13F0h+var_30]
0x1800066fe  xor     rcx, rsp; StackCookie
0x180006701  call    __security_check_cookie
0x180006706  mov     rbx, [rsp+14F0h+arg_10]
0x18000670e  add     rsp, 14D0h
0x180006715  pop     r15
0x180006717  pop     r14
0x180006719  pop     rdi
0x18000671a  pop     rsi
0x18000671b  pop     rbp
0x18000671c  retn
0x18000671d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180006722  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180006728  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
