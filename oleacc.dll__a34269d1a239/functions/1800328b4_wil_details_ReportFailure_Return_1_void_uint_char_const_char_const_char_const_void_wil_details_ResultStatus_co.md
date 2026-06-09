# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800328b4`
- end: `0x180032b4a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800323bc`

## callees

- `0x18001e4c0`
- `0x18001efc4`
- `0x1800328b4`
- `0x180034b54`
- `0x180036dd0`
- `0x180038a60`
- `0x180038c18`
- `0x180047f80`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003295f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003295f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180032a5a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180032a5a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180032ae4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180032ae4`

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
0x1800328b4  mov     [rsp-8+arg_10], rbx
0x1800328b9  push    rbp
0x1800328ba  push    rsi
0x1800328bb  push    rdi
0x1800328bc  push    r14
0x1800328be  push    r15
0x1800328c0  lea     rbp, [rsp-13D0h]
0x1800328c8  mov     eax, 14D0h
0x1800328cd  call    _alloca_probe
0x1800328d2  sub     rsp, rax
0x1800328d5  mov     rax, cs:__security_cookie
0x1800328dc  xor     rax, rsp
0x1800328df  mov     [rbp+13F0h+var_30], rax
0x1800328e6  mov     esi, edx
0x1800328e8  mov     r14, rcx
0x1800328eb  mov     rdi, [rbp+13F0h+arg_28]
0x1800328f2  xor     edx, edx; Val
0x1800328f4  mov     r8d, 98h; Size
0x1800328fa  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800328ff  call    memset_0
0x180032904  nop
0x180032905  xor     r15d, r15d
0x180032908  mov     [rbp+13F0h+OutputString], r15w
0x180032910  mov     [rbp+13F0h+var_1430], r15b
0x180032914  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18003291b  mov     ecx, [rdx]; this
0x18003291d  mov     [rsp+14F0h+var_14C8], ecx
0x180032921  mov     eax, [rdx+4]
0x180032924  mov     [rsp+14F0h+var_14C4], eax
0x180032928  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18003292d  mov     ebx, eax
0x18003292f  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180032937  mov     ecx, r15d
0x18003293a  lea     eax, [r15+8]
0x18003293e  cmp     dword ptr [rdx+8], 1
0x180032942  cmovz   ecx, eax
0x180032945  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180032949  lea     ecx, [rax-7]
0x18003294c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180032954  inc     ecx
0x180032956  mov     [rsp+14F0h+var_14C0], ecx
0x18003295a  mov     [rsp+14F0h+var_14B8], r15
0x18003295f  call    cs:__imp_GetCurrentThreadId
0x180032965  mov     [rsp+14F0h+var_14B0], eax
0x180032969  lea     rax, aWil; "wil"
0x180032970  mov     [rsp+14F0h+var_1498], rax
0x180032975  mov     [rsp+14F0h+var_1490], esi
0x180032979  mov     [rsp+14F0h+var_148C], ebx
0x18003297d  mov     [rsp+14F0h+var_14A8], r15
0x180032982  mov     [rsp+14F0h+var_14A0], r15
0x180032987  mov     [rbp+13F0h+var_1448], rdi
0x18003298b  mov     [rbp+13F0h+var_1440], r14
0x18003298f  mov     [rsp+14F0h+var_1488], r15
0x180032994  xorps   xmm0, xmm0
0x180032997  xor     eax, eax
0x180032999  movups  [rbp+13F0h+var_1468], xmm0
0x18003299d  mov     [rbp+13F0h+var_1458], rax
0x1800329a1  xorps   xmm1, xmm1
0x1800329a4  movups  [rsp+14F0h+var_1480], xmm1
0x1800329a9  mov     [rbp+13F0h+var_1470], rax
0x1800329ad  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800329b4  test    rax, rax
0x1800329b7  jz      short loc_1800329C4
0x1800329b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800329be  mov     [rbp+13F0h+var_1450], rax
0x1800329c2  jmp     short loc_1800329C8
0x1800329c4  mov     [rbp+13F0h+var_1450], r15
0x1800329c8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800329cf  test    rax, rax
0x1800329d2  jz      short loc_1800329DE
0x1800329d4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800329d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800329de  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800329e5  test    rax, rax
0x1800329e8  jz      short loc_1800329FE
0x1800329ea  mov     r8d, 400h
0x1800329f0  lea     rdx, [rbp+13F0h+var_1430]
0x1800329f4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800329f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800329fe  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180032a05  test    rax, rax
0x180032a08  jz      short loc_180032A14
0x180032a0a  lea     rcx, [rsp+14F0h+var_14D0]
0x180032a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a14  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180032a1b  test    rax, rax
0x180032a1e  jz      short loc_180032A31
0x180032a20  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180032a25  jnz     short loc_180032A31
0x180032a27  lea     rcx, [rsp+14F0h+var_14D0]
0x180032a2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a31  cmp     [rsp+14F0h+var_14C8], r15d
0x180032a36  jge     loc_180032B44
0x180032a3c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180032a43  jnz     short loc_180032A64
0x180032a45  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180032a4c  test    rax, rax
0x180032a4f  jz      short loc_180032A5A
0x180032a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a56  test    al, al
0x180032a58  jmp     short loc_180032A62
0x180032a5a  call    cs:__imp_IsDebuggerPresent
0x180032a60  test    eax, eax
0x180032a62  jz      short loc_180032A6B
0x180032a64  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180032a69  jz      short loc_180032A91
0x180032a6b  mov     rax, cs:g_pfnResultLoggingCallback
0x180032a72  test    rax, rax
0x180032a75  jz      short loc_180032AEA
0x180032a77  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180032a7e  jnz     short loc_180032AEA
0x180032a80  xor     r8d, r8d
0x180032a83  xor     edx, edx
0x180032a85  lea     rcx, [rsp+14F0h+var_14D0]
0x180032a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a8f  jmp     short loc_180032AEA
0x180032a91  mov     ebx, 800h
0x180032a96  mov     rax, cs:g_pfnResultLoggingCallback
0x180032a9d  test    rax, rax
0x180032aa0  jz      short loc_180032ABF
0x180032aa2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180032aa9  jnz     short loc_180032ABF
0x180032aab  mov     r8d, ebx
0x180032aae  lea     rdx, [rbp+13F0h+OutputString]
0x180032ab5  lea     rcx, [rsp+14F0h+var_14D0]
0x180032aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032abf  cmp     [rbp+13F0h+OutputString], r15w
0x180032ac7  jnz     short loc_180032ADD
0x180032ac9  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180032ace  mov     rdx, rbx; unsigned __int16 *
0x180032ad1  lea     rcx, [rbp+13F0h+OutputString]; this
0x180032ad8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180032add  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180032ae4  call    cs:__imp_OutputDebugStringW
0x180032aea  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180032aef  jnz     short loc_180032AFA
0x180032af1  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180032af8  jz      short loc_180032B0C
0x180032afa  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180032b01  test    rax, rax
0x180032b04  jz      short loc_180032B0C
0x180032b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b0b  nop
0x180032b0c  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180032b11  jnz     short loc_180032B39
0x180032b13  mov     rcx, [rbp+13F0h+var_30]
0x180032b1a  xor     rcx, rsp; StackCookie
0x180032b1d  call    __security_check_cookie
0x180032b22  mov     rbx, [rsp+14F0h+arg_10]
0x180032b2a  add     rsp, 14D0h
0x180032b31  pop     r15
0x180032b33  pop     r14
0x180032b35  pop     rdi
0x180032b36  pop     rsi
0x180032b37  pop     rbp
0x180032b38  retn
0x180032b39  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180032b3e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180032b44  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
