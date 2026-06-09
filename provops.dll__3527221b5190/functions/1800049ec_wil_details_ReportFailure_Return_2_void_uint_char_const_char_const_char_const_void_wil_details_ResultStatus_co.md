# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800049ec`
- end: `0x180004ce4`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int *, _WORD *, int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1800041e8`

## callees

- `0x1800043f4`
- `0x1800049ec`
- `0x180005fa4`
- `0x180006850`
- `0x180007084`
- `0x1800083c0`
- `0x18000863c`
- `0x180033e9a`
- `0x180033ed0`
- `0x180033f90`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b05`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004c81`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004c81`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004bf8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004bf8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
    ModuleName = wil::details::g_pfnGetModuleName(v19);
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
      : (v21 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v19) == 0),
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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v23, v20);
    OutputDebugStringW(OutputString);
  }
  if ( ((v24 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v19);
  if ( (v24 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v23, v18);
}

```

## disassembly

```asm
0x1800049ec  push    rbp
0x1800049ee  push    rbx
0x1800049ef  push    rsi
0x1800049f0  push    rdi
0x1800049f1  push    r12
0x1800049f3  push    r13
0x1800049f5  push    r14
0x1800049f7  push    r15
0x1800049f9  lea     rbp, [rsp-1408h]
0x180004a01  mov     eax, 1508h
0x180004a06  call    _alloca_probe
0x180004a0b  sub     rsp, rax
0x180004a0e  mov     rax, cs:__security_cookie
0x180004a15  xor     rax, rsp
0x180004a18  mov     [rbp+1440h+var_50], rax
0x180004a1f  mov     r12, r9
0x180004a22  mov     r15, r8
0x180004a25  mov     r14d, edx
0x180004a28  mov     rsi, rcx
0x180004a2b  mov     r13, [rbp+1440h+arg_20]
0x180004a32  mov     rax, [rbp+1440h+arg_28]
0x180004a39  mov     [rsp+1540h+var_1500], rax
0x180004a3e  xor     edx, edx; Val
0x180004a40  mov     r8d, 98h; Size
0x180004a46  lea     rcx, [rsp+1540h+var_14F0]; void *
0x180004a4b  call    memset_0
0x180004a50  nop
0x180004a51  xor     eax, eax
0x180004a53  mov     [rbp+1440h+OutputString], ax
0x180004a5a  mov     [rbp+1440h+var_1450], al
0x180004a5d  mov     rdi, [rbp+1440h+arg_30]
0x180004a64  mov     ebx, [rdi]
0x180004a66  mov     [rsp+1540h+var_14E8], ebx
0x180004a6a  mov     eax, [rdi+4]
0x180004a6d  mov     [rsp+1540h+var_14E4], eax
0x180004a71  test    ebx, ebx
0x180004a73  js      short loc_180004AAD
0x180004a75  mov     ebx, 8007029Ch
0x180004a7a  mov     dword ptr [rsp+1540h+var_1510], ebx; wil::details *
0x180004a7e  mov     rax, [rsp+1540h+var_1500]
0x180004a83  mov     [rsp+1540h+var_1518], rax; __int64
0x180004a88  mov     [rsp+1540h+var_1520], r13; __int64
0x180004a8d  mov     r9, r12; int
0x180004a90  mov     r8, r15; int
0x180004a93  mov     edx, r14d; int
0x180004a96  mov     rcx, rsi; int
0x180004a99  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004a9e  mov     [rsp+1540h+var_14E8], ebx
0x180004aa2  mov     ecx, ebx; this
0x180004aa4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004aa9  mov     [rsp+1540h+var_14E4], eax
0x180004aad  mov     ecx, ebx; this
0x180004aaf  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004ab4  mov     ebx, eax
0x180004ab6  mov     dword ptr [rsp+1540h+var_14F0], 2
0x180004abe  mov     ecx, [rbp+1440h+arg_48]
0x180004ac4  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x180004ac8  cmp     dword ptr [rdi+8], 1
0x180004acc  jnz     short loc_180004AD5
0x180004ace  or      ecx, 8
0x180004ad1  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x180004ad5  mov     ecx, 1
0x180004ada  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004ae2  inc     ecx
0x180004ae4  mov     [rsp+1540h+var_14E0], ecx
0x180004ae8  mov     rax, [rbp+1440h+arg_38]
0x180004aef  xor     edi, edi
0x180004af1  test    rax, rax
0x180004af4  jz      short loc_180004B00
0x180004af6  cmp     [rax], di
0x180004af9  mov     [rsp+1540h+var_14D8], rax
0x180004afe  jnz     short loc_180004B05
0x180004b00  mov     [rsp+1540h+var_14D8], rdi
0x180004b05  call    cs:__imp_GetCurrentThreadId
0x180004b0b  mov     [rsp+1540h+var_14D0], eax
0x180004b0f  mov     [rbp+1440h+var_14B8], r15
0x180004b13  mov     [rbp+1440h+var_14B0], r14d
0x180004b17  mov     [rbp+1440h+var_14AC], ebx
0x180004b1a  mov     [rsp+1540h+var_14C8], r13
0x180004b1f  mov     [rbp+1440h+var_14C0], r12
0x180004b23  mov     rax, [rsp+1540h+var_1500]
0x180004b28  mov     [rbp+1440h+var_1468], rax
0x180004b2c  mov     [rbp+1440h+var_1460], rsi
0x180004b30  mov     [rbp+1440h+var_14A8], rdi
0x180004b34  xorps   xmm0, xmm0
0x180004b37  xor     eax, eax
0x180004b39  movups  [rbp+1440h+var_1488], xmm0
0x180004b3d  mov     [rbp+1440h+var_1478], rax
0x180004b41  xorps   xmm1, xmm1
0x180004b44  movups  [rbp+1440h+var_14A0], xmm1
0x180004b48  mov     [rbp+1440h+var_1490], rax
0x180004b4c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004b53  test    rax, rax
0x180004b56  jz      short loc_180004B63
0x180004b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b5d  mov     [rbp+1440h+var_1470], rax
0x180004b61  jmp     short loc_180004B67
0x180004b63  mov     [rbp+1440h+var_1470], rdi
0x180004b67  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004b6e  test    rax, rax
0x180004b71  jz      short loc_180004B7D
0x180004b73  lea     rcx, [rsp+1540h+var_14F0]
0x180004b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b7d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004b84  test    rax, rax
0x180004b87  jz      short loc_180004B9D
0x180004b89  mov     r8d, 400h
0x180004b8f  lea     rdx, [rbp+1440h+var_1450]
0x180004b93  lea     rcx, [rsp+1540h+var_14F0]
0x180004b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b9d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004ba4  test    rax, rax
0x180004ba7  jz      short loc_180004BB3
0x180004ba9  lea     rcx, [rsp+1540h+var_14F0]
0x180004bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bb3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004bba  test    rax, rax
0x180004bbd  jz      short loc_180004BD0
0x180004bbf  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x180004bc4  jnz     short loc_180004BD0
0x180004bc6  lea     rcx, [rsp+1540h+var_14F0]
0x180004bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bd0  cmp     [rsp+1540h+var_14E8], edi
0x180004bd4  jge     loc_180004CDE
0x180004bda  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180004be1  jnz     short loc_180004C02
0x180004be3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004bea  test    rax, rax
0x180004bed  jz      short loc_180004BF8
0x180004bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bf4  test    al, al
0x180004bf6  jmp     short loc_180004C00
0x180004bf8  call    cs:__imp_IsDebuggerPresent
0x180004bfe  test    eax, eax
0x180004c00  jz      short loc_180004C09
0x180004c02  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x180004c07  jz      short loc_180004C2F
0x180004c09  mov     rax, cs:g_pfnResultLoggingCallback
0x180004c10  test    rax, rax
0x180004c13  jz      short loc_180004C87
0x180004c15  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004c1c  jnz     short loc_180004C87
0x180004c1e  xor     r8d, r8d
0x180004c21  xor     edx, edx
0x180004c23  lea     rcx, [rsp+1540h+var_14F0]
0x180004c28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c2d  jmp     short loc_180004C87
0x180004c2f  mov     ebx, 800h
0x180004c34  mov     rax, cs:g_pfnResultLoggingCallback
0x180004c3b  test    rax, rax
0x180004c3e  jz      short loc_180004C5D
0x180004c40  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004c47  jnz     short loc_180004C5D
0x180004c49  mov     r8d, ebx
0x180004c4c  lea     rdx, [rbp+1440h+OutputString]
0x180004c53  lea     rcx, [rsp+1540h+var_14F0]
0x180004c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c5d  cmp     [rbp+1440h+OutputString], di
0x180004c64  jnz     short loc_180004C7A
0x180004c66  lea     r8, [rsp+1540h+var_14F0]; unsigned __int64
0x180004c6b  mov     rdx, rbx; unsigned __int16 *
0x180004c6e  lea     rcx, [rbp+1440h+OutputString]; this
0x180004c75  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004c7a  lea     rcx, [rbp+1440h+OutputString]; lpOutputString
0x180004c81  call    cs:__imp_OutputDebugStringW
0x180004c87  test    byte ptr [rsp+1540h+var_14F0+4], 4
0x180004c8c  jnz     short loc_180004C97
0x180004c8e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180004c95  jz      short loc_180004CA9
0x180004c97  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004c9e  test    rax, rax
0x180004ca1  jz      short loc_180004CA9
0x180004ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ca8  nop
0x180004ca9  test    byte ptr [rsp+1540h+var_14F0+4], 1
0x180004cae  jnz     short loc_180004CD3
0x180004cb0  mov     rcx, [rbp+1440h+var_50]
0x180004cb7  xor     rcx, rsp; StackCookie
0x180004cba  call    __security_check_cookie
0x180004cbf  add     rsp, 1508h
0x180004cc6  pop     r15
0x180004cc8  pop     r14
0x180004cca  pop     r13
0x180004ccc  pop     r12
0x180004cce  pop     rdi
0x180004ccf  pop     rsi
0x180004cd0  pop     rbx
0x180004cd1  pop     rbp
0x180004cd2  retn
0x180004cd3  lea     rcx, [rsp+1540h+var_14F0]; this
0x180004cd8  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004cde  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
