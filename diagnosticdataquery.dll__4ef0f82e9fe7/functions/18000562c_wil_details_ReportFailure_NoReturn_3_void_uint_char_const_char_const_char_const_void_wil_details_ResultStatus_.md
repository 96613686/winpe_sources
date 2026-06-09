# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000562c`
- end: `0x180005895`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `617`
- prototype: `void __fastcall __noreturn(unsigned __int64, unsigned int, __int64, __int64, int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800053d8`

## callees

- `0x18000562c`
- `0x180006a04`
- `0x1800071a4`
- `0x1800078f0`
- `0x180008860`
- `0x18000b110`
- `0x18000b8b0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800056ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800056ce`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005862`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005862`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800057d8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800057d8`

## string_xrefs

- `0x1800056d8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        unsigned __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        unsigned __int64 a6,
        __int64 a7)
{
  int v9; // edx
  unsigned int v10; // edi
  int v11; // ecx
  const struct wil::FailureInfo *v12; // rdx
  __int64 v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  unsigned __int64 v16[20]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v17[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset(v16, 0, 0x98u);
  OutputString[0] = 0;
  v17[0] = 0;
  v16[1] = *(_QWORD *)a7;
  v10 = wil::details::RecordFailFast((wil::details *)LODWORD(v16[1]), v9);
  LODWORD(v16[0]) = 3;
  v11 = 0;
  if ( *(_DWORD *)(a7 + 8) == 1 )
    v11 = 8;
  HIDWORD(v16[0]) = v11;
  LODWORD(v16[2]) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v16[3] = 0;
  LODWORD(v16[4]) = GetCurrentThreadId();
  v16[7] = (unsigned __int64)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h";
  v16[8] = __PAIR64__(v10, a2);
  v16[5] = 0;
  v16[6] = 0;
  v16[17] = a6;
  v16[18] = a1;
  memset(&v16[9], 0, 56);
  if ( wil::details::g_pfnGetModuleName )
    v16[16] = wil::details::g_pfnGetModuleName(v13);
  else
    v16[16] = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v16, v17, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v16);
  if ( wil::details::g_pfnOriginateCallback && (v16[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v16);
  if ( SLODWORD(v16[1]) >= 0 )
  {
    LODWORD(v16[1]) = -2147418113;
    HIDWORD(v16[1]) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v12);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v16[0] & 0x200000000LL) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString(OutputString, (unsigned __int16 *)0x800, (unsigned __int64)v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( (v16[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v13);
  }
  wil::details::WilFailFast((wil::details *)v16, v12);
}

```

## disassembly

```asm
0x18000562c  mov     [rsp-8+arg_10], rbx
0x180005631  mov     [rsp-8+arg_18], rsi
0x180005636  push    rbp
0x180005637  push    rdi
0x180005638  push    r12
0x18000563a  push    r14
0x18000563c  push    r15
0x18000563e  lea     rbp, [rsp-13C0h]
0x180005646  mov     eax, 14C0h
0x18000564b  call    _alloca_probe
0x180005650  sub     rsp, rax
0x180005653  mov     r14d, edx
0x180005656  mov     r15, rcx
0x180005659  mov     rsi, [rbp+13E0h+arg_28]
0x180005660  xor     edx, edx; Val
0x180005662  mov     r8d, 98h; Size
0x180005668  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x18000566d  call    memset
0x180005672  nop
0x180005673  xor     r12d, r12d
0x180005676  mov     [rbp+13E0h+OutputString], r12w
0x18000567e  mov     [rbp+13E0h+var_1420], r12b
0x180005682  mov     rbx, [rbp+13E0h+arg_30]
0x180005689  mov     ecx, [rbx]; this
0x18000568b  mov     [rsp+14E0h+var_14B8], ecx
0x18000568f  mov     eax, [rbx+4]
0x180005692  mov     [rsp+14E0h+var_14B4], eax
0x180005696  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000569b  mov     edi, eax
0x18000569d  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x1800056a5  mov     ecx, r12d
0x1800056a8  lea     eax, [r12+8]
0x1800056ad  cmp     dword ptr [rbx+8], 1
0x1800056b1  cmovz   ecx, eax
0x1800056b4  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x1800056b8  lea     ecx, [rax-7]
0x1800056bb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800056c3  inc     ecx
0x1800056c5  mov     [rsp+14E0h+var_14B0], ecx
0x1800056c9  mov     [rsp+14E0h+var_14A8], r12
0x1800056ce  call    cs:__imp_GetCurrentThreadId
0x1800056d4  mov     [rsp+14E0h+var_14A0], eax
0x1800056d8  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800056df  mov     [rsp+14E0h+var_1488], rax
0x1800056e4  mov     [rsp+14E0h+var_1480], r14d
0x1800056e9  mov     [rsp+14E0h+var_147C], edi
0x1800056ed  mov     [rsp+14E0h+var_1498], r12
0x1800056f2  mov     [rsp+14E0h+var_1490], r12
0x1800056f7  mov     [rbp+13E0h+var_1438], rsi
0x1800056fb  mov     [rbp+13E0h+var_1430], r15
0x1800056ff  mov     [rsp+14E0h+var_1478], r12
0x180005704  xorps   xmm0, xmm0
0x180005707  xor     eax, eax
0x180005709  movups  [rbp+13E0h+var_1458], xmm0
0x18000570d  mov     [rbp+13E0h+var_1448], rax
0x180005711  xorps   xmm1, xmm1
0x180005714  movups  [rsp+14E0h+var_1470], xmm1
0x180005719  mov     [rbp+13E0h+var_1460], rax
0x18000571d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005724  test    rax, rax
0x180005727  jz      short loc_180005734
0x180005729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000572e  mov     [rbp+13E0h+var_1440], rax
0x180005732  jmp     short loc_180005738
0x180005734  mov     [rbp+13E0h+var_1440], r12
0x180005738  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000573f  test    rax, rax
0x180005742  jz      short loc_18000574E
0x180005744  lea     rcx, [rsp+14E0h+var_14C0]
0x180005749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000574e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005755  test    rax, rax
0x180005758  jz      short loc_18000576E
0x18000575a  mov     r8d, 400h
0x180005760  lea     rdx, [rbp+13E0h+var_1420]
0x180005764  lea     rcx, [rsp+14E0h+var_14C0]
0x180005769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000576e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005775  test    rax, rax
0x180005778  jz      short loc_180005784
0x18000577a  lea     rcx, [rsp+14E0h+var_14C0]
0x18000577f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005784  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000578b  test    rax, rax
0x18000578e  jz      short loc_1800057A1
0x180005790  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180005795  jnz     short loc_1800057A1
0x180005797  lea     rcx, [rsp+14E0h+var_14C0]
0x18000579c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057a1  cmp     [rsp+14E0h+var_14B8], r12d
0x1800057a6  jl      short loc_1800057BA
0x1800057a8  mov     ecx, 8000FFFFh; this
0x1800057ad  mov     [rsp+14E0h+var_14B8], ecx
0x1800057b1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800057b6  mov     [rsp+14E0h+var_14B4], eax
0x1800057ba  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800057c1  jnz     short loc_1800057E2
0x1800057c3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800057ca  test    rax, rax
0x1800057cd  jz      short loc_1800057D8
0x1800057cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057d4  test    al, al
0x1800057d6  jmp     short loc_1800057E0
0x1800057d8  call    cs:__imp_IsDebuggerPresent
0x1800057de  test    eax, eax
0x1800057e0  jz      short loc_1800057E9
0x1800057e2  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1800057e7  jz      short loc_18000580F
0x1800057e9  mov     rax, cs:g_pfnResultLoggingCallback
0x1800057f0  test    rax, rax
0x1800057f3  jz      short loc_180005868
0x1800057f5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800057fc  jnz     short loc_180005868
0x1800057fe  xor     r8d, r8d
0x180005801  xor     edx, edx
0x180005803  lea     rcx, [rsp+14E0h+var_14C0]
0x180005808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000580d  jmp     short loc_180005868
0x18000580f  mov     ebx, 800h
0x180005814  mov     rax, cs:g_pfnResultLoggingCallback
0x18000581b  test    rax, rax
0x18000581e  jz      short loc_18000583D
0x180005820  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180005827  jnz     short loc_18000583D
0x180005829  mov     r8d, ebx
0x18000582c  lea     rdx, [rbp+13E0h+OutputString]
0x180005833  lea     rcx, [rsp+14E0h+var_14C0]
0x180005838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000583d  cmp     [rbp+13E0h+OutputString], r12w
0x180005845  jnz     short loc_18000585B
0x180005847  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x18000584c  mov     rdx, rbx; unsigned __int16 *
0x18000584f  lea     rcx, [rbp+13E0h+OutputString]; Buffer
0x180005856  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000585b  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180005862  call    cs:__imp_OutputDebugStringW
0x180005868  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x18000586d  jnz     short loc_180005878
0x18000586f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180005876  jz      short loc_18000588A
0x180005878  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000587f  test    rax, rax
0x180005882  jz      short loc_18000588A
0x180005884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005889  nop
0x18000588a  lea     rcx, [rsp+14E0h+var_14C0]; this
0x18000588f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
