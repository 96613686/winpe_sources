# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140004754`
- end: `0x140004a0d`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400043d4`

## callees

- `0x1400039b1`
- `0x140004754`
- `0x1400056e4`
- `0x140006874`
- `0x140007540`
- `0x140007750`
- `0x140061c90`
- `0x140061d50`
- `0x140063010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000481a`
- `KERNEL32!GetCurrentThreadId` at `0x14000481a`
- `KERNEL32!OutputDebugStringW` at `0x1400049a5`
- `KERNEL32!OutputDebugStringW` at `0x1400049a5`
- `KERNEL32!IsDebuggerPresent` at `0x140004915`
- `KERNEL32!IsDebuggerPresent` at `0x140004915`

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
0x140004754  push    rbp
0x140004756  push    rbx
0x140004757  push    rsi
0x140004758  push    rdi
0x140004759  push    r12
0x14000475b  push    r14
0x14000475d  push    r15
0x14000475f  lea     rbp, [rsp-13D0h]
0x140004767  mov     eax, 14D0h
0x14000476c  call    _alloca_probe
0x140004771  sub     rsp, rax
0x140004774  mov     rax, cs:__security_cookie
0x14000477b  xor     rax, rsp
0x14000477e  mov     [rbp+1400h+var_40], rax
0x140004785  mov     rsi, r8
0x140004788  mov     edi, edx
0x14000478a  mov     rbx, rcx
0x14000478d  mov     r14, [rbp+1400h+arg_28]
0x140004794  xor     edx, edx; Val
0x140004796  mov     r8d, 98h; Size
0x14000479c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1400047a1  call    memset_0
0x1400047a6  nop
0x1400047a7  xor     r12d, r12d
0x1400047aa  mov     [rbp+1400h+OutputString], r12w
0x1400047b2  mov     [rbp+1400h+var_1440], r12b
0x1400047b6  mov     rdx, [rbp+1400h+arg_30]; int
0x1400047bd  mov     ecx, [rdx]; this
0x1400047bf  mov     [rsp+1500h+var_14D8], ecx
0x1400047c3  mov     eax, [rdx+4]
0x1400047c6  mov     [rsp+1500h+var_14D4], eax
0x1400047ca  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400047cf  mov     r15d, eax
0x1400047d2  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1400047da  mov     ecx, r12d
0x1400047dd  lea     eax, [r12+8]
0x1400047e2  cmp     dword ptr [rdx+8], 1
0x1400047e6  cmovz   ecx, eax
0x1400047e9  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1400047ed  lea     ecx, [rax-7]
0x1400047f0  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400047f8  inc     ecx
0x1400047fa  mov     [rsp+1500h+var_14D0], ecx
0x1400047fe  mov     rcx, [rbp+1400h+arg_38]
0x140004805  test    rcx, rcx
0x140004808  jz      short loc_140004815
0x14000480a  cmp     [rcx], r12w
0x14000480e  mov     [rsp+1500h+var_14C8], rcx
0x140004813  jnz     short loc_14000481A
0x140004815  mov     [rsp+1500h+var_14C8], r12
0x14000481a  call    cs:__imp_GetCurrentThreadId
0x140004821  nop     dword ptr [rax+rax+00h]
0x140004826  mov     [rsp+1500h+var_14C0], eax
0x14000482a  mov     [rsp+1500h+var_14A8], rsi
0x14000482f  mov     [rsp+1500h+var_14A0], edi
0x140004833  mov     [rsp+1500h+var_149C], r15d
0x140004838  mov     [rsp+1500h+var_14B8], r12
0x14000483d  mov     [rsp+1500h+var_14B0], r12
0x140004842  mov     [rbp+1400h+var_1458], r14
0x140004846  mov     [rbp+1400h+var_1450], rbx
0x14000484a  mov     [rsp+1500h+var_1498], r12
0x14000484f  xorps   xmm0, xmm0
0x140004852  xor     eax, eax
0x140004854  movups  [rbp+1400h+var_1478], xmm0
0x140004858  mov     [rbp+1400h+var_1468], rax
0x14000485c  xorps   xmm1, xmm1
0x14000485f  movups  [rsp+1500h+var_1490], xmm1
0x140004864  mov     [rbp+1400h+var_1480], rax
0x140004868  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000486f  test    rax, rax
0x140004872  jz      short loc_14000487F
0x140004874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004879  mov     [rbp+1400h+var_1460], rax
0x14000487d  jmp     short loc_140004883
0x14000487f  mov     [rbp+1400h+var_1460], r12
0x140004883  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000488a  test    rax, rax
0x14000488d  jz      short loc_140004899
0x14000488f  lea     rcx, [rsp+1500h+var_14E0]
0x140004894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004899  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400048a0  test    rax, rax
0x1400048a3  jz      short loc_1400048B9
0x1400048a5  mov     r8d, 400h
0x1400048ab  lea     rdx, [rbp+1400h+var_1440]
0x1400048af  lea     rcx, [rsp+1500h+var_14E0]
0x1400048b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400048b9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400048c0  test    rax, rax
0x1400048c3  jz      short loc_1400048CF
0x1400048c5  lea     rcx, [rsp+1500h+var_14E0]
0x1400048ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400048cf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400048d6  test    rax, rax
0x1400048d9  jz      short loc_1400048EC
0x1400048db  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1400048e0  jnz     short loc_1400048EC
0x1400048e2  lea     rcx, [rsp+1500h+var_14E0]
0x1400048e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400048ec  cmp     [rsp+1500h+var_14D8], r12d
0x1400048f1  jge     loc_140004A07
0x1400048f7  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1400048fe  jnz     short loc_140004925
0x140004900  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140004907  test    rax, rax
0x14000490a  jz      short loc_140004915
0x14000490c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004911  test    al, al
0x140004913  jmp     short loc_140004923
0x140004915  call    cs:__imp_IsDebuggerPresent
0x14000491c  nop     dword ptr [rax+rax+00h]
0x140004921  test    eax, eax
0x140004923  jz      short loc_14000492C
0x140004925  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x14000492a  jz      short loc_140004952
0x14000492c  mov     rax, cs:g_pfnResultLoggingCallback
0x140004933  test    rax, rax
0x140004936  jz      short loc_1400049B1
0x140004938  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000493f  jnz     short loc_1400049B1
0x140004941  xor     r8d, r8d
0x140004944  xor     edx, edx
0x140004946  lea     rcx, [rsp+1500h+var_14E0]
0x14000494b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004950  jmp     short loc_1400049B1
0x140004952  mov     ebx, 800h
0x140004957  mov     rax, cs:g_pfnResultLoggingCallback
0x14000495e  test    rax, rax
0x140004961  jz      short loc_140004980
0x140004963  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000496a  jnz     short loc_140004980
0x14000496c  mov     r8d, ebx
0x14000496f  lea     rdx, [rbp+1400h+OutputString]
0x140004976  lea     rcx, [rsp+1500h+var_14E0]
0x14000497b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004980  cmp     [rbp+1400h+OutputString], r12w
0x140004988  jnz     short loc_14000499E
0x14000498a  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x14000498f  mov     rdx, rbx; unsigned __int16 *
0x140004992  lea     rcx, [rbp+1400h+OutputString]; this
0x140004999  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000499e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1400049a5  call    cs:__imp_OutputDebugStringW
0x1400049ac  nop     dword ptr [rax+rax+00h]
0x1400049b1  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1400049b6  jnz     short loc_1400049C1
0x1400049b8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1400049bf  jz      short loc_1400049D3
0x1400049c1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400049c8  test    rax, rax
0x1400049cb  jz      short loc_1400049D3
0x1400049cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400049d2  nop
0x1400049d3  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1400049d8  jnz     short loc_1400049FC
0x1400049da  mov     rcx, [rbp+1400h+var_40]
0x1400049e1  xor     rcx, rsp; StackCookie
0x1400049e4  call    __security_check_cookie
0x1400049e9  add     rsp, 14D0h
0x1400049f0  pop     r15
0x1400049f2  pop     r14
0x1400049f4  pop     r12
0x1400049f6  pop     rdi
0x1400049f7  pop     rsi
0x1400049f8  pop     rbx
0x1400049f9  pop     rbp
0x1400049fa  retn
0x1400049fc  lea     rcx, [rsp+1500h+var_14E0]; this
0x140004a01  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140004a07  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
