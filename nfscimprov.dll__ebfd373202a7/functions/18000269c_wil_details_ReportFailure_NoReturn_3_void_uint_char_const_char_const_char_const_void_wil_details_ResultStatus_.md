# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000269c`
- end: `0x1800028fe`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002468`

## callees

- `0x18000269c`
- `0x1800041c4`
- `0x180004a30`
- `0x180005980`
- `0x1800073d0`
- `0x180035b02`
- `0x180035c00`
- `0x180037010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000273e`
- `KERNEL32!GetCurrentThreadId` at `0x18000273e`
- `KERNEL32!OutputDebugStringW` at `0x1800028cb`
- `KERNEL32!OutputDebugStringW` at `0x1800028cb`
- `KERNEL32!IsDebuggerPresent` at `0x180002841`
- `KERNEL32!IsDebuggerPresent` at `0x180002841`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // edx
  int v11; // edi
  int v12; // ecx
  const struct wil::FailureInfo *v13; // rdx
  __int64 v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v19, v10);
  v17 = 3;
  v12 = 0;
  if ( a7[2] == 1 )
    v12 = 8;
  v18 = v12;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v11;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
  {
    v19 = -2147418113;
    v20 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v13);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( (v18 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v14);
  }
  wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x18000269c  mov     [rsp-8+arg_18], rbx
0x1800026a1  push    rbp
0x1800026a2  push    rsi
0x1800026a3  push    rdi
0x1800026a4  push    r12
0x1800026a6  push    r13
0x1800026a8  push    r14
0x1800026aa  push    r15
0x1800026ac  lea     rbp, [rsp-13C0h]
0x1800026b4  mov     eax, 14C0h
0x1800026b9  call    _alloca_probe
0x1800026be  sub     rsp, rax
0x1800026c1  mov     r15, r8
0x1800026c4  mov     r14d, edx
0x1800026c7  mov     r12, rcx
0x1800026ca  mov     rsi, [rbp+13F0h+arg_28]
0x1800026d1  xor     edx, edx; Val
0x1800026d3  mov     r8d, 98h; Size
0x1800026d9  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800026de  call    memset_0
0x1800026e3  nop
0x1800026e4  xor     r13d, r13d
0x1800026e7  mov     [rbp+13F0h+OutputString], r13w
0x1800026ef  mov     [rbp+13F0h+var_1430], r13b
0x1800026f3  mov     rbx, [rbp+13F0h+arg_30]
0x1800026fa  mov     ecx, [rbx]; this
0x1800026fc  mov     [rsp+14F0h+var_14C8], ecx
0x180002700  mov     eax, [rbx+4]
0x180002703  mov     [rsp+14F0h+var_14C4], eax
0x180002707  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000270c  mov     edi, eax
0x18000270e  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180002716  mov     ecx, r13d
0x180002719  lea     eax, [r13+8]
0x18000271d  cmp     dword ptr [rbx+8], 1
0x180002721  cmovz   ecx, eax
0x180002724  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002728  lea     ecx, [rax-7]
0x18000272b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002733  inc     ecx
0x180002735  mov     [rsp+14F0h+var_14C0], ecx
0x180002739  mov     [rsp+14F0h+var_14B8], r13
0x18000273e  call    cs:__imp_GetCurrentThreadId
0x180002744  mov     [rsp+14F0h+var_14B0], eax
0x180002748  mov     [rsp+14F0h+var_1498], r15
0x18000274d  mov     [rsp+14F0h+var_1490], r14d
0x180002752  mov     [rsp+14F0h+var_148C], edi
0x180002756  mov     [rsp+14F0h+var_14A8], r13
0x18000275b  mov     [rsp+14F0h+var_14A0], r13
0x180002760  mov     [rbp+13F0h+var_1448], rsi
0x180002764  mov     [rbp+13F0h+var_1440], r12
0x180002768  mov     [rsp+14F0h+var_1488], r13
0x18000276d  xorps   xmm0, xmm0
0x180002770  xor     eax, eax
0x180002772  movups  [rbp+13F0h+var_1468], xmm0
0x180002776  mov     [rbp+13F0h+var_1458], rax
0x18000277a  xorps   xmm1, xmm1
0x18000277d  movups  [rsp+14F0h+var_1480], xmm1
0x180002782  mov     [rbp+13F0h+var_1470], rax
0x180002786  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000278d  test    rax, rax
0x180002790  jz      short loc_18000279D
0x180002792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002797  mov     [rbp+13F0h+var_1450], rax
0x18000279b  jmp     short loc_1800027A1
0x18000279d  mov     [rbp+13F0h+var_1450], r13
0x1800027a1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800027a8  test    rax, rax
0x1800027ab  jz      short loc_1800027B7
0x1800027ad  lea     rcx, [rsp+14F0h+var_14D0]
0x1800027b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027b7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800027be  test    rax, rax
0x1800027c1  jz      short loc_1800027D7
0x1800027c3  mov     r8d, 400h
0x1800027c9  lea     rdx, [rbp+13F0h+var_1430]
0x1800027cd  lea     rcx, [rsp+14F0h+var_14D0]
0x1800027d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027d7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800027de  test    rax, rax
0x1800027e1  jz      short loc_1800027ED
0x1800027e3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800027e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027ed  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800027f4  test    rax, rax
0x1800027f7  jz      short loc_18000280A
0x1800027f9  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800027fe  jnz     short loc_18000280A
0x180002800  lea     rcx, [rsp+14F0h+var_14D0]
0x180002805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000280a  cmp     [rsp+14F0h+var_14C8], r13d
0x18000280f  jl      short loc_180002823
0x180002811  mov     ecx, 8000FFFFh; this
0x180002816  mov     [rsp+14F0h+var_14C8], ecx
0x18000281a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000281f  mov     [rsp+14F0h+var_14C4], eax
0x180002823  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000282a  jnz     short loc_18000284B
0x18000282c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002833  test    rax, rax
0x180002836  jz      short loc_180002841
0x180002838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000283d  test    al, al
0x18000283f  jmp     short loc_180002849
0x180002841  call    cs:__imp_IsDebuggerPresent
0x180002847  test    eax, eax
0x180002849  jz      short loc_180002852
0x18000284b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002850  jz      short loc_180002878
0x180002852  mov     rax, cs:g_pfnResultLoggingCallback
0x180002859  test    rax, rax
0x18000285c  jz      short loc_1800028D1
0x18000285e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002865  jnz     short loc_1800028D1
0x180002867  xor     r8d, r8d
0x18000286a  xor     edx, edx
0x18000286c  lea     rcx, [rsp+14F0h+var_14D0]
0x180002871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002876  jmp     short loc_1800028D1
0x180002878  mov     ebx, 800h
0x18000287d  mov     rax, cs:g_pfnResultLoggingCallback
0x180002884  test    rax, rax
0x180002887  jz      short loc_1800028A6
0x180002889  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002890  jnz     short loc_1800028A6
0x180002892  mov     r8d, ebx
0x180002895  lea     rdx, [rbp+13F0h+OutputString]
0x18000289c  lea     rcx, [rsp+14F0h+var_14D0]
0x1800028a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028a6  cmp     [rbp+13F0h+OutputString], r13w
0x1800028ae  jnz     short loc_1800028C4
0x1800028b0  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800028b5  mov     rdx, rbx; unsigned __int16 *
0x1800028b8  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800028bf  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800028c4  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800028cb  call    cs:__imp_OutputDebugStringW
0x1800028d1  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800028d6  jnz     short loc_1800028E1
0x1800028d8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800028df  jz      short loc_1800028F3
0x1800028e1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800028e8  test    rax, rax
0x1800028eb  jz      short loc_1800028F3
0x1800028ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028f2  nop
0x1800028f3  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800028f8  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
