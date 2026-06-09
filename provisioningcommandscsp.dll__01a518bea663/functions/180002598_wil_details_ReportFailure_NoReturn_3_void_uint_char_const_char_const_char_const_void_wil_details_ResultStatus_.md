# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002598`
- end: `0x180002811`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, __int64, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002308`

## callees

- `0x180002598`
- `0x180003a74`
- `0x180004214`
- `0x180004a10`
- `0x180005930`
- `0x18000c5ce`
- `0x18000c6c0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002651`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002651`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800027de`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800027de`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002754`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002754`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // edx
  int v12; // r12d
  int v13; // ecx
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
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

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, v11);
  v18 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v19 = v13;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v12;
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
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
  {
    v20 = -2147418113;
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v14);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v15);
  }
  wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180002598  mov     [rsp-8+arg_18], rbx
0x18000259d  push    rbp
0x18000259e  push    rsi
0x18000259f  push    rdi
0x1800025a0  push    r12
0x1800025a2  push    r13
0x1800025a4  push    r14
0x1800025a6  push    r15
0x1800025a8  lea     rbp, [rsp-13C0h]
0x1800025b0  mov     eax, 14C0h
0x1800025b5  call    _alloca_probe
0x1800025ba  sub     rsp, rax
0x1800025bd  mov     r14, r8
0x1800025c0  mov     esi, edx
0x1800025c2  mov     rdi, rcx
0x1800025c5  mov     r15, [rbp+13F0h+arg_28]
0x1800025cc  xor     edx, edx; Val
0x1800025ce  mov     r8d, 98h; Size
0x1800025d4  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800025d9  call    memset_0
0x1800025de  nop
0x1800025df  xor     r13d, r13d
0x1800025e2  mov     [rbp+13F0h+OutputString], r13w
0x1800025ea  mov     [rbp+13F0h+var_1430], r13b
0x1800025ee  mov     rbx, [rbp+13F0h+arg_30]
0x1800025f5  mov     ecx, [rbx]; this
0x1800025f7  mov     [rsp+14F0h+var_14C8], ecx
0x1800025fb  mov     eax, [rbx+4]
0x1800025fe  mov     [rsp+14F0h+var_14C4], eax
0x180002602  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002607  mov     r12d, eax
0x18000260a  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180002612  mov     ecx, r13d
0x180002615  lea     eax, [r13+8]
0x180002619  cmp     dword ptr [rbx+8], 1
0x18000261d  cmovz   ecx, eax
0x180002620  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002624  lea     ecx, [rax-7]
0x180002627  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000262f  inc     ecx
0x180002631  mov     [rsp+14F0h+var_14C0], ecx
0x180002635  mov     rcx, [rbp+13F0h+arg_38]
0x18000263c  test    rcx, rcx
0x18000263f  jz      short loc_18000264C
0x180002641  cmp     [rcx], r13w
0x180002645  mov     [rsp+14F0h+var_14B8], rcx
0x18000264a  jnz     short loc_180002651
0x18000264c  mov     [rsp+14F0h+var_14B8], r13
0x180002651  call    cs:__imp_GetCurrentThreadId
0x180002657  mov     [rsp+14F0h+var_14B0], eax
0x18000265b  mov     [rsp+14F0h+var_1498], r14
0x180002660  mov     [rsp+14F0h+var_1490], esi
0x180002664  mov     [rsp+14F0h+var_148C], r12d
0x180002669  mov     [rsp+14F0h+var_14A8], r13
0x18000266e  mov     [rsp+14F0h+var_14A0], r13
0x180002673  mov     [rbp+13F0h+var_1448], r15
0x180002677  mov     [rbp+13F0h+var_1440], rdi
0x18000267b  mov     [rsp+14F0h+var_1488], r13
0x180002680  xorps   xmm0, xmm0
0x180002683  xor     eax, eax
0x180002685  movups  [rbp+13F0h+var_1468], xmm0
0x180002689  mov     [rbp+13F0h+var_1458], rax
0x18000268d  xorps   xmm1, xmm1
0x180002690  movups  [rsp+14F0h+var_1480], xmm1
0x180002695  mov     [rbp+13F0h+var_1470], rax
0x180002699  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800026a0  test    rax, rax
0x1800026a3  jz      short loc_1800026B0
0x1800026a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026aa  mov     [rbp+13F0h+var_1450], rax
0x1800026ae  jmp     short loc_1800026B4
0x1800026b0  mov     [rbp+13F0h+var_1450], r13
0x1800026b4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800026bb  test    rax, rax
0x1800026be  jz      short loc_1800026CA
0x1800026c0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800026c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026ca  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800026d1  test    rax, rax
0x1800026d4  jz      short loc_1800026EA
0x1800026d6  mov     r8d, 400h
0x1800026dc  lea     rdx, [rbp+13F0h+var_1430]
0x1800026e0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800026e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026ea  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800026f1  test    rax, rax
0x1800026f4  jz      short loc_180002700
0x1800026f6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800026fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002700  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002707  test    rax, rax
0x18000270a  jz      short loc_18000271D
0x18000270c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002711  jnz     short loc_18000271D
0x180002713  lea     rcx, [rsp+14F0h+var_14D0]
0x180002718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000271d  cmp     [rsp+14F0h+var_14C8], r13d
0x180002722  jl      short loc_180002736
0x180002724  mov     ecx, 8000FFFFh; this
0x180002729  mov     [rsp+14F0h+var_14C8], ecx
0x18000272d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002732  mov     [rsp+14F0h+var_14C4], eax
0x180002736  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000273d  jnz     short loc_18000275E
0x18000273f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002746  test    rax, rax
0x180002749  jz      short loc_180002754
0x18000274b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002750  test    al, al
0x180002752  jmp     short loc_18000275C
0x180002754  call    cs:__imp_IsDebuggerPresent
0x18000275a  test    eax, eax
0x18000275c  jz      short loc_180002765
0x18000275e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002763  jz      short loc_18000278B
0x180002765  mov     rax, cs:g_pfnResultLoggingCallback
0x18000276c  test    rax, rax
0x18000276f  jz      short loc_1800027E4
0x180002771  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002778  jnz     short loc_1800027E4
0x18000277a  xor     r8d, r8d
0x18000277d  xor     edx, edx
0x18000277f  lea     rcx, [rsp+14F0h+var_14D0]
0x180002784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002789  jmp     short loc_1800027E4
0x18000278b  mov     ebx, 800h
0x180002790  mov     rax, cs:g_pfnResultLoggingCallback
0x180002797  test    rax, rax
0x18000279a  jz      short loc_1800027B9
0x18000279c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800027a3  jnz     short loc_1800027B9
0x1800027a5  mov     r8d, ebx
0x1800027a8  lea     rdx, [rbp+13F0h+OutputString]
0x1800027af  lea     rcx, [rsp+14F0h+var_14D0]
0x1800027b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027b9  cmp     [rbp+13F0h+OutputString], r13w
0x1800027c1  jnz     short loc_1800027D7
0x1800027c3  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800027c8  mov     rdx, rbx; unsigned __int16 *
0x1800027cb  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800027d2  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800027d7  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800027de  call    cs:__imp_OutputDebugStringW
0x1800027e4  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800027e9  jnz     short loc_1800027F4
0x1800027eb  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800027f2  jz      short loc_180002806
0x1800027f4  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800027fb  test    rax, rax
0x1800027fe  jz      short loc_180002806
0x180002800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002805  nop
0x180002806  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000280b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
