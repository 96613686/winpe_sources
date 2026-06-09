# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000d400`
- end: `0x18000d700`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `768`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18000d068`

## callees

- `0x180002890`
- `0x180003474`
- `0x180005804`
- `0x180005bec`
- `0x180006f90`
- `0x18000d108`
- `0x18000d400`
- `0x18000e2d4`
- `0x18000e5f8`
- `0x180049280`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d521`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d521`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000d69d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000d69d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d614`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d614`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<2>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8,
        int a9,
        int a10)
{
  int v14; // edx
  int v15; // ebx
  int v16; // edx
  int v17; // ebx
  const struct wil::FailureInfo *v18; // rdx
  wil::details::in1diag3 *v19; // rcx
  const struct wil::FailureInfo *v20; // r9
  bool v21; // zf
  wil::details *v22; // [rsp+30h] [rbp-D0h]
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+54h] [rbp-ACh]
  int v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+5Ch] [rbp-A4h]
  signed __int32 v27; // [rsp+60h] [rbp-A0h]
  _WORD *v28; // [rsp+68h] [rbp-98h]
  DWORD CurrentThreadId; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+78h] [rbp-88h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int64 v32; // [rsp+88h] [rbp-78h]
  int v33; // [rsp+90h] [rbp-70h]
  int v34; // [rsp+94h] [rbp-6Ch]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int128 v36; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  __int128 v38; // [rsp+B8h] [rbp-48h]
  __int64 v39; // [rsp+C8h] [rbp-38h]
  __int64 ModuleName; // [rsp+D0h] [rbp-30h]
  __int64 v41; // [rsp+D8h] [rbp-28h]
  __int64 v42; // [rsp+E0h] [rbp-20h]
  char v43[1024]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR OutputString[2048]; // [rsp+4F0h] [rbp+3F0h] BYREF

  memset_0(&v23, 0, 0x98u);
  OutputString[0] = 0;
  v43[0] = 0;
  v15 = *a7;
  v25 = v15;
  v26 = a7[1];
  if ( v15 >= 0 )
  {
    v15 = -2147024228;
    LODWORD(v22) = -2147024228;
    wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v22);
    v25 = -2147024228;
    v26 = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v16);
  }
  v17 = wil::details::RecordLog((wil::details *)(unsigned int)v15, v14);
  v23 = 2;
  v24 = a10;
  if ( a7[2] == 1 )
    v24 = a10 | 8;
  v27 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v21 = *a8 == 0, v28 = a8, v21) )
    v28 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v32 = a3;
  v33 = a2;
  v34 = v17;
  v30 = a5;
  v31 = a4;
  v41 = a6;
  v42 = a1;
  v35 = 0;
  v38 = 0;
  v39 = 0;
  v36 = 0;
  v37 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v23);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v23, v43, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v23);
  if ( wil::details::g_pfnOriginateCallback && (v24 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v23);
  if ( v25 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v19);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v21 = !IsDebuggerPresent())
      : (v21 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v21)
    || (v24 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v23, v20);
    OutputDebugStringW(OutputString);
  }
  if ( ((v24 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak();
  if ( (v24 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v23, v18);
}

```

## disassembly

```asm
0x18000d400  push    rbp
0x18000d402  push    rbx
0x18000d403  push    rsi
0x18000d404  push    rdi
0x18000d405  push    r12
0x18000d407  push    r13
0x18000d409  push    r14
0x18000d40b  push    r15
0x18000d40d  lea     rbp, [rsp-1408h]
0x18000d415  mov     eax, 1508h
0x18000d41a  call    _alloca_probe
0x18000d41f  sub     rsp, rax
0x18000d422  mov     rax, cs:__security_cookie
0x18000d429  xor     rax, rsp
0x18000d42c  mov     [rbp+1440h+var_50], rax
0x18000d433  mov     r12, r9
0x18000d436  mov     r15, r8
0x18000d439  mov     r14d, edx
0x18000d43c  mov     rsi, rcx
0x18000d43f  mov     r13, [rbp+1440h+arg_20]
0x18000d446  mov     rax, [rbp+1440h+arg_28]
0x18000d44d  mov     [rsp+1540h+var_1500], rax
0x18000d452  xor     edx, edx; Val
0x18000d454  mov     r8d, 98h; Size
0x18000d45a  lea     rcx, [rsp+1540h+var_14F0]; void *
0x18000d45f  call    memset_0
0x18000d464  nop
0x18000d465  xor     eax, eax
0x18000d467  mov     [rbp+1440h+OutputString], ax
0x18000d46e  mov     [rbp+1440h+var_1450], al
0x18000d471  mov     rdi, [rbp+1440h+arg_30]
0x18000d478  mov     ebx, [rdi]
0x18000d47a  mov     [rsp+1540h+var_14E8], ebx
0x18000d47e  mov     eax, [rdi+4]
0x18000d481  mov     [rsp+1540h+var_14E4], eax
0x18000d485  test    ebx, ebx
0x18000d487  js      short loc_18000D4C9
0x18000d489  mov     [rsp+1540h+var_1508], 0
0x18000d491  mov     ebx, 8007029Ch
0x18000d496  mov     dword ptr [rsp+1540h+var_1510], ebx; wil::details *
0x18000d49a  mov     rax, [rsp+1540h+var_1500]
0x18000d49f  mov     [rsp+1540h+var_1518], rax; __int64
0x18000d4a4  mov     [rsp+1540h+var_1520], r13; __int64
0x18000d4a9  mov     r9, r12; int
0x18000d4ac  mov     r8, r15; int
0x18000d4af  mov     edx, r14d; int
0x18000d4b2  mov     rcx, rsi; int
0x18000d4b5  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000d4ba  mov     [rsp+1540h+var_14E8], ebx
0x18000d4be  mov     ecx, ebx; this
0x18000d4c0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000d4c5  mov     [rsp+1540h+var_14E4], eax
0x18000d4c9  mov     ecx, ebx; this
0x18000d4cb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000d4d0  mov     ebx, eax
0x18000d4d2  mov     dword ptr [rsp+1540h+var_14F0], 2
0x18000d4da  mov     ecx, [rbp+1440h+arg_48]
0x18000d4e0  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x18000d4e4  cmp     dword ptr [rdi+8], 1
0x18000d4e8  jnz     short loc_18000D4F1
0x18000d4ea  or      ecx, 8
0x18000d4ed  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x18000d4f1  mov     ecx, 1
0x18000d4f6  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000d4fe  inc     ecx
0x18000d500  mov     [rsp+1540h+var_14E0], ecx
0x18000d504  mov     rax, [rbp+1440h+arg_38]
0x18000d50b  xor     edi, edi
0x18000d50d  test    rax, rax
0x18000d510  jz      short loc_18000D51C
0x18000d512  cmp     [rax], di
0x18000d515  mov     [rsp+1540h+var_14D8], rax
0x18000d51a  jnz     short loc_18000D521
0x18000d51c  mov     [rsp+1540h+var_14D8], rdi
0x18000d521  call    cs:__imp_GetCurrentThreadId
0x18000d527  mov     [rsp+1540h+var_14D0], eax
0x18000d52b  mov     [rbp+1440h+var_14B8], r15
0x18000d52f  mov     [rbp+1440h+var_14B0], r14d
0x18000d533  mov     [rbp+1440h+var_14AC], ebx
0x18000d536  mov     [rsp+1540h+var_14C8], r13
0x18000d53b  mov     [rbp+1440h+var_14C0], r12
0x18000d53f  mov     rax, [rsp+1540h+var_1500]
0x18000d544  mov     [rbp+1440h+var_1468], rax
0x18000d548  mov     [rbp+1440h+var_1460], rsi
0x18000d54c  mov     [rbp+1440h+var_14A8], rdi
0x18000d550  xorps   xmm0, xmm0
0x18000d553  xor     eax, eax
0x18000d555  movups  [rbp+1440h+var_1488], xmm0
0x18000d559  mov     [rbp+1440h+var_1478], rax
0x18000d55d  xorps   xmm1, xmm1
0x18000d560  movups  [rbp+1440h+var_14A0], xmm1
0x18000d564  mov     [rbp+1440h+var_1490], rax
0x18000d568  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000d56f  test    rax, rax
0x18000d572  jz      short loc_18000D57F
0x18000d574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d579  mov     [rbp+1440h+var_1470], rax
0x18000d57d  jmp     short loc_18000D583
0x18000d57f  mov     [rbp+1440h+var_1470], rdi
0x18000d583  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000d58a  test    rax, rax
0x18000d58d  jz      short loc_18000D599
0x18000d58f  lea     rcx, [rsp+1540h+var_14F0]
0x18000d594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d599  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000d5a0  test    rax, rax
0x18000d5a3  jz      short loc_18000D5B9
0x18000d5a5  mov     r8d, 400h
0x18000d5ab  lea     rdx, [rbp+1440h+var_1450]
0x18000d5af  lea     rcx, [rsp+1540h+var_14F0]
0x18000d5b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5b9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000d5c0  test    rax, rax
0x18000d5c3  jz      short loc_18000D5CF
0x18000d5c5  lea     rcx, [rsp+1540h+var_14F0]
0x18000d5ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5cf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000d5d6  test    rax, rax
0x18000d5d9  jz      short loc_18000D5EC
0x18000d5db  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x18000d5e0  jnz     short loc_18000D5EC
0x18000d5e2  lea     rcx, [rsp+1540h+var_14F0]
0x18000d5e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5ec  cmp     [rsp+1540h+var_14E8], edi
0x18000d5f0  jge     loc_18000D6FA
0x18000d5f6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000d5fd  jnz     short loc_18000D61E
0x18000d5ff  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000d606  test    rax, rax
0x18000d609  jz      short loc_18000D614
0x18000d60b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d610  test    al, al
0x18000d612  jmp     short loc_18000D61C
0x18000d614  call    cs:__imp_IsDebuggerPresent
0x18000d61a  test    eax, eax
0x18000d61c  jz      short loc_18000D625
0x18000d61e  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x18000d623  jz      short loc_18000D64B
0x18000d625  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d62c  test    rax, rax
0x18000d62f  jz      short loc_18000D6A3
0x18000d631  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000d638  jnz     short loc_18000D6A3
0x18000d63a  xor     r8d, r8d
0x18000d63d  xor     edx, edx
0x18000d63f  lea     rcx, [rsp+1540h+var_14F0]
0x18000d644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d649  jmp     short loc_18000D6A3
0x18000d64b  mov     ebx, 800h
0x18000d650  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d657  test    rax, rax
0x18000d65a  jz      short loc_18000D679
0x18000d65c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000d663  jnz     short loc_18000D679
0x18000d665  mov     r8d, ebx
0x18000d668  lea     rdx, [rbp+1440h+OutputString]
0x18000d66f  lea     rcx, [rsp+1540h+var_14F0]
0x18000d674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d679  cmp     [rbp+1440h+OutputString], di
0x18000d680  jnz     short loc_18000D696
0x18000d682  lea     r8, [rsp+1540h+var_14F0]; unsigned __int64
0x18000d687  mov     rdx, rbx; wchar_t *
0x18000d68a  lea     rcx, [rbp+1440h+OutputString]; this
0x18000d691  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000d696  lea     rcx, [rbp+1440h+OutputString]; lpOutputString
0x18000d69d  call    cs:__imp_OutputDebugStringW
0x18000d6a3  test    byte ptr [rsp+1540h+var_14F0+4], 4
0x18000d6a8  jnz     short loc_18000D6B3
0x18000d6aa  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000d6b1  jz      short loc_18000D6C5
0x18000d6b3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000d6ba  test    rax, rax
0x18000d6bd  jz      short loc_18000D6C5
0x18000d6bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6c4  nop
0x18000d6c5  test    byte ptr [rsp+1540h+var_14F0+4], 1
0x18000d6ca  jnz     short loc_18000D6EF
0x18000d6cc  mov     rcx, [rbp+1440h+var_50]
0x18000d6d3  xor     rcx, rsp; StackCookie
0x18000d6d6  call    __security_check_cookie
0x18000d6db  add     rsp, 1508h
0x18000d6e2  pop     r15
0x18000d6e4  pop     r14
0x18000d6e6  pop     r13
0x18000d6e8  pop     r12
0x18000d6ea  pop     rdi
0x18000d6eb  pop     rsi
0x18000d6ec  pop     rbx
0x18000d6ed  pop     rbp
0x18000d6ee  retn
0x18000d6ef  lea     rcx, [rsp+1540h+var_14F0]; this
0x18000d6f4  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000d6fa  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
