# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18004f5f4`
- end: `0x18004f87f`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18004f334`

## callees

- `0x1800438c8`
- `0x18004d900`
- `0x18004e530`
- `0x18004f5f4`
- `0x1800520a4`
- `0x180055f28`
- `0x18005674c`
- `0x18009a5a0`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004f6a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004f6a1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18004f81f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18004f81f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004f795`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004f795`

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
      wil::GetFailureLogString(OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
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
0x18004f5f4  push    rbp
0x18004f5f6  push    rbx
0x18004f5f7  push    rsi
0x18004f5f8  push    rdi
0x18004f5f9  push    r12
0x18004f5fb  push    r14
0x18004f5fd  push    r15
0x18004f5ff  lea     rbp, [rsp-13D0h]
0x18004f607  mov     eax, 14D0h
0x18004f60c  call    _alloca_probe
0x18004f611  sub     rsp, rax
0x18004f614  mov     rax, cs:__security_cookie
0x18004f61b  xor     rax, rsp
0x18004f61e  mov     [rbp+1400h+var_40], rax
0x18004f625  mov     rdi, [rbp+1400h+arg_28]
0x18004f62c  mov     r14, r8
0x18004f62f  mov     esi, edx
0x18004f631  mov     r15, rcx
0x18004f634  xor     edx, edx; Val
0x18004f636  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18004f63b  mov     r8d, 98h; Size
0x18004f641  call    memset_0
0x18004f646  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18004f64d  xor     r12d, r12d
0x18004f650  mov     [rbp+1400h+OutputString], r12w
0x18004f658  mov     [rbp+1400h+var_1440], r12b
0x18004f65c  mov     ecx, [rdx]; this
0x18004f65e  mov     eax, [rdx+4]
0x18004f661  mov     [rsp+1500h+var_14D8], ecx
0x18004f665  mov     [rsp+1500h+var_14D4], eax
0x18004f669  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18004f66e  cmp     dword ptr [rdx+8], 1
0x18004f672  mov     ebx, eax
0x18004f674  lea     eax, [r12+8]
0x18004f679  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18004f681  mov     ecx, r12d
0x18004f684  cmovz   ecx, eax
0x18004f687  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18004f68b  lea     ecx, [rax-7]
0x18004f68e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18004f696  inc     ecx
0x18004f698  mov     [rsp+1500h+var_14C8], r12
0x18004f69d  mov     [rsp+1500h+var_14D0], ecx
0x18004f6a1  call    cs:__imp_GetCurrentThreadId
0x18004f6a7  xorps   xmm0, xmm0
0x18004f6aa  mov     [rsp+1500h+var_14A8], r14
0x18004f6af  mov     [rsp+1500h+var_14C0], eax
0x18004f6b3  xorps   xmm1, xmm1
0x18004f6b6  xor     eax, eax
0x18004f6b8  mov     [rsp+1500h+var_14A0], esi
0x18004f6bc  mov     [rbp+1400h+var_1468], rax
0x18004f6c0  mov     [rbp+1400h+var_1480], rax
0x18004f6c4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18004f6cb  mov     [rsp+1500h+var_149C], ebx
0x18004f6cf  mov     [rsp+1500h+var_14B8], r12
0x18004f6d4  mov     [rsp+1500h+var_14B0], r12
0x18004f6d9  mov     [rbp+1400h+var_1458], rdi
0x18004f6dd  mov     [rbp+1400h+var_1450], r15
0x18004f6e1  mov     [rsp+1500h+var_1498], r12
0x18004f6e6  movups  [rbp+1400h+var_1478], xmm0
0x18004f6ea  movups  [rsp+1500h+var_1490], xmm1
0x18004f6ef  test    rax, rax
0x18004f6f2  jz      short loc_18004F6FF
0x18004f6f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f6f9  mov     [rbp+1400h+var_1460], rax
0x18004f6fd  jmp     short loc_18004F703
0x18004f6ff  mov     [rbp+1400h+var_1460], r12
0x18004f703  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18004f70a  test    rax, rax
0x18004f70d  jz      short loc_18004F719
0x18004f70f  lea     rcx, [rsp+1500h+var_14E0]
0x18004f714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f719  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18004f720  test    rax, rax
0x18004f723  jz      short loc_18004F739
0x18004f725  mov     r8d, 400h
0x18004f72b  lea     rdx, [rbp+1400h+var_1440]
0x18004f72f  lea     rcx, [rsp+1500h+var_14E0]
0x18004f734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f739  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18004f740  test    rax, rax
0x18004f743  jz      short loc_18004F74F
0x18004f745  lea     rcx, [rsp+1500h+var_14E0]
0x18004f74a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f74f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18004f756  test    rax, rax
0x18004f759  jz      short loc_18004F76C
0x18004f75b  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18004f760  jnz     short loc_18004F76C
0x18004f762  lea     rcx, [rsp+1500h+var_14E0]
0x18004f767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f76c  cmp     [rsp+1500h+var_14D8], r12d
0x18004f771  jge     loc_18004F86E
0x18004f777  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18004f77e  jnz     short loc_18004F79F
0x18004f780  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18004f787  test    rax, rax
0x18004f78a  jz      short loc_18004F795
0x18004f78c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f791  test    al, al
0x18004f793  jmp     short loc_18004F79D
0x18004f795  call    cs:__imp_IsDebuggerPresent
0x18004f79b  test    eax, eax
0x18004f79d  jz      short loc_18004F7A6
0x18004f79f  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18004f7a4  jz      short loc_18004F7CC
0x18004f7a6  mov     rax, cs:g_pfnResultLoggingCallback
0x18004f7ad  test    rax, rax
0x18004f7b0  jz      short loc_18004F825
0x18004f7b2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18004f7b9  jnz     short loc_18004F825
0x18004f7bb  xor     r8d, r8d
0x18004f7be  lea     rcx, [rsp+1500h+var_14E0]
0x18004f7c3  xor     edx, edx
0x18004f7c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f7ca  jmp     short loc_18004F825
0x18004f7cc  mov     rax, cs:g_pfnResultLoggingCallback
0x18004f7d3  mov     ebx, 800h
0x18004f7d8  test    rax, rax
0x18004f7db  jz      short loc_18004F7FA
0x18004f7dd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18004f7e4  jnz     short loc_18004F7FA
0x18004f7e6  mov     r8d, ebx
0x18004f7e9  lea     rdx, [rbp+1400h+OutputString]
0x18004f7f0  lea     rcx, [rsp+1500h+var_14E0]
0x18004f7f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f7fa  cmp     [rbp+1400h+OutputString], r12w
0x18004f802  jnz     short loc_18004F818
0x18004f804  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18004f809  mov     rdx, rbx; unsigned __int16 *
0x18004f80c  lea     rcx, [rbp+1400h+OutputString]; pszDest
0x18004f813  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18004f818  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18004f81f  call    cs:__imp_OutputDebugStringW
0x18004f825  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18004f82a  jnz     short loc_18004F835
0x18004f82c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18004f833  jz      short loc_18004F846
0x18004f835  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18004f83c  test    rax, rax
0x18004f83f  jz      short loc_18004F846
0x18004f841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f846  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18004f84b  jnz     short loc_18004F874
0x18004f84d  mov     rcx, [rbp+1400h+var_40]
0x18004f854  xor     rcx, rsp; StackCookie
0x18004f857  call    __security_check_cookie
0x18004f85c  add     rsp, 14D0h
0x18004f863  pop     r15
0x18004f865  pop     r14
0x18004f867  pop     r12
0x18004f869  pop     rdi
0x18004f86a  pop     rsi
0x18004f86b  pop     rbx
0x18004f86c  pop     rbp
0x18004f86d  retn
0x18004f86e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18004f874  lea     rcx, [rsp+1500h+var_14E0]; this
0x18004f879  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
