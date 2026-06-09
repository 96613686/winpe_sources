# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180002374`
- end: `0x1800025ed`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, __int64, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800020e4`

## callees

- `0x180001f9e`
- `0x180002374`
- `0x180003784`
- `0x180003f24`
- `0x180004690`
- `0x180005740`
- `0x18000a850`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000242d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000242d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800025ba`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800025ba`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002530`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002530`

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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v18, v16);
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
0x180002374  mov     [rsp-8+arg_18], rbx
0x180002379  push    rbp
0x18000237a  push    rsi
0x18000237b  push    rdi
0x18000237c  push    r12
0x18000237e  push    r13
0x180002380  push    r14
0x180002382  push    r15
0x180002384  lea     rbp, [rsp-13C0h]
0x18000238c  mov     eax, 14C0h
0x180002391  call    _alloca_probe
0x180002396  sub     rsp, rax
0x180002399  mov     r14, r8
0x18000239c  mov     esi, edx
0x18000239e  mov     rdi, rcx
0x1800023a1  mov     r15, [rbp+13F0h+arg_28]
0x1800023a8  xor     edx, edx; Val
0x1800023aa  mov     r8d, 98h; Size
0x1800023b0  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800023b5  call    memset_0
0x1800023ba  nop
0x1800023bb  xor     r13d, r13d
0x1800023be  mov     [rbp+13F0h+OutputString], r13w
0x1800023c6  mov     [rbp+13F0h+var_1430], r13b
0x1800023ca  mov     rbx, [rbp+13F0h+arg_30]
0x1800023d1  mov     ecx, [rbx]; this
0x1800023d3  mov     [rsp+14F0h+var_14C8], ecx
0x1800023d7  mov     eax, [rbx+4]
0x1800023da  mov     [rsp+14F0h+var_14C4], eax
0x1800023de  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800023e3  mov     r12d, eax
0x1800023e6  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800023ee  mov     ecx, r13d
0x1800023f1  lea     eax, [r13+8]
0x1800023f5  cmp     dword ptr [rbx+8], 1
0x1800023f9  cmovz   ecx, eax
0x1800023fc  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002400  lea     ecx, [rax-7]
0x180002403  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000240b  inc     ecx
0x18000240d  mov     [rsp+14F0h+var_14C0], ecx
0x180002411  mov     rcx, [rbp+13F0h+arg_38]
0x180002418  test    rcx, rcx
0x18000241b  jz      short loc_180002428
0x18000241d  cmp     [rcx], r13w
0x180002421  mov     [rsp+14F0h+var_14B8], rcx
0x180002426  jnz     short loc_18000242D
0x180002428  mov     [rsp+14F0h+var_14B8], r13
0x18000242d  call    cs:__imp_GetCurrentThreadId
0x180002433  mov     [rsp+14F0h+var_14B0], eax
0x180002437  mov     [rsp+14F0h+var_1498], r14
0x18000243c  mov     [rsp+14F0h+var_1490], esi
0x180002440  mov     [rsp+14F0h+var_148C], r12d
0x180002445  mov     [rsp+14F0h+var_14A8], r13
0x18000244a  mov     [rsp+14F0h+var_14A0], r13
0x18000244f  mov     [rbp+13F0h+var_1448], r15
0x180002453  mov     [rbp+13F0h+var_1440], rdi
0x180002457  mov     [rsp+14F0h+var_1488], r13
0x18000245c  xorps   xmm0, xmm0
0x18000245f  xor     eax, eax
0x180002461  movups  [rbp+13F0h+var_1468], xmm0
0x180002465  mov     [rbp+13F0h+var_1458], rax
0x180002469  xorps   xmm1, xmm1
0x18000246c  movups  [rsp+14F0h+var_1480], xmm1
0x180002471  mov     [rbp+13F0h+var_1470], rax
0x180002475  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000247c  test    rax, rax
0x18000247f  jz      short loc_18000248C
0x180002481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002486  mov     [rbp+13F0h+var_1450], rax
0x18000248a  jmp     short loc_180002490
0x18000248c  mov     [rbp+13F0h+var_1450], r13
0x180002490  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002497  test    rax, rax
0x18000249a  jz      short loc_1800024A6
0x18000249c  lea     rcx, [rsp+14F0h+var_14D0]
0x1800024a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024a6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800024ad  test    rax, rax
0x1800024b0  jz      short loc_1800024C6
0x1800024b2  mov     r8d, 400h
0x1800024b8  lea     rdx, [rbp+13F0h+var_1430]
0x1800024bc  lea     rcx, [rsp+14F0h+var_14D0]
0x1800024c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024c6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800024cd  test    rax, rax
0x1800024d0  jz      short loc_1800024DC
0x1800024d2  lea     rcx, [rsp+14F0h+var_14D0]
0x1800024d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024dc  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800024e3  test    rax, rax
0x1800024e6  jz      short loc_1800024F9
0x1800024e8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800024ed  jnz     short loc_1800024F9
0x1800024ef  lea     rcx, [rsp+14F0h+var_14D0]
0x1800024f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024f9  cmp     [rsp+14F0h+var_14C8], r13d
0x1800024fe  jl      short loc_180002512
0x180002500  mov     ecx, 8000FFFFh; this
0x180002505  mov     [rsp+14F0h+var_14C8], ecx
0x180002509  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000250e  mov     [rsp+14F0h+var_14C4], eax
0x180002512  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180002519  jnz     short loc_18000253A
0x18000251b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002522  test    rax, rax
0x180002525  jz      short loc_180002530
0x180002527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000252c  test    al, al
0x18000252e  jmp     short loc_180002538
0x180002530  call    cs:__imp_IsDebuggerPresent
0x180002536  test    eax, eax
0x180002538  jz      short loc_180002541
0x18000253a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000253f  jz      short loc_180002567
0x180002541  mov     rax, cs:g_pfnResultLoggingCallback
0x180002548  test    rax, rax
0x18000254b  jz      short loc_1800025C0
0x18000254d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002554  jnz     short loc_1800025C0
0x180002556  xor     r8d, r8d
0x180002559  xor     edx, edx
0x18000255b  lea     rcx, [rsp+14F0h+var_14D0]
0x180002560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002565  jmp     short loc_1800025C0
0x180002567  mov     ebx, 800h
0x18000256c  mov     rax, cs:g_pfnResultLoggingCallback
0x180002573  test    rax, rax
0x180002576  jz      short loc_180002595
0x180002578  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000257f  jnz     short loc_180002595
0x180002581  mov     r8d, ebx
0x180002584  lea     rdx, [rbp+13F0h+OutputString]
0x18000258b  lea     rcx, [rsp+14F0h+var_14D0]
0x180002590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002595  cmp     [rbp+13F0h+OutputString], r13w
0x18000259d  jnz     short loc_1800025B3
0x18000259f  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800025a4  mov     rdx, rbx; wchar_t *
0x1800025a7  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800025ae  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800025b3  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800025ba  call    cs:__imp_OutputDebugStringW
0x1800025c0  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800025c5  jnz     short loc_1800025D0
0x1800025c7  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800025ce  jz      short loc_1800025E2
0x1800025d0  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800025d7  test    rax, rax
0x1800025da  jz      short loc_1800025E2
0x1800025dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025e1  nop
0x1800025e2  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800025e7  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
