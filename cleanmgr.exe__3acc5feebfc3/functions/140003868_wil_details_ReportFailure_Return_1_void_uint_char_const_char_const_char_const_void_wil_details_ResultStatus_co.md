# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140003868`
- end: `0x140003afe`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000353c`

## callees

- `0x1400029a0`
- `0x140003390`
- `0x140003868`
- `0x140004794`
- `0x1400058c0`
- `0x1400063a8`
- `0x140006564`
- `0x140017670`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003913`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003913`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003a98`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003a98`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003a0e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003a0e`

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
0x140003868  mov     [rsp-8+arg_10], rbx
0x14000386d  push    rbp
0x14000386e  push    rsi
0x14000386f  push    rdi
0x140003870  push    r14
0x140003872  push    r15
0x140003874  lea     rbp, [rsp-13D0h]
0x14000387c  mov     eax, 14D0h
0x140003881  call    _alloca_probe
0x140003886  sub     rsp, rax
0x140003889  mov     rax, cs:__security_cookie
0x140003890  xor     rax, rsp
0x140003893  mov     [rbp+13F0h+var_30], rax
0x14000389a  mov     esi, edx
0x14000389c  mov     r14, rcx
0x14000389f  mov     rdi, [rbp+13F0h+arg_28]
0x1400038a6  xor     edx, edx; Val
0x1400038a8  mov     r8d, 98h; Size
0x1400038ae  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1400038b3  call    memset_0
0x1400038b8  nop
0x1400038b9  xor     r15d, r15d
0x1400038bc  mov     [rbp+13F0h+OutputString], r15w
0x1400038c4  mov     [rbp+13F0h+var_1430], r15b
0x1400038c8  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1400038cf  mov     ecx, [rdx]; this
0x1400038d1  mov     [rsp+14F0h+var_14C8], ecx
0x1400038d5  mov     eax, [rdx+4]
0x1400038d8  mov     [rsp+14F0h+var_14C4], eax
0x1400038dc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400038e1  mov     ebx, eax
0x1400038e3  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1400038eb  mov     ecx, r15d
0x1400038ee  lea     eax, [r15+8]
0x1400038f2  cmp     dword ptr [rdx+8], 1
0x1400038f6  cmovz   ecx, eax
0x1400038f9  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1400038fd  lea     ecx, [rax-7]
0x140003900  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003908  inc     ecx
0x14000390a  mov     [rsp+14F0h+var_14C0], ecx
0x14000390e  mov     [rsp+14F0h+var_14B8], r15
0x140003913  call    cs:__imp_GetCurrentThreadId
0x140003919  mov     [rsp+14F0h+var_14B0], eax
0x14000391d  lea     rax, aWil; "wil"
0x140003924  mov     [rsp+14F0h+var_1498], rax
0x140003929  mov     [rsp+14F0h+var_1490], esi
0x14000392d  mov     [rsp+14F0h+var_148C], ebx
0x140003931  mov     [rsp+14F0h+var_14A8], r15
0x140003936  mov     [rsp+14F0h+var_14A0], r15
0x14000393b  mov     [rbp+13F0h+var_1448], rdi
0x14000393f  mov     [rbp+13F0h+var_1440], r14
0x140003943  mov     [rsp+14F0h+var_1488], r15
0x140003948  xorps   xmm0, xmm0
0x14000394b  xor     eax, eax
0x14000394d  movups  [rbp+13F0h+var_1468], xmm0
0x140003951  mov     [rbp+13F0h+var_1458], rax
0x140003955  xorps   xmm1, xmm1
0x140003958  movups  [rsp+14F0h+var_1480], xmm1
0x14000395d  mov     [rbp+13F0h+var_1470], rax
0x140003961  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003968  test    rax, rax
0x14000396b  jz      short loc_140003978
0x14000396d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003972  mov     [rbp+13F0h+var_1450], rax
0x140003976  jmp     short loc_14000397C
0x140003978  mov     [rbp+13F0h+var_1450], r15
0x14000397c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003983  test    rax, rax
0x140003986  jz      short loc_140003992
0x140003988  lea     rcx, [rsp+14F0h+var_14D0]
0x14000398d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003992  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140003999  test    rax, rax
0x14000399c  jz      short loc_1400039B2
0x14000399e  mov     r8d, 400h
0x1400039a4  lea     rdx, [rbp+13F0h+var_1430]
0x1400039a8  lea     rcx, [rsp+14F0h+var_14D0]
0x1400039ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400039b2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400039b9  test    rax, rax
0x1400039bc  jz      short loc_1400039C8
0x1400039be  lea     rcx, [rsp+14F0h+var_14D0]
0x1400039c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400039c8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400039cf  test    rax, rax
0x1400039d2  jz      short loc_1400039E5
0x1400039d4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400039d9  jnz     short loc_1400039E5
0x1400039db  lea     rcx, [rsp+14F0h+var_14D0]
0x1400039e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400039e5  cmp     [rsp+14F0h+var_14C8], r15d
0x1400039ea  jge     loc_140003AF8
0x1400039f0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1400039f7  jnz     short loc_140003A18
0x1400039f9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140003a00  test    rax, rax
0x140003a03  jz      short loc_140003A0E
0x140003a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003a0a  test    al, al
0x140003a0c  jmp     short loc_140003A16
0x140003a0e  call    cs:__imp_IsDebuggerPresent
0x140003a14  test    eax, eax
0x140003a16  jz      short loc_140003A1F
0x140003a18  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140003a1d  jz      short loc_140003A45
0x140003a1f  mov     rax, cs:g_pfnResultLoggingCallback
0x140003a26  test    rax, rax
0x140003a29  jz      short loc_140003A9E
0x140003a2b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140003a32  jnz     short loc_140003A9E
0x140003a34  xor     r8d, r8d
0x140003a37  xor     edx, edx
0x140003a39  lea     rcx, [rsp+14F0h+var_14D0]
0x140003a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003a43  jmp     short loc_140003A9E
0x140003a45  mov     ebx, 800h
0x140003a4a  mov     rax, cs:g_pfnResultLoggingCallback
0x140003a51  test    rax, rax
0x140003a54  jz      short loc_140003A73
0x140003a56  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140003a5d  jnz     short loc_140003A73
0x140003a5f  mov     r8d, ebx
0x140003a62  lea     rdx, [rbp+13F0h+OutputString]
0x140003a69  lea     rcx, [rsp+14F0h+var_14D0]
0x140003a6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003a73  cmp     [rbp+13F0h+OutputString], r15w
0x140003a7b  jnz     short loc_140003A91
0x140003a7d  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140003a82  mov     rdx, rbx; unsigned __int16 *
0x140003a85  lea     rcx, [rbp+13F0h+OutputString]; this
0x140003a8c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140003a91  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140003a98  call    cs:__imp_OutputDebugStringW
0x140003a9e  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140003aa3  jnz     short loc_140003AAE
0x140003aa5  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x140003aac  jz      short loc_140003AC0
0x140003aae  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003ab5  test    rax, rax
0x140003ab8  jz      short loc_140003AC0
0x140003aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003abf  nop
0x140003ac0  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140003ac5  jnz     short loc_140003AED
0x140003ac7  mov     rcx, [rbp+13F0h+var_30]
0x140003ace  xor     rcx, rsp; StackCookie
0x140003ad1  call    __security_check_cookie
0x140003ad6  mov     rbx, [rsp+14F0h+arg_10]
0x140003ade  add     rsp, 14D0h
0x140003ae5  pop     r15
0x140003ae7  pop     r14
0x140003ae9  pop     rdi
0x140003aea  pop     rsi
0x140003aeb  pop     rbp
0x140003aec  retn
0x140003aed  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140003af2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140003af8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
