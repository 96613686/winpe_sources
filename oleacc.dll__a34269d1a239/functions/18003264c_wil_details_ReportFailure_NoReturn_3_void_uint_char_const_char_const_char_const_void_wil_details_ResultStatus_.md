# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18003264c`
- end: `0x1800328ae`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180032418`

## callees

- `0x18001efc4`
- `0x18003264c`
- `0x180034b54`
- `0x180035bd4`
- `0x180036c30`
- `0x180038a60`
- `0x180047f80`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800326ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800326ee`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800327f1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800327f1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003287b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003287b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // edx
  int v11; // edi
  int v12; // ecx
  const struct wil::FailureInfo *v13; // rdx
  __int64 v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v19, v10);
  v17 = 3;
  v12 = 0;
  if ( a7[2] == 1 )
    v12 = 8;
  v18 = v12;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v11;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
  {
    v19 = -2147418113;
    v20 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v13);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( (v18 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v14);
  }
  wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x18003264c  mov     [rsp-8+arg_18], rbx
0x180032651  push    rbp
0x180032652  push    rsi
0x180032653  push    rdi
0x180032654  push    r12
0x180032656  push    r13
0x180032658  push    r14
0x18003265a  push    r15
0x18003265c  lea     rbp, [rsp-13C0h]
0x180032664  mov     eax, 14C0h
0x180032669  call    _alloca_probe
0x18003266e  sub     rsp, rax
0x180032671  mov     r15, r8
0x180032674  mov     r14d, edx
0x180032677  mov     r12, rcx
0x18003267a  mov     rsi, [rbp+13F0h+arg_28]
0x180032681  xor     edx, edx; Val
0x180032683  mov     r8d, 98h; Size
0x180032689  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18003268e  call    memset_0
0x180032693  nop
0x180032694  xor     r13d, r13d
0x180032697  mov     [rbp+13F0h+OutputString], r13w
0x18003269f  mov     [rbp+13F0h+var_1430], r13b
0x1800326a3  mov     rbx, [rbp+13F0h+arg_30]
0x1800326aa  mov     ecx, [rbx]; this
0x1800326ac  mov     [rsp+14F0h+var_14C8], ecx
0x1800326b0  mov     eax, [rbx+4]
0x1800326b3  mov     [rsp+14F0h+var_14C4], eax
0x1800326b7  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800326bc  mov     edi, eax
0x1800326be  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800326c6  mov     ecx, r13d
0x1800326c9  lea     eax, [r13+8]
0x1800326cd  cmp     dword ptr [rbx+8], 1
0x1800326d1  cmovz   ecx, eax
0x1800326d4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800326d8  lea     ecx, [rax-7]
0x1800326db  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800326e3  inc     ecx
0x1800326e5  mov     [rsp+14F0h+var_14C0], ecx
0x1800326e9  mov     [rsp+14F0h+var_14B8], r13
0x1800326ee  call    cs:__imp_GetCurrentThreadId
0x1800326f4  mov     [rsp+14F0h+var_14B0], eax
0x1800326f8  mov     [rsp+14F0h+var_1498], r15
0x1800326fd  mov     [rsp+14F0h+var_1490], r14d
0x180032702  mov     [rsp+14F0h+var_148C], edi
0x180032706  mov     [rsp+14F0h+var_14A8], r13
0x18003270b  mov     [rsp+14F0h+var_14A0], r13
0x180032710  mov     [rbp+13F0h+var_1448], rsi
0x180032714  mov     [rbp+13F0h+var_1440], r12
0x180032718  mov     [rsp+14F0h+var_1488], r13
0x18003271d  xorps   xmm0, xmm0
0x180032720  xor     eax, eax
0x180032722  movups  [rbp+13F0h+var_1468], xmm0
0x180032726  mov     [rbp+13F0h+var_1458], rax
0x18003272a  xorps   xmm1, xmm1
0x18003272d  movups  [rsp+14F0h+var_1480], xmm1
0x180032732  mov     [rbp+13F0h+var_1470], rax
0x180032736  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18003273d  test    rax, rax
0x180032740  jz      short loc_18003274D
0x180032742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032747  mov     [rbp+13F0h+var_1450], rax
0x18003274b  jmp     short loc_180032751
0x18003274d  mov     [rbp+13F0h+var_1450], r13
0x180032751  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180032758  test    rax, rax
0x18003275b  jz      short loc_180032767
0x18003275d  lea     rcx, [rsp+14F0h+var_14D0]
0x180032762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032767  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18003276e  test    rax, rax
0x180032771  jz      short loc_180032787
0x180032773  mov     r8d, 400h
0x180032779  lea     rdx, [rbp+13F0h+var_1430]
0x18003277d  lea     rcx, [rsp+14F0h+var_14D0]
0x180032782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032787  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003278e  test    rax, rax
0x180032791  jz      short loc_18003279D
0x180032793  lea     rcx, [rsp+14F0h+var_14D0]
0x180032798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003279d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800327a4  test    rax, rax
0x1800327a7  jz      short loc_1800327BA
0x1800327a9  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800327ae  jnz     short loc_1800327BA
0x1800327b0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800327b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800327ba  cmp     [rsp+14F0h+var_14C8], r13d
0x1800327bf  jl      short loc_1800327D3
0x1800327c1  mov     ecx, 8000FFFFh; this
0x1800327c6  mov     [rsp+14F0h+var_14C8], ecx
0x1800327ca  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800327cf  mov     [rsp+14F0h+var_14C4], eax
0x1800327d3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800327da  jnz     short loc_1800327FB
0x1800327dc  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800327e3  test    rax, rax
0x1800327e6  jz      short loc_1800327F1
0x1800327e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800327ed  test    al, al
0x1800327ef  jmp     short loc_1800327F9
0x1800327f1  call    cs:__imp_IsDebuggerPresent
0x1800327f7  test    eax, eax
0x1800327f9  jz      short loc_180032802
0x1800327fb  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180032800  jz      short loc_180032828
0x180032802  mov     rax, cs:g_pfnResultLoggingCallback
0x180032809  test    rax, rax
0x18003280c  jz      short loc_180032881
0x18003280e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180032815  jnz     short loc_180032881
0x180032817  xor     r8d, r8d
0x18003281a  xor     edx, edx
0x18003281c  lea     rcx, [rsp+14F0h+var_14D0]
0x180032821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032826  jmp     short loc_180032881
0x180032828  mov     ebx, 800h
0x18003282d  mov     rax, cs:g_pfnResultLoggingCallback
0x180032834  test    rax, rax
0x180032837  jz      short loc_180032856
0x180032839  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180032840  jnz     short loc_180032856
0x180032842  mov     r8d, ebx
0x180032845  lea     rdx, [rbp+13F0h+OutputString]
0x18003284c  lea     rcx, [rsp+14F0h+var_14D0]
0x180032851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032856  cmp     [rbp+13F0h+OutputString], r13w
0x18003285e  jnz     short loc_180032874
0x180032860  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180032865  mov     rdx, rbx; unsigned __int16 *
0x180032868  lea     rcx, [rbp+13F0h+OutputString]; this
0x18003286f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180032874  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18003287b  call    cs:__imp_OutputDebugStringW
0x180032881  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180032886  jnz     short loc_180032891
0x180032888  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18003288f  jz      short loc_1800328A3
0x180032891  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180032898  test    rax, rax
0x18003289b  jz      short loc_1800328A3
0x18003289d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800328a2  nop
0x1800328a3  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800328a8  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
