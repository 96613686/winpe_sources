# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180005d10`
- end: `0x180005fa6`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180005818`

## callees

- `0x180001710`
- `0x180002320`
- `0x1800032c4`
- `0x180005d10`
- `0x1800140bc`
- `0x18001871c`
- `0x1800189ec`
- `0x180034d90`
- `0x180036010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180005eb6`
- `KERNEL32!IsDebuggerPresent` at `0x180005eb6`
- `KERNEL32!OutputDebugStringW` at `0x180005f40`
- `KERNEL32!OutputDebugStringW` at `0x180005f40`
- `KERNEL32!GetCurrentThreadId` at `0x180005dbb`
- `KERNEL32!GetCurrentThreadId` at `0x180005dbb`

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
0x180005d10  mov     [rsp-8+arg_10], rbx
0x180005d15  push    rbp
0x180005d16  push    rsi
0x180005d17  push    rdi
0x180005d18  push    r14
0x180005d1a  push    r15
0x180005d1c  lea     rbp, [rsp-13D0h]
0x180005d24  mov     eax, 14D0h
0x180005d29  call    _alloca_probe
0x180005d2e  sub     rsp, rax
0x180005d31  mov     rax, cs:__security_cookie
0x180005d38  xor     rax, rsp
0x180005d3b  mov     [rbp+13F0h+var_30], rax
0x180005d42  mov     esi, edx
0x180005d44  mov     r14, rcx
0x180005d47  mov     rdi, [rbp+13F0h+arg_28]
0x180005d4e  xor     edx, edx; Val
0x180005d50  mov     r8d, 98h; Size
0x180005d56  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180005d5b  call    memset_0
0x180005d60  nop
0x180005d61  xor     r15d, r15d
0x180005d64  mov     [rbp+13F0h+OutputString], r15w
0x180005d6c  mov     [rbp+13F0h+var_1430], r15b
0x180005d70  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180005d77  mov     ecx, [rdx]; this
0x180005d79  mov     [rsp+14F0h+var_14C8], ecx
0x180005d7d  mov     eax, [rdx+4]
0x180005d80  mov     [rsp+14F0h+var_14C4], eax
0x180005d84  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005d89  mov     ebx, eax
0x180005d8b  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180005d93  mov     ecx, r15d
0x180005d96  lea     eax, [r15+8]
0x180005d9a  cmp     dword ptr [rdx+8], 1
0x180005d9e  cmovz   ecx, eax
0x180005da1  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180005da5  lea     ecx, [rax-7]
0x180005da8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005db0  inc     ecx
0x180005db2  mov     [rsp+14F0h+var_14C0], ecx
0x180005db6  mov     [rsp+14F0h+var_14B8], r15
0x180005dbb  call    cs:__imp_GetCurrentThreadId
0x180005dc1  mov     [rsp+14F0h+var_14B0], eax
0x180005dc5  lea     rax, aWil; "wil"
0x180005dcc  mov     [rsp+14F0h+var_1498], rax
0x180005dd1  mov     [rsp+14F0h+var_1490], esi
0x180005dd5  mov     [rsp+14F0h+var_148C], ebx
0x180005dd9  mov     [rsp+14F0h+var_14A8], r15
0x180005dde  mov     [rsp+14F0h+var_14A0], r15
0x180005de3  mov     [rbp+13F0h+var_1448], rdi
0x180005de7  mov     [rbp+13F0h+var_1440], r14
0x180005deb  mov     [rsp+14F0h+var_1488], r15
0x180005df0  xorps   xmm0, xmm0
0x180005df3  xor     eax, eax
0x180005df5  movups  [rbp+13F0h+var_1468], xmm0
0x180005df9  mov     [rbp+13F0h+var_1458], rax
0x180005dfd  xorps   xmm1, xmm1
0x180005e00  movups  [rsp+14F0h+var_1480], xmm1
0x180005e05  mov     [rbp+13F0h+var_1470], rax
0x180005e09  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005e10  test    rax, rax
0x180005e13  jz      short loc_180005E20
0x180005e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e1a  mov     [rbp+13F0h+var_1450], rax
0x180005e1e  jmp     short loc_180005E24
0x180005e20  mov     [rbp+13F0h+var_1450], r15
0x180005e24  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005e2b  test    rax, rax
0x180005e2e  jz      short loc_180005E3A
0x180005e30  lea     rcx, [rsp+14F0h+var_14D0]
0x180005e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e3a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005e41  test    rax, rax
0x180005e44  jz      short loc_180005E5A
0x180005e46  mov     r8d, 400h
0x180005e4c  lea     rdx, [rbp+13F0h+var_1430]
0x180005e50  lea     rcx, [rsp+14F0h+var_14D0]
0x180005e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e5a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005e61  test    rax, rax
0x180005e64  jz      short loc_180005E70
0x180005e66  lea     rcx, [rsp+14F0h+var_14D0]
0x180005e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e70  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005e77  test    rax, rax
0x180005e7a  jz      short loc_180005E8D
0x180005e7c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005e81  jnz     short loc_180005E8D
0x180005e83  lea     rcx, [rsp+14F0h+var_14D0]
0x180005e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e8d  cmp     [rsp+14F0h+var_14C8], r15d
0x180005e92  jge     loc_180005FA0
0x180005e98  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180005e9f  jnz     short loc_180005EC0
0x180005ea1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005ea8  test    rax, rax
0x180005eab  jz      short loc_180005EB6
0x180005ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eb2  test    al, al
0x180005eb4  jmp     short loc_180005EBE
0x180005eb6  call    cs:__imp_IsDebuggerPresent
0x180005ebc  test    eax, eax
0x180005ebe  jz      short loc_180005EC7
0x180005ec0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005ec5  jz      short loc_180005EED
0x180005ec7  mov     rax, cs:g_pfnResultLoggingCallback
0x180005ece  test    rax, rax
0x180005ed1  jz      short loc_180005F46
0x180005ed3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005eda  jnz     short loc_180005F46
0x180005edc  xor     r8d, r8d
0x180005edf  xor     edx, edx
0x180005ee1  lea     rcx, [rsp+14F0h+var_14D0]
0x180005ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eeb  jmp     short loc_180005F46
0x180005eed  mov     ebx, 800h
0x180005ef2  mov     rax, cs:g_pfnResultLoggingCallback
0x180005ef9  test    rax, rax
0x180005efc  jz      short loc_180005F1B
0x180005efe  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005f05  jnz     short loc_180005F1B
0x180005f07  mov     r8d, ebx
0x180005f0a  lea     rdx, [rbp+13F0h+OutputString]
0x180005f11  lea     rcx, [rsp+14F0h+var_14D0]
0x180005f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f1b  cmp     [rbp+13F0h+OutputString], r15w
0x180005f23  jnz     short loc_180005F39
0x180005f25  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180005f2a  mov     rdx, rbx; unsigned __int16 *
0x180005f2d  lea     rcx, [rbp+13F0h+OutputString]; this
0x180005f34  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005f39  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180005f40  call    cs:__imp_OutputDebugStringW
0x180005f46  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180005f4b  jnz     short loc_180005F56
0x180005f4d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180005f54  jz      short loc_180005F68
0x180005f56  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005f5d  test    rax, rax
0x180005f60  jz      short loc_180005F68
0x180005f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f67  nop
0x180005f68  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180005f6d  jnz     short loc_180005F95
0x180005f6f  mov     rcx, [rbp+13F0h+var_30]
0x180005f76  xor     rcx, rsp; StackCookie
0x180005f79  call    __security_check_cookie
0x180005f7e  mov     rbx, [rsp+14F0h+arg_10]
0x180005f86  add     rsp, 14D0h
0x180005f8d  pop     r15
0x180005f8f  pop     r14
0x180005f91  pop     rdi
0x180005f92  pop     rsi
0x180005f93  pop     rbp
0x180005f94  retn
0x180005f95  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005f9a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005fa0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
