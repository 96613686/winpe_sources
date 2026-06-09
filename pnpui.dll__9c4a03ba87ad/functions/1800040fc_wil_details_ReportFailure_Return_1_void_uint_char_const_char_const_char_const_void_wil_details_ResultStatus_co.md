# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800040fc`
- end: `0x180004390`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003bdc`

## callees

- `0x1800040fc`
- `0x180006444`
- `0x180008824`
- `0x18000a3b0`
- `0x18000a56c`
- `0x18000ccde`
- `0x18000cd10`
- `0x18000cda0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000432b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000432b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800042a1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800042a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800041a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800041a6`

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
0x1800040fc  mov     [rsp-8+arg_10], rbx
0x180004101  push    rbp
0x180004102  push    rsi
0x180004103  push    rdi
0x180004104  push    r14
0x180004106  push    r15
0x180004108  lea     rbp, [rsp-13D0h]
0x180004110  mov     eax, 14D0h
0x180004115  call    _alloca_probe
0x18000411a  sub     rsp, rax
0x18000411d  mov     rax, cs:__security_cookie
0x180004124  xor     rax, rsp
0x180004127  mov     [rbp+13F0h+var_30], rax
0x18000412e  mov     rdi, [rbp+13F0h+arg_28]
0x180004135  mov     esi, edx
0x180004137  mov     r14, rcx
0x18000413a  xor     edx, edx; Val
0x18000413c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180004141  mov     r8d, 98h; Size
0x180004147  call    memset_0
0x18000414c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180004153  xor     r15d, r15d
0x180004156  mov     [rbp+13F0h+OutputString], r15w
0x18000415e  mov     [rbp+13F0h+var_1430], r15b
0x180004162  mov     ecx, [rdx]; this
0x180004164  mov     eax, [rdx+4]
0x180004167  mov     [rsp+14F0h+var_14C8], ecx
0x18000416b  mov     [rsp+14F0h+var_14C4], eax
0x18000416f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004174  cmp     dword ptr [rdx+8], 1
0x180004178  mov     ebx, eax
0x18000417a  lea     eax, [r15+8]
0x18000417e  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180004186  mov     ecx, r15d
0x180004189  cmovz   ecx, eax
0x18000418c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180004190  lea     ecx, [rax-7]
0x180004193  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000419b  inc     ecx
0x18000419d  mov     [rsp+14F0h+var_14B8], r15
0x1800041a2  mov     [rsp+14F0h+var_14C0], ecx
0x1800041a6  call    cs:__imp_GetCurrentThreadId
0x1800041ac  xorps   xmm0, xmm0
0x1800041af  mov     [rsp+14F0h+var_1490], esi
0x1800041b3  mov     [rsp+14F0h+var_14B0], eax
0x1800041b7  xorps   xmm1, xmm1
0x1800041ba  lea     rax, aWil; "wil"
0x1800041c1  mov     [rsp+14F0h+var_148C], ebx
0x1800041c5  mov     [rsp+14F0h+var_1498], rax
0x1800041ca  xor     eax, eax
0x1800041cc  mov     [rbp+13F0h+var_1458], rax
0x1800041d0  mov     [rbp+13F0h+var_1470], rax
0x1800041d4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800041db  mov     [rsp+14F0h+var_14A8], r15
0x1800041e0  mov     [rsp+14F0h+var_14A0], r15
0x1800041e5  mov     [rbp+13F0h+var_1448], rdi
0x1800041e9  mov     [rbp+13F0h+var_1440], r14
0x1800041ed  mov     [rsp+14F0h+var_1488], r15
0x1800041f2  movups  [rbp+13F0h+var_1468], xmm0
0x1800041f6  movups  [rsp+14F0h+var_1480], xmm1
0x1800041fb  test    rax, rax
0x1800041fe  jz      short loc_18000420B
0x180004200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004205  mov     [rbp+13F0h+var_1450], rax
0x180004209  jmp     short loc_18000420F
0x18000420b  mov     [rbp+13F0h+var_1450], r15
0x18000420f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004216  test    rax, rax
0x180004219  jz      short loc_180004225
0x18000421b  lea     rcx, [rsp+14F0h+var_14D0]
0x180004220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004225  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000422c  test    rax, rax
0x18000422f  jz      short loc_180004245
0x180004231  mov     r8d, 400h
0x180004237  lea     rdx, [rbp+13F0h+var_1430]
0x18000423b  lea     rcx, [rsp+14F0h+var_14D0]
0x180004240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004245  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000424c  test    rax, rax
0x18000424f  jz      short loc_18000425B
0x180004251  lea     rcx, [rsp+14F0h+var_14D0]
0x180004256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000425b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004262  test    rax, rax
0x180004265  jz      short loc_180004278
0x180004267  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000426c  jnz     short loc_180004278
0x18000426e  lea     rcx, [rsp+14F0h+var_14D0]
0x180004273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004278  cmp     [rsp+14F0h+var_14C8], r15d
0x18000427d  jge     loc_18000437F
0x180004283  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000428a  jnz     short loc_1800042AB
0x18000428c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004293  test    rax, rax
0x180004296  jz      short loc_1800042A1
0x180004298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000429d  test    al, al
0x18000429f  jmp     short loc_1800042A9
0x1800042a1  call    cs:__imp_IsDebuggerPresent
0x1800042a7  test    eax, eax
0x1800042a9  jz      short loc_1800042B2
0x1800042ab  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800042b0  jz      short loc_1800042D8
0x1800042b2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800042b9  test    rax, rax
0x1800042bc  jz      short loc_180004331
0x1800042be  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800042c5  jnz     short loc_180004331
0x1800042c7  xor     r8d, r8d
0x1800042ca  lea     rcx, [rsp+14F0h+var_14D0]
0x1800042cf  xor     edx, edx
0x1800042d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042d6  jmp     short loc_180004331
0x1800042d8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800042df  mov     ebx, 800h
0x1800042e4  test    rax, rax
0x1800042e7  jz      short loc_180004306
0x1800042e9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800042f0  jnz     short loc_180004306
0x1800042f2  mov     r8d, ebx
0x1800042f5  lea     rdx, [rbp+13F0h+OutputString]
0x1800042fc  lea     rcx, [rsp+14F0h+var_14D0]
0x180004301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004306  cmp     [rbp+13F0h+OutputString], r15w
0x18000430e  jnz     short loc_180004324
0x180004310  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180004315  mov     rdx, rbx; unsigned __int16 *
0x180004318  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000431f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004324  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000432b  call    cs:__imp_OutputDebugStringW
0x180004331  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180004336  jnz     short loc_180004341
0x180004338  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000433f  jz      short loc_180004352
0x180004341  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004348  test    rax, rax
0x18000434b  jz      short loc_180004352
0x18000434d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004352  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180004357  jnz     short loc_180004385
0x180004359  mov     rcx, [rbp+13F0h+var_30]
0x180004360  xor     rcx, rsp; StackCookie
0x180004363  call    __security_check_cookie
0x180004368  mov     rbx, [rsp+14F0h+arg_10]
0x180004370  add     rsp, 14D0h
0x180004377  pop     r15
0x180004379  pop     r14
0x18000437b  pop     rdi
0x18000437c  pop     rsi
0x18000437d  pop     rbp
0x18000437e  retn
0x18000437f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004385  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000438a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
