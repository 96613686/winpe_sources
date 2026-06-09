# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000427c`
- end: `0x180004510`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003f44`

## callees

- `0x18000427c`
- `0x180004f24`
- `0x180005fc0`
- `0x180006798`
- `0x180006954`
- `0x180018a52`
- `0x180018a80`
- `0x180018b10`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004326`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004326`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800044ab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800044ab`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004421`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004421`

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
0x18000427c  mov     [rsp-8+arg_10], rbx
0x180004281  push    rbp
0x180004282  push    rsi
0x180004283  push    rdi
0x180004284  push    r14
0x180004286  push    r15
0x180004288  lea     rbp, [rsp-13D0h]
0x180004290  mov     eax, 14D0h
0x180004295  call    _alloca_probe
0x18000429a  sub     rsp, rax
0x18000429d  mov     rax, cs:__security_cookie
0x1800042a4  xor     rax, rsp
0x1800042a7  mov     [rbp+13F0h+var_30], rax
0x1800042ae  mov     rdi, [rbp+13F0h+arg_28]
0x1800042b5  mov     esi, edx
0x1800042b7  mov     r14, rcx
0x1800042ba  xor     edx, edx; Val
0x1800042bc  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800042c1  mov     r8d, 98h; Size
0x1800042c7  call    memset_0
0x1800042cc  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800042d3  xor     r15d, r15d
0x1800042d6  mov     [rbp+13F0h+OutputString], r15w
0x1800042de  mov     [rbp+13F0h+var_1430], r15b
0x1800042e2  mov     ecx, [rdx]; this
0x1800042e4  mov     eax, [rdx+4]
0x1800042e7  mov     [rsp+14F0h+var_14C8], ecx
0x1800042eb  mov     [rsp+14F0h+var_14C4], eax
0x1800042ef  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800042f4  cmp     dword ptr [rdx+8], 1
0x1800042f8  mov     ebx, eax
0x1800042fa  lea     eax, [r15+8]
0x1800042fe  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180004306  mov     ecx, r15d
0x180004309  cmovz   ecx, eax
0x18000430c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180004310  lea     ecx, [rax-7]
0x180004313  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000431b  inc     ecx
0x18000431d  mov     [rsp+14F0h+var_14B8], r15
0x180004322  mov     [rsp+14F0h+var_14C0], ecx
0x180004326  call    cs:__imp_GetCurrentThreadId
0x18000432c  xorps   xmm0, xmm0
0x18000432f  mov     [rsp+14F0h+var_1490], esi
0x180004333  mov     [rsp+14F0h+var_14B0], eax
0x180004337  xorps   xmm1, xmm1
0x18000433a  lea     rax, aWil; "wil"
0x180004341  mov     [rsp+14F0h+var_148C], ebx
0x180004345  mov     [rsp+14F0h+var_1498], rax
0x18000434a  xor     eax, eax
0x18000434c  mov     [rbp+13F0h+var_1458], rax
0x180004350  mov     [rbp+13F0h+var_1470], rax
0x180004354  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000435b  mov     [rsp+14F0h+var_14A8], r15
0x180004360  mov     [rsp+14F0h+var_14A0], r15
0x180004365  mov     [rbp+13F0h+var_1448], rdi
0x180004369  mov     [rbp+13F0h+var_1440], r14
0x18000436d  mov     [rsp+14F0h+var_1488], r15
0x180004372  movups  [rbp+13F0h+var_1468], xmm0
0x180004376  movups  [rsp+14F0h+var_1480], xmm1
0x18000437b  test    rax, rax
0x18000437e  jz      short loc_18000438B
0x180004380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004385  mov     [rbp+13F0h+var_1450], rax
0x180004389  jmp     short loc_18000438F
0x18000438b  mov     [rbp+13F0h+var_1450], r15
0x18000438f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004396  test    rax, rax
0x180004399  jz      short loc_1800043A5
0x18000439b  lea     rcx, [rsp+14F0h+var_14D0]
0x1800043a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043a5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800043ac  test    rax, rax
0x1800043af  jz      short loc_1800043C5
0x1800043b1  mov     r8d, 400h
0x1800043b7  lea     rdx, [rbp+13F0h+var_1430]
0x1800043bb  lea     rcx, [rsp+14F0h+var_14D0]
0x1800043c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043c5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800043cc  test    rax, rax
0x1800043cf  jz      short loc_1800043DB
0x1800043d1  lea     rcx, [rsp+14F0h+var_14D0]
0x1800043d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043db  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800043e2  test    rax, rax
0x1800043e5  jz      short loc_1800043F8
0x1800043e7  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800043ec  jnz     short loc_1800043F8
0x1800043ee  lea     rcx, [rsp+14F0h+var_14D0]
0x1800043f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043f8  cmp     [rsp+14F0h+var_14C8], r15d
0x1800043fd  jge     loc_1800044FF
0x180004403  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000440a  jnz     short loc_18000442B
0x18000440c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004413  test    rax, rax
0x180004416  jz      short loc_180004421
0x180004418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000441d  test    al, al
0x18000441f  jmp     short loc_180004429
0x180004421  call    cs:__imp_IsDebuggerPresent
0x180004427  test    eax, eax
0x180004429  jz      short loc_180004432
0x18000442b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004430  jz      short loc_180004458
0x180004432  mov     rax, cs:g_pfnResultLoggingCallback
0x180004439  test    rax, rax
0x18000443c  jz      short loc_1800044B1
0x18000443e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004445  jnz     short loc_1800044B1
0x180004447  xor     r8d, r8d
0x18000444a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000444f  xor     edx, edx
0x180004451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004456  jmp     short loc_1800044B1
0x180004458  mov     rax, cs:g_pfnResultLoggingCallback
0x18000445f  mov     ebx, 800h
0x180004464  test    rax, rax
0x180004467  jz      short loc_180004486
0x180004469  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004470  jnz     short loc_180004486
0x180004472  mov     r8d, ebx
0x180004475  lea     rdx, [rbp+13F0h+OutputString]
0x18000447c  lea     rcx, [rsp+14F0h+var_14D0]
0x180004481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004486  cmp     [rbp+13F0h+OutputString], r15w
0x18000448e  jnz     short loc_1800044A4
0x180004490  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180004495  mov     rdx, rbx; unsigned __int16 *
0x180004498  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000449f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800044a4  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800044ab  call    cs:__imp_OutputDebugStringW
0x1800044b1  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800044b6  jnz     short loc_1800044C1
0x1800044b8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800044bf  jz      short loc_1800044D2
0x1800044c1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800044c8  test    rax, rax
0x1800044cb  jz      short loc_1800044D2
0x1800044cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044d2  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800044d7  jnz     short loc_180004505
0x1800044d9  mov     rcx, [rbp+13F0h+var_30]
0x1800044e0  xor     rcx, rsp; StackCookie
0x1800044e3  call    __security_check_cookie
0x1800044e8  mov     rbx, [rsp+14F0h+arg_10]
0x1800044f0  add     rsp, 14D0h
0x1800044f7  pop     r15
0x1800044f9  pop     r14
0x1800044fb  pop     rdi
0x1800044fc  pop     rsi
0x1800044fd  pop     rbp
0x1800044fe  retn
0x1800044ff  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004505  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000450a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
