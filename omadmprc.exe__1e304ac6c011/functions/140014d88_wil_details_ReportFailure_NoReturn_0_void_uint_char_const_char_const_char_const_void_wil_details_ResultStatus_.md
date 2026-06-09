# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140014d88`
- end: `0x14001504d`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140014c90`

## callees

- `0x14000271f`
- `0x140005604`
- `0x140007248`
- `0x1400093d0`
- `0x140009b3c`
- `0x140009e10`
- `0x140014d88`
- `0x140015750`
- `0x140017010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140014e31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140014e31`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140014f39`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140014f39`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140014fdb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140014fdb`

## string_xrefs

- `0x140014e41`: `onecoreuap\admin\dm\omadm\omadmprc\autothreadpool.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v9; // r15
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  char v17; // bl
  const struct wil::FailureInfo *v18; // rdx
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
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

  v9 = g_pfnThrowPlatformException != 0;
  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v21 = *a7;
  v22 = a7[1];
  v10 = wil::details::RecordException((wil::details *)(unsigned int)v21, (int)a7);
  v19 = 0;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v20 = v11;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v24 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v28 = "onecoreuap\\admin\\dm\\omadm\\omadmprc\\autothreadpool.cpp";
  v29 = a2;
  v30 = v10;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v35 = 0;
  v32 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && !v9 && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v17 = 1, (v20 & 2) != 0) )
  {
    v17 = 0;
  }
  if ( v9 || v17 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v15);
    if ( v17 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v13);
  if ( v9 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v19, OutputString);
  wil::ThrowResultException((wil *)&v19, v13);
  wil::details::WilFailFast((wil::details *)&v19, v18);
}

```

## disassembly

```asm
0x140014d88  mov     [rsp-8+arg_10], rbx
0x140014d8d  mov     [rsp-8+arg_18], rsi
0x140014d92  push    rbp
0x140014d93  push    rdi
0x140014d94  push    r12
0x140014d96  push    r14
0x140014d98  push    r15
0x140014d9a  lea     rbp, [rsp-13C0h]
0x140014da2  mov     eax, 14C0h
0x140014da7  call    _alloca_probe
0x140014dac  sub     rsp, rax
0x140014daf  mov     esi, edx
0x140014db1  mov     r14, rcx
0x140014db4  mov     rdi, [rbp+13E0h+arg_28]
0x140014dbb  xor     r12d, r12d
0x140014dbe  cmp     cs:g_pfnThrowPlatformException, r12
0x140014dc5  setnz   r15b
0x140014dc9  xor     edx, edx; Val
0x140014dcb  mov     r8d, 98h; Size
0x140014dd1  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x140014dd6  call    memset_0
0x140014ddb  nop
0x140014ddc  mov     [rbp+13E0h+OutputString], r12w
0x140014de4  mov     [rbp+13E0h+var_1420], r12b
0x140014de8  mov     rdx, qword ptr [rbp+13E0h+arg_30]; int
0x140014def  mov     ecx, [rdx]; this
0x140014df1  mov     [rsp+14E0h+var_14B8], ecx
0x140014df5  mov     eax, [rdx+4]
0x140014df8  mov     [rsp+14E0h+var_14B4], eax
0x140014dfc  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140014e01  mov     ebx, eax
0x140014e03  mov     dword ptr [rsp+14E0h+var_14C0], r12d
0x140014e08  mov     ecx, r12d
0x140014e0b  lea     eax, [r12+8]
0x140014e10  cmp     dword ptr [rdx+8], 1
0x140014e14  cmovz   ecx, eax
0x140014e17  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x140014e1b  lea     ecx, [rax-7]
0x140014e1e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140014e26  inc     ecx
0x140014e28  mov     [rsp+14E0h+var_14B0], ecx
0x140014e2c  mov     [rsp+14E0h+var_14A8], r12
0x140014e31  call    cs:__imp_GetCurrentThreadId
0x140014e38  nop     dword ptr [rax+rax+00h]
0x140014e3d  mov     [rsp+14E0h+var_14A0], eax
0x140014e41  lea     rax, aOnecoreuapAdmi_0; "onecoreuap\\admin\\dm\\omadm\\omadmprc"...
0x140014e48  mov     [rsp+14E0h+var_1488], rax
0x140014e4d  mov     [rsp+14E0h+var_1480], esi
0x140014e51  mov     [rsp+14E0h+var_147C], ebx
0x140014e55  mov     [rsp+14E0h+var_1498], r12
0x140014e5a  mov     [rsp+14E0h+var_1490], r12
0x140014e5f  mov     [rbp+13E0h+var_1438], rdi
0x140014e63  mov     [rbp+13E0h+var_1430], r14
0x140014e67  mov     [rsp+14E0h+var_1478], r12
0x140014e6c  xorps   xmm0, xmm0
0x140014e6f  xor     eax, eax
0x140014e71  movups  [rbp+13E0h+var_1458], xmm0
0x140014e75  mov     [rbp+13E0h+var_1448], rax
0x140014e79  xorps   xmm1, xmm1
0x140014e7c  movups  [rsp+14E0h+var_1470], xmm1
0x140014e81  mov     [rbp+13E0h+var_1460], rax
0x140014e85  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140014e8c  test    rax, rax
0x140014e8f  jz      short loc_140014E9C
0x140014e91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014e96  mov     [rbp+13E0h+var_1440], rax
0x140014e9a  jmp     short loc_140014EA0
0x140014e9c  mov     [rbp+13E0h+var_1440], r12
0x140014ea0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140014ea7  test    rax, rax
0x140014eaa  jz      short loc_140014EB6
0x140014eac  lea     rcx, [rsp+14E0h+var_14C0]
0x140014eb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014eb6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140014ebd  test    rax, rax
0x140014ec0  jz      short loc_140014ED6
0x140014ec2  mov     r8d, 400h
0x140014ec8  lea     rdx, [rbp+13E0h+var_1420]
0x140014ecc  lea     rcx, [rsp+14E0h+var_14C0]
0x140014ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014ed6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140014edd  test    rax, rax
0x140014ee0  jz      short loc_140014EEC
0x140014ee2  lea     rcx, [rsp+14E0h+var_14C0]
0x140014ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014eec  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140014ef3  test    rax, rax
0x140014ef6  jz      short loc_140014F0E
0x140014ef8  test    r15b, r15b
0x140014efb  jnz     short loc_140014F0E
0x140014efd  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x140014f02  jnz     short loc_140014F0E
0x140014f04  lea     rcx, [rsp+14E0h+var_14C0]
0x140014f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014f0e  cmp     [rsp+14E0h+var_14B8], r12d
0x140014f13  jl      short loc_140014F1B
0x140014f15  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140014f1b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140014f22  jnz     short loc_140014F49
0x140014f24  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140014f2b  test    rax, rax
0x140014f2e  jz      short loc_140014F39
0x140014f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014f35  test    al, al
0x140014f37  jmp     short loc_140014F47
0x140014f39  call    cs:__imp_IsDebuggerPresent
0x140014f40  nop     dword ptr [rax+rax+00h]
0x140014f45  test    eax, eax
0x140014f47  jz      short loc_140014F52
0x140014f49  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x140014f4e  mov     bl, 1
0x140014f50  jz      short loc_140014F55
0x140014f52  mov     bl, r12b
0x140014f55  test    r15b, r15b
0x140014f58  jnz     short loc_140014F84
0x140014f5a  test    bl, bl
0x140014f5c  jnz     short loc_140014F84
0x140014f5e  mov     rax, cs:g_pfnResultLoggingCallback
0x140014f65  test    rax, rax
0x140014f68  jz      short loc_140014FE7
0x140014f6a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140014f71  jnz     short loc_140014FE7
0x140014f73  xor     r8d, r8d
0x140014f76  xor     edx, edx
0x140014f78  lea     rcx, [rsp+14E0h+var_14C0]
0x140014f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014f82  jmp     short loc_140014FE7
0x140014f84  mov     edi, 800h
0x140014f89  mov     rax, cs:g_pfnResultLoggingCallback
0x140014f90  test    rax, rax
0x140014f93  jz      short loc_140014FB2
0x140014f95  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140014f9c  jnz     short loc_140014FB2
0x140014f9e  mov     r8d, edi
0x140014fa1  lea     rdx, [rbp+13E0h+OutputString]
0x140014fa8  lea     rcx, [rsp+14E0h+var_14C0]
0x140014fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014fb2  cmp     [rbp+13E0h+OutputString], r12w
0x140014fba  jnz     short loc_140014FD0
0x140014fbc  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x140014fc1  mov     rdx, rdi; unsigned __int16 *
0x140014fc4  lea     rcx, [rbp+13E0h+OutputString]; this
0x140014fcb  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140014fd0  test    bl, bl
0x140014fd2  jz      short loc_140014FE7
0x140014fd4  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x140014fdb  call    cs:__imp_OutputDebugStringW
0x140014fe2  nop     dword ptr [rax+rax+00h]
0x140014fe7  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x140014fec  jnz     short loc_140014FF7
0x140014fee  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140014ff5  jz      short loc_140015009
0x140014ff7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140014ffe  test    rax, rax
0x140015001  jz      short loc_140015009
0x140015003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015008  nop
0x140015009  test    byte ptr [rsp+14E0h+var_14C0+4], 1
0x14001500e  jz      short loc_14001501B
0x140015010  lea     rcx, [rsp+14E0h+var_14C0]; this
0x140015015  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14001501b  test    r15b, r15b
0x14001501e  jz      short loc_140015038
0x140015020  lea     rdx, [rbp+13E0h+OutputString]
0x140015027  lea     rcx, [rsp+14E0h+var_14C0]
0x14001502c  mov     rax, cs:g_pfnThrowPlatformException
0x140015033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015038  lea     rcx, [rsp+14E0h+var_14C0]; this
0x14001503d  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x140015042  lea     rcx, [rsp+14E0h+var_14C0]; this
0x140015047  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
