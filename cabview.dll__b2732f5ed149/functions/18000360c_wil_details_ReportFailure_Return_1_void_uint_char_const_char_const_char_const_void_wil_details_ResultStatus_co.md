# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000360c`
- end: `0x180003897`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800032cc`

## callees

- `0x180002620`
- `0x180002f40`
- `0x18000360c`
- `0x180005c94`
- `0x180007b6c`
- `0x180009738`
- `0x180009c4c`
- `0x180012a20`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800036b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800036b9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800037ad`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800037ad`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003837`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003837`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // ebx
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  wil::details::in1diag3 *v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v22, (int)a7);
  v19 = *(_DWORD *)(v12 + 8) == 1;
  v13 = v11;
  v20 = 1;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v17);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x18000360c  push    rbp
0x18000360e  push    rbx
0x18000360f  push    rsi
0x180003610  push    rdi
0x180003611  push    r12
0x180003613  push    r14
0x180003615  push    r15
0x180003617  lea     rbp, [rsp-13D0h]
0x18000361f  mov     eax, 14D0h
0x180003624  call    _alloca_probe
0x180003629  sub     rsp, rax
0x18000362c  mov     rax, cs:__security_cookie
0x180003633  xor     rax, rsp
0x180003636  mov     [rbp+1400h+var_40], rax
0x18000363d  mov     rdi, [rbp+1400h+arg_28]
0x180003644  mov     r14, r8
0x180003647  mov     esi, edx
0x180003649  mov     r15, rcx
0x18000364c  xor     edx, edx; Val
0x18000364e  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003653  mov     r8d, 98h; Size
0x180003659  call    memset_0
0x18000365e  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180003665  xor     r12d, r12d
0x180003668  mov     [rbp+1400h+OutputString], r12w
0x180003670  mov     [rbp+1400h+var_1440], r12b
0x180003674  mov     ecx, [rdx]; this
0x180003676  mov     eax, [rdx+4]
0x180003679  mov     [rsp+1500h+var_14D8], ecx
0x18000367d  mov     [rsp+1500h+var_14D4], eax
0x180003681  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003686  cmp     dword ptr [rdx+8], 1
0x18000368a  mov     ebx, eax
0x18000368c  lea     eax, [r12+8]
0x180003691  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003699  mov     ecx, r12d
0x18000369c  cmovz   ecx, eax
0x18000369f  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800036a3  lea     ecx, [rax-7]
0x1800036a6  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800036ae  inc     ecx
0x1800036b0  mov     [rsp+1500h+var_14C8], r12
0x1800036b5  mov     [rsp+1500h+var_14D0], ecx
0x1800036b9  call    cs:__imp_GetCurrentThreadId
0x1800036bf  xorps   xmm0, xmm0
0x1800036c2  mov     [rsp+1500h+var_14A8], r14
0x1800036c7  mov     [rsp+1500h+var_14C0], eax
0x1800036cb  xorps   xmm1, xmm1
0x1800036ce  xor     eax, eax
0x1800036d0  mov     [rsp+1500h+var_14A0], esi
0x1800036d4  mov     [rbp+1400h+var_1468], rax
0x1800036d8  mov     [rbp+1400h+var_1480], rax
0x1800036dc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800036e3  mov     [rsp+1500h+var_149C], ebx
0x1800036e7  mov     [rsp+1500h+var_14B8], r12
0x1800036ec  mov     [rsp+1500h+var_14B0], r12
0x1800036f1  mov     [rbp+1400h+var_1458], rdi
0x1800036f5  mov     [rbp+1400h+var_1450], r15
0x1800036f9  mov     [rsp+1500h+var_1498], r12
0x1800036fe  movups  [rbp+1400h+var_1478], xmm0
0x180003702  movups  [rsp+1500h+var_1490], xmm1
0x180003707  test    rax, rax
0x18000370a  jz      short loc_180003717
0x18000370c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003711  mov     [rbp+1400h+var_1460], rax
0x180003715  jmp     short loc_18000371B
0x180003717  mov     [rbp+1400h+var_1460], r12
0x18000371b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003722  test    rax, rax
0x180003725  jz      short loc_180003731
0x180003727  lea     rcx, [rsp+1500h+var_14E0]
0x18000372c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003731  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003738  test    rax, rax
0x18000373b  jz      short loc_180003751
0x18000373d  mov     r8d, 400h
0x180003743  lea     rdx, [rbp+1400h+var_1440]
0x180003747  lea     rcx, [rsp+1500h+var_14E0]
0x18000374c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003751  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003758  test    rax, rax
0x18000375b  jz      short loc_180003767
0x18000375d  lea     rcx, [rsp+1500h+var_14E0]
0x180003762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003767  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000376e  test    rax, rax
0x180003771  jz      short loc_180003784
0x180003773  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003778  jnz     short loc_180003784
0x18000377a  lea     rcx, [rsp+1500h+var_14E0]
0x18000377f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003784  cmp     [rsp+1500h+var_14D8], r12d
0x180003789  jge     loc_180003886
0x18000378f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003796  jnz     short loc_1800037B7
0x180003798  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000379f  test    rax, rax
0x1800037a2  jz      short loc_1800037AD
0x1800037a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037a9  test    al, al
0x1800037ab  jmp     short loc_1800037B5
0x1800037ad  call    cs:__imp_IsDebuggerPresent
0x1800037b3  test    eax, eax
0x1800037b5  jz      short loc_1800037BE
0x1800037b7  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800037bc  jz      short loc_1800037E4
0x1800037be  mov     rax, cs:g_pfnResultLoggingCallback
0x1800037c5  test    rax, rax
0x1800037c8  jz      short loc_18000383D
0x1800037ca  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800037d1  jnz     short loc_18000383D
0x1800037d3  xor     r8d, r8d
0x1800037d6  lea     rcx, [rsp+1500h+var_14E0]
0x1800037db  xor     edx, edx
0x1800037dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037e2  jmp     short loc_18000383D
0x1800037e4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800037eb  mov     ebx, 800h
0x1800037f0  test    rax, rax
0x1800037f3  jz      short loc_180003812
0x1800037f5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800037fc  jnz     short loc_180003812
0x1800037fe  mov     r8d, ebx
0x180003801  lea     rdx, [rbp+1400h+OutputString]
0x180003808  lea     rcx, [rsp+1500h+var_14E0]
0x18000380d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003812  cmp     [rbp+1400h+OutputString], r12w
0x18000381a  jnz     short loc_180003830
0x18000381c  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003821  mov     rdx, rbx; unsigned __int16 *
0x180003824  lea     rcx, [rbp+1400h+OutputString]; this
0x18000382b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003830  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003837  call    cs:__imp_OutputDebugStringW
0x18000383d  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003842  jnz     short loc_18000384D
0x180003844  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000384b  jz      short loc_18000385E
0x18000384d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003854  test    rax, rax
0x180003857  jz      short loc_18000385E
0x180003859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000385e  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003863  jnz     short loc_18000388C
0x180003865  mov     rcx, [rbp+1400h+var_40]
0x18000386c  xor     rcx, rsp; StackCookie
0x18000386f  call    __security_check_cookie
0x180003874  add     rsp, 14D0h
0x18000387b  pop     r15
0x18000387d  pop     r14
0x18000387f  pop     r12
0x180003881  pop     rdi
0x180003882  pop     rsi
0x180003883  pop     rbx
0x180003884  pop     rbp
0x180003885  retn
0x180003886  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000388c  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003891  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
