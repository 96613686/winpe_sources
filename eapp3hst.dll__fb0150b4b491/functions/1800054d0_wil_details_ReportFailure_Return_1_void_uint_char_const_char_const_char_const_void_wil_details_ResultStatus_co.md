# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800054d0`
- end: `0x180005766`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180005198`

## callees

- `0x1800017a0`
- `0x18000213c`
- `0x180002ad4`
- `0x1800054d0`
- `0x180009df8`
- `0x18000b78c`
- `0x18000b944`
- `0x18002f450`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000557b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000557b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005700`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005700`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005676`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005676`

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
0x1800054d0  mov     [rsp-8+arg_10], rbx
0x1800054d5  push    rbp
0x1800054d6  push    rsi
0x1800054d7  push    rdi
0x1800054d8  push    r14
0x1800054da  push    r15
0x1800054dc  lea     rbp, [rsp-13D0h]
0x1800054e4  mov     eax, 14D0h
0x1800054e9  call    _alloca_probe
0x1800054ee  sub     rsp, rax
0x1800054f1  mov     rax, cs:__security_cookie
0x1800054f8  xor     rax, rsp
0x1800054fb  mov     [rbp+13F0h+var_30], rax
0x180005502  mov     esi, edx
0x180005504  mov     r14, rcx
0x180005507  mov     rdi, [rbp+13F0h+arg_28]
0x18000550e  xor     edx, edx; Val
0x180005510  mov     r8d, 98h; Size
0x180005516  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000551b  call    memset_0
0x180005520  nop
0x180005521  xor     r15d, r15d
0x180005524  mov     [rbp+13F0h+OutputString], r15w
0x18000552c  mov     [rbp+13F0h+var_1430], r15b
0x180005530  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180005537  mov     ecx, [rdx]; this
0x180005539  mov     [rsp+14F0h+var_14C8], ecx
0x18000553d  mov     eax, [rdx+4]
0x180005540  mov     [rsp+14F0h+var_14C4], eax
0x180005544  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005549  mov     ebx, eax
0x18000554b  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180005553  mov     ecx, r15d
0x180005556  lea     eax, [r15+8]
0x18000555a  cmp     dword ptr [rdx+8], 1
0x18000555e  cmovz   ecx, eax
0x180005561  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180005565  lea     ecx, [rax-7]
0x180005568  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005570  inc     ecx
0x180005572  mov     [rsp+14F0h+var_14C0], ecx
0x180005576  mov     [rsp+14F0h+var_14B8], r15
0x18000557b  call    cs:__imp_GetCurrentThreadId
0x180005581  mov     [rsp+14F0h+var_14B0], eax
0x180005585  lea     rax, aWil; "wil"
0x18000558c  mov     [rsp+14F0h+var_1498], rax
0x180005591  mov     [rsp+14F0h+var_1490], esi
0x180005595  mov     [rsp+14F0h+var_148C], ebx
0x180005599  mov     [rsp+14F0h+var_14A8], r15
0x18000559e  mov     [rsp+14F0h+var_14A0], r15
0x1800055a3  mov     [rbp+13F0h+var_1448], rdi
0x1800055a7  mov     [rbp+13F0h+var_1440], r14
0x1800055ab  mov     [rsp+14F0h+var_1488], r15
0x1800055b0  xorps   xmm0, xmm0
0x1800055b3  xor     eax, eax
0x1800055b5  movups  [rbp+13F0h+var_1468], xmm0
0x1800055b9  mov     [rbp+13F0h+var_1458], rax
0x1800055bd  xorps   xmm1, xmm1
0x1800055c0  movups  [rsp+14F0h+var_1480], xmm1
0x1800055c5  mov     [rbp+13F0h+var_1470], rax
0x1800055c9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800055d0  test    rax, rax
0x1800055d3  jz      short loc_1800055E0
0x1800055d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055da  mov     [rbp+13F0h+var_1450], rax
0x1800055de  jmp     short loc_1800055E4
0x1800055e0  mov     [rbp+13F0h+var_1450], r15
0x1800055e4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800055eb  test    rax, rax
0x1800055ee  jz      short loc_1800055FA
0x1800055f0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800055f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055fa  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005601  test    rax, rax
0x180005604  jz      short loc_18000561A
0x180005606  mov     r8d, 400h
0x18000560c  lea     rdx, [rbp+13F0h+var_1430]
0x180005610  lea     rcx, [rsp+14F0h+var_14D0]
0x180005615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000561a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005621  test    rax, rax
0x180005624  jz      short loc_180005630
0x180005626  lea     rcx, [rsp+14F0h+var_14D0]
0x18000562b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005630  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005637  test    rax, rax
0x18000563a  jz      short loc_18000564D
0x18000563c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005641  jnz     short loc_18000564D
0x180005643  lea     rcx, [rsp+14F0h+var_14D0]
0x180005648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000564d  cmp     [rsp+14F0h+var_14C8], r15d
0x180005652  jge     loc_180005760
0x180005658  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000565f  jnz     short loc_180005680
0x180005661  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005668  test    rax, rax
0x18000566b  jz      short loc_180005676
0x18000566d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005672  test    al, al
0x180005674  jmp     short loc_18000567E
0x180005676  call    cs:__imp_IsDebuggerPresent
0x18000567c  test    eax, eax
0x18000567e  jz      short loc_180005687
0x180005680  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005685  jz      short loc_1800056AD
0x180005687  mov     rax, cs:g_pfnResultLoggingCallback
0x18000568e  test    rax, rax
0x180005691  jz      short loc_180005706
0x180005693  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000569a  jnz     short loc_180005706
0x18000569c  xor     r8d, r8d
0x18000569f  xor     edx, edx
0x1800056a1  lea     rcx, [rsp+14F0h+var_14D0]
0x1800056a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056ab  jmp     short loc_180005706
0x1800056ad  mov     ebx, 800h
0x1800056b2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800056b9  test    rax, rax
0x1800056bc  jz      short loc_1800056DB
0x1800056be  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800056c5  jnz     short loc_1800056DB
0x1800056c7  mov     r8d, ebx
0x1800056ca  lea     rdx, [rbp+13F0h+OutputString]
0x1800056d1  lea     rcx, [rsp+14F0h+var_14D0]
0x1800056d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056db  cmp     [rbp+13F0h+OutputString], r15w
0x1800056e3  jnz     short loc_1800056F9
0x1800056e5  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800056ea  mov     rdx, rbx; wchar_t *
0x1800056ed  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800056f4  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800056f9  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180005700  call    cs:__imp_OutputDebugStringW
0x180005706  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000570b  jnz     short loc_180005716
0x18000570d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180005714  jz      short loc_180005728
0x180005716  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000571d  test    rax, rax
0x180005720  jz      short loc_180005728
0x180005722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005727  nop
0x180005728  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000572d  jnz     short loc_180005755
0x18000572f  mov     rcx, [rbp+13F0h+var_30]
0x180005736  xor     rcx, rsp; StackCookie
0x180005739  call    __security_check_cookie
0x18000573e  mov     rbx, [rsp+14F0h+arg_10]
0x180005746  add     rsp, 14D0h
0x18000574d  pop     r15
0x18000574f  pop     r14
0x180005751  pop     rdi
0x180005752  pop     rsi
0x180005753  pop     rbp
0x180005754  retn
0x180005755  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000575a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005760  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
