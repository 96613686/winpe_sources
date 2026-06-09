# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003e50`
- end: `0x1800040f6`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800038e4`

## callees

- `0x1800022e0`
- `0x180002cbc`
- `0x180003e50`
- `0x1800050a4`
- `0x180005fe0`
- `0x180007070`
- `0x18000714c`
- `0x18001ea10`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003f16`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003f16`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004095`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004095`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000400b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000400b`

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
0x180003e50  push    rbp
0x180003e52  push    rbx
0x180003e53  push    rsi
0x180003e54  push    rdi
0x180003e55  push    r12
0x180003e57  push    r14
0x180003e59  push    r15
0x180003e5b  lea     rbp, [rsp-13D0h]
0x180003e63  mov     eax, 14D0h
0x180003e68  call    _alloca_probe
0x180003e6d  sub     rsp, rax
0x180003e70  mov     rax, cs:__security_cookie
0x180003e77  xor     rax, rsp
0x180003e7a  mov     [rbp+1400h+var_40], rax
0x180003e81  mov     rsi, r8
0x180003e84  mov     edi, edx
0x180003e86  mov     rbx, rcx
0x180003e89  mov     r14, [rbp+1400h+arg_28]
0x180003e90  xor     edx, edx; Val
0x180003e92  mov     r8d, 98h; Size
0x180003e98  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003e9d  call    memset_0
0x180003ea2  nop
0x180003ea3  xor     r12d, r12d
0x180003ea6  mov     [rbp+1400h+OutputString], r12w
0x180003eae  mov     [rbp+1400h+var_1440], r12b
0x180003eb2  mov     rdx, [rbp+1400h+arg_30]; int
0x180003eb9  mov     ecx, [rdx]; this
0x180003ebb  mov     [rsp+1500h+var_14D8], ecx
0x180003ebf  mov     eax, [rdx+4]
0x180003ec2  mov     [rsp+1500h+var_14D4], eax
0x180003ec6  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003ecb  mov     r15d, eax
0x180003ece  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003ed6  mov     ecx, r12d
0x180003ed9  lea     eax, [r12+8]
0x180003ede  cmp     dword ptr [rdx+8], 1
0x180003ee2  cmovz   ecx, eax
0x180003ee5  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003ee9  lea     ecx, [rax-7]
0x180003eec  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003ef4  inc     ecx
0x180003ef6  mov     [rsp+1500h+var_14D0], ecx
0x180003efa  mov     rcx, [rbp+1400h+arg_38]
0x180003f01  test    rcx, rcx
0x180003f04  jz      short loc_180003F11
0x180003f06  cmp     [rcx], r12w
0x180003f0a  mov     [rsp+1500h+var_14C8], rcx
0x180003f0f  jnz     short loc_180003F16
0x180003f11  mov     [rsp+1500h+var_14C8], r12
0x180003f16  call    cs:__imp_GetCurrentThreadId
0x180003f1c  mov     [rsp+1500h+var_14C0], eax
0x180003f20  mov     [rsp+1500h+var_14A8], rsi
0x180003f25  mov     [rsp+1500h+var_14A0], edi
0x180003f29  mov     [rsp+1500h+var_149C], r15d
0x180003f2e  mov     [rsp+1500h+var_14B8], r12
0x180003f33  mov     [rsp+1500h+var_14B0], r12
0x180003f38  mov     [rbp+1400h+var_1458], r14
0x180003f3c  mov     [rbp+1400h+var_1450], rbx
0x180003f40  mov     [rsp+1500h+var_1498], r12
0x180003f45  xorps   xmm0, xmm0
0x180003f48  xor     eax, eax
0x180003f4a  movups  [rbp+1400h+var_1478], xmm0
0x180003f4e  mov     [rbp+1400h+var_1468], rax
0x180003f52  xorps   xmm1, xmm1
0x180003f55  movups  [rsp+1500h+var_1490], xmm1
0x180003f5a  mov     [rbp+1400h+var_1480], rax
0x180003f5e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003f65  test    rax, rax
0x180003f68  jz      short loc_180003F75
0x180003f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f6f  mov     [rbp+1400h+var_1460], rax
0x180003f73  jmp     short loc_180003F79
0x180003f75  mov     [rbp+1400h+var_1460], r12
0x180003f79  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003f80  test    rax, rax
0x180003f83  jz      short loc_180003F8F
0x180003f85  lea     rcx, [rsp+1500h+var_14E0]
0x180003f8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f8f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003f96  test    rax, rax
0x180003f99  jz      short loc_180003FAF
0x180003f9b  mov     r8d, 400h
0x180003fa1  lea     rdx, [rbp+1400h+var_1440]
0x180003fa5  lea     rcx, [rsp+1500h+var_14E0]
0x180003faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003faf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003fb6  test    rax, rax
0x180003fb9  jz      short loc_180003FC5
0x180003fbb  lea     rcx, [rsp+1500h+var_14E0]
0x180003fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fc5  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003fcc  test    rax, rax
0x180003fcf  jz      short loc_180003FE2
0x180003fd1  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003fd6  jnz     short loc_180003FE2
0x180003fd8  lea     rcx, [rsp+1500h+var_14E0]
0x180003fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fe2  cmp     [rsp+1500h+var_14D8], r12d
0x180003fe7  jge     loc_1800040F0
0x180003fed  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003ff4  jnz     short loc_180004015
0x180003ff6  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003ffd  test    rax, rax
0x180004000  jz      short loc_18000400B
0x180004002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004007  test    al, al
0x180004009  jmp     short loc_180004013
0x18000400b  call    cs:__imp_IsDebuggerPresent
0x180004011  test    eax, eax
0x180004013  jz      short loc_18000401C
0x180004015  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000401a  jz      short loc_180004042
0x18000401c  mov     rax, cs:g_pfnResultLoggingCallback
0x180004023  test    rax, rax
0x180004026  jz      short loc_18000409B
0x180004028  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000402f  jnz     short loc_18000409B
0x180004031  xor     r8d, r8d
0x180004034  xor     edx, edx
0x180004036  lea     rcx, [rsp+1500h+var_14E0]
0x18000403b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004040  jmp     short loc_18000409B
0x180004042  mov     ebx, 800h
0x180004047  mov     rax, cs:g_pfnResultLoggingCallback
0x18000404e  test    rax, rax
0x180004051  jz      short loc_180004070
0x180004053  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000405a  jnz     short loc_180004070
0x18000405c  mov     r8d, ebx
0x18000405f  lea     rdx, [rbp+1400h+OutputString]
0x180004066  lea     rcx, [rsp+1500h+var_14E0]
0x18000406b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004070  cmp     [rbp+1400h+OutputString], r12w
0x180004078  jnz     short loc_18000408E
0x18000407a  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000407f  mov     rdx, rbx; unsigned __int16 *
0x180004082  lea     rcx, [rbp+1400h+OutputString]; this
0x180004089  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000408e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004095  call    cs:__imp_OutputDebugStringW
0x18000409b  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800040a0  jnz     short loc_1800040AB
0x1800040a2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800040a9  jz      short loc_1800040BD
0x1800040ab  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800040b2  test    rax, rax
0x1800040b5  jz      short loc_1800040BD
0x1800040b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040bc  nop
0x1800040bd  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800040c2  jnz     short loc_1800040E5
0x1800040c4  mov     rcx, [rbp+1400h+var_40]
0x1800040cb  xor     rcx, rsp; StackCookie
0x1800040ce  call    __security_check_cookie
0x1800040d3  add     rsp, 14D0h
0x1800040da  pop     r15
0x1800040dc  pop     r14
0x1800040de  pop     r12
0x1800040e0  pop     rdi
0x1800040e1  pop     rsi
0x1800040e2  pop     rbx
0x1800040e3  pop     rbp
0x1800040e4  retn
0x1800040e5  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800040ea  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800040f0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
