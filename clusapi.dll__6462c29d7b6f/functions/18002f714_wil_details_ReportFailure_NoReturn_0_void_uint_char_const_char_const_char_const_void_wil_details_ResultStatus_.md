# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x18002f714`
- end: `0x18002f9d9`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002f66c`

## callees

- `0x180003c14`
- `0x18000fba4`
- `0x180011398`
- `0x180012668`
- `0x180012c08`
- `0x180012e14`
- `0x18002f714`
- `0x1800acfe0`
- `0x1800b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f7d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f7d5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002f8d1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002f8d1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002f96d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002f96d`

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
        int *a7,
        _WORD *a8)
{
  bool v11; // di
  int v12; // r12d
  int v13; // ecx
  __int64 v14; // rdx
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  char v19; // bl
  const struct wil::FailureInfo *v20; // rdx
  int v21; // [rsp+20h] [rbp-E0h] BYREF
  int v22; // [rsp+24h] [rbp-DCh]
  int v23; // [rsp+28h] [rbp-D8h]
  int v24; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v25; // [rsp+30h] [rbp-D0h]
  _WORD *v26; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v28; // [rsp+48h] [rbp-B8h]
  __int64 v29; // [rsp+50h] [rbp-B0h]
  __int64 v30; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+60h] [rbp-A0h]
  int v32; // [rsp+64h] [rbp-9Ch]
  __int64 v33; // [rsp+68h] [rbp-98h]
  __int128 v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+80h] [rbp-80h]
  __int128 v36; // [rsp+88h] [rbp-78h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v39; // [rsp+A8h] [rbp-58h]
  __int64 v40; // [rsp+B0h] [rbp-50h]
  char v41[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v11 = g_pfnThrowPlatformException != 0;
  memset_0(&v21, 0, 0x98u);
  OutputString[0] = 0;
  v41[0] = 0;
  v23 = *a7;
  v24 = a7[1];
  v12 = wil::details::RecordException((wil::details *)(unsigned int)v23, (int)a7);
  v21 = 0;
  v13 = 0;
  if ( *(_DWORD *)(v14 + 8) == 1 )
    v13 = 8;
  v22 = v13;
  v25 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v18 = *a8 == 0, v26 = a8, v18) )
    v26 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v30 = a3;
  v31 = a2;
  v32 = v12;
  v28 = 0;
  v29 = 0;
  v39 = a6;
  v40 = a1;
  v33 = 0;
  v36 = 0;
  v37 = 0;
  v34 = 0;
  v35 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v21);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v21, v41, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v21);
  if ( wil::details::g_pfnOriginateCallback && !v11 && (v22 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v21);
  if ( v23 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v19 = 1, (v22 & 2) != 0) )
  {
    v19 = 0;
  }
  if ( v11 || v19 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v21, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v21, v17);
    if ( v19 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v21, 0, 0);
  }
  if ( ((v22 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v22 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v21, v15);
  if ( v11 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v21, OutputString);
  wil::ThrowResultException((wil *)&v21, v15);
  wil::details::WilFailFast((wil::details *)&v21, v20);
}

```

## disassembly

```asm
0x18002f714  mov     [rsp-8+arg_18], rbx
0x18002f719  push    rbp
0x18002f71a  push    rsi
0x18002f71b  push    rdi
0x18002f71c  push    r12
0x18002f71e  push    r13
0x18002f720  push    r14
0x18002f722  push    r15
0x18002f724  lea     rbp, [rsp-13C0h]
0x18002f72c  mov     eax, 14C0h
0x18002f731  call    _alloca_probe
0x18002f736  sub     rsp, rax
0x18002f739  mov     r14, r8
0x18002f73c  mov     esi, edx
0x18002f73e  mov     rbx, rcx
0x18002f741  mov     r15, [rbp+13F0h+arg_28]
0x18002f748  xor     r13d, r13d
0x18002f74b  cmp     cs:g_pfnThrowPlatformException, r13
0x18002f752  setnz   dil
0x18002f756  xor     edx, edx; Val
0x18002f758  mov     r8d, 98h; Size
0x18002f75e  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18002f763  call    memset_0
0x18002f768  nop
0x18002f769  mov     [rbp+13F0h+OutputString], r13w
0x18002f771  mov     [rbp+13F0h+var_1430], r13b
0x18002f775  mov     rdx, [rbp+13F0h+arg_30]; int
0x18002f77c  mov     ecx, [rdx]; this
0x18002f77e  mov     [rsp+14F0h+var_14C8], ecx
0x18002f782  mov     eax, [rdx+4]
0x18002f785  mov     [rsp+14F0h+var_14C4], eax
0x18002f789  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18002f78e  mov     r12d, eax
0x18002f791  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18002f796  mov     ecx, r13d
0x18002f799  lea     eax, [r13+8]
0x18002f79d  cmp     dword ptr [rdx+8], 1
0x18002f7a1  cmovz   ecx, eax
0x18002f7a4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18002f7a8  lea     ecx, [rax-7]
0x18002f7ab  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002f7b3  inc     ecx
0x18002f7b5  mov     [rsp+14F0h+var_14C0], ecx
0x18002f7b9  mov     rcx, [rbp+13F0h+arg_38]
0x18002f7c0  test    rcx, rcx
0x18002f7c3  jz      short loc_18002F7D0
0x18002f7c5  cmp     [rcx], r13w
0x18002f7c9  mov     [rsp+14F0h+var_14B8], rcx
0x18002f7ce  jnz     short loc_18002F7D5
0x18002f7d0  mov     [rsp+14F0h+var_14B8], r13
0x18002f7d5  call    cs:__imp_GetCurrentThreadId
0x18002f7db  mov     [rsp+14F0h+var_14B0], eax
0x18002f7df  mov     [rsp+14F0h+var_1498], r14
0x18002f7e4  mov     [rsp+14F0h+var_1490], esi
0x18002f7e8  mov     [rsp+14F0h+var_148C], r12d
0x18002f7ed  mov     [rsp+14F0h+var_14A8], r13
0x18002f7f2  mov     [rsp+14F0h+var_14A0], r13
0x18002f7f7  mov     [rbp+13F0h+var_1448], r15
0x18002f7fb  mov     [rbp+13F0h+var_1440], rbx
0x18002f7ff  mov     [rsp+14F0h+var_1488], r13
0x18002f804  xorps   xmm0, xmm0
0x18002f807  xor     eax, eax
0x18002f809  movups  [rbp+13F0h+var_1468], xmm0
0x18002f80d  mov     [rbp+13F0h+var_1458], rax
0x18002f811  xorps   xmm1, xmm1
0x18002f814  movups  [rsp+14F0h+var_1480], xmm1
0x18002f819  mov     [rbp+13F0h+var_1470], rax
0x18002f81d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002f824  test    rax, rax
0x18002f827  jz      short loc_18002F834
0x18002f829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f82e  mov     [rbp+13F0h+var_1450], rax
0x18002f832  jmp     short loc_18002F838
0x18002f834  mov     [rbp+13F0h+var_1450], r13
0x18002f838  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002f83f  test    rax, rax
0x18002f842  jz      short loc_18002F84E
0x18002f844  lea     rcx, [rsp+14F0h+var_14D0]
0x18002f849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f84e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002f855  test    rax, rax
0x18002f858  jz      short loc_18002F86E
0x18002f85a  mov     r8d, 400h
0x18002f860  lea     rdx, [rbp+13F0h+var_1430]
0x18002f864  lea     rcx, [rsp+14F0h+var_14D0]
0x18002f869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f86e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002f875  test    rax, rax
0x18002f878  jz      short loc_18002F884
0x18002f87a  lea     rcx, [rsp+14F0h+var_14D0]
0x18002f87f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f884  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002f88b  test    rax, rax
0x18002f88e  jz      short loc_18002F8A6
0x18002f890  test    dil, dil
0x18002f893  jnz     short loc_18002F8A6
0x18002f895  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18002f89a  jnz     short loc_18002F8A6
0x18002f89c  lea     rcx, [rsp+14F0h+var_14D0]
0x18002f8a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f8a6  cmp     [rsp+14F0h+var_14C8], r13d
0x18002f8ab  jl      short loc_18002F8B3
0x18002f8ad  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18002f8b3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18002f8ba  jnz     short loc_18002F8DB
0x18002f8bc  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18002f8c3  test    rax, rax
0x18002f8c6  jz      short loc_18002F8D1
0x18002f8c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f8cd  test    al, al
0x18002f8cf  jmp     short loc_18002F8D9
0x18002f8d1  call    cs:__imp_IsDebuggerPresent
0x18002f8d7  test    eax, eax
0x18002f8d9  jz      short loc_18002F8E4
0x18002f8db  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18002f8e0  mov     bl, 1
0x18002f8e2  jz      short loc_18002F8E7
0x18002f8e4  mov     bl, r13b
0x18002f8e7  test    dil, dil
0x18002f8ea  jnz     short loc_18002F916
0x18002f8ec  test    bl, bl
0x18002f8ee  jnz     short loc_18002F916
0x18002f8f0  mov     rax, cs:g_pfnResultLoggingCallback
0x18002f8f7  test    rax, rax
0x18002f8fa  jz      short loc_18002F973
0x18002f8fc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18002f903  jnz     short loc_18002F973
0x18002f905  xor     r8d, r8d
0x18002f908  xor     edx, edx
0x18002f90a  lea     rcx, [rsp+14F0h+var_14D0]
0x18002f90f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f914  jmp     short loc_18002F973
0x18002f916  mov     esi, 800h
0x18002f91b  mov     rax, cs:g_pfnResultLoggingCallback
0x18002f922  test    rax, rax
0x18002f925  jz      short loc_18002F944
0x18002f927  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18002f92e  jnz     short loc_18002F944
0x18002f930  mov     r8d, esi
0x18002f933  lea     rdx, [rbp+13F0h+OutputString]
0x18002f93a  lea     rcx, [rsp+14F0h+var_14D0]
0x18002f93f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f944  cmp     [rbp+13F0h+OutputString], r13w
0x18002f94c  jnz     short loc_18002F962
0x18002f94e  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18002f953  mov     rdx, rsi; wchar_t *
0x18002f956  lea     rcx, [rbp+13F0h+OutputString]; this
0x18002f95d  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18002f962  test    bl, bl
0x18002f964  jz      short loc_18002F973
0x18002f966  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18002f96d  call    cs:__imp_OutputDebugStringW
0x18002f973  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18002f978  jnz     short loc_18002F983
0x18002f97a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18002f981  jz      short loc_18002F995
0x18002f983  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002f98a  test    rax, rax
0x18002f98d  jz      short loc_18002F995
0x18002f98f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f994  nop
0x18002f995  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18002f99a  jz      short loc_18002F9A7
0x18002f99c  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18002f9a1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18002f9a7  test    dil, dil
0x18002f9aa  jz      short loc_18002F9C4
0x18002f9ac  lea     rdx, [rbp+13F0h+OutputString]
0x18002f9b3  lea     rcx, [rsp+14F0h+var_14D0]
0x18002f9b8  mov     rax, cs:g_pfnThrowPlatformException
0x18002f9bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f9c4  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18002f9c9  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18002f9ce  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18002f9d3  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
