# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800040f8`
- end: `0x18000438c`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002550`

## callees

- `0x1800040f8`
- `0x180005814`
- `0x180007140`
- `0x180008888`
- `0x180008a98`
- `0x180009922`
- `0x180009950`
- `0x1800099e0`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800041a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800041a2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000429d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000429d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004327`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004327`

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
0x1800040f8  mov     [rsp-8+arg_10], rbx
0x1800040fd  push    rbp
0x1800040fe  push    rsi
0x1800040ff  push    rdi
0x180004100  push    r14
0x180004102  push    r15
0x180004104  lea     rbp, [rsp-13D0h]
0x18000410c  mov     eax, 14D0h
0x180004111  call    _alloca_probe
0x180004116  sub     rsp, rax
0x180004119  mov     rax, cs:__security_cookie
0x180004120  xor     rax, rsp
0x180004123  mov     [rbp+13F0h+var_30], rax
0x18000412a  mov     rdi, [rbp+13F0h+arg_28]
0x180004131  mov     esi, edx
0x180004133  mov     r14, rcx
0x180004136  xor     edx, edx; Val
0x180004138  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000413d  mov     r8d, 98h; Size
0x180004143  call    memset_0
0x180004148  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000414f  xor     r15d, r15d
0x180004152  mov     [rbp+13F0h+OutputString], r15w
0x18000415a  mov     [rbp+13F0h+var_1430], r15b
0x18000415e  mov     ecx, [rdx]; this
0x180004160  mov     eax, [rdx+4]
0x180004163  mov     [rsp+14F0h+var_14C8], ecx
0x180004167  mov     [rsp+14F0h+var_14C4], eax
0x18000416b  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004170  cmp     dword ptr [rdx+8], 1
0x180004174  mov     ebx, eax
0x180004176  lea     eax, [r15+8]
0x18000417a  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180004182  mov     ecx, r15d
0x180004185  cmovz   ecx, eax
0x180004188  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000418c  lea     ecx, [rax-7]
0x18000418f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004197  inc     ecx
0x180004199  mov     [rsp+14F0h+var_14B8], r15
0x18000419e  mov     [rsp+14F0h+var_14C0], ecx
0x1800041a2  call    cs:__imp_GetCurrentThreadId
0x1800041a8  xorps   xmm0, xmm0
0x1800041ab  mov     [rsp+14F0h+var_1490], esi
0x1800041af  mov     [rsp+14F0h+var_14B0], eax
0x1800041b3  xorps   xmm1, xmm1
0x1800041b6  lea     rax, aWil; "wil"
0x1800041bd  mov     [rsp+14F0h+var_148C], ebx
0x1800041c1  mov     [rsp+14F0h+var_1498], rax
0x1800041c6  xor     eax, eax
0x1800041c8  mov     [rbp+13F0h+var_1458], rax
0x1800041cc  mov     [rbp+13F0h+var_1470], rax
0x1800041d0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800041d7  mov     [rsp+14F0h+var_14A8], r15
0x1800041dc  mov     [rsp+14F0h+var_14A0], r15
0x1800041e1  mov     [rbp+13F0h+var_1448], rdi
0x1800041e5  mov     [rbp+13F0h+var_1440], r14
0x1800041e9  mov     [rsp+14F0h+var_1488], r15
0x1800041ee  movups  [rbp+13F0h+var_1468], xmm0
0x1800041f2  movups  [rsp+14F0h+var_1480], xmm1
0x1800041f7  test    rax, rax
0x1800041fa  jz      short loc_180004207
0x1800041fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004201  mov     [rbp+13F0h+var_1450], rax
0x180004205  jmp     short loc_18000420B
0x180004207  mov     [rbp+13F0h+var_1450], r15
0x18000420b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004212  test    rax, rax
0x180004215  jz      short loc_180004221
0x180004217  lea     rcx, [rsp+14F0h+var_14D0]
0x18000421c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004221  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004228  test    rax, rax
0x18000422b  jz      short loc_180004241
0x18000422d  mov     r8d, 400h
0x180004233  lea     rdx, [rbp+13F0h+var_1430]
0x180004237  lea     rcx, [rsp+14F0h+var_14D0]
0x18000423c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004241  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004248  test    rax, rax
0x18000424b  jz      short loc_180004257
0x18000424d  lea     rcx, [rsp+14F0h+var_14D0]
0x180004252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004257  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000425e  test    rax, rax
0x180004261  jz      short loc_180004274
0x180004263  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004268  jnz     short loc_180004274
0x18000426a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000426f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004274  cmp     [rsp+14F0h+var_14C8], r15d
0x180004279  jge     loc_18000437B
0x18000427f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180004286  jnz     short loc_1800042A7
0x180004288  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000428f  test    rax, rax
0x180004292  jz      short loc_18000429D
0x180004294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004299  test    al, al
0x18000429b  jmp     short loc_1800042A5
0x18000429d  call    cs:__imp_IsDebuggerPresent
0x1800042a3  test    eax, eax
0x1800042a5  jz      short loc_1800042AE
0x1800042a7  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800042ac  jz      short loc_1800042D4
0x1800042ae  mov     rax, cs:g_pfnResultLoggingCallback
0x1800042b5  test    rax, rax
0x1800042b8  jz      short loc_18000432D
0x1800042ba  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800042c1  jnz     short loc_18000432D
0x1800042c3  xor     r8d, r8d
0x1800042c6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800042cb  xor     edx, edx
0x1800042cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042d2  jmp     short loc_18000432D
0x1800042d4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800042db  mov     ebx, 800h
0x1800042e0  test    rax, rax
0x1800042e3  jz      short loc_180004302
0x1800042e5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800042ec  jnz     short loc_180004302
0x1800042ee  mov     r8d, ebx
0x1800042f1  lea     rdx, [rbp+13F0h+OutputString]
0x1800042f8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800042fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004302  cmp     [rbp+13F0h+OutputString], r15w
0x18000430a  jnz     short loc_180004320
0x18000430c  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180004311  mov     rdx, rbx; unsigned __int16 *
0x180004314  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000431b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004320  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180004327  call    cs:__imp_OutputDebugStringW
0x18000432d  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180004332  jnz     short loc_18000433D
0x180004334  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000433b  jz      short loc_18000434E
0x18000433d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004344  test    rax, rax
0x180004347  jz      short loc_18000434E
0x180004349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000434e  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180004353  jnz     short loc_180004381
0x180004355  mov     rcx, [rbp+13F0h+var_30]
0x18000435c  xor     rcx, rsp; StackCookie
0x18000435f  call    __security_check_cookie
0x180004364  mov     rbx, [rsp+14F0h+arg_10]
0x18000436c  add     rsp, 14D0h
0x180004373  pop     r15
0x180004375  pop     r14
0x180004377  pop     rdi
0x180004378  pop     rsi
0x180004379  pop     rbp
0x18000437a  retn
0x18000437b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004381  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180004386  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
