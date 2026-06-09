# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000589c`
- end: `0x180005b29`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(unsigned __int64, unsigned int, unsigned __int64, __int64, int, unsigned __int64, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000537c`

## callees

- `0x180001500`
- `0x18000589c`
- `0x180006a04`
- `0x180007920`
- `0x180008860`
- `0x18000893c`
- `0x18000b110`
- `0x18000b8b0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000594a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000594a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005ac8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005ac8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005a3e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005a3e`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        unsigned __int64 a1,
        unsigned int a2,
        unsigned __int64 a3,
        __int64 a4,
        int a5,
        unsigned __int64 a6,
        unsigned __int64 *a7)
{
  unsigned int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  unsigned __int64 v17[20]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v18[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset(v17, 0, 0x98u);
  OutputString[0] = 0;
  v18[0] = 0;
  v17[1] = *a7;
  v10 = wil::details::RecordReturn((wil::details *)LODWORD(v17[1]), (int)a7);
  LODWORD(v17[0]) = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  HIDWORD(v17[0]) = v11;
  LODWORD(v17[2]) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v17[3] = 0;
  LODWORD(v17[4]) = GetCurrentThreadId();
  v17[7] = a3;
  v17[8] = __PAIR64__(v10, a2);
  v17[5] = 0;
  v17[6] = 0;
  v17[17] = a6;
  v17[18] = a1;
  memset(&v17[9], 0, 56);
  if ( wil::details::g_pfnGetModuleName )
    v17[16] = wil::details::g_pfnGetModuleName(v14);
  else
    v17[16] = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v17, v18, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v17);
  if ( wil::details::g_pfnOriginateCallback && (v17[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v17);
  if ( SLODWORD(v17[1]) >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v17[0] & 0x200000000LL) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString(OutputString, (unsigned __int16 *)0x800, (unsigned __int64)v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v17[0] & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)v17, v13);
}

```

## disassembly

```asm
0x18000589c  push    rbp
0x18000589e  push    rbx
0x18000589f  push    rsi
0x1800058a0  push    rdi
0x1800058a1  push    r12
0x1800058a3  push    r14
0x1800058a5  push    r15
0x1800058a7  lea     rbp, [rsp-13D0h]
0x1800058af  mov     eax, 14D0h
0x1800058b4  call    _alloca_probe
0x1800058b9  sub     rsp, rax
0x1800058bc  mov     rax, cs:__security_cookie
0x1800058c3  xor     rax, rsp
0x1800058c6  mov     [rbp+1400h+var_40], rax
0x1800058cd  mov     r14, r8
0x1800058d0  mov     esi, edx
0x1800058d2  mov     r15, rcx
0x1800058d5  mov     rdi, [rbp+1400h+arg_28]
0x1800058dc  xor     edx, edx; Val
0x1800058de  mov     r8d, 98h; Size
0x1800058e4  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800058e9  call    memset
0x1800058ee  nop
0x1800058ef  xor     r12d, r12d
0x1800058f2  mov     [rbp+1400h+OutputString], r12w
0x1800058fa  mov     [rbp+1400h+var_1440], r12b
0x1800058fe  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180005905  mov     ecx, [rdx]; this
0x180005907  mov     [rsp+1500h+var_14D8], ecx
0x18000590b  mov     eax, [rdx+4]
0x18000590e  mov     [rsp+1500h+var_14D4], eax
0x180005912  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005917  mov     ebx, eax
0x180005919  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180005921  mov     ecx, r12d
0x180005924  lea     eax, [r12+8]
0x180005929  cmp     dword ptr [rdx+8], 1
0x18000592d  cmovz   ecx, eax
0x180005930  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180005934  lea     ecx, [rax-7]
0x180005937  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000593f  inc     ecx
0x180005941  mov     [rsp+1500h+var_14D0], ecx
0x180005945  mov     [rsp+1500h+var_14C8], r12
0x18000594a  call    cs:__imp_GetCurrentThreadId
0x180005950  mov     [rsp+1500h+var_14C0], eax
0x180005954  mov     [rsp+1500h+var_14A8], r14
0x180005959  mov     [rsp+1500h+var_14A0], esi
0x18000595d  mov     [rsp+1500h+var_149C], ebx
0x180005961  mov     [rsp+1500h+var_14B8], r12
0x180005966  mov     [rsp+1500h+var_14B0], r12
0x18000596b  mov     [rbp+1400h+var_1458], rdi
0x18000596f  mov     [rbp+1400h+var_1450], r15
0x180005973  mov     [rsp+1500h+var_1498], r12
0x180005978  xorps   xmm0, xmm0
0x18000597b  xor     eax, eax
0x18000597d  movups  [rbp+1400h+var_1478], xmm0
0x180005981  mov     [rbp+1400h+var_1468], rax
0x180005985  xorps   xmm1, xmm1
0x180005988  movups  [rsp+1500h+var_1490], xmm1
0x18000598d  mov     [rbp+1400h+var_1480], rax
0x180005991  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005998  test    rax, rax
0x18000599b  jz      short loc_1800059A8
0x18000599d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059a2  mov     [rbp+1400h+var_1460], rax
0x1800059a6  jmp     short loc_1800059AC
0x1800059a8  mov     [rbp+1400h+var_1460], r12
0x1800059ac  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800059b3  test    rax, rax
0x1800059b6  jz      short loc_1800059C2
0x1800059b8  lea     rcx, [rsp+1500h+var_14E0]
0x1800059bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059c2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800059c9  test    rax, rax
0x1800059cc  jz      short loc_1800059E2
0x1800059ce  mov     r8d, 400h
0x1800059d4  lea     rdx, [rbp+1400h+var_1440]
0x1800059d8  lea     rcx, [rsp+1500h+var_14E0]
0x1800059dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059e2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800059e9  test    rax, rax
0x1800059ec  jz      short loc_1800059F8
0x1800059ee  lea     rcx, [rsp+1500h+var_14E0]
0x1800059f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059f8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800059ff  test    rax, rax
0x180005a02  jz      short loc_180005A15
0x180005a04  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005a09  jnz     short loc_180005A15
0x180005a0b  lea     rcx, [rsp+1500h+var_14E0]
0x180005a10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a15  cmp     [rsp+1500h+var_14D8], r12d
0x180005a1a  jge     loc_180005B23
0x180005a20  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180005a27  jnz     short loc_180005A48
0x180005a29  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005a30  test    rax, rax
0x180005a33  jz      short loc_180005A3E
0x180005a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a3a  test    al, al
0x180005a3c  jmp     short loc_180005A46
0x180005a3e  call    cs:__imp_IsDebuggerPresent
0x180005a44  test    eax, eax
0x180005a46  jz      short loc_180005A4F
0x180005a48  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005a4d  jz      short loc_180005A75
0x180005a4f  mov     rax, cs:g_pfnResultLoggingCallback
0x180005a56  test    rax, rax
0x180005a59  jz      short loc_180005ACE
0x180005a5b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180005a62  jnz     short loc_180005ACE
0x180005a64  xor     r8d, r8d
0x180005a67  xor     edx, edx
0x180005a69  lea     rcx, [rsp+1500h+var_14E0]
0x180005a6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a73  jmp     short loc_180005ACE
0x180005a75  mov     ebx, 800h
0x180005a7a  mov     rax, cs:g_pfnResultLoggingCallback
0x180005a81  test    rax, rax
0x180005a84  jz      short loc_180005AA3
0x180005a86  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180005a8d  jnz     short loc_180005AA3
0x180005a8f  mov     r8d, ebx
0x180005a92  lea     rdx, [rbp+1400h+OutputString]
0x180005a99  lea     rcx, [rsp+1500h+var_14E0]
0x180005a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005aa3  cmp     [rbp+1400h+OutputString], r12w
0x180005aab  jnz     short loc_180005AC1
0x180005aad  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180005ab2  mov     rdx, rbx; unsigned __int16 *
0x180005ab5  lea     rcx, [rbp+1400h+OutputString]; Buffer
0x180005abc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005ac1  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180005ac8  call    cs:__imp_OutputDebugStringW
0x180005ace  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180005ad3  jnz     short loc_180005ADE
0x180005ad5  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180005adc  jz      short loc_180005AF0
0x180005ade  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005ae5  test    rax, rax
0x180005ae8  jz      short loc_180005AF0
0x180005aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005aef  nop
0x180005af0  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180005af5  jnz     short loc_180005B18
0x180005af7  mov     rcx, [rbp+1400h+var_40]
0x180005afe  xor     rcx, rsp; StackCookie
0x180005b01  call    __security_check_cookie
0x180005b06  add     rsp, 14D0h
0x180005b0d  pop     r15
0x180005b0f  pop     r14
0x180005b11  pop     r12
0x180005b13  pop     rdi
0x180005b14  pop     rsi
0x180005b15  pop     rbx
0x180005b16  pop     rbp
0x180005b17  retn
0x180005b18  lea     rcx, [rsp+1500h+var_14E0]; this
0x180005b1d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005b23  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
