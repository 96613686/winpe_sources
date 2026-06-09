# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002d98`
- end: `0x18000302e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002a60`

## callees

- `0x180002d98`
- `0x180004684`
- `0x180006178`
- `0x180007978`
- `0x180007b88`
- `0x180023c5a`
- `0x180023ca0`
- `0x180023d60`
- `0x180026010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180002e43`
- `KERNEL32!GetCurrentThreadId` at `0x180002e43`
- `KERNEL32!IsDebuggerPresent` at `0x180002f3e`
- `KERNEL32!IsDebuggerPresent` at `0x180002f3e`
- `KERNEL32!OutputDebugStringW` at `0x180002fc8`
- `KERNEL32!OutputDebugStringW` at `0x180002fc8`

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
        int *a7)
{
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString(OutputString, (wchar_t *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x180002d98  mov     [rsp-8+arg_10], rbx
0x180002d9d  push    rbp
0x180002d9e  push    rsi
0x180002d9f  push    rdi
0x180002da0  push    r14
0x180002da2  push    r15
0x180002da4  lea     rbp, [rsp-13D0h]
0x180002dac  mov     eax, 14D0h
0x180002db1  call    _alloca_probe
0x180002db6  sub     rsp, rax
0x180002db9  mov     rax, cs:__security_cookie
0x180002dc0  xor     rax, rsp
0x180002dc3  mov     [rbp+13F0h+var_30], rax
0x180002dca  mov     esi, edx
0x180002dcc  mov     r14, rcx
0x180002dcf  mov     rdi, [rbp+13F0h+arg_28]
0x180002dd6  xor     edx, edx; Val
0x180002dd8  mov     r8d, 98h; Size
0x180002dde  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002de3  call    memset_0
0x180002de8  nop
0x180002de9  xor     r15d, r15d
0x180002dec  mov     [rbp+13F0h+OutputString], r15w
0x180002df4  mov     [rbp+13F0h+var_1430], r15b
0x180002df8  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180002dff  mov     ecx, [rdx]; this
0x180002e01  mov     [rsp+14F0h+var_14C8], ecx
0x180002e05  mov     eax, [rdx+4]
0x180002e08  mov     [rsp+14F0h+var_14C4], eax
0x180002e0c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002e11  mov     ebx, eax
0x180002e13  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180002e1b  mov     ecx, r15d
0x180002e1e  lea     eax, [r15+8]
0x180002e22  cmp     dword ptr [rdx+8], 1
0x180002e26  cmovz   ecx, eax
0x180002e29  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002e2d  lea     ecx, [rax-7]
0x180002e30  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002e38  inc     ecx
0x180002e3a  mov     [rsp+14F0h+var_14C0], ecx
0x180002e3e  mov     [rsp+14F0h+var_14B8], r15
0x180002e43  call    cs:__imp_GetCurrentThreadId
0x180002e49  mov     [rsp+14F0h+var_14B0], eax
0x180002e4d  lea     rax, aWil; "wil"
0x180002e54  mov     [rsp+14F0h+var_1498], rax
0x180002e59  mov     [rsp+14F0h+var_1490], esi
0x180002e5d  mov     [rsp+14F0h+var_148C], ebx
0x180002e61  mov     [rsp+14F0h+var_14A8], r15
0x180002e66  mov     [rsp+14F0h+var_14A0], r15
0x180002e6b  mov     [rbp+13F0h+var_1448], rdi
0x180002e6f  mov     [rbp+13F0h+var_1440], r14
0x180002e73  mov     [rsp+14F0h+var_1488], r15
0x180002e78  xorps   xmm0, xmm0
0x180002e7b  xor     eax, eax
0x180002e7d  movups  [rbp+13F0h+var_1468], xmm0
0x180002e81  mov     [rbp+13F0h+var_1458], rax
0x180002e85  xorps   xmm1, xmm1
0x180002e88  movups  [rsp+14F0h+var_1480], xmm1
0x180002e8d  mov     [rbp+13F0h+var_1470], rax
0x180002e91  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002e98  test    rax, rax
0x180002e9b  jz      short loc_180002EA8
0x180002e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ea2  mov     [rbp+13F0h+var_1450], rax
0x180002ea6  jmp     short loc_180002EAC
0x180002ea8  mov     [rbp+13F0h+var_1450], r15
0x180002eac  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002eb3  test    rax, rax
0x180002eb6  jz      short loc_180002EC2
0x180002eb8  lea     rcx, [rsp+14F0h+var_14D0]
0x180002ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ec2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002ec9  test    rax, rax
0x180002ecc  jz      short loc_180002EE2
0x180002ece  mov     r8d, 400h
0x180002ed4  lea     rdx, [rbp+13F0h+var_1430]
0x180002ed8  lea     rcx, [rsp+14F0h+var_14D0]
0x180002edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ee2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002ee9  test    rax, rax
0x180002eec  jz      short loc_180002EF8
0x180002eee  lea     rcx, [rsp+14F0h+var_14D0]
0x180002ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ef8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002eff  test    rax, rax
0x180002f02  jz      short loc_180002F15
0x180002f04  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002f09  jnz     short loc_180002F15
0x180002f0b  lea     rcx, [rsp+14F0h+var_14D0]
0x180002f10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f15  cmp     [rsp+14F0h+var_14C8], r15d
0x180002f1a  jge     loc_180003028
0x180002f20  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180002f27  jnz     short loc_180002F48
0x180002f29  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002f30  test    rax, rax
0x180002f33  jz      short loc_180002F3E
0x180002f35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f3a  test    al, al
0x180002f3c  jmp     short loc_180002F46
0x180002f3e  call    cs:__imp_IsDebuggerPresent
0x180002f44  test    eax, eax
0x180002f46  jz      short loc_180002F4F
0x180002f48  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002f4d  jz      short loc_180002F75
0x180002f4f  mov     rax, cs:g_pfnResultLoggingCallback
0x180002f56  test    rax, rax
0x180002f59  jz      short loc_180002FCE
0x180002f5b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002f62  jnz     short loc_180002FCE
0x180002f64  xor     r8d, r8d
0x180002f67  xor     edx, edx
0x180002f69  lea     rcx, [rsp+14F0h+var_14D0]
0x180002f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f73  jmp     short loc_180002FCE
0x180002f75  mov     ebx, 800h
0x180002f7a  mov     rax, cs:g_pfnResultLoggingCallback
0x180002f81  test    rax, rax
0x180002f84  jz      short loc_180002FA3
0x180002f86  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002f8d  jnz     short loc_180002FA3
0x180002f8f  mov     r8d, ebx
0x180002f92  lea     rdx, [rbp+13F0h+OutputString]
0x180002f99  lea     rcx, [rsp+14F0h+var_14D0]
0x180002f9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fa3  cmp     [rbp+13F0h+OutputString], r15w
0x180002fab  jnz     short loc_180002FC1
0x180002fad  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002fb2  mov     rdx, rbx; wchar_t *
0x180002fb5  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002fbc  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180002fc1  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002fc8  call    cs:__imp_OutputDebugStringW
0x180002fce  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002fd3  jnz     short loc_180002FDE
0x180002fd5  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180002fdc  jz      short loc_180002FF0
0x180002fde  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002fe5  test    rax, rax
0x180002fe8  jz      short loc_180002FF0
0x180002fea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fef  nop
0x180002ff0  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180002ff5  jnz     short loc_18000301D
0x180002ff7  mov     rcx, [rbp+13F0h+var_30]
0x180002ffe  xor     rcx, rsp; StackCookie
0x180003001  call    __security_check_cookie
0x180003006  mov     rbx, [rsp+14F0h+arg_10]
0x18000300e  add     rsp, 14D0h
0x180003015  pop     r15
0x180003017  pop     r14
0x180003019  pop     rdi
0x18000301a  pop     rsi
0x18000301b  pop     rbp
0x18000301c  retn
0x18000301d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003022  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003028  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
