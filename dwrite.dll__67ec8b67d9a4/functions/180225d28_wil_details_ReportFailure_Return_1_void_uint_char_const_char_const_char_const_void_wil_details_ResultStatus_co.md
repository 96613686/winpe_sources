# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180225d28`
- end: `0x180225fb5`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180210c2c`

## callees

- `0x180212490`
- `0x180212f4c`
- `0x180225390`
- `0x180225d28`
- `0x1802272b4`
- `0x180228898`
- `0x180229ec8`
- `0x18022a110`
- `0x180330010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180225dd6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180225dd6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180225eca`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180225eca`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180225f54`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180225f54`

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
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v19, (int)a7);
  v17 = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v18 = v11;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v10;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString(OutputString, (wchar_t *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( ((v18 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v18 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x180225d28  push    rbp
0x180225d2a  push    rbx
0x180225d2b  push    rsi
0x180225d2c  push    rdi
0x180225d2d  push    r12
0x180225d2f  push    r14
0x180225d31  push    r15
0x180225d33  lea     rbp, [rsp-13D0h]
0x180225d3b  mov     eax, 14D0h
0x180225d40  call    _alloca_probe
0x180225d45  sub     rsp, rax
0x180225d48  mov     rax, cs:__security_cookie
0x180225d4f  xor     rax, rsp
0x180225d52  mov     [rbp+1400h+var_40], rax
0x180225d59  mov     r14, r8
0x180225d5c  mov     esi, edx
0x180225d5e  mov     r15, rcx
0x180225d61  mov     rdi, [rbp+1400h+arg_28]
0x180225d68  xor     edx, edx; Val
0x180225d6a  mov     r8d, 98h; Size
0x180225d70  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180225d75  call    memset_0
0x180225d7a  nop
0x180225d7b  xor     r12d, r12d
0x180225d7e  mov     [rbp+1400h+OutputString], r12w
0x180225d86  mov     [rbp+1400h+var_1440], r12b
0x180225d8a  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180225d91  mov     ecx, [rdx]; this
0x180225d93  mov     [rsp+1500h+var_14D8], ecx
0x180225d97  mov     eax, [rdx+4]
0x180225d9a  mov     [rsp+1500h+var_14D4], eax
0x180225d9e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180225da3  mov     ebx, eax
0x180225da5  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180225dad  mov     ecx, r12d
0x180225db0  lea     eax, [r12+8]
0x180225db5  cmp     dword ptr [rdx+8], 1
0x180225db9  cmovz   ecx, eax
0x180225dbc  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180225dc0  lea     ecx, [rax-7]
0x180225dc3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180225dcb  inc     ecx
0x180225dcd  mov     [rsp+1500h+var_14D0], ecx
0x180225dd1  mov     [rsp+1500h+var_14C8], r12
0x180225dd6  call    cs:__imp_GetCurrentThreadId
0x180225ddc  mov     [rsp+1500h+var_14C0], eax
0x180225de0  mov     [rsp+1500h+var_14A8], r14
0x180225de5  mov     [rsp+1500h+var_14A0], esi
0x180225de9  mov     [rsp+1500h+var_149C], ebx
0x180225ded  mov     [rsp+1500h+var_14B8], r12
0x180225df2  mov     [rsp+1500h+var_14B0], r12
0x180225df7  mov     [rbp+1400h+var_1458], rdi
0x180225dfb  mov     [rbp+1400h+var_1450], r15
0x180225dff  mov     [rsp+1500h+var_1498], r12
0x180225e04  xorps   xmm0, xmm0
0x180225e07  xor     eax, eax
0x180225e09  movups  [rbp+1400h+var_1478], xmm0
0x180225e0d  mov     [rbp+1400h+var_1468], rax
0x180225e11  xorps   xmm1, xmm1
0x180225e14  movups  [rsp+1500h+var_1490], xmm1
0x180225e19  mov     [rbp+1400h+var_1480], rax
0x180225e1d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180225e24  test    rax, rax
0x180225e27  jz      short loc_180225E34
0x180225e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180225e2e  mov     [rbp+1400h+var_1460], rax
0x180225e32  jmp     short loc_180225E38
0x180225e34  mov     [rbp+1400h+var_1460], r12
0x180225e38  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180225e3f  test    rax, rax
0x180225e42  jz      short loc_180225E4E
0x180225e44  lea     rcx, [rsp+1500h+var_14E0]
0x180225e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180225e4e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180225e55  test    rax, rax
0x180225e58  jz      short loc_180225E6E
0x180225e5a  mov     r8d, 400h
0x180225e60  lea     rdx, [rbp+1400h+var_1440]
0x180225e64  lea     rcx, [rsp+1500h+var_14E0]
0x180225e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180225e6e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180225e75  test    rax, rax
0x180225e78  jz      short loc_180225E84
0x180225e7a  lea     rcx, [rsp+1500h+var_14E0]
0x180225e7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180225e84  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180225e8b  test    rax, rax
0x180225e8e  jz      short loc_180225EA1
0x180225e90  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180225e95  jnz     short loc_180225EA1
0x180225e97  lea     rcx, [rsp+1500h+var_14E0]
0x180225e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180225ea1  cmp     [rsp+1500h+var_14D8], r12d
0x180225ea6  jge     loc_180225FAF
0x180225eac  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180225eb3  jnz     short loc_180225ED4
0x180225eb5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180225ebc  test    rax, rax
0x180225ebf  jz      short loc_180225ECA
0x180225ec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180225ec6  test    al, al
0x180225ec8  jmp     short loc_180225ED2
0x180225eca  call    cs:__imp_IsDebuggerPresent
0x180225ed0  test    eax, eax
0x180225ed2  jz      short loc_180225EDB
0x180225ed4  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180225ed9  jz      short loc_180225F01
0x180225edb  mov     rax, cs:g_pfnResultLoggingCallback
0x180225ee2  test    rax, rax
0x180225ee5  jz      short loc_180225F5A
0x180225ee7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180225eee  jnz     short loc_180225F5A
0x180225ef0  xor     r8d, r8d
0x180225ef3  xor     edx, edx
0x180225ef5  lea     rcx, [rsp+1500h+var_14E0]
0x180225efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180225eff  jmp     short loc_180225F5A
0x180225f01  mov     ebx, 800h
0x180225f06  mov     rax, cs:g_pfnResultLoggingCallback
0x180225f0d  test    rax, rax
0x180225f10  jz      short loc_180225F2F
0x180225f12  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180225f19  jnz     short loc_180225F2F
0x180225f1b  mov     r8d, ebx
0x180225f1e  lea     rdx, [rbp+1400h+OutputString]
0x180225f25  lea     rcx, [rsp+1500h+var_14E0]
0x180225f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180225f2f  cmp     [rbp+1400h+OutputString], r12w
0x180225f37  jnz     short loc_180225F4D
0x180225f39  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180225f3e  mov     rdx, rbx; wchar_t *
0x180225f41  lea     rcx, [rbp+1400h+OutputString]; pszDest
0x180225f48  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180225f4d  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180225f54  call    cs:__imp_OutputDebugStringW
0x180225f5a  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180225f5f  jnz     short loc_180225F6A
0x180225f61  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180225f68  jz      short loc_180225F7C
0x180225f6a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180225f71  test    rax, rax
0x180225f74  jz      short loc_180225F7C
0x180225f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180225f7b  nop
0x180225f7c  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180225f81  jnz     short loc_180225FA4
0x180225f83  mov     rcx, [rbp+1400h+var_40]
0x180225f8a  xor     rcx, rsp; StackCookie
0x180225f8d  call    __security_check_cookie
0x180225f92  add     rsp, 14D0h
0x180225f99  pop     r15
0x180225f9b  pop     r14
0x180225f9d  pop     r12
0x180225f9f  pop     rdi
0x180225fa0  pop     rsi
0x180225fa1  pop     rbx
0x180225fa2  pop     rbp
0x180225fa3  retn
0x180225fa4  lea     rcx, [rsp+1500h+var_14E0]; this
0x180225fa9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180225faf  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
