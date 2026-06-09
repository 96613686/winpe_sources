# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003780`
- end: `0x180003a78`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180002f70`

## callees

- `0x180001550`
- `0x180002158`
- `0x180003154`
- `0x180003780`
- `0x180004bd4`
- `0x18000537c`
- `0x180006364`
- `0x180006e90`
- `0x180006ffc`
- `0x18000eda0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003899`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003899`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003a15`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003a15`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000398c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000398c`

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
      g_pfnResultLoggingCallback(&v23, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v23, v20);
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
0x180003780  push    rbp
0x180003782  push    rbx
0x180003783  push    rsi
0x180003784  push    rdi
0x180003785  push    r12
0x180003787  push    r13
0x180003789  push    r14
0x18000378b  push    r15
0x18000378d  lea     rbp, [rsp-1408h]
0x180003795  mov     eax, 1508h
0x18000379a  call    _alloca_probe
0x18000379f  sub     rsp, rax
0x1800037a2  mov     rax, cs:__security_cookie
0x1800037a9  xor     rax, rsp
0x1800037ac  mov     [rbp+1440h+var_50], rax
0x1800037b3  mov     r12, r9
0x1800037b6  mov     r15, r8
0x1800037b9  mov     r14d, edx
0x1800037bc  mov     rsi, rcx
0x1800037bf  mov     r13, [rbp+1440h+arg_20]
0x1800037c6  mov     rax, [rbp+1440h+arg_28]
0x1800037cd  mov     [rsp+1540h+var_1500], rax
0x1800037d2  xor     edx, edx; Val
0x1800037d4  mov     r8d, 98h; Size
0x1800037da  lea     rcx, [rsp+1540h+var_14F0]; void *
0x1800037df  call    memset_0
0x1800037e4  nop
0x1800037e5  xor     eax, eax
0x1800037e7  mov     [rbp+1440h+OutputString], ax
0x1800037ee  mov     [rbp+1440h+var_1450], al
0x1800037f1  mov     rdi, [rbp+1440h+arg_30]
0x1800037f8  mov     ebx, [rdi]
0x1800037fa  mov     [rsp+1540h+var_14E8], ebx
0x1800037fe  mov     eax, [rdi+4]
0x180003801  mov     [rsp+1540h+var_14E4], eax
0x180003805  test    ebx, ebx
0x180003807  js      short loc_180003841
0x180003809  mov     ebx, 8007029Ch
0x18000380e  mov     dword ptr [rsp+1540h+var_1510], ebx; wil::details *
0x180003812  mov     rax, [rsp+1540h+var_1500]
0x180003817  mov     [rsp+1540h+var_1518], rax; __int64
0x18000381c  mov     [rsp+1540h+var_1520], r13; __int64
0x180003821  mov     r9, r12; int
0x180003824  mov     r8, r15; int
0x180003827  mov     edx, r14d; int
0x18000382a  mov     rcx, rsi; int
0x18000382d  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180003832  mov     [rsp+1540h+var_14E8], ebx
0x180003836  mov     ecx, ebx; this
0x180003838  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000383d  mov     [rsp+1540h+var_14E4], eax
0x180003841  mov     ecx, ebx; this
0x180003843  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180003848  mov     ebx, eax
0x18000384a  mov     dword ptr [rsp+1540h+var_14F0], 2
0x180003852  mov     ecx, [rbp+1440h+arg_48]
0x180003858  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x18000385c  cmp     dword ptr [rdi+8], 1
0x180003860  jnz     short loc_180003869
0x180003862  or      ecx, 8
0x180003865  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x180003869  mov     ecx, 1
0x18000386e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003876  inc     ecx
0x180003878  mov     [rsp+1540h+var_14E0], ecx
0x18000387c  mov     rax, [rbp+1440h+arg_38]
0x180003883  xor     edi, edi
0x180003885  test    rax, rax
0x180003888  jz      short loc_180003894
0x18000388a  cmp     [rax], di
0x18000388d  mov     [rsp+1540h+var_14D8], rax
0x180003892  jnz     short loc_180003899
0x180003894  mov     [rsp+1540h+var_14D8], rdi
0x180003899  call    cs:__imp_GetCurrentThreadId
0x18000389f  mov     [rsp+1540h+var_14D0], eax
0x1800038a3  mov     [rbp+1440h+var_14B8], r15
0x1800038a7  mov     [rbp+1440h+var_14B0], r14d
0x1800038ab  mov     [rbp+1440h+var_14AC], ebx
0x1800038ae  mov     [rsp+1540h+var_14C8], r13
0x1800038b3  mov     [rbp+1440h+var_14C0], r12
0x1800038b7  mov     rax, [rsp+1540h+var_1500]
0x1800038bc  mov     [rbp+1440h+var_1468], rax
0x1800038c0  mov     [rbp+1440h+var_1460], rsi
0x1800038c4  mov     [rbp+1440h+var_14A8], rdi
0x1800038c8  xorps   xmm0, xmm0
0x1800038cb  xor     eax, eax
0x1800038cd  movups  [rbp+1440h+var_1488], xmm0
0x1800038d1  mov     [rbp+1440h+var_1478], rax
0x1800038d5  xorps   xmm1, xmm1
0x1800038d8  movups  [rbp+1440h+var_14A0], xmm1
0x1800038dc  mov     [rbp+1440h+var_1490], rax
0x1800038e0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800038e7  test    rax, rax
0x1800038ea  jz      short loc_1800038F7
0x1800038ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038f1  mov     [rbp+1440h+var_1470], rax
0x1800038f5  jmp     short loc_1800038FB
0x1800038f7  mov     [rbp+1440h+var_1470], rdi
0x1800038fb  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003902  test    rax, rax
0x180003905  jz      short loc_180003911
0x180003907  lea     rcx, [rsp+1540h+var_14F0]
0x18000390c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003911  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003918  test    rax, rax
0x18000391b  jz      short loc_180003931
0x18000391d  mov     r8d, 400h
0x180003923  lea     rdx, [rbp+1440h+var_1450]
0x180003927  lea     rcx, [rsp+1540h+var_14F0]
0x18000392c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003931  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003938  test    rax, rax
0x18000393b  jz      short loc_180003947
0x18000393d  lea     rcx, [rsp+1540h+var_14F0]
0x180003942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003947  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000394e  test    rax, rax
0x180003951  jz      short loc_180003964
0x180003953  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x180003958  jnz     short loc_180003964
0x18000395a  lea     rcx, [rsp+1540h+var_14F0]
0x18000395f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003964  cmp     [rsp+1540h+var_14E8], edi
0x180003968  jge     loc_180003A72
0x18000396e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180003975  jnz     short loc_180003996
0x180003977  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000397e  test    rax, rax
0x180003981  jz      short loc_18000398C
0x180003983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003988  test    al, al
0x18000398a  jmp     short loc_180003994
0x18000398c  call    cs:__imp_IsDebuggerPresent
0x180003992  test    eax, eax
0x180003994  jz      short loc_18000399D
0x180003996  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x18000399b  jz      short loc_1800039C3
0x18000399d  mov     rax, cs:g_pfnResultLoggingCallback
0x1800039a4  test    rax, rax
0x1800039a7  jz      short loc_180003A1B
0x1800039a9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800039b0  jnz     short loc_180003A1B
0x1800039b2  xor     r8d, r8d
0x1800039b5  xor     edx, edx
0x1800039b7  lea     rcx, [rsp+1540h+var_14F0]
0x1800039bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039c1  jmp     short loc_180003A1B
0x1800039c3  mov     ebx, 800h
0x1800039c8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800039cf  test    rax, rax
0x1800039d2  jz      short loc_1800039F1
0x1800039d4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800039db  jnz     short loc_1800039F1
0x1800039dd  mov     r8d, ebx
0x1800039e0  lea     rdx, [rbp+1440h+OutputString]
0x1800039e7  lea     rcx, [rsp+1540h+var_14F0]
0x1800039ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039f1  cmp     [rbp+1440h+OutputString], di
0x1800039f8  jnz     short loc_180003A0E
0x1800039fa  lea     r8, [rsp+1540h+var_14F0]; unsigned __int64
0x1800039ff  mov     rdx, rbx; unsigned __int16 *
0x180003a02  lea     rcx, [rbp+1440h+OutputString]; this
0x180003a09  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003a0e  lea     rcx, [rbp+1440h+OutputString]; lpOutputString
0x180003a15  call    cs:__imp_OutputDebugStringW
0x180003a1b  test    byte ptr [rsp+1540h+var_14F0+4], 4
0x180003a20  jnz     short loc_180003A2B
0x180003a22  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180003a29  jz      short loc_180003A3D
0x180003a2b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003a32  test    rax, rax
0x180003a35  jz      short loc_180003A3D
0x180003a37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a3c  nop
0x180003a3d  test    byte ptr [rsp+1540h+var_14F0+4], 1
0x180003a42  jnz     short loc_180003A67
0x180003a44  mov     rcx, [rbp+1440h+var_50]
0x180003a4b  xor     rcx, rsp; StackCookie
0x180003a4e  call    __security_check_cookie
0x180003a53  add     rsp, 1508h
0x180003a5a  pop     r15
0x180003a5c  pop     r14
0x180003a5e  pop     r13
0x180003a60  pop     r12
0x180003a62  pop     rdi
0x180003a63  pop     rsi
0x180003a64  pop     rbx
0x180003a65  pop     rbp
0x180003a66  retn
0x180003a67  lea     rcx, [rsp+1540h+var_14F0]; this
0x180003a6c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003a72  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
