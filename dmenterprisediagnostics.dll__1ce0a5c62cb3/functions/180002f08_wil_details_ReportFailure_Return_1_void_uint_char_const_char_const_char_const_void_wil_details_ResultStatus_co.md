# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002f08`
- end: `0x1800031ae`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002a04`

## callees

- `0x1800017e0`
- `0x1800023c0`
- `0x180002f08`
- `0x1800045b4`
- `0x180005710`
- `0x1800070a8`
- `0x1800071e0`
- `0x180024370`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002fce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002fce`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800030c3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800030c3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000314d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000314d`

## pseudocode

```c
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
0x180002f08  push    rbp
0x180002f0a  push    rbx
0x180002f0b  push    rsi
0x180002f0c  push    rdi
0x180002f0d  push    r12
0x180002f0f  push    r14
0x180002f11  push    r15
0x180002f13  lea     rbp, [rsp-13D0h]
0x180002f1b  mov     eax, 14D0h
0x180002f20  call    _alloca_probe
0x180002f25  sub     rsp, rax
0x180002f28  mov     rax, cs:__security_cookie
0x180002f2f  xor     rax, rsp
0x180002f32  mov     [rbp+1400h+var_40], rax
0x180002f39  mov     rsi, r8
0x180002f3c  mov     edi, edx
0x180002f3e  mov     rbx, rcx
0x180002f41  mov     r14, [rbp+1400h+arg_28]
0x180002f48  xor     edx, edx; Val
0x180002f4a  mov     r8d, 98h; Size
0x180002f50  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180002f55  call    memset_0
0x180002f5a  nop
0x180002f5b  xor     r12d, r12d
0x180002f5e  mov     [rbp+1400h+OutputString], r12w
0x180002f66  mov     [rbp+1400h+var_1440], r12b
0x180002f6a  mov     rdx, [rbp+1400h+arg_30]; int
0x180002f71  mov     ecx, [rdx]; this
0x180002f73  mov     [rsp+1500h+var_14D8], ecx
0x180002f77  mov     eax, [rdx+4]
0x180002f7a  mov     [rsp+1500h+var_14D4], eax
0x180002f7e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002f83  mov     r15d, eax
0x180002f86  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180002f8e  mov     ecx, r12d
0x180002f91  lea     eax, [r12+8]
0x180002f96  cmp     dword ptr [rdx+8], 1
0x180002f9a  cmovz   ecx, eax
0x180002f9d  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180002fa1  lea     ecx, [rax-7]
0x180002fa4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002fac  inc     ecx
0x180002fae  mov     [rsp+1500h+var_14D0], ecx
0x180002fb2  mov     rcx, [rbp+1400h+arg_38]
0x180002fb9  test    rcx, rcx
0x180002fbc  jz      short loc_180002FC9
0x180002fbe  cmp     [rcx], r12w
0x180002fc2  mov     [rsp+1500h+var_14C8], rcx
0x180002fc7  jnz     short loc_180002FCE
0x180002fc9  mov     [rsp+1500h+var_14C8], r12
0x180002fce  call    cs:__imp_GetCurrentThreadId
0x180002fd4  mov     [rsp+1500h+var_14C0], eax
0x180002fd8  mov     [rsp+1500h+var_14A8], rsi
0x180002fdd  mov     [rsp+1500h+var_14A0], edi
0x180002fe1  mov     [rsp+1500h+var_149C], r15d
0x180002fe6  mov     [rsp+1500h+var_14B8], r12
0x180002feb  mov     [rsp+1500h+var_14B0], r12
0x180002ff0  mov     [rbp+1400h+var_1458], r14
0x180002ff4  mov     [rbp+1400h+var_1450], rbx
0x180002ff8  mov     [rsp+1500h+var_1498], r12
0x180002ffd  xorps   xmm0, xmm0
0x180003000  xor     eax, eax
0x180003002  movups  [rbp+1400h+var_1478], xmm0
0x180003006  mov     [rbp+1400h+var_1468], rax
0x18000300a  xorps   xmm1, xmm1
0x18000300d  movups  [rsp+1500h+var_1490], xmm1
0x180003012  mov     [rbp+1400h+var_1480], rax
0x180003016  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000301d  test    rax, rax
0x180003020  jz      short loc_18000302D
0x180003022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003027  mov     [rbp+1400h+var_1460], rax
0x18000302b  jmp     short loc_180003031
0x18000302d  mov     [rbp+1400h+var_1460], r12
0x180003031  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003038  test    rax, rax
0x18000303b  jz      short loc_180003047
0x18000303d  lea     rcx, [rsp+1500h+var_14E0]
0x180003042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003047  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000304e  test    rax, rax
0x180003051  jz      short loc_180003067
0x180003053  mov     r8d, 400h
0x180003059  lea     rdx, [rbp+1400h+var_1440]
0x18000305d  lea     rcx, [rsp+1500h+var_14E0]
0x180003062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003067  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000306e  test    rax, rax
0x180003071  jz      short loc_18000307D
0x180003073  lea     rcx, [rsp+1500h+var_14E0]
0x180003078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000307d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003084  test    rax, rax
0x180003087  jz      short loc_18000309A
0x180003089  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000308e  jnz     short loc_18000309A
0x180003090  lea     rcx, [rsp+1500h+var_14E0]
0x180003095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000309a  cmp     [rsp+1500h+var_14D8], r12d
0x18000309f  jge     loc_1800031A8
0x1800030a5  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800030ac  jnz     short loc_1800030CD
0x1800030ae  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800030b5  test    rax, rax
0x1800030b8  jz      short loc_1800030C3
0x1800030ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030bf  test    al, al
0x1800030c1  jmp     short loc_1800030CB
0x1800030c3  call    cs:__imp_IsDebuggerPresent
0x1800030c9  test    eax, eax
0x1800030cb  jz      short loc_1800030D4
0x1800030cd  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800030d2  jz      short loc_1800030FA
0x1800030d4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800030db  test    rax, rax
0x1800030de  jz      short loc_180003153
0x1800030e0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800030e7  jnz     short loc_180003153
0x1800030e9  xor     r8d, r8d
0x1800030ec  xor     edx, edx
0x1800030ee  lea     rcx, [rsp+1500h+var_14E0]
0x1800030f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030f8  jmp     short loc_180003153
0x1800030fa  mov     ebx, 800h
0x1800030ff  mov     rax, cs:g_pfnResultLoggingCallback
0x180003106  test    rax, rax
0x180003109  jz      short loc_180003128
0x18000310b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003112  jnz     short loc_180003128
0x180003114  mov     r8d, ebx
0x180003117  lea     rdx, [rbp+1400h+OutputString]
0x18000311e  lea     rcx, [rsp+1500h+var_14E0]
0x180003123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003128  cmp     [rbp+1400h+OutputString], r12w
0x180003130  jnz     short loc_180003146
0x180003132  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003137  mov     rdx, rbx; unsigned __int16 *
0x18000313a  lea     rcx, [rbp+1400h+OutputString]; this
0x180003141  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003146  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000314d  call    cs:__imp_OutputDebugStringW
0x180003153  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003158  jnz     short loc_180003163
0x18000315a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003161  jz      short loc_180003175
0x180003163  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000316a  test    rax, rax
0x18000316d  jz      short loc_180003175
0x18000316f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003174  nop
0x180003175  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000317a  jnz     short loc_18000319D
0x18000317c  mov     rcx, [rbp+1400h+var_40]
0x180003183  xor     rcx, rsp; StackCookie
0x180003186  call    __security_check_cookie
0x18000318b  add     rsp, 14D0h
0x180003192  pop     r15
0x180003194  pop     r14
0x180003196  pop     r12
0x180003198  pop     rdi
0x180003199  pop     rsi
0x18000319a  pop     rbx
0x18000319b  pop     rbp
0x18000319c  retn
0x18000319d  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800031a2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800031a8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
