# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180003fac`
- end: `0x180004237`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003bb0`

## callees

- `0x180003fac`
- `0x180005534`
- `0x180005e24`
- `0x180006610`
- `0x18000768c`
- `0x18003586a`
- `0x180035960`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004065`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004065`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000416e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000416e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800041fe`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800041fe`

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
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
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
0x180003fac  mov     [rsp-8+arg_18], rbx
0x180003fb1  push    rbp
0x180003fb2  push    rsi
0x180003fb3  push    rdi
0x180003fb4  push    r12
0x180003fb6  push    r13
0x180003fb8  push    r14
0x180003fba  push    r15
0x180003fbc  lea     rbp, [rsp-13C0h]
0x180003fc4  mov     eax, 14C0h
0x180003fc9  call    _alloca_probe
0x180003fce  sub     rsp, rax
0x180003fd1  mov     r14, r8
0x180003fd4  mov     esi, edx
0x180003fd6  mov     rdi, rcx
0x180003fd9  mov     r15, [rbp+13F0h+arg_28]
0x180003fe0  xor     edx, edx; Val
0x180003fe2  mov     r8d, 98h; Size
0x180003fe8  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003fed  call    memset_0
0x180003ff2  nop
0x180003ff3  xor     r13d, r13d
0x180003ff6  mov     [rbp+13F0h+OutputString], r13w
0x180003ffe  mov     [rbp+13F0h+var_1430], r13b
0x180004002  mov     rbx, [rbp+13F0h+arg_30]
0x180004009  mov     ecx, [rbx]; this
0x18000400b  mov     [rsp+14F0h+var_14C8], ecx
0x18000400f  mov     eax, [rbx+4]
0x180004012  mov     [rsp+14F0h+var_14C4], eax
0x180004016  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000401b  mov     r12d, eax
0x18000401e  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180004026  mov     ecx, r13d
0x180004029  lea     eax, [r13+8]
0x18000402d  cmp     dword ptr [rbx+8], 1
0x180004031  cmovz   ecx, eax
0x180004034  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180004038  lea     ecx, [rax-7]
0x18000403b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004043  inc     ecx
0x180004045  mov     [rsp+14F0h+var_14C0], ecx
0x180004049  mov     rcx, [rbp+13F0h+arg_38]
0x180004050  test    rcx, rcx
0x180004053  jz      short loc_180004060
0x180004055  cmp     [rcx], r13w
0x180004059  mov     [rsp+14F0h+var_14B8], rcx
0x18000405e  jnz     short loc_180004065
0x180004060  mov     [rsp+14F0h+var_14B8], r13
0x180004065  call    cs:__imp_GetCurrentThreadId
0x18000406c  nop     dword ptr [rax+rax+00h]
0x180004071  mov     [rsp+14F0h+var_14B0], eax
0x180004075  mov     [rsp+14F0h+var_1498], r14
0x18000407a  mov     [rsp+14F0h+var_1490], esi
0x18000407e  mov     [rsp+14F0h+var_148C], r12d
0x180004083  mov     [rsp+14F0h+var_14A8], r13
0x180004088  mov     [rsp+14F0h+var_14A0], r13
0x18000408d  mov     [rbp+13F0h+var_1448], r15
0x180004091  mov     [rbp+13F0h+var_1440], rdi
0x180004095  mov     [rsp+14F0h+var_1488], r13
0x18000409a  xorps   xmm0, xmm0
0x18000409d  xor     eax, eax
0x18000409f  movups  [rbp+13F0h+var_1468], xmm0
0x1800040a3  mov     [rbp+13F0h+var_1458], rax
0x1800040a7  xorps   xmm1, xmm1
0x1800040aa  movups  [rsp+14F0h+var_1480], xmm1
0x1800040af  mov     [rbp+13F0h+var_1470], rax
0x1800040b3  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800040ba  test    rax, rax
0x1800040bd  jz      short loc_1800040CA
0x1800040bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040c4  mov     [rbp+13F0h+var_1450], rax
0x1800040c8  jmp     short loc_1800040CE
0x1800040ca  mov     [rbp+13F0h+var_1450], r13
0x1800040ce  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800040d5  test    rax, rax
0x1800040d8  jz      short loc_1800040E4
0x1800040da  lea     rcx, [rsp+14F0h+var_14D0]
0x1800040df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040e4  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800040eb  test    rax, rax
0x1800040ee  jz      short loc_180004104
0x1800040f0  mov     r8d, 400h
0x1800040f6  lea     rdx, [rbp+13F0h+var_1430]
0x1800040fa  lea     rcx, [rsp+14F0h+var_14D0]
0x1800040ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004104  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000410b  test    rax, rax
0x18000410e  jz      short loc_18000411A
0x180004110  lea     rcx, [rsp+14F0h+var_14D0]
0x180004115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000411a  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004121  test    rax, rax
0x180004124  jz      short loc_180004137
0x180004126  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000412b  jnz     short loc_180004137
0x18000412d  lea     rcx, [rsp+14F0h+var_14D0]
0x180004132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004137  cmp     [rsp+14F0h+var_14C8], r13d
0x18000413c  jl      short loc_180004150
0x18000413e  mov     ecx, 8000FFFFh; this
0x180004143  mov     [rsp+14F0h+var_14C8], ecx
0x180004147  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000414c  mov     [rsp+14F0h+var_14C4], eax
0x180004150  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180004157  jnz     short loc_18000417E
0x180004159  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004160  test    rax, rax
0x180004163  jz      short loc_18000416E
0x180004165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000416a  test    al, al
0x18000416c  jmp     short loc_18000417C
0x18000416e  call    cs:__imp_IsDebuggerPresent
0x180004175  nop     dword ptr [rax+rax+00h]
0x18000417a  test    eax, eax
0x18000417c  jz      short loc_180004185
0x18000417e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004183  jz      short loc_1800041AB
0x180004185  mov     rax, cs:g_pfnResultLoggingCallback
0x18000418c  test    rax, rax
0x18000418f  jz      short loc_18000420A
0x180004191  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180004198  jnz     short loc_18000420A
0x18000419a  xor     r8d, r8d
0x18000419d  xor     edx, edx
0x18000419f  lea     rcx, [rsp+14F0h+var_14D0]
0x1800041a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041a9  jmp     short loc_18000420A
0x1800041ab  mov     ebx, 800h
0x1800041b0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800041b7  test    rax, rax
0x1800041ba  jz      short loc_1800041D9
0x1800041bc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800041c3  jnz     short loc_1800041D9
0x1800041c5  mov     r8d, ebx
0x1800041c8  lea     rdx, [rbp+13F0h+OutputString]
0x1800041cf  lea     rcx, [rsp+14F0h+var_14D0]
0x1800041d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041d9  cmp     [rbp+13F0h+OutputString], r13w
0x1800041e1  jnz     short loc_1800041F7
0x1800041e3  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800041e8  mov     rdx, rbx; unsigned __int16 *
0x1800041eb  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800041f2  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800041f7  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800041fe  call    cs:__imp_OutputDebugStringW
0x180004205  nop     dword ptr [rax+rax+00h]
0x18000420a  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000420f  jnz     short loc_18000421A
0x180004211  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180004218  jz      short loc_18000422C
0x18000421a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004221  test    rax, rax
0x180004224  jz      short loc_18000422C
0x180004226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000422b  nop
0x18000422c  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180004231  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
