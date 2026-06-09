# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000d16c`
- end: `0x18000d3f9`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000d05c`

## callees

- `0x180002890`
- `0x180003474`
- `0x180005804`
- `0x180006f90`
- `0x18000d16c`
- `0x18000e2f0`
- `0x18000e5f8`
- `0x180049280`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d21a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d21a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000d398`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000d398`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d30e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d30e`

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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v17, v15);
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
0x18000d16c  push    rbp
0x18000d16e  push    rbx
0x18000d16f  push    rsi
0x18000d170  push    rdi
0x18000d171  push    r12
0x18000d173  push    r14
0x18000d175  push    r15
0x18000d177  lea     rbp, [rsp-13D0h]
0x18000d17f  mov     eax, 14D0h
0x18000d184  call    _alloca_probe
0x18000d189  sub     rsp, rax
0x18000d18c  mov     rax, cs:__security_cookie
0x18000d193  xor     rax, rsp
0x18000d196  mov     [rbp+1400h+var_40], rax
0x18000d19d  mov     r14, r8
0x18000d1a0  mov     esi, edx
0x18000d1a2  mov     r15, rcx
0x18000d1a5  mov     rdi, [rbp+1400h+arg_28]
0x18000d1ac  xor     edx, edx; Val
0x18000d1ae  mov     r8d, 98h; Size
0x18000d1b4  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000d1b9  call    memset_0
0x18000d1be  nop
0x18000d1bf  xor     r12d, r12d
0x18000d1c2  mov     [rbp+1400h+OutputString], r12w
0x18000d1ca  mov     [rbp+1400h+var_1440], r12b
0x18000d1ce  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18000d1d5  mov     ecx, [rdx]; this
0x18000d1d7  mov     [rsp+1500h+var_14D8], ecx
0x18000d1db  mov     eax, [rdx+4]
0x18000d1de  mov     [rsp+1500h+var_14D4], eax
0x18000d1e2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000d1e7  mov     ebx, eax
0x18000d1e9  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000d1f1  mov     ecx, r12d
0x18000d1f4  lea     eax, [r12+8]
0x18000d1f9  cmp     dword ptr [rdx+8], 1
0x18000d1fd  cmovz   ecx, eax
0x18000d200  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000d204  lea     ecx, [rax-7]
0x18000d207  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000d20f  inc     ecx
0x18000d211  mov     [rsp+1500h+var_14D0], ecx
0x18000d215  mov     [rsp+1500h+var_14C8], r12
0x18000d21a  call    cs:__imp_GetCurrentThreadId
0x18000d220  mov     [rsp+1500h+var_14C0], eax
0x18000d224  mov     [rsp+1500h+var_14A8], r14
0x18000d229  mov     [rsp+1500h+var_14A0], esi
0x18000d22d  mov     [rsp+1500h+var_149C], ebx
0x18000d231  mov     [rsp+1500h+var_14B8], r12
0x18000d236  mov     [rsp+1500h+var_14B0], r12
0x18000d23b  mov     [rbp+1400h+var_1458], rdi
0x18000d23f  mov     [rbp+1400h+var_1450], r15
0x18000d243  mov     [rsp+1500h+var_1498], r12
0x18000d248  xorps   xmm0, xmm0
0x18000d24b  xor     eax, eax
0x18000d24d  movups  [rbp+1400h+var_1478], xmm0
0x18000d251  mov     [rbp+1400h+var_1468], rax
0x18000d255  xorps   xmm1, xmm1
0x18000d258  movups  [rsp+1500h+var_1490], xmm1
0x18000d25d  mov     [rbp+1400h+var_1480], rax
0x18000d261  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000d268  test    rax, rax
0x18000d26b  jz      short loc_18000D278
0x18000d26d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d272  mov     [rbp+1400h+var_1460], rax
0x18000d276  jmp     short loc_18000D27C
0x18000d278  mov     [rbp+1400h+var_1460], r12
0x18000d27c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000d283  test    rax, rax
0x18000d286  jz      short loc_18000D292
0x18000d288  lea     rcx, [rsp+1500h+var_14E0]
0x18000d28d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d292  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000d299  test    rax, rax
0x18000d29c  jz      short loc_18000D2B2
0x18000d29e  mov     r8d, 400h
0x18000d2a4  lea     rdx, [rbp+1400h+var_1440]
0x18000d2a8  lea     rcx, [rsp+1500h+var_14E0]
0x18000d2ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2b2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000d2b9  test    rax, rax
0x18000d2bc  jz      short loc_18000D2C8
0x18000d2be  lea     rcx, [rsp+1500h+var_14E0]
0x18000d2c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2c8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000d2cf  test    rax, rax
0x18000d2d2  jz      short loc_18000D2E5
0x18000d2d4  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000d2d9  jnz     short loc_18000D2E5
0x18000d2db  lea     rcx, [rsp+1500h+var_14E0]
0x18000d2e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2e5  cmp     [rsp+1500h+var_14D8], r12d
0x18000d2ea  jge     loc_18000D3F3
0x18000d2f0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000d2f7  jnz     short loc_18000D318
0x18000d2f9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000d300  test    rax, rax
0x18000d303  jz      short loc_18000D30E
0x18000d305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d30a  test    al, al
0x18000d30c  jmp     short loc_18000D316
0x18000d30e  call    cs:__imp_IsDebuggerPresent
0x18000d314  test    eax, eax
0x18000d316  jz      short loc_18000D31F
0x18000d318  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000d31d  jz      short loc_18000D345
0x18000d31f  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d326  test    rax, rax
0x18000d329  jz      short loc_18000D39E
0x18000d32b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000d332  jnz     short loc_18000D39E
0x18000d334  xor     r8d, r8d
0x18000d337  xor     edx, edx
0x18000d339  lea     rcx, [rsp+1500h+var_14E0]
0x18000d33e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d343  jmp     short loc_18000D39E
0x18000d345  mov     ebx, 800h
0x18000d34a  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d351  test    rax, rax
0x18000d354  jz      short loc_18000D373
0x18000d356  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000d35d  jnz     short loc_18000D373
0x18000d35f  mov     r8d, ebx
0x18000d362  lea     rdx, [rbp+1400h+OutputString]
0x18000d369  lea     rcx, [rsp+1500h+var_14E0]
0x18000d36e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d373  cmp     [rbp+1400h+OutputString], r12w
0x18000d37b  jnz     short loc_18000D391
0x18000d37d  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000d382  mov     rdx, rbx; wchar_t *
0x18000d385  lea     rcx, [rbp+1400h+OutputString]; this
0x18000d38c  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000d391  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000d398  call    cs:__imp_OutputDebugStringW
0x18000d39e  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000d3a3  jnz     short loc_18000D3AE
0x18000d3a5  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000d3ac  jz      short loc_18000D3C0
0x18000d3ae  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000d3b5  test    rax, rax
0x18000d3b8  jz      short loc_18000D3C0
0x18000d3ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3bf  nop
0x18000d3c0  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000d3c5  jnz     short loc_18000D3E8
0x18000d3c7  mov     rcx, [rbp+1400h+var_40]
0x18000d3ce  xor     rcx, rsp; StackCookie
0x18000d3d1  call    __security_check_cookie
0x18000d3d6  add     rsp, 14D0h
0x18000d3dd  pop     r15
0x18000d3df  pop     r14
0x18000d3e1  pop     r12
0x18000d3e3  pop     rdi
0x18000d3e4  pop     rsi
0x18000d3e5  pop     rbx
0x18000d3e6  pop     rbp
0x18000d3e7  retn
0x18000d3e8  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000d3ed  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000d3f3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
