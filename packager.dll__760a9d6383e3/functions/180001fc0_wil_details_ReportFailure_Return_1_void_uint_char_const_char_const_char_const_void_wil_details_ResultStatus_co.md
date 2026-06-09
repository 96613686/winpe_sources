# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180001fc0`
- end: `0x180002254`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180001aa8`

## callees

- `0x180001fc0`
- `0x180002dc4`
- `0x180003cb0`
- `0x1800045b0`
- `0x18000468c`
- `0x18000cbbe`
- `0x18000cbf0`
- `0x18000cc80`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000206a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000206a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800021ef`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800021ef`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002165`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002165`

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
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v18 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  v19 = 1;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v20 = v13;
  v24 = 0;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v25 = CurrentThreadId;
  v30 = v12;
  v28 = "wil";
  v35 = 0;
  v33 = 0;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x180001fc0  mov     [rsp-8+arg_10], rbx
0x180001fc5  push    rbp
0x180001fc6  push    rsi
0x180001fc7  push    rdi
0x180001fc8  push    r14
0x180001fca  push    r15
0x180001fcc  lea     rbp, [rsp-13D0h]
0x180001fd4  mov     eax, 14D0h
0x180001fd9  call    _alloca_probe
0x180001fde  sub     rsp, rax
0x180001fe1  mov     rax, cs:__security_cookie
0x180001fe8  xor     rax, rsp
0x180001feb  mov     [rbp+13F0h+var_30], rax
0x180001ff2  mov     rdi, [rbp+13F0h+arg_28]
0x180001ff9  mov     esi, edx
0x180001ffb  mov     r14, rcx
0x180001ffe  xor     edx, edx; Val
0x180002000  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002005  mov     r8d, 98h; Size
0x18000200b  call    memset_0
0x180002010  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180002017  xor     r15d, r15d
0x18000201a  mov     [rbp+13F0h+OutputString], r15w
0x180002022  mov     [rbp+13F0h+var_1430], r15b
0x180002026  mov     ecx, [rdx]; this
0x180002028  mov     eax, [rdx+4]
0x18000202b  mov     [rsp+14F0h+var_14C8], ecx
0x18000202f  mov     [rsp+14F0h+var_14C4], eax
0x180002033  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002038  cmp     dword ptr [rdx+8], 1
0x18000203c  mov     ebx, eax
0x18000203e  lea     eax, [r15+8]
0x180002042  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000204a  mov     ecx, r15d
0x18000204d  cmovz   ecx, eax
0x180002050  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002054  lea     ecx, [rax-7]
0x180002057  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000205f  inc     ecx
0x180002061  mov     [rsp+14F0h+var_14B8], r15
0x180002066  mov     [rsp+14F0h+var_14C0], ecx
0x18000206a  call    cs:__imp_GetCurrentThreadId
0x180002070  xorps   xmm0, xmm0
0x180002073  mov     [rsp+14F0h+var_1490], esi
0x180002077  mov     [rsp+14F0h+var_14B0], eax
0x18000207b  xorps   xmm1, xmm1
0x18000207e  lea     rax, aWil; "wil"
0x180002085  mov     [rsp+14F0h+var_148C], ebx
0x180002089  mov     [rsp+14F0h+var_1498], rax
0x18000208e  xor     eax, eax
0x180002090  mov     [rbp+13F0h+var_1458], rax
0x180002094  mov     [rbp+13F0h+var_1470], rax
0x180002098  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000209f  mov     [rsp+14F0h+var_14A8], r15
0x1800020a4  mov     [rsp+14F0h+var_14A0], r15
0x1800020a9  mov     [rbp+13F0h+var_1448], rdi
0x1800020ad  mov     [rbp+13F0h+var_1440], r14
0x1800020b1  mov     [rsp+14F0h+var_1488], r15
0x1800020b6  movups  [rbp+13F0h+var_1468], xmm0
0x1800020ba  movups  [rsp+14F0h+var_1480], xmm1
0x1800020bf  test    rax, rax
0x1800020c2  jz      short loc_1800020CF
0x1800020c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020c9  mov     [rbp+13F0h+var_1450], rax
0x1800020cd  jmp     short loc_1800020D3
0x1800020cf  mov     [rbp+13F0h+var_1450], r15
0x1800020d3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800020da  test    rax, rax
0x1800020dd  jz      short loc_1800020E9
0x1800020df  lea     rcx, [rsp+14F0h+var_14D0]
0x1800020e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020e9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800020f0  test    rax, rax
0x1800020f3  jz      short loc_180002109
0x1800020f5  mov     r8d, 400h
0x1800020fb  lea     rdx, [rbp+13F0h+var_1430]
0x1800020ff  lea     rcx, [rsp+14F0h+var_14D0]
0x180002104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002109  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002110  test    rax, rax
0x180002113  jz      short loc_18000211F
0x180002115  lea     rcx, [rsp+14F0h+var_14D0]
0x18000211a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000211f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002126  test    rax, rax
0x180002129  jz      short loc_18000213C
0x18000212b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002130  jnz     short loc_18000213C
0x180002132  lea     rcx, [rsp+14F0h+var_14D0]
0x180002137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000213c  cmp     [rsp+14F0h+var_14C8], r15d
0x180002141  jge     loc_180002243
0x180002147  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000214e  jnz     short loc_18000216F
0x180002150  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002157  test    rax, rax
0x18000215a  jz      short loc_180002165
0x18000215c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002161  test    al, al
0x180002163  jmp     short loc_18000216D
0x180002165  call    cs:__imp_IsDebuggerPresent
0x18000216b  test    eax, eax
0x18000216d  jz      short loc_180002176
0x18000216f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002174  jz      short loc_18000219C
0x180002176  mov     rax, cs:g_pfnResultLoggingCallback
0x18000217d  test    rax, rax
0x180002180  jz      short loc_1800021F5
0x180002182  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002189  jnz     short loc_1800021F5
0x18000218b  xor     r8d, r8d
0x18000218e  lea     rcx, [rsp+14F0h+var_14D0]
0x180002193  xor     edx, edx
0x180002195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000219a  jmp     short loc_1800021F5
0x18000219c  mov     rax, cs:g_pfnResultLoggingCallback
0x1800021a3  mov     ebx, 800h
0x1800021a8  test    rax, rax
0x1800021ab  jz      short loc_1800021CA
0x1800021ad  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800021b4  jnz     short loc_1800021CA
0x1800021b6  mov     r8d, ebx
0x1800021b9  lea     rdx, [rbp+13F0h+OutputString]
0x1800021c0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800021c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021ca  cmp     [rbp+13F0h+OutputString], r15w
0x1800021d2  jnz     short loc_1800021E8
0x1800021d4  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800021d9  mov     rdx, rbx; unsigned __int16 *
0x1800021dc  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800021e3  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800021e8  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800021ef  call    cs:__imp_OutputDebugStringW
0x1800021f5  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800021fa  jnz     short loc_180002205
0x1800021fc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180002203  jz      short loc_180002216
0x180002205  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000220c  test    rax, rax
0x18000220f  jz      short loc_180002216
0x180002211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002216  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000221b  jnz     short loc_180002249
0x18000221d  mov     rcx, [rbp+13F0h+var_30]
0x180002224  xor     rcx, rsp; StackCookie
0x180002227  call    __security_check_cookie
0x18000222c  mov     rbx, [rsp+14F0h+arg_10]
0x180002234  add     rsp, 14D0h
0x18000223b  pop     r15
0x18000223d  pop     r14
0x18000223f  pop     rdi
0x180002240  pop     rsi
0x180002241  pop     rbp
0x180002242  retn
0x180002243  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180002249  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000224e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
