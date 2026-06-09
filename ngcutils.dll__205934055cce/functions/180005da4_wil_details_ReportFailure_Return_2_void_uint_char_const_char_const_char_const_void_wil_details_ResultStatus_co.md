# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180005da4`
- end: `0x18000609c`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180005590`

## callees

- `0x180003080`
- `0x180003bc8`
- `0x1800057ac`
- `0x180005da4`
- `0x180008064`
- `0x18000880c`
- `0x18000964c`
- `0x18000bc50`
- `0x18000be1c`
- `0x180057f50`
- `0x180061010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005ebd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005ebd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005fb0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005fb0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006039`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006039`

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
      g_pfnResultLoggingCallback(&v23, 0, 0, v20);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, OutputString, 2048, v20);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v23, v20);
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
0x180005da4  push    rbp
0x180005da6  push    rbx
0x180005da7  push    rsi
0x180005da8  push    rdi
0x180005da9  push    r12
0x180005dab  push    r13
0x180005dad  push    r14
0x180005daf  push    r15
0x180005db1  lea     rbp, [rsp-1408h]
0x180005db9  mov     eax, 1508h
0x180005dbe  call    _alloca_probe
0x180005dc3  sub     rsp, rax
0x180005dc6  mov     rax, cs:__security_cookie
0x180005dcd  xor     rax, rsp
0x180005dd0  mov     [rbp+1440h+var_50], rax
0x180005dd7  mov     r12, r9
0x180005dda  mov     r15, r8
0x180005ddd  mov     r14d, edx
0x180005de0  mov     rsi, rcx
0x180005de3  mov     r13, [rbp+1440h+arg_20]
0x180005dea  mov     rax, [rbp+1440h+arg_28]
0x180005df1  mov     [rsp+1540h+var_1500], rax
0x180005df6  xor     edx, edx; Val
0x180005df8  mov     r8d, 98h; Size
0x180005dfe  lea     rcx, [rsp+1540h+var_14F0]; void *
0x180005e03  call    memset_0
0x180005e08  nop
0x180005e09  xor     eax, eax
0x180005e0b  mov     [rbp+1440h+OutputString], ax
0x180005e12  mov     [rbp+1440h+var_1450], al
0x180005e15  mov     rdi, [rbp+1440h+arg_30]
0x180005e1c  mov     ebx, [rdi]
0x180005e1e  mov     [rsp+1540h+var_14E8], ebx
0x180005e22  mov     eax, [rdi+4]
0x180005e25  mov     [rsp+1540h+var_14E4], eax
0x180005e29  test    ebx, ebx
0x180005e2b  js      short loc_180005E65
0x180005e2d  mov     ebx, 8007029Ch
0x180005e32  mov     dword ptr [rsp+1540h+var_1510], ebx; wil::details *
0x180005e36  mov     rax, [rsp+1540h+var_1500]
0x180005e3b  mov     [rsp+1540h+var_1518], rax; __int64
0x180005e40  mov     [rsp+1540h+var_1520], r13; __int64
0x180005e45  mov     r9, r12; int
0x180005e48  mov     r8, r15; int
0x180005e4b  mov     edx, r14d; int
0x180005e4e  mov     rcx, rsi; int
0x180005e51  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005e56  mov     [rsp+1540h+var_14E8], ebx
0x180005e5a  mov     ecx, ebx; this
0x180005e5c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005e61  mov     [rsp+1540h+var_14E4], eax
0x180005e65  mov     ecx, ebx; this
0x180005e67  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005e6c  mov     ebx, eax
0x180005e6e  mov     dword ptr [rsp+1540h+var_14F0], 2
0x180005e76  mov     ecx, [rbp+1440h+arg_48]
0x180005e7c  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x180005e80  cmp     dword ptr [rdi+8], 1
0x180005e84  jnz     short loc_180005E8D
0x180005e86  or      ecx, 8
0x180005e89  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x180005e8d  mov     ecx, 1
0x180005e92  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005e9a  inc     ecx
0x180005e9c  mov     [rsp+1540h+var_14E0], ecx
0x180005ea0  mov     rax, [rbp+1440h+arg_38]
0x180005ea7  xor     edi, edi
0x180005ea9  test    rax, rax
0x180005eac  jz      short loc_180005EB8
0x180005eae  cmp     [rax], di
0x180005eb1  mov     [rsp+1540h+var_14D8], rax
0x180005eb6  jnz     short loc_180005EBD
0x180005eb8  mov     [rsp+1540h+var_14D8], rdi
0x180005ebd  call    cs:__imp_GetCurrentThreadId
0x180005ec3  mov     [rsp+1540h+var_14D0], eax
0x180005ec7  mov     [rbp+1440h+var_14B8], r15
0x180005ecb  mov     [rbp+1440h+var_14B0], r14d
0x180005ecf  mov     [rbp+1440h+var_14AC], ebx
0x180005ed2  mov     [rsp+1540h+var_14C8], r13
0x180005ed7  mov     [rbp+1440h+var_14C0], r12
0x180005edb  mov     rax, [rsp+1540h+var_1500]
0x180005ee0  mov     [rbp+1440h+var_1468], rax
0x180005ee4  mov     [rbp+1440h+var_1460], rsi
0x180005ee8  mov     [rbp+1440h+var_14A8], rdi
0x180005eec  xorps   xmm0, xmm0
0x180005eef  xor     eax, eax
0x180005ef1  movups  [rbp+1440h+var_1488], xmm0
0x180005ef5  mov     [rbp+1440h+var_1478], rax
0x180005ef9  xorps   xmm1, xmm1
0x180005efc  movups  [rbp+1440h+var_14A0], xmm1
0x180005f00  mov     [rbp+1440h+var_1490], rax
0x180005f04  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005f0b  test    rax, rax
0x180005f0e  jz      short loc_180005F1B
0x180005f10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f15  mov     [rbp+1440h+var_1470], rax
0x180005f19  jmp     short loc_180005F1F
0x180005f1b  mov     [rbp+1440h+var_1470], rdi
0x180005f1f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005f26  test    rax, rax
0x180005f29  jz      short loc_180005F35
0x180005f2b  lea     rcx, [rsp+1540h+var_14F0]
0x180005f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f35  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005f3c  test    rax, rax
0x180005f3f  jz      short loc_180005F55
0x180005f41  mov     r8d, 400h
0x180005f47  lea     rdx, [rbp+1440h+var_1450]
0x180005f4b  lea     rcx, [rsp+1540h+var_14F0]
0x180005f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f55  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005f5c  test    rax, rax
0x180005f5f  jz      short loc_180005F6B
0x180005f61  lea     rcx, [rsp+1540h+var_14F0]
0x180005f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f6b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005f72  test    rax, rax
0x180005f75  jz      short loc_180005F88
0x180005f77  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x180005f7c  jnz     short loc_180005F88
0x180005f7e  lea     rcx, [rsp+1540h+var_14F0]
0x180005f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f88  cmp     [rsp+1540h+var_14E8], edi
0x180005f8c  jge     loc_180006096
0x180005f92  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005f99  jnz     short loc_180005FBA
0x180005f9b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005fa2  test    rax, rax
0x180005fa5  jz      short loc_180005FB0
0x180005fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fac  test    al, al
0x180005fae  jmp     short loc_180005FB8
0x180005fb0  call    cs:__imp_IsDebuggerPresent
0x180005fb6  test    eax, eax
0x180005fb8  jz      short loc_180005FC1
0x180005fba  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x180005fbf  jz      short loc_180005FE7
0x180005fc1  mov     rax, cs:g_pfnResultLoggingCallback
0x180005fc8  test    rax, rax
0x180005fcb  jz      short loc_18000603F
0x180005fcd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005fd4  jnz     short loc_18000603F
0x180005fd6  xor     r8d, r8d
0x180005fd9  xor     edx, edx
0x180005fdb  lea     rcx, [rsp+1540h+var_14F0]
0x180005fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fe5  jmp     short loc_18000603F
0x180005fe7  mov     ebx, 800h
0x180005fec  mov     rax, cs:g_pfnResultLoggingCallback
0x180005ff3  test    rax, rax
0x180005ff6  jz      short loc_180006015
0x180005ff8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005fff  jnz     short loc_180006015
0x180006001  mov     r8d, ebx
0x180006004  lea     rdx, [rbp+1440h+OutputString]
0x18000600b  lea     rcx, [rsp+1540h+var_14F0]
0x180006010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006015  cmp     [rbp+1440h+OutputString], di
0x18000601c  jnz     short loc_180006032
0x18000601e  lea     r8, [rsp+1540h+var_14F0]; unsigned __int64
0x180006023  mov     rdx, rbx; unsigned __int16 *
0x180006026  lea     rcx, [rbp+1440h+OutputString]; this
0x18000602d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006032  lea     rcx, [rbp+1440h+OutputString]; lpOutputString
0x180006039  call    cs:__imp_OutputDebugStringW
0x18000603f  test    byte ptr [rsp+1540h+var_14F0+4], 4
0x180006044  jnz     short loc_18000604F
0x180006046  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000604d  jz      short loc_180006061
0x18000604f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006056  test    rax, rax
0x180006059  jz      short loc_180006061
0x18000605b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006060  nop
0x180006061  test    byte ptr [rsp+1540h+var_14F0+4], 1
0x180006066  jnz     short loc_18000608B
0x180006068  mov     rcx, [rbp+1440h+var_50]
0x18000606f  xor     rcx, rsp; StackCookie
0x180006072  call    __security_check_cookie
0x180006077  add     rsp, 1508h
0x18000607e  pop     r15
0x180006080  pop     r14
0x180006082  pop     r13
0x180006084  pop     r12
0x180006086  pop     rdi
0x180006087  pop     rsi
0x180006088  pop     rbx
0x180006089  pop     rbp
0x18000608a  retn
0x18000608b  lea     rcx, [rsp+1540h+var_14F0]; this
0x180006090  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180006096  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
