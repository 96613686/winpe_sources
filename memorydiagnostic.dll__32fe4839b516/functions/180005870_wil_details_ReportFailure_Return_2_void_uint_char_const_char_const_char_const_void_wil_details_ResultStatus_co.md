# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180005870`
- end: `0x180005b6f`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `767`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1800047d0`

## callees

- `0x1800026b0`
- `0x180003374`
- `0x180004e1c`
- `0x180005870`
- `0x18000d474`
- `0x18000dd50`
- `0x18000fcd0`
- `0x180015bec`
- `0x1800162d8`
- `0x180021f90`
- `0x180024010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180005a79`
- `KERNEL32!IsDebuggerPresent` at `0x180005a79`
- `KERNEL32!OutputDebugStringW` at `0x180005b06`
- `KERNEL32!OutputDebugStringW` at `0x180005b06`
- `KERNEL32!GetCurrentThreadId` at `0x180005983`
- `KERNEL32!GetCurrentThreadId` at `0x180005983`

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
        _WORD *a8)
{
  int v12; // edx
  int v13; // ebx
  int v14; // edx
  int v15; // ebx
  _WORD *v16; // r8
  int v17; // ecx
  const struct wil::FailureInfo *v18; // rdx
  wil::details::in1diag3 *v19; // rcx
  const struct wil::FailureInfo *v20; // r9
  bool v21; // zf
  wil::details *v22; // [rsp+30h] [rbp-D0h]
  int v23; // [rsp+40h] [rbp-C0h] BYREF
  int v24; // [rsp+44h] [rbp-BCh]
  int v25; // [rsp+48h] [rbp-B8h]
  int v26; // [rsp+4Ch] [rbp-B4h]
  signed __int32 v27; // [rsp+50h] [rbp-B0h]
  _WORD *v28; // [rsp+58h] [rbp-A8h]
  DWORD CurrentThreadId; // [rsp+60h] [rbp-A0h]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int64 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+78h] [rbp-88h]
  int v33; // [rsp+80h] [rbp-80h]
  int v34; // [rsp+84h] [rbp-7Ch]
  __int64 v35; // [rsp+88h] [rbp-78h]
  __int128 v36; // [rsp+90h] [rbp-70h]
  __int64 v37; // [rsp+A0h] [rbp-60h]
  __int128 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B8h] [rbp-48h]
  __int64 ModuleName; // [rsp+C0h] [rbp-40h]
  __int64 v41; // [rsp+C8h] [rbp-38h]
  __int64 v42; // [rsp+D0h] [rbp-30h]
  char v43[1024]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR OutputString[2048]; // [rsp+4E0h] [rbp+3E0h] BYREF

  memset_0(&v23, 0, 0x98u);
  OutputString[0] = 0;
  v43[0] = 0;
  v13 = *a7;
  v25 = v13;
  v26 = a7[1];
  if ( v13 >= 0 )
  {
    v13 = -2147024228;
    LODWORD(v22) = -2147024228;
    wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v22);
    v25 = -2147024228;
    v26 = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v14);
  }
  v15 = wil::details::RecordLog((wil::details *)(unsigned int)v13, v12);
  v23 = 2;
  v17 = (int)v16;
  if ( a7[2] == 1 )
    v17 = 8;
  v24 = v17;
  v27 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v21 = *a8 == (unsigned __int16)v16, v28 = a8, v21) )
    v28 = v16;
  CurrentThreadId = GetCurrentThreadId();
  v32 = a3;
  v33 = a2;
  v34 = v15;
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
0x180005870  push    rbp
0x180005872  push    rbx
0x180005873  push    rsi
0x180005874  push    rdi
0x180005875  push    r12
0x180005877  push    r13
0x180005879  push    r14
0x18000587b  push    r15
0x18000587d  lea     rbp, [rsp-13F8h]
0x180005885  mov     eax, 14F8h
0x18000588a  call    _alloca_probe
0x18000588f  sub     rsp, rax
0x180005892  mov     rax, cs:__security_cookie
0x180005899  xor     rax, rsp
0x18000589c  mov     [rbp+1430h+var_50], rax
0x1800058a3  mov     r15, r9
0x1800058a6  mov     r14, r8
0x1800058a9  mov     esi, edx
0x1800058ab  mov     rdi, rcx
0x1800058ae  mov     r12, [rbp+1430h+arg_20]
0x1800058b5  mov     r13, [rbp+1430h+arg_28]
0x1800058bc  xor     edx, edx; Val
0x1800058be  mov     r8d, 98h; Size
0x1800058c4  lea     rcx, [rsp+1530h+var_14F0]; void *
0x1800058c9  call    memset_0
0x1800058ce  nop
0x1800058cf  xor     r8d, r8d
0x1800058d2  mov     [rbp+1430h+OutputString], r8w
0x1800058da  mov     [rbp+1430h+var_1450], r8b
0x1800058de  mov     rax, [rbp+1430h+arg_30]
0x1800058e5  mov     ebx, [rax]
0x1800058e7  mov     [rsp+1530h+var_14E8], ebx
0x1800058eb  mov     eax, [rax+4]
0x1800058ee  mov     [rsp+1530h+var_14E4], eax
0x1800058f2  test    ebx, ebx
0x1800058f4  js      short loc_18000592B
0x1800058f6  mov     ebx, 8007029Ch
0x1800058fb  mov     dword ptr [rsp+1530h+var_1500], ebx; wil::details *
0x1800058ff  mov     [rsp+1530h+var_1508], r13; __int64
0x180005904  mov     [rsp+1530h+var_1510], r12; __int64
0x180005909  mov     r9, r15; int
0x18000590c  mov     r8, r14; int
0x18000590f  mov     edx, esi; int
0x180005911  mov     rcx, rdi; int
0x180005914  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long)
0x180005919  mov     [rsp+1530h+var_14E8], ebx
0x18000591d  mov     ecx, ebx; this
0x18000591f  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005924  mov     [rsp+1530h+var_14E4], eax
0x180005928  xor     r8d, r8d
0x18000592b  mov     ecx, ebx; this
0x18000592d  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005932  mov     ebx, eax
0x180005934  mov     dword ptr [rsp+1530h+var_14F0], 2
0x18000593c  mov     ecx, r8d
0x18000593f  mov     eax, 8
0x180005944  mov     rdx, [rbp+1430h+arg_30]
0x18000594b  cmp     dword ptr [rdx+8], 1
0x18000594f  cmovz   ecx, eax
0x180005952  mov     dword ptr [rsp+1530h+var_14F0+4], ecx
0x180005956  lea     ecx, [rax-7]
0x180005959  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x180005961  inc     ecx
0x180005963  mov     [rsp+1530h+var_14E0], ecx
0x180005967  mov     rcx, [rbp+1430h+arg_38]
0x18000596e  test    rcx, rcx
0x180005971  jz      short loc_18000597E
0x180005973  cmp     [rcx], r8w
0x180005977  mov     [rsp+1530h+var_14D8], rcx
0x18000597c  jnz     short loc_180005983
0x18000597e  mov     [rsp+1530h+var_14D8], r8
0x180005983  call    cs:__imp_GetCurrentThreadId
0x18000598a  nop     dword ptr [rax+rax+00h]
0x18000598f  mov     [rsp+1530h+var_14D0], eax
0x180005993  mov     [rsp+1530h+var_14B8], r14
0x180005998  mov     [rbp+1430h+var_14B0], esi
0x18000599b  mov     [rbp+1430h+var_14AC], ebx
0x18000599e  mov     [rsp+1530h+var_14C8], r12
0x1800059a3  mov     [rsp+1530h+var_14C0], r15
0x1800059a8  mov     [rbp+1430h+var_1468], r13
0x1800059ac  mov     [rbp+1430h+var_1460], rdi
0x1800059b0  xor     ebx, ebx
0x1800059b2  mov     [rbp+1430h+var_14A8], rbx
0x1800059b6  xorps   xmm0, xmm0
0x1800059b9  xor     eax, eax
0x1800059bb  movups  [rbp+1430h+var_1488], xmm0
0x1800059bf  mov     [rbp+1430h+var_1478], rax
0x1800059c3  xorps   xmm1, xmm1
0x1800059c6  movups  [rbp+1430h+var_14A0], xmm1
0x1800059ca  mov     [rbp+1430h+var_1490], rax
0x1800059ce  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800059d5  test    rax, rax
0x1800059d8  jz      short loc_1800059E5
0x1800059da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059df  mov     [rbp+1430h+var_1470], rax
0x1800059e3  jmp     short loc_1800059E9
0x1800059e5  mov     [rbp+1430h+var_1470], rbx
0x1800059e9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800059f0  test    rax, rax
0x1800059f3  jz      short loc_1800059FF
0x1800059f5  lea     rcx, [rsp+1530h+var_14F0]
0x1800059fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059ff  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005a06  test    rax, rax
0x180005a09  jz      short loc_180005A1F
0x180005a0b  mov     r8d, 400h
0x180005a11  lea     rdx, [rbp+1430h+var_1450]
0x180005a15  lea     rcx, [rsp+1530h+var_14F0]
0x180005a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a1f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005a26  test    rax, rax
0x180005a29  jz      short loc_180005A35
0x180005a2b  lea     rcx, [rsp+1530h+var_14F0]
0x180005a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a35  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005a3c  test    rax, rax
0x180005a3f  jz      short loc_180005A52
0x180005a41  test    byte ptr [rsp+1530h+var_14F0+4], 2
0x180005a46  jnz     short loc_180005A52
0x180005a48  lea     rcx, [rsp+1530h+var_14F0]
0x180005a4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a52  cmp     [rsp+1530h+var_14E8], ebx
0x180005a56  jge     loc_180005B69
0x180005a5c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, bl; bool wil::g_fIsDebuggerPresent
0x180005a62  jnz     short loc_180005A89
0x180005a64  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005a6b  test    rax, rax
0x180005a6e  jz      short loc_180005A79
0x180005a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a75  test    al, al
0x180005a77  jmp     short loc_180005A87
0x180005a79  call    cs:__imp_IsDebuggerPresent
0x180005a80  nop     dword ptr [rax+rax+00h]
0x180005a85  test    eax, eax
0x180005a87  jz      short loc_180005A90
0x180005a89  test    byte ptr [rsp+1530h+var_14F0+4], 2
0x180005a8e  jz      short loc_180005AB5
0x180005a90  mov     rax, cs:g_pfnResultLoggingCallback
0x180005a97  test    rax, rax
0x180005a9a  jz      short loc_180005B12
0x180005a9c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, bl; bool wil::details::g_resultMessageCallbackSet
0x180005aa2  jnz     short loc_180005B12
0x180005aa4  xor     r8d, r8d
0x180005aa7  xor     edx, edx
0x180005aa9  lea     rcx, [rsp+1530h+var_14F0]
0x180005aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ab3  jmp     short loc_180005B12
0x180005ab5  mov     edi, 800h
0x180005aba  mov     rax, cs:g_pfnResultLoggingCallback
0x180005ac1  test    rax, rax
0x180005ac4  jz      short loc_180005AE2
0x180005ac6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, bl; bool wil::details::g_resultMessageCallbackSet
0x180005acc  jnz     short loc_180005AE2
0x180005ace  mov     r8d, edi
0x180005ad1  lea     rdx, [rbp+1430h+OutputString]
0x180005ad8  lea     rcx, [rsp+1530h+var_14F0]
0x180005add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ae2  cmp     [rbp+1430h+OutputString], bx
0x180005ae9  jnz     short loc_180005AFF
0x180005aeb  lea     r8, [rsp+1530h+var_14F0]; unsigned __int64
0x180005af0  mov     rdx, rdi; unsigned __int16 *
0x180005af3  lea     rcx, [rbp+1430h+OutputString]; this
0x180005afa  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005aff  lea     rcx, [rbp+1430h+OutputString]; lpOutputString
0x180005b06  call    cs:__imp_OutputDebugStringW
0x180005b0d  nop     dword ptr [rax+rax+00h]
0x180005b12  test    byte ptr [rsp+1530h+var_14F0+4], 4
0x180005b17  jnz     short loc_180005B21
0x180005b19  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, bl; bool wil::g_fBreakOnFailure
0x180005b1f  jz      short loc_180005B33
0x180005b21  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005b28  test    rax, rax
0x180005b2b  jz      short loc_180005B33
0x180005b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b32  nop
0x180005b33  test    byte ptr [rsp+1530h+var_14F0+4], 1
0x180005b38  jnz     short loc_180005B5E
0x180005b3a  mov     rcx, [rbp+1430h+var_50]
0x180005b41  xor     rcx, rsp; StackCookie
0x180005b44  call    __security_check_cookie
0x180005b49  add     rsp, 14F8h
0x180005b50  pop     r15
0x180005b52  pop     r14
0x180005b54  pop     r13
0x180005b56  pop     r12
0x180005b58  pop     rdi
0x180005b59  pop     rsi
0x180005b5a  pop     rbx
0x180005b5b  pop     rbp
0x180005b5c  retn
0x180005b5e  lea     rcx, [rsp+1530h+var_14F0]; this
0x180005b63  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005b69  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
