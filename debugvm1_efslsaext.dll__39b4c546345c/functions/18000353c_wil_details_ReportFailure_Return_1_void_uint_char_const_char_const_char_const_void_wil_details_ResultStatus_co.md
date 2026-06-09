# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000353c`
- end: `0x1800037d0`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000301c`

## callees

- `0x18000353c`
- `0x18000459c`
- `0x180005530`
- `0x180006210`
- `0x1800062ec`
- `0x18001200e`
- `0x180012040`
- `0x1800120d0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000376b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000376b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800036e1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800036e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800035e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800035e6`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v18 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  v19 = 1;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v20 = v13;
  v24 = 0;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v25 = CurrentThreadId;
  v30 = v12;
  v28 = "wil";
  v35 = 0;
  v33 = 0;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x18000353c  mov     [rsp-8+arg_10], rbx
0x180003541  push    rbp
0x180003542  push    rsi
0x180003543  push    rdi
0x180003544  push    r14
0x180003546  push    r15
0x180003548  lea     rbp, [rsp-13D0h]
0x180003550  mov     eax, 14D0h
0x180003555  call    _alloca_probe
0x18000355a  sub     rsp, rax
0x18000355d  mov     rax, cs:__security_cookie
0x180003564  xor     rax, rsp
0x180003567  mov     [rbp+13F0h+var_30], rax
0x18000356e  mov     rdi, [rbp+13F0h+arg_28]
0x180003575  mov     esi, edx
0x180003577  mov     r14, rcx
0x18000357a  xor     edx, edx; Val
0x18000357c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003581  mov     r8d, 98h; Size
0x180003587  call    memset_0
0x18000358c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180003593  xor     r15d, r15d
0x180003596  mov     [rbp+13F0h+OutputString], r15w
0x18000359e  mov     [rbp+13F0h+var_1430], r15b
0x1800035a2  mov     ecx, [rdx]; this
0x1800035a4  mov     eax, [rdx+4]
0x1800035a7  mov     [rsp+14F0h+var_14C8], ecx
0x1800035ab  mov     [rsp+14F0h+var_14C4], eax
0x1800035af  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800035b4  cmp     dword ptr [rdx+8], 1
0x1800035b8  mov     ebx, eax
0x1800035ba  lea     eax, [r15+8]
0x1800035be  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800035c6  mov     ecx, r15d
0x1800035c9  cmovz   ecx, eax
0x1800035cc  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800035d0  lea     ecx, [rax-7]
0x1800035d3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800035db  inc     ecx
0x1800035dd  mov     [rsp+14F0h+var_14B8], r15
0x1800035e2  mov     [rsp+14F0h+var_14C0], ecx
0x1800035e6  call    cs:__imp_GetCurrentThreadId
0x1800035ec  xorps   xmm0, xmm0
0x1800035ef  mov     [rsp+14F0h+var_1490], esi
0x1800035f3  mov     [rsp+14F0h+var_14B0], eax
0x1800035f7  xorps   xmm1, xmm1
0x1800035fa  lea     rax, aWil; "wil"
0x180003601  mov     [rsp+14F0h+var_148C], ebx
0x180003605  mov     [rsp+14F0h+var_1498], rax
0x18000360a  xor     eax, eax
0x18000360c  mov     [rbp+13F0h+var_1458], rax
0x180003610  mov     [rbp+13F0h+var_1470], rax
0x180003614  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000361b  mov     [rsp+14F0h+var_14A8], r15
0x180003620  mov     [rsp+14F0h+var_14A0], r15
0x180003625  mov     [rbp+13F0h+var_1448], rdi
0x180003629  mov     [rbp+13F0h+var_1440], r14
0x18000362d  mov     [rsp+14F0h+var_1488], r15
0x180003632  movups  [rbp+13F0h+var_1468], xmm0
0x180003636  movups  [rsp+14F0h+var_1480], xmm1
0x18000363b  test    rax, rax
0x18000363e  jz      short loc_18000364B
0x180003640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003645  mov     [rbp+13F0h+var_1450], rax
0x180003649  jmp     short loc_18000364F
0x18000364b  mov     [rbp+13F0h+var_1450], r15
0x18000364f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003656  test    rax, rax
0x180003659  jz      short loc_180003665
0x18000365b  lea     rcx, [rsp+14F0h+var_14D0]
0x180003660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003665  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000366c  test    rax, rax
0x18000366f  jz      short loc_180003685
0x180003671  mov     r8d, 400h
0x180003677  lea     rdx, [rbp+13F0h+var_1430]
0x18000367b  lea     rcx, [rsp+14F0h+var_14D0]
0x180003680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003685  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000368c  test    rax, rax
0x18000368f  jz      short loc_18000369B
0x180003691  lea     rcx, [rsp+14F0h+var_14D0]
0x180003696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000369b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800036a2  test    rax, rax
0x1800036a5  jz      short loc_1800036B8
0x1800036a7  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800036ac  jnz     short loc_1800036B8
0x1800036ae  lea     rcx, [rsp+14F0h+var_14D0]
0x1800036b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036b8  cmp     [rsp+14F0h+var_14C8], r15d
0x1800036bd  jge     loc_1800037BF
0x1800036c3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800036ca  jnz     short loc_1800036EB
0x1800036cc  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800036d3  test    rax, rax
0x1800036d6  jz      short loc_1800036E1
0x1800036d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036dd  test    al, al
0x1800036df  jmp     short loc_1800036E9
0x1800036e1  call    cs:__imp_IsDebuggerPresent
0x1800036e7  test    eax, eax
0x1800036e9  jz      short loc_1800036F2
0x1800036eb  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800036f0  jz      short loc_180003718
0x1800036f2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800036f9  test    rax, rax
0x1800036fc  jz      short loc_180003771
0x1800036fe  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003705  jnz     short loc_180003771
0x180003707  xor     r8d, r8d
0x18000370a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000370f  xor     edx, edx
0x180003711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003716  jmp     short loc_180003771
0x180003718  mov     rax, cs:g_pfnResultLoggingCallback
0x18000371f  mov     ebx, 800h
0x180003724  test    rax, rax
0x180003727  jz      short loc_180003746
0x180003729  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003730  jnz     short loc_180003746
0x180003732  mov     r8d, ebx
0x180003735  lea     rdx, [rbp+13F0h+OutputString]
0x18000373c  lea     rcx, [rsp+14F0h+var_14D0]
0x180003741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003746  cmp     [rbp+13F0h+OutputString], r15w
0x18000374e  jnz     short loc_180003764
0x180003750  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003755  mov     rdx, rbx; unsigned __int16 *
0x180003758  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000375f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003764  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000376b  call    cs:__imp_OutputDebugStringW
0x180003771  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003776  jnz     short loc_180003781
0x180003778  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000377f  jz      short loc_180003792
0x180003781  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003788  test    rax, rax
0x18000378b  jz      short loc_180003792
0x18000378d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003792  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180003797  jnz     short loc_1800037C5
0x180003799  mov     rcx, [rbp+13F0h+var_30]
0x1800037a0  xor     rcx, rsp; StackCookie
0x1800037a3  call    __security_check_cookie
0x1800037a8  mov     rbx, [rsp+14F0h+arg_10]
0x1800037b0  add     rsp, 14D0h
0x1800037b7  pop     r15
0x1800037b9  pop     r14
0x1800037bb  pop     rdi
0x1800037bc  pop     rsi
0x1800037bd  pop     rbp
0x1800037be  retn
0x1800037bf  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800037c5  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800037ca  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
