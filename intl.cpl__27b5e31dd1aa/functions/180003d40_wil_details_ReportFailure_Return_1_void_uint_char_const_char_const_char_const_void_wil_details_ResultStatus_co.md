# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003d40`
- end: `0x180003fd6`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003a04`

## callees

- `0x180003d40`
- `0x180004ba4`
- `0x180005c00`
- `0x1800066e8`
- `0x180006984`
- `0x18002a112`
- `0x18002a150`
- `0x18002a210`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003deb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003deb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003f70`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003f70`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003ee6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003ee6`

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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
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
0x180003d40  mov     [rsp-8+arg_10], rbx
0x180003d45  push    rbp
0x180003d46  push    rsi
0x180003d47  push    rdi
0x180003d48  push    r14
0x180003d4a  push    r15
0x180003d4c  lea     rbp, [rsp-13D0h]
0x180003d54  mov     eax, 14D0h
0x180003d59  call    _alloca_probe
0x180003d5e  sub     rsp, rax
0x180003d61  mov     rax, cs:__security_cookie
0x180003d68  xor     rax, rsp
0x180003d6b  mov     [rbp+13F0h+var_30], rax
0x180003d72  mov     esi, edx
0x180003d74  mov     r14, rcx
0x180003d77  mov     rdi, [rbp+13F0h+arg_28]
0x180003d7e  xor     edx, edx; Val
0x180003d80  mov     r8d, 98h; Size
0x180003d86  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003d8b  call    memset_0
0x180003d90  nop
0x180003d91  xor     r15d, r15d
0x180003d94  mov     [rbp+13F0h+OutputString], r15w
0x180003d9c  mov     [rbp+13F0h+var_1430], r15b
0x180003da0  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180003da7  mov     ecx, [rdx]; this
0x180003da9  mov     [rsp+14F0h+var_14C8], ecx
0x180003dad  mov     eax, [rdx+4]
0x180003db0  mov     [rsp+14F0h+var_14C4], eax
0x180003db4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003db9  mov     ebx, eax
0x180003dbb  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180003dc3  mov     ecx, r15d
0x180003dc6  lea     eax, [r15+8]
0x180003dca  cmp     dword ptr [rdx+8], 1
0x180003dce  cmovz   ecx, eax
0x180003dd1  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003dd5  lea     ecx, [rax-7]
0x180003dd8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003de0  inc     ecx
0x180003de2  mov     [rsp+14F0h+var_14C0], ecx
0x180003de6  mov     [rsp+14F0h+var_14B8], r15
0x180003deb  call    cs:__imp_GetCurrentThreadId
0x180003df1  mov     [rsp+14F0h+var_14B0], eax
0x180003df5  lea     rax, aWil; "wil"
0x180003dfc  mov     [rsp+14F0h+var_1498], rax
0x180003e01  mov     [rsp+14F0h+var_1490], esi
0x180003e05  mov     [rsp+14F0h+var_148C], ebx
0x180003e09  mov     [rsp+14F0h+var_14A8], r15
0x180003e0e  mov     [rsp+14F0h+var_14A0], r15
0x180003e13  mov     [rbp+13F0h+var_1448], rdi
0x180003e17  mov     [rbp+13F0h+var_1440], r14
0x180003e1b  mov     [rsp+14F0h+var_1488], r15
0x180003e20  xorps   xmm0, xmm0
0x180003e23  xor     eax, eax
0x180003e25  movups  [rbp+13F0h+var_1468], xmm0
0x180003e29  mov     [rbp+13F0h+var_1458], rax
0x180003e2d  xorps   xmm1, xmm1
0x180003e30  movups  [rsp+14F0h+var_1480], xmm1
0x180003e35  mov     [rbp+13F0h+var_1470], rax
0x180003e39  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003e40  test    rax, rax
0x180003e43  jz      short loc_180003E50
0x180003e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e4a  mov     [rbp+13F0h+var_1450], rax
0x180003e4e  jmp     short loc_180003E54
0x180003e50  mov     [rbp+13F0h+var_1450], r15
0x180003e54  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003e5b  test    rax, rax
0x180003e5e  jz      short loc_180003E6A
0x180003e60  lea     rcx, [rsp+14F0h+var_14D0]
0x180003e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e6a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003e71  test    rax, rax
0x180003e74  jz      short loc_180003E8A
0x180003e76  mov     r8d, 400h
0x180003e7c  lea     rdx, [rbp+13F0h+var_1430]
0x180003e80  lea     rcx, [rsp+14F0h+var_14D0]
0x180003e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e8a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003e91  test    rax, rax
0x180003e94  jz      short loc_180003EA0
0x180003e96  lea     rcx, [rsp+14F0h+var_14D0]
0x180003e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ea0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003ea7  test    rax, rax
0x180003eaa  jz      short loc_180003EBD
0x180003eac  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003eb1  jnz     short loc_180003EBD
0x180003eb3  lea     rcx, [rsp+14F0h+var_14D0]
0x180003eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ebd  cmp     [rsp+14F0h+var_14C8], r15d
0x180003ec2  jge     loc_180003FD0
0x180003ec8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180003ecf  jnz     short loc_180003EF0
0x180003ed1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003ed8  test    rax, rax
0x180003edb  jz      short loc_180003EE6
0x180003edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ee2  test    al, al
0x180003ee4  jmp     short loc_180003EEE
0x180003ee6  call    cs:__imp_IsDebuggerPresent
0x180003eec  test    eax, eax
0x180003eee  jz      short loc_180003EF7
0x180003ef0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003ef5  jz      short loc_180003F1D
0x180003ef7  mov     rax, cs:g_pfnResultLoggingCallback
0x180003efe  test    rax, rax
0x180003f01  jz      short loc_180003F76
0x180003f03  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003f0a  jnz     short loc_180003F76
0x180003f0c  xor     r8d, r8d
0x180003f0f  xor     edx, edx
0x180003f11  lea     rcx, [rsp+14F0h+var_14D0]
0x180003f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f1b  jmp     short loc_180003F76
0x180003f1d  mov     ebx, 800h
0x180003f22  mov     rax, cs:g_pfnResultLoggingCallback
0x180003f29  test    rax, rax
0x180003f2c  jz      short loc_180003F4B
0x180003f2e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003f35  jnz     short loc_180003F4B
0x180003f37  mov     r8d, ebx
0x180003f3a  lea     rdx, [rbp+13F0h+OutputString]
0x180003f41  lea     rcx, [rsp+14F0h+var_14D0]
0x180003f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f4b  cmp     [rbp+13F0h+OutputString], r15w
0x180003f53  jnz     short loc_180003F69
0x180003f55  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003f5a  mov     rdx, rbx; unsigned __int16 *
0x180003f5d  lea     rcx, [rbp+13F0h+OutputString]; this
0x180003f64  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003f69  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003f70  call    cs:__imp_OutputDebugStringW
0x180003f76  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003f7b  jnz     short loc_180003F86
0x180003f7d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180003f84  jz      short loc_180003F98
0x180003f86  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003f8d  test    rax, rax
0x180003f90  jz      short loc_180003F98
0x180003f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f97  nop
0x180003f98  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180003f9d  jnz     short loc_180003FC5
0x180003f9f  mov     rcx, [rbp+13F0h+var_30]
0x180003fa6  xor     rcx, rsp; StackCookie
0x180003fa9  call    __security_check_cookie
0x180003fae  mov     rbx, [rsp+14F0h+arg_10]
0x180003fb6  add     rsp, 14D0h
0x180003fbd  pop     r15
0x180003fbf  pop     r14
0x180003fc1  pop     rdi
0x180003fc2  pop     rsi
0x180003fc3  pop     rbp
0x180003fc4  retn
0x180003fc5  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003fca  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003fd0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
