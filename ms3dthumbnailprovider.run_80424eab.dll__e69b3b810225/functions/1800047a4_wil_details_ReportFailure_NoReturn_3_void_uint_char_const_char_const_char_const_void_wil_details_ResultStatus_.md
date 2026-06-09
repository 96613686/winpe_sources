# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800047a4`
- end: `0x180004a0d`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `617`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180004558`

## callees

- `0x180002954`
- `0x1800047a4`
- `0x1800065f4`
- `0x180006e5c`
- `0x180007e00`
- `0x180009820`
- `0x18000a270`
- `0x18000b010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x1800049da`
- `KERNEL32!OutputDebugStringW` at `0x1800049da`
- `KERNEL32!IsDebuggerPresent` at `0x180004950`
- `KERNEL32!IsDebuggerPresent` at `0x180004950`
- `KERNEL32!GetCurrentThreadId` at `0x180004846`
- `KERNEL32!GetCurrentThreadId` at `0x180004846`

## string_xrefs

- `0x180004850`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  int v9; // edx
  int v10; // edi
  int v11; // ecx
  const struct wil::FailureInfo *v12; // rdx
  __int64 v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v10 = wil::details::RecordFailFast((wil::details *)(unsigned int)v18, v9);
  v16 = 3;
  v11 = 0;
  if ( a7[2] == 1 )
    v11 = 8;
  v17 = v11;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h";
  v26 = a2;
  v27 = v10;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
  {
    v18 = -2147418113;
    v19 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v12);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( (v17 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v13);
  }
  wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x1800047a4  mov     [rsp-8+arg_10], rbx
0x1800047a9  mov     [rsp-8+arg_18], rsi
0x1800047ae  push    rbp
0x1800047af  push    rdi
0x1800047b0  push    r12
0x1800047b2  push    r14
0x1800047b4  push    r15
0x1800047b6  lea     rbp, [rsp-13C0h]
0x1800047be  mov     eax, 14C0h
0x1800047c3  call    _alloca_probe
0x1800047c8  sub     rsp, rax
0x1800047cb  mov     r14d, edx
0x1800047ce  mov     r15, rcx
0x1800047d1  mov     rsi, [rbp+13E0h+arg_28]
0x1800047d8  xor     edx, edx; Val
0x1800047da  mov     r8d, 98h; Size
0x1800047e0  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x1800047e5  call    memset_0
0x1800047ea  nop
0x1800047eb  xor     r12d, r12d
0x1800047ee  mov     [rbp+13E0h+OutputString], r12w
0x1800047f6  mov     [rbp+13E0h+var_1420], r12b
0x1800047fa  mov     rbx, [rbp+13E0h+arg_30]
0x180004801  mov     ecx, [rbx]; this
0x180004803  mov     [rsp+14E0h+var_14B8], ecx
0x180004807  mov     eax, [rbx+4]
0x18000480a  mov     [rsp+14E0h+var_14B4], eax
0x18000480e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004813  mov     edi, eax
0x180004815  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x18000481d  mov     ecx, r12d
0x180004820  lea     eax, [r12+8]
0x180004825  cmp     dword ptr [rbx+8], 1
0x180004829  cmovz   ecx, eax
0x18000482c  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x180004830  lea     ecx, [rax-7]
0x180004833  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000483b  inc     ecx
0x18000483d  mov     [rsp+14E0h+var_14B0], ecx
0x180004841  mov     [rsp+14E0h+var_14A8], r12
0x180004846  call    cs:__imp_GetCurrentThreadId
0x18000484c  mov     [rsp+14E0h+var_14A0], eax
0x180004850  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004857  mov     [rsp+14E0h+var_1488], rax
0x18000485c  mov     [rsp+14E0h+var_1480], r14d
0x180004861  mov     [rsp+14E0h+var_147C], edi
0x180004865  mov     [rsp+14E0h+var_1498], r12
0x18000486a  mov     [rsp+14E0h+var_1490], r12
0x18000486f  mov     [rbp+13E0h+var_1438], rsi
0x180004873  mov     [rbp+13E0h+var_1430], r15
0x180004877  mov     [rsp+14E0h+var_1478], r12
0x18000487c  xorps   xmm0, xmm0
0x18000487f  xor     eax, eax
0x180004881  movups  [rbp+13E0h+var_1458], xmm0
0x180004885  mov     [rbp+13E0h+var_1448], rax
0x180004889  xorps   xmm1, xmm1
0x18000488c  movups  [rsp+14E0h+var_1470], xmm1
0x180004891  mov     [rbp+13E0h+var_1460], rax
0x180004895  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000489c  test    rax, rax
0x18000489f  jz      short loc_1800048AC
0x1800048a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048a6  mov     [rbp+13E0h+var_1440], rax
0x1800048aa  jmp     short loc_1800048B0
0x1800048ac  mov     [rbp+13E0h+var_1440], r12
0x1800048b0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800048b7  test    rax, rax
0x1800048ba  jz      short loc_1800048C6
0x1800048bc  lea     rcx, [rsp+14E0h+var_14C0]
0x1800048c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048c6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800048cd  test    rax, rax
0x1800048d0  jz      short loc_1800048E6
0x1800048d2  mov     r8d, 400h
0x1800048d8  lea     rdx, [rbp+13E0h+var_1420]
0x1800048dc  lea     rcx, [rsp+14E0h+var_14C0]
0x1800048e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048e6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800048ed  test    rax, rax
0x1800048f0  jz      short loc_1800048FC
0x1800048f2  lea     rcx, [rsp+14E0h+var_14C0]
0x1800048f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048fc  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004903  test    rax, rax
0x180004906  jz      short loc_180004919
0x180004908  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x18000490d  jnz     short loc_180004919
0x18000490f  lea     rcx, [rsp+14E0h+var_14C0]
0x180004914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004919  cmp     [rsp+14E0h+var_14B8], r12d
0x18000491e  jl      short loc_180004932
0x180004920  mov     ecx, 8000FFFFh; this
0x180004925  mov     [rsp+14E0h+var_14B8], ecx
0x180004929  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000492e  mov     [rsp+14E0h+var_14B4], eax
0x180004932  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180004939  jnz     short loc_18000495A
0x18000493b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004942  test    rax, rax
0x180004945  jz      short loc_180004950
0x180004947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000494c  test    al, al
0x18000494e  jmp     short loc_180004958
0x180004950  call    cs:__imp_IsDebuggerPresent
0x180004956  test    eax, eax
0x180004958  jz      short loc_180004961
0x18000495a  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x18000495f  jz      short loc_180004987
0x180004961  mov     rax, cs:g_pfnResultLoggingCallback
0x180004968  test    rax, rax
0x18000496b  jz      short loc_1800049E0
0x18000496d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004974  jnz     short loc_1800049E0
0x180004976  xor     r8d, r8d
0x180004979  xor     edx, edx
0x18000497b  lea     rcx, [rsp+14E0h+var_14C0]
0x180004980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004985  jmp     short loc_1800049E0
0x180004987  mov     ebx, 800h
0x18000498c  mov     rax, cs:g_pfnResultLoggingCallback
0x180004993  test    rax, rax
0x180004996  jz      short loc_1800049B5
0x180004998  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000499f  jnz     short loc_1800049B5
0x1800049a1  mov     r8d, ebx
0x1800049a4  lea     rdx, [rbp+13E0h+OutputString]
0x1800049ab  lea     rcx, [rsp+14E0h+var_14C0]
0x1800049b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049b5  cmp     [rbp+13E0h+OutputString], r12w
0x1800049bd  jnz     short loc_1800049D3
0x1800049bf  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x1800049c4  mov     rdx, rbx; unsigned __int16 *
0x1800049c7  lea     rcx, [rbp+13E0h+OutputString]; this
0x1800049ce  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800049d3  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x1800049da  call    cs:__imp_OutputDebugStringW
0x1800049e0  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x1800049e5  jnz     short loc_1800049F0
0x1800049e7  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800049ee  jz      short loc_180004A02
0x1800049f0  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800049f7  test    rax, rax
0x1800049fa  jz      short loc_180004A02
0x1800049fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a01  nop
0x180004a02  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180004a07  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
