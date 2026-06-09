# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180007c24`
- end: `0x180007eba`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180007aa8`

## callees

- `0x1800015b0`
- `0x180001fe2`
- `0x180003b44`
- `0x180007928`
- `0x180007990`
- `0x180007a6c`
- `0x180007c24`
- `0x1800094e0`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007ccf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007ccf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007e54`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007e54`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007dca`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007dca`

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
0x180007c24  mov     [rsp-8+arg_10], rbx
0x180007c29  push    rbp
0x180007c2a  push    rsi
0x180007c2b  push    rdi
0x180007c2c  push    r14
0x180007c2e  push    r15
0x180007c30  lea     rbp, [rsp-13D0h]
0x180007c38  mov     eax, 14D0h
0x180007c3d  call    _alloca_probe
0x180007c42  sub     rsp, rax
0x180007c45  mov     rax, cs:__security_cookie
0x180007c4c  xor     rax, rsp
0x180007c4f  mov     [rbp+13F0h+var_30], rax
0x180007c56  mov     esi, edx
0x180007c58  mov     r14, rcx
0x180007c5b  mov     rdi, [rbp+13F0h+arg_28]
0x180007c62  xor     edx, edx; Val
0x180007c64  mov     r8d, 98h; Size
0x180007c6a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180007c6f  call    memset_0
0x180007c74  nop
0x180007c75  xor     r15d, r15d
0x180007c78  mov     [rbp+13F0h+OutputString], r15w
0x180007c80  mov     [rbp+13F0h+var_1430], r15b
0x180007c84  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180007c8b  mov     ecx, [rdx]; this
0x180007c8d  mov     [rsp+14F0h+var_14C8], ecx
0x180007c91  mov     eax, [rdx+4]
0x180007c94  mov     [rsp+14F0h+var_14C4], eax
0x180007c98  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007c9d  mov     ebx, eax
0x180007c9f  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180007ca7  mov     ecx, r15d
0x180007caa  lea     eax, [r15+8]
0x180007cae  cmp     dword ptr [rdx+8], 1
0x180007cb2  cmovz   ecx, eax
0x180007cb5  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180007cb9  lea     ecx, [rax-7]
0x180007cbc  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007cc4  inc     ecx
0x180007cc6  mov     [rsp+14F0h+var_14C0], ecx
0x180007cca  mov     [rsp+14F0h+var_14B8], r15
0x180007ccf  call    cs:__imp_GetCurrentThreadId
0x180007cd5  mov     [rsp+14F0h+var_14B0], eax
0x180007cd9  lea     rax, aWil; "wil"
0x180007ce0  mov     [rsp+14F0h+var_1498], rax
0x180007ce5  mov     [rsp+14F0h+var_1490], esi
0x180007ce9  mov     [rsp+14F0h+var_148C], ebx
0x180007ced  mov     [rsp+14F0h+var_14A8], r15
0x180007cf2  mov     [rsp+14F0h+var_14A0], r15
0x180007cf7  mov     [rbp+13F0h+var_1448], rdi
0x180007cfb  mov     [rbp+13F0h+var_1440], r14
0x180007cff  mov     [rsp+14F0h+var_1488], r15
0x180007d04  xorps   xmm0, xmm0
0x180007d07  xor     eax, eax
0x180007d09  movups  [rbp+13F0h+var_1468], xmm0
0x180007d0d  mov     [rbp+13F0h+var_1458], rax
0x180007d11  xorps   xmm1, xmm1
0x180007d14  movups  [rsp+14F0h+var_1480], xmm1
0x180007d19  mov     [rbp+13F0h+var_1470], rax
0x180007d1d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007d24  test    rax, rax
0x180007d27  jz      short loc_180007D34
0x180007d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d2e  mov     [rbp+13F0h+var_1450], rax
0x180007d32  jmp     short loc_180007D38
0x180007d34  mov     [rbp+13F0h+var_1450], r15
0x180007d38  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007d3f  test    rax, rax
0x180007d42  jz      short loc_180007D4E
0x180007d44  lea     rcx, [rsp+14F0h+var_14D0]
0x180007d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d4e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007d55  test    rax, rax
0x180007d58  jz      short loc_180007D6E
0x180007d5a  mov     r8d, 400h
0x180007d60  lea     rdx, [rbp+13F0h+var_1430]
0x180007d64  lea     rcx, [rsp+14F0h+var_14D0]
0x180007d69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d6e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007d75  test    rax, rax
0x180007d78  jz      short loc_180007D84
0x180007d7a  lea     rcx, [rsp+14F0h+var_14D0]
0x180007d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d84  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007d8b  test    rax, rax
0x180007d8e  jz      short loc_180007DA1
0x180007d90  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007d95  jnz     short loc_180007DA1
0x180007d97  lea     rcx, [rsp+14F0h+var_14D0]
0x180007d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007da1  cmp     [rsp+14F0h+var_14C8], r15d
0x180007da6  jge     loc_180007EB4
0x180007dac  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180007db3  jnz     short loc_180007DD4
0x180007db5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007dbc  test    rax, rax
0x180007dbf  jz      short loc_180007DCA
0x180007dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dc6  test    al, al
0x180007dc8  jmp     short loc_180007DD2
0x180007dca  call    cs:__imp_IsDebuggerPresent
0x180007dd0  test    eax, eax
0x180007dd2  jz      short loc_180007DDB
0x180007dd4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007dd9  jz      short loc_180007E01
0x180007ddb  mov     rax, cs:g_pfnResultLoggingCallback
0x180007de2  test    rax, rax
0x180007de5  jz      short loc_180007E5A
0x180007de7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180007dee  jnz     short loc_180007E5A
0x180007df0  xor     r8d, r8d
0x180007df3  xor     edx, edx
0x180007df5  lea     rcx, [rsp+14F0h+var_14D0]
0x180007dfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dff  jmp     short loc_180007E5A
0x180007e01  mov     ebx, 800h
0x180007e06  mov     rax, cs:g_pfnResultLoggingCallback
0x180007e0d  test    rax, rax
0x180007e10  jz      short loc_180007E2F
0x180007e12  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180007e19  jnz     short loc_180007E2F
0x180007e1b  mov     r8d, ebx
0x180007e1e  lea     rdx, [rbp+13F0h+OutputString]
0x180007e25  lea     rcx, [rsp+14F0h+var_14D0]
0x180007e2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e2f  cmp     [rbp+13F0h+OutputString], r15w
0x180007e37  jnz     short loc_180007E4D
0x180007e39  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180007e3e  mov     rdx, rbx; unsigned __int16 *
0x180007e41  lea     rcx, [rbp+13F0h+OutputString]; this
0x180007e48  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007e4d  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180007e54  call    cs:__imp_OutputDebugStringW
0x180007e5a  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180007e5f  jnz     short loc_180007E6A
0x180007e61  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180007e68  jz      short loc_180007E7C
0x180007e6a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007e71  test    rax, rax
0x180007e74  jz      short loc_180007E7C
0x180007e76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e7b  nop
0x180007e7c  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180007e81  jnz     short loc_180007EA9
0x180007e83  mov     rcx, [rbp+13F0h+var_30]
0x180007e8a  xor     rcx, rsp; StackCookie
0x180007e8d  call    __security_check_cookie
0x180007e92  mov     rbx, [rsp+14F0h+arg_10]
0x180007e9a  add     rsp, 14D0h
0x180007ea1  pop     r15
0x180007ea3  pop     r14
0x180007ea5  pop     rdi
0x180007ea6  pop     rsi
0x180007ea7  pop     rbp
0x180007ea8  retn
0x180007ea9  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180007eae  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180007eb4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
