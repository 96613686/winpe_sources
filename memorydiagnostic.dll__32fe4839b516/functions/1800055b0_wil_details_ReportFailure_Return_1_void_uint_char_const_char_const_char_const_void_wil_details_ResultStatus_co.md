# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800055b0`
- end: `0x180005869`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800047c4`

## callees

- `0x1800026b0`
- `0x180003374`
- `0x1800055b0`
- `0x18000d474`
- `0x18000fcf0`
- `0x180015bec`
- `0x1800162d8`
- `0x180021f90`
- `0x180024010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180005771`
- `KERNEL32!IsDebuggerPresent` at `0x180005771`
- `KERNEL32!OutputDebugStringW` at `0x180005801`
- `KERNEL32!OutputDebugStringW` at `0x180005801`
- `KERNEL32!GetCurrentThreadId` at `0x180005676`
- `KERNEL32!GetCurrentThreadId` at `0x180005676`

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
0x1800055b0  push    rbp
0x1800055b2  push    rbx
0x1800055b3  push    rsi
0x1800055b4  push    rdi
0x1800055b5  push    r12
0x1800055b7  push    r14
0x1800055b9  push    r15
0x1800055bb  lea     rbp, [rsp-13D0h]
0x1800055c3  mov     eax, 14D0h
0x1800055c8  call    _alloca_probe
0x1800055cd  sub     rsp, rax
0x1800055d0  mov     rax, cs:__security_cookie
0x1800055d7  xor     rax, rsp
0x1800055da  mov     [rbp+1400h+var_40], rax
0x1800055e1  mov     rsi, r8
0x1800055e4  mov     edi, edx
0x1800055e6  mov     rbx, rcx
0x1800055e9  mov     r14, [rbp+1400h+arg_28]
0x1800055f0  xor     edx, edx; Val
0x1800055f2  mov     r8d, 98h; Size
0x1800055f8  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800055fd  call    memset_0
0x180005602  nop
0x180005603  xor     r12d, r12d
0x180005606  mov     [rbp+1400h+OutputString], r12w
0x18000560e  mov     [rbp+1400h+var_1440], r12b
0x180005612  mov     rdx, [rbp+1400h+arg_30]; int
0x180005619  mov     ecx, [rdx]; this
0x18000561b  mov     [rsp+1500h+var_14D8], ecx
0x18000561f  mov     eax, [rdx+4]
0x180005622  mov     [rsp+1500h+var_14D4], eax
0x180005626  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000562b  mov     r15d, eax
0x18000562e  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180005636  mov     ecx, r12d
0x180005639  lea     eax, [r12+8]
0x18000563e  cmp     dword ptr [rdx+8], 1
0x180005642  cmovz   ecx, eax
0x180005645  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180005649  lea     ecx, [rax-7]
0x18000564c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x180005654  inc     ecx
0x180005656  mov     [rsp+1500h+var_14D0], ecx
0x18000565a  mov     rcx, [rbp+1400h+arg_38]
0x180005661  test    rcx, rcx
0x180005664  jz      short loc_180005671
0x180005666  cmp     [rcx], r12w
0x18000566a  mov     [rsp+1500h+var_14C8], rcx
0x18000566f  jnz     short loc_180005676
0x180005671  mov     [rsp+1500h+var_14C8], r12
0x180005676  call    cs:__imp_GetCurrentThreadId
0x18000567d  nop     dword ptr [rax+rax+00h]
0x180005682  mov     [rsp+1500h+var_14C0], eax
0x180005686  mov     [rsp+1500h+var_14A8], rsi
0x18000568b  mov     [rsp+1500h+var_14A0], edi
0x18000568f  mov     [rsp+1500h+var_149C], r15d
0x180005694  mov     [rsp+1500h+var_14B8], r12
0x180005699  mov     [rsp+1500h+var_14B0], r12
0x18000569e  mov     [rbp+1400h+var_1458], r14
0x1800056a2  mov     [rbp+1400h+var_1450], rbx
0x1800056a6  mov     [rsp+1500h+var_1498], r12
0x1800056ab  xorps   xmm0, xmm0
0x1800056ae  xor     eax, eax
0x1800056b0  movups  [rbp+1400h+var_1478], xmm0
0x1800056b4  mov     [rbp+1400h+var_1468], rax
0x1800056b8  xorps   xmm1, xmm1
0x1800056bb  movups  [rsp+1500h+var_1490], xmm1
0x1800056c0  mov     [rbp+1400h+var_1480], rax
0x1800056c4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800056cb  test    rax, rax
0x1800056ce  jz      short loc_1800056DB
0x1800056d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056d5  mov     [rbp+1400h+var_1460], rax
0x1800056d9  jmp     short loc_1800056DF
0x1800056db  mov     [rbp+1400h+var_1460], r12
0x1800056df  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800056e6  test    rax, rax
0x1800056e9  jz      short loc_1800056F5
0x1800056eb  lea     rcx, [rsp+1500h+var_14E0]
0x1800056f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056f5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800056fc  test    rax, rax
0x1800056ff  jz      short loc_180005715
0x180005701  mov     r8d, 400h
0x180005707  lea     rdx, [rbp+1400h+var_1440]
0x18000570b  lea     rcx, [rsp+1500h+var_14E0]
0x180005710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005715  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000571c  test    rax, rax
0x18000571f  jz      short loc_18000572B
0x180005721  lea     rcx, [rsp+1500h+var_14E0]
0x180005726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000572b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005732  test    rax, rax
0x180005735  jz      short loc_180005748
0x180005737  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000573c  jnz     short loc_180005748
0x18000573e  lea     rcx, [rsp+1500h+var_14E0]
0x180005743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005748  cmp     [rsp+1500h+var_14D8], r12d
0x18000574d  jge     loc_180005863
0x180005753  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000575a  jnz     short loc_180005781
0x18000575c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005763  test    rax, rax
0x180005766  jz      short loc_180005771
0x180005768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000576d  test    al, al
0x18000576f  jmp     short loc_18000577F
0x180005771  call    cs:__imp_IsDebuggerPresent
0x180005778  nop     dword ptr [rax+rax+00h]
0x18000577d  test    eax, eax
0x18000577f  jz      short loc_180005788
0x180005781  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005786  jz      short loc_1800057AE
0x180005788  mov     rax, cs:g_pfnResultLoggingCallback
0x18000578f  test    rax, rax
0x180005792  jz      short loc_18000580D
0x180005794  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000579b  jnz     short loc_18000580D
0x18000579d  xor     r8d, r8d
0x1800057a0  xor     edx, edx
0x1800057a2  lea     rcx, [rsp+1500h+var_14E0]
0x1800057a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057ac  jmp     short loc_18000580D
0x1800057ae  mov     ebx, 800h
0x1800057b3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800057ba  test    rax, rax
0x1800057bd  jz      short loc_1800057DC
0x1800057bf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800057c6  jnz     short loc_1800057DC
0x1800057c8  mov     r8d, ebx
0x1800057cb  lea     rdx, [rbp+1400h+OutputString]
0x1800057d2  lea     rcx, [rsp+1500h+var_14E0]
0x1800057d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057dc  cmp     [rbp+1400h+OutputString], r12w
0x1800057e4  jnz     short loc_1800057FA
0x1800057e6  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800057eb  mov     rdx, rbx; unsigned __int16 *
0x1800057ee  lea     rcx, [rbp+1400h+OutputString]; this
0x1800057f5  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800057fa  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180005801  call    cs:__imp_OutputDebugStringW
0x180005808  nop     dword ptr [rax+rax+00h]
0x18000580d  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180005812  jnz     short loc_18000581D
0x180005814  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000581b  jz      short loc_18000582F
0x18000581d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005824  test    rax, rax
0x180005827  jz      short loc_18000582F
0x180005829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000582e  nop
0x18000582f  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180005834  jnz     short loc_180005858
0x180005836  mov     rcx, [rbp+1400h+var_40]
0x18000583d  xor     rcx, rsp; StackCookie
0x180005840  call    __security_check_cookie
0x180005845  add     rsp, 14D0h
0x18000584c  pop     r15
0x18000584e  pop     r14
0x180005850  pop     r12
0x180005852  pop     rdi
0x180005853  pop     rsi
0x180005854  pop     rbx
0x180005855  pop     rbp
0x180005856  retn
0x180005858  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000585d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005863  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
