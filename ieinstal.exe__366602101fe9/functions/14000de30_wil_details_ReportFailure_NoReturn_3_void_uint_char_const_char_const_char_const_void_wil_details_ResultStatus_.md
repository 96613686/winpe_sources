# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x14000de30`
- end: `0x14000e0a9`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14000dbdc`

## callees

- `0x140001af3`
- `0x14000abc0`
- `0x14000de30`
- `0x14000eb2c`
- `0x14000f1fc`
- `0x1400103d0`
- `0x140010a80`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000ded1`
- `KERNEL32!GetCurrentThreadId` at `0x14000ded1`
- `KERNEL32!IsDebuggerPresent` at `0x14000dfe1`
- `KERNEL32!IsDebuggerPresent` at `0x14000dfe1`
- `KERNEL32!OutputDebugStringW` at `0x14000e071`
- `KERNEL32!OutputDebugStringW` at `0x14000e071`

## string_xrefs

- `0x14000deec`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x14000de30  mov     [rsp-8+arg_10], rbx
0x14000de35  mov     [rsp-8+arg_18], rsi
0x14000de3a  push    rbp
0x14000de3b  push    rdi
0x14000de3c  push    r12
0x14000de3e  push    r14
0x14000de40  push    r15
0x14000de42  lea     rbp, [rsp-13C0h]
0x14000de4a  mov     eax, 14C0h
0x14000de4f  call    _alloca_probe
0x14000de54  sub     rsp, rax
0x14000de57  mov     rsi, [rbp+13E0h+arg_28]
0x14000de5e  mov     r14d, edx
0x14000de61  mov     r15, rcx
0x14000de64  xor     edx, edx; Val
0x14000de66  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x14000de6b  mov     r8d, 98h; Size
0x14000de71  call    memset_0
0x14000de76  mov     rbx, [rbp+13E0h+arg_30]
0x14000de7d  xor     r12d, r12d
0x14000de80  mov     [rbp+13E0h+OutputString], r12w
0x14000de88  mov     [rbp+13E0h+var_1420], r12b
0x14000de8c  mov     ecx, [rbx]; this
0x14000de8e  mov     eax, [rbx+4]
0x14000de91  mov     [rsp+14E0h+var_14B8], ecx
0x14000de95  mov     [rsp+14E0h+var_14B4], eax
0x14000de99  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000de9e  cmp     dword ptr [rbx+8], 1
0x14000dea2  mov     edi, eax
0x14000dea4  lea     eax, [r12+8]
0x14000dea9  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x14000deb1  mov     ecx, r12d
0x14000deb4  cmovz   ecx, eax
0x14000deb7  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x14000debb  lea     ecx, [rax-7]
0x14000debe  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000dec6  inc     ecx
0x14000dec8  mov     [rsp+14E0h+var_14A8], r12
0x14000decd  mov     [rsp+14E0h+var_14B0], ecx
0x14000ded1  call    cs:__imp_GetCurrentThreadId
0x14000ded8  nop     dword ptr [rax+rax+00h]
0x14000dedd  xorps   xmm0, xmm0
0x14000dee0  mov     [rsp+14E0h+var_1480], r14d
0x14000dee5  mov     [rsp+14E0h+var_14A0], eax
0x14000dee9  xorps   xmm1, xmm1
0x14000deec  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000def3  mov     [rsp+14E0h+var_147C], edi
0x14000def7  mov     [rsp+14E0h+var_1488], rax
0x14000defc  xor     eax, eax
0x14000defe  mov     [rbp+13E0h+var_1448], rax
0x14000df02  mov     [rbp+13E0h+var_1460], rax
0x14000df06  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000df0d  mov     [rsp+14E0h+var_1498], r12
0x14000df12  mov     [rsp+14E0h+var_1490], r12
0x14000df17  mov     [rbp+13E0h+var_1438], rsi
0x14000df1b  mov     [rbp+13E0h+var_1430], r15
0x14000df1f  mov     [rsp+14E0h+var_1478], r12
0x14000df24  movups  [rbp+13E0h+var_1458], xmm0
0x14000df28  movups  [rsp+14E0h+var_1470], xmm1
0x14000df2d  test    rax, rax
0x14000df30  jz      short loc_14000DF3D
0x14000df32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000df37  mov     [rbp+13E0h+var_1440], rax
0x14000df3b  jmp     short loc_14000DF41
0x14000df3d  mov     [rbp+13E0h+var_1440], r12
0x14000df41  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000df48  test    rax, rax
0x14000df4b  jz      short loc_14000DF57
0x14000df4d  lea     rcx, [rsp+14E0h+var_14C0]
0x14000df52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000df57  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000df5e  test    rax, rax
0x14000df61  jz      short loc_14000DF77
0x14000df63  mov     r8d, 400h
0x14000df69  lea     rdx, [rbp+13E0h+var_1420]
0x14000df6d  lea     rcx, [rsp+14E0h+var_14C0]
0x14000df72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000df77  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000df7e  test    rax, rax
0x14000df81  jz      short loc_14000DF8D
0x14000df83  lea     rcx, [rsp+14E0h+var_14C0]
0x14000df88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000df8d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000df94  test    rax, rax
0x14000df97  jz      short loc_14000DFAA
0x14000df99  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x14000df9e  jnz     short loc_14000DFAA
0x14000dfa0  lea     rcx, [rsp+14E0h+var_14C0]
0x14000dfa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dfaa  cmp     [rsp+14E0h+var_14B8], r12d
0x14000dfaf  jl      short loc_14000DFC3
0x14000dfb1  mov     ecx, 8000FFFFh; this
0x14000dfb6  mov     [rsp+14E0h+var_14B8], ecx
0x14000dfba  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000dfbf  mov     [rsp+14E0h+var_14B4], eax
0x14000dfc3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x14000dfca  jnz     short loc_14000DFF1
0x14000dfcc  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000dfd3  test    rax, rax
0x14000dfd6  jz      short loc_14000DFE1
0x14000dfd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dfdd  test    al, al
0x14000dfdf  jmp     short loc_14000DFEF
0x14000dfe1  call    cs:__imp_IsDebuggerPresent
0x14000dfe8  nop     dword ptr [rax+rax+00h]
0x14000dfed  test    eax, eax
0x14000dfef  jz      short loc_14000DFF8
0x14000dff1  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x14000dff6  jz      short loc_14000E01E
0x14000dff8  mov     rax, cs:g_pfnResultLoggingCallback
0x14000dfff  test    rax, rax
0x14000e002  jz      short loc_14000E07D
0x14000e004  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000e00b  jnz     short loc_14000E07D
0x14000e00d  xor     r8d, r8d
0x14000e010  lea     rcx, [rsp+14E0h+var_14C0]
0x14000e015  xor     edx, edx
0x14000e017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e01c  jmp     short loc_14000E07D
0x14000e01e  mov     rax, cs:g_pfnResultLoggingCallback
0x14000e025  mov     ebx, 800h
0x14000e02a  test    rax, rax
0x14000e02d  jz      short loc_14000E04C
0x14000e02f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000e036  jnz     short loc_14000E04C
0x14000e038  mov     r8d, ebx
0x14000e03b  lea     rdx, [rbp+13E0h+OutputString]
0x14000e042  lea     rcx, [rsp+14E0h+var_14C0]
0x14000e047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e04c  cmp     [rbp+13E0h+OutputString], r12w
0x14000e054  jnz     short loc_14000E06A
0x14000e056  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x14000e05b  mov     rdx, rbx; unsigned __int16 *
0x14000e05e  lea     rcx, [rbp+13E0h+OutputString]; this
0x14000e065  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000e06a  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x14000e071  call    cs:__imp_OutputDebugStringW
0x14000e078  nop     dword ptr [rax+rax+00h]
0x14000e07d  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x14000e082  jnz     short loc_14000E08D
0x14000e084  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x14000e08b  jz      short loc_14000E09E
0x14000e08d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000e094  test    rax, rax
0x14000e097  jz      short loc_14000E09E
0x14000e099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e09e  lea     rcx, [rsp+14E0h+var_14C0]; this
0x14000e0a3  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
