# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140002334`
- end: `0x14000259b`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `615`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400020e8`

## callees

- `0x1400017bf`
- `0x140002334`
- `0x1400033a4`
- `0x140003b3c`
- `0x140004260`
- `0x140004b20`
- `0x140004d60`
- `0x140005010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400023d5`
- `KERNEL32!GetCurrentThreadId` at `0x1400023d5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400024df`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400024df`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002569`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002569`

## string_xrefs

- `0x1400023ea`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  int v9; // eax
  int v10; // edx
  int v11; // eax
  int v12; // edi
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  __int64 v16; // rcx
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
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v21, v10);
  v18 = a7[2] == 1;
  v12 = v11;
  v19 = 3;
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
  v28 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h";
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
  {
    v21 = -2147418113;
    v22 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v15);
  }
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
  if ( (v20 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v16);
  }
  wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x140002334  mov     [rsp-8+arg_10], rbx
0x140002339  mov     [rsp-8+arg_18], rsi
0x14000233e  push    rbp
0x14000233f  push    rdi
0x140002340  push    r12
0x140002342  push    r14
0x140002344  push    r15
0x140002346  lea     rbp, [rsp-13C0h]
0x14000234e  mov     eax, 14C0h
0x140002353  call    _alloca_probe
0x140002358  sub     rsp, rax
0x14000235b  mov     rsi, [rbp+13E0h+arg_28]
0x140002362  mov     r14d, edx
0x140002365  mov     r15, rcx
0x140002368  xor     edx, edx; Val
0x14000236a  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x14000236f  mov     r8d, 98h; Size
0x140002375  call    memset_0
0x14000237a  mov     rbx, [rbp+13E0h+arg_30]
0x140002381  xor     r12d, r12d
0x140002384  mov     [rbp+13E0h+OutputString], r12w
0x14000238c  mov     [rbp+13E0h+var_1420], r12b
0x140002390  mov     ecx, [rbx]; this
0x140002392  mov     eax, [rbx+4]
0x140002395  mov     [rsp+14E0h+var_14B8], ecx
0x140002399  mov     [rsp+14E0h+var_14B4], eax
0x14000239d  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400023a2  cmp     dword ptr [rbx+8], 1
0x1400023a6  mov     edi, eax
0x1400023a8  lea     eax, [r12+8]
0x1400023ad  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x1400023b5  mov     ecx, r12d
0x1400023b8  cmovz   ecx, eax
0x1400023bb  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x1400023bf  lea     ecx, [rax-7]
0x1400023c2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400023ca  inc     ecx
0x1400023cc  mov     [rsp+14E0h+var_14A8], r12
0x1400023d1  mov     [rsp+14E0h+var_14B0], ecx
0x1400023d5  call    cs:__imp_GetCurrentThreadId
0x1400023db  xorps   xmm0, xmm0
0x1400023de  mov     [rsp+14E0h+var_1480], r14d
0x1400023e3  mov     [rsp+14E0h+var_14A0], eax
0x1400023e7  xorps   xmm1, xmm1
0x1400023ea  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400023f1  mov     [rsp+14E0h+var_147C], edi
0x1400023f5  mov     [rsp+14E0h+var_1488], rax
0x1400023fa  xor     eax, eax
0x1400023fc  mov     [rbp+13E0h+var_1448], rax
0x140002400  mov     [rbp+13E0h+var_1460], rax
0x140002404  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000240b  mov     [rsp+14E0h+var_1498], r12
0x140002410  mov     [rsp+14E0h+var_1490], r12
0x140002415  mov     [rbp+13E0h+var_1438], rsi
0x140002419  mov     [rbp+13E0h+var_1430], r15
0x14000241d  mov     [rsp+14E0h+var_1478], r12
0x140002422  movups  [rbp+13E0h+var_1458], xmm0
0x140002426  movups  [rsp+14E0h+var_1470], xmm1
0x14000242b  test    rax, rax
0x14000242e  jz      short loc_14000243B
0x140002430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002435  mov     [rbp+13E0h+var_1440], rax
0x140002439  jmp     short loc_14000243F
0x14000243b  mov     [rbp+13E0h+var_1440], r12
0x14000243f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002446  test    rax, rax
0x140002449  jz      short loc_140002455
0x14000244b  lea     rcx, [rsp+14E0h+var_14C0]
0x140002450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002455  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000245c  test    rax, rax
0x14000245f  jz      short loc_140002475
0x140002461  mov     r8d, 400h
0x140002467  lea     rdx, [rbp+13E0h+var_1420]
0x14000246b  lea     rcx, [rsp+14E0h+var_14C0]
0x140002470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002475  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000247c  test    rax, rax
0x14000247f  jz      short loc_14000248B
0x140002481  lea     rcx, [rsp+14E0h+var_14C0]
0x140002486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000248b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002492  test    rax, rax
0x140002495  jz      short loc_1400024A8
0x140002497  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x14000249c  jnz     short loc_1400024A8
0x14000249e  lea     rcx, [rsp+14E0h+var_14C0]
0x1400024a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400024a8  cmp     [rsp+14E0h+var_14B8], r12d
0x1400024ad  jl      short loc_1400024C1
0x1400024af  mov     ecx, 8000FFFFh; this
0x1400024b4  mov     [rsp+14E0h+var_14B8], ecx
0x1400024b8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400024bd  mov     [rsp+14E0h+var_14B4], eax
0x1400024c1  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1400024c8  jnz     short loc_1400024E9
0x1400024ca  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400024d1  test    rax, rax
0x1400024d4  jz      short loc_1400024DF
0x1400024d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400024db  test    al, al
0x1400024dd  jmp     short loc_1400024E7
0x1400024df  call    cs:__imp_IsDebuggerPresent
0x1400024e5  test    eax, eax
0x1400024e7  jz      short loc_1400024F0
0x1400024e9  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1400024ee  jz      short loc_140002516
0x1400024f0  mov     rax, cs:g_pfnResultLoggingCallback
0x1400024f7  test    rax, rax
0x1400024fa  jz      short loc_14000256F
0x1400024fc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140002503  jnz     short loc_14000256F
0x140002505  xor     r8d, r8d
0x140002508  lea     rcx, [rsp+14E0h+var_14C0]
0x14000250d  xor     edx, edx
0x14000250f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002514  jmp     short loc_14000256F
0x140002516  mov     rax, cs:g_pfnResultLoggingCallback
0x14000251d  mov     ebx, 800h
0x140002522  test    rax, rax
0x140002525  jz      short loc_140002544
0x140002527  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000252e  jnz     short loc_140002544
0x140002530  mov     r8d, ebx
0x140002533  lea     rdx, [rbp+13E0h+OutputString]
0x14000253a  lea     rcx, [rsp+14E0h+var_14C0]
0x14000253f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002544  cmp     [rbp+13E0h+OutputString], r12w
0x14000254c  jnz     short loc_140002562
0x14000254e  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x140002553  mov     rdx, rbx; unsigned __int16 *
0x140002556  lea     rcx, [rbp+13E0h+OutputString]; this
0x14000255d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140002562  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x140002569  call    cs:__imp_OutputDebugStringW
0x14000256f  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x140002574  jnz     short loc_14000257F
0x140002576  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x14000257d  jz      short loc_140002590
0x14000257f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002586  test    rax, rax
0x140002589  jz      short loc_140002590
0x14000258b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002590  lea     rcx, [rsp+14E0h+var_14C0]; this
0x140002595  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
