# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140011258`
- end: `0x1400114e5`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000e01c`

## callees

- `0x140010ad3`
- `0x140011258`
- `0x140011e14`
- `0x140012ac0`
- `0x140013598`
- `0x140013674`
- `0x14001e050`
- `0x14001e110`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140011306`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140011306`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400113fa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400113fa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140011484`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140011484`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v19, (int)a7);
  v17 = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v18 = v11;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v10;
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( ((v18 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v18 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x140011258  push    rbp
0x14001125a  push    rbx
0x14001125b  push    rsi
0x14001125c  push    rdi
0x14001125d  push    r12
0x14001125f  push    r14
0x140011261  push    r15
0x140011263  lea     rbp, [rsp-13D0h]
0x14001126b  mov     eax, 14D0h
0x140011270  call    _alloca_probe
0x140011275  sub     rsp, rax
0x140011278  mov     rax, cs:__security_cookie
0x14001127f  xor     rax, rsp
0x140011282  mov     [rbp+1400h+var_40], rax
0x140011289  mov     r14, r8
0x14001128c  mov     esi, edx
0x14001128e  mov     r15, rcx
0x140011291  mov     rdi, [rbp+1400h+arg_28]
0x140011298  xor     edx, edx; Val
0x14001129a  mov     r8d, 98h; Size
0x1400112a0  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1400112a5  call    memset_0
0x1400112aa  nop
0x1400112ab  xor     r12d, r12d
0x1400112ae  mov     [rbp+1400h+OutputString], r12w
0x1400112b6  mov     [rbp+1400h+var_1440], r12b
0x1400112ba  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1400112c1  mov     ecx, [rdx]; this
0x1400112c3  mov     [rsp+1500h+var_14D8], ecx
0x1400112c7  mov     eax, [rdx+4]
0x1400112ca  mov     [rsp+1500h+var_14D4], eax
0x1400112ce  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400112d3  mov     ebx, eax
0x1400112d5  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1400112dd  mov     ecx, r12d
0x1400112e0  lea     eax, [r12+8]
0x1400112e5  cmp     dword ptr [rdx+8], 1
0x1400112e9  cmovz   ecx, eax
0x1400112ec  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1400112f0  lea     ecx, [rax-7]
0x1400112f3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400112fb  inc     ecx
0x1400112fd  mov     [rsp+1500h+var_14D0], ecx
0x140011301  mov     [rsp+1500h+var_14C8], r12
0x140011306  call    cs:__imp_GetCurrentThreadId
0x14001130c  mov     [rsp+1500h+var_14C0], eax
0x140011310  mov     [rsp+1500h+var_14A8], r14
0x140011315  mov     [rsp+1500h+var_14A0], esi
0x140011319  mov     [rsp+1500h+var_149C], ebx
0x14001131d  mov     [rsp+1500h+var_14B8], r12
0x140011322  mov     [rsp+1500h+var_14B0], r12
0x140011327  mov     [rbp+1400h+var_1458], rdi
0x14001132b  mov     [rbp+1400h+var_1450], r15
0x14001132f  mov     [rsp+1500h+var_1498], r12
0x140011334  xorps   xmm0, xmm0
0x140011337  xor     eax, eax
0x140011339  movups  [rbp+1400h+var_1478], xmm0
0x14001133d  mov     [rbp+1400h+var_1468], rax
0x140011341  xorps   xmm1, xmm1
0x140011344  movups  [rsp+1500h+var_1490], xmm1
0x140011349  mov     [rbp+1400h+var_1480], rax
0x14001134d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140011354  test    rax, rax
0x140011357  jz      short loc_140011364
0x140011359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001135e  mov     [rbp+1400h+var_1460], rax
0x140011362  jmp     short loc_140011368
0x140011364  mov     [rbp+1400h+var_1460], r12
0x140011368  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14001136f  test    rax, rax
0x140011372  jz      short loc_14001137E
0x140011374  lea     rcx, [rsp+1500h+var_14E0]
0x140011379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001137e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140011385  test    rax, rax
0x140011388  jz      short loc_14001139E
0x14001138a  mov     r8d, 400h
0x140011390  lea     rdx, [rbp+1400h+var_1440]
0x140011394  lea     rcx, [rsp+1500h+var_14E0]
0x140011399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001139e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400113a5  test    rax, rax
0x1400113a8  jz      short loc_1400113B4
0x1400113aa  lea     rcx, [rsp+1500h+var_14E0]
0x1400113af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400113b4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400113bb  test    rax, rax
0x1400113be  jz      short loc_1400113D1
0x1400113c0  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1400113c5  jnz     short loc_1400113D1
0x1400113c7  lea     rcx, [rsp+1500h+var_14E0]
0x1400113cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400113d1  cmp     [rsp+1500h+var_14D8], r12d
0x1400113d6  jge     loc_1400114DF
0x1400113dc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1400113e3  jnz     short loc_140011404
0x1400113e5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400113ec  test    rax, rax
0x1400113ef  jz      short loc_1400113FA
0x1400113f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400113f6  test    al, al
0x1400113f8  jmp     short loc_140011402
0x1400113fa  call    cs:__imp_IsDebuggerPresent
0x140011400  test    eax, eax
0x140011402  jz      short loc_14001140B
0x140011404  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140011409  jz      short loc_140011431
0x14001140b  mov     rax, cs:g_pfnResultLoggingCallback
0x140011412  test    rax, rax
0x140011415  jz      short loc_14001148A
0x140011417  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14001141e  jnz     short loc_14001148A
0x140011420  xor     r8d, r8d
0x140011423  xor     edx, edx
0x140011425  lea     rcx, [rsp+1500h+var_14E0]
0x14001142a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001142f  jmp     short loc_14001148A
0x140011431  mov     ebx, 800h
0x140011436  mov     rax, cs:g_pfnResultLoggingCallback
0x14001143d  test    rax, rax
0x140011440  jz      short loc_14001145F
0x140011442  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140011449  jnz     short loc_14001145F
0x14001144b  mov     r8d, ebx
0x14001144e  lea     rdx, [rbp+1400h+OutputString]
0x140011455  lea     rcx, [rsp+1500h+var_14E0]
0x14001145a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001145f  cmp     [rbp+1400h+OutputString], r12w
0x140011467  jnz     short loc_14001147D
0x140011469  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x14001146e  mov     rdx, rbx; unsigned __int16 *
0x140011471  lea     rcx, [rbp+1400h+OutputString]; this
0x140011478  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14001147d  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140011484  call    cs:__imp_OutputDebugStringW
0x14001148a  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x14001148f  jnz     short loc_14001149A
0x140011491  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140011498  jz      short loc_1400114AC
0x14001149a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400114a1  test    rax, rax
0x1400114a4  jz      short loc_1400114AC
0x1400114a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400114ab  nop
0x1400114ac  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1400114b1  jnz     short loc_1400114D4
0x1400114b3  mov     rcx, [rbp+1400h+var_40]
0x1400114ba  xor     rcx, rsp; StackCookie
0x1400114bd  call    __security_check_cookie
0x1400114c2  add     rsp, 14D0h
0x1400114c9  pop     r15
0x1400114cb  pop     r14
0x1400114cd  pop     r12
0x1400114cf  pop     rdi
0x1400114d0  pop     rsi
0x1400114d1  pop     rbx
0x1400114d2  pop     rbp
0x1400114d3  retn
0x1400114d4  lea     rcx, [rsp+1500h+var_14E0]; this
0x1400114d9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1400114df  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
