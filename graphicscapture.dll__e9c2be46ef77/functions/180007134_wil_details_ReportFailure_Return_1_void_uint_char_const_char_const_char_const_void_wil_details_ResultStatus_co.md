# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180007134`
- end: `0x1800073da`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180006c2c`

## callees

- `0x180001640`
- `0x180001f78`
- `0x180007134`
- `0x180008b54`
- `0x18000a88c`
- `0x18000c338`
- `0x18000c544`
- `0x180025330`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800071fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800071fa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007379`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007379`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800072ef`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800072ef`

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
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180007134  push    rbp
0x180007136  push    rbx
0x180007137  push    rsi
0x180007138  push    rdi
0x180007139  push    r12
0x18000713b  push    r14
0x18000713d  push    r15
0x18000713f  lea     rbp, [rsp-13D0h]
0x180007147  mov     eax, 14D0h
0x18000714c  call    _alloca_probe
0x180007151  sub     rsp, rax
0x180007154  mov     rax, cs:__security_cookie
0x18000715b  xor     rax, rsp
0x18000715e  mov     [rbp+1400h+var_40], rax
0x180007165  mov     rsi, r8
0x180007168  mov     edi, edx
0x18000716a  mov     rbx, rcx
0x18000716d  mov     r14, [rbp+1400h+arg_28]
0x180007174  xor     edx, edx; Val
0x180007176  mov     r8d, 98h; Size
0x18000717c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180007181  call    memset_0
0x180007186  nop
0x180007187  xor     r12d, r12d
0x18000718a  mov     [rbp+1400h+OutputString], r12w
0x180007192  mov     [rbp+1400h+var_1440], r12b
0x180007196  mov     rdx, [rbp+1400h+arg_30]; int
0x18000719d  mov     ecx, [rdx]; this
0x18000719f  mov     [rsp+1500h+var_14D8], ecx
0x1800071a3  mov     eax, [rdx+4]
0x1800071a6  mov     [rsp+1500h+var_14D4], eax
0x1800071aa  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800071af  mov     r15d, eax
0x1800071b2  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800071ba  mov     ecx, r12d
0x1800071bd  lea     eax, [r12+8]
0x1800071c2  cmp     dword ptr [rdx+8], 1
0x1800071c6  cmovz   ecx, eax
0x1800071c9  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800071cd  lea     ecx, [rax-7]
0x1800071d0  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800071d8  inc     ecx
0x1800071da  mov     [rsp+1500h+var_14D0], ecx
0x1800071de  mov     rcx, [rbp+1400h+arg_38]
0x1800071e5  test    rcx, rcx
0x1800071e8  jz      short loc_1800071F5
0x1800071ea  cmp     [rcx], r12w
0x1800071ee  mov     [rsp+1500h+var_14C8], rcx
0x1800071f3  jnz     short loc_1800071FA
0x1800071f5  mov     [rsp+1500h+var_14C8], r12
0x1800071fa  call    cs:__imp_GetCurrentThreadId
0x180007200  mov     [rsp+1500h+var_14C0], eax
0x180007204  mov     [rsp+1500h+var_14A8], rsi
0x180007209  mov     [rsp+1500h+var_14A0], edi
0x18000720d  mov     [rsp+1500h+var_149C], r15d
0x180007212  mov     [rsp+1500h+var_14B8], r12
0x180007217  mov     [rsp+1500h+var_14B0], r12
0x18000721c  mov     [rbp+1400h+var_1458], r14
0x180007220  mov     [rbp+1400h+var_1450], rbx
0x180007224  mov     [rsp+1500h+var_1498], r12
0x180007229  xorps   xmm0, xmm0
0x18000722c  xor     eax, eax
0x18000722e  movups  [rbp+1400h+var_1478], xmm0
0x180007232  mov     [rbp+1400h+var_1468], rax
0x180007236  xorps   xmm1, xmm1
0x180007239  movups  [rsp+1500h+var_1490], xmm1
0x18000723e  mov     [rbp+1400h+var_1480], rax
0x180007242  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007249  test    rax, rax
0x18000724c  jz      short loc_180007259
0x18000724e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007253  mov     [rbp+1400h+var_1460], rax
0x180007257  jmp     short loc_18000725D
0x180007259  mov     [rbp+1400h+var_1460], r12
0x18000725d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007264  test    rax, rax
0x180007267  jz      short loc_180007273
0x180007269  lea     rcx, [rsp+1500h+var_14E0]
0x18000726e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007273  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000727a  test    rax, rax
0x18000727d  jz      short loc_180007293
0x18000727f  mov     r8d, 400h
0x180007285  lea     rdx, [rbp+1400h+var_1440]
0x180007289  lea     rcx, [rsp+1500h+var_14E0]
0x18000728e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007293  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000729a  test    rax, rax
0x18000729d  jz      short loc_1800072A9
0x18000729f  lea     rcx, [rsp+1500h+var_14E0]
0x1800072a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072a9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800072b0  test    rax, rax
0x1800072b3  jz      short loc_1800072C6
0x1800072b5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800072ba  jnz     short loc_1800072C6
0x1800072bc  lea     rcx, [rsp+1500h+var_14E0]
0x1800072c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072c6  cmp     [rsp+1500h+var_14D8], r12d
0x1800072cb  jge     loc_1800073D4
0x1800072d1  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800072d8  jnz     short loc_1800072F9
0x1800072da  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800072e1  test    rax, rax
0x1800072e4  jz      short loc_1800072EF
0x1800072e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072eb  test    al, al
0x1800072ed  jmp     short loc_1800072F7
0x1800072ef  call    cs:__imp_IsDebuggerPresent
0x1800072f5  test    eax, eax
0x1800072f7  jz      short loc_180007300
0x1800072f9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800072fe  jz      short loc_180007326
0x180007300  mov     rax, cs:g_pfnResultLoggingCallback
0x180007307  test    rax, rax
0x18000730a  jz      short loc_18000737F
0x18000730c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180007313  jnz     short loc_18000737F
0x180007315  xor     r8d, r8d
0x180007318  xor     edx, edx
0x18000731a  lea     rcx, [rsp+1500h+var_14E0]
0x18000731f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007324  jmp     short loc_18000737F
0x180007326  mov     ebx, 800h
0x18000732b  mov     rax, cs:g_pfnResultLoggingCallback
0x180007332  test    rax, rax
0x180007335  jz      short loc_180007354
0x180007337  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000733e  jnz     short loc_180007354
0x180007340  mov     r8d, ebx
0x180007343  lea     rdx, [rbp+1400h+OutputString]
0x18000734a  lea     rcx, [rsp+1500h+var_14E0]
0x18000734f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007354  cmp     [rbp+1400h+OutputString], r12w
0x18000735c  jnz     short loc_180007372
0x18000735e  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180007363  mov     rdx, rbx; unsigned __int16 *
0x180007366  lea     rcx, [rbp+1400h+OutputString]; this
0x18000736d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007372  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180007379  call    cs:__imp_OutputDebugStringW
0x18000737f  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180007384  jnz     short loc_18000738F
0x180007386  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000738d  jz      short loc_1800073A1
0x18000738f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007396  test    rax, rax
0x180007399  jz      short loc_1800073A1
0x18000739b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073a0  nop
0x1800073a1  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800073a6  jnz     short loc_1800073C9
0x1800073a8  mov     rcx, [rbp+1400h+var_40]
0x1800073af  xor     rcx, rsp; StackCookie
0x1800073b2  call    __security_check_cookie
0x1800073b7  add     rsp, 14D0h
0x1800073be  pop     r15
0x1800073c0  pop     r14
0x1800073c2  pop     r12
0x1800073c4  pop     rdi
0x1800073c5  pop     rsi
0x1800073c6  pop     rbx
0x1800073c7  pop     rbp
0x1800073c8  retn
0x1800073c9  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800073ce  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800073d4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
