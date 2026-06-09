# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800091dc`
- end: `0x180009455`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180008f88`

## callees

- `0x180002b70`
- `0x1800091dc`
- `0x18000a03c`
- `0x18000a70c`
- `0x18000bc80`
- `0x18000d192`
- `0x18000d250`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000938d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000938d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000941d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000941d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000927d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000927d`

## string_xrefs

- `0x180009298`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1800091dc  mov     [rsp-8+arg_10], rbx
0x1800091e1  mov     [rsp-8+arg_18], rsi
0x1800091e6  push    rbp
0x1800091e7  push    rdi
0x1800091e8  push    r12
0x1800091ea  push    r14
0x1800091ec  push    r15
0x1800091ee  lea     rbp, [rsp-13C0h]
0x1800091f6  mov     eax, 14C0h
0x1800091fb  call    _alloca_probe
0x180009200  sub     rsp, rax
0x180009203  mov     rsi, [rbp+13E0h+arg_28]
0x18000920a  mov     r14d, edx
0x18000920d  mov     r15, rcx
0x180009210  xor     edx, edx; Val
0x180009212  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x180009217  mov     r8d, 98h; Size
0x18000921d  call    memset_0
0x180009222  mov     rbx, [rbp+13E0h+arg_30]
0x180009229  xor     r12d, r12d
0x18000922c  mov     [rbp+13E0h+OutputString], r12w
0x180009234  mov     [rbp+13E0h+var_1420], r12b
0x180009238  mov     ecx, [rbx]; this
0x18000923a  mov     eax, [rbx+4]
0x18000923d  mov     [rsp+14E0h+var_14B8], ecx
0x180009241  mov     [rsp+14E0h+var_14B4], eax
0x180009245  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000924a  cmp     dword ptr [rbx+8], 1
0x18000924e  mov     edi, eax
0x180009250  lea     eax, [r12+8]
0x180009255  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x18000925d  mov     ecx, r12d
0x180009260  cmovz   ecx, eax
0x180009263  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x180009267  lea     ecx, [rax-7]
0x18000926a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180009272  inc     ecx
0x180009274  mov     [rsp+14E0h+var_14A8], r12
0x180009279  mov     [rsp+14E0h+var_14B0], ecx
0x18000927d  call    cs:__imp_GetCurrentThreadId
0x180009284  nop     dword ptr [rax+rax+00h]
0x180009289  xorps   xmm0, xmm0
0x18000928c  mov     [rsp+14E0h+var_1480], r14d
0x180009291  mov     [rsp+14E0h+var_14A0], eax
0x180009295  xorps   xmm1, xmm1
0x180009298  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000929f  mov     [rsp+14E0h+var_147C], edi
0x1800092a3  mov     [rsp+14E0h+var_1488], rax
0x1800092a8  xor     eax, eax
0x1800092aa  mov     [rbp+13E0h+var_1448], rax
0x1800092ae  mov     [rbp+13E0h+var_1460], rax
0x1800092b2  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800092b9  mov     [rsp+14E0h+var_1498], r12
0x1800092be  mov     [rsp+14E0h+var_1490], r12
0x1800092c3  mov     [rbp+13E0h+var_1438], rsi
0x1800092c7  mov     [rbp+13E0h+var_1430], r15
0x1800092cb  mov     [rsp+14E0h+var_1478], r12
0x1800092d0  movups  [rbp+13E0h+var_1458], xmm0
0x1800092d4  movups  [rsp+14E0h+var_1470], xmm1
0x1800092d9  test    rax, rax
0x1800092dc  jz      short loc_1800092E9
0x1800092de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092e3  mov     [rbp+13E0h+var_1440], rax
0x1800092e7  jmp     short loc_1800092ED
0x1800092e9  mov     [rbp+13E0h+var_1440], r12
0x1800092ed  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800092f4  test    rax, rax
0x1800092f7  jz      short loc_180009303
0x1800092f9  lea     rcx, [rsp+14E0h+var_14C0]
0x1800092fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009303  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000930a  test    rax, rax
0x18000930d  jz      short loc_180009323
0x18000930f  mov     r8d, 400h
0x180009315  lea     rdx, [rbp+13E0h+var_1420]
0x180009319  lea     rcx, [rsp+14E0h+var_14C0]
0x18000931e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009323  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000932a  test    rax, rax
0x18000932d  jz      short loc_180009339
0x18000932f  lea     rcx, [rsp+14E0h+var_14C0]
0x180009334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009339  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009340  test    rax, rax
0x180009343  jz      short loc_180009356
0x180009345  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x18000934a  jnz     short loc_180009356
0x18000934c  lea     rcx, [rsp+14E0h+var_14C0]
0x180009351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009356  cmp     [rsp+14E0h+var_14B8], r12d
0x18000935b  jl      short loc_18000936F
0x18000935d  mov     ecx, 8000FFFFh; this
0x180009362  mov     [rsp+14E0h+var_14B8], ecx
0x180009366  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000936b  mov     [rsp+14E0h+var_14B4], eax
0x18000936f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180009376  jnz     short loc_18000939D
0x180009378  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000937f  test    rax, rax
0x180009382  jz      short loc_18000938D
0x180009384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009389  test    al, al
0x18000938b  jmp     short loc_18000939B
0x18000938d  call    cs:__imp_IsDebuggerPresent
0x180009394  nop     dword ptr [rax+rax+00h]
0x180009399  test    eax, eax
0x18000939b  jz      short loc_1800093A4
0x18000939d  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1800093a2  jz      short loc_1800093CA
0x1800093a4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800093ab  test    rax, rax
0x1800093ae  jz      short loc_180009429
0x1800093b0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800093b7  jnz     short loc_180009429
0x1800093b9  xor     r8d, r8d
0x1800093bc  lea     rcx, [rsp+14E0h+var_14C0]
0x1800093c1  xor     edx, edx
0x1800093c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093c8  jmp     short loc_180009429
0x1800093ca  mov     rax, cs:g_pfnResultLoggingCallback
0x1800093d1  mov     ebx, 800h
0x1800093d6  test    rax, rax
0x1800093d9  jz      short loc_1800093F8
0x1800093db  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800093e2  jnz     short loc_1800093F8
0x1800093e4  mov     r8d, ebx
0x1800093e7  lea     rdx, [rbp+13E0h+OutputString]
0x1800093ee  lea     rcx, [rsp+14E0h+var_14C0]
0x1800093f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093f8  cmp     [rbp+13E0h+OutputString], r12w
0x180009400  jnz     short loc_180009416
0x180009402  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180009407  mov     rdx, rbx; unsigned __int16 *
0x18000940a  lea     rcx, [rbp+13E0h+OutputString]; this
0x180009411  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180009416  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x18000941d  call    cs:__imp_OutputDebugStringW
0x180009424  nop     dword ptr [rax+rax+00h]
0x180009429  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x18000942e  jnz     short loc_180009439
0x180009430  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180009437  jz      short loc_18000944A
0x180009439  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180009440  test    rax, rax
0x180009443  jz      short loc_18000944A
0x180009445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000944a  lea     rcx, [rsp+14E0h+var_14C0]; this
0x18000944f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
