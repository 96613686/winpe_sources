# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000328c`
- end: `0x180003522`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002d6c`

## callees

- `0x180001f60`
- `0x1800028dc`
- `0x18000328c`
- `0x1800057b4`
- `0x1800070a8`
- `0x180009880`
- `0x180009a4c`
- `0x180014e20`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003337`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003337`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003432`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003432`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800034bc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800034bc`

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
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x18000328c  mov     [rsp-8+arg_10], rbx
0x180003291  push    rbp
0x180003292  push    rsi
0x180003293  push    rdi
0x180003294  push    r14
0x180003296  push    r15
0x180003298  lea     rbp, [rsp-13D0h]
0x1800032a0  mov     eax, 14D0h
0x1800032a5  call    _alloca_probe
0x1800032aa  sub     rsp, rax
0x1800032ad  mov     rax, cs:__security_cookie
0x1800032b4  xor     rax, rsp
0x1800032b7  mov     [rbp+13F0h+var_30], rax
0x1800032be  mov     esi, edx
0x1800032c0  mov     r14, rcx
0x1800032c3  mov     rdi, [rbp+13F0h+arg_28]
0x1800032ca  xor     edx, edx; Val
0x1800032cc  mov     r8d, 98h; Size
0x1800032d2  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800032d7  call    memset_0
0x1800032dc  nop
0x1800032dd  xor     r15d, r15d
0x1800032e0  mov     [rbp+13F0h+OutputString], r15w
0x1800032e8  mov     [rbp+13F0h+var_1430], r15b
0x1800032ec  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800032f3  mov     ecx, [rdx]; this
0x1800032f5  mov     [rsp+14F0h+var_14C8], ecx
0x1800032f9  mov     eax, [rdx+4]
0x1800032fc  mov     [rsp+14F0h+var_14C4], eax
0x180003300  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003305  mov     ebx, eax
0x180003307  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000330f  mov     ecx, r15d
0x180003312  lea     eax, [r15+8]
0x180003316  cmp     dword ptr [rdx+8], 1
0x18000331a  cmovz   ecx, eax
0x18000331d  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003321  lea     ecx, [rax-7]
0x180003324  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000332c  inc     ecx
0x18000332e  mov     [rsp+14F0h+var_14C0], ecx
0x180003332  mov     [rsp+14F0h+var_14B8], r15
0x180003337  call    cs:__imp_GetCurrentThreadId
0x18000333d  mov     [rsp+14F0h+var_14B0], eax
0x180003341  lea     rax, aWil; "wil"
0x180003348  mov     [rsp+14F0h+var_1498], rax
0x18000334d  mov     [rsp+14F0h+var_1490], esi
0x180003351  mov     [rsp+14F0h+var_148C], ebx
0x180003355  mov     [rsp+14F0h+var_14A8], r15
0x18000335a  mov     [rsp+14F0h+var_14A0], r15
0x18000335f  mov     [rbp+13F0h+var_1448], rdi
0x180003363  mov     [rbp+13F0h+var_1440], r14
0x180003367  mov     [rsp+14F0h+var_1488], r15
0x18000336c  xorps   xmm0, xmm0
0x18000336f  xor     eax, eax
0x180003371  movups  [rbp+13F0h+var_1468], xmm0
0x180003375  mov     [rbp+13F0h+var_1458], rax
0x180003379  xorps   xmm1, xmm1
0x18000337c  movups  [rsp+14F0h+var_1480], xmm1
0x180003381  mov     [rbp+13F0h+var_1470], rax
0x180003385  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000338c  test    rax, rax
0x18000338f  jz      short loc_18000339C
0x180003391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003396  mov     [rbp+13F0h+var_1450], rax
0x18000339a  jmp     short loc_1800033A0
0x18000339c  mov     [rbp+13F0h+var_1450], r15
0x1800033a0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800033a7  test    rax, rax
0x1800033aa  jz      short loc_1800033B6
0x1800033ac  lea     rcx, [rsp+14F0h+var_14D0]
0x1800033b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033b6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800033bd  test    rax, rax
0x1800033c0  jz      short loc_1800033D6
0x1800033c2  mov     r8d, 400h
0x1800033c8  lea     rdx, [rbp+13F0h+var_1430]
0x1800033cc  lea     rcx, [rsp+14F0h+var_14D0]
0x1800033d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033d6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800033dd  test    rax, rax
0x1800033e0  jz      short loc_1800033EC
0x1800033e2  lea     rcx, [rsp+14F0h+var_14D0]
0x1800033e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033ec  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800033f3  test    rax, rax
0x1800033f6  jz      short loc_180003409
0x1800033f8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800033fd  jnz     short loc_180003409
0x1800033ff  lea     rcx, [rsp+14F0h+var_14D0]
0x180003404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003409  cmp     [rsp+14F0h+var_14C8], r15d
0x18000340e  jge     loc_18000351C
0x180003414  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000341b  jnz     short loc_18000343C
0x18000341d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003424  test    rax, rax
0x180003427  jz      short loc_180003432
0x180003429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000342e  test    al, al
0x180003430  jmp     short loc_18000343A
0x180003432  call    cs:__imp_IsDebuggerPresent
0x180003438  test    eax, eax
0x18000343a  jz      short loc_180003443
0x18000343c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003441  jz      short loc_180003469
0x180003443  mov     rax, cs:g_pfnResultLoggingCallback
0x18000344a  test    rax, rax
0x18000344d  jz      short loc_1800034C2
0x18000344f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003456  jnz     short loc_1800034C2
0x180003458  xor     r8d, r8d
0x18000345b  xor     edx, edx
0x18000345d  lea     rcx, [rsp+14F0h+var_14D0]
0x180003462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003467  jmp     short loc_1800034C2
0x180003469  mov     ebx, 800h
0x18000346e  mov     rax, cs:g_pfnResultLoggingCallback
0x180003475  test    rax, rax
0x180003478  jz      short loc_180003497
0x18000347a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003481  jnz     short loc_180003497
0x180003483  mov     r8d, ebx
0x180003486  lea     rdx, [rbp+13F0h+OutputString]
0x18000348d  lea     rcx, [rsp+14F0h+var_14D0]
0x180003492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003497  cmp     [rbp+13F0h+OutputString], r15w
0x18000349f  jnz     short loc_1800034B5
0x1800034a1  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800034a6  mov     rdx, rbx; wchar_t *
0x1800034a9  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800034b0  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800034b5  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800034bc  call    cs:__imp_OutputDebugStringW
0x1800034c2  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800034c7  jnz     short loc_1800034D2
0x1800034c9  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800034d0  jz      short loc_1800034E4
0x1800034d2  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800034d9  test    rax, rax
0x1800034dc  jz      short loc_1800034E4
0x1800034de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034e3  nop
0x1800034e4  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800034e9  jnz     short loc_180003511
0x1800034eb  mov     rcx, [rbp+13F0h+var_30]
0x1800034f2  xor     rcx, rsp; StackCookie
0x1800034f5  call    __security_check_cookie
0x1800034fa  mov     rbx, [rsp+14F0h+arg_10]
0x180003502  add     rsp, 14D0h
0x180003509  pop     r15
0x18000350b  pop     r14
0x18000350d  pop     rdi
0x18000350e  pop     rsi
0x18000350f  pop     rbp
0x180003510  retn
0x180003511  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003516  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000351c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
