# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180005570`
- end: `0x1800057e9`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180004d4c`

## callees

- `0x180003940`
- `0x180005570`
- `0x18000cd54`
- `0x18000d5a0`
- `0x18000f280`
- `0x180014e80`
- `0x180020830`
- `0x180023010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x18000572c`
- `KERNEL32!IsDebuggerPresent` at `0x18000572c`
- `KERNEL32!OutputDebugStringW` at `0x1800057b6`
- `KERNEL32!OutputDebugStringW` at `0x1800057b6`
- `KERNEL32!GetCurrentThreadId` at `0x180005629`
- `KERNEL32!GetCurrentThreadId` at `0x180005629`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
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
0x180005570  mov     [rsp-8+arg_18], rbx
0x180005575  push    rbp
0x180005576  push    rsi
0x180005577  push    rdi
0x180005578  push    r12
0x18000557a  push    r13
0x18000557c  push    r14
0x18000557e  push    r15
0x180005580  lea     rbp, [rsp-13C0h]
0x180005588  mov     eax, 14C0h
0x18000558d  call    _alloca_probe
0x180005592  sub     rsp, rax
0x180005595  mov     r14, r8
0x180005598  mov     esi, edx
0x18000559a  mov     rdi, rcx
0x18000559d  mov     r15, [rbp+13F0h+arg_28]
0x1800055a4  xor     edx, edx; Val
0x1800055a6  mov     r8d, 98h; Size
0x1800055ac  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800055b1  call    memset_0
0x1800055b6  nop
0x1800055b7  xor     r13d, r13d
0x1800055ba  mov     [rbp+13F0h+OutputString], r13w
0x1800055c2  mov     [rbp+13F0h+var_1430], r13b
0x1800055c6  mov     rbx, [rbp+13F0h+arg_30]
0x1800055cd  mov     ecx, [rbx]; this
0x1800055cf  mov     [rsp+14F0h+var_14C8], ecx
0x1800055d3  mov     eax, [rbx+4]
0x1800055d6  mov     [rsp+14F0h+var_14C4], eax
0x1800055da  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800055df  mov     r12d, eax
0x1800055e2  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800055ea  mov     ecx, r13d
0x1800055ed  lea     eax, [r13+8]
0x1800055f1  cmp     dword ptr [rbx+8], 1
0x1800055f5  cmovz   ecx, eax
0x1800055f8  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800055fc  lea     ecx, [rax-7]
0x1800055ff  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005607  inc     ecx
0x180005609  mov     [rsp+14F0h+var_14C0], ecx
0x18000560d  mov     rcx, [rbp+13F0h+arg_38]
0x180005614  test    rcx, rcx
0x180005617  jz      short loc_180005624
0x180005619  cmp     [rcx], r13w
0x18000561d  mov     [rsp+14F0h+var_14B8], rcx
0x180005622  jnz     short loc_180005629
0x180005624  mov     [rsp+14F0h+var_14B8], r13
0x180005629  call    cs:__imp_GetCurrentThreadId
0x18000562f  mov     [rsp+14F0h+var_14B0], eax
0x180005633  mov     [rsp+14F0h+var_1498], r14
0x180005638  mov     [rsp+14F0h+var_1490], esi
0x18000563c  mov     [rsp+14F0h+var_148C], r12d
0x180005641  mov     [rsp+14F0h+var_14A8], r13
0x180005646  mov     [rsp+14F0h+var_14A0], r13
0x18000564b  mov     [rbp+13F0h+var_1448], r15
0x18000564f  mov     [rbp+13F0h+var_1440], rdi
0x180005653  mov     [rsp+14F0h+var_1488], r13
0x180005658  xorps   xmm0, xmm0
0x18000565b  xor     eax, eax
0x18000565d  movups  [rbp+13F0h+var_1468], xmm0
0x180005661  mov     [rbp+13F0h+var_1458], rax
0x180005665  xorps   xmm1, xmm1
0x180005668  movups  [rsp+14F0h+var_1480], xmm1
0x18000566d  mov     [rbp+13F0h+var_1470], rax
0x180005671  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005678  test    rax, rax
0x18000567b  jz      short loc_180005688
0x18000567d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005682  mov     [rbp+13F0h+var_1450], rax
0x180005686  jmp     short loc_18000568C
0x180005688  mov     [rbp+13F0h+var_1450], r13
0x18000568c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005693  test    rax, rax
0x180005696  jz      short loc_1800056A2
0x180005698  lea     rcx, [rsp+14F0h+var_14D0]
0x18000569d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056a2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800056a9  test    rax, rax
0x1800056ac  jz      short loc_1800056C2
0x1800056ae  mov     r8d, 400h
0x1800056b4  lea     rdx, [rbp+13F0h+var_1430]
0x1800056b8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800056bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056c2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800056c9  test    rax, rax
0x1800056cc  jz      short loc_1800056D8
0x1800056ce  lea     rcx, [rsp+14F0h+var_14D0]
0x1800056d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056d8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800056df  test    rax, rax
0x1800056e2  jz      short loc_1800056F5
0x1800056e4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800056e9  jnz     short loc_1800056F5
0x1800056eb  lea     rcx, [rsp+14F0h+var_14D0]
0x1800056f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056f5  cmp     [rsp+14F0h+var_14C8], r13d
0x1800056fa  jl      short loc_18000570E
0x1800056fc  mov     ecx, 8000FFFFh; this
0x180005701  mov     [rsp+14F0h+var_14C8], ecx
0x180005705  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000570a  mov     [rsp+14F0h+var_14C4], eax
0x18000570e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180005715  jnz     short loc_180005736
0x180005717  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000571e  test    rax, rax
0x180005721  jz      short loc_18000572C
0x180005723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005728  test    al, al
0x18000572a  jmp     short loc_180005734
0x18000572c  call    cs:__imp_IsDebuggerPresent
0x180005732  test    eax, eax
0x180005734  jz      short loc_18000573D
0x180005736  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000573b  jz      short loc_180005763
0x18000573d  mov     rax, cs:g_pfnResultLoggingCallback
0x180005744  test    rax, rax
0x180005747  jz      short loc_1800057BC
0x180005749  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180005750  jnz     short loc_1800057BC
0x180005752  xor     r8d, r8d
0x180005755  xor     edx, edx
0x180005757  lea     rcx, [rsp+14F0h+var_14D0]
0x18000575c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005761  jmp     short loc_1800057BC
0x180005763  mov     ebx, 800h
0x180005768  mov     rax, cs:g_pfnResultLoggingCallback
0x18000576f  test    rax, rax
0x180005772  jz      short loc_180005791
0x180005774  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000577b  jnz     short loc_180005791
0x18000577d  mov     r8d, ebx
0x180005780  lea     rdx, [rbp+13F0h+OutputString]
0x180005787  lea     rcx, [rsp+14F0h+var_14D0]
0x18000578c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005791  cmp     [rbp+13F0h+OutputString], r13w
0x180005799  jnz     short loc_1800057AF
0x18000579b  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800057a0  mov     rdx, rbx; unsigned __int16 *
0x1800057a3  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800057aa  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800057af  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800057b6  call    cs:__imp_OutputDebugStringW
0x1800057bc  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800057c1  jnz     short loc_1800057CC
0x1800057c3  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800057ca  jz      short loc_1800057DE
0x1800057cc  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800057d3  test    rax, rax
0x1800057d6  jz      short loc_1800057DE
0x1800057d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057dd  nop
0x1800057de  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800057e3  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
