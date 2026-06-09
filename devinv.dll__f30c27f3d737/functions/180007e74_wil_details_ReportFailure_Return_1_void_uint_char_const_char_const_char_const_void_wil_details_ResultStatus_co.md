# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180007e74`
- end: `0x180008101`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000794c`

## callees

- `0x180005e40`
- `0x180006ec4`
- `0x180007e74`
- `0x18000a734`
- `0x18000c0f8`
- `0x18000e8e0`
- `0x18000eaac`
- `0x18010d870`
- `0x180116010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007f22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007f22`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800080a0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800080a0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008016`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008016`

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
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v19, (int)a7);
  v17 = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v18 = v11;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v10;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( ((v18 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v18 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x180007e74  push    rbp
0x180007e76  push    rbx
0x180007e77  push    rsi
0x180007e78  push    rdi
0x180007e79  push    r12
0x180007e7b  push    r14
0x180007e7d  push    r15
0x180007e7f  lea     rbp, [rsp-13D0h]
0x180007e87  mov     eax, 14D0h
0x180007e8c  call    _alloca_probe
0x180007e91  sub     rsp, rax
0x180007e94  mov     rax, cs:__security_cookie
0x180007e9b  xor     rax, rsp
0x180007e9e  mov     [rbp+1400h+var_40], rax
0x180007ea5  mov     r14, r8
0x180007ea8  mov     esi, edx
0x180007eaa  mov     r15, rcx
0x180007ead  mov     rdi, [rbp+1400h+arg_28]
0x180007eb4  xor     edx, edx; Val
0x180007eb6  mov     r8d, 98h; Size
0x180007ebc  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180007ec1  call    memset_0
0x180007ec6  nop
0x180007ec7  xor     r12d, r12d
0x180007eca  mov     [rbp+1400h+OutputString], r12w
0x180007ed2  mov     [rbp+1400h+var_1440], r12b
0x180007ed6  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180007edd  mov     ecx, [rdx]; this
0x180007edf  mov     [rsp+1500h+var_14D8], ecx
0x180007ee3  mov     eax, [rdx+4]
0x180007ee6  mov     [rsp+1500h+var_14D4], eax
0x180007eea  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007eef  mov     ebx, eax
0x180007ef1  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180007ef9  mov     ecx, r12d
0x180007efc  lea     eax, [r12+8]
0x180007f01  cmp     dword ptr [rdx+8], 1
0x180007f05  cmovz   ecx, eax
0x180007f08  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180007f0c  lea     ecx, [rax-7]
0x180007f0f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007f17  inc     ecx
0x180007f19  mov     [rsp+1500h+var_14D0], ecx
0x180007f1d  mov     [rsp+1500h+var_14C8], r12
0x180007f22  call    cs:__imp_GetCurrentThreadId
0x180007f28  mov     [rsp+1500h+var_14C0], eax
0x180007f2c  mov     [rsp+1500h+var_14A8], r14
0x180007f31  mov     [rsp+1500h+var_14A0], esi
0x180007f35  mov     [rsp+1500h+var_149C], ebx
0x180007f39  mov     [rsp+1500h+var_14B8], r12
0x180007f3e  mov     [rsp+1500h+var_14B0], r12
0x180007f43  mov     [rbp+1400h+var_1458], rdi
0x180007f47  mov     [rbp+1400h+var_1450], r15
0x180007f4b  mov     [rsp+1500h+var_1498], r12
0x180007f50  xorps   xmm0, xmm0
0x180007f53  xor     eax, eax
0x180007f55  movups  [rbp+1400h+var_1478], xmm0
0x180007f59  mov     [rbp+1400h+var_1468], rax
0x180007f5d  xorps   xmm1, xmm1
0x180007f60  movups  [rsp+1500h+var_1490], xmm1
0x180007f65  mov     [rbp+1400h+var_1480], rax
0x180007f69  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007f70  test    rax, rax
0x180007f73  jz      short loc_180007F80
0x180007f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f7a  mov     [rbp+1400h+var_1460], rax
0x180007f7e  jmp     short loc_180007F84
0x180007f80  mov     [rbp+1400h+var_1460], r12
0x180007f84  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007f8b  test    rax, rax
0x180007f8e  jz      short loc_180007F9A
0x180007f90  lea     rcx, [rsp+1500h+var_14E0]
0x180007f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f9a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007fa1  test    rax, rax
0x180007fa4  jz      short loc_180007FBA
0x180007fa6  mov     r8d, 400h
0x180007fac  lea     rdx, [rbp+1400h+var_1440]
0x180007fb0  lea     rcx, [rsp+1500h+var_14E0]
0x180007fb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fba  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007fc1  test    rax, rax
0x180007fc4  jz      short loc_180007FD0
0x180007fc6  lea     rcx, [rsp+1500h+var_14E0]
0x180007fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fd0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007fd7  test    rax, rax
0x180007fda  jz      short loc_180007FED
0x180007fdc  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180007fe1  jnz     short loc_180007FED
0x180007fe3  lea     rcx, [rsp+1500h+var_14E0]
0x180007fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fed  cmp     [rsp+1500h+var_14D8], r12d
0x180007ff2  jge     loc_1800080FB
0x180007ff8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180007fff  jnz     short loc_180008020
0x180008001  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008008  test    rax, rax
0x18000800b  jz      short loc_180008016
0x18000800d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008012  test    al, al
0x180008014  jmp     short loc_18000801E
0x180008016  call    cs:__imp_IsDebuggerPresent
0x18000801c  test    eax, eax
0x18000801e  jz      short loc_180008027
0x180008020  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180008025  jz      short loc_18000804D
0x180008027  mov     rax, cs:g_pfnResultLoggingCallback
0x18000802e  test    rax, rax
0x180008031  jz      short loc_1800080A6
0x180008033  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000803a  jnz     short loc_1800080A6
0x18000803c  xor     r8d, r8d
0x18000803f  xor     edx, edx
0x180008041  lea     rcx, [rsp+1500h+var_14E0]
0x180008046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000804b  jmp     short loc_1800080A6
0x18000804d  mov     ebx, 800h
0x180008052  mov     rax, cs:g_pfnResultLoggingCallback
0x180008059  test    rax, rax
0x18000805c  jz      short loc_18000807B
0x18000805e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180008065  jnz     short loc_18000807B
0x180008067  mov     r8d, ebx
0x18000806a  lea     rdx, [rbp+1400h+OutputString]
0x180008071  lea     rcx, [rsp+1500h+var_14E0]
0x180008076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000807b  cmp     [rbp+1400h+OutputString], r12w
0x180008083  jnz     short loc_180008099
0x180008085  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000808a  mov     rdx, rbx; unsigned __int16 *
0x18000808d  lea     rcx, [rbp+1400h+OutputString]; this
0x180008094  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008099  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800080a0  call    cs:__imp_OutputDebugStringW
0x1800080a6  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800080ab  jnz     short loc_1800080B6
0x1800080ad  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800080b4  jz      short loc_1800080C8
0x1800080b6  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800080bd  test    rax, rax
0x1800080c0  jz      short loc_1800080C8
0x1800080c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080c7  nop
0x1800080c8  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800080cd  jnz     short loc_1800080F0
0x1800080cf  mov     rcx, [rbp+1400h+var_40]
0x1800080d6  xor     rcx, rsp; StackCookie
0x1800080d9  call    __security_check_cookie
0x1800080de  add     rsp, 14D0h
0x1800080e5  pop     r15
0x1800080e7  pop     r14
0x1800080e9  pop     r12
0x1800080eb  pop     rdi
0x1800080ec  pop     rsi
0x1800080ed  pop     rbx
0x1800080ee  pop     rbp
0x1800080ef  retn
0x1800080f0  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800080f5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800080fb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
