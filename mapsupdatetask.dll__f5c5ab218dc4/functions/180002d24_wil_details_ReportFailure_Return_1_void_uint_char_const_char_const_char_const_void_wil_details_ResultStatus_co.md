# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002d24`
- end: `0x180002fba`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000280c`

## callees

- `0x180001be0`
- `0x180002612`
- `0x180002d24`
- `0x180004534`
- `0x1800057a0`
- `0x180007210`
- `0x1800075d4`
- `0x180007e70`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002dcf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002dcf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002f54`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002f54`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002eca`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002eca`

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
0x180002d24  mov     [rsp-8+arg_10], rbx
0x180002d29  push    rbp
0x180002d2a  push    rsi
0x180002d2b  push    rdi
0x180002d2c  push    r14
0x180002d2e  push    r15
0x180002d30  lea     rbp, [rsp-13D0h]
0x180002d38  mov     eax, 14D0h
0x180002d3d  call    _alloca_probe
0x180002d42  sub     rsp, rax
0x180002d45  mov     rax, cs:__security_cookie
0x180002d4c  xor     rax, rsp
0x180002d4f  mov     [rbp+13F0h+var_30], rax
0x180002d56  mov     esi, edx
0x180002d58  mov     r14, rcx
0x180002d5b  mov     rdi, [rbp+13F0h+arg_28]
0x180002d62  xor     edx, edx; Val
0x180002d64  mov     r8d, 98h; Size
0x180002d6a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002d6f  call    memset_0
0x180002d74  nop
0x180002d75  xor     r15d, r15d
0x180002d78  mov     [rbp+13F0h+OutputString], r15w
0x180002d80  mov     [rbp+13F0h+var_1430], r15b
0x180002d84  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180002d8b  mov     ecx, [rdx]; this
0x180002d8d  mov     [rsp+14F0h+var_14C8], ecx
0x180002d91  mov     eax, [rdx+4]
0x180002d94  mov     [rsp+14F0h+var_14C4], eax
0x180002d98  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002d9d  mov     ebx, eax
0x180002d9f  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180002da7  mov     ecx, r15d
0x180002daa  lea     eax, [r15+8]
0x180002dae  cmp     dword ptr [rdx+8], 1
0x180002db2  cmovz   ecx, eax
0x180002db5  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002db9  lea     ecx, [rax-7]
0x180002dbc  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002dc4  inc     ecx
0x180002dc6  mov     [rsp+14F0h+var_14C0], ecx
0x180002dca  mov     [rsp+14F0h+var_14B8], r15
0x180002dcf  call    cs:__imp_GetCurrentThreadId
0x180002dd5  mov     [rsp+14F0h+var_14B0], eax
0x180002dd9  lea     rax, aWil; "wil"
0x180002de0  mov     [rsp+14F0h+var_1498], rax
0x180002de5  mov     [rsp+14F0h+var_1490], esi
0x180002de9  mov     [rsp+14F0h+var_148C], ebx
0x180002ded  mov     [rsp+14F0h+var_14A8], r15
0x180002df2  mov     [rsp+14F0h+var_14A0], r15
0x180002df7  mov     [rbp+13F0h+var_1448], rdi
0x180002dfb  mov     [rbp+13F0h+var_1440], r14
0x180002dff  mov     [rsp+14F0h+var_1488], r15
0x180002e04  xorps   xmm0, xmm0
0x180002e07  xor     eax, eax
0x180002e09  movups  [rbp+13F0h+var_1468], xmm0
0x180002e0d  mov     [rbp+13F0h+var_1458], rax
0x180002e11  xorps   xmm1, xmm1
0x180002e14  movups  [rsp+14F0h+var_1480], xmm1
0x180002e19  mov     [rbp+13F0h+var_1470], rax
0x180002e1d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002e24  test    rax, rax
0x180002e27  jz      short loc_180002E34
0x180002e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e2e  mov     [rbp+13F0h+var_1450], rax
0x180002e32  jmp     short loc_180002E38
0x180002e34  mov     [rbp+13F0h+var_1450], r15
0x180002e38  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002e3f  test    rax, rax
0x180002e42  jz      short loc_180002E4E
0x180002e44  lea     rcx, [rsp+14F0h+var_14D0]
0x180002e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e4e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002e55  test    rax, rax
0x180002e58  jz      short loc_180002E6E
0x180002e5a  mov     r8d, 400h
0x180002e60  lea     rdx, [rbp+13F0h+var_1430]
0x180002e64  lea     rcx, [rsp+14F0h+var_14D0]
0x180002e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e6e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002e75  test    rax, rax
0x180002e78  jz      short loc_180002E84
0x180002e7a  lea     rcx, [rsp+14F0h+var_14D0]
0x180002e7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e84  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002e8b  test    rax, rax
0x180002e8e  jz      short loc_180002EA1
0x180002e90  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002e95  jnz     short loc_180002EA1
0x180002e97  lea     rcx, [rsp+14F0h+var_14D0]
0x180002e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ea1  cmp     [rsp+14F0h+var_14C8], r15d
0x180002ea6  jge     loc_180002FB4
0x180002eac  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180002eb3  jnz     short loc_180002ED4
0x180002eb5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002ebc  test    rax, rax
0x180002ebf  jz      short loc_180002ECA
0x180002ec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ec6  test    al, al
0x180002ec8  jmp     short loc_180002ED2
0x180002eca  call    cs:__imp_IsDebuggerPresent
0x180002ed0  test    eax, eax
0x180002ed2  jz      short loc_180002EDB
0x180002ed4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002ed9  jz      short loc_180002F01
0x180002edb  mov     rax, cs:g_pfnResultLoggingCallback
0x180002ee2  test    rax, rax
0x180002ee5  jz      short loc_180002F5A
0x180002ee7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002eee  jnz     short loc_180002F5A
0x180002ef0  xor     r8d, r8d
0x180002ef3  xor     edx, edx
0x180002ef5  lea     rcx, [rsp+14F0h+var_14D0]
0x180002efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002eff  jmp     short loc_180002F5A
0x180002f01  mov     ebx, 800h
0x180002f06  mov     rax, cs:g_pfnResultLoggingCallback
0x180002f0d  test    rax, rax
0x180002f10  jz      short loc_180002F2F
0x180002f12  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002f19  jnz     short loc_180002F2F
0x180002f1b  mov     r8d, ebx
0x180002f1e  lea     rdx, [rbp+13F0h+OutputString]
0x180002f25  lea     rcx, [rsp+14F0h+var_14D0]
0x180002f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f2f  cmp     [rbp+13F0h+OutputString], r15w
0x180002f37  jnz     short loc_180002F4D
0x180002f39  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002f3e  mov     rdx, rbx; unsigned __int16 *
0x180002f41  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002f48  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002f4d  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002f54  call    cs:__imp_OutputDebugStringW
0x180002f5a  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002f5f  jnz     short loc_180002F6A
0x180002f61  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180002f68  jz      short loc_180002F7C
0x180002f6a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002f71  test    rax, rax
0x180002f74  jz      short loc_180002F7C
0x180002f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f7b  nop
0x180002f7c  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180002f81  jnz     short loc_180002FA9
0x180002f83  mov     rcx, [rbp+13F0h+var_30]
0x180002f8a  xor     rcx, rsp; StackCookie
0x180002f8d  call    __security_check_cookie
0x180002f92  mov     rbx, [rsp+14F0h+arg_10]
0x180002f9a  add     rsp, 14D0h
0x180002fa1  pop     r15
0x180002fa3  pop     r14
0x180002fa5  pop     rdi
0x180002fa6  pop     rsi
0x180002fa7  pop     rbp
0x180002fa8  retn
0x180002fa9  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002fae  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180002fb4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
