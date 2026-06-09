# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180007f34`
- end: `0x1800081e0`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180007d5c`

## callees

- `0x180002ef8`
- `0x180005534`
- `0x1800064c4`
- `0x1800072b4`
- `0x180007610`
- `0x180007798`
- `0x180007f34`
- `0x18002df90`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007fdd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007fdd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008174`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008174`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800080d8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800080d8`

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
  bool v10; // r12
  int v11; // ebx
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  char v18; // bl
  const struct wil::FailureInfo *v19; // rdx
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v10 = g_pfnThrowPlatformException != 0;
  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v22 = *a7;
  v23 = a7[1];
  v11 = wil::details::RecordException((wil::details *)(unsigned int)v22, (int)a7);
  v20 = 0;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v21 = v12;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v25 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v30 = a2;
  v31 = v11;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && !v10 && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v18 = 1, (v21 & 2) != 0) )
  {
    v18 = 0;
  }
  if ( v10 || v18 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v20, v16);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0, v16);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v14);
  if ( v10 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v20, OutputString);
  wil::ThrowResultException((wil *)&v20, v14);
  wil::details::WilFailFast((wil::details *)&v20, v19);
}

```

## disassembly

```asm
0x180007f34  mov     [rsp-8+arg_18], rbx
0x180007f39  push    rbp
0x180007f3a  push    rsi
0x180007f3b  push    rdi
0x180007f3c  push    r12
0x180007f3e  push    r13
0x180007f40  push    r14
0x180007f42  push    r15
0x180007f44  lea     rbp, [rsp-13C0h]
0x180007f4c  mov     eax, 14C0h
0x180007f51  call    _alloca_probe
0x180007f56  sub     rsp, rax
0x180007f59  mov     r14, r8
0x180007f5c  mov     esi, edx
0x180007f5e  mov     r15, rcx
0x180007f61  mov     rdi, [rbp+13F0h+arg_28]
0x180007f68  xor     r13d, r13d
0x180007f6b  cmp     cs:g_pfnThrowPlatformException, r13
0x180007f72  setnz   r12b
0x180007f76  xor     edx, edx; Val
0x180007f78  mov     r8d, 98h; Size
0x180007f7e  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180007f83  call    memset_0
0x180007f88  nop
0x180007f89  mov     [rbp+13F0h+OutputString], r13w
0x180007f91  mov     [rbp+13F0h+var_1430], r13b
0x180007f95  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180007f9c  mov     ecx, [rdx]; this
0x180007f9e  mov     [rsp+14F0h+var_14C8], ecx
0x180007fa2  mov     eax, [rdx+4]
0x180007fa5  mov     [rsp+14F0h+var_14C4], eax
0x180007fa9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180007fae  mov     ebx, eax
0x180007fb0  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x180007fb5  mov     ecx, r13d
0x180007fb8  lea     eax, [r13+8]
0x180007fbc  cmp     dword ptr [rdx+8], 1
0x180007fc0  cmovz   ecx, eax
0x180007fc3  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180007fc7  lea     ecx, [rax-7]
0x180007fca  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007fd2  inc     ecx
0x180007fd4  mov     [rsp+14F0h+var_14C0], ecx
0x180007fd8  mov     [rsp+14F0h+var_14B8], r13
0x180007fdd  call    cs:__imp_GetCurrentThreadId
0x180007fe3  mov     [rsp+14F0h+var_14B0], eax
0x180007fe7  mov     [rsp+14F0h+var_1498], r14
0x180007fec  mov     [rsp+14F0h+var_1490], esi
0x180007ff0  mov     [rsp+14F0h+var_148C], ebx
0x180007ff4  mov     [rsp+14F0h+var_14A8], r13
0x180007ff9  mov     [rsp+14F0h+var_14A0], r13
0x180007ffe  mov     [rbp+13F0h+var_1448], rdi
0x180008002  mov     [rbp+13F0h+var_1440], r15
0x180008006  mov     [rsp+14F0h+var_1488], r13
0x18000800b  xorps   xmm0, xmm0
0x18000800e  xor     eax, eax
0x180008010  movups  [rbp+13F0h+var_1468], xmm0
0x180008014  mov     [rbp+13F0h+var_1458], rax
0x180008018  xorps   xmm1, xmm1
0x18000801b  movups  [rsp+14F0h+var_1480], xmm1
0x180008020  mov     [rbp+13F0h+var_1470], rax
0x180008024  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000802b  test    rax, rax
0x18000802e  jz      short loc_18000803B
0x180008030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008035  mov     [rbp+13F0h+var_1450], rax
0x180008039  jmp     short loc_18000803F
0x18000803b  mov     [rbp+13F0h+var_1450], r13
0x18000803f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008046  test    rax, rax
0x180008049  jz      short loc_180008055
0x18000804b  lea     rcx, [rsp+14F0h+var_14D0]
0x180008050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008055  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000805c  test    rax, rax
0x18000805f  jz      short loc_180008075
0x180008061  mov     r8d, 400h
0x180008067  lea     rdx, [rbp+13F0h+var_1430]
0x18000806b  lea     rcx, [rsp+14F0h+var_14D0]
0x180008070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008075  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000807c  test    rax, rax
0x18000807f  jz      short loc_18000808B
0x180008081  lea     rcx, [rsp+14F0h+var_14D0]
0x180008086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000808b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008092  test    rax, rax
0x180008095  jz      short loc_1800080AD
0x180008097  test    r12b, r12b
0x18000809a  jnz     short loc_1800080AD
0x18000809c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800080a1  jnz     short loc_1800080AD
0x1800080a3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800080a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080ad  cmp     [rsp+14F0h+var_14C8], r13d
0x1800080b2  jl      short loc_1800080BA
0x1800080b4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800080ba  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800080c1  jnz     short loc_1800080E2
0x1800080c3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800080ca  test    rax, rax
0x1800080cd  jz      short loc_1800080D8
0x1800080cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080d4  test    al, al
0x1800080d6  jmp     short loc_1800080E0
0x1800080d8  call    cs:__imp_IsDebuggerPresent
0x1800080de  test    eax, eax
0x1800080e0  jz      short loc_1800080EB
0x1800080e2  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800080e7  mov     bl, 1
0x1800080e9  jz      short loc_1800080EE
0x1800080eb  mov     bl, r13b
0x1800080ee  test    r12b, r12b
0x1800080f1  jnz     short loc_18000811D
0x1800080f3  test    bl, bl
0x1800080f5  jnz     short loc_18000811D
0x1800080f7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800080fe  test    rax, rax
0x180008101  jz      short loc_18000817A
0x180008103  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000810a  jnz     short loc_18000817A
0x18000810c  xor     r8d, r8d
0x18000810f  xor     edx, edx
0x180008111  lea     rcx, [rsp+14F0h+var_14D0]
0x180008116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000811b  jmp     short loc_18000817A
0x18000811d  mov     edi, 800h
0x180008122  mov     rax, cs:g_pfnResultLoggingCallback
0x180008129  test    rax, rax
0x18000812c  jz      short loc_18000814B
0x18000812e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180008135  jnz     short loc_18000814B
0x180008137  mov     r8d, edi
0x18000813a  lea     rdx, [rbp+13F0h+OutputString]
0x180008141  lea     rcx, [rsp+14F0h+var_14D0]
0x180008146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000814b  cmp     [rbp+13F0h+OutputString], r13w
0x180008153  jnz     short loc_180008169
0x180008155  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000815a  mov     rdx, rdi; unsigned __int16 *
0x18000815d  lea     rcx, [rbp+13F0h+OutputString]; this
0x180008164  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008169  test    bl, bl
0x18000816b  jz      short loc_18000817A
0x18000816d  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180008174  call    cs:__imp_OutputDebugStringW
0x18000817a  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000817f  jnz     short loc_18000818A
0x180008181  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180008188  jz      short loc_18000819C
0x18000818a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008191  test    rax, rax
0x180008194  jz      short loc_18000819C
0x180008196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000819b  nop
0x18000819c  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800081a1  jz      short loc_1800081AE
0x1800081a3  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800081a8  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800081ae  test    r12b, r12b
0x1800081b1  jz      short loc_1800081CB
0x1800081b3  lea     rdx, [rbp+13F0h+OutputString]
0x1800081ba  lea     rcx, [rsp+14F0h+var_14D0]
0x1800081bf  mov     rax, cs:g_pfnThrowPlatformException
0x1800081c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081cb  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800081d0  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x1800081d5  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800081da  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
