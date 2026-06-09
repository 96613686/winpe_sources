# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800033d0`
- end: `0x180003630`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003174`

## callees

- `0x1800033d0`
- `0x1800052e4`
- `0x180005a7c`
- `0x180006650`
- `0x180008280`
- `0x18000bbc2`
- `0x18000bc80`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003471`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003471`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800035fe`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800035fe`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003574`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003574`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // eax
  int v11; // edx
  int v12; // eax
  int v13; // edi
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  __int64 v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
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

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v22, v11);
  v19 = a7[2] == 1;
  v13 = v12;
  v20 = 3;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
  {
    v22 = -2147418113;
    v23 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v16);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( (v21 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v17);
  }
  wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x1800033d0  mov     [rsp-8+arg_18], rbx
0x1800033d5  push    rbp
0x1800033d6  push    rsi
0x1800033d7  push    rdi
0x1800033d8  push    r12
0x1800033da  push    r13
0x1800033dc  push    r14
0x1800033de  push    r15
0x1800033e0  lea     rbp, [rsp-13C0h]
0x1800033e8  mov     eax, 14C0h
0x1800033ed  call    _alloca_probe
0x1800033f2  sub     rsp, rax
0x1800033f5  mov     rsi, [rbp+13F0h+arg_28]
0x1800033fc  mov     r15, r8
0x1800033ff  mov     r14d, edx
0x180003402  mov     r12, rcx
0x180003405  xor     edx, edx; Val
0x180003407  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000340c  mov     r8d, 98h; Size
0x180003412  call    memset_0
0x180003417  mov     rbx, [rbp+13F0h+arg_30]
0x18000341e  xor     r13d, r13d
0x180003421  mov     [rbp+13F0h+OutputString], r13w
0x180003429  mov     [rbp+13F0h+var_1430], r13b
0x18000342d  mov     ecx, [rbx]; this
0x18000342f  mov     eax, [rbx+4]
0x180003432  mov     [rsp+14F0h+var_14C8], ecx
0x180003436  mov     [rsp+14F0h+var_14C4], eax
0x18000343a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000343f  cmp     dword ptr [rbx+8], 1
0x180003443  mov     edi, eax
0x180003445  lea     eax, [r13+8]
0x180003449  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180003451  mov     ecx, r13d
0x180003454  cmovz   ecx, eax
0x180003457  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000345b  lea     ecx, [rax-7]
0x18000345e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003466  inc     ecx
0x180003468  mov     [rsp+14F0h+var_14B8], r13
0x18000346d  mov     [rsp+14F0h+var_14C0], ecx
0x180003471  call    cs:__imp_GetCurrentThreadId
0x180003477  xorps   xmm0, xmm0
0x18000347a  mov     [rsp+14F0h+var_1498], r15
0x18000347f  mov     [rsp+14F0h+var_14B0], eax
0x180003483  xorps   xmm1, xmm1
0x180003486  xor     eax, eax
0x180003488  mov     [rsp+14F0h+var_1490], r14d
0x18000348d  mov     [rbp+13F0h+var_1458], rax
0x180003491  mov     [rbp+13F0h+var_1470], rax
0x180003495  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000349c  mov     [rsp+14F0h+var_148C], edi
0x1800034a0  mov     [rsp+14F0h+var_14A8], r13
0x1800034a5  mov     [rsp+14F0h+var_14A0], r13
0x1800034aa  mov     [rbp+13F0h+var_1448], rsi
0x1800034ae  mov     [rbp+13F0h+var_1440], r12
0x1800034b2  mov     [rsp+14F0h+var_1488], r13
0x1800034b7  movups  [rbp+13F0h+var_1468], xmm0
0x1800034bb  movups  [rsp+14F0h+var_1480], xmm1
0x1800034c0  test    rax, rax
0x1800034c3  jz      short loc_1800034D0
0x1800034c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034ca  mov     [rbp+13F0h+var_1450], rax
0x1800034ce  jmp     short loc_1800034D4
0x1800034d0  mov     [rbp+13F0h+var_1450], r13
0x1800034d4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800034db  test    rax, rax
0x1800034de  jz      short loc_1800034EA
0x1800034e0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800034e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034ea  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800034f1  test    rax, rax
0x1800034f4  jz      short loc_18000350A
0x1800034f6  mov     r8d, 400h
0x1800034fc  lea     rdx, [rbp+13F0h+var_1430]
0x180003500  lea     rcx, [rsp+14F0h+var_14D0]
0x180003505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000350a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003511  test    rax, rax
0x180003514  jz      short loc_180003520
0x180003516  lea     rcx, [rsp+14F0h+var_14D0]
0x18000351b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003520  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003527  test    rax, rax
0x18000352a  jz      short loc_18000353D
0x18000352c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003531  jnz     short loc_18000353D
0x180003533  lea     rcx, [rsp+14F0h+var_14D0]
0x180003538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000353d  cmp     [rsp+14F0h+var_14C8], r13d
0x180003542  jl      short loc_180003556
0x180003544  mov     ecx, 8000FFFFh; this
0x180003549  mov     [rsp+14F0h+var_14C8], ecx
0x18000354d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003552  mov     [rsp+14F0h+var_14C4], eax
0x180003556  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000355d  jnz     short loc_18000357E
0x18000355f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003566  test    rax, rax
0x180003569  jz      short loc_180003574
0x18000356b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003570  test    al, al
0x180003572  jmp     short loc_18000357C
0x180003574  call    cs:__imp_IsDebuggerPresent
0x18000357a  test    eax, eax
0x18000357c  jz      short loc_180003585
0x18000357e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003583  jz      short loc_1800035AB
0x180003585  mov     rax, cs:g_pfnResultLoggingCallback
0x18000358c  test    rax, rax
0x18000358f  jz      short loc_180003604
0x180003591  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003598  jnz     short loc_180003604
0x18000359a  xor     r8d, r8d
0x18000359d  lea     rcx, [rsp+14F0h+var_14D0]
0x1800035a2  xor     edx, edx
0x1800035a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035a9  jmp     short loc_180003604
0x1800035ab  mov     rax, cs:g_pfnResultLoggingCallback
0x1800035b2  mov     ebx, 800h
0x1800035b7  test    rax, rax
0x1800035ba  jz      short loc_1800035D9
0x1800035bc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800035c3  jnz     short loc_1800035D9
0x1800035c5  mov     r8d, ebx
0x1800035c8  lea     rdx, [rbp+13F0h+OutputString]
0x1800035cf  lea     rcx, [rsp+14F0h+var_14D0]
0x1800035d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035d9  cmp     [rbp+13F0h+OutputString], r13w
0x1800035e1  jnz     short loc_1800035F7
0x1800035e3  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800035e8  mov     rdx, rbx; unsigned __int16 *
0x1800035eb  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800035f2  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800035f7  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800035fe  call    cs:__imp_OutputDebugStringW
0x180003604  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003609  jnz     short loc_180003614
0x18000360b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180003612  jz      short loc_180003625
0x180003614  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000361b  test    rax, rax
0x18000361e  jz      short loc_180003625
0x180003620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003625  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000362a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
