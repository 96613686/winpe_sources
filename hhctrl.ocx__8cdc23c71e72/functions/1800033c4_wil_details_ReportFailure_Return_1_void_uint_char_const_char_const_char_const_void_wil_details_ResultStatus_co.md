# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800033c4`
- end: `0x18000365a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002ecc`

## callees

- `0x1800033c4`
- `0x180005554`
- `0x180008130`
- `0x180009f80`
- `0x18000a13c`
- `0x180075c5a`
- `0x180075c90`
- `0x180075d50`
- `0x180078010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x1800035f4`
- `KERNEL32!OutputDebugStringW` at `0x1800035f4`
- `KERNEL32!IsDebuggerPresent` at `0x18000356a`
- `KERNEL32!IsDebuggerPresent` at `0x18000356a`
- `KERNEL32!GetCurrentThreadId` at `0x18000346f`
- `KERNEL32!GetCurrentThreadId` at `0x18000346f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
      wil::GetFailureLogString(OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
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
0x1800033c4  mov     [rsp-8+arg_10], rbx
0x1800033c9  push    rbp
0x1800033ca  push    rsi
0x1800033cb  push    rdi
0x1800033cc  push    r14
0x1800033ce  push    r15
0x1800033d0  lea     rbp, [rsp-13D0h]
0x1800033d8  mov     eax, 14D0h
0x1800033dd  call    _alloca_probe
0x1800033e2  sub     rsp, rax
0x1800033e5  mov     rax, cs:__security_cookie
0x1800033ec  xor     rax, rsp
0x1800033ef  mov     [rbp+13F0h+var_30], rax
0x1800033f6  mov     esi, edx
0x1800033f8  mov     r14, rcx
0x1800033fb  mov     rdi, [rbp+13F0h+arg_28]
0x180003402  xor     edx, edx; Val
0x180003404  mov     r8d, 98h; Size
0x18000340a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000340f  call    memset_0
0x180003414  nop
0x180003415  xor     r15d, r15d
0x180003418  mov     [rbp+13F0h+OutputString], r15w
0x180003420  mov     [rbp+13F0h+var_1430], r15b
0x180003424  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000342b  mov     ecx, [rdx]; this
0x18000342d  mov     [rsp+14F0h+var_14C8], ecx
0x180003431  mov     eax, [rdx+4]
0x180003434  mov     [rsp+14F0h+var_14C4], eax
0x180003438  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000343d  mov     ebx, eax
0x18000343f  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180003447  mov     ecx, r15d
0x18000344a  lea     eax, [r15+8]
0x18000344e  cmp     dword ptr [rdx+8], 1
0x180003452  cmovz   ecx, eax
0x180003455  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003459  lea     ecx, [rax-7]
0x18000345c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003464  inc     ecx
0x180003466  mov     [rsp+14F0h+var_14C0], ecx
0x18000346a  mov     [rsp+14F0h+var_14B8], r15
0x18000346f  call    cs:__imp_GetCurrentThreadId
0x180003475  mov     [rsp+14F0h+var_14B0], eax
0x180003479  lea     rax, aWil; "wil"
0x180003480  mov     [rsp+14F0h+var_1498], rax
0x180003485  mov     [rsp+14F0h+var_1490], esi
0x180003489  mov     [rsp+14F0h+var_148C], ebx
0x18000348d  mov     [rsp+14F0h+var_14A8], r15
0x180003492  mov     [rsp+14F0h+var_14A0], r15
0x180003497  mov     [rbp+13F0h+var_1448], rdi
0x18000349b  mov     [rbp+13F0h+var_1440], r14
0x18000349f  mov     [rsp+14F0h+var_1488], r15
0x1800034a4  xorps   xmm0, xmm0
0x1800034a7  xor     eax, eax
0x1800034a9  movups  [rbp+13F0h+var_1468], xmm0
0x1800034ad  mov     [rbp+13F0h+var_1458], rax
0x1800034b1  xorps   xmm1, xmm1
0x1800034b4  movups  [rsp+14F0h+var_1480], xmm1
0x1800034b9  mov     [rbp+13F0h+var_1470], rax
0x1800034bd  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800034c4  test    rax, rax
0x1800034c7  jz      short loc_1800034D4
0x1800034c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034ce  mov     [rbp+13F0h+var_1450], rax
0x1800034d2  jmp     short loc_1800034D8
0x1800034d4  mov     [rbp+13F0h+var_1450], r15
0x1800034d8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800034df  test    rax, rax
0x1800034e2  jz      short loc_1800034EE
0x1800034e4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800034e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034ee  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800034f5  test    rax, rax
0x1800034f8  jz      short loc_18000350E
0x1800034fa  mov     r8d, 400h
0x180003500  lea     rdx, [rbp+13F0h+var_1430]
0x180003504  lea     rcx, [rsp+14F0h+var_14D0]
0x180003509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000350e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003515  test    rax, rax
0x180003518  jz      short loc_180003524
0x18000351a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000351f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003524  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000352b  test    rax, rax
0x18000352e  jz      short loc_180003541
0x180003530  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003535  jnz     short loc_180003541
0x180003537  lea     rcx, [rsp+14F0h+var_14D0]
0x18000353c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003541  cmp     [rsp+14F0h+var_14C8], r15d
0x180003546  jge     loc_180003654
0x18000354c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180003553  jnz     short loc_180003574
0x180003555  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000355c  test    rax, rax
0x18000355f  jz      short loc_18000356A
0x180003561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003566  test    al, al
0x180003568  jmp     short loc_180003572
0x18000356a  call    cs:__imp_IsDebuggerPresent
0x180003570  test    eax, eax
0x180003572  jz      short loc_18000357B
0x180003574  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003579  jz      short loc_1800035A1
0x18000357b  mov     rax, cs:g_pfnResultLoggingCallback
0x180003582  test    rax, rax
0x180003585  jz      short loc_1800035FA
0x180003587  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000358e  jnz     short loc_1800035FA
0x180003590  xor     r8d, r8d
0x180003593  xor     edx, edx
0x180003595  lea     rcx, [rsp+14F0h+var_14D0]
0x18000359a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000359f  jmp     short loc_1800035FA
0x1800035a1  mov     ebx, 800h
0x1800035a6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800035ad  test    rax, rax
0x1800035b0  jz      short loc_1800035CF
0x1800035b2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800035b9  jnz     short loc_1800035CF
0x1800035bb  mov     r8d, ebx
0x1800035be  lea     rdx, [rbp+13F0h+OutputString]
0x1800035c5  lea     rcx, [rsp+14F0h+var_14D0]
0x1800035ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035cf  cmp     [rbp+13F0h+OutputString], r15w
0x1800035d7  jnz     short loc_1800035ED
0x1800035d9  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800035de  mov     rdx, rbx; unsigned __int16 *
0x1800035e1  lea     rcx, [rbp+13F0h+OutputString]; lpString
0x1800035e8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800035ed  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800035f4  call    cs:__imp_OutputDebugStringW
0x1800035fa  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800035ff  jnz     short loc_18000360A
0x180003601  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180003608  jz      short loc_18000361C
0x18000360a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003611  test    rax, rax
0x180003614  jz      short loc_18000361C
0x180003616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000361b  nop
0x18000361c  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180003621  jnz     short loc_180003649
0x180003623  mov     rcx, [rbp+13F0h+var_30]
0x18000362a  xor     rcx, rsp; StackCookie
0x18000362d  call    __security_check_cookie
0x180003632  mov     rbx, [rsp+14F0h+arg_10]
0x18000363a  add     rsp, 14D0h
0x180003641  pop     r15
0x180003643  pop     r14
0x180003645  pop     rdi
0x180003646  pop     rsi
0x180003647  pop     rbp
0x180003648  retn
0x180003649  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000364e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003654  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
