# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180006e68`
- end: `0x18000710e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800068fc`

## callees

- `0x1800039f0`
- `0x1800043a8`
- `0x180006e68`
- `0x180009204`
- `0x18000aba8`
- `0x18000d1c0`
- `0x18000d438`
- `0x1800388e0`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f2e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800070ad`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800070ad`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007023`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007023`

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
0x180006e68  push    rbp
0x180006e6a  push    rbx
0x180006e6b  push    rsi
0x180006e6c  push    rdi
0x180006e6d  push    r12
0x180006e6f  push    r14
0x180006e71  push    r15
0x180006e73  lea     rbp, [rsp-13D0h]
0x180006e7b  mov     eax, 14D0h
0x180006e80  call    _alloca_probe
0x180006e85  sub     rsp, rax
0x180006e88  mov     rax, cs:__security_cookie
0x180006e8f  xor     rax, rsp
0x180006e92  mov     [rbp+1400h+var_40], rax
0x180006e99  mov     rsi, r8
0x180006e9c  mov     edi, edx
0x180006e9e  mov     rbx, rcx
0x180006ea1  mov     r14, [rbp+1400h+arg_28]
0x180006ea8  xor     edx, edx; Val
0x180006eaa  mov     r8d, 98h; Size
0x180006eb0  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180006eb5  call    memset_0
0x180006eba  nop
0x180006ebb  xor     r12d, r12d
0x180006ebe  mov     [rbp+1400h+OutputString], r12w
0x180006ec6  mov     [rbp+1400h+var_1440], r12b
0x180006eca  mov     rdx, [rbp+1400h+arg_30]; int
0x180006ed1  mov     ecx, [rdx]; this
0x180006ed3  mov     [rsp+1500h+var_14D8], ecx
0x180006ed7  mov     eax, [rdx+4]
0x180006eda  mov     [rsp+1500h+var_14D4], eax
0x180006ede  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006ee3  mov     r15d, eax
0x180006ee6  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180006eee  mov     ecx, r12d
0x180006ef1  lea     eax, [r12+8]
0x180006ef6  cmp     dword ptr [rdx+8], 1
0x180006efa  cmovz   ecx, eax
0x180006efd  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180006f01  lea     ecx, [rax-7]
0x180006f04  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006f0c  inc     ecx
0x180006f0e  mov     [rsp+1500h+var_14D0], ecx
0x180006f12  mov     rcx, [rbp+1400h+arg_38]
0x180006f19  test    rcx, rcx
0x180006f1c  jz      short loc_180006F29
0x180006f1e  cmp     [rcx], r12w
0x180006f22  mov     [rsp+1500h+var_14C8], rcx
0x180006f27  jnz     short loc_180006F2E
0x180006f29  mov     [rsp+1500h+var_14C8], r12
0x180006f2e  call    cs:__imp_GetCurrentThreadId
0x180006f34  mov     [rsp+1500h+var_14C0], eax
0x180006f38  mov     [rsp+1500h+var_14A8], rsi
0x180006f3d  mov     [rsp+1500h+var_14A0], edi
0x180006f41  mov     [rsp+1500h+var_149C], r15d
0x180006f46  mov     [rsp+1500h+var_14B8], r12
0x180006f4b  mov     [rsp+1500h+var_14B0], r12
0x180006f50  mov     [rbp+1400h+var_1458], r14
0x180006f54  mov     [rbp+1400h+var_1450], rbx
0x180006f58  mov     [rsp+1500h+var_1498], r12
0x180006f5d  xorps   xmm0, xmm0
0x180006f60  xor     eax, eax
0x180006f62  movups  [rbp+1400h+var_1478], xmm0
0x180006f66  mov     [rbp+1400h+var_1468], rax
0x180006f6a  xorps   xmm1, xmm1
0x180006f6d  movups  [rsp+1500h+var_1490], xmm1
0x180006f72  mov     [rbp+1400h+var_1480], rax
0x180006f76  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006f7d  test    rax, rax
0x180006f80  jz      short loc_180006F8D
0x180006f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f87  mov     [rbp+1400h+var_1460], rax
0x180006f8b  jmp     short loc_180006F91
0x180006f8d  mov     [rbp+1400h+var_1460], r12
0x180006f91  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006f98  test    rax, rax
0x180006f9b  jz      short loc_180006FA7
0x180006f9d  lea     rcx, [rsp+1500h+var_14E0]
0x180006fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fa7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006fae  test    rax, rax
0x180006fb1  jz      short loc_180006FC7
0x180006fb3  mov     r8d, 400h
0x180006fb9  lea     rdx, [rbp+1400h+var_1440]
0x180006fbd  lea     rcx, [rsp+1500h+var_14E0]
0x180006fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fc7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006fce  test    rax, rax
0x180006fd1  jz      short loc_180006FDD
0x180006fd3  lea     rcx, [rsp+1500h+var_14E0]
0x180006fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fdd  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006fe4  test    rax, rax
0x180006fe7  jz      short loc_180006FFA
0x180006fe9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180006fee  jnz     short loc_180006FFA
0x180006ff0  lea     rcx, [rsp+1500h+var_14E0]
0x180006ff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ffa  cmp     [rsp+1500h+var_14D8], r12d
0x180006fff  jge     loc_180007108
0x180007005  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000700c  jnz     short loc_18000702D
0x18000700e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007015  test    rax, rax
0x180007018  jz      short loc_180007023
0x18000701a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000701f  test    al, al
0x180007021  jmp     short loc_18000702B
0x180007023  call    cs:__imp_IsDebuggerPresent
0x180007029  test    eax, eax
0x18000702b  jz      short loc_180007034
0x18000702d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180007032  jz      short loc_18000705A
0x180007034  mov     rax, cs:g_pfnResultLoggingCallback
0x18000703b  test    rax, rax
0x18000703e  jz      short loc_1800070B3
0x180007040  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180007047  jnz     short loc_1800070B3
0x180007049  xor     r8d, r8d
0x18000704c  xor     edx, edx
0x18000704e  lea     rcx, [rsp+1500h+var_14E0]
0x180007053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007058  jmp     short loc_1800070B3
0x18000705a  mov     ebx, 800h
0x18000705f  mov     rax, cs:g_pfnResultLoggingCallback
0x180007066  test    rax, rax
0x180007069  jz      short loc_180007088
0x18000706b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180007072  jnz     short loc_180007088
0x180007074  mov     r8d, ebx
0x180007077  lea     rdx, [rbp+1400h+OutputString]
0x18000707e  lea     rcx, [rsp+1500h+var_14E0]
0x180007083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007088  cmp     [rbp+1400h+OutputString], r12w
0x180007090  jnz     short loc_1800070A6
0x180007092  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180007097  mov     rdx, rbx; unsigned __int16 *
0x18000709a  lea     rcx, [rbp+1400h+OutputString]; this
0x1800070a1  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800070a6  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800070ad  call    cs:__imp_OutputDebugStringW
0x1800070b3  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800070b8  jnz     short loc_1800070C3
0x1800070ba  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800070c1  jz      short loc_1800070D5
0x1800070c3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800070ca  test    rax, rax
0x1800070cd  jz      short loc_1800070D5
0x1800070cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070d4  nop
0x1800070d5  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800070da  jnz     short loc_1800070FD
0x1800070dc  mov     rcx, [rbp+1400h+var_40]
0x1800070e3  xor     rcx, rsp; StackCookie
0x1800070e6  call    __security_check_cookie
0x1800070eb  add     rsp, 14D0h
0x1800070f2  pop     r15
0x1800070f4  pop     r14
0x1800070f6  pop     r12
0x1800070f8  pop     rdi
0x1800070f9  pop     rsi
0x1800070fa  pop     rbx
0x1800070fb  pop     rbp
0x1800070fc  retn
0x1800070fd  lea     rcx, [rsp+1500h+var_14E0]; this
0x180007102  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180007108  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
