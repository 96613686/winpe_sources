# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x1800036b8`
- end: `0x180003931`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, __int64, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800032c4`

## callees

- `0x1800021f0`
- `0x1800036b8`
- `0x180005054`
- `0x1800057f4`
- `0x180006050`
- `0x180007260`
- `0x1800151e0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003771`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003771`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003874`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003874`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800038fe`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800038fe`

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
0x1800036b8  mov     [rsp-8+arg_18], rbx
0x1800036bd  push    rbp
0x1800036be  push    rsi
0x1800036bf  push    rdi
0x1800036c0  push    r12
0x1800036c2  push    r13
0x1800036c4  push    r14
0x1800036c6  push    r15
0x1800036c8  lea     rbp, [rsp-13C0h]
0x1800036d0  mov     eax, 14C0h
0x1800036d5  call    _alloca_probe
0x1800036da  sub     rsp, rax
0x1800036dd  mov     r14, r8
0x1800036e0  mov     esi, edx
0x1800036e2  mov     rdi, rcx
0x1800036e5  mov     r15, [rbp+13F0h+arg_28]
0x1800036ec  xor     edx, edx; Val
0x1800036ee  mov     r8d, 98h; Size
0x1800036f4  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800036f9  call    memset_0
0x1800036fe  nop
0x1800036ff  xor     r13d, r13d
0x180003702  mov     [rbp+13F0h+OutputString], r13w
0x18000370a  mov     [rbp+13F0h+var_1430], r13b
0x18000370e  mov     rbx, [rbp+13F0h+arg_30]
0x180003715  mov     ecx, [rbx]; this
0x180003717  mov     [rsp+14F0h+var_14C8], ecx
0x18000371b  mov     eax, [rbx+4]
0x18000371e  mov     [rsp+14F0h+var_14C4], eax
0x180003722  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180003727  mov     r12d, eax
0x18000372a  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180003732  mov     ecx, r13d
0x180003735  lea     eax, [r13+8]
0x180003739  cmp     dword ptr [rbx+8], 1
0x18000373d  cmovz   ecx, eax
0x180003740  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003744  lea     ecx, [rax-7]
0x180003747  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000374f  inc     ecx
0x180003751  mov     [rsp+14F0h+var_14C0], ecx
0x180003755  mov     rcx, [rbp+13F0h+arg_38]
0x18000375c  test    rcx, rcx
0x18000375f  jz      short loc_18000376C
0x180003761  cmp     [rcx], r13w
0x180003765  mov     [rsp+14F0h+var_14B8], rcx
0x18000376a  jnz     short loc_180003771
0x18000376c  mov     [rsp+14F0h+var_14B8], r13
0x180003771  call    cs:__imp_GetCurrentThreadId
0x180003777  mov     [rsp+14F0h+var_14B0], eax
0x18000377b  mov     [rsp+14F0h+var_1498], r14
0x180003780  mov     [rsp+14F0h+var_1490], esi
0x180003784  mov     [rsp+14F0h+var_148C], r12d
0x180003789  mov     [rsp+14F0h+var_14A8], r13
0x18000378e  mov     [rsp+14F0h+var_14A0], r13
0x180003793  mov     [rbp+13F0h+var_1448], r15
0x180003797  mov     [rbp+13F0h+var_1440], rdi
0x18000379b  mov     [rsp+14F0h+var_1488], r13
0x1800037a0  xorps   xmm0, xmm0
0x1800037a3  xor     eax, eax
0x1800037a5  movups  [rbp+13F0h+var_1468], xmm0
0x1800037a9  mov     [rbp+13F0h+var_1458], rax
0x1800037ad  xorps   xmm1, xmm1
0x1800037b0  movups  [rsp+14F0h+var_1480], xmm1
0x1800037b5  mov     [rbp+13F0h+var_1470], rax
0x1800037b9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800037c0  test    rax, rax
0x1800037c3  jz      short loc_1800037D0
0x1800037c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037ca  mov     [rbp+13F0h+var_1450], rax
0x1800037ce  jmp     short loc_1800037D4
0x1800037d0  mov     [rbp+13F0h+var_1450], r13
0x1800037d4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800037db  test    rax, rax
0x1800037de  jz      short loc_1800037EA
0x1800037e0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800037e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037ea  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800037f1  test    rax, rax
0x1800037f4  jz      short loc_18000380A
0x1800037f6  mov     r8d, 400h
0x1800037fc  lea     rdx, [rbp+13F0h+var_1430]
0x180003800  lea     rcx, [rsp+14F0h+var_14D0]
0x180003805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000380a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003811  test    rax, rax
0x180003814  jz      short loc_180003820
0x180003816  lea     rcx, [rsp+14F0h+var_14D0]
0x18000381b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003820  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003827  test    rax, rax
0x18000382a  jz      short loc_18000383D
0x18000382c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003831  jnz     short loc_18000383D
0x180003833  lea     rcx, [rsp+14F0h+var_14D0]
0x180003838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000383d  cmp     [rsp+14F0h+var_14C8], r13d
0x180003842  jl      short loc_180003856
0x180003844  mov     ecx, 8000FFFFh; this
0x180003849  mov     [rsp+14F0h+var_14C8], ecx
0x18000384d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003852  mov     [rsp+14F0h+var_14C4], eax
0x180003856  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000385d  jnz     short loc_18000387E
0x18000385f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003866  test    rax, rax
0x180003869  jz      short loc_180003874
0x18000386b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003870  test    al, al
0x180003872  jmp     short loc_18000387C
0x180003874  call    cs:__imp_IsDebuggerPresent
0x18000387a  test    eax, eax
0x18000387c  jz      short loc_180003885
0x18000387e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003883  jz      short loc_1800038AB
0x180003885  mov     rax, cs:g_pfnResultLoggingCallback
0x18000388c  test    rax, rax
0x18000388f  jz      short loc_180003904
0x180003891  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003898  jnz     short loc_180003904
0x18000389a  xor     r8d, r8d
0x18000389d  xor     edx, edx
0x18000389f  lea     rcx, [rsp+14F0h+var_14D0]
0x1800038a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038a9  jmp     short loc_180003904
0x1800038ab  mov     ebx, 800h
0x1800038b0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800038b7  test    rax, rax
0x1800038ba  jz      short loc_1800038D9
0x1800038bc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800038c3  jnz     short loc_1800038D9
0x1800038c5  mov     r8d, ebx
0x1800038c8  lea     rdx, [rbp+13F0h+OutputString]
0x1800038cf  lea     rcx, [rsp+14F0h+var_14D0]
0x1800038d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038d9  cmp     [rbp+13F0h+OutputString], r13w
0x1800038e1  jnz     short loc_1800038F7
0x1800038e3  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800038e8  mov     rdx, rbx; wchar_t *
0x1800038eb  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800038f2  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800038f7  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800038fe  call    cs:__imp_OutputDebugStringW
0x180003904  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003909  jnz     short loc_180003914
0x18000390b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180003912  jz      short loc_180003926
0x180003914  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000391b  test    rax, rax
0x18000391e  jz      short loc_180003926
0x180003920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003925  nop
0x180003926  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000392b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
