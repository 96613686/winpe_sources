# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000f530`
- end: `0x18000f7c4`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000f204`

## callees

- `0x18000ab30`
- `0x18000b468`
- `0x18000f530`
- `0x180010254`
- `0x180011dd0`
- `0x1800144d8`
- `0x1800146b8`
- `0x180029f60`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f5da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f5da`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000f6d5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000f6d5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000f75f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000f75f`

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
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD v25; // [rsp+40h] [rbp-C0h]
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v18 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  v19 = 1;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v20 = v13;
  v24 = 0;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v25 = CurrentThreadId;
  v30 = v12;
  v28 = "wil";
  v35 = 0;
  v33 = 0;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x18000f530  mov     [rsp-8+arg_10], rbx
0x18000f535  push    rbp
0x18000f536  push    rsi
0x18000f537  push    rdi
0x18000f538  push    r14
0x18000f53a  push    r15
0x18000f53c  lea     rbp, [rsp-13D0h]
0x18000f544  mov     eax, 14D0h
0x18000f549  call    _alloca_probe
0x18000f54e  sub     rsp, rax
0x18000f551  mov     rax, cs:__security_cookie
0x18000f558  xor     rax, rsp
0x18000f55b  mov     [rbp+13F0h+var_30], rax
0x18000f562  mov     rdi, [rbp+13F0h+arg_28]
0x18000f569  mov     esi, edx
0x18000f56b  mov     r14, rcx
0x18000f56e  xor     edx, edx; Val
0x18000f570  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000f575  mov     r8d, 98h; Size
0x18000f57b  call    memset_0
0x18000f580  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000f587  xor     r15d, r15d
0x18000f58a  mov     [rbp+13F0h+OutputString], r15w
0x18000f592  mov     [rbp+13F0h+var_1430], r15b
0x18000f596  mov     ecx, [rdx]; this
0x18000f598  mov     eax, [rdx+4]
0x18000f59b  mov     [rsp+14F0h+var_14C8], ecx
0x18000f59f  mov     [rsp+14F0h+var_14C4], eax
0x18000f5a3  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000f5a8  cmp     dword ptr [rdx+8], 1
0x18000f5ac  mov     ebx, eax
0x18000f5ae  lea     eax, [r15+8]
0x18000f5b2  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000f5ba  mov     ecx, r15d
0x18000f5bd  cmovz   ecx, eax
0x18000f5c0  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000f5c4  lea     ecx, [rax-7]
0x18000f5c7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000f5cf  inc     ecx
0x18000f5d1  mov     [rsp+14F0h+var_14B8], r15
0x18000f5d6  mov     [rsp+14F0h+var_14C0], ecx
0x18000f5da  call    cs:__imp_GetCurrentThreadId
0x18000f5e0  xorps   xmm0, xmm0
0x18000f5e3  mov     [rsp+14F0h+var_1490], esi
0x18000f5e7  mov     [rsp+14F0h+var_14B0], eax
0x18000f5eb  xorps   xmm1, xmm1
0x18000f5ee  lea     rax, aWil; "wil"
0x18000f5f5  mov     [rsp+14F0h+var_148C], ebx
0x18000f5f9  mov     [rsp+14F0h+var_1498], rax
0x18000f5fe  xor     eax, eax
0x18000f600  mov     [rbp+13F0h+var_1458], rax
0x18000f604  mov     [rbp+13F0h+var_1470], rax
0x18000f608  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000f60f  mov     [rsp+14F0h+var_14A8], r15
0x18000f614  mov     [rsp+14F0h+var_14A0], r15
0x18000f619  mov     [rbp+13F0h+var_1448], rdi
0x18000f61d  mov     [rbp+13F0h+var_1440], r14
0x18000f621  mov     [rsp+14F0h+var_1488], r15
0x18000f626  movups  [rbp+13F0h+var_1468], xmm0
0x18000f62a  movups  [rsp+14F0h+var_1480], xmm1
0x18000f62f  test    rax, rax
0x18000f632  jz      short loc_18000F63F
0x18000f634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f639  mov     [rbp+13F0h+var_1450], rax
0x18000f63d  jmp     short loc_18000F643
0x18000f63f  mov     [rbp+13F0h+var_1450], r15
0x18000f643  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000f64a  test    rax, rax
0x18000f64d  jz      short loc_18000F659
0x18000f64f  lea     rcx, [rsp+14F0h+var_14D0]
0x18000f654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f659  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000f660  test    rax, rax
0x18000f663  jz      short loc_18000F679
0x18000f665  mov     r8d, 400h
0x18000f66b  lea     rdx, [rbp+13F0h+var_1430]
0x18000f66f  lea     rcx, [rsp+14F0h+var_14D0]
0x18000f674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f679  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000f680  test    rax, rax
0x18000f683  jz      short loc_18000F68F
0x18000f685  lea     rcx, [rsp+14F0h+var_14D0]
0x18000f68a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f68f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000f696  test    rax, rax
0x18000f699  jz      short loc_18000F6AC
0x18000f69b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000f6a0  jnz     short loc_18000F6AC
0x18000f6a2  lea     rcx, [rsp+14F0h+var_14D0]
0x18000f6a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6ac  cmp     [rsp+14F0h+var_14C8], r15d
0x18000f6b1  jge     loc_18000F7B3
0x18000f6b7  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000f6be  jnz     short loc_18000F6DF
0x18000f6c0  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000f6c7  test    rax, rax
0x18000f6ca  jz      short loc_18000F6D5
0x18000f6cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6d1  test    al, al
0x18000f6d3  jmp     short loc_18000F6DD
0x18000f6d5  call    cs:__imp_IsDebuggerPresent
0x18000f6db  test    eax, eax
0x18000f6dd  jz      short loc_18000F6E6
0x18000f6df  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000f6e4  jz      short loc_18000F70C
0x18000f6e6  mov     rax, cs:g_pfnResultLoggingCallback
0x18000f6ed  test    rax, rax
0x18000f6f0  jz      short loc_18000F765
0x18000f6f2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000f6f9  jnz     short loc_18000F765
0x18000f6fb  xor     r8d, r8d
0x18000f6fe  lea     rcx, [rsp+14F0h+var_14D0]
0x18000f703  xor     edx, edx
0x18000f705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f70a  jmp     short loc_18000F765
0x18000f70c  mov     rax, cs:g_pfnResultLoggingCallback
0x18000f713  mov     ebx, 800h
0x18000f718  test    rax, rax
0x18000f71b  jz      short loc_18000F73A
0x18000f71d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000f724  jnz     short loc_18000F73A
0x18000f726  mov     r8d, ebx
0x18000f729  lea     rdx, [rbp+13F0h+OutputString]
0x18000f730  lea     rcx, [rsp+14F0h+var_14D0]
0x18000f735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f73a  cmp     [rbp+13F0h+OutputString], r15w
0x18000f742  jnz     short loc_18000F758
0x18000f744  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000f749  mov     rdx, rbx; unsigned __int16 *
0x18000f74c  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000f753  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000f758  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000f75f  call    cs:__imp_OutputDebugStringW
0x18000f765  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000f76a  jnz     short loc_18000F775
0x18000f76c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000f773  jz      short loc_18000F786
0x18000f775  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000f77c  test    rax, rax
0x18000f77f  jz      short loc_18000F786
0x18000f781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f786  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000f78b  jnz     short loc_18000F7B9
0x18000f78d  mov     rcx, [rbp+13F0h+var_30]
0x18000f794  xor     rcx, rsp; StackCookie
0x18000f797  call    __security_check_cookie
0x18000f79c  mov     rbx, [rsp+14F0h+arg_10]
0x18000f7a4  add     rsp, 14D0h
0x18000f7ab  pop     r15
0x18000f7ad  pop     r14
0x18000f7af  pop     rdi
0x18000f7b0  pop     rsi
0x18000f7b1  pop     rbp
0x18000f7b2  retn
0x18000f7b3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000f7b9  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000f7be  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
