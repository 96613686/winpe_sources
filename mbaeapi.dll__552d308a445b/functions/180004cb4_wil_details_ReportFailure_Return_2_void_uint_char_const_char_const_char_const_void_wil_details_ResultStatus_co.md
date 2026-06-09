# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004cb4`
- end: `0x180004fac`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int *, _WORD *, int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1800044a0`

## callees

- `0x1800024e0`
- `0x180002efc`
- `0x1800046bc`
- `0x180004cb4`
- `0x180006fe4`
- `0x18000778c`
- `0x18000853c`
- `0x18000ab80`
- `0x18000ad4c`
- `0x1800588d0`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004dcd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004dcd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004f49`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004f49`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004ec0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004ec0`

## pseudocode

```c
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
0x180004cb4  push    rbp
0x180004cb6  push    rbx
0x180004cb7  push    rsi
0x180004cb8  push    rdi
0x180004cb9  push    r12
0x180004cbb  push    r13
0x180004cbd  push    r14
0x180004cbf  push    r15
0x180004cc1  lea     rbp, [rsp-1408h]
0x180004cc9  mov     eax, 1508h
0x180004cce  call    _alloca_probe
0x180004cd3  sub     rsp, rax
0x180004cd6  mov     rax, cs:__security_cookie
0x180004cdd  xor     rax, rsp
0x180004ce0  mov     [rbp+1440h+var_50], rax
0x180004ce7  mov     r12, r9
0x180004cea  mov     r15, r8
0x180004ced  mov     r14d, edx
0x180004cf0  mov     rsi, rcx
0x180004cf3  mov     r13, [rbp+1440h+arg_20]
0x180004cfa  mov     rax, [rbp+1440h+arg_28]
0x180004d01  mov     [rsp+1540h+var_1500], rax
0x180004d06  xor     edx, edx; Val
0x180004d08  mov     r8d, 98h; Size
0x180004d0e  lea     rcx, [rsp+1540h+var_14F0]; void *
0x180004d13  call    memset_0
0x180004d18  nop
0x180004d19  xor     eax, eax
0x180004d1b  mov     [rbp+1440h+OutputString], ax
0x180004d22  mov     [rbp+1440h+var_1450], al
0x180004d25  mov     rdi, [rbp+1440h+arg_30]
0x180004d2c  mov     ebx, [rdi]
0x180004d2e  mov     [rsp+1540h+var_14E8], ebx
0x180004d32  mov     eax, [rdi+4]
0x180004d35  mov     [rsp+1540h+var_14E4], eax
0x180004d39  test    ebx, ebx
0x180004d3b  js      short loc_180004D75
0x180004d3d  mov     ebx, 8007029Ch
0x180004d42  mov     dword ptr [rsp+1540h+var_1510], ebx; wil::details *
0x180004d46  mov     rax, [rsp+1540h+var_1500]
0x180004d4b  mov     [rsp+1540h+var_1518], rax; __int64
0x180004d50  mov     [rsp+1540h+var_1520], r13; __int64
0x180004d55  mov     r9, r12; int
0x180004d58  mov     r8, r15; int
0x180004d5b  mov     edx, r14d; int
0x180004d5e  mov     rcx, rsi; int
0x180004d61  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004d66  mov     [rsp+1540h+var_14E8], ebx
0x180004d6a  mov     ecx, ebx; this
0x180004d6c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004d71  mov     [rsp+1540h+var_14E4], eax
0x180004d75  mov     ecx, ebx; this
0x180004d77  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004d7c  mov     ebx, eax
0x180004d7e  mov     dword ptr [rsp+1540h+var_14F0], 2
0x180004d86  mov     ecx, [rbp+1440h+arg_48]
0x180004d8c  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x180004d90  cmp     dword ptr [rdi+8], 1
0x180004d94  jnz     short loc_180004D9D
0x180004d96  or      ecx, 8
0x180004d99  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x180004d9d  mov     ecx, 1
0x180004da2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004daa  inc     ecx
0x180004dac  mov     [rsp+1540h+var_14E0], ecx
0x180004db0  mov     rax, [rbp+1440h+arg_38]
0x180004db7  xor     edi, edi
0x180004db9  test    rax, rax
0x180004dbc  jz      short loc_180004DC8
0x180004dbe  cmp     [rax], di
0x180004dc1  mov     [rsp+1540h+var_14D8], rax
0x180004dc6  jnz     short loc_180004DCD
0x180004dc8  mov     [rsp+1540h+var_14D8], rdi
0x180004dcd  call    cs:__imp_GetCurrentThreadId
0x180004dd3  mov     [rsp+1540h+var_14D0], eax
0x180004dd7  mov     [rbp+1440h+var_14B8], r15
0x180004ddb  mov     [rbp+1440h+var_14B0], r14d
0x180004ddf  mov     [rbp+1440h+var_14AC], ebx
0x180004de2  mov     [rsp+1540h+var_14C8], r13
0x180004de7  mov     [rbp+1440h+var_14C0], r12
0x180004deb  mov     rax, [rsp+1540h+var_1500]
0x180004df0  mov     [rbp+1440h+var_1468], rax
0x180004df4  mov     [rbp+1440h+var_1460], rsi
0x180004df8  mov     [rbp+1440h+var_14A8], rdi
0x180004dfc  xorps   xmm0, xmm0
0x180004dff  xor     eax, eax
0x180004e01  movups  [rbp+1440h+var_1488], xmm0
0x180004e05  mov     [rbp+1440h+var_1478], rax
0x180004e09  xorps   xmm1, xmm1
0x180004e0c  movups  [rbp+1440h+var_14A0], xmm1
0x180004e10  mov     [rbp+1440h+var_1490], rax
0x180004e14  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004e1b  test    rax, rax
0x180004e1e  jz      short loc_180004E2B
0x180004e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e25  mov     [rbp+1440h+var_1470], rax
0x180004e29  jmp     short loc_180004E2F
0x180004e2b  mov     [rbp+1440h+var_1470], rdi
0x180004e2f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004e36  test    rax, rax
0x180004e39  jz      short loc_180004E45
0x180004e3b  lea     rcx, [rsp+1540h+var_14F0]
0x180004e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e45  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004e4c  test    rax, rax
0x180004e4f  jz      short loc_180004E65
0x180004e51  mov     r8d, 400h
0x180004e57  lea     rdx, [rbp+1440h+var_1450]
0x180004e5b  lea     rcx, [rsp+1540h+var_14F0]
0x180004e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e65  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004e6c  test    rax, rax
0x180004e6f  jz      short loc_180004E7B
0x180004e71  lea     rcx, [rsp+1540h+var_14F0]
0x180004e76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e7b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004e82  test    rax, rax
0x180004e85  jz      short loc_180004E98
0x180004e87  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x180004e8c  jnz     short loc_180004E98
0x180004e8e  lea     rcx, [rsp+1540h+var_14F0]
0x180004e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e98  cmp     [rsp+1540h+var_14E8], edi
0x180004e9c  jge     loc_180004FA6
0x180004ea2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180004ea9  jnz     short loc_180004ECA
0x180004eab  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004eb2  test    rax, rax
0x180004eb5  jz      short loc_180004EC0
0x180004eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ebc  test    al, al
0x180004ebe  jmp     short loc_180004EC8
0x180004ec0  call    cs:__imp_IsDebuggerPresent
0x180004ec6  test    eax, eax
0x180004ec8  jz      short loc_180004ED1
0x180004eca  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x180004ecf  jz      short loc_180004EF7
0x180004ed1  mov     rax, cs:g_pfnResultLoggingCallback
0x180004ed8  test    rax, rax
0x180004edb  jz      short loc_180004F4F
0x180004edd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004ee4  jnz     short loc_180004F4F
0x180004ee6  xor     r8d, r8d
0x180004ee9  xor     edx, edx
0x180004eeb  lea     rcx, [rsp+1540h+var_14F0]
0x180004ef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ef5  jmp     short loc_180004F4F
0x180004ef7  mov     ebx, 800h
0x180004efc  mov     rax, cs:g_pfnResultLoggingCallback
0x180004f03  test    rax, rax
0x180004f06  jz      short loc_180004F25
0x180004f08  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004f0f  jnz     short loc_180004F25
0x180004f11  mov     r8d, ebx
0x180004f14  lea     rdx, [rbp+1440h+OutputString]
0x180004f1b  lea     rcx, [rsp+1540h+var_14F0]
0x180004f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f25  cmp     [rbp+1440h+OutputString], di
0x180004f2c  jnz     short loc_180004F42
0x180004f2e  lea     r8, [rsp+1540h+var_14F0]; unsigned __int64
0x180004f33  mov     rdx, rbx; unsigned __int16 *
0x180004f36  lea     rcx, [rbp+1440h+OutputString]; this
0x180004f3d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004f42  lea     rcx, [rbp+1440h+OutputString]; lpOutputString
0x180004f49  call    cs:__imp_OutputDebugStringW
0x180004f4f  test    byte ptr [rsp+1540h+var_14F0+4], 4
0x180004f54  jnz     short loc_180004F5F
0x180004f56  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180004f5d  jz      short loc_180004F71
0x180004f5f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004f66  test    rax, rax
0x180004f69  jz      short loc_180004F71
0x180004f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f70  nop
0x180004f71  test    byte ptr [rsp+1540h+var_14F0+4], 1
0x180004f76  jnz     short loc_180004F9B
0x180004f78  mov     rcx, [rbp+1440h+var_50]
0x180004f7f  xor     rcx, rsp; StackCookie
0x180004f82  call    __security_check_cookie
0x180004f87  add     rsp, 1508h
0x180004f8e  pop     r15
0x180004f90  pop     r14
0x180004f92  pop     r13
0x180004f94  pop     r12
0x180004f96  pop     rdi
0x180004f97  pop     rsi
0x180004f98  pop     rbx
0x180004f99  pop     rbp
0x180004f9a  retn
0x180004f9b  lea     rcx, [rsp+1540h+var_14F0]; this
0x180004fa0  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004fa6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
