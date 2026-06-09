# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140003148`
- end: `0x1400033d3`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `651`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140002eb0`

## callees

- `0x140002b2c`
- `0x140003148`
- `0x140004b34`
- `0x1400052b8`
- `0x1400069c0`
- `0x140008dcc`
- `0x14002e860`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003201`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003201`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000339a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000339a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000330a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000330a`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // edx
  int v12; // r12d
  int v13; // ecx
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, v11);
  v18 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v19 = v13;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v12;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
  {
    v20 = -2147418113;
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v14);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v15);
  }
  wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x140003148  mov     [rsp-8+arg_18], rbx
0x14000314d  push    rbp
0x14000314e  push    rsi
0x14000314f  push    rdi
0x140003150  push    r12
0x140003152  push    r13
0x140003154  push    r14
0x140003156  push    r15
0x140003158  lea     rbp, [rsp-13C0h]
0x140003160  mov     eax, 14C0h
0x140003165  call    _alloca_probe
0x14000316a  sub     rsp, rax
0x14000316d  mov     r14, r8
0x140003170  mov     esi, edx
0x140003172  mov     rdi, rcx
0x140003175  mov     r15, [rbp+13F0h+arg_28]
0x14000317c  xor     edx, edx; Val
0x14000317e  mov     r8d, 98h; Size
0x140003184  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140003189  call    memset_0
0x14000318e  nop
0x14000318f  xor     r13d, r13d
0x140003192  mov     [rbp+13F0h+OutputString], r13w
0x14000319a  mov     [rbp+13F0h+var_1430], r13b
0x14000319e  mov     rbx, [rbp+13F0h+arg_30]
0x1400031a5  mov     ecx, [rbx]; this
0x1400031a7  mov     [rsp+14F0h+var_14C8], ecx
0x1400031ab  mov     eax, [rbx+4]
0x1400031ae  mov     [rsp+14F0h+var_14C4], eax
0x1400031b2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400031b7  mov     r12d, eax
0x1400031ba  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1400031c2  mov     ecx, r13d
0x1400031c5  lea     eax, [r13+8]
0x1400031c9  cmp     dword ptr [rbx+8], 1
0x1400031cd  cmovz   ecx, eax
0x1400031d0  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1400031d4  lea     ecx, [rax-7]
0x1400031d7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400031df  inc     ecx
0x1400031e1  mov     [rsp+14F0h+var_14C0], ecx
0x1400031e5  mov     rcx, [rbp+13F0h+arg_38]
0x1400031ec  test    rcx, rcx
0x1400031ef  jz      short loc_1400031FC
0x1400031f1  cmp     [rcx], r13w
0x1400031f5  mov     [rsp+14F0h+var_14B8], rcx
0x1400031fa  jnz     short loc_140003201
0x1400031fc  mov     [rsp+14F0h+var_14B8], r13
0x140003201  call    cs:__imp_GetCurrentThreadId
0x140003208  nop     dword ptr [rax+rax+00h]
0x14000320d  mov     [rsp+14F0h+var_14B0], eax
0x140003211  mov     [rsp+14F0h+var_1498], r14
0x140003216  mov     [rsp+14F0h+var_1490], esi
0x14000321a  mov     [rsp+14F0h+var_148C], r12d
0x14000321f  mov     [rsp+14F0h+var_14A8], r13
0x140003224  mov     [rsp+14F0h+var_14A0], r13
0x140003229  mov     [rbp+13F0h+var_1448], r15
0x14000322d  mov     [rbp+13F0h+var_1440], rdi
0x140003231  mov     [rsp+14F0h+var_1488], r13
0x140003236  xorps   xmm0, xmm0
0x140003239  xor     eax, eax
0x14000323b  movups  [rbp+13F0h+var_1468], xmm0
0x14000323f  mov     [rbp+13F0h+var_1458], rax
0x140003243  xorps   xmm1, xmm1
0x140003246  movups  [rsp+14F0h+var_1480], xmm1
0x14000324b  mov     [rbp+13F0h+var_1470], rax
0x14000324f  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003256  test    rax, rax
0x140003259  jz      short loc_140003266
0x14000325b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003260  mov     [rbp+13F0h+var_1450], rax
0x140003264  jmp     short loc_14000326A
0x140003266  mov     [rbp+13F0h+var_1450], r13
0x14000326a  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003271  test    rax, rax
0x140003274  jz      short loc_140003280
0x140003276  lea     rcx, [rsp+14F0h+var_14D0]
0x14000327b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003280  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140003287  test    rax, rax
0x14000328a  jz      short loc_1400032A0
0x14000328c  mov     r8d, 400h
0x140003292  lea     rdx, [rbp+13F0h+var_1430]
0x140003296  lea     rcx, [rsp+14F0h+var_14D0]
0x14000329b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400032a0  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400032a7  test    rax, rax
0x1400032aa  jz      short loc_1400032B6
0x1400032ac  lea     rcx, [rsp+14F0h+var_14D0]
0x1400032b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400032b6  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400032bd  test    rax, rax
0x1400032c0  jz      short loc_1400032D3
0x1400032c2  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400032c7  jnz     short loc_1400032D3
0x1400032c9  lea     rcx, [rsp+14F0h+var_14D0]
0x1400032ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400032d3  cmp     [rsp+14F0h+var_14C8], r13d
0x1400032d8  jl      short loc_1400032EC
0x1400032da  mov     ecx, 8000FFFFh; this
0x1400032df  mov     [rsp+14F0h+var_14C8], ecx
0x1400032e3  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400032e8  mov     [rsp+14F0h+var_14C4], eax
0x1400032ec  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1400032f3  jnz     short loc_14000331A
0x1400032f5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400032fc  test    rax, rax
0x1400032ff  jz      short loc_14000330A
0x140003301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003306  test    al, al
0x140003308  jmp     short loc_140003318
0x14000330a  call    cs:__imp_IsDebuggerPresent
0x140003311  nop     dword ptr [rax+rax+00h]
0x140003316  test    eax, eax
0x140003318  jz      short loc_140003321
0x14000331a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000331f  jz      short loc_140003347
0x140003321  mov     rax, cs:g_pfnResultLoggingCallback
0x140003328  test    rax, rax
0x14000332b  jz      short loc_1400033A6
0x14000332d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140003334  jnz     short loc_1400033A6
0x140003336  xor     r8d, r8d
0x140003339  xor     edx, edx
0x14000333b  lea     rcx, [rsp+14F0h+var_14D0]
0x140003340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003345  jmp     short loc_1400033A6
0x140003347  mov     ebx, 800h
0x14000334c  mov     rax, cs:g_pfnResultLoggingCallback
0x140003353  test    rax, rax
0x140003356  jz      short loc_140003375
0x140003358  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x14000335f  jnz     short loc_140003375
0x140003361  mov     r8d, ebx
0x140003364  lea     rdx, [rbp+13F0h+OutputString]
0x14000336b  lea     rcx, [rsp+14F0h+var_14D0]
0x140003370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003375  cmp     [rbp+13F0h+OutputString], r13w
0x14000337d  jnz     short loc_140003393
0x14000337f  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140003384  mov     rdx, rbx; unsigned __int16 *
0x140003387  lea     rcx, [rbp+13F0h+OutputString]; this
0x14000338e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140003393  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x14000339a  call    cs:__imp_OutputDebugStringW
0x1400033a1  nop     dword ptr [rax+rax+00h]
0x1400033a6  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1400033ab  jnz     short loc_1400033B6
0x1400033ad  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1400033b4  jz      short loc_1400033C8
0x1400033b6  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400033bd  test    rax, rax
0x1400033c0  jz      short loc_1400033C8
0x1400033c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400033c7  nop
0x1400033c8  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1400033cd  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
