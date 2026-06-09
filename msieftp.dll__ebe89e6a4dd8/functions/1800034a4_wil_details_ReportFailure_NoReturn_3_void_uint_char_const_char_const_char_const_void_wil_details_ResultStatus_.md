# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800034a4`
- end: `0x180003704`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003248`

## callees

- `0x180002b60`
- `0x1800034a4`
- `0x1800061e4`
- `0x18000697c`
- `0x180007d00`
- `0x18000a1f0`
- `0x1800271f0`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003545`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003545`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800036d2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800036d2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003648`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003648`

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
0x1800034a4  mov     [rsp-8+arg_18], rbx
0x1800034a9  push    rbp
0x1800034aa  push    rsi
0x1800034ab  push    rdi
0x1800034ac  push    r12
0x1800034ae  push    r13
0x1800034b0  push    r14
0x1800034b2  push    r15
0x1800034b4  lea     rbp, [rsp-13C0h]
0x1800034bc  mov     eax, 14C0h
0x1800034c1  call    _alloca_probe
0x1800034c6  sub     rsp, rax
0x1800034c9  mov     rsi, [rbp+13F0h+arg_28]
0x1800034d0  mov     r15, r8
0x1800034d3  mov     r14d, edx
0x1800034d6  mov     r12, rcx
0x1800034d9  xor     edx, edx; Val
0x1800034db  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800034e0  mov     r8d, 98h; Size
0x1800034e6  call    memset_0
0x1800034eb  mov     rbx, [rbp+13F0h+arg_30]
0x1800034f2  xor     r13d, r13d
0x1800034f5  mov     [rbp+13F0h+OutputString], r13w
0x1800034fd  mov     [rbp+13F0h+var_1430], r13b
0x180003501  mov     ecx, [rbx]; this
0x180003503  mov     eax, [rbx+4]
0x180003506  mov     [rsp+14F0h+var_14C8], ecx
0x18000350a  mov     [rsp+14F0h+var_14C4], eax
0x18000350e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180003513  cmp     dword ptr [rbx+8], 1
0x180003517  mov     edi, eax
0x180003519  lea     eax, [r13+8]
0x18000351d  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180003525  mov     ecx, r13d
0x180003528  cmovz   ecx, eax
0x18000352b  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000352f  lea     ecx, [rax-7]
0x180003532  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000353a  inc     ecx
0x18000353c  mov     [rsp+14F0h+var_14B8], r13
0x180003541  mov     [rsp+14F0h+var_14C0], ecx
0x180003545  call    cs:__imp_GetCurrentThreadId
0x18000354b  xorps   xmm0, xmm0
0x18000354e  mov     [rsp+14F0h+var_1498], r15
0x180003553  mov     [rsp+14F0h+var_14B0], eax
0x180003557  xorps   xmm1, xmm1
0x18000355a  xor     eax, eax
0x18000355c  mov     [rsp+14F0h+var_1490], r14d
0x180003561  mov     [rbp+13F0h+var_1458], rax
0x180003565  mov     [rbp+13F0h+var_1470], rax
0x180003569  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003570  mov     [rsp+14F0h+var_148C], edi
0x180003574  mov     [rsp+14F0h+var_14A8], r13
0x180003579  mov     [rsp+14F0h+var_14A0], r13
0x18000357e  mov     [rbp+13F0h+var_1448], rsi
0x180003582  mov     [rbp+13F0h+var_1440], r12
0x180003586  mov     [rsp+14F0h+var_1488], r13
0x18000358b  movups  [rbp+13F0h+var_1468], xmm0
0x18000358f  movups  [rsp+14F0h+var_1480], xmm1
0x180003594  test    rax, rax
0x180003597  jz      short loc_1800035A4
0x180003599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000359e  mov     [rbp+13F0h+var_1450], rax
0x1800035a2  jmp     short loc_1800035A8
0x1800035a4  mov     [rbp+13F0h+var_1450], r13
0x1800035a8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800035af  test    rax, rax
0x1800035b2  jz      short loc_1800035BE
0x1800035b4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800035b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035be  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800035c5  test    rax, rax
0x1800035c8  jz      short loc_1800035DE
0x1800035ca  mov     r8d, 400h
0x1800035d0  lea     rdx, [rbp+13F0h+var_1430]
0x1800035d4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800035d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035de  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800035e5  test    rax, rax
0x1800035e8  jz      short loc_1800035F4
0x1800035ea  lea     rcx, [rsp+14F0h+var_14D0]
0x1800035ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035f4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800035fb  test    rax, rax
0x1800035fe  jz      short loc_180003611
0x180003600  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003605  jnz     short loc_180003611
0x180003607  lea     rcx, [rsp+14F0h+var_14D0]
0x18000360c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003611  cmp     [rsp+14F0h+var_14C8], r13d
0x180003616  jl      short loc_18000362A
0x180003618  mov     ecx, 8000FFFFh; this
0x18000361d  mov     [rsp+14F0h+var_14C8], ecx
0x180003621  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003626  mov     [rsp+14F0h+var_14C4], eax
0x18000362a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180003631  jnz     short loc_180003652
0x180003633  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000363a  test    rax, rax
0x18000363d  jz      short loc_180003648
0x18000363f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003644  test    al, al
0x180003646  jmp     short loc_180003650
0x180003648  call    cs:__imp_IsDebuggerPresent
0x18000364e  test    eax, eax
0x180003650  jz      short loc_180003659
0x180003652  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003657  jz      short loc_18000367F
0x180003659  mov     rax, cs:g_pfnResultLoggingCallback
0x180003660  test    rax, rax
0x180003663  jz      short loc_1800036D8
0x180003665  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000366c  jnz     short loc_1800036D8
0x18000366e  xor     r8d, r8d
0x180003671  lea     rcx, [rsp+14F0h+var_14D0]
0x180003676  xor     edx, edx
0x180003678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000367d  jmp     short loc_1800036D8
0x18000367f  mov     rax, cs:g_pfnResultLoggingCallback
0x180003686  mov     ebx, 800h
0x18000368b  test    rax, rax
0x18000368e  jz      short loc_1800036AD
0x180003690  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003697  jnz     short loc_1800036AD
0x180003699  mov     r8d, ebx
0x18000369c  lea     rdx, [rbp+13F0h+OutputString]
0x1800036a3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800036a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036ad  cmp     [rbp+13F0h+OutputString], r13w
0x1800036b5  jnz     short loc_1800036CB
0x1800036b7  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800036bc  mov     rdx, rbx; unsigned __int16 *
0x1800036bf  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800036c6  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800036cb  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800036d2  call    cs:__imp_OutputDebugStringW
0x1800036d8  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800036dd  jnz     short loc_1800036E8
0x1800036df  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800036e6  jz      short loc_1800036F9
0x1800036e8  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800036ef  test    rax, rax
0x1800036f2  jz      short loc_1800036F9
0x1800036f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036f9  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800036fe  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
