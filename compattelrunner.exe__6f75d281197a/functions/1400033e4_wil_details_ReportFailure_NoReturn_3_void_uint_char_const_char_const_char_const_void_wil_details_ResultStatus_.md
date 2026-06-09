# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1400033e4`
- end: `0x140003646`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140003188`

## callees

- `0x1400026c0`
- `0x1400033e4`
- `0x140005e84`
- `0x140006620`
- `0x140007720`
- `0x140009f50`
- `0x1400a7290`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003486`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003486`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003589`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003589`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003613`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003613`

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
0x1400033e4  mov     [rsp-8+arg_18], rbx
0x1400033e9  push    rbp
0x1400033ea  push    rsi
0x1400033eb  push    rdi
0x1400033ec  push    r12
0x1400033ee  push    r13
0x1400033f0  push    r14
0x1400033f2  push    r15
0x1400033f4  lea     rbp, [rsp-13C0h]
0x1400033fc  mov     eax, 14C0h
0x140003401  call    _alloca_probe
0x140003406  sub     rsp, rax
0x140003409  mov     r15, r8
0x14000340c  mov     r14d, edx
0x14000340f  mov     r12, rcx
0x140003412  mov     rsi, [rbp+13F0h+arg_28]
0x140003419  xor     edx, edx; Val
0x14000341b  mov     r8d, 98h; Size
0x140003421  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140003426  call    memset_0
0x14000342b  nop
0x14000342c  xor     r13d, r13d
0x14000342f  mov     [rbp+13F0h+OutputString], r13w
0x140003437  mov     [rbp+13F0h+var_1430], r13b
0x14000343b  mov     rbx, [rbp+13F0h+arg_30]
0x140003442  mov     ecx, [rbx]; this
0x140003444  mov     [rsp+14F0h+var_14C8], ecx
0x140003448  mov     eax, [rbx+4]
0x14000344b  mov     [rsp+14F0h+var_14C4], eax
0x14000344f  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140003454  mov     edi, eax
0x140003456  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x14000345e  mov     ecx, r13d
0x140003461  lea     eax, [r13+8]
0x140003465  cmp     dword ptr [rbx+8], 1
0x140003469  cmovz   ecx, eax
0x14000346c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140003470  lea     ecx, [rax-7]
0x140003473  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000347b  inc     ecx
0x14000347d  mov     [rsp+14F0h+var_14C0], ecx
0x140003481  mov     [rsp+14F0h+var_14B8], r13
0x140003486  call    cs:__imp_GetCurrentThreadId
0x14000348c  mov     [rsp+14F0h+var_14B0], eax
0x140003490  mov     [rsp+14F0h+var_1498], r15
0x140003495  mov     [rsp+14F0h+var_1490], r14d
0x14000349a  mov     [rsp+14F0h+var_148C], edi
0x14000349e  mov     [rsp+14F0h+var_14A8], r13
0x1400034a3  mov     [rsp+14F0h+var_14A0], r13
0x1400034a8  mov     [rbp+13F0h+var_1448], rsi
0x1400034ac  mov     [rbp+13F0h+var_1440], r12
0x1400034b0  mov     [rsp+14F0h+var_1488], r13
0x1400034b5  xorps   xmm0, xmm0
0x1400034b8  xor     eax, eax
0x1400034ba  movups  [rbp+13F0h+var_1468], xmm0
0x1400034be  mov     [rbp+13F0h+var_1458], rax
0x1400034c2  xorps   xmm1, xmm1
0x1400034c5  movups  [rsp+14F0h+var_1480], xmm1
0x1400034ca  mov     [rbp+13F0h+var_1470], rax
0x1400034ce  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400034d5  test    rax, rax
0x1400034d8  jz      short loc_1400034E5
0x1400034da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400034df  mov     [rbp+13F0h+var_1450], rax
0x1400034e3  jmp     short loc_1400034E9
0x1400034e5  mov     [rbp+13F0h+var_1450], r13
0x1400034e9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400034f0  test    rax, rax
0x1400034f3  jz      short loc_1400034FF
0x1400034f5  lea     rcx, [rsp+14F0h+var_14D0]
0x1400034fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400034ff  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140003506  test    rax, rax
0x140003509  jz      short loc_14000351F
0x14000350b  mov     r8d, 400h
0x140003511  lea     rdx, [rbp+13F0h+var_1430]
0x140003515  lea     rcx, [rsp+14F0h+var_14D0]
0x14000351a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000351f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003526  test    rax, rax
0x140003529  jz      short loc_140003535
0x14000352b  lea     rcx, [rsp+14F0h+var_14D0]
0x140003530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003535  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000353c  test    rax, rax
0x14000353f  jz      short loc_140003552
0x140003541  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140003546  jnz     short loc_140003552
0x140003548  lea     rcx, [rsp+14F0h+var_14D0]
0x14000354d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003552  cmp     [rsp+14F0h+var_14C8], r13d
0x140003557  jl      short loc_14000356B
0x140003559  mov     ecx, 8000FFFFh; this
0x14000355e  mov     [rsp+14F0h+var_14C8], ecx
0x140003562  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140003567  mov     [rsp+14F0h+var_14C4], eax
0x14000356b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140003572  jnz     short loc_140003593
0x140003574  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000357b  test    rax, rax
0x14000357e  jz      short loc_140003589
0x140003580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003585  test    al, al
0x140003587  jmp     short loc_140003591
0x140003589  call    cs:__imp_IsDebuggerPresent
0x14000358f  test    eax, eax
0x140003591  jz      short loc_14000359A
0x140003593  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140003598  jz      short loc_1400035C0
0x14000359a  mov     rax, cs:g_pfnResultLoggingCallback
0x1400035a1  test    rax, rax
0x1400035a4  jz      short loc_140003619
0x1400035a6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1400035ad  jnz     short loc_140003619
0x1400035af  xor     r8d, r8d
0x1400035b2  xor     edx, edx
0x1400035b4  lea     rcx, [rsp+14F0h+var_14D0]
0x1400035b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400035be  jmp     short loc_140003619
0x1400035c0  mov     ebx, 800h
0x1400035c5  mov     rax, cs:g_pfnResultLoggingCallback
0x1400035cc  test    rax, rax
0x1400035cf  jz      short loc_1400035EE
0x1400035d1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1400035d8  jnz     short loc_1400035EE
0x1400035da  mov     r8d, ebx
0x1400035dd  lea     rdx, [rbp+13F0h+OutputString]
0x1400035e4  lea     rcx, [rsp+14F0h+var_14D0]
0x1400035e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400035ee  cmp     [rbp+13F0h+OutputString], r13w
0x1400035f6  jnz     short loc_14000360C
0x1400035f8  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1400035fd  mov     rdx, rbx; unsigned __int16 *
0x140003600  lea     rcx, [rbp+13F0h+OutputString]; this
0x140003607  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000360c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140003613  call    cs:__imp_OutputDebugStringW
0x140003619  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x14000361e  jnz     short loc_140003629
0x140003620  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140003627  jz      short loc_14000363B
0x140003629  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003630  test    rax, rax
0x140003633  jz      short loc_14000363B
0x140003635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000363a  nop
0x14000363b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140003640  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
