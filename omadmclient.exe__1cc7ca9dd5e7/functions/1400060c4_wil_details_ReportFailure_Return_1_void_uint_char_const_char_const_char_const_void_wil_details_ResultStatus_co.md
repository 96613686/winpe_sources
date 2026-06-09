# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1400060c4`
- end: `0x14000637d`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140005b3c`

## callees

- `0x140003450`
- `0x140003eb4`
- `0x1400060c4`
- `0x14000866c`
- `0x14000a068`
- `0x14000cbdc`
- `0x14000ce6c`
- `0x140065e80`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000618a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000618a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140006285`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140006285`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006315`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006315`

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
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x1400060c4  push    rbp
0x1400060c6  push    rbx
0x1400060c7  push    rsi
0x1400060c8  push    rdi
0x1400060c9  push    r12
0x1400060cb  push    r14
0x1400060cd  push    r15
0x1400060cf  lea     rbp, [rsp-13D0h]
0x1400060d7  mov     eax, 14D0h
0x1400060dc  call    _alloca_probe
0x1400060e1  sub     rsp, rax
0x1400060e4  mov     rax, cs:__security_cookie
0x1400060eb  xor     rax, rsp
0x1400060ee  mov     [rbp+1400h+var_40], rax
0x1400060f5  mov     rsi, r8
0x1400060f8  mov     edi, edx
0x1400060fa  mov     rbx, rcx
0x1400060fd  mov     r14, [rbp+1400h+arg_28]
0x140006104  xor     edx, edx; Val
0x140006106  mov     r8d, 98h; Size
0x14000610c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140006111  call    memset_0
0x140006116  nop
0x140006117  xor     r12d, r12d
0x14000611a  mov     [rbp+1400h+OutputString], r12w
0x140006122  mov     [rbp+1400h+var_1440], r12b
0x140006126  mov     rdx, [rbp+1400h+arg_30]; int
0x14000612d  mov     ecx, [rdx]; this
0x14000612f  mov     [rsp+1500h+var_14D8], ecx
0x140006133  mov     eax, [rdx+4]
0x140006136  mov     [rsp+1500h+var_14D4], eax
0x14000613a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000613f  mov     r15d, eax
0x140006142  mov     dword ptr [rsp+1500h+var_14E0], 1
0x14000614a  mov     ecx, r12d
0x14000614d  lea     eax, [r12+8]
0x140006152  cmp     dword ptr [rdx+8], 1
0x140006156  cmovz   ecx, eax
0x140006159  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x14000615d  lea     ecx, [rax-7]
0x140006160  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140006168  inc     ecx
0x14000616a  mov     [rsp+1500h+var_14D0], ecx
0x14000616e  mov     rcx, [rbp+1400h+arg_38]
0x140006175  test    rcx, rcx
0x140006178  jz      short loc_140006185
0x14000617a  cmp     [rcx], r12w
0x14000617e  mov     [rsp+1500h+var_14C8], rcx
0x140006183  jnz     short loc_14000618A
0x140006185  mov     [rsp+1500h+var_14C8], r12
0x14000618a  call    cs:__imp_GetCurrentThreadId
0x140006191  nop     dword ptr [rax+rax+00h]
0x140006196  mov     [rsp+1500h+var_14C0], eax
0x14000619a  mov     [rsp+1500h+var_14A8], rsi
0x14000619f  mov     [rsp+1500h+var_14A0], edi
0x1400061a3  mov     [rsp+1500h+var_149C], r15d
0x1400061a8  mov     [rsp+1500h+var_14B8], r12
0x1400061ad  mov     [rsp+1500h+var_14B0], r12
0x1400061b2  mov     [rbp+1400h+var_1458], r14
0x1400061b6  mov     [rbp+1400h+var_1450], rbx
0x1400061ba  mov     [rsp+1500h+var_1498], r12
0x1400061bf  xorps   xmm0, xmm0
0x1400061c2  xor     eax, eax
0x1400061c4  movups  [rbp+1400h+var_1478], xmm0
0x1400061c8  mov     [rbp+1400h+var_1468], rax
0x1400061cc  xorps   xmm1, xmm1
0x1400061cf  movups  [rsp+1500h+var_1490], xmm1
0x1400061d4  mov     [rbp+1400h+var_1480], rax
0x1400061d8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400061df  test    rax, rax
0x1400061e2  jz      short loc_1400061EF
0x1400061e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400061e9  mov     [rbp+1400h+var_1460], rax
0x1400061ed  jmp     short loc_1400061F3
0x1400061ef  mov     [rbp+1400h+var_1460], r12
0x1400061f3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400061fa  test    rax, rax
0x1400061fd  jz      short loc_140006209
0x1400061ff  lea     rcx, [rsp+1500h+var_14E0]
0x140006204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006209  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140006210  test    rax, rax
0x140006213  jz      short loc_140006229
0x140006215  mov     r8d, 400h
0x14000621b  lea     rdx, [rbp+1400h+var_1440]
0x14000621f  lea     rcx, [rsp+1500h+var_14E0]
0x140006224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006229  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006230  test    rax, rax
0x140006233  jz      short loc_14000623F
0x140006235  lea     rcx, [rsp+1500h+var_14E0]
0x14000623a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000623f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006246  test    rax, rax
0x140006249  jz      short loc_14000625C
0x14000624b  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140006250  jnz     short loc_14000625C
0x140006252  lea     rcx, [rsp+1500h+var_14E0]
0x140006257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000625c  cmp     [rsp+1500h+var_14D8], r12d
0x140006261  jge     loc_140006377
0x140006267  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x14000626e  jnz     short loc_140006295
0x140006270  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140006277  test    rax, rax
0x14000627a  jz      short loc_140006285
0x14000627c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006281  test    al, al
0x140006283  jmp     short loc_140006293
0x140006285  call    cs:__imp_IsDebuggerPresent
0x14000628c  nop     dword ptr [rax+rax+00h]
0x140006291  test    eax, eax
0x140006293  jz      short loc_14000629C
0x140006295  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x14000629a  jz      short loc_1400062C2
0x14000629c  mov     rax, cs:g_pfnResultLoggingCallback
0x1400062a3  test    rax, rax
0x1400062a6  jz      short loc_140006321
0x1400062a8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1400062af  jnz     short loc_140006321
0x1400062b1  xor     r8d, r8d
0x1400062b4  xor     edx, edx
0x1400062b6  lea     rcx, [rsp+1500h+var_14E0]
0x1400062bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400062c0  jmp     short loc_140006321
0x1400062c2  mov     ebx, 800h
0x1400062c7  mov     rax, cs:g_pfnResultLoggingCallback
0x1400062ce  test    rax, rax
0x1400062d1  jz      short loc_1400062F0
0x1400062d3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1400062da  jnz     short loc_1400062F0
0x1400062dc  mov     r8d, ebx
0x1400062df  lea     rdx, [rbp+1400h+OutputString]
0x1400062e6  lea     rcx, [rsp+1500h+var_14E0]
0x1400062eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400062f0  cmp     [rbp+1400h+OutputString], r12w
0x1400062f8  jnz     short loc_14000630E
0x1400062fa  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1400062ff  mov     rdx, rbx; unsigned __int16 *
0x140006302  lea     rcx, [rbp+1400h+OutputString]; this
0x140006309  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000630e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140006315  call    cs:__imp_OutputDebugStringW
0x14000631c  nop     dword ptr [rax+rax+00h]
0x140006321  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x140006326  jnz     short loc_140006331
0x140006328  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x14000632f  jz      short loc_140006343
0x140006331  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140006338  test    rax, rax
0x14000633b  jz      short loc_140006343
0x14000633d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006342  nop
0x140006343  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140006348  jnz     short loc_14000636C
0x14000634a  mov     rcx, [rbp+1400h+var_40]
0x140006351  xor     rcx, rsp; StackCookie
0x140006354  call    __security_check_cookie
0x140006359  add     rsp, 14D0h
0x140006360  pop     r15
0x140006362  pop     r14
0x140006364  pop     r12
0x140006366  pop     rdi
0x140006367  pop     rsi
0x140006368  pop     rbx
0x140006369  pop     rbp
0x14000636a  retn
0x14000636c  lea     rcx, [rsp+1500h+var_14E0]; this
0x140006371  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140006377  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
