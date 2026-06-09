# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180005144`
- end: `0x1800053da`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004c4c`

## callees

- `0x180005144`
- `0x180006b34`
- `0x1800090a4`
- `0x18000aa30`
- `0x18000abec`
- `0x18002f0ba`
- `0x18002f0e0`
- `0x18002f1a0`
- `0x180031010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1800052ea`
- `KERNEL32!IsDebuggerPresent` at `0x1800052ea`
- `KERNEL32!OutputDebugStringW` at `0x180005374`
- `KERNEL32!OutputDebugStringW` at `0x180005374`
- `KERNEL32!GetCurrentThreadId` at `0x1800051ef`
- `KERNEL32!GetCurrentThreadId` at `0x1800051ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
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
      wil::GetFailureLogString(OutputString, (wchar_t *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x180005144  mov     [rsp-8+arg_10], rbx
0x180005149  push    rbp
0x18000514a  push    rsi
0x18000514b  push    rdi
0x18000514c  push    r14
0x18000514e  push    r15
0x180005150  lea     rbp, [rsp-13D0h]
0x180005158  mov     eax, 14D0h
0x18000515d  call    _alloca_probe
0x180005162  sub     rsp, rax
0x180005165  mov     rax, cs:__security_cookie
0x18000516c  xor     rax, rsp
0x18000516f  mov     [rbp+13F0h+var_30], rax
0x180005176  mov     esi, edx
0x180005178  mov     r14, rcx
0x18000517b  mov     rdi, [rbp+13F0h+arg_28]
0x180005182  xor     edx, edx; Val
0x180005184  mov     r8d, 98h; Size
0x18000518a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000518f  call    memset_0
0x180005194  nop
0x180005195  xor     r15d, r15d
0x180005198  mov     [rbp+13F0h+OutputString], r15w
0x1800051a0  mov     [rbp+13F0h+var_1430], r15b
0x1800051a4  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800051ab  mov     ecx, [rdx]; this
0x1800051ad  mov     [rsp+14F0h+var_14C8], ecx
0x1800051b1  mov     eax, [rdx+4]
0x1800051b4  mov     [rsp+14F0h+var_14C4], eax
0x1800051b8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800051bd  mov     ebx, eax
0x1800051bf  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800051c7  mov     ecx, r15d
0x1800051ca  lea     eax, [r15+8]
0x1800051ce  cmp     dword ptr [rdx+8], 1
0x1800051d2  cmovz   ecx, eax
0x1800051d5  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800051d9  lea     ecx, [rax-7]
0x1800051dc  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800051e4  inc     ecx
0x1800051e6  mov     [rsp+14F0h+var_14C0], ecx
0x1800051ea  mov     [rsp+14F0h+var_14B8], r15
0x1800051ef  call    cs:__imp_GetCurrentThreadId
0x1800051f5  mov     [rsp+14F0h+var_14B0], eax
0x1800051f9  lea     rax, aWil; "wil"
0x180005200  mov     [rsp+14F0h+var_1498], rax
0x180005205  mov     [rsp+14F0h+var_1490], esi
0x180005209  mov     [rsp+14F0h+var_148C], ebx
0x18000520d  mov     [rsp+14F0h+var_14A8], r15
0x180005212  mov     [rsp+14F0h+var_14A0], r15
0x180005217  mov     [rbp+13F0h+var_1448], rdi
0x18000521b  mov     [rbp+13F0h+var_1440], r14
0x18000521f  mov     [rsp+14F0h+var_1488], r15
0x180005224  xorps   xmm0, xmm0
0x180005227  xor     eax, eax
0x180005229  movups  [rbp+13F0h+var_1468], xmm0
0x18000522d  mov     [rbp+13F0h+var_1458], rax
0x180005231  xorps   xmm1, xmm1
0x180005234  movups  [rsp+14F0h+var_1480], xmm1
0x180005239  mov     [rbp+13F0h+var_1470], rax
0x18000523d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005244  test    rax, rax
0x180005247  jz      short loc_180005254
0x180005249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000524e  mov     [rbp+13F0h+var_1450], rax
0x180005252  jmp     short loc_180005258
0x180005254  mov     [rbp+13F0h+var_1450], r15
0x180005258  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000525f  test    rax, rax
0x180005262  jz      short loc_18000526E
0x180005264  lea     rcx, [rsp+14F0h+var_14D0]
0x180005269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000526e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005275  test    rax, rax
0x180005278  jz      short loc_18000528E
0x18000527a  mov     r8d, 400h
0x180005280  lea     rdx, [rbp+13F0h+var_1430]
0x180005284  lea     rcx, [rsp+14F0h+var_14D0]
0x180005289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000528e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005295  test    rax, rax
0x180005298  jz      short loc_1800052A4
0x18000529a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000529f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052a4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800052ab  test    rax, rax
0x1800052ae  jz      short loc_1800052C1
0x1800052b0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800052b5  jnz     short loc_1800052C1
0x1800052b7  lea     rcx, [rsp+14F0h+var_14D0]
0x1800052bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052c1  cmp     [rsp+14F0h+var_14C8], r15d
0x1800052c6  jge     loc_1800053D4
0x1800052cc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800052d3  jnz     short loc_1800052F4
0x1800052d5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800052dc  test    rax, rax
0x1800052df  jz      short loc_1800052EA
0x1800052e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052e6  test    al, al
0x1800052e8  jmp     short loc_1800052F2
0x1800052ea  call    cs:__imp_IsDebuggerPresent
0x1800052f0  test    eax, eax
0x1800052f2  jz      short loc_1800052FB
0x1800052f4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800052f9  jz      short loc_180005321
0x1800052fb  mov     rax, cs:g_pfnResultLoggingCallback
0x180005302  test    rax, rax
0x180005305  jz      short loc_18000537A
0x180005307  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000530e  jnz     short loc_18000537A
0x180005310  xor     r8d, r8d
0x180005313  xor     edx, edx
0x180005315  lea     rcx, [rsp+14F0h+var_14D0]
0x18000531a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000531f  jmp     short loc_18000537A
0x180005321  mov     ebx, 800h
0x180005326  mov     rax, cs:g_pfnResultLoggingCallback
0x18000532d  test    rax, rax
0x180005330  jz      short loc_18000534F
0x180005332  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005339  jnz     short loc_18000534F
0x18000533b  mov     r8d, ebx
0x18000533e  lea     rdx, [rbp+13F0h+OutputString]
0x180005345  lea     rcx, [rsp+14F0h+var_14D0]
0x18000534a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000534f  cmp     [rbp+13F0h+OutputString], r15w
0x180005357  jnz     short loc_18000536D
0x180005359  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000535e  mov     rdx, rbx; wchar_t *
0x180005361  lea     rcx, [rbp+13F0h+OutputString]; this
0x180005368  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000536d  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180005374  call    cs:__imp_OutputDebugStringW
0x18000537a  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000537f  jnz     short loc_18000538A
0x180005381  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180005388  jz      short loc_18000539C
0x18000538a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005391  test    rax, rax
0x180005394  jz      short loc_18000539C
0x180005396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000539b  nop
0x18000539c  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800053a1  jnz     short loc_1800053C9
0x1800053a3  mov     rcx, [rbp+13F0h+var_30]
0x1800053aa  xor     rcx, rsp; StackCookie
0x1800053ad  call    __security_check_cookie
0x1800053b2  mov     rbx, [rsp+14F0h+arg_10]
0x1800053ba  add     rsp, 14D0h
0x1800053c1  pop     r15
0x1800053c3  pop     r14
0x1800053c5  pop     rdi
0x1800053c6  pop     rsi
0x1800053c7  pop     rbp
0x1800053c8  retn
0x1800053c9  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800053ce  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800053d4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
