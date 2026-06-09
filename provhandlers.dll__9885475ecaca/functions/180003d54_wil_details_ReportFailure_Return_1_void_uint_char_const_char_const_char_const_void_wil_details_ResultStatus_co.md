# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003d54`
- end: `0x180003ffa`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800037e4`

## callees

- `0x180003d54`
- `0x180005ed4`
- `0x180007160`
- `0x180008440`
- `0x18000872c`
- `0x18003b96a`
- `0x18003b9a0`
- `0x18003ba60`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e1a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003f99`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003f99`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003f0f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003f0f`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
0x180003d54  push    rbp
0x180003d56  push    rbx
0x180003d57  push    rsi
0x180003d58  push    rdi
0x180003d59  push    r12
0x180003d5b  push    r14
0x180003d5d  push    r15
0x180003d5f  lea     rbp, [rsp-13D0h]
0x180003d67  mov     eax, 14D0h
0x180003d6c  call    _alloca_probe
0x180003d71  sub     rsp, rax
0x180003d74  mov     rax, cs:__security_cookie
0x180003d7b  xor     rax, rsp
0x180003d7e  mov     [rbp+1400h+var_40], rax
0x180003d85  mov     rsi, r8
0x180003d88  mov     edi, edx
0x180003d8a  mov     rbx, rcx
0x180003d8d  mov     r14, [rbp+1400h+arg_28]
0x180003d94  xor     edx, edx; Val
0x180003d96  mov     r8d, 98h; Size
0x180003d9c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003da1  call    memset_0
0x180003da6  nop
0x180003da7  xor     r12d, r12d
0x180003daa  mov     [rbp+1400h+OutputString], r12w
0x180003db2  mov     [rbp+1400h+var_1440], r12b
0x180003db6  mov     rdx, [rbp+1400h+arg_30]; int
0x180003dbd  mov     ecx, [rdx]; this
0x180003dbf  mov     [rsp+1500h+var_14D8], ecx
0x180003dc3  mov     eax, [rdx+4]
0x180003dc6  mov     [rsp+1500h+var_14D4], eax
0x180003dca  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003dcf  mov     r15d, eax
0x180003dd2  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003dda  mov     ecx, r12d
0x180003ddd  lea     eax, [r12+8]
0x180003de2  cmp     dword ptr [rdx+8], 1
0x180003de6  cmovz   ecx, eax
0x180003de9  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003ded  lea     ecx, [rax-7]
0x180003df0  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003df8  inc     ecx
0x180003dfa  mov     [rsp+1500h+var_14D0], ecx
0x180003dfe  mov     rcx, [rbp+1400h+arg_38]
0x180003e05  test    rcx, rcx
0x180003e08  jz      short loc_180003E15
0x180003e0a  cmp     [rcx], r12w
0x180003e0e  mov     [rsp+1500h+var_14C8], rcx
0x180003e13  jnz     short loc_180003E1A
0x180003e15  mov     [rsp+1500h+var_14C8], r12
0x180003e1a  call    cs:__imp_GetCurrentThreadId
0x180003e20  mov     [rsp+1500h+var_14C0], eax
0x180003e24  mov     [rsp+1500h+var_14A8], rsi
0x180003e29  mov     [rsp+1500h+var_14A0], edi
0x180003e2d  mov     [rsp+1500h+var_149C], r15d
0x180003e32  mov     [rsp+1500h+var_14B8], r12
0x180003e37  mov     [rsp+1500h+var_14B0], r12
0x180003e3c  mov     [rbp+1400h+var_1458], r14
0x180003e40  mov     [rbp+1400h+var_1450], rbx
0x180003e44  mov     [rsp+1500h+var_1498], r12
0x180003e49  xorps   xmm0, xmm0
0x180003e4c  xor     eax, eax
0x180003e4e  movups  [rbp+1400h+var_1478], xmm0
0x180003e52  mov     [rbp+1400h+var_1468], rax
0x180003e56  xorps   xmm1, xmm1
0x180003e59  movups  [rsp+1500h+var_1490], xmm1
0x180003e5e  mov     [rbp+1400h+var_1480], rax
0x180003e62  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003e69  test    rax, rax
0x180003e6c  jz      short loc_180003E79
0x180003e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e73  mov     [rbp+1400h+var_1460], rax
0x180003e77  jmp     short loc_180003E7D
0x180003e79  mov     [rbp+1400h+var_1460], r12
0x180003e7d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003e84  test    rax, rax
0x180003e87  jz      short loc_180003E93
0x180003e89  lea     rcx, [rsp+1500h+var_14E0]
0x180003e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e93  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003e9a  test    rax, rax
0x180003e9d  jz      short loc_180003EB3
0x180003e9f  mov     r8d, 400h
0x180003ea5  lea     rdx, [rbp+1400h+var_1440]
0x180003ea9  lea     rcx, [rsp+1500h+var_14E0]
0x180003eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003eb3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003eba  test    rax, rax
0x180003ebd  jz      short loc_180003EC9
0x180003ebf  lea     rcx, [rsp+1500h+var_14E0]
0x180003ec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ec9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003ed0  test    rax, rax
0x180003ed3  jz      short loc_180003EE6
0x180003ed5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003eda  jnz     short loc_180003EE6
0x180003edc  lea     rcx, [rsp+1500h+var_14E0]
0x180003ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ee6  cmp     [rsp+1500h+var_14D8], r12d
0x180003eeb  jge     loc_180003FF4
0x180003ef1  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003ef8  jnz     short loc_180003F19
0x180003efa  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003f01  test    rax, rax
0x180003f04  jz      short loc_180003F0F
0x180003f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f0b  test    al, al
0x180003f0d  jmp     short loc_180003F17
0x180003f0f  call    cs:__imp_IsDebuggerPresent
0x180003f15  test    eax, eax
0x180003f17  jz      short loc_180003F20
0x180003f19  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003f1e  jz      short loc_180003F46
0x180003f20  mov     rax, cs:g_pfnResultLoggingCallback
0x180003f27  test    rax, rax
0x180003f2a  jz      short loc_180003F9F
0x180003f2c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003f33  jnz     short loc_180003F9F
0x180003f35  xor     r8d, r8d
0x180003f38  xor     edx, edx
0x180003f3a  lea     rcx, [rsp+1500h+var_14E0]
0x180003f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f44  jmp     short loc_180003F9F
0x180003f46  mov     ebx, 800h
0x180003f4b  mov     rax, cs:g_pfnResultLoggingCallback
0x180003f52  test    rax, rax
0x180003f55  jz      short loc_180003F74
0x180003f57  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003f5e  jnz     short loc_180003F74
0x180003f60  mov     r8d, ebx
0x180003f63  lea     rdx, [rbp+1400h+OutputString]
0x180003f6a  lea     rcx, [rsp+1500h+var_14E0]
0x180003f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f74  cmp     [rbp+1400h+OutputString], r12w
0x180003f7c  jnz     short loc_180003F92
0x180003f7e  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003f83  mov     rdx, rbx; unsigned __int16 *
0x180003f86  lea     rcx, [rbp+1400h+OutputString]; this
0x180003f8d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003f92  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003f99  call    cs:__imp_OutputDebugStringW
0x180003f9f  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003fa4  jnz     short loc_180003FAF
0x180003fa6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003fad  jz      short loc_180003FC1
0x180003faf  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003fb6  test    rax, rax
0x180003fb9  jz      short loc_180003FC1
0x180003fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fc0  nop
0x180003fc1  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003fc6  jnz     short loc_180003FE9
0x180003fc8  mov     rcx, [rbp+1400h+var_40]
0x180003fcf  xor     rcx, rsp; StackCookie
0x180003fd2  call    __security_check_cookie
0x180003fd7  add     rsp, 14D0h
0x180003fde  pop     r15
0x180003fe0  pop     r14
0x180003fe2  pop     r12
0x180003fe4  pop     rdi
0x180003fe5  pop     rsi
0x180003fe6  pop     rbx
0x180003fe7  pop     rbp
0x180003fe8  retn
0x180003fe9  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003fee  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003ff4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
