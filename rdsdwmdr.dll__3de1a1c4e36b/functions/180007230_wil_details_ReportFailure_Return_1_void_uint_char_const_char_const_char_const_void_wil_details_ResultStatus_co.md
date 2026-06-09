# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180007230`
- end: `0x1800074c4`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180006f04`

## callees

- `0x180007230`
- `0x1800095b0`
- `0x18000bbf0`
- `0x18000c768`
- `0x18000c85c`
- `0x18002b93a`
- `0x18002b960`
- `0x18002b9f0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800072da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800072da`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800073d5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800073d5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000745f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000745f`

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
0x180007230  mov     [rsp-8+arg_10], rbx
0x180007235  push    rbp
0x180007236  push    rsi
0x180007237  push    rdi
0x180007238  push    r14
0x18000723a  push    r15
0x18000723c  lea     rbp, [rsp-13D0h]
0x180007244  mov     eax, 14D0h
0x180007249  call    _alloca_probe
0x18000724e  sub     rsp, rax
0x180007251  mov     rax, cs:__security_cookie
0x180007258  xor     rax, rsp
0x18000725b  mov     [rbp+13F0h+var_30], rax
0x180007262  mov     rdi, [rbp+13F0h+arg_28]
0x180007269  mov     esi, edx
0x18000726b  mov     r14, rcx
0x18000726e  xor     edx, edx; Val
0x180007270  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180007275  mov     r8d, 98h; Size
0x18000727b  call    memset_0
0x180007280  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180007287  xor     r15d, r15d
0x18000728a  mov     [rbp+13F0h+OutputString], r15w
0x180007292  mov     [rbp+13F0h+var_1430], r15b
0x180007296  mov     ecx, [rdx]; this
0x180007298  mov     eax, [rdx+4]
0x18000729b  mov     [rsp+14F0h+var_14C8], ecx
0x18000729f  mov     [rsp+14F0h+var_14C4], eax
0x1800072a3  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800072a8  cmp     dword ptr [rdx+8], 1
0x1800072ac  mov     ebx, eax
0x1800072ae  lea     eax, [r15+8]
0x1800072b2  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800072ba  mov     ecx, r15d
0x1800072bd  cmovz   ecx, eax
0x1800072c0  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800072c4  lea     ecx, [rax-7]
0x1800072c7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800072cf  inc     ecx
0x1800072d1  mov     [rsp+14F0h+var_14B8], r15
0x1800072d6  mov     [rsp+14F0h+var_14C0], ecx
0x1800072da  call    cs:__imp_GetCurrentThreadId
0x1800072e0  xorps   xmm0, xmm0
0x1800072e3  mov     [rsp+14F0h+var_1490], esi
0x1800072e7  mov     [rsp+14F0h+var_14B0], eax
0x1800072eb  xorps   xmm1, xmm1
0x1800072ee  lea     rax, aWil; "wil"
0x1800072f5  mov     [rsp+14F0h+var_148C], ebx
0x1800072f9  mov     [rsp+14F0h+var_1498], rax
0x1800072fe  xor     eax, eax
0x180007300  mov     [rbp+13F0h+var_1458], rax
0x180007304  mov     [rbp+13F0h+var_1470], rax
0x180007308  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000730f  mov     [rsp+14F0h+var_14A8], r15
0x180007314  mov     [rsp+14F0h+var_14A0], r15
0x180007319  mov     [rbp+13F0h+var_1448], rdi
0x18000731d  mov     [rbp+13F0h+var_1440], r14
0x180007321  mov     [rsp+14F0h+var_1488], r15
0x180007326  movups  [rbp+13F0h+var_1468], xmm0
0x18000732a  movups  [rsp+14F0h+var_1480], xmm1
0x18000732f  test    rax, rax
0x180007332  jz      short loc_18000733F
0x180007334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007339  mov     [rbp+13F0h+var_1450], rax
0x18000733d  jmp     short loc_180007343
0x18000733f  mov     [rbp+13F0h+var_1450], r15
0x180007343  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000734a  test    rax, rax
0x18000734d  jz      short loc_180007359
0x18000734f  lea     rcx, [rsp+14F0h+var_14D0]
0x180007354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007359  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007360  test    rax, rax
0x180007363  jz      short loc_180007379
0x180007365  mov     r8d, 400h
0x18000736b  lea     rdx, [rbp+13F0h+var_1430]
0x18000736f  lea     rcx, [rsp+14F0h+var_14D0]
0x180007374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007379  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007380  test    rax, rax
0x180007383  jz      short loc_18000738F
0x180007385  lea     rcx, [rsp+14F0h+var_14D0]
0x18000738a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000738f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007396  test    rax, rax
0x180007399  jz      short loc_1800073AC
0x18000739b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800073a0  jnz     short loc_1800073AC
0x1800073a2  lea     rcx, [rsp+14F0h+var_14D0]
0x1800073a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073ac  cmp     [rsp+14F0h+var_14C8], r15d
0x1800073b1  jge     loc_1800074B3
0x1800073b7  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800073be  jnz     short loc_1800073DF
0x1800073c0  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800073c7  test    rax, rax
0x1800073ca  jz      short loc_1800073D5
0x1800073cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073d1  test    al, al
0x1800073d3  jmp     short loc_1800073DD
0x1800073d5  call    cs:__imp_IsDebuggerPresent
0x1800073db  test    eax, eax
0x1800073dd  jz      short loc_1800073E6
0x1800073df  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800073e4  jz      short loc_18000740C
0x1800073e6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800073ed  test    rax, rax
0x1800073f0  jz      short loc_180007465
0x1800073f2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800073f9  jnz     short loc_180007465
0x1800073fb  xor     r8d, r8d
0x1800073fe  lea     rcx, [rsp+14F0h+var_14D0]
0x180007403  xor     edx, edx
0x180007405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000740a  jmp     short loc_180007465
0x18000740c  mov     rax, cs:g_pfnResultLoggingCallback
0x180007413  mov     ebx, 800h
0x180007418  test    rax, rax
0x18000741b  jz      short loc_18000743A
0x18000741d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180007424  jnz     short loc_18000743A
0x180007426  mov     r8d, ebx
0x180007429  lea     rdx, [rbp+13F0h+OutputString]
0x180007430  lea     rcx, [rsp+14F0h+var_14D0]
0x180007435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000743a  cmp     [rbp+13F0h+OutputString], r15w
0x180007442  jnz     short loc_180007458
0x180007444  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180007449  mov     rdx, rbx; unsigned __int16 *
0x18000744c  lea     rcx, [rbp+13F0h+OutputString]; this
0x180007453  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007458  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000745f  call    cs:__imp_OutputDebugStringW
0x180007465  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000746a  jnz     short loc_180007475
0x18000746c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180007473  jz      short loc_180007486
0x180007475  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000747c  test    rax, rax
0x18000747f  jz      short loc_180007486
0x180007481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007486  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000748b  jnz     short loc_1800074B9
0x18000748d  mov     rcx, [rbp+13F0h+var_30]
0x180007494  xor     rcx, rsp; StackCookie
0x180007497  call    __security_check_cookie
0x18000749c  mov     rbx, [rsp+14F0h+arg_10]
0x1800074a4  add     rsp, 14D0h
0x1800074ab  pop     r15
0x1800074ad  pop     r14
0x1800074af  pop     rdi
0x1800074b0  pop     rsi
0x1800074b1  pop     rbp
0x1800074b2  retn
0x1800074b3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800074b9  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800074be  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
