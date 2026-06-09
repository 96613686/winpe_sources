# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800092a4`
- end: `0x1800095a4`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `768`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180008728`

## callees

- `0x1800067c0`
- `0x180007438`
- `0x1800089e4`
- `0x1800092a4`
- `0x18000c36c`
- `0x18000cea0`
- `0x18000df50`
- `0x180011320`
- `0x1800115b4`
- `0x180099a90`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800093c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800093c5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009541`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009541`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800094b8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800094b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<2>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8,
        int a9,
        int a10)
{
  int v14; // edx
  int v15; // ebx
  int v16; // edx
  int v17; // ebx
  const struct wil::FailureInfo *v18; // rdx
  wil::details::in1diag3 *v19; // rcx
  const struct wil::FailureInfo *v20; // r9
  bool v21; // zf
  wil::details *v22; // [rsp+30h] [rbp-D0h]
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+54h] [rbp-ACh]
  int v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+5Ch] [rbp-A4h]
  signed __int32 v27; // [rsp+60h] [rbp-A0h]
  _WORD *v28; // [rsp+68h] [rbp-98h]
  DWORD CurrentThreadId; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+78h] [rbp-88h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int64 v32; // [rsp+88h] [rbp-78h]
  int v33; // [rsp+90h] [rbp-70h]
  int v34; // [rsp+94h] [rbp-6Ch]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int128 v36; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  __int128 v38; // [rsp+B8h] [rbp-48h]
  __int64 v39; // [rsp+C8h] [rbp-38h]
  __int64 ModuleName; // [rsp+D0h] [rbp-30h]
  __int64 v41; // [rsp+D8h] [rbp-28h]
  __int64 v42; // [rsp+E0h] [rbp-20h]
  char v43[1024]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR OutputString[2048]; // [rsp+4F0h] [rbp+3F0h] BYREF

  memset_0(&v23, 0, 0x98u);
  OutputString[0] = 0;
  v43[0] = 0;
  v15 = *a7;
  v25 = v15;
  v26 = a7[1];
  if ( v15 >= 0 )
  {
    v15 = -2147024228;
    LODWORD(v22) = -2147024228;
    wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v22);
    v25 = -2147024228;
    v26 = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v16);
  }
  v17 = wil::details::RecordLog((wil::details *)(unsigned int)v15, v14);
  v23 = 2;
  v24 = a10;
  if ( a7[2] == 1 )
    v24 = a10 | 8;
  v27 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v21 = *a8 == 0, v28 = a8, v21) )
    v28 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v32 = a3;
  v33 = a2;
  v34 = v17;
  v30 = a5;
  v31 = a4;
  v41 = a6;
  v42 = a1;
  v35 = 0;
  v38 = 0;
  v39 = 0;
  v36 = 0;
  v37 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v23);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v23, v43, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v23);
  if ( wil::details::g_pfnOriginateCallback && (v24 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v23);
  if ( v25 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v19);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v21 = !IsDebuggerPresent())
      : (v21 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v21)
    || (v24 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, 0, 0, v20);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, OutputString, 2048, v20);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v23, v20);
    OutputDebugStringW(OutputString);
  }
  if ( ((v24 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak();
  if ( (v24 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v23, v18);
}

```

## disassembly

```asm
0x1800092a4  push    rbp
0x1800092a6  push    rbx
0x1800092a7  push    rsi
0x1800092a8  push    rdi
0x1800092a9  push    r12
0x1800092ab  push    r13
0x1800092ad  push    r14
0x1800092af  push    r15
0x1800092b1  lea     rbp, [rsp-1408h]
0x1800092b9  mov     eax, 1508h
0x1800092be  call    _alloca_probe
0x1800092c3  sub     rsp, rax
0x1800092c6  mov     rax, cs:__security_cookie
0x1800092cd  xor     rax, rsp
0x1800092d0  mov     [rbp+1440h+var_50], rax
0x1800092d7  mov     r12, r9
0x1800092da  mov     r15, r8
0x1800092dd  mov     r14d, edx
0x1800092e0  mov     rsi, rcx
0x1800092e3  mov     r13, [rbp+1440h+arg_20]
0x1800092ea  mov     rax, [rbp+1440h+arg_28]
0x1800092f1  mov     [rsp+1540h+var_1500], rax
0x1800092f6  xor     edx, edx; Val
0x1800092f8  mov     r8d, 98h; Size
0x1800092fe  lea     rcx, [rsp+1540h+var_14F0]; void *
0x180009303  call    memset_0
0x180009308  nop
0x180009309  xor     eax, eax
0x18000930b  mov     [rbp+1440h+OutputString], ax
0x180009312  mov     [rbp+1440h+var_1450], al
0x180009315  mov     rdi, [rbp+1440h+arg_30]
0x18000931c  mov     ebx, [rdi]
0x18000931e  mov     [rsp+1540h+var_14E8], ebx
0x180009322  mov     eax, [rdi+4]
0x180009325  mov     [rsp+1540h+var_14E4], eax
0x180009329  test    ebx, ebx
0x18000932b  js      short loc_18000936D
0x18000932d  mov     [rsp+1540h+var_1508], 0
0x180009335  mov     ebx, 8007029Ch
0x18000933a  mov     dword ptr [rsp+1540h+var_1510], ebx; wil::details *
0x18000933e  mov     rax, [rsp+1540h+var_1500]
0x180009343  mov     [rsp+1540h+var_1518], rax; __int64
0x180009348  mov     [rsp+1540h+var_1520], r13; __int64
0x18000934d  mov     r9, r12; int
0x180009350  mov     r8, r15; int
0x180009353  mov     edx, r14d; int
0x180009356  mov     rcx, rsi; int
0x180009359  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000935e  mov     [rsp+1540h+var_14E8], ebx
0x180009362  mov     ecx, ebx; this
0x180009364  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009369  mov     [rsp+1540h+var_14E4], eax
0x18000936d  mov     ecx, ebx; this
0x18000936f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180009374  mov     ebx, eax
0x180009376  mov     dword ptr [rsp+1540h+var_14F0], 2
0x18000937e  mov     ecx, [rbp+1440h+arg_48]
0x180009384  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x180009388  cmp     dword ptr [rdi+8], 1
0x18000938c  jnz     short loc_180009395
0x18000938e  or      ecx, 8
0x180009391  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x180009395  mov     ecx, 1
0x18000939a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800093a2  inc     ecx
0x1800093a4  mov     [rsp+1540h+var_14E0], ecx
0x1800093a8  mov     rax, [rbp+1440h+arg_38]
0x1800093af  xor     edi, edi
0x1800093b1  test    rax, rax
0x1800093b4  jz      short loc_1800093C0
0x1800093b6  cmp     [rax], di
0x1800093b9  mov     [rsp+1540h+var_14D8], rax
0x1800093be  jnz     short loc_1800093C5
0x1800093c0  mov     [rsp+1540h+var_14D8], rdi
0x1800093c5  call    cs:__imp_GetCurrentThreadId
0x1800093cb  mov     [rsp+1540h+var_14D0], eax
0x1800093cf  mov     [rbp+1440h+var_14B8], r15
0x1800093d3  mov     [rbp+1440h+var_14B0], r14d
0x1800093d7  mov     [rbp+1440h+var_14AC], ebx
0x1800093da  mov     [rsp+1540h+var_14C8], r13
0x1800093df  mov     [rbp+1440h+var_14C0], r12
0x1800093e3  mov     rax, [rsp+1540h+var_1500]
0x1800093e8  mov     [rbp+1440h+var_1468], rax
0x1800093ec  mov     [rbp+1440h+var_1460], rsi
0x1800093f0  mov     [rbp+1440h+var_14A8], rdi
0x1800093f4  xorps   xmm0, xmm0
0x1800093f7  xor     eax, eax
0x1800093f9  movups  [rbp+1440h+var_1488], xmm0
0x1800093fd  mov     [rbp+1440h+var_1478], rax
0x180009401  xorps   xmm1, xmm1
0x180009404  movups  [rbp+1440h+var_14A0], xmm1
0x180009408  mov     [rbp+1440h+var_1490], rax
0x18000940c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180009413  test    rax, rax
0x180009416  jz      short loc_180009423
0x180009418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000941d  mov     [rbp+1440h+var_1470], rax
0x180009421  jmp     short loc_180009427
0x180009423  mov     [rbp+1440h+var_1470], rdi
0x180009427  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000942e  test    rax, rax
0x180009431  jz      short loc_18000943D
0x180009433  lea     rcx, [rsp+1540h+var_14F0]
0x180009438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000943d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009444  test    rax, rax
0x180009447  jz      short loc_18000945D
0x180009449  mov     r8d, 400h
0x18000944f  lea     rdx, [rbp+1440h+var_1450]
0x180009453  lea     rcx, [rsp+1540h+var_14F0]
0x180009458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000945d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009464  test    rax, rax
0x180009467  jz      short loc_180009473
0x180009469  lea     rcx, [rsp+1540h+var_14F0]
0x18000946e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009473  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000947a  test    rax, rax
0x18000947d  jz      short loc_180009490
0x18000947f  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x180009484  jnz     short loc_180009490
0x180009486  lea     rcx, [rsp+1540h+var_14F0]
0x18000948b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009490  cmp     [rsp+1540h+var_14E8], edi
0x180009494  jge     loc_18000959E
0x18000949a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800094a1  jnz     short loc_1800094C2
0x1800094a3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800094aa  test    rax, rax
0x1800094ad  jz      short loc_1800094B8
0x1800094af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094b4  test    al, al
0x1800094b6  jmp     short loc_1800094C0
0x1800094b8  call    cs:__imp_IsDebuggerPresent
0x1800094be  test    eax, eax
0x1800094c0  jz      short loc_1800094C9
0x1800094c2  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x1800094c7  jz      short loc_1800094EF
0x1800094c9  mov     rax, cs:g_pfnResultLoggingCallback
0x1800094d0  test    rax, rax
0x1800094d3  jz      short loc_180009547
0x1800094d5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800094dc  jnz     short loc_180009547
0x1800094de  xor     r8d, r8d
0x1800094e1  xor     edx, edx
0x1800094e3  lea     rcx, [rsp+1540h+var_14F0]
0x1800094e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094ed  jmp     short loc_180009547
0x1800094ef  mov     ebx, 800h
0x1800094f4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800094fb  test    rax, rax
0x1800094fe  jz      short loc_18000951D
0x180009500  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180009507  jnz     short loc_18000951D
0x180009509  mov     r8d, ebx
0x18000950c  lea     rdx, [rbp+1440h+OutputString]
0x180009513  lea     rcx, [rsp+1540h+var_14F0]
0x180009518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000951d  cmp     [rbp+1440h+OutputString], di
0x180009524  jnz     short loc_18000953A
0x180009526  lea     r8, [rsp+1540h+var_14F0]; unsigned __int64
0x18000952b  mov     rdx, rbx; unsigned __int16 *
0x18000952e  lea     rcx, [rbp+1440h+OutputString]; this
0x180009535  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000953a  lea     rcx, [rbp+1440h+OutputString]; lpOutputString
0x180009541  call    cs:__imp_OutputDebugStringW
0x180009547  test    byte ptr [rsp+1540h+var_14F0+4], 4
0x18000954c  jnz     short loc_180009557
0x18000954e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180009555  jz      short loc_180009569
0x180009557  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000955e  test    rax, rax
0x180009561  jz      short loc_180009569
0x180009563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009568  nop
0x180009569  test    byte ptr [rsp+1540h+var_14F0+4], 1
0x18000956e  jnz     short loc_180009593
0x180009570  mov     rcx, [rbp+1440h+var_50]
0x180009577  xor     rcx, rsp; StackCookie
0x18000957a  call    __security_check_cookie
0x18000957f  add     rsp, 1508h
0x180009586  pop     r15
0x180009588  pop     r14
0x18000958a  pop     r13
0x18000958c  pop     r12
0x18000958e  pop     rdi
0x18000958f  pop     rsi
0x180009590  pop     rbx
0x180009591  pop     rbp
0x180009592  retn
0x180009593  lea     rcx, [rsp+1540h+var_14F0]; this
0x180009598  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000959e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
